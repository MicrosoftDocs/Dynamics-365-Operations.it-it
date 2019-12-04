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
ms.openlocfilehash: ebf0fce60ad006e798aa4f404fbffcf10a0b31f9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770291"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="7128a-103">Sincronizzare le stime di progetto direttamente da Project Service Automation a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7128a-103">Synchronize project estimates directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7128a-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le stime orarie di progetto e le stime di spesa del progetto direttamente da Dynamics 365 Project Service Automation a Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="7128a-104">This topic describes the templates and underlying tasks that are used to synchronize project hour estimates and project expense estimates directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="7128a-105">L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili nella versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="7128a-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in version 8.0.</span></span>
> - <span data-ttu-id="7128a-106">L'integrazione dei numeri effettivi è disponibile nella versione 8.0.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="7128a-106">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="7128a-107">Flusso di dati per Project Service Automation verso Finance</span><span class="sxs-lookup"><span data-stu-id="7128a-107">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="7128a-108">La soluzione di integrazione di Project Service Automation a Finance utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7128a-108">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="7128a-109">I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle stime orarie e di spesa del progetto da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="7128a-109">The integration templates that are available with the Data integration feature enable the flow of data about project hour estimates and project expense estimates from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7128a-110">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance.</span><span class="sxs-lookup"><span data-stu-id="7128a-110">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="7128a-111">[![Flusso di dati per l'integrazione di Project Service Automation con Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="7128a-111">[![Data flow for Project Service Automation integration with Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span></span>

## <a name="project-hour-estimates"></a><span data-ttu-id="7128a-112">Stime orarie di progetto</span><span class="sxs-lookup"><span data-stu-id="7128a-112">Project hour estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="7128a-113">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="7128a-113">Template and tasks</span></span>

<span data-ttu-id="7128a-114">Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft Power Apps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="7128a-114">To access the available templates, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="7128a-115">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le stime orarie di progetto da Project Service Automation a Finance:</span><span class="sxs-lookup"><span data-stu-id="7128a-115">The following template and underlying tasks are used to synchronize project hour estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="7128a-116">**Nome del modello in Integrazione dati:** Stime orarie di progetto (da PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7128a-116">**Name of the template in Data integration:** Project hour estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="7128a-117">**Nome delle attività del progetto:**</span><span class="sxs-lookup"><span data-stu-id="7128a-117">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="7128a-118">Relazioni tra transazioni</span><span class="sxs-lookup"><span data-stu-id="7128a-118">Transaction relationships</span></span>
    - <span data-ttu-id="7128a-119">Stime di spesa</span><span class="sxs-lookup"><span data-stu-id="7128a-119">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="7128a-120">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="7128a-120">Entity set</span></span>

| <span data-ttu-id="7128a-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7128a-121">Project Service Automation</span></span> | <span data-ttu-id="7128a-122">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="7128a-122">Finance</span></span>                                       |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="7128a-123">Attività di progetto</span><span class="sxs-lookup"><span data-stu-id="7128a-123">Project tasks</span></span>              | <span data-ttu-id="7128a-124">Entità di integrazione per stime orarie del progetto</span><span class="sxs-lookup"><span data-stu-id="7128a-124">Integration entity for project hour estimates</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="7128a-125">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="7128a-125">Entity flow</span></span>

<span data-ttu-id="7128a-126">Le stime orarie di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance come previsioni orarie di progetto.</span><span class="sxs-lookup"><span data-stu-id="7128a-126">Project hour estimates are managed in Project Service Automation, and they are synchronized to Finance as project hour forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7128a-127">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7128a-127">Prerequisites</span></span>

<span data-ttu-id="7128a-128">Prima di eseguire la sincronizzazione delle stime delle ore di progetto, è necessario sincronizzare i progetti, le attività di progetto e le categorie di transazioni di spesa del progetto.</span><span class="sxs-lookup"><span data-stu-id="7128a-128">Before synchronization of project hour estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="7128a-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="7128a-129">Power Query</span></span>

<span data-ttu-id="7128a-130">Nel modello delle stime orarie di progetto, è necessario utilizzare Microsoft Power Query per Excel per completare queste attività:</span><span class="sxs-lookup"><span data-stu-id="7128a-130">In the project hour estimates template, you must use Microsoft Power Query for Excel to complete these tasks:</span></span>

- <span data-ttu-id="7128a-131">Impostare l'ID modello previsionale predefinito da utilizzare quando l'integrazione crea nuove previsioni orarie.</span><span class="sxs-lookup"><span data-stu-id="7128a-131">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="7128a-132">Filtrare tutti i record specifici delle risorse nell'attività che impediranno l'integrazione nelle previsioni orarie.</span><span class="sxs-lookup"><span data-stu-id="7128a-132">Filter out any resource-specific records in the task that will fail the integration into hour forecasts.</span></span>
- <span data-ttu-id="7128a-133">Filtrare tutte le righe vuote di categoria di transazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-133">Filter out any empty transaction category rows.</span></span> <span data-ttu-id="7128a-134">In caso contrario, questa attività potrebbe generare previsioni errate.</span><span class="sxs-lookup"><span data-stu-id="7128a-134">Failure to complete this task might result in incorrect hour forecasts.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="7128a-135">Impostare l'ID del modello previsionale predefinito.</span><span class="sxs-lookup"><span data-stu-id="7128a-135">Set the default forecast model ID</span></span>

<span data-ttu-id="7128a-136">Per aggiornare l'ID di modello previsionale predefinito nel modello, fare clic sulla freccia **Mappa** per aprire il mapping.</span><span class="sxs-lookup"><span data-stu-id="7128a-136">To update the default forecast model ID in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="7128a-137">Selezionare quindi il collegamento **Query avanzata e Filtro avanzato**.</span><span class="sxs-lookup"><span data-stu-id="7128a-137">Then select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="7128a-138">Se si utilizza il modello predefinito delle stime orarie di Project (da PSA a Fin and Ops), selezionare la **Condizione inserita** nell'elenco di **Passaggi applicati**.</span><span class="sxs-lookup"><span data-stu-id="7128a-138">If you're using the default Project hour estimates (PSA to Fin and Ops) template, select the **Inserted Condition** in the list of **Applied Steps**.</span></span> <span data-ttu-id="7128a-139">Nella voce **Funzione** sostituire **O\_forecast** con il nome dell'ID del modello previsionale che deve essere utilizzato con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-139">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="7128a-140">Il modello predefinito include un ID modello previsionale proveniente dai dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="7128a-140">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="7128a-141">Se si crea un nuovo modello, è necessario aggiungere questa colonna.</span><span class="sxs-lookup"><span data-stu-id="7128a-141">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="7128a-142">In Power Query selezionare **Aggiungi colonna condizionale** e assegnare un nome alla nuova colonna, ad esempio **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="7128a-142">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="7128a-143">Immettere la condizione per la colonna dove se l'attività progetto è diversa da null, allora \<immettere l'ID modello previsionale\>; altrimenti null.</span><span class="sxs-lookup"><span data-stu-id="7128a-143">Enter the condition for the column, where, if Project task is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="filter-out-resource-specific-records"></a><span data-ttu-id="7128a-144">Filtrare i record specifici delle risorse</span><span class="sxs-lookup"><span data-stu-id="7128a-144">Filter out resource-specific records</span></span>

<span data-ttu-id="7128a-145">Il modello delle stime orarie di progetto (da PSA a Fin and Ops) include un filtro predefinito che rimuove qualsiasi record specifico di risorsa.</span><span class="sxs-lookup"><span data-stu-id="7128a-145">The Project hour estimates (PSA to Fin and Ops) template has a default filter that removes any resource-specific records.</span></span> <span data-ttu-id="7128a-146">Se si crea un modello personale, è necessario aggiungere questo filtro.</span><span class="sxs-lookup"><span data-stu-id="7128a-146">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="7128a-147">Selezionare il collegamento **Query avanzata e Filtro avanzato** per filtrare la colonna **msdyn\_islinetask** in modo che vengano inclusi solo i record impostati su **False**.</span><span class="sxs-lookup"><span data-stu-id="7128a-147">Select the **Advanced Query and Filtering** link to filter on the **msdyn\_islinetask** column so that only **False** records are included.</span></span>

#### <a name="filter-out-empty-transaction-category-rows"></a><span data-ttu-id="7128a-148">Filtrare le righe vuote di categoria di transazione</span><span class="sxs-lookup"><span data-stu-id="7128a-148">Filter out empty transaction category rows</span></span>

<span data-ttu-id="7128a-149">È necessario aggiungere un filtro per rimuovere tutte le righe che hanno categorie di transazione vuote.</span><span class="sxs-lookup"><span data-stu-id="7128a-149">You must add a filter to remove any rows that have empty transaction categories.</span></span> <span data-ttu-id="7128a-150">Questa attività è necessaria, indipendentemente che si utilizzi il modello predefinito o che se ne crei uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="7128a-150">This task is required, regardless of whether you're using the default template or creating your own template.</span></span> <span data-ttu-id="7128a-151">Questo filtro rimuove tutte le righe di riepilogo provenienti da Project Service Automation che potrebbero generare errori nelle previsioni orarie di Finance.</span><span class="sxs-lookup"><span data-stu-id="7128a-151">This filter removes any summary rows from Project Service Automation that might cause the hour forecasts in Finance to be incorrect.</span></span> <span data-ttu-id="7128a-152">Selezionare il collegamento **Query avanzata e Filtro avanzato** per filtrare i record null nella colonna **msdyn\_transactioncategory\_value**.</span><span class="sxs-lookup"><span data-stu-id="7128a-152">Select **Advanced Query and Filtering** link to filter out null records in the **msdyn\_transactioncategory\_value** column.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7128a-153">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="7128a-153">Template mapping in Data integration</span></span>

<span data-ttu-id="7128a-154">Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7128a-154">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="7128a-155">Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="7128a-155">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7128a-156">[![Mapping del modello](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7128a-156">[![Template mapping](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span></span>

## <a name="project-expense-estimates"></a><span data-ttu-id="7128a-157">Stime di spesa del progetto</span><span class="sxs-lookup"><span data-stu-id="7128a-157">Project expense estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="7128a-158">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="7128a-158">Template and tasks</span></span>

<span data-ttu-id="7128a-159">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le stime delle spese di progetto da Project Service Automation a Finance:</span><span class="sxs-lookup"><span data-stu-id="7128a-159">The following template and underlying tasks are used to synchronize project expense estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="7128a-160">**Nome del modello in Integrazione dati:** Stime di spesa di progetto (da PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7128a-160">**Name of the template in Data integration:** Project expense estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="7128a-161">**Nome delle attività del progetto:**</span><span class="sxs-lookup"><span data-stu-id="7128a-161">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="7128a-162">Relazioni tra transazioni</span><span class="sxs-lookup"><span data-stu-id="7128a-162">Transaction relationships</span></span> 
    - <span data-ttu-id="7128a-163">Stime di spesa</span><span class="sxs-lookup"><span data-stu-id="7128a-163">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="7128a-164">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="7128a-164">Entity set</span></span>

| <span data-ttu-id="7128a-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7128a-165">Project Service Automation</span></span> | <span data-ttu-id="7128a-166">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="7128a-166">Finance</span></span>                                                  |
|----------------------------|----------------------------------------------------------|
| <span data-ttu-id="7128a-167">Connessioni delle transazioni</span><span class="sxs-lookup"><span data-stu-id="7128a-167">Transaction Connections</span></span>    | <span data-ttu-id="7128a-168">Entità di integrazione per relazioni tra transazioni del progetto</span><span class="sxs-lookup"><span data-stu-id="7128a-168">Integration entity for project transaction relationships</span></span> |
| <span data-ttu-id="7128a-169">Righe di stima</span><span class="sxs-lookup"><span data-stu-id="7128a-169">Estimate Lines</span></span>             | <span data-ttu-id="7128a-170">Entità di integrazione per stime delle spese del progetto</span><span class="sxs-lookup"><span data-stu-id="7128a-170">Integration entity for project expense estimates</span></span>         |

### <a name="entity-flow"></a><span data-ttu-id="7128a-171">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="7128a-171">Entity flow</span></span>

<span data-ttu-id="7128a-172">Le stime di spesa di progetto vengono gestite in Project Service Automation e vengono sincronizzate con Finance come previsioni di spesa di progetto.</span><span class="sxs-lookup"><span data-stu-id="7128a-172">Project expense estimates are managed in Project Service Automation, and they are synchronized to Finance as project expense forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7128a-173">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7128a-173">Prerequisites</span></span>

<span data-ttu-id="7128a-174">Prima di eseguire la sincronizzazione delle stime di spesa di progetto, è necessario sincronizzare i progetti, le attività di progetto e le categorie di transazioni di spesa del progetto.</span><span class="sxs-lookup"><span data-stu-id="7128a-174">Before synchronization of project expense estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="7128a-175">Power Query</span><span class="sxs-lookup"><span data-stu-id="7128a-175">Power Query</span></span>

<span data-ttu-id="7128a-176">Nel modello delle stime di spesa del progetto, è necessario utilizzare Power Query per completare queste attività:</span><span class="sxs-lookup"><span data-stu-id="7128a-176">In the project expense estimates template, you must use Power Query to complete the following tasks:</span></span>

- <span data-ttu-id="7128a-177">Filtrare per includere solo i record riga di stima delle spese.</span><span class="sxs-lookup"><span data-stu-id="7128a-177">Filter to include only expense estimate line records.</span></span>
- <span data-ttu-id="7128a-178">Impostare l'ID modello previsionale predefinito da utilizzare quando l'integrazione crea nuove previsioni orarie.</span><span class="sxs-lookup"><span data-stu-id="7128a-178">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="7128a-179">Trasformare i tipi di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-179">Transform the billing types.</span></span>
- <span data-ttu-id="7128a-180">Trasformare i tipi di transazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-180">Transform the transaction types.</span></span>

#### <a name="filter-to-include-only-expense-estimate-lines"></a><span data-ttu-id="7128a-181">Filtrare per includere solo le righe di stima delle spese</span><span class="sxs-lookup"><span data-stu-id="7128a-181">Filter to include only expense estimate lines</span></span>

<span data-ttu-id="7128a-182">Il modello di stima delle spese di progetto (da PSA a Fin and Ops) include un filtro predefinito che include solo righe di spesa nell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-182">The Project expense estimates (PSA to Fin and Ops) template has a default filter that includes only expense lines in the integration.</span></span> <span data-ttu-id="7128a-183">Se si crea un modello personale, è necessario aggiungere questo filtro.</span><span class="sxs-lookup"><span data-stu-id="7128a-183">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="7128a-184">Selezionare l'attività **Relazioni tra transazioni** e fare clic sulla freccia **Mappa** per aprire il mapping.</span><span class="sxs-lookup"><span data-stu-id="7128a-184">Select the **Transaction relationships** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="7128a-185">Selezionare il collegamento **Query avanzata e Filtro avanzato**.</span><span class="sxs-lookup"><span data-stu-id="7128a-185">Select the **Advanced Query and Filtering** link.</span></span> <span data-ttu-id="7128a-186">Filtrare la colonna **msdyn\_transactiontype1** in modo che inclusa solo **msdyn\_estimateline**.</span><span class="sxs-lookup"><span data-stu-id="7128a-186">Filter the **msdyn\_transactiontype1** column so that it includes only **msdyn\_estimateline**.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="7128a-187">Impostare l'ID del modello previsionale predefinito.</span><span class="sxs-lookup"><span data-stu-id="7128a-187">Set the default forecast model ID</span></span>

<span data-ttu-id="7128a-188">Per aggiornare l'ID modello previsionale predefinito nel modello, selezionare l'attività **Stime di spesa**, fare clic sulla freccia **Mappa** per aprire il mapping.</span><span class="sxs-lookup"><span data-stu-id="7128a-188">To update the default forecast model ID in the template, select the **Expense estimates** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="7128a-189">Selezionare il collegamento **Query avanzata e Filtro avanzato**.</span><span class="sxs-lookup"><span data-stu-id="7128a-189">Select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="7128a-190">Se si utilizza il modello predefinito delle stime di spesa del progetto (da PSA a Fin and Ops), in Power Query selezionare la prima **Condizione inserita** nella sezione **Passaggi applicati**.</span><span class="sxs-lookup"><span data-stu-id="7128a-190">If you're using the default Project expense estimates (PSA to Fin and Ops) template, in Power Query, select the first **Inserted Condition** from the **Applied Steps** section.</span></span> <span data-ttu-id="7128a-191">Nella voce **Funzione** sostituire **O\_forecast** con il nome dell'ID del modello previsionale che deve essere utilizzato con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-191">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="7128a-192">Il modello predefinito include un ID modello previsionale proveniente dai dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="7128a-192">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="7128a-193">Se si crea un nuovo modello, è necessario aggiungere questa colonna.</span><span class="sxs-lookup"><span data-stu-id="7128a-193">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="7128a-194">In Power Query selezionare **Aggiungi colonna condizionale** e assegnare un nome alla nuova colonna, ad esempio **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="7128a-194">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="7128a-195">Immettere la condizione per la colonna dove se ID riga stima è diverso da null, allora \<immettere l'ID modello previsionale\>; altrimenti null.</span><span class="sxs-lookup"><span data-stu-id="7128a-195">Enter the condition for the column, where, if Estimate line ID is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="transform-the-billing-types"></a><span data-ttu-id="7128a-196">Trasformare i tipi di fatturazione</span><span class="sxs-lookup"><span data-stu-id="7128a-196">Transform the billing types</span></span>

<span data-ttu-id="7128a-197">Il modello delle stime di spesa di progetto (da PSA a Fin and Ops) include una colonna condizionale che viene utilizzata per trasformare i tipi di fatturazione ricevuti da Project Service Automation durante l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-197">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the billing types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="7128a-198">Se si crea un modello personale, è necessario aggiungere la colonna condizionale.</span><span class="sxs-lookup"><span data-stu-id="7128a-198">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="7128a-199">Selezionare il collegamento **Query avanzata e Filtro avanzato** e quindi selezionare **Aggiungi colonna condizionale**.</span><span class="sxs-lookup"><span data-stu-id="7128a-199">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="7128a-200">Immettere un nome per la nuova colonna, ad esempio **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="7128a-200">Enter a name for the new column, such as **BillingType**.</span></span> <span data-ttu-id="7128a-201">Immettere la condizione seguente:</span><span class="sxs-lookup"><span data-stu-id="7128a-201">Then enter the following condition:</span></span>

<span data-ttu-id="7128a-202">If **msdyn\_billingtype** = 192350000, then **Non addebitabile**</span><span class="sxs-lookup"><span data-stu-id="7128a-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span></span>  
<span data-ttu-id="7128a-203">else if **msdyn\_billingtype** = 192350001, then **Addebitabile**</span><span class="sxs-lookup"><span data-stu-id="7128a-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span></span>  
<span data-ttu-id="7128a-204">else if **msdyn\_billingtype** = 192350002, then **Gratuito**</span><span class="sxs-lookup"><span data-stu-id="7128a-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span></span>  
<span data-ttu-id="7128a-205">else **Non disponibile**</span><span class="sxs-lookup"><span data-stu-id="7128a-205">else **NotAvailable**</span></span>

#### <a name="transform-the-transaction-types"></a><span data-ttu-id="7128a-206">Trasformare i tipi di transazione</span><span class="sxs-lookup"><span data-stu-id="7128a-206">Transform the transaction types</span></span>

<span data-ttu-id="7128a-207">Il modello delle stime di spesa di progetto (da PSA a Fin and Ops) include una colonna condizionale che viene utilizzata per trasformare i tipi di transazione ricevuti da Project Service Automation durante l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7128a-207">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the transaction types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="7128a-208">Se si crea un modello personale, è necessario aggiungere la colonna condizionale.</span><span class="sxs-lookup"><span data-stu-id="7128a-208">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="7128a-209">Selezionare il collegamento **Query avanzata e Filtro avanzato** e quindi selezionare **Aggiungi colonna condizionale**.</span><span class="sxs-lookup"><span data-stu-id="7128a-209">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="7128a-210">Immettere un nome per la nuova colonna, ad esempio **TransactionType**.</span><span class="sxs-lookup"><span data-stu-id="7128a-210">Enter a name for the new column, such as **TransactionType**.</span></span> <span data-ttu-id="7128a-211">Immettere la condizione seguente:</span><span class="sxs-lookup"><span data-stu-id="7128a-211">Then enter the following condition:</span></span>

<span data-ttu-id="7128a-212">If **msdyn\_transactiontypecode** = 192350000, then **Costo**</span><span class="sxs-lookup"><span data-stu-id="7128a-212">If **msdyn\_transactiontypecode** = 192350000, then **Cost**</span></span>  
<span data-ttu-id="7128a-213">else if **msdyn\_transactiontypecode** = 192350005, then **Vendita**</span><span class="sxs-lookup"><span data-stu-id="7128a-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sales**</span></span>  
<span data-ttu-id="7128a-214">else **null**</span><span class="sxs-lookup"><span data-stu-id="7128a-214">else **null**</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7128a-215">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="7128a-215">Template mapping in Data integration</span></span>

<span data-ttu-id="7128a-216">Nelle figure seguenti vengono mostrati esempi dei mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7128a-216">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="7128a-217">Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="7128a-217">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7128a-218">[![Mapping del modello](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7128a-218">[![Template mapping](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span></span>

<span data-ttu-id="7128a-219">[![Mapping del modello](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7128a-219">[![Template mapping](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span></span>
