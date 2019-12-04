---
title: Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Microsoft Dynamics 365 Finance e Dynamics 365 Project Service Automation.
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
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 7b0b3721c3b0755218c834d2bf77ec976be3bdcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770314"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="f5bc5-103">Sincronizzare le categorie di spesa del progetto tra Finance and Operations and Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f5bc5-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f5bc5-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le categorie di spesa di progetto tra Dynamics 365 Finance e Dynamics 365 Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Dynamics 365 Finance and Dynamics 365 Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="f5bc5-105">L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili nella versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="f5bc5-106">L'integrazione dei numeri effettivi è disponibile nella versione 8.0.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-106">Actuals integration is available in version 8.0.1 or later.</span></span>
> - <span data-ttu-id="f5bc5-107">Se si utilizza Enterprise Edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-107">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="f5bc5-108">Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance"></a><span data-ttu-id="f5bc5-109">Flusso di dati per Project Service Automation e Finance</span><span class="sxs-lookup"><span data-stu-id="f5bc5-109">Data flow for Project Service Automation and Finance</span></span>

<span data-ttu-id="f5bc5-110">La soluzione di integrazione di Project Service Automation e Finance utilizza la funzionalità di integrazione dei dati per sincronizzare i dati tra istanze di Project Service Automation e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-110">The Project Service Automation and Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="f5bc5-111">I modelli di integrazione disponibili con la funzionalità di integrazione dei dati consentono il flusso di dati relativi alle categorie di transazioni di spesa di progetto tra Finance e Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Project Service Automation.</span></span>

<span data-ttu-id="f5bc5-112">Se le categorie di spesa di progetto vengono gestite in Finance, il flusso di integrazione avviene prima di tutto da Finance a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-112">If the project expense categories are mastered in Finance, the integration flow is first from Finance to Project Service Automation.</span></span> <span data-ttu-id="f5bc5-113">Gli ID integrazione delle categorie di spesa di progetto vengono quindi aggiornati attraverso la sincronizzazione da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance.</span></span>

<span data-ttu-id="f5bc5-114">Se le categorie di spesa di progetto vengono gestite in Project Service Automation, il flusso di integrazione avviene prima di tutto da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance.</span></span> <span data-ttu-id="f5bc5-115">Le categorie di progetto devono essere già configurate in Finance prima della sincronizzazione da Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-115">The project categories must already be configured in Finance before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="f5bc5-116">Occorre quindi sincronizzare di nuovo da Finance a Project Service Automation e poi da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-116">Then synchronize from Finance back to Project Service Automation, and then from Project Service Automation to Finance again.</span></span> <span data-ttu-id="f5bc5-117">In questo modo, si garantisce che le categorie siano collegate e che non vengano creati duplicati.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="f5bc5-118">In genere, le categorie di spesa di progetto vengono gestite in Finance.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-118">Typically, the project expense categories are mastered in Finance.</span></span> <span data-ttu-id="f5bc5-119">Se tuttavia non vengono gestite o se le categorie di spesa sono già state create in Project Service Automation, è necessario prima di tutto eseguire la sincronizzazione utilizzando il modello delle categorie di transazione di spesa di progetto (da PSA a Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="f5bc5-119">However, if they aren't, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="f5bc5-120">Successivamente si può sincronizzare utilizzando il modello di categorie di transazione di spesa di progetto (da Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="f5bc5-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="f5bc5-121">Si consiglia quindi eseguire ancora una volta la sincronizzazione da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-121">You should then run the synchronization from Project Service Automation to Finance one more time.</span></span>
>
> <span data-ttu-id="f5bc5-122">Se si esegue la sincronizzazione prima da Project Service Automation, è necessario soddisfare i seguenti requisiti in Finance prima di avviare la sincronizzazione:</span><span class="sxs-lookup"><span data-stu-id="f5bc5-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance before the synchronization is run:</span></span>
>
> - <span data-ttu-id="f5bc5-123">La categoria condivisa corrispondente alla categoria di progetto che è impostata in Project Service Automation deve essere presente e deve essere attivata per **Progetto** e per **Spese**.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="f5bc5-124">Per ciascuna persona giuridica di Finance che deve essere integrata, devono essere presenti le seguenti categorie di progetto:</span><span class="sxs-lookup"><span data-stu-id="f5bc5-124">For each Finance legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="f5bc5-125">**Categoria progetto** esiste.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="f5bc5-126">**Usa in Gestione spese** è attivata.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="f5bc5-127">**Attivo nei giornali di registrazione** è attivata.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="f5bc5-128">**Tipo di transazione** è impostato su **Spesa**.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="f5bc5-129">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Project Service Automation e Finance.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="f5bc5-130">[![Flusso di dati per l'integrazione di Project Service Automation con Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="f5bc5-130">[![Data flow for Project Service Automation integration with Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a><span data-ttu-id="f5bc5-131">Sincronizzazione delle categorie di spesa del progetto da Finance a Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f5bc5-131">Project expense category synchronization from Finance to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="f5bc5-132">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="f5bc5-132">Template and task</span></span>

<span data-ttu-id="f5bc5-133">Per accedere al modello disponibile, nell'interfaccia di amministrazione di Microsoft Power Apps selezionare **Progetti** e quindi, nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-133">To access the template, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="f5bc5-134">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie delle spese da Finance a Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="f5bc5-134">The following template and underlying task are used to synchronize project expense categories from Finance to Project Service Automation:</span></span>

- <span data-ttu-id="f5bc5-135">**Nome del modello in Integrazione dati:** Categorie di transazione di spesa di progetto (da Fin and Ops a PSA)</span><span class="sxs-lookup"><span data-stu-id="f5bc5-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="f5bc5-136">**Nome dell'attività del progetto:** Sincronizzare le categorie a PSA</span><span class="sxs-lookup"><span data-stu-id="f5bc5-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="f5bc5-137">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="f5bc5-137">Entity set</span></span>

| <span data-ttu-id="f5bc5-138">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="f5bc5-138">Finance</span></span>                           | <span data-ttu-id="f5bc5-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f5bc5-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="f5bc5-140">Entità di integrazione per categorie</span><span class="sxs-lookup"><span data-stu-id="f5bc5-140">Integration entity for categories</span></span> | <span data-ttu-id="f5bc5-141">Categorie di transazioni</span><span class="sxs-lookup"><span data-stu-id="f5bc5-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="f5bc5-142">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="f5bc5-142">Entity flow</span></span>

<span data-ttu-id="f5bc5-143">Le categorie di spesa di progetto vengono gestite in Finance e vengono sincronizzate con Project Service Automation come categorie di transazioni.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-143">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="f5bc5-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="f5bc5-144">Power Query</span></span>

<span data-ttu-id="f5bc5-145">Quando si sincronizza in Project Service Automation, è necessario utilizzare Microsoft Power Query per Excel per impostare il tipo di fatturazione sulla categoria di transazione.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="f5bc5-146">Il modello delle categorie di transazione di spesa di progetto (da Fin and Ops a PSA) include una colonna predefinita e un mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="f5bc5-147">Se si crea un modello personale, è necessario aggiungere una colonna condizionale in Power Query.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="f5bc5-148">Eseguire i passaggi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-148">Follow these steps.</span></span>

1. <span data-ttu-id="f5bc5-149">Fare clic sulla freccia per aprire il mapping dell'attività categorie di spesa di progetto nel modello di categorie di transazione di spesa di progetto (da Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="f5bc5-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="f5bc5-150">Fare clic sul collegamento **Query avanzata e Filtro avanzato** per aprire Power Query.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="f5bc5-151">Selezionare **Aggiungi colonna condizionale**.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="f5bc5-152">Immettere un nome per la nuova colonna, ad esempio **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="f5bc5-153">Immettere la seguente condizione: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="f5bc5-154">Fare clic su **OK** sulla colonna.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="f5bc5-155">Assicurarsi di mappare la nuova colonna nella pagina di mapping.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="f5bc5-156">Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="f5bc5-157">Il mapping mostra le informazioni di campo che verranno sincronizzate da Finance a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-157">The mapping shows the field information that will be synchronized from Finance to Project Service Automation.</span></span>

<span data-ttu-id="f5bc5-158">[![Mapping del modello](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="f5bc5-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a><span data-ttu-id="f5bc5-159">Sincronizzazione delle categorie di spesa del progetto da Project Service Automation a Finance</span><span class="sxs-lookup"><span data-stu-id="f5bc5-159">Project expense category synchronization from Project Service Automation to Finance</span></span>

### <a name="template-and-task"></a><span data-ttu-id="f5bc5-160">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="f5bc5-160">Template and task</span></span>

<span data-ttu-id="f5bc5-161">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare le categorie delle spese da Project Service Automation a Finance:</span><span class="sxs-lookup"><span data-stu-id="f5bc5-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="f5bc5-162">**Nome del modello in Integrazione dati:** categorie di transazione di spesa di progetto (da PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="f5bc5-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="f5bc5-163">**Nome dell'attività del progetto:** Sincronizzare le categorie in Fin Ops</span><span class="sxs-lookup"><span data-stu-id="f5bc5-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="f5bc5-164">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="f5bc5-164">Entity set</span></span>

| <span data-ttu-id="f5bc5-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f5bc5-165">Project Service Automation</span></span> | <span data-ttu-id="f5bc5-166">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="f5bc5-166">Finance</span></span>                           |
|----------------------------|-----------------------------------|
| <span data-ttu-id="f5bc5-167">Categorie di transazioni</span><span class="sxs-lookup"><span data-stu-id="f5bc5-167">Transaction categories</span></span>     | <span data-ttu-id="f5bc5-168">Entità di integrazione per categorie</span><span class="sxs-lookup"><span data-stu-id="f5bc5-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="f5bc5-169">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="f5bc5-169">Entity flow</span></span>

<span data-ttu-id="f5bc5-170">Le categorie di spesa di progetto vengono gestite in Finance e vengono sincronizzate con Project Service Automation come categorie di transazioni.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-170">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="f5bc5-171">La nuova sincronizzazione con Finance aggiorna la categoria di progetto di Finance con l'ID integrazione da Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-171">The synchronization back to Finance updates the project category in Finance with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f5bc5-172">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="f5bc5-172">Template mapping in Data integration</span></span>

<span data-ttu-id="f5bc5-173">Nella figura seguente viene mostrato un esempio del mapping delle attività di modello in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="f5bc5-174">Il mapping mostra le informazioni di campo che verranno sincronizzate da Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="f5bc5-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="f5bc5-175">[![Mapping del modello](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="f5bc5-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
