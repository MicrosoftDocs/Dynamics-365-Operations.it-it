---
title: Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Finance and Operations
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: ChristianRytt
manager: AnnBe
ms.date: 11/14/2017
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 8a75c6dd91020ab3e676e2bb40d5c822731e244f
ms.contentlocale: it-it
ms.lasthandoff: 11/14/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a>Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Finance and Operations

[!include[banner](../includes/banner.md)]

L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrazione dati di Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

## <a name="template-and-tasks"></a>Modello e attività

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle offerte di vendita direttamente da Sales in Finance and Operations:

- **Nome del modello in Integrazione dati:** Offerte di vendita (da Sales in Fin and Ops) - Diretto
- **Nomi delle attività nel progetto di Integrazione dati:**

    - QuoteHeader
    - QuoteLine

Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di un'offerta di vendita:

- Prodotti (da Fin and Ops in Sales) - Diretto
- Conti (da Sales in Fin and Ops) - Diretto (se utilizzata)
- Da Contatti a Clienti (da Sales in Fin and Ops) - Diretto (se utilizzata)

## <a name="entity-set"></a>Insieme di entità

| Vendite        | Finance and Operations     |
|--------------|----------------------------|
| Citazioni       | Intestazione offerta di vendita CDS |
| QuoteDetails | Righe di offerta di vendita CDS  |

## <a name="entity-flow"></a>Flusso di entità

Le offerte di vendita vengono create in Sales e sincronizzate in Finance and Operations.

Le offerte di vendita da Sales vengono sincronizzate solo se vengono soddisfatte le condizioni seguenti:

- Tutti i prodotti offerta nelle righe dell'offerta di vendita sono gestiti esternamente.
- Dopo aver fatto clic su **Attiva offerta**, l'offerta di vendita è attiva.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

È stato aggiunto il campo **Solo prodotti gestiti esternamente** all'entità **Offerta** per rilevare in modo coerente se l'offerta di vendita consiste interamente di prodotti gestiti esternamente. Se un'offerta di vendita include solo prodotti gestiti esternamente, i prodotti vengono gestiti in Finance and Operations. Questo comportamento impedisce il tentativo di sincronizzare righe di offerta di vendita che hanno prodotti sconosciuti in Finance and Operations.

Tutti i prodotti offerta e l'offerta di vendita vengono aggiornati con le informazioni **Solo prodotti gestiti esternamente** derivate dall'intestazione dell'offerta di vendita. Queste informazioni sono disponibili nel campo **L'offerta ha solo prodotti gestiti esternamente** nell'entità **QuoteDetails**.

Uno sconto può essere aggiunto al prodotto offerta e verrà sincronizzato con Finance and Operations. I campi **Sconto**, **Spese** e **Imposta** nell'intestazione sono controllati da un'impostazione in Finance and Operations. Questa impostazione al momento non supporta il mapping di integrazione. Nella progettazione attuale, i campi **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti in Finance and Operations.

In Sales, la soluzione rende i campi seguenti di sola lettura, perché i valori non vengono sincronizzati con Finance and Operations:

- Campi di sola lettura nell'intestazione dell'offerta di vendita: **% sconto**, **Sconto**, **Importo trasporto**
- Campi di sola lettura nei prodotti offerta: **Imposta**

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

Prima di sincronizzare le offerte di vendita, è importante aggiornare le seguenti impostazioni.

### <a name="setup-in-sales"></a>Impostazione in Sales

- Assicurarsi che le autorizzazioni siano impostate per il team a cui l'utente nel set di connessione in Sales viene assegnato. Se si utilizzano dati dimostrativi, in genere l'utente ha privilegi di amministratore, ma non il team. Se il team non dispone di privilegi di amministratore quando si esegue il progetto da Integrazione dati, verrà visualizzato un messaggio di errore in cui viene indicato che il team principale è mancante.

    Per impostare le autorizzazioni per il team, andare a **Impostazioni** &gt; **Sicurezza** &gt; **Team** e selezionare il team pertinente. Selezionare **Gestisci ruoli** e quindi selezionare un ruolo che dispone delle autorizzazioni appropriate, ad esempio **Amministratore di sistema**.

- Andare a **Impostazioni** &gt; **Amministrazione** &gt; **Impostazioni di sistema** &gt; **Vendite** e assicurarsi che:

    - L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.
    - Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.

### <a name="setup-in-the-data-integration-project"></a>Impostazione nel progetto di Integrazione dati

#### <a name="quoteheader"></a>QuoteHeader

- Assicurarsi che il mapping necessario esista per **Shipto\_country** a **DeliveryAddressCountryRegionISOCode**. Nella mappa di valori, è possibile definire un valore predefinito utilizzato se il valore è vuoto. Lasciare la parte sinistra vuota e impostare la parte destra sul paese desiderato. In questo modo, non sarà necessario immettere il paese per gli ordini nazionali.

    Il valore di modello è una mappa di valori dove vari paesi vengono mappati e dove un valore vuoto equivale a **Stati Uniti**.

#### <a name="quoteline"></a>QuoteLine

- Assicurarsi che la mappa valori richiesta esista per **SalesUnitSymbol** in Finance and Operations.
- Assicurarsi che le unità richieste siano definite in Sales.

    Un valore di modello con una mappa di valori viene definito per **oumid.name** a **SalesUnitSymbol**.

- Facoltativo: è possibile aggiungere i mapping seguenti in modo da garantire che le righe dell'offerta di vendita vengano importate in Finance and Operations se non sono disponibili informazioni predefinite dal cliente o dal prodotto:

    - **SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations. Non è disponibile alcun valore del modello predefinito per **SiteId**.
    - **WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations. Non è disponibile alcun valore del modello predefinito per **WarehouseId**.

## <a name="template-mapping-in-data-integrator"></a>Mapping dei modelli nell'integratore di dati

> [!NOTE]
> - I campi relativi a **Sconto**, **Spese** e **Imposta** sono controllati da un'impostazione complessa in Finance and Operations. Questa impostazione al momento non supporta il mapping di integrazione. Nella progettazione attuale, i campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti da Finance and Operations.
> - I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.

### <a name="quoteheader"></a>QuoteHeader

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Argomenti correlati

[Prospect to cash](prospect-to-cash.md)


