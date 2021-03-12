---
title: Panoramica del sistema del flusso di lavoro
description: Viene descritto il sistema flusso di lavoro.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660e01618eea66bc611dd51818694d36993ba9ea
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796998"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="aace4-103">Panoramica del sistema del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aace4-104">Viene descritto il sistema flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aace4-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="aace4-105">Flusso di lavoro e Workflow</span><span class="sxs-lookup"><span data-stu-id="aace4-105">What is workflow?</span></span>

<span data-ttu-id="aace4-106">Il termine *flusso di lavoro* può essere definito in due modi: come un sistema e come un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="aace4-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="aace4-107">Flusso di lavoro: il sistema</span><span class="sxs-lookup"><span data-stu-id="aace4-107">Workflow is a system</span></span>

<span data-ttu-id="aace4-108">Il flusso di lavoro è un sistema che viene eseguito sul server oggetti applicativi (AOS).</span><span class="sxs-lookup"><span data-stu-id="aace4-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="aace4-109">Nel sistema sono disponibili funzionalità che consentono di creare singoli flussi di lavoro o processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="aace4-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="aace4-110">Flusso di lavoro: il processo aziendale</span><span class="sxs-lookup"><span data-stu-id="aace4-110">Workflow is a business process</span></span>

<span data-ttu-id="aace4-111">Un flusso di lavoro rappresenta un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="aace4-111">A workflow represents a business process.</span></span> <span data-ttu-id="aace4-112">Definisce il modo in cui un documento attraversa il sistema, o si sposta al suo interno, identificando chi deve completare un'attività, prendere una decisione o approvare un documento.</span><span class="sxs-lookup"><span data-stu-id="aace4-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="aace4-113">Nella figura indicata di seguito viene illustrato un esempio di un flusso di lavoro per note spese.</span><span class="sxs-lookup"><span data-stu-id="aace4-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Flusso di lavoro con elementi assegnati a utenti](./media/workflow_user.gif)

<span data-ttu-id="aace4-115">Per meglio comprendere questo flusso di lavoro, si supponga ora che Giorgio invii una nota spese per un importo pari a USD 7.000.</span><span class="sxs-lookup"><span data-stu-id="aace4-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="aace4-116">In questo scenario Indro deve verificare le ricevute inoltrate da Giorgio,</span><span class="sxs-lookup"><span data-stu-id="aace4-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="aace4-117">quindi Ezio e Luisa devono approvare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="aace4-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="aace4-118">Si supponga ora che Giorgio presenti una nota spese per un importo pari a USD 11.000.</span><span class="sxs-lookup"><span data-stu-id="aace4-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="aace4-119">In questo scenario Indro deve verificare le ricevute e Ezio, Luisa e Elena devono approvare la nota spese.</span><span class="sxs-lookup"><span data-stu-id="aace4-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="aace4-120">Vantaggi del sistema del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="aace4-121">Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="aace4-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="aace4-122">**Processi coerenti**: è possibile definire il processo di elaborazione di documenti specifici, ad esempio richieste di acquisto e note spese.</span><span class="sxs-lookup"><span data-stu-id="aace4-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="aace4-123">L'utilizzo del sistema di flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.</span><span class="sxs-lookup"><span data-stu-id="aace4-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="aace4-124">**Visibilità dei processi**: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di istanze di flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aace4-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="aace4-125">In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="aace4-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="aace4-126">**Elenco di lavoro centralizzato**: gli utenti possono visualizzare un elenco di lavoro centralizzato contenente le attività del flusso di lavoro e le approvazioni assegnati.</span><span class="sxs-lookup"><span data-stu-id="aace4-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="aace4-127">Contenuto del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-127">Workflow content</span></span>

+ [<span data-ttu-id="aace4-128">Architettura del sistema del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="aace4-129">Elementi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="aace4-130">Azioni dei processi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="aace4-131">Creare panoramica flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="aace4-132">Configurare le proprietà del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="aace4-133">Configurare le attività manuali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="aace4-134">Configurare le attività automatiche in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="aace4-135">Configurare i processi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="aace4-136">Configurare i passaggi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="aace4-137">Configurare le decisioni manuali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="aace4-138">Configurare le decisioni condizionali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="aace4-139">Configurare le attività parallele in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="aace4-140">Configurare i rami paralleli in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="aace4-141">Configurare flussi di lavoro voci</span><span class="sxs-lookup"><span data-stu-id="aace4-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="aace4-142">Domande frequenti sul flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="aace4-142">Workflow FAQ</span></span>](workflow-FAQ.md)
