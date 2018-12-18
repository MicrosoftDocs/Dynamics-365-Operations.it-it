---
title: Sistema del flusso di lavoro
description: Viene descritto il sistema flusso di lavoro in Microsoft Dynamics 365 for Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: 7eb6d743131937081ce83b31988d792185cb28b2
ms.contentlocale: it-it
ms.lasthandoff: 12/18/2018

---

# <a name="workflow-system"></a><span data-ttu-id="eaa89-103">Sistema del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eaa89-104">Viene descritto il sistema flusso di lavoro in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eaa89-104">This topic describes the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="eaa89-105">Flusso di lavoro e Workflow</span><span class="sxs-lookup"><span data-stu-id="eaa89-105">What is workflow?</span></span>

<span data-ttu-id="eaa89-106">Il termine *flusso di lavoro* può essere definito in due modi: come un sistema e come un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="eaa89-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="eaa89-107">Flusso di lavoro: il sistema</span><span class="sxs-lookup"><span data-stu-id="eaa89-107">Workflow is a system</span></span>

<span data-ttu-id="eaa89-108">Il sistema del flusso di lavoro viene installato con Finance and Operations e viene eseguito nel server oggetti applicativi (AOS).</span><span class="sxs-lookup"><span data-stu-id="eaa89-108">Workflow is a system that is installed with Finance and Operations and runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="eaa89-109">Nel sistema sono disponibili funzionalità che consentono di creare singoli flussi di lavoro o processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="eaa89-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="eaa89-110">Flusso di lavoro: il processo aziendale</span><span class="sxs-lookup"><span data-stu-id="eaa89-110">Workflow is a business process</span></span>

<span data-ttu-id="eaa89-111">Un flusso di lavoro rappresenta un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="eaa89-111">A workflow represents a business process.</span></span> <span data-ttu-id="eaa89-112">Definisce il modo in cui un documento attraversa il sistema, o si sposta al suo interno, identificando chi deve completare un'attività, prendere una decisione o approvare un documento.</span><span class="sxs-lookup"><span data-stu-id="eaa89-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="eaa89-113">Nella figura indicata di seguito viene illustrato un esempio di un flusso di lavoro per note spese.</span><span class="sxs-lookup"><span data-stu-id="eaa89-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Flusso di lavoro con elementi assegnati a utenti](./media/workflow_user.gif)

<span data-ttu-id="eaa89-115">Per meglio comprendere questo flusso di lavoro, si supponga ora che Giorgio invii una nota spese per un importo pari a USD 7.000.</span><span class="sxs-lookup"><span data-stu-id="eaa89-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="eaa89-116">In questo scenario Indro deve verificare le ricevute inoltrate da Giorgio,</span><span class="sxs-lookup"><span data-stu-id="eaa89-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="eaa89-117">quindi Ezio e Luisa devono approvare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="eaa89-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="eaa89-118">Si supponga ora che Giorgio presenti una nota spese per un importo pari a USD 11.000.</span><span class="sxs-lookup"><span data-stu-id="eaa89-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="eaa89-119">In questo scenario Indro deve verificare le ricevute e Ezio, Luisa e Elena devono approvare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="eaa89-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="eaa89-120">Vantaggi del sistema del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="eaa89-121">Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="eaa89-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="eaa89-122">**Processi coerenti**: è possibile definire il processo di elaborazione di documenti specifici, ad esempio richieste di acquisto e note spese.</span><span class="sxs-lookup"><span data-stu-id="eaa89-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="eaa89-123">L'utilizzo del sistema di flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.</span><span class="sxs-lookup"><span data-stu-id="eaa89-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="eaa89-124">**Visibilità dei processi**: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di istanze di flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="eaa89-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="eaa89-125">In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="eaa89-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="eaa89-126">**Elenco di lavoro centralizzato**: gli utenti possono visualizzare un elenco di lavoro centralizzato contenente le attività del flusso di lavoro e le approvazioni assegnati.</span><span class="sxs-lookup"><span data-stu-id="eaa89-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="eaa89-127">Contenuto del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-127">Workflow content</span></span>

+ [<span data-ttu-id="eaa89-128">Architettura del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-128">Workflow architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="eaa89-129">Elementi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="eaa89-130">Azioni flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-130">Workflow actions</span></span>](workflow-actions.md)
+ [<span data-ttu-id="eaa89-131">Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-131">Create a workflow</span></span>](create-workflow.md)
+ [<span data-ttu-id="eaa89-132">Configurare le proprietà del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="eaa89-133">Configurare un'attività manuale in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-133">Configure a manual task in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="eaa89-134">Configurare un'attività automatica in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-134">Configure an automated task in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="eaa89-135">Configurare un processo di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-135">Configure an approval process in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="eaa89-136">Configurare un passaggio di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-136">Configure an approval step in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="eaa89-137">Configurare una decisione manuale in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-137">Configure a manual decision in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="eaa89-138">Configurare una decisione condizionale in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-138">Configure a conditional decision in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="eaa89-139">Configurare un'attività parallela in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-139">Configure a parallel activity in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="eaa89-140">Configurare un ramo parallelo in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eaa89-140">Configure a parallel branch in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="eaa89-141">Configurare un flusso di lavoro voci</span><span class="sxs-lookup"><span data-stu-id="eaa89-141">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)

