---
title: Elementi flusso di lavoro
description: Questo articolo descrive i vari elementi che costituiscono un flusso di lavoro.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 255777651a45b899850fc870c9da288f65df702c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="workflow-elements"></a><span data-ttu-id="6d8eb-103">Elementi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6d8eb-103">Workflow elements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6d8eb-104">Questo articolo descrive i vari elementi che costituiscono un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-104">This article describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="6d8eb-105">Un flusso di lavoro è costituito da elementi.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-105">A workflow consists of elements.</span></span> <span data-ttu-id="6d8eb-106">Nelle sezioni indicate di seguito viene descritto ciascun tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="6d8eb-107">Attività</span><span class="sxs-lookup"><span data-stu-id="6d8eb-107">Tasks</span></span>
<span data-ttu-id="6d8eb-108">Un'*attività* è un'unità di lavoro che deve essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="6d8eb-109">Sono disponibili due tipi di attività che possono essere aggiunte a un flusso di lavoro: un'attività manuale o un'attività automatica.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="6d8eb-110">Attività manuale</span><span class="sxs-lookup"><span data-stu-id="6d8eb-110">Manual task</span></span>

<span data-ttu-id="6d8eb-111">Un'*attività manuale* è un'unità di lavoro che deve essere eseguita da un utente.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="6d8eb-112">Un flusso di lavoro relativo a una nota spese, ad esempio, può includere attività manuali che richiedono agli utenti assegnatari di completare le operazioni indicate di seguito:</span><span class="sxs-lookup"><span data-stu-id="6d8eb-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

-   <span data-ttu-id="6d8eb-113">Esaminare le ricevute inviate con una nota spese.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-113">Review the receipts that are submitted together with an expense report.</span></span>
-   <span data-ttu-id="6d8eb-114">Chiamare il manager del dipendente.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="6d8eb-115">Attività automatica</span><span class="sxs-lookup"><span data-stu-id="6d8eb-115">Automated task</span></span>

<span data-ttu-id="6d8eb-116">Un'*attività automatica* è un'unità di lavoro che deve essere eseguita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="6d8eb-117">Non richiede interazione umana.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-117">No human interaction is required.</span></span> <span data-ttu-id="6d8eb-118">Un flusso di lavoro relativo a un ordine cliente, ad esempio, può includere attività automatiche che prevedono il completamento delle operazioni indicate di seguito da parte del sistema:</span><span class="sxs-lookup"><span data-stu-id="6d8eb-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

-   <span data-ttu-id="6d8eb-119">Eseguire una verifica del credito.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-119">Perform a credit check.</span></span>
-   <span data-ttu-id="6d8eb-120">Creare un record per il cliente, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="6d8eb-121">Processi di approvazione</span><span class="sxs-lookup"><span data-stu-id="6d8eb-121">Approval processes</span></span>
<span data-ttu-id="6d8eb-122">Un *processo di approvazione* è costituito da vari passaggi separati.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="6d8eb-123">A ogni passaggio di approvazione, l'utente può eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d8eb-123">At each approval step, the user can perform the following actions:</span></span>

-   <span data-ttu-id="6d8eb-124">Consente di approvare il documento.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-124">Approve the document.</span></span>
-   <span data-ttu-id="6d8eb-125">Consente di rifiutare il documento.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-125">Reject the document.</span></span>
-   <span data-ttu-id="6d8eb-126">Richiedere una modifica del documento.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-126">Request a change to the document.</span></span>
-   <span data-ttu-id="6d8eb-127">Assegnare il documento a un altro utente per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-127">Assign the document to another user for approval.</span></span>

## <a name="lineitem-workflow-elements"></a><span data-ttu-id="6d8eb-128">Elemento del flusso di lavoro voci</span><span class="sxs-lookup"><span data-stu-id="6d8eb-128">Lineitem workflow elements</span></span>
<span data-ttu-id="6d8eb-129">È possibile creare un flusso di lavoro per elaborare documenti o le voci in un documento.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="6d8eb-130">Si supponga ad esempio di aver creato un flusso di lavoro di approvazione per fogli presenze.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="6d8eb-131">Verrà fatto riferimento al flusso di lavoro come *flusso di lavoro del documento*. È possibile aggiungere un *flusso di lavoro voci* a tale flusso di lavoro del documento.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="6d8eb-132">Quando viene eseguito l'elemento voce, ogni voce nel documento viene inviata per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="6d8eb-133">È possibile decidere di elaborare tutte le voci tramite lo stesso flusso di lavoro voci oppure elaborare ogni singola voce tramite un flusso di lavoro voci diverso.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="6d8eb-134">Si supponga che un dipendente abbia inviato un foglio presenze analogo a quello illustrato nella figura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span>

![Flusso di lavoro con voci](./media/workflow_lineitemworkflow.gif) 

<span data-ttu-id="6d8eb-136">In questo scenario è possibile creare i flussi di lavoro voci seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d8eb-136">In this scenario, you might want to create the following line-item workflows:</span></span>

-   <span data-ttu-id="6d8eb-137">**Flusso di lavoro voci 1**: questo flusso di lavoro viene utilizzato per elaborare le voci con ID progetto 1111.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-137">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
-   <span data-ttu-id="6d8eb-138">**Flusso di lavoro voci 2**: questo flusso di lavoro viene utilizzato per elaborare le voci con ID progetto 2222.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-138">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
-   <span data-ttu-id="6d8eb-139">**Flusso di lavoro voci 3**: questo flusso di lavoro viene utilizzato per elaborare le voci con ID progetto 3333.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-139">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flowcontrol-elements"></a><span data-ttu-id="6d8eb-140">Elementi del controllo di flusso</span><span class="sxs-lookup"><span data-stu-id="6d8eb-140">Flowcontrol elements</span></span>
<span data-ttu-id="6d8eb-141">Gli elementi indicati di seguito consentono di progettare flussi di lavoro con rami alternati o rami eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-141">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="6d8eb-142">Decisione manuale</span><span class="sxs-lookup"><span data-stu-id="6d8eb-142">Manual decision</span></span>

<span data-ttu-id="6d8eb-143">Una *decisione manuale* rappresenta un punto in cui un flusso di lavoro si suddivide in due rami.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-143">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="6d8eb-144">Un utente deve prendere una decisione che determinerà quale ramo del flusso di lavoro verrà utilizzato per elaborare il documento inviato.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-144">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="6d8eb-145">Decisione condizionale</span><span class="sxs-lookup"><span data-stu-id="6d8eb-145">Conditional decision</span></span>

<span data-ttu-id="6d8eb-146">Una *decisione condizionale* rappresenta anch'essa un punto in cui un flusso di lavoro si suddivide in due rami.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-146">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="6d8eb-147">Tuttavia, il sistema decide quale ramo del flusso di lavoro viene utilizzato per elaborare il documento inviato.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-147">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="6d8eb-148">A tale scopo, il sistema valuta il record per determinare se soddisfa le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-148">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="6d8eb-149">Attività parallela</span><span class="sxs-lookup"><span data-stu-id="6d8eb-149">Parallel activity</span></span>

<span data-ttu-id="6d8eb-150">Un'*attività parallela* è un elemento del flusso di lavoro che include due o più rami del flusso eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-150">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="6d8eb-151">Flusso di lavoro secondario</span><span class="sxs-lookup"><span data-stu-id="6d8eb-151">Subworkflow</span></span>

<span data-ttu-id="6d8eb-152">Un *flusso di lavoro secondario* è un flusso di lavoro eseguito nel contesto di un altro flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6d8eb-152">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>




