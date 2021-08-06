---
title: Prospect to cash in doppia scrittura
description: Questo argomento fornisce informazioni sul prospect to cash in doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 0fcbc5b0f571e9f2cf7f1ad7c1e976d022199b47
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542273"
---
# <a name="prospect-to-cash-in-dual-write"></a>Prospect to cash in doppia scrittura

[!include [banner](../../includes/banner.md)]

Un obiettivo importante della maggior parte delle aziende è convertire i prospect in clienti e quindi mantenere un rapporto commerciale costante con tali clienti. Nelle app Microsoft Dynamics 365, il processo prospect to cash avviene tramite preventivi o flussi di lavoro di elaborazione degli ordini e i dati finanziari vengono riconciliati e riconosciuti. L'integrazione di prospect to cash con la doppia scrittura crea un flusso di lavoro che accetta un'offerta e un ordine che hanno origine in Dynamics 365 Sales o Dynamics 365 Supply Chain Management e rende disponibili le offerte e l'ordine in entrambe le app.

Nelle interfacce delle app, è possibile accedere agli stati di elaborazione e alle informazioni di fatturazione in tempo reale. Pertanto, è possibile gestire più facilmente funzioni come lo stoccaggio dei prodotti, la gestione delle scorte e l'evasione in Supply Chain Management, senza dover ricreare le offerte e gli ordini.

![Flusso di dati in doppia scrittura da prospect a contanti.](../dual-write/media/dual-write-prospect-to-cash[1].png)

Per informazioni sull'integrazione di clienti e contatti, vedere [Gestione integrata dei dati dei clienti](customer-mapping.md). Per informazioni sull'integrazione del prodotto, vedere [Esperienza prodotto unificata](product-mapping.md).

> [!NOTE]
> In Dynamics 365 Sales, sia il prospect che il cliente fanno riferimento a un record nella tabella **Account** dove la colonna **RelationshipType** è **Prospect** o **Cliente**. Se la tua logica aziendale include un processo di qualidica **Account** in cui il record **Account** viene creato e qualificato come prospect prima e poi come cliente, quel record si sincronizza con l'app Finance and Operations solo quando è un cliente (`RelationshipType=Customer`). Se desideri che la riga **Account** venga sincronizzata come prospecr, è necessaria una mappa personalizzata per integrare i dati del prospect.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

Prima di poter sincronizzare le offerte di vendita, è necessario aggiornare le seguenti impostazioni.

### <a name="setup-in-sales"></a>Impostazione in Sales

In Sales, andare a **Impostazioni \> Amministrazione \> Impostazioni di sistema \> Vendite** e assicurarsi che siano configurate le seguenti impostazioni:

- L'opzione di sistema **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.
- La colonna **Metodo di calcolo sconto** sia impostato su **Voce**.

### <a name="sites-and-warehouses"></a>Siti e magazzini

In Supply Chain Management, le colonne **Sito** e **magazzino** sono obbligatorie per le righe di offerta e le righe di ordine. Se si imposta il sito e il magazzino nelle impostazioni ordine predefinite, tali colonne verranno automaticamente impostati quando si aggiunge un prodotto a una riga di offerta o a una riga di ordine. 

### <a name="number-sequences-for-quotations-and-orders"></a>Sequenze numeriche per offerte e ordini

Le sequenze numeriche per Supply Chain Management e Sales non sono connesse quando le offerte e gli ordini vengono creati e sincronizzati in Sales e Supply Chain Management. Se un ordine cliente creato in Sales è sincronizzato con Supply Chain Management, ha lo stesso numero di ordine di vendita in Supply Chain Management. Per garantire che il numero dell'ordine cliente non sia duplicato, è necessario utilizzare diversi sistemi di sequenza numerica nelle due app.

Ad esempio, la sequenza numerica in Supply Chain Management è **1, 2, 3, 4, 5, ...** e la sequenza numerica in Sales è **100, 99, 98, ...** . Se si creano 100 ordini cliente in Sales, verrà eventualmente generato un numero di ordine già esistente in Supply Chain Management. In altre parole, le due sequenze numeriche alla fine si sovrapporranno man mano che gli ordini cliente vengono creati in Supply Chain Management e Sales. Invece, è possibile usare una sequenza numerica come **F1, F2, F3, ...** in Supply Chain Management e una sequenza numerica come **C1, C2, C3, ...** in Sales. Queste sequenze numeriche non produrranno mai numeri duplicati degli ordini cliente.

## <a name="sales-quotations"></a>Offerte di vendita

Le offerte di vendita possono essere create in Sales o in Supply Chain Management. Se si crea un'offerta in Sales, viene sincronizzata con Supply Chain Management in tempo reale. Analogamente se si crea un'offerta in Supply Chain Management, viene sincronizzata con Sales in tempo reale. Notare i punti seguenti:

+ È possibile aggiungere uno sconto al prodotto sull'offerta. In questo caso, lo sconto verrà sincronizzato con Supply Chain Management. Le colonne **Sconto**, **Spese** e **Imposta** nell'intestazione sono controllati da un'impostazione in Supply Chain Management. Questa impostazione non supporta il mapping di integrazione. Le colonne relative a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestite e mantenute in Supply Chain Management.
+ Le colonne **% sconto**, **Sconto** e **Importo trasporto** nell'intestazione dell'offerta di vendita sono di sola lettura.
+ Le colonne **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono incluse nei mapping predefiniti. Per mappare queste colonne, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui la tabella viene sincronizzata.

Se si utilizza anche la soluzione Field Service, assicurarsi di riattivare il parametro della **riga di richiesta di offerta della creazione rapida**. La riattivazione del parametro consente di continuare a creare le righe di richiesta di offerta utilizzando la funzione di creazione rapida.

1. Passare all'applicazione Dynamics 365 Sales.
2. Seleziona l'icona delle impostazioni nella barra di navigazione in alto.
3. Selezionare **Impostazioni avanzate**.
4. Scegliere l'opzione **Personalizza il sistema**.
5. Selezionare la voce di menu **Riga richiesta di offerta**.
6. Andare alla sezione **Servizi dati** e selezionare la casella di controllo **Consenti creazione rapida**.

## <a name="sales-orders"></a>Gestione ordini cliente

Gli ordini cliente possono essere creati in Sales o in Supply Chain Management. Se si crea un ordine cliente in Sales, viene sincronizzato con Supply Chain Management in tempo reale. Analogamente se si crea un ordine cliente in Supply Chain Management, viene sincronizzato con Sales in tempo reale. Notare i punti seguenti:

+ I prodotti per scrittura in Dynamics 365 Sales verranno visualizzati come categorie di prodotti in Dynamics 365 Supply Chain Management.
+ Calcolo e arrotondamento dello sconto:

    - Il modello di calcolo dello sconto in Sales differisce da quello in Supply Chain Management. In Supply Chain Management, l'importo di sconto finale in una riga di vendita può derivare da una combinazione di importi e percentuali di sconto. Se questo importo di sconto finale viene diviso per la quantità nella riga, è possibile che venga applicato l'arrotondamento. Tuttavia, questo arrotondamento non viene considerato se un importo di sconto per unità arrotondato viene sincronizzato in Sales. Per garantire la corretta sincronizzazione in Sales dell'intero importo di sconto da una riga di vendita in Supply Chain Management, l'intero importo deve essere sincronizzato senza essere diviso per la quantità della riga. Di conseguenza, è necessario definire il metodo di calcolo sconto come **Voce** in Sales.
    - Quando una riga dell'ordine cliente viene sincronizzata da Sales in Supply Chain Management, viene utilizzato l'intero importo di sconto riga. Poiché Supply Chain Management non include una colonna in cui registrare l'intero importo di sconto per una riga, l'importo viene diviso per la quantità e registrato nella colonna **Sconto riga**. Qualsiasi arrotondamento durante questa divisione viene registrato nella colonna **Addebiti vendite** nella riga di vendita.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Esempio: Sincronizzazione da Sales a Supply Chain Management

È disponibile il seguente ordine cliente:

+ **Sales:** Quantità = 3, sconto per riga = $ 10,00
+ **Supply Chain Management:** Quantità = 3, importo di sconto riga = $3.33, addebito vendita = –$0.01

Se si esegue la sincronizzazione da Supply Chain Management a Sales, si ottiene il seguente risultato:

+ **Supply Chain Management:** Quantità = 3, importo di sconto riga = $3.33, addebito vendita = –$0.01
+ **Sales:** Quantità = 3, sconto per riga = (3 × $ 3,33) + $ 0,01 = $ 10,00

## <a name="dual-write-solution-for-sales"></a>Soluzione di doppia scrittura per Sales

Nuove colonne sono state aggiunte alla tabella **Ordine** e visualizzati nella pagina. La maggior parte di queste colonne appare nella scheda **Integrazione** in Sales. Per ulteriori informazioni su come vengono mappate le colonne di stato, vedere [Configurare il mapping per le colonne di stato dell'ordine cliente](sales-status-map.md).

+ I pulsanti **Crea fattura** e **Annulla ordine** nella pagina **Ordine cliente** sono nascosti in Sales.
+ Il valore dello **stato dell'ordine cliente** rimarrà **attivo** per garantire che le modifiche da Supply Chain Management possano essere applicate all'ordine cliente in Sales. Per controllare questo comportamento, impostare il valore **Codice stato \[Stato\]** su **Attivo**.

## <a name="invoices"></a>Fatture

Le fatture di vendita vengono create in Supply Chain Management e sincronizzate in Sales. Notare i punti seguenti:

+ Un colonna **Numero fattura** è stato aggiunto alla tabella **Fattura** ed è visualizzato nella pagina.
+ Il pulsante **Crea fattura** nella pagina **Ordine cliente** è nascosto perché le fatture verranno create in Supply Chain Management e sincronizzate in Sales. La pagina **Fattura** non è modificabile poiché le fatture verranno sincronizzate da Supply Chain Management.
+ Il valore **Stato dell'ordine cliente** diventa automaticamente **Fatturato** dopo la sincronizzazione della fattura correlata da Supply Chain Management in Sales. Inoltre, il proprietario dell'ordine cliente da cui la fattura è stata creata viene assegnato come proprietario della fattura. Di conseguenza, il proprietario dell'ordine cliente può visualizzare la fattura.
+ Le colonne **Termini di trasporto**, **Termini di consegna** e **Modalità di consegna** non vengono incluse nei mapping predefiniti. Per mappare queste colonne, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui la tabella viene sincronizzata.

## <a name="templates"></a>Modelli

Prospect per uno scenario di liquidazione include una raccolta di mappe della tabella di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

| App di Finance and Operations | App di interazione con i clienti | descrizione |
|-----------------------------|-----------------------------------|-------------|
[Tutti i prodotti](mapping-reference.md#138) | msdyn_globalproducts | |
[Clienti V3](mapping-reference.md#101) | conti | |
[Clienti V3](mapping-reference.md#116) | contatti | |
[Contatti V2](mapping-reference.md#221) | msdyn_contactforparties | |
[Intestazioni ordine cliente CDS](mapping-reference.md#217) | salesorders | |
[Righe ordine cliente CDS](mapping-reference.md#216) | salesorderdetails | |
[Intestazione offerta di vendita CDS](mapping-reference.md#215) | offerte | |
[Righe di offerta di vendita CDS](mapping-reference.md#214) | quotedetails | |
[Prodotti rilasciati V2](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[Intestazioni fattura di vendita V2](mapping-reference.md#118) | fatture | La tabella delle intestazioni delle fatture di vendita V2 nell'app Finance and Operations contiene fatture per ordini cliente e fatture a testo libero. Viene applicato un filtro in Dataverse per la doppia scrittura che filtrerà qualsiasi documento di fattura a testo libero. |
[Righe fattura di vendita V2](mapping-reference.md#117) | invoicedetails | |
[Codici origine ordine cliente](mapping-reference.md#186) | msdyn_salesorderorigins | |

Per informazioni sui listini prezzi vedi [Esperienza prodotto unificata](product-mapping.md).

## <a name="limitations"></a>Limiti

- Gli ordini di reso non sono supportati.
- Le note di credito non sono supportate.
- Le dimensioni finanziarie devono essere impostate per i dati master, ad esempio, cliente e fornitore. Quando un cliente viene aggiunto a un'offerta o a un ordine cliente, le dimensioni finanziarie associate al record del cliente fluiscono automaticamente nell'ordine. Attualmente la doppia scrittura non include i dati sulle dimensioni finanziarie per i dati master.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
