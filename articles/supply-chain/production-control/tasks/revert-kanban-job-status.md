---
title: Ripristina stato del processo kanban
description: La procedura riguarda il ripristino di uno stato non di processo kanban non corretto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27874f89cede151b52b869fa0d58e320d548e6d3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562209"
---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="ab382-103">Ripristina stato del processo kanban</span><span class="sxs-lookup"><span data-stu-id="ab382-103">Revert kanban job status</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab382-104">La procedura riguarda il ripristino di uno stato non di processo kanban non corretto.</span><span class="sxs-lookup"><span data-stu-id="ab382-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="ab382-105">Questa opzione è utile nel caso dell'operatore che aggiorna il processo sbagliato o imposta lo stato non corretto per errore.</span><span class="sxs-lookup"><span data-stu-id="ab382-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="ab382-106">In questa procedura, un processo kanban viene registrato come preparato per errore e lo stato viene ripristinato.</span><span class="sxs-lookup"><span data-stu-id="ab382-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="ab382-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="ab382-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ab382-108">Questa procedura è destinata al supervisore o all'operatore che opera in una società di produzione snella.</span><span class="sxs-lookup"><span data-stu-id="ab382-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="ab382-109">Aprire la bacheca processo per la cella di lavoro</span><span class="sxs-lookup"><span data-stu-id="ab382-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="ab382-110">Andare a Bacheca kanban per i processi lavorazione.</span><span class="sxs-lookup"><span data-stu-id="ab382-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="ab382-111">Nel campo Cella di lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ab382-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="ab382-112">Selezionare la cella di lavoro 1260.</span><span class="sxs-lookup"><span data-stu-id="ab382-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="ab382-113">Preparare il processo kanban</span><span class="sxs-lookup"><span data-stu-id="ab382-113">Prepare kanban job</span></span>
1. <span data-ttu-id="ab382-114">Fare clic su Prepara.</span><span class="sxs-lookup"><span data-stu-id="ab382-114">Click Prepare.</span></span>
    * <span data-ttu-id="ab382-115">Se non è possibile fare clic su Prepara perché è in grigio, assicurarsi che il processo kanban selezionato abbia lo stato Pianificato, indicato dall'icona kanban vuota.</span><span class="sxs-lookup"><span data-stu-id="ab382-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="ab382-116">Se Prepara ha esito negativo, assicurarsi che tutti i materiali nella distinta di prelievo siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="ab382-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="ab382-117">Selezionare il processo preparato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ab382-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="ab382-118">Selezionare il primo processo appena preparato.</span><span class="sxs-lookup"><span data-stu-id="ab382-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="ab382-119">Si noti che lo stato del processo è Preparato, indicato con un triangolo all'interno dell'icona kanban.</span><span class="sxs-lookup"><span data-stu-id="ab382-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="ab382-120">Reimpostare lo stato del processo kanban preparato</span><span class="sxs-lookup"><span data-stu-id="ab382-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="ab382-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ab382-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ab382-122">Selezionare il primo processo che era stato preparato.</span><span class="sxs-lookup"><span data-stu-id="ab382-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="ab382-123">Nel riquadro azioni, fare clic su Produzione.</span><span class="sxs-lookup"><span data-stu-id="ab382-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="ab382-124">Fare clic su Ripristina stato.</span><span class="sxs-lookup"><span data-stu-id="ab382-124">Click Revert status.</span></span>
    * <span data-ttu-id="ab382-125">È possibile utilizzare una regola kanban alternativa se vengono soddisfatte le seguenti condizioni: - La strategia di rifornimento è uguale per entrambe le regole.</span><span class="sxs-lookup"><span data-stu-id="ab382-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="ab382-126">- La versione del flusso di produzione è uguale per entrambe le regole.</span><span class="sxs-lookup"><span data-stu-id="ab382-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="ab382-127">- Il prodotto che viene fornito è uguale per entrambe le regole.</span><span class="sxs-lookup"><span data-stu-id="ab382-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="ab382-128">- Tutte le attività downstream configurate per l'ultima attività delle regole kanban devono essere uguali per entrambe le regole.</span><span class="sxs-lookup"><span data-stu-id="ab382-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="ab382-129">- Le stesse dimensioni inventariali fornite devono essere configurate per entrambe le regole.</span><span class="sxs-lookup"><span data-stu-id="ab382-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="ab382-130">- Lo stato dell'unità movimentazione deve essere Non assegnato.</span><span class="sxs-lookup"><span data-stu-id="ab382-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="ab382-131">- La configurazione per i kanban evento deve essere uguale.</span><span class="sxs-lookup"><span data-stu-id="ab382-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="ab382-132">Assicurarsi che il nuovo stato sia Pianificato.</span><span class="sxs-lookup"><span data-stu-id="ab382-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="ab382-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ab382-133">Click OK.</span></span>
5. <span data-ttu-id="ab382-134">Nell'elenco deselezionare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ab382-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="ab382-135">Selezionare lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="ab382-135">Select the same job.</span></span>  
    * <span data-ttu-id="ab382-136">Si noti che lo stato del processo kanban viene reimpostato su Pianificato, indicato da un'icona kanban vuota.</span><span class="sxs-lookup"><span data-stu-id="ab382-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  

