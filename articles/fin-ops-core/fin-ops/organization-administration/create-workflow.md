---
title: Panoramica della creazione di flussi di lavoro
description: In questo argomento viene illustrato come creare un flusso di lavoro.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 23fe13f7e3c7e8138b690c96fafc075c4700a60f
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693308"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="0131f-103">Panoramica di creazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0131f-104">In questo argomento viene illustrato come creare un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0131f-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="0131f-105">Aprire l'editor flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-105">Open the workflow editor</span></span>

<span data-ttu-id="0131f-106">Il modulo in uso determina i tipi di flusso di lavoro che è possibile creare.</span><span class="sxs-lookup"><span data-stu-id="0131f-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="0131f-107">Per selezionare il tipo di flusso di lavoro da creare e aprire l'editor flusso di lavoro, eseguire i passaggi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="0131f-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="0131f-108">Aprire il modulo per il quale si desidera creare un nuovo flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0131f-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="0131f-109">Ad esempio, per creare un flusso di lavoro per le richieste di acquisto, fare clic su **Approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="0131f-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="0131f-110">Fare clic su **Impostazione** &gt; **\[Nome modulo\] - flussi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="0131f-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="0131f-111">Nella pagina elenco visualizzata, nel riquadro azioni, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0131f-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="0131f-112">Nella pagina **Crea flusso di lavoro**, selezionare il tipo di flusso di lavoro da creare e fare clic su **Crea flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="0131f-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="0131f-113">Viene visualizzato l'editor flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0131f-113">The workflow editor appears.</span></span> <span data-ttu-id="0131f-114">Per progettare il flusso di lavoro, è ora possibile usare le procedure indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0131f-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="0131f-115">Trascinare gli elementi del flusso di lavoro nella canvas</span><span class="sxs-lookup"><span data-stu-id="0131f-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="0131f-116">L'area **Elementi flusso di lavoro** dell'editor flusso di lavoro contiene gli elementi che è possibile aggiungere al flusso.</span><span class="sxs-lookup"><span data-stu-id="0131f-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="0131f-117">Per aggiungere elementi al flusso di lavoro, trascinarli nella canvas.</span><span class="sxs-lookup"><span data-stu-id="0131f-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="0131f-118">Connettere gli elementi</span><span class="sxs-lookup"><span data-stu-id="0131f-118">Connect the elements</span></span>

<span data-ttu-id="0131f-119">Per connettere un elemento del flusso di lavoro a un altro, tenere premuto il puntatore su un elemento finché non verranno visualizzati punti di connessione.</span><span class="sxs-lookup"><span data-stu-id="0131f-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="0131f-120">Fare clic su un punto di connessione e trascinarlo su un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="0131f-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="0131f-121">Verificare di connettere tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0131f-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="0131f-122">Configurare le proprietà del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="0131f-123">Per configurare le proprietà del flusso di lavoro, eseguire i passaggi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="0131f-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="0131f-124">Per verificare che non sia selezionato alcun elemento del flusso di lavoro, fare clic sulla canvas.</span><span class="sxs-lookup"><span data-stu-id="0131f-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="0131f-125">Fare clic su **Proprietà** per aprire la pagina **Proprietà** per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0131f-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="0131f-126">Seguire le procedure nell'argomento [Configurare le proprietà del flusso di lavoro](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0131f-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="0131f-127">Configurare gli elementi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="0131f-128">Configurare ogni elemento trascinato nella canvas.</span><span class="sxs-lookup"><span data-stu-id="0131f-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="0131f-129">Per ulteriori informazioni su come configurare ciascun elemento del flusso di lavoro, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="0131f-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="0131f-130">Configurare le attività manuali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="0131f-131">Configurare le attività automatiche in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="0131f-132">Configurare i processi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="0131f-133">Configurare i passaggi di approvazione in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="0131f-134">Configurare le decisioni manuali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="0131f-135">Configurare le decisioni condizionali in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="0131f-136">Configurare i rami paralleli in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="0131f-137">Configurare un ramo parallelo</span><span class="sxs-lookup"><span data-stu-id="0131f-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="0131f-138">Configurare flussi di lavoro voci</span><span class="sxs-lookup"><span data-stu-id="0131f-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="0131f-139">Risolvere eventuali errori o avvisi</span><span class="sxs-lookup"><span data-stu-id="0131f-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="0131f-140">Nel riquadro **Errori e avvisi** situato nella parte inferiore dell'editor flusso di lavoro vengono visualizzati i messaggi generati per il flusso.</span><span class="sxs-lookup"><span data-stu-id="0131f-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="0131f-141">Per individuare l'elemento in cui si è verificato un errore o un avviso, fare doppio clic sul relativo messaggio.</span><span class="sxs-lookup"><span data-stu-id="0131f-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="0131f-142">Per rendere il flusso di lavoro attivo, è necessario risolvere tutti gli errori e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="0131f-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="0131f-143">Salvare e attivare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0131f-143">Save and activate the workflow</span></span>

<span data-ttu-id="0131f-144">Per salvare e attivare il flusso di lavoro, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="0131f-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="0131f-145">Fare clic su **Salva e chiudi** per chiudere l'editor flusso di lavoro e aprire la pagina **Salva flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="0131f-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="0131f-146">Immettere commenti sulle modifiche apportate al flusso di lavoro, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0131f-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="0131f-147">Se sono stati risolti tutti gli errori e gli avvisi, verrà visualizzata la pagina **Attiva flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="0131f-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="0131f-148">Consente di selezionare una delle opzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0131f-148">Select one of the following options:</span></span>

    - <span data-ttu-id="0131f-149">Per attivare questa versione del flusso di lavoro, fare clic su **Attiva la nuova versione**.</span><span class="sxs-lookup"><span data-stu-id="0131f-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="0131f-150">Quando un flusso di lavoro è attivo, l'utente è in grado di inviare documenti per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="0131f-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="0131f-151">Se non si desidera attivare questa versione, fare clic su **Non attivare la nuova versione**.</span><span class="sxs-lookup"><span data-stu-id="0131f-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="0131f-152">Sarà possibile attivare il flusso di lavoro in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0131f-152">You can activate the workflow later.</span></span>
