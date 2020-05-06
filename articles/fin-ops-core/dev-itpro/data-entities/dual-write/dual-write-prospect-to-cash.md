---
title: Prospect to cash in doppia scrittura
description: Questo argomento fornisce informazioni sul prospect to cash in doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 57aabeef0ee94b4b13bbe6e3925bcafe1e809ab2
ms.sourcegitcommit: 984604fd651d74aa49a2d7513f096faaf49f9f27
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2020
ms.locfileid: "3270290"
---
# <a name="prospect-to-cash-in-dual-write"></a>Prospect to cash in doppia scrittura

[!include [banner](../../includes/banner.md)]



Un obiettivo importante della maggior parte delle aziende è convertire i prospect in clienti e quindi mantenere un rapporto commerciale costante con tali clienti. Nelle app Microsoft Dynamics 365, il processo prospect to cash avviene tramite preventivi o flussi di lavoro di elaborazione degli ordini e i dati finanziari vengono riconciliati e riconosciuti. L'integrazione di prospect to cash con la doppia scrittura crea un flusso di lavoro che accetta un'offerta e un ordine che hanno origine in Dynamics 365 Sales o Dynamics 365 Supply Chain Management e rende disponibili le offerte e l'ordine in entrambe le app.

Nelle interfacce delle app, è possibile accedere agli stati di elaborazione e alle informazioni di fatturazione in tempo reale. Pertanto, è possibile gestire più facilmente funzioni come lo stoccaggio dei prodotti, la gestione delle scorte e l'evasione in Supply Chain Management, senza dover ricreare le offerte e gli ordini.

![Flusso di dati doppia scrittura in prospect to cash](../dual-write/media/dual-write-prospect-to-cash[1].png)

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

Prima di poter sincronizzare le offerte di vendita, è necessario aggiornare le seguenti impostazioni.

### <a name="setup-in-sales"></a>Impostazione in Sales

In Sales, andare a **Impostazioni \> Amministrazione \> Impostazioni di sistema \> Vendite** e assicurarsi che siano configurate le seguenti impostazioni:

- L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.
- Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.

### <a name="sites-and-warehouses"></a>Siti e magazzini

In Supply Chain Management, i campi **Sito** e **magazzino** sono obbligatori per le righe di offerta e le righe di ordine. Se si imposta il sito e il magazzino nelle impostazioni ordine predefinite, tali campi verranno automaticamente impostati quando si aggiunge un prodotto a una riga di offerta o a una riga di ordine. 

### <a name="number-sequences-for-quotations-and-orders"></a>Sequenze numeriche per offerte e ordini

Le sequenze numeriche per Supply Chain Management e Sales non sono connesse quando le offerte e gli ordini vengono creati e sincronizzati in Sales e Supply Chain Management. Se un ordine cliente creato in Sales è sincronizzato con Supply Chain Management, ha lo stesso numero di ordine di vendita in Supply Chain Management. Per garantire che il numero dell'ordine cliente non sia duplicato, è necessario utilizzare diversi sistemi di sequenza numerica nelle due app.

Ad esempio, la sequenza numerica in Supply Chain Management è **1, 2, 3, 4, 5, ...** e la sequenza numerica in Sales è **100, 99, 98, ...** . Se si creano 100 ordini cliente in Sales, verrà eventualmente generato un numero di ordine già esistente in Supply Chain Management. In altre parole, le due sequenze numeriche alla fine si sovrapporranno man mano che gli ordini cliente vengono creati in Supply Chain Management e Sales. Invece, è possibile usare una sequenza numerica come **F1, F2, F3, ...** in Supply Chain Management e una sequenza numerica come **C1, C2, C3, ...** in Sales. Queste sequenze numeriche non produrranno mai numeri duplicati degli ordini cliente.

## <a name="sales-quotations"></a>Offerte di vendita

Le offerte di vendita possono essere create in Sales o in Supply Chain Management. Se si crea un'offerta in Sales, viene sincronizzata con Supply Chain Management in tempo reale. Analogamente se si crea un'offerta in Supply Chain Management, viene sincronizzata con Sales in tempo reale. Notare i punti seguenti:

+ È possibile aggiungere uno sconto al prodotto sull'offerta. In questo caso, lo sconto verrà sincronizzato con Supply Chain Management. I campi **Sconto**, **Spese** e **Imposta** nell'intestazione sono controllati da un'impostazione in Supply Chain Management. Questa impostazione non supporta il mapping di integrazione. I campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti e mantenuti in Supply Chain Management.
+ I campi **% sconto**, **Sconto** e **Importo trasporto** nell'intestazione dell'offerta di vendita sono di sola lettura.
+ I campi **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Se si utilizza anche la soluzione Field Service, assicurarsi di riattivare il parametro della **riga di richiesta di offerta della creazione rapida**. La riattivazione del parametro consente di continuare a creare le righe di richiesta di offerta utilizzando la funzione di creazione rapida.
1. Passare all'applicazione Dynamics 365 Sales.
2. Seleziona l'icona delle impostazioni nella barra di navigazione in alto.
3. Selezionare **Impostazioni avanzate**.
4. Scegliere l'opzione **Personalizza il sistema**.
5. Selezionare la voce di menu **Riga richiesta di offerta**.
6. Andare alla sezione **Servizi dati** e selezionare la casella di controllo **Consenti creazione rapida**.

## <a name="sales-orders"></a>Gestione ordini cliente

Gli ordini cliente possono essere creati in Sales o in Supply Chain Management. Se si crea un ordine cliente in Sales, viene sincronizzato con Supply Chain Management in tempo reale. Analogamente se si crea un ordine cliente in Supply Chain Management, viene sincronizzato con Sales in tempo reale. Notare i punti seguenti:

+ È possibile attivare e sincronizzare gli ordini da Sales solo se tutti i prodotti dell'ordine provengono da app Finance and Operations. Di conseguenza, non possono includere prodotti fuori catalogo.
+ Calcolo e arrotondamento dello sconto:

    - Il modello di calcolo dello sconto in Sales differisce da quello in Supply Chain Management. In Supply Chain Management, l'importo di sconto finale in una riga di vendita può derivare da una combinazione di importi e percentuali di sconto. Se questo importo di sconto finale viene diviso per la quantità nella riga, è possibile che venga applicato l'arrotondamento. Tuttavia, questo arrotondamento non viene considerato se un importo di sconto per unità arrotondato viene sincronizzato in Sales. Per garantire la corretta sincronizzazione in Sales dell'intero importo di sconto da una riga di vendita in Supply Chain Management, l'intero importo deve essere sincronizzato senza essere diviso per la quantità della riga. Di conseguenza, è necessario definire il metodo di calcolo sconto come **Voce** in Sales.
    - Quando una riga dell'ordine cliente viene sincronizzata da Sales in Supply Chain Management, viene utilizzato l'intero importo di sconto riga. Poiché Supply Chain Management non include un campo in cui registrare l'intero importo di sconto per una riga, l'importo viene diviso per la quantità e registrato nel campo **Sconto riga**. Qualsiasi arrotondamento durante questa divisione viene registrato nel campo **Addebiti vendite** nella riga di vendita.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Esempio: Sincronizzazione da Sales a Supply Chain Management

È disponibile il seguente ordine cliente:

+ **Sales:** Quantità = 3, sconto per riga = $ 10,00
+ **Supply Chain Management:** Quantità = 3, importo di sconto riga = $3.33, addebito vendita = –$0.01

Se si esegue la sincronizzazione da Supply Chain Management a Sales, si ottiene il seguente risultato:

+ **Supply Chain Management:** Quantità = 3, importo di sconto riga = $3.33, addebito vendita = –$0.01
+ **Sales:** Quantità = 3, sconto per riga = (3 × $ 3,33) + $ 0,01 = $ 10,00

## <a name="dual-write-solution-for-sales"></a>Soluzione di doppia scrittura per Sales

Nuovi campi sono stati aggiunti all'entità **Ordine** e visualizzati nella pagina. La maggior parte di questi campi appare nella scheda **Integrazione** in Sales. Ci sono alcuni campi speciali:

+ Il campo **Stato elaborazione** mostra lo stato di elaborazione dell'ordine in Supply Chain Management. Questo campo è bloccato e mostra solo lo stato dell'ordine da Supply Chain Management. Sono disponibili i valori seguenti:

    + **Attivo** - Lo stato dopo che l'ordine viene attivato in Sales utilizzando il pulsante **Attiva**.
    + **Confermata**
    + **Consegnata**
    + **Fatturate**
    + **Consegnato in parte**
    + **Parzialmente fatturato**
    + **Prelevato**
    + **Annullata**

    La tabella seguente mostra come lo stato di elaborazione è mappato sul valore **Codice di stato CRM**.

    | Stato elaborazione           | Codice di stato CRM    |
    |-----------------------------|--------------------|
    | Attive                      | Nuovo/In sospeso/In attesa |
    | Confermato/Prelevato            | In corso        |
    | Consegnato in parte         | Parziale            |
    | Consegnata                   | Completati           |
    | Fatturato/Parzialmente fatturato | Fatturate           |
    | Annullata                    | Senza denaro           |

+ I pulsanti **Crea fattura** e **Annulla ordine** nella pagina **Ordine cliente** sono nascosti in Sales.
+ Il valore dello **stato dell'ordine cliente** rimarrà **attivo** per garantire che le modifiche da Supply Chain Management possano essere applicate all'ordine cliente in Sales. Per controllare questo comportamento, impostare il valore **Codice stato \[Stato\]** su **Attivo**.

## <a name="invoices"></a>Fatture

Le fatture di vendita vengono create in Supply Chain Management e sincronizzate in Sales. Notare i punti seguenti:

+ Un campo **Numero fattura** è stato aggiunto all'entità **Fattura** ed è visualizzato nella pagina.
+ Il pulsante **Crea fattura** nella pagina **Ordine cliente** è nascosto perché le fatture verranno create in Supply Chain Management e sincronizzate in Sales. La pagina **Fattura** non è modificabile poiché le fatture verranno sincronizzate da Supply Chain Management.
+ Il valore **Stato dell'ordine cliente** diventa automaticamente **Fatturato** dopo la sincronizzazione della fattura correlata da Supply Chain Management in Sales. Inoltre, il proprietario dell'ordine cliente da cui la fattura è stata creata viene assegnato come proprietario della fattura. Di conseguenza, il proprietario dell'ordine cliente può visualizzare la fattura.
+ I campi **Termini di trasporto**, **Termini di consegna** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

## <a name="templates"></a>Modelli

Prospect to cash include una raccolta di mappe di entità di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

| App di Finance and Operations | App basate su modello in Dynamics 365 | descrizione |
|-----------------------------|-----------------------------------|-------------|
| Intestazioni fattura di vendita V2    | fatture                          |             |
| Righe fattura di vendita V2      | invoicedetails                    |             |
| Intestazioni ordine cliente CDS     | salesorders                       |             |
| Righe ordine cliente CDS       | salesorderdetails                 |             |
| Codici origine ordine cliente    | msdyn\_salesorderorigins          |             |
| Intestazione offerta di vendita CDS  | offerte                            |             |
| Righe di offerta di vendita CDS   | quotedetails                      |             |

Ecco le mappe delle entità core correlate per prospect to cash:

+ [Clienti V3 per accounts](customer-mapping.md#customers-v3-to-accounts)
+ [Contatti CDS V2 per contacts](customer-mapping.md#cds-contacts-v2-to-contacts)
+ [Clienti V3 per contacts](customer-mapping.md#customers-v3-to-contacts)
+ [Prodotti V2 rilasciati per msdyn_sharedproductdetails](product-mapping.md#released-products-v2-to-msdyn_sharedproductdetails)
+ [Tutti i prodotti per msdyn_globalproducts](product-mapping.md#all-products-to-msdyn_globalproducts)
+ [Listino prezzi](product-mapping.md)

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [sales invoice](includes/SalesInvoiceHeaderV2Entity-invoice.md)]

[!include [sales invoice line](includes/SalesInvoiceLineV2Entity-invoicedetail.md)]

[!include [sales order header](includes/SalesOrderHeaderCDSEntity-salesorder.md)]

[!include [sales order line](includes/SalesOrderLineCDSEntity-salesorderdetails.md)]

[!include [sales order origin](includes/SalesOrderOriginEntity-msdyn-salesorderorigin.md)]

[!include [sales quotation header](includes/SalesQuotationHeaderCDSEntity-quote.md)]

[!include [sales quotation line](includes/SalesQuotationLineCDSEntity-QuoteDetails.md)]
