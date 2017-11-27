---
title: Sincronizzare intestazioni e righe di ordini cliente direttamente da Finance and Operations in Sales
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente direttamente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Sincronizzare intestazioni e righe di ordini cliente direttamente da Finance and Operations in Sales

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente direttamente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.

[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe degli ordini cliente da Finance and Operations in Sales:

- **Nome del modello in Integrazione dati:** Ordini cliente (da Fin and Ops in Sales) - Diretto
- **Nomi delle attività nel progetto di Integrazione dati:**

    - OrderHeader
    - OrderLine

Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di fatture di vendita:

- Prodotti (da Fin and Ops in Sales) - Diretto
- Conti (da Sales in Fin and Ops) - Diretto (se utilizzata)
- Da Contatti a Clienti (da Sales in Fin and Ops) - Diretto (se utilizzata)

## <a name="entity-set"></a>Insieme di entità

| Finance and Operations  | Vendite             |
|-------------------------|-------------------|
| Intestazioni ordine cliente CDS | SalesOrders       |
| Righe ordine cliente CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Flusso di entità

Gli ordini cliente vengono creati in Finance and Operations e sincronizzati in Sales.

I filtri nel modello garantiscono che solo gli ordini cliente pertinenti sono inclusi nella sincronizzazione:

- Nell'ordine cliente, il cliente che richiede l'ordine e quello che emette la fattura originati da Sales saranno inclusi nella sincronizzazione. In Finance and Operations, i campi **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** sono utilizzati per tenere traccia della sincronizzazione nelle entità di dati.
- L'ordine cliente in Finance and Operations deve essere confermato. Solo gli ordini cliente confermati o gli ordini cliente con stato di elaborazione più elevato, ad esempio **Inviato** o **Fatturato** vengono sincronizzati in Sales.
- Dopo la creazione o la modifica di un ordine cliente, è necessario eseguire il processo batch **Calcola totali vendite** in Finance and Operations. Solo gli ordini cliente in cui vengono calcolati i totali delle vendite saranno sincronizzati in Sales.

> [!NOTE]
> L'imposta relativa alle spese nell'intestazione dell'ordine cliente non è attualmente inclusa nella sincronizzazione da Finance and Operations in Sales. Sales non supporta le informazioni fiscali a livello di intestazione. Tuttavia, l'imposta relativa alle spese a livello di riga è inclusa nella sincronizzazione.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

Nuovi campi sono stati aggiunti all'entità **Ordine** e visualizzati nella pagina:

- **Gestito esternamente** - Impostare questa opzione su **Sì** se l'ordine proviene da Finance and Operations.
- **Stato elaborazione** - Questo campo mostra lo stato di elaborazione dell'ordine in Finance and Operations. Sono disponibili i valori seguenti:

    - Attive
    - Confermata
    - Documento di trasporto
    - Fatturate
    - Prelevato
    - Prelevato in parte
    - Parzialmente imballato
    - Spedito
    - Parzialmente spedito
    - Parzialmente fatturato
    - Operazione annullata

L'impostazione **Solo prodotti gestiti esternamente** viene utilizzata in altri scenari per ordini cliente (ad esempio, sincronizzazione da Sales in Finance and Operation) per rilevare in modo coerente se un ordine cliente è composto interamente di prodotti gestiti esternamente. Se un ordine cliente include solo prodotti gestiti esternamente, i prodotti vengono gestiti in Finance and Operations. Questa impostazione impedisce il tentativo di sincronizzare righe dell'ordine cliente che hanno prodotti sconosciuti in Finance and Operations.

I pulsanti **Crea fattura**, **Annulla ordine**, **Ricalcola**, **Ottieni prodotti** e **Cerca indirizzo** della pagina **Ordine cliente** sono nascosti per gli ordini gestiti esternamente poiché le fatture verranno create in Finance and Operations e sincronizzate in Sales. La pagina degli ordini non è modificabile poiché le informazioni dell'ordine cliente verranno sincronizzate da Finance and Operations.

Lo stato di un ordine cliente rimarrà **Attivo** per garantire che le modifiche da Finance and Operations possano essere applicate all'ordine cliente in Sales. Per controllare questo comportamento, impostare il valore **Codice stato \[Stato\]** su **Attivo** nel progetto di Integrazione dati.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

Prima di sincronizzare gli ordini cliente, è importante aggiornare le impostazioni seguenti nei sistemi.

### <a name="setup-in-sales"></a>Impostazione in Sales

- Assicurarsi che le autorizzazioni siano impostate per il team a cui l'utente dal set di connessione in Sales viene assegnato. Se si utilizzano dati dimostrativi, in genere l'utente ha privilegi di amministratore, ma non il team. Se il team non dispone anche di privilegi di amministratore, quando si esegue il progetto da Integrazione dati, verrà visualizzato un messaggio di errore in cui viene indicato che il team principale è mancante.

    Andare a **Impostazioni** > **Sicurezza** > **Team**, selezionare il team pertinente, selezionare **Gestisci ruoli** e selezionare un ruolo con le autorizzazioni desiderate, ad esempio **Amministratore di sistema**.

- Andare a **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** e assicurarsi che:

    - L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.
    - Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.

### <a name="setup-in-finance-and-operations"></a>Impostazione in Finance and Operations

Andare a **Vendite e marketing** > **Attività periodiche** > **Calcola totali vendite** e impostare il processo da eseguire come processo batch. Impostare l'opzione **Calcola totali per ordini cliente** su **Sì**. Questo passaggio è importante perché solo gli ordini cliente con totali vendite calcolati verranno sincronizzati in Sales. La frequenza del processo batch deve essere in linea con la frequenza della sincronizzazione dell'ordine cliente.

### <a name="setup-in-the-data-integration-project"></a>Impostazione nel progetto di Integrazione dati

#### <a name="salesheader-task"></a>Attività SalesHeader

- Assicurarsi che il mapping necessario esista per **InvoiceCountryRegionId** a **BillingAddress\_Country** e per **DeliveryCountryRegionId** a **DeliveryAddress\_Country**.

    Il valore di modello è una mappa di valori dove vari paesi sono mappati.

- Un listino prezzi è necessario per creare ordini in Sales. Aggiornare la mappa di valori per **pricelevelid.name \[nome listino prezzi\]** al listino prezzi utilizzato in Sales per la valuta. È possibile utilizzare il listino prezzi predefinito per una singola valuta. In alternativa, se si hanno listini prezzi in più valute, è possibile utilizzare una mappa di valori.

    Il valore di modello predefinito per **pricelevelid.name \[nome listino prezzi\]** è **Servizio CRM USA (esempio)**.

#### <a name="salesline-task"></a>Attività SalesLine

- Assicurarsi che il mapping necessario esista per **DeliveryCountryRegionId** a **DeliveryAddress\_Country**.

    Il valore di modello è una mappa di valori dove vari paesi sono mappati.

- Assicurarsi che la mappa di valori richiesta esista per **SalesUnitSymbol** in Finance and Operations.

    Un valore di modello con una mappa di valori viene definito per **SalesUnitSymbol** a **Quantity\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

> [!NOTE]
> I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.

### <a name="orderheader"></a>OrderHeader

![Mapping dei modelli nell'integratore di dati](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a>OrderLine

![Mapping dei modelli nell'integratore di dati](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Argomenti correlati

[Prospect to cash](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales](products-template-mapping-direct.md)

[Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales](sales-invoice-template-mapping-direct.md)




