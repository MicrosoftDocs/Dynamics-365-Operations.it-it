--- 
title: Programmazione processi kanban
description: Questa procedura riguarda la programmazione dei processi kanban di lavorazione per una cella di lavoro specifica.
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 692a867eae15ac02f7042c69b9dde4f1fcbd0d54
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="schedule-kanban-jobs"></a><span data-ttu-id="64c8f-103">Programmazione processi kanban</span><span class="sxs-lookup"><span data-stu-id="64c8f-103">Schedule kanban jobs</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64c8f-104">Questa procedura riguarda la programmazione dei processi kanban di lavorazione per una cella di lavoro specifica.</span><span class="sxs-lookup"><span data-stu-id="64c8f-104">This procedure focuses on scheduling process kanban jobs for a specific work cell.</span></span> <span data-ttu-id="64c8f-105">La procedura "Preparare un processo kanban quando non sono disponibili materiali per la cella di lavoro" è un prerequisito per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="64c8f-105">The procedure "Prepare a process kanban job when materials are not available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="64c8f-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="64c8f-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="64c8f-107">Questa attività è destinata al supervisore dello shop floor e al responsabile di pianificazione della produzione che utilizzano i processi kanban.</span><span class="sxs-lookup"><span data-stu-id="64c8f-107">This task is intended for the shop floor supervisor and production planner working with kanbans.</span></span>


## <a name="select-kanban-jobs-for-a-work-cell"></a><span data-ttu-id="64c8f-108">Selezionare processi kanban per una cella di lavoro</span><span class="sxs-lookup"><span data-stu-id="64c8f-108">Select kanban jobs for a work cell</span></span>
1. <span data-ttu-id="64c8f-109">Andare a Controllo produzione > Kanban > Programmazione processo kanban.</span><span class="sxs-lookup"><span data-stu-id="64c8f-109">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="64c8f-110">Espandere il riquadro Dettaglio informazioni della capacità periodo</span><span class="sxs-lookup"><span data-stu-id="64c8f-110">Expand the Period capacity fact box</span></span>
    * <span data-ttu-id="64c8f-111">Espandere il riquadro Dettaglio informazioni kanban.</span><span class="sxs-lookup"><span data-stu-id="64c8f-111">Expand the Kanban FactBox.</span></span>  
3. <span data-ttu-id="64c8f-112">Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="64c8f-112">In the Work cell field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="64c8f-113">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="64c8f-113">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="64c8f-114">Selezionare la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="64c8f-114">Select work cell 1250.</span></span> <span data-ttu-id="64c8f-115">In questo modo verrà filtrata la visualizzazione per mostrare solo i processi per la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="64c8f-115">This will filter the view to display only the jobs for work cell 1250.</span></span>  
5. <span data-ttu-id="64c8f-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="64c8f-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="64c8f-117">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="64c8f-117">Click Select.</span></span>

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a><span data-ttu-id="64c8f-118">Programmare un processo kanban nel primo periodo disponibile</span><span class="sxs-lookup"><span data-stu-id="64c8f-118">Schedule a kanban job in the first available period</span></span>
1. <span data-ttu-id="64c8f-119">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="64c8f-119">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="64c8f-120">Selezionare la prima riga nell'elenco con lo stato Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="64c8f-120">Select the first row in the list that has the Not planned status.</span></span> <span data-ttu-id="64c8f-121">L'icona punteggiata nel campo Stato del processo indica uno stato non pianificato.</span><span class="sxs-lookup"><span data-stu-id="64c8f-121">The dotted icon in the Job status field indicates not planned.</span></span>  
2. <span data-ttu-id="64c8f-122">Fare clic su Programma.</span><span class="sxs-lookup"><span data-stu-id="64c8f-122">Click Schedule.</span></span>
    * <span data-ttu-id="64c8f-123">In questo modo il processo kanban verrà programmato nel primo periodo disponibile.</span><span class="sxs-lookup"><span data-stu-id="64c8f-123">This will schedule the kanban job in the first available period.</span></span>  
    * <span data-ttu-id="64c8f-124">Si noti che il processo kanban viene spostato alla fine dell'elenco perché è stato aggiunto al periodo a partire dalla data odierna.</span><span class="sxs-lookup"><span data-stu-id="64c8f-124">Notice that the kanban job is moved to the end of the list because it has been added to the period starting from today.</span></span>  
    * <span data-ttu-id="64c8f-125">Se il periodo a partire dalla data odierna è completamente prenotato, il processo verrà spostato nel primo periodo disponibile.</span><span class="sxs-lookup"><span data-stu-id="64c8f-125">If the period starting from today is fully booked, the job will be moved to the first available period.</span></span>  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a><span data-ttu-id="64c8f-126">Programmare due processi kanban per un giorno specifico</span><span class="sxs-lookup"><span data-stu-id="64c8f-126">Schedule two kanban jobs for a specific day</span></span>
1. <span data-ttu-id="64c8f-127">Nell'elenco selezionare la riga 1.</span><span class="sxs-lookup"><span data-stu-id="64c8f-127">In the list, select row 1.</span></span>
    * <span data-ttu-id="64c8f-128">Nel campo Stato del processo alla prima riga è associato lo stato Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="64c8f-128">You should see that the first row has the Not planned status in the Job status field.</span></span>  
2. <span data-ttu-id="64c8f-129">Nell'elenco selezionare la riga 2.</span><span class="sxs-lookup"><span data-stu-id="64c8f-129">In the list, select row 2.</span></span>
    * <span data-ttu-id="64c8f-130">Nel campo Stato del processo alla seconda riga è associato lo stato Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="64c8f-130">You should see that the second row has the Not planned status in the Job status field.</span></span> <span data-ttu-id="64c8f-131">Ora i primi due processi sono selezionati.</span><span class="sxs-lookup"><span data-stu-id="64c8f-131">Now you have the first two jobs selected.</span></span>  
3. <span data-ttu-id="64c8f-132">Fare clic su Data di inizio programmazione per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="64c8f-132">Click Schedule from date to open the drop dialog.</span></span>
4. <span data-ttu-id="64c8f-133">Selezionare o deselezionare la casella Ignora reazione alla carenza di capacità.</span><span class="sxs-lookup"><span data-stu-id="64c8f-133">Check or uncheck the Override capacity shortage reaction box.</span></span>
    * <span data-ttu-id="64c8f-134">Questa opzione consente di sostituire la reazione alla carenza di capacità predefinita.</span><span class="sxs-lookup"><span data-stu-id="64c8f-134">This option allows you to override the default capacity shortage reaction.</span></span>  
5. <span data-ttu-id="64c8f-135">Nel campo Reazione alla carenza di capacità selezionare Aggiungi al periodo richiesto.</span><span class="sxs-lookup"><span data-stu-id="64c8f-135">In the Capacity shortage reaction field, select 'Add to the requested period'.</span></span>
    * <span data-ttu-id="64c8f-136">Questa opzione assicura che il processo viene aggiunto al periodo di tempo richiesto se la cella di lavoro risultasse sovraccarica.</span><span class="sxs-lookup"><span data-stu-id="64c8f-136">This option will ensure that the job is added to the requested period, regardless if the work cell might be overloaded.</span></span>  
6. <span data-ttu-id="64c8f-137">Fare clic su Programma.</span><span class="sxs-lookup"><span data-stu-id="64c8f-137">Click Schedule.</span></span>
    * <span data-ttu-id="64c8f-138">Si noti che entrambi i processi vengono aggiunti al periodo desiderato.</span><span class="sxs-lookup"><span data-stu-id="64c8f-138">Notice that both jobs are added to the desired period.</span></span>  
    * <span data-ttu-id="64c8f-139">Nella sezione Capacità periodo, è possibile visualizzare il carico per ogni periodo.</span><span class="sxs-lookup"><span data-stu-id="64c8f-139">In the Period capacity section, you can see the load for each period.</span></span> <span data-ttu-id="64c8f-140">Il campo Consumo mostra il consumo previsto in questo periodo.</span><span class="sxs-lookup"><span data-stu-id="64c8f-140">The Consumption field shows the scheduled consumption in this period.</span></span> <span data-ttu-id="64c8f-141">Se il consumo programmato è superiore alla capacità disponibile di questo periodo, verrà selezionato il consumo di overload.</span><span class="sxs-lookup"><span data-stu-id="64c8f-141">If the scheduled consumption is higher than the available capacity in this period, the overloaded consumption will be selected.</span></span>  


