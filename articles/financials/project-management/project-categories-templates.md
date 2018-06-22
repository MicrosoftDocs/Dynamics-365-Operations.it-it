---
title: Sincronizzare le categorie di spesa di progetto da Project Service Automation
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Microsoft Dynamics 365 for Finance and Operations e Dynamics 365 for Project Service Automation."
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
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: it-it
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Microsoft Dynamics 365 for Finance and Operations e Dynamics 365 for Project Service Automation.

> [!NOTE]
> L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Dynamics 365 for Finance and Operations versione 8.0.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Flusso di dati per Project Service Automation e Finance and Operations

La soluzione di integrazione di Project Service Automation e Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations. I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle categorie di transazioni di spesa di progetto tra Finance and Operations e Project Service Automation.

Se le categorie di spesa di progetto vengono gestite in Finance and Operations, il flusso di integrazione avviene prima di tutto da Finance and Operations a Project Service Automation e successivamente aggiornando gli ID di integrazione delle categorie di spesa di progetto tramite sincronizzazione da Project Service Automation a Finance and Operations.

Se le categorie di spesa di progetto vengono gestite in Project Service Automation, il flusso di integrazione avviene prima di tutto da Project Service Automation a Finance and Operations. Le categorie di progetto devono essere già configurate in Finance and Operations prima della sincronizzazione da Project Service Automation. Occorre quindi sincronizzare da Finance and Operations a Project Service Automation e poi da Project Service Automation a Finance and Operations. Questa procedura assicura che le categorie vengano associate e non vengano creati duplicati.

> [!NOTE]
> In genere, le categorie di spesa di progetto verranno gestite in Finance and Operations. Se non è questo il caso o si dispone già di categorie di spese create in Project Service Automation, è necessario prima sincronizzare utilizzando le categorie di transazioni di spesa di progetto (da PSA a Fin and Ops) e successivamente sincronizzare utilizzando le categorie di transazioni di spesa di progetto (da Fin and Ops a PSA). È quindi consigliabile eseguire la sincronizzazione da PSA a Fin and Ops un'altra volta.

> Se si sincronizza prima da Project Service Automation, è necessario che le categorie di progetto siano già impostate in Finance and Operations e che tutte le categorie di progetto che devono essere sincronizzate con le categorie di progetto di Project Service Automation siano impostate su **Attivo nei giornali di registrazione**.

La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.

[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)


## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie di spesa di progetto da Finance and Operations a Project Service Automation:

-  **Nome del modello in Integrazione dati:** Categorie di transazione di spesa di progetto (da Fin and Ops a PSA)
-  **Nome dell'attività del progetto:** Sincronizzare le categorie a PSA

## <a name="entity-set"></a>Insieme di entità

| Finance and Operations               | Project Service Automation    |
|--------------------------------------|-------------------------------|
| Entità di integrazione per categorie    | Categorie di transazioni        |

## <a name="entity-flow"></a>Flusso di entità

Le categorie di spesa di progetto vengono gestite in Finance and Operations e vengono sincronizzate con Project Service Automation come categorie di transazioni.

## <a name="power-query"></a>Power Query

Quando si sincronizza a Project Service Automation, è necessario impostare il tipo di fatturazione sulla categoria di transazione. Il modello delle categorie di transazioni di spesa di progetto (Fin and Ops to PSA) include una colonna predefinita e un mapping già fornito. Se si crea un modello personale, è necessario aggiungere una colonna condizionale in Power Query.
- Aprire il modulo di Query e filtro avanzato dall'interno dell'attività di mapping delle categorie di spesa di progetto.
- Selezionare **Aggiungi colonna condizionale**.
- Assegnare alla nuova colonna un nome, ad esempio "BillingType".
- Immettere la seguente condizione: if **CATEGORYID not equal to null then 19235001, Otherwise null**.
- Fare clic su **OK** sulla colonna.
- Assicurarsi di mappare la nuova colonna nella pagina di mapping.

Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati. Il mapping mostra le informazioni di campo che verranno sincronizzate da Finance and Operations a Project Service Automation.

[![Mapping del modello](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie di spesa di progetto da Project Service Automation a Finance and Operations:

-**Nome del modello in Integrazione dati:** Categorie di transazione di spesa di progetto (da PSA a Fin and Ops) -**Nome dell'attività del progetto:** Sincronizzare le categorie a Fin and Ops

## <a name="entity-set"></a>Insieme di entità

| Project Service Automation      | Finance and Operations             |
|---------------------------------|------------------------------------|
| Categorie di transazioni          | Entità di integrazione per categorie  | 

## <a name="entity-flow"></a>Flusso di entità

Le categorie di spesa di progetto vengono gestite in Finance and Operations e vengono sincronizzate con Project Service Automation come categorie di transazioni. La risincronizzazione a Finance and Operations aggiorna l'ID integrazione da Project Service Automation nella categoria di progetto di Finance and Operations.

Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.

> [!NOTE]
> Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.

[![Mapping del modello](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

