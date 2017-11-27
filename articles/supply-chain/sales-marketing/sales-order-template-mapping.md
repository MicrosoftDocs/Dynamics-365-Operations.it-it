---
title: Sincronizzare intestazioni e righe di ordini cliente da Finance and Operations in Sales
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a>Sincronizzare intestazioni e righe di ordini cliente da Finance and Operations in Sales

[!include[banner](../includes/banner.md)]

L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales. 

## <a name="template-and-tasks"></a>Modello e attività

I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe degli ordini cliente da Finance and Operations in Sales:

- **Nome del modello in Integrazione dati** 

    - Ordini cliente (da Fin and Ops in Sales)
    
- **Nomi delle attività nel progetto di Integrazione dati**

    - OrderHeader
    - OrderLine

Le attività di sincronizzazione necessarie prima di sincronizzare righe e intestazione della fattura di vendita:

- Prodotti (da Fin and Ops in Sales)
- Conti (da Sales in Fin and Ops) (se utilizzata)
- Da Contatti a Clienti (da Sales in Fin and Ops) (se utilizzata)

## <a name="entity-set"></a>Insieme di entità

| Finance and Operations |    Common Data Service (CDS)         |     Vendite      |
|------------------------|----------------|----------------|
| Intestazioni ordine cliente CDS| SalesOrder     | SalesOrders |
| Righe ordine cliente CDS  | SalesOrderLine | SalesOrderDetails|

## <a name="entity-flow"></a>Flusso di entità

Gli ordini cliente vengono creati in Finance and Operations e sincronizzati in Sales.

I filtri nel modello garantiscono che solo gli ordini cliente pertinenti sono inclusi nella sincronizzazione:

- Il cliente che richiede l'ordine e quello che emette la fattura indicati nell'ordine cliente generato in Sales saranno inclusi nella sincronizzazione. In Finance and Operations, i campi **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** sono utilizzati per tenere traccia della sincronizzazione nelle entità di dati.

- L'**ordine cliente** in Finance and Operations deve essere confermato. Solo gli ordini cliente confermati o gli ordini cliente con stato di elaborazione più elevato, ad esempio Inviato o Fatturato vengono sincronizzati in Sales.

- Dopo la creazione o la modifica di un ordine cliente, è necessario eseguire il processo batch **Calcola totali vendite** in Finance and Operations. Solo gli ordini cliente con totali delle vendite calcolati verranno sincronizzati in CDS e Sales.

> [!NOTE]
> L'imposta relativa alle spese nell'**intestazione dell'ordine cliente** non è attualmente inclusa nella sincronizzazione da Finance and Operations in Sales. Questo perché Sales non supporta le informazioni fiscali a livello di intestazione. È inclusa l'imposta relativa alle spese a livello di riga.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

Nuovi campi sono stati aggiunti all'entità **Ordine** e visualizzati nella pagina:

- **È gestito esternamente**: impostare su **Sì** se l'ordine proviene da Finance and Operations.

- **Stato elaborazione**: utilizzato per visualizzare lo stato di elaborazione dell'ordine in Finance and Operations. I valori sono:

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

L'impostazione **Ha solo prodotti gestiti esternamente** viene utilizzata in altri scenari (sincronizzazione da Sales in Finance and Operation) per determinare se l'ordine cliente è composto interamente di **prodotti gestiti esternamente**, nel qual caso i prodotti vengono gestiti in Finance and Operations. In questo modo, si impedisce la sincronizzazione delle righe degli ordini cliente con prodotti sconosciuti in Finance and Operations.
 
I pulsanti **Crea fattura**, **Annulla ordine**, **Ricalcola**, **Ottieni prodotti** e **Cerca indirizzo** della pagina **Ordine cliente** sono nascosti per gli ordini gestiti esternamente poiché le fatture verranno create in Finance and Operations e sincronizzate in Sales. La pagina dell'ordine non è modificabile poiché le informazioni dell'ordine cliente verranno sincronizzate da Finance and Operations.
 
Lo **stato dell'ordine cliente** rimarrà attivo per garantire che le modifiche da Finance and Operations possano essere applicate all'**ordine cliente** in Sales. Questo comportamento viene definito impostando il **codice di stato [stato]** su **Attivo** nel progetto di integrazione dei dati.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping 

Prima di sincronizzare gli ordini cliente, è importante aggiornare i sistemi con la seguente impostazione:

### <a name="setup-in-sales"></a>Impostazione in Sales

- Verificare le autorizzazioni per il team a cui l'utente viene assegnato (dal **set di connessione** in Sales). Se si utilizzano dati dimostrativi, in genere l'utente ha privilegi di amministratore, ma non il team. In tal caso, viene visualizzato un messaggio di errore indicante che il team principale è mancante quando si esegue il progetto dall'integratore di dati. 

    - In **Impostazioni** > **Sicurezza** > **Team**, selezionare il team pertinente, fare clic su **Gestisci ruoli** e selezionare un ruolo con le autorizzazioni desiderate, ad esempio Amministratore di sistema.

- In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Usa sistema di calcolo prezzi sistema** sia impostato su **Sì**. 

- In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Metodo di calcolo sconto** sia impostato su **Voce**. 

### <a name="setup-in-finance-and-operations"></a>Impostazione in Finance and Operations

Impostare **Vendite e marketing** > **Attività periodiche** > **Calcola totali vendite** per l'esecuzione come processo batch con **Calcola totali per ordini cliente** impostato su **Sì**. Cio è importante perché solo gli ordini cliente con totali vendite calcolati verranno sincronizzati in CDS e Sales. La frequenza del processo batch deve essere in linea con la frequenza della sincronizzazione dell'ordine cliente.

### <a name="setup-in-the-data-integration-project"></a>Impostazione nel progetto di Integrazione dati

#### <a name="salesheader-task"></a>Attività SalesHeader

- Aggiornare il mapping per **ID organizzazione CDS in Origine** > **CDS**.

    - Il valore del modello predefinito per **Account_Organization_OrganizationId** è ORG001.
    - Il valore del modello predefinito per **Account_Organization_OrganizationId** è ORG001.
    - Il valore del modello predefinito per **Organization_OrganizationId** è ORG001.

- Verificare che il mapping necessario esista in **Origine** > **CDS per InvoiceCountryRegionId a BillingAddress_Country** e per **DeliveryCountryRegionId a DeliveryAddress_Country**.

    - Il valore del modello è **ValueMap** con un numero di paesi mappati.

- Il **listino prezzi** è necessario per creare ordini in Sales. Aggiornare **ValueMap** in **CDS** > **Destinazione** per **pricelevelid.name [nome listino prezzi]** al **listino prezzi** utilizzato in Sales per la valuta. È possibile utilizzare il **listino prezzi** predefinito per una singola valuta oppure **ValueMap** se si hanno **listini prezzi** in molteplici valute.
    
    - Il valore del modello predefinito per **pricelevelid.name [nome listino prezzi]** è Servizio CRM USA (esempio). 

#### <a name="salesline-task"></a>Attività SalesLine

- Aggiornare il mapping per **ID organizzazione CDS in Origine** > **CDS**. 
    
    - Il valore del modello predefinito per **SalesOrder_Organization_OrganizationId** è ORG001.
    - Il valore del modello predefinito per **Product_Organization_OrganizationId** è ORG001.

- Verificare che il mapping necessario esista in **Origine** > **CDS** per **DeliveryCountryRegionId** a **DeliveryAddress_Country**.

    - Il valore del modello è **ValueMap** con un numero di paesi mappati.
    
- Assicurarsi che **ValueMap** per **SalesUnitSymbol** in Finance and Operations sia presente in **Origine** > **Mapping CDS**.

    - Il valore del modello con **ValueMap** è definito per **SalesUnitSymbol a Quantity_UOM**.

## <a name="template-mapping-in-data-integrator"></a>Mapping dei modelli nell'integratore di dati

> [!NOTE]
> I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.

### <a name="orderheader"></a>OrderHeader

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-1.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a>OrderLine

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-3.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Argomenti correlati

[Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales](products-template-mapping.md)

[Sincronizzare conti da Sales con clienti in Finance and Operations](accounts-template-mapping.md)

[Sincronizzare contatti da Sales con contatti o clienti in Finance and Operations](contacts-template-mapping.md)

[Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales](sales-invoice-template-mapping.md)


