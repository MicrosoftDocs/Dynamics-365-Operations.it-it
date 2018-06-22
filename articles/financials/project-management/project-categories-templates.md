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

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="7c39a-103">Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7c39a-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

<span data-ttu-id="7c39a-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Microsoft Dynamics 365 for Finance and Operations e Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="7c39a-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> <span data-ttu-id="7c39a-105">L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Dynamics 365 for Finance and Operations versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="7c39a-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="7c39a-106">Flusso di dati per Project Service Automation e Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7c39a-106">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="7c39a-107">La soluzione di integrazione di Project Service Automation e Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-107">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="7c39a-108">I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consente il flusso di dati relativi alle categorie di transazioni di spesa di progetto tra Finance and Operations e Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="7c39a-108">The integration templates that are available with the Data integration feature enables the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="7c39a-109">Se le categorie di spesa di progetto vengono gestite in Finance and Operations, il flusso di integrazione avviene prima di tutto da Finance and Operations a Project Service Automation e successivamente aggiornando gli ID di integrazione delle categorie di spesa di progetto tramite sincronizzazione da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-109">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation, and then updating the project expense categories integration IDs by synchronizing from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="7c39a-110">Se le categorie di spesa di progetto vengono gestite in Project Service Automation, il flusso di integrazione avviene prima di tutto da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-110">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="7c39a-111">Le categorie di progetto devono essere già configurate in Finance and Operations prima della sincronizzazione da Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="7c39a-111">The project categories must already be configured in Finance and Operations prior to the synchronization from Project Service Automation.</span></span> <span data-ttu-id="7c39a-112">Occorre quindi sincronizzare da Finance and Operations a Project Service Automation e poi da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-112">Then synchronize from Finance and Operations back to Project Service Automation and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="7c39a-113">Questa procedura assicura che le categorie vengano associate e non vengano creati duplicati.</span><span class="sxs-lookup"><span data-stu-id="7c39a-113">This ensures the categories are linked and duplicates are not created.</span></span>

> [!NOTE]
> <span data-ttu-id="7c39a-114">In genere, le categorie di spesa di progetto verranno gestite in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-114">Typically, the project expense categories will be mastered in Finance and Operations.</span></span> <span data-ttu-id="7c39a-115">Se non è questo il caso o si dispone già di categorie di spese create in Project Service Automation, è necessario prima sincronizzare utilizzando le categorie di transazioni di spesa di progetto (da PSA a Fin and Ops) e successivamente sincronizzare utilizzando le categorie di transazioni di spesa di progetto (da Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="7c39a-115">If that is not your situation, or you already have expense categories created in Project Service Automation, you must first sync using the Project expense transaction categories (PSA to Fin and Ops) and then sync using Project expense transaction categories (Fin and Ops to PSA).</span></span> <span data-ttu-id="7c39a-116">È quindi consigliabile eseguire la sincronizzazione da PSA a Fin and Ops un'altra volta.</span><span class="sxs-lookup"><span data-stu-id="7c39a-116">You should then run the sync from PSA to Fin and Ops one more time.</span></span>

> <span data-ttu-id="7c39a-117">Se si sincronizza prima da Project Service Automation, è necessario che le categorie di progetto siano già impostate in Finance and Operations e che tutte le categorie di progetto che devono essere sincronizzate con le categorie di progetto di Project Service Automation siano impostate su **Attivo nei giornali di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="7c39a-117">If synchronizing first from Project Service Automation, the project categories must already be set up in Finance and Operations and any project categories that need to be synched with the Project Service Automation transaction categories must be set up to be **Active in journals**.</span></span>

<span data-ttu-id="7c39a-118">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-118">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="7c39a-119">[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="7c39a-119">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="7c39a-120">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="7c39a-120">Templates and tasks</span></span>

<span data-ttu-id="7c39a-121">Per accedere ai modelli disponibili, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="7c39a-121">To access available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="7c39a-122">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie di spesa di progetto da Finance and Operations a Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="7c39a-122">The following template and underlying task is used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="7c39a-123">**Nome del modello in Integrazione dati:** Categorie di transazione di spesa di progetto (da Fin and Ops a PSA)</span><span class="sxs-lookup"><span data-stu-id="7c39a-123">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
-  <span data-ttu-id="7c39a-124">**Nome dell'attività del progetto:** Sincronizzare le categorie a PSA</span><span class="sxs-lookup"><span data-stu-id="7c39a-124">**Name of the task in the project:** Sync categories to PSA</span></span>

## <a name="entity-set"></a><span data-ttu-id="7c39a-125">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="7c39a-125">Entity set</span></span>

| <span data-ttu-id="7c39a-126">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7c39a-126">Finance and Operations</span></span>               | <span data-ttu-id="7c39a-127">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7c39a-127">Project Service Automation</span></span>    |
|--------------------------------------|-------------------------------|
| <span data-ttu-id="7c39a-128">Entità di integrazione per categorie</span><span class="sxs-lookup"><span data-stu-id="7c39a-128">Integration entity for categories</span></span>    | <span data-ttu-id="7c39a-129">Categorie di transazioni</span><span class="sxs-lookup"><span data-stu-id="7c39a-129">Transaction categories</span></span>        |

## <a name="entity-flow"></a><span data-ttu-id="7c39a-130">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="7c39a-130">Entity flow</span></span>

<span data-ttu-id="7c39a-131">Le categorie di spesa di progetto vengono gestite in Finance and Operations e vengono sincronizzate con Project Service Automation come categorie di transazioni.</span><span class="sxs-lookup"><span data-stu-id="7c39a-131">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="7c39a-132">Power Query</span><span class="sxs-lookup"><span data-stu-id="7c39a-132">Power Query</span></span>

<span data-ttu-id="7c39a-133">Quando si sincronizza a Project Service Automation, è necessario impostare il tipo di fatturazione sulla categoria di transazione.</span><span class="sxs-lookup"><span data-stu-id="7c39a-133">You must use Microsoft Power Query to set the billing type on the transaction category when synchronizing to Project Service Automation.</span></span> <span data-ttu-id="7c39a-134">Il modello delle categorie di transazioni di spesa di progetto (Fin and Ops to PSA) include una colonna predefinita e un mapping già fornito.</span><span class="sxs-lookup"><span data-stu-id="7c39a-134">The Project expense transaction categories (Fin and Ops to PSA) template has a default column and mapping already provided.</span></span> <span data-ttu-id="7c39a-135">Se si crea un modello personale, è necessario aggiungere una colonna condizionale in Power Query.</span><span class="sxs-lookup"><span data-stu-id="7c39a-135">If you create your own template, you must add a conditional column in Power Query.</span></span>
- <span data-ttu-id="7c39a-136">Aprire il modulo di Query e filtro avanzato dall'interno dell'attività di mapping delle categorie di spesa di progetto.</span><span class="sxs-lookup"><span data-stu-id="7c39a-136">Open the Advance Query and Filtering form from within the mapping of project expense categories task.</span></span>
- <span data-ttu-id="7c39a-137">Selezionare **Aggiungi colonna condizionale**.</span><span class="sxs-lookup"><span data-stu-id="7c39a-137">Select **Add Conditional Column**.</span></span>
- <span data-ttu-id="7c39a-138">Assegnare alla nuova colonna un nome, ad esempio "BillingType".</span><span class="sxs-lookup"><span data-stu-id="7c39a-138">Give the new column a name, such as BillingType.</span></span>
- <span data-ttu-id="7c39a-139">Immettere la seguente condizione: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="7c39a-139">Enter the following condition: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
- <span data-ttu-id="7c39a-140">Fare clic su **OK** sulla colonna.</span><span class="sxs-lookup"><span data-stu-id="7c39a-140">Click **OK** on the column.</span></span>
- <span data-ttu-id="7c39a-141">Assicurarsi di mappare la nuova colonna nella pagina di mapping.</span><span class="sxs-lookup"><span data-stu-id="7c39a-141">Be sure to map this new column in the mapping page.</span></span>

<span data-ttu-id="7c39a-142">Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7c39a-142">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="7c39a-143">Il mapping mostra le informazioni di campo che verranno sincronizzate da Finance and Operations a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="7c39a-143">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="7c39a-144">[![Mapping del modello](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7c39a-144">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

<span data-ttu-id="7c39a-145">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie di spesa di progetto da Project Service Automation a Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="7c39a-145">The following template and underlying task is used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="7c39a-146">-**Nome del modello in Integrazione dati:** Categorie di transazione di spesa di progetto (da PSA a Fin and Ops) -**Nome dell'attività del progetto:** Sincronizzare le categorie a Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="7c39a-146">-**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops) -**Name of the task in the project:** Sync categories to Fin Ops</span></span>

## <a name="entity-set"></a><span data-ttu-id="7c39a-147">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="7c39a-147">Entity set</span></span>

| <span data-ttu-id="7c39a-148">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7c39a-148">Project Service Automation</span></span>      | <span data-ttu-id="7c39a-149">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7c39a-149">Finance and Operations</span></span>             |
|---------------------------------|------------------------------------|
| <span data-ttu-id="7c39a-150">Categorie di transazioni</span><span class="sxs-lookup"><span data-stu-id="7c39a-150">Transaction categories</span></span>          | <span data-ttu-id="7c39a-151">Entità di integrazione per categorie</span><span class="sxs-lookup"><span data-stu-id="7c39a-151">Integration entity for categories</span></span>  | 

## <a name="entity-flow"></a><span data-ttu-id="7c39a-152">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="7c39a-152">Entity flow</span></span>

<span data-ttu-id="7c39a-153">Le categorie di spesa di progetto vengono gestite in Finance and Operations e vengono sincronizzate con Project Service Automation come categorie di transazioni.</span><span class="sxs-lookup"><span data-stu-id="7c39a-153">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="7c39a-154">La risincronizzazione a Finance and Operations aggiorna l'ID integrazione da Project Service Automation nella categoria di progetto di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-154">The synchronization back to Finance and Operations updates the integration ID from Project Service Automation on the Finance and Operations project category.</span></span>

<span data-ttu-id="7c39a-155">Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="7c39a-155">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="7c39a-156">Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c39a-156">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="7c39a-157">[![Mapping del modello](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7c39a-157">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

