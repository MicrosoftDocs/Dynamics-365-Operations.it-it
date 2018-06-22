---
title: Sincronizzare le stime di progetto in Project Service Automation direttamente con le previsioni di progetto di Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le stime orarie di progetto e le stime di spesa del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: it-it
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a>Sincronizzare le stime di progetto in Project Service Automation direttamente con le previsioni di progetto di Finance and Operations

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le stime orarie di progetto e le stime di spesa del progetto direttamente da Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.

> [!NOTE]
> L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Dynamics 365 for Finance and Operations versione 8.0.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flusso di dati per Project Service Automation verso Finance and Operations

La soluzione di integrazione di Project Service Automation in Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle stime orarie e di spesa del progetto da Project Service Automation a Finance and Operations.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)


## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le stime orarie di progetto da Project Service Automation a Finance and Operations:

-  **Nome del modello in Integrazione dati:** Stime orarie di progetto (da PSA a Fin and Ops)

-  **Nome delle attività del progetto:** 
    - Relazioni tra transazioni 
    - Stime di spesa

## <a name="entity-set"></a>Insieme di entità

| Project Service Automation      | Finance and Operations                          |
|---------------------------------|-------------------------------------------------|
| Attività di progetto                   | Entità di integrazione per stime orarie del progetto   |

## <a name="entity-flow"></a>Flusso di entità

Le stime orarie di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance and Operations come previsioni orarie di progetto.

## <a name="preconditions"></a>Condizioni preliminari

Prima di eseguire la sincronizzazione delle stime delle ore di progetto, è necessario sincronizzare i progetti, le attività di progetto e le categorie di transazioni di spesa del progetto.

## <a name="power-query"></a>Power Query

È necessario utilizzare Microsoft Power Query nel modello delle stime orarie di progetto per:
- Impostare l'**ID modello previsionale** da utilizzare quando l'integrazione crea nuove previsioni orarie.
- Filtrare tutti i record specifici delle risorse nell'attività che impediranno l'integrazione nelle previsioni orarie
- Filtrare tutte le righe vuote di categoria di transazione. In caso contrario, le previsioni orarie potrebbero risultare errate.

### <a name="forecast-model-id"></a>ID modello previsionale
Per aggiornare l'ID di modello previsionale predefinito nel modello, fare clic sulla freccia **Mappa** per aprire il mapping. Selezionare per aprire Query avanzata e Filtro avanzato.
- Se si utilizza il modello predefinito delle stime orarie di Microsoft Project (da PSA a Fin and Ops), selezionare l'ultima **Condizione inserita** nella sezione **Passaggi applicati**. Nella voce **Funzione** sostituire **O_forecast** con il nome dell'**ID modello previsionale** da utilizzare con l'integrazione. Il modello predefinito include un ID modello previsionale proveniente dai dati dimostrativi.
- Se si crea un nuovo modello, è necessario aggiungere questa colonna. Selezionare **Aggiungi colonna condizionale** e assegnare un nome alla colonna, ad esempio ModelID. Inserire la condizione per la colonna dove se Inserire la condizione per la colonna dove se Attività progetto non è null, allora <enter the forecast model ID>; altrimenti null.

### <a name="filter-out-resource-specific-records"></a>Filtrare i record specifici delle risorse
Il modello delle stime orarie di progetto (da PSA a Fin and Ops) include un filtro predefinito che rimuove qualsiasi record specifico di risorsa. Se si crea un modello personale, è necessario aggiungere questo filtro. Nel modulo di Query e filtro avanzati, selezionare per filtrare la colonna **msdyn_islinetask** per includere solo i record **False**.

### <a name="filter-out-empty-transaction-category-rows"></a>Filtrare le righe vuote di categoria di transazione
È necessario aggiungere un filtro per rimuovere tutte le righe con categorie di transazione vuote. Questa impostazione è necessaria indipendentemente che si utilizzi il modello predefinito o che se crei uno nuovo. Questo filtro rimuoverà tutte le righe di riepilogo provenienti da Project Service Automation che potrebbero generare errori nelle previsioni orarie di Finance and Operations. Nel modulo di Query e filtro avanzati, selezionare per filtrare i record null nella colonna **msdyn_transactioncategory_value**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le stime di spesa di progetto da Project Service Automation a Finance and Operations:

-  **Nome del modello in Integrazione dati:** Stime di spesa di progetto (da PSA a Fin and Ops)
-  **Nome delle attività del progetto:** 
     - Relazioni tra transazioni 
     - Stime di spesa

## <a name="entity-set"></a>Insieme di entità

| Project Service Automation      | Finance and Operations                                     |
|---------------------------------|------------------------------------------------------------|
| Connessioni delle transazioni         | Entità di integrazione per relazioni tra transazioni del progetto   |
| Righe di stima                  | Entità di integrazione per stime di spesa del progetto           |

## <a name="entity-flow"></a>Flusso di entità

Le stime di spesa di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance and Operations come previsioni di spesa di progetto.

## <a name="prerequisites"></a>Prerequisiti

Prima di eseguire la sincronizzazione delle stime di spesa di progetto, è necessario sincronizzare i progetti, le attività di progetto e le categorie di transazioni di spesa del progetto.

## <a name="power-query"></a>Power Query

È necessario utilizzare Microsoft Power Query nel modello delle stime di spesa di progetto per:
- Filtrare per includere solo i record riga di stima delle spese
- Impostare l'**ID modello previsionale** da utilizzare quando l'integrazione crea nuove previsioni orarie.
- Trasformare i tipi di fatturazione.
- Trasformare i tipi di transazione.

### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrare per includere solo le righe di stima delle spese
Il modello di stima delle spese di progetto (da PSA a Fin and Ops) include un filtro predefinito per includere sono righe di spesa nell'integrazione. Se si crea un modello personale, è necessario aggiungere questo filtro. Selezionare l'attività Relazioni tra transazioni e fare clic sulla freccia **Mappa**. Selezionare **Query e filtro avanzati**. Filtrare la colonna **msdyn_transactiontype1** per includere solo **msdyn_estimateline**.

### <a name="forecast-model-id"></a>ID modello previsionale
Per aggiornare l'ID modello previsionale predefinito nel modello, per l'attività Stime di spesa, fare clic sulla freccia **Mappa** per aprire il mapping. Selezionare per aprire Query avanzata e Filtro avanzato.
- Se si utilizza il modello predefinito delle stime di spesa di Microsoft Project (da PSA a Fin and Ops), selezionare la prima **Condizione inserita** nella sezione **Passaggi applicati**. Nella voce **Funzione** sostituire **O_forecast** con il nome dell'**ID modello previsionale** da utilizzare con l'integrazione. Il modello predefinito include un ID modello previsionale proveniente dai dati dimostrativi.
- Se si crea un nuovo modello, è necessario aggiungere questa colonna. Selezionare **Aggiungi colonna condizionale** e assegnare un nome alla colonna, ad esempio ModelID. Immettere la condizione per la colonna dove se ID riga stima è diverso da null, allora < immettere l'ID modello previsionale >; altrimenti null.

### <a name="transform-the-billing-types"></a>Trasformare i tipi di fatturazione
Il modello delle stime di spesa di progetto (da PSA a Fin and Ops) include una colonna condizionale aggiunta per trasformare i tipi di fatturazione ricevuti da Project Service Automation durante l'integrazione.
- Se si crea un modello personale, è necessario aggiungere la colonna condizionale. Nel modulo di Query e filtro avanzati selezionare **Aggiungi colonna condizionale**. Assegnare alla colonna un nome, ad esempio "BillingType". La condizione da immettere è come segue:

    If **msdyn_billingtype** = 192350000, then **NonChargeable** else if **msdyn_billingtype** = 192350001, then **Chargeable** else if **msdyn_billingtype** = 192350002, then **Complimentary** else **NotAvailable**

### <a name="transform-the-transaction-types"></a>Trasformare i tipi di transazione
Il modello delle stime di spesa di progetto (da PSA a Fin and Ops) include una colonna condizionale aggiunta per trasformare i tipi di transazione ricevuti da Project Service Automation durante l'integrazione.
- Se si crea un modello personale, è necessario aggiungere la colonna condizionale. Nel modulo di Query e filtro avanzati selezionare **Aggiungi colonna condizionale**. Assegnare alla colonna un nome, ad esempio "TransactionType". La condizione da immettere è la seguente: If **msdyn_transactiontypecode** = 192350000, then **Cost** else if **msdyn_transactiontypecode** = 192350005, then **Sales** else **null**

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti vengono mostrati esempi dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mapping del modello](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)




