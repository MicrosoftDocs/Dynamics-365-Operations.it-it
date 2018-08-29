---
title: Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Microsoft Dynamics 365 for Finance and Operations e Microsoft Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="87524-103">Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="87524-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="87524-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Microsoft Dynamics 365 for Finance and Operations e Microsoft Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="87524-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="87524-105">L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Microsoft Dynamics 365 for Finance and Operations versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="87524-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in Microsoft Dynamics 365 for Finance and Operations version 8.0.</span></span>
> - <span data-ttu-id="87524-106">L'integrazione dei valori effettivi è disponibile in Microsoft Dynamics 365 for Finance and Operations versione 8.0.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="87524-106">Actuals integration is available in Microsoft Dynamics 365 for Finance and Operations version 8.0.1 or later.</span></span>
> - <span data-ttu-id="87524-107">Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="87524-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="87524-108">Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="87524-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="87524-109">Flusso di dati per Project Service Automation e Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87524-109">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="87524-110">La soluzione di integrazione di Project Service Automation e Finance and Operations utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-110">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="87524-111">I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consentono il flusso di dati relativi alle categorie di transazioni di spesa di progetto tra Finance and Operations e Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="87524-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="87524-112">Se le categorie di spesa di progetto vengono gestite in Finance and Operations, il flusso di integrazione avviene prima di tutto da Finance and Operations a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="87524-112">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation.</span></span> <span data-ttu-id="87524-113">Gli ID integrazione delle categorie di spesa di progetto vengono quindi aggiornati attraverso la sincronizzazione da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="87524-114">Se le categorie di spesa di progetto vengono gestite in Project Service Automation, il flusso di integrazione avviene prima di tutto da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="87524-115">Le categorie di progetto devono essere già configurate in Finance and Operations prima della sincronizzazione da Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="87524-115">The project categories must already be configured in Finance and Operations before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="87524-116">Occorre quindi sincronizzare di nuovo da Finance and Operations a Project Service Automation e poi da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-116">Then synchronize from Finance and Operations back to Project Service Automation, and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="87524-117">In questo modo, si garantisce che le categorie siano collegate e che non vengano creati duplicati.</span><span class="sxs-lookup"><span data-stu-id="87524-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="87524-118">In genere, le categorie di spesa di progetto vengono gestite in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-118">Typically, the project expense categories are mastered in Finance and Operations.</span></span> <span data-ttu-id="87524-119">Se tuttavia non vengono gestite in Finance and Operations e se le categorie di spesa sono già state create in Project Service Automation, è necessario prima di tutto eseguire la sincronizzazione utilizzando il modello delle categorie di transazione di spesa di progetto (da PSA a Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="87524-119">However, if they aren't mastered in Finance and Operations, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="87524-120">Successivamente si può sincronizzare utilizzando il modello di categorie di transazione di spesa di progetto (da Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="87524-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="87524-121">Si consiglia quindi eseguire ancora una volta la sincronizzazione da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-121">You should then run the synchronization from Project Service Automation to Finance and Operations one more time.</span></span>
>
> <span data-ttu-id="87524-122">Se si esegue la sincronizzazione prima da Project Service Automation, è necessario soddisfare i seguenti requisiti in Finance and Operations prima di avviare la sincronizzazione:</span><span class="sxs-lookup"><span data-stu-id="87524-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance and Operations before the synchronization is run:</span></span>
>
> - <span data-ttu-id="87524-123">La categoria condivisa corrispondente alla categoria di progetto che è impostata in Project Service Automation deve essere presente e deve essere attivata per **Progetto** e per **Spese**.</span><span class="sxs-lookup"><span data-stu-id="87524-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="87524-124">Per ciascuna persona giuridica di Finance and Operations che deve essere integrata, devono essere presenti le seguenti categorie di progetto:</span><span class="sxs-lookup"><span data-stu-id="87524-124">For each Finance and Operations legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="87524-125">**Categoria progetto** esiste.</span><span class="sxs-lookup"><span data-stu-id="87524-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="87524-126">**Usa in Gestione spese** è attivata.</span><span class="sxs-lookup"><span data-stu-id="87524-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="87524-127">**Attivo nei giornali di registrazione** è attivata.</span><span class="sxs-lookup"><span data-stu-id="87524-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="87524-128">**Tipo di transazione** è impostato su **Spesa**.</span><span class="sxs-lookup"><span data-stu-id="87524-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="87524-129">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="87524-130">[![Flusso di dati per l'integrazione di Project Service Automation con Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="87524-130">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a><span data-ttu-id="87524-131">Sincronizzazione delle categorie di spesa del progetto da Finance and Operations a Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="87524-131">Project expense category synchronization from Finance and Operations to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="87524-132">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="87524-132">Template and task</span></span>

<span data-ttu-id="87524-133">Per accedere al modello disponibile, nell'interfaccia di amministrazione di Microsoft PowerApps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="87524-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="87524-134">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie di spesa di progetto da Finance and Operations a Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="87524-134">The following template and underlying task are used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

- <span data-ttu-id="87524-135">**Nome del modello in Integrazione dati:** Categorie di transazione di spesa di progetto (da Fin and Ops a PSA)</span><span class="sxs-lookup"><span data-stu-id="87524-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="87524-136">**Nome dell'attività del progetto:** Sincronizzare le categorie a PSA</span><span class="sxs-lookup"><span data-stu-id="87524-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="87524-137">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="87524-137">Entity set</span></span>

| <span data-ttu-id="87524-138">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87524-138">Finance and Operations</span></span>            | <span data-ttu-id="87524-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="87524-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="87524-140">Entità di integrazione per categorie</span><span class="sxs-lookup"><span data-stu-id="87524-140">Integration entity for categories</span></span> | <span data-ttu-id="87524-141">Categorie di transazioni</span><span class="sxs-lookup"><span data-stu-id="87524-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="87524-142">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="87524-142">Entity flow</span></span>

<span data-ttu-id="87524-143">Le categorie di spesa di progetto vengono gestite in Finance and Operations e vengono sincronizzate con Project Service Automation come categorie di transazioni.</span><span class="sxs-lookup"><span data-stu-id="87524-143">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="87524-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="87524-144">Power Query</span></span>

<span data-ttu-id="87524-145">Quando si sincronizza in Project Service Automation, è necessario utilizzare Microsoft Power Query per Excel per impostare il tipo di fatturazione sulla categoria di transazione.</span><span class="sxs-lookup"><span data-stu-id="87524-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="87524-146">Il modello delle categorie di transazione di spesa di progetto (da Fin and Ops a PSA) include una colonna predefinita e un mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="87524-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="87524-147">Se si crea un modello personale, è necessario aggiungere una colonna condizionale in Power Query.</span><span class="sxs-lookup"><span data-stu-id="87524-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="87524-148">Eseguire i passaggi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="87524-148">Follow these steps.</span></span>

1. <span data-ttu-id="87524-149">Fare clic sulla freccia per aprire il mapping dell'attività categorie di spesa di progetto nel modello di categorie di transazione di spesa di progetto (da Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="87524-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="87524-150">Fare clic sul collegamento **Query avanzata e Filtro avanzato** per aprire Power Query.</span><span class="sxs-lookup"><span data-stu-id="87524-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="87524-151">Selezionare **Aggiungi colonna condizionale**.</span><span class="sxs-lookup"><span data-stu-id="87524-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="87524-152">Immettere un nome per la nuova colonna, ad esempio **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="87524-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="87524-153">Immettere la seguente condizione: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="87524-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="87524-154">Fare clic su **OK** sulla colonna.</span><span class="sxs-lookup"><span data-stu-id="87524-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="87524-155">Assicurarsi di mappare la nuova colonna nella pagina di mapping.</span><span class="sxs-lookup"><span data-stu-id="87524-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="87524-156">Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="87524-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="87524-157">Il mapping mostra le informazioni di campo che verranno sincronizzate da Finance and Operations a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="87524-157">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="87524-158">[![Mapping del modello](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="87524-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="87524-159">Sincronizzazione delle categorie di spesa del progetto da Project Service Automation a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87524-159">Project expense category synchronization from Project Service Automation to Finance and Operations</span></span>

### <a name="template-and-task"></a><span data-ttu-id="87524-160">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="87524-160">Template and task</span></span>

<span data-ttu-id="87524-161">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie di spesa di progetto da Project Service Automation a Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="87524-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

- <span data-ttu-id="87524-162">**Nome del modello in Integrazione dati:** categorie di transazione di spesa di progetto (da PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="87524-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="87524-163">**Nome dell'attività del progetto:** Sincronizzare le categorie in Fin Ops</span><span class="sxs-lookup"><span data-stu-id="87524-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="87524-164">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="87524-164">Entity set</span></span>

| <span data-ttu-id="87524-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="87524-165">Project Service Automation</span></span> | <span data-ttu-id="87524-166">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87524-166">Finance and Operations</span></span>            |
|----------------------------|-----------------------------------|
| <span data-ttu-id="87524-167">Categorie di transazioni</span><span class="sxs-lookup"><span data-stu-id="87524-167">Transaction categories</span></span>     | <span data-ttu-id="87524-168">Entità di integrazione per categorie</span><span class="sxs-lookup"><span data-stu-id="87524-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="87524-169">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="87524-169">Entity flow</span></span>

<span data-ttu-id="87524-170">Le categorie di spesa di progetto vengono gestite in Finance and Operations e vengono sincronizzate con Project Service Automation come categorie di transazioni.</span><span class="sxs-lookup"><span data-stu-id="87524-170">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="87524-171">La nuova sincronizzazione con Finance and Operations aggiorna la categoria di progetto di Finance and Operations con l'ID integrazione da Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="87524-171">The synchronization back to Finance and Operations updates the project category in Finance and Operations with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="87524-172">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="87524-172">Template mapping in Data integration</span></span>

<span data-ttu-id="87524-173">Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="87524-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="87524-174">Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87524-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="87524-175">[![Mapping del modello](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="87524-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

