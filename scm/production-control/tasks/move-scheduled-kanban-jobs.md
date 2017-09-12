--- 
title: Spostare processi kanban programmati
description: Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso.
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="c9e97-103">Spostare processi kanban programmati</span><span class="sxs-lookup"><span data-stu-id="c9e97-103">Move scheduled kanban jobs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9e97-104">Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso.</span><span class="sxs-lookup"><span data-stu-id="c9e97-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="c9e97-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c9e97-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c9e97-106">La procedura è destinata al supervisore dello shop floor o al responsabile di pianificazione della produzione che utilizza i processi kanban.</span><span class="sxs-lookup"><span data-stu-id="c9e97-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="c9e97-107">Selezionare processi kanban programmati</span><span class="sxs-lookup"><span data-stu-id="c9e97-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="c9e97-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span><span class="sxs-lookup"><span data-stu-id="c9e97-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="c9e97-109">!MtCMR!Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c9e97-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="c9e97-110">áçêìõý !</span><span class="sxs-lookup"><span data-stu-id="c9e97-110">áçêìõý !</span></span>
3. <span data-ttu-id="c9e97-111">Markér den valgte række på listen.</span><span class="sxs-lookup"><span data-stu-id="c9e97-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="c9e97-112">Selezionare la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="c9e97-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="c9e97-113">Klik på Select.</span><span class="sxs-lookup"><span data-stu-id="c9e97-113">Klik på Select.</span></span>
5. <span data-ttu-id="c9e97-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="c9e97-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="c9e97-115">Viene filtrato l'elenco dei processi per visualizzare solo i processi kanban programmati.</span><span class="sxs-lookup"><span data-stu-id="c9e97-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="c9e97-116">Spostare processi kanban in un periodo diverso</span><span class="sxs-lookup"><span data-stu-id="c9e97-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="c9e97-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="c9e97-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="c9e97-118">Selezionare un processo con stato del processo Pianificato, ad esempio un processo programmato il 20 dicembre 2012 nel campo Periodo pianificato,</span><span class="sxs-lookup"><span data-stu-id="c9e97-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="c9e97-119">quindi spostare il processo al periodo precedente.</span><span class="sxs-lookup"><span data-stu-id="c9e97-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="c9e97-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="c9e97-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="c9e97-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="c9e97-121">Klik på End.</span></span>
    * <span data-ttu-id="c9e97-122">In questo modo il processo verrà spostato alla fine dell'elenco di processi come l'ultimo processo nel periodo precedente.</span><span class="sxs-lookup"><span data-stu-id="c9e97-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="c9e97-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="c9e97-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="c9e97-124">Selezionare un processo con stato del processo Pianificato, ad esempio un processo programmato il 18 dicembre 2012 nel campo Periodo pianificato,</span><span class="sxs-lookup"><span data-stu-id="c9e97-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="c9e97-125">quindi spostare il processo al periodo successivo.</span><span class="sxs-lookup"><span data-stu-id="c9e97-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="c9e97-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="c9e97-126">Klik på Next period.</span></span>
6. <span data-ttu-id="c9e97-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="c9e97-127">Klik på Start.</span></span>
    * <span data-ttu-id="c9e97-128">In questo modo il processo verrà spostato all'inizio dell'elenco di processi come il primo processo nel periodo precedente.</span><span class="sxs-lookup"><span data-stu-id="c9e97-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="c9e97-129">Attività: spostare un processo all'interno di un periodo</span><span class="sxs-lookup"><span data-stu-id="c9e97-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="c9e97-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="c9e97-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="c9e97-131">Selezionare un processo con stato del processo Pianificato, ad esempio il secondo processo programmato il 19 dicembre 2012 nel campo Periodo pianificato,</span><span class="sxs-lookup"><span data-stu-id="c9e97-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="c9e97-132">quindi spostare il processo nel periodo pianificato.</span><span class="sxs-lookup"><span data-stu-id="c9e97-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="c9e97-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="c9e97-133">Klik på Forward.</span></span>
    * <span data-ttu-id="c9e97-134">Si noti che il processo viene spostato una riga verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c9e97-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="c9e97-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="c9e97-135">Klik på Backward.</span></span>
    * <span data-ttu-id="c9e97-136">Si noti che il processo viene spostato una riga verso l'alto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c9e97-136">Notice that the job is moved one line up on the list.</span></span>  


