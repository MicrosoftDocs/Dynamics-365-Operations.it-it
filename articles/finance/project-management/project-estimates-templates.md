---
title: Sincronizzare le stime di progetto direttamente da Project Service Automation a Finance and Operations
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le stime orarie di progetto e le stime di spesa del progetto direttamente da Microsoft Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 3b885610ac9ca8645358ba8ab6d46ab82143a534
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250486"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizzare le stime di progetto direttamente da Project Service Automation a Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le stime orarie di progetto e le stime di spesa del progetto direttamente da Dynamics 365 Project Service Automation a Dynamics 365 Finance.

> [!NOTE]
> - L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili nella versione 8.0.
> - L'integrazione dei numeri effettivi è disponibile nella versione 8.0.1 o successive.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flusso di dati per Project Service Automation verso Finance

La soluzione di integrazione di Project Service Automation a Finance utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle stime orarie e di spesa del progetto da Project Service Automation a Finance.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)

## <a name="project-hour-estimates"></a>Stime orarie di progetto

### <a name="template-and-tasks"></a>Modello e attività

Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le stime orarie di progetto da Project Service Automation a Finance:

- **Nome del modello in Integrazione dati:** Stime orarie di progetto (da PSA a Fin and Ops)
- **Nome delle attività del progetto:**

    - Relazioni tra transazioni
    - Stime di spesa

### <a name="entity-set"></a>Insieme di entità

| Project Service Automation | Dati finanziari                                       |
|----------------------------|-----------------------------------------------|
| Attività di progetto              | Entità di integrazione per stime orarie del progetto |

### <a name="entity-flow"></a>Flusso di entità

Le stime orarie di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance come previsioni orarie di progetto.

### <a name="prerequisites"></a>Prerequisiti

Prima di eseguire la sincronizzazione delle stime delle ore di progetto, è necessario sincronizzare i progetti, le attività di progetto e le categorie di transazioni di spesa del progetto.

### <a name="power-query"></a>Power Query

Nel modello delle stime orarie di progetto, è necessario utilizzare Microsoft Power Query per Excel per completare queste attività:

- Impostare l'ID modello previsionale predefinito da utilizzare quando l'integrazione crea nuove previsioni orarie.
- Filtrare tutti i record specifici delle risorse nell'attività che impediranno l'integrazione nelle previsioni orarie.
- Filtrare tutte le righe vuote di categoria di transazione. In caso contrario, questa attività potrebbe generare previsioni errate.

#### <a name="set-the-default-forecast-model-id"></a>Impostare l'ID del modello previsionale predefinito.

Per aggiornare l'ID di modello previsionale predefinito nel modello, fare clic sulla freccia **Mappa** per aprire il mapping. Selezionare quindi il collegamento **Query avanzata e Filtro avanzato**.

- Se si utilizza il modello predefinito delle stime orarie di Project (da PSA a Fin and Ops), selezionare la **Condizione inserita** nell'elenco di **Passaggi applicati**. Nella voce **Funzione** sostituire **O\_forecast** con il nome dell'ID del modello previsionale che deve essere utilizzato con l'integrazione. Il modello predefinito include un ID modello previsionale proveniente dai dati dimostrativi.
- Se si crea un nuovo modello, è necessario aggiungere questa colonna. In Power Query selezionare **Aggiungi colonna condizionale** e assegnare un nome alla nuova colonna, ad esempio **ModelID**. Immettere la condizione per la colonna dove se l'attività progetto è diversa da null, allora \<immettere l'ID modello previsionale\>; altrimenti null.

#### <a name="filter-out-resource-specific-records"></a>Filtrare i record specifici delle risorse

Il modello delle stime orarie di progetto (da PSA a Fin and Ops) include un filtro predefinito che rimuove qualsiasi record specifico di risorsa. Se si crea un modello personale, è necessario aggiungere questo filtro. Selezionare il collegamento **Query avanzata e Filtro avanzato** per filtrare la colonna **msdyn\_islinetask** in modo che vengano inclusi solo i record impostati su **False**.

#### <a name="filter-out-empty-transaction-category-rows"></a>Filtrare le righe vuote di categoria di transazione

È necessario aggiungere un filtro per rimuovere tutte le righe che hanno categorie di transazione vuote. Questa attività è necessaria, indipendentemente che si utilizzi il modello predefinito o che se ne crei uno nuovo. Questo filtro rimuove tutte le righe di riepilogo provenienti da Project Service Automation che potrebbero generare errori nelle previsioni orarie di Finance. Selezionare il collegamento **Query avanzata e Filtro avanzato** per filtrare i record null nella colonna **msdyn\_transactioncategory\_value**.

### <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.

[![Mapping del modello](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

## <a name="project-expense-estimates"></a>Stime di spesa del progetto

### <a name="template-and-tasks"></a>Modello e attività

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le stime delle spese di progetto da Project Service Automation a Finance:

- **Nome del modello in Integrazione dati:** Stime di spesa di progetto (da PSA a Fin and Ops)
- **Nome delle attività del progetto:**

    - Relazioni tra transazioni 
    - Stime di spesa

### <a name="entity-set"></a>Insieme di entità

| Project Service Automation | Dati finanziari                                                  |
|----------------------------|----------------------------------------------------------|
| Connessioni delle transazioni    | Entità di integrazione per relazioni tra transazioni del progetto |
| Righe di stima             | Entità di integrazione per stime delle spese del progetto         |

### <a name="entity-flow"></a>Flusso di entità

Le stime di spesa di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance come previsioni di spesa di progetto.

### <a name="prerequisites"></a>Prerequisiti

Prima di eseguire la sincronizzazione delle stime di spesa di progetto, è necessario sincronizzare i progetti, le attività di progetto e le categorie di transazioni di spesa del progetto.

### <a name="power-query"></a>Power Query

Nel modello delle stime di spesa del progetto, è necessario utilizzare Power Query per completare queste attività:

- Filtrare per includere solo i record riga di stima delle spese.
- Impostare l'ID modello previsionale predefinito da utilizzare quando l'integrazione crea nuove previsioni orarie.
- Trasformare i tipi di fatturazione.
- Trasformare i tipi di transazione.

#### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrare per includere solo le righe di stima delle spese

Il modello di stima delle spese di progetto (da PSA a Fin and Ops) include un filtro predefinito che include solo righe di spesa nell'integrazione. Se si crea un modello personale, è necessario aggiungere questo filtro. Selezionare l'attività **Relazioni tra transazioni** e fare clic sulla freccia **Mappa** per aprire il mapping. Selezionare il collegamento **Query avanzata e Filtro avanzato**. Filtrare la colonna **msdyn\_transactiontype1** in modo che inclusa solo **msdyn\_estimateline**.

#### <a name="set-the-default-forecast-model-id"></a>Impostare l'ID del modello previsionale predefinito.

Per aggiornare l'ID modello previsionale predefinito nel modello, selezionare l'attività **Stime di spesa**, fare clic sulla freccia **Mappa** per aprire il mapping. Selezionare il collegamento **Query avanzata e Filtro avanzato**.

- Se si utilizza il modello predefinito delle stime di spesa del progetto (da PSA a Fin and Ops), in Power Query selezionare la prima **Condizione inserita** nella sezione **Passaggi applicati**. Nella voce **Funzione** sostituire **O\_forecast** con il nome dell'ID del modello previsionale che deve essere utilizzato con l'integrazione. Il modello predefinito include un ID modello previsionale proveniente dai dati dimostrativi.
- Se si crea un nuovo modello, è necessario aggiungere questa colonna. In Power Query selezionare **Aggiungi colonna condizionale** e assegnare un nome alla nuova colonna, ad esempio **ModelID**. Immettere la condizione per la colonna dove se ID riga stima è diverso da null, allora \<immettere l'ID modello previsionale\>; altrimenti null.

#### <a name="transform-the-billing-types"></a>Trasformare i tipi di fatturazione

Il modello delle stime di spesa di progetto (da PSA a Fin and Ops) include una colonna condizionale che viene utilizzata per trasformare i tipi di fatturazione ricevuti da Project Service Automation durante l'integrazione. Se si crea un modello personale, è necessario aggiungere la colonna condizionale. Selezionare il collegamento **Query avanzata e Filtro avanzato** e quindi selezionare **Aggiungi colonna condizionale**. Immettere un nome per la nuova colonna, ad esempio **BillingType**. Immettere la condizione seguente:

If **msdyn\_billingtype** = 192350000, then **Non addebitabile**  
else if **msdyn\_billingtype** = 192350001, then **Addebitabile**  
else if **msdyn\_billingtype** = 192350002, then **Gratuito**  
else **Non disponibile**

#### <a name="transform-the-transaction-types"></a>Trasformare i tipi di transazione

Il modello delle stime di spesa di progetto (da PSA a Fin and Ops) include una colonna condizionale che viene utilizzata per trasformare i tipi di transazione ricevuti da Project Service Automation durante l'integrazione. Se si crea un modello personale, è necessario aggiungere la colonna condizionale. Selezionare il collegamento **Query avanzata e Filtro avanzato** e quindi selezionare **Aggiungi colonna condizionale**. Immettere un nome per la nuova colonna, ad esempio **TransactionType**. Immettere la condizione seguente:

If **msdyn\_transactiontypecode** = 192350000, then **Costo**  
else if **msdyn\_transactiontypecode** = 192350005, then **Vendita**  
else **null**

### <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti vengono mostrati esempi dei mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.

[![Mapping del modello](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mapping del modello](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)
