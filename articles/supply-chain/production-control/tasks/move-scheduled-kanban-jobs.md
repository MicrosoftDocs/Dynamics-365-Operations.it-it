---
title: Spostare processi kanban programmati
description: Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso.
author: ChristianRytt
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d58ee740824809f15da68db66616bb01d5dbfab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825016"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="23593-103">Spostare processi kanban programmati</span><span class="sxs-lookup"><span data-stu-id="23593-103">Move scheduled kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="23593-104">Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso.</span><span class="sxs-lookup"><span data-stu-id="23593-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="23593-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="23593-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="23593-106">La procedura è destinata al supervisore dello shop floor o al responsabile di pianificazione della produzione che utilizza i processi kanban.</span><span class="sxs-lookup"><span data-stu-id="23593-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="23593-107">Selezionare processi kanban programmati.</span><span class="sxs-lookup"><span data-stu-id="23593-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="23593-108">Andare a **Controllo produzione > Kanban > Programmazione processo kanban**.</span><span class="sxs-lookup"><span data-stu-id="23593-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="23593-109">Nel campo **Cella di lavoro**, fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="23593-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="23593-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="23593-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="23593-111">Selezionare la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="23593-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="23593-112">Fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="23593-112">Click **Select**.</span></span> 

5. <span data-ttu-id="23593-113">Nel campo **Visualizza stato processo** selezionare **Programmato**.</span><span class="sxs-lookup"><span data-stu-id="23593-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="23593-114">Viene filtrato l'elenco dei processi per visualizzare solo i processi kanban programmati.</span><span class="sxs-lookup"><span data-stu-id="23593-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="23593-115">Spostare processi kanban in un periodo diverso.</span><span class="sxs-lookup"><span data-stu-id="23593-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="23593-116">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="23593-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="23593-117">Selezionare un processo con stato **processo Pianificato**, ad esempio un processo programmato il 20 dicembre 2012 nel campo **Periodo pianificato**,</span><span class="sxs-lookup"><span data-stu-id="23593-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="23593-118">quindi spostare il processo al periodo precedente.</span><span class="sxs-lookup"><span data-stu-id="23593-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="23593-119">Fare clic su **Periodo precedente**.</span><span class="sxs-lookup"><span data-stu-id="23593-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="23593-120">Fare clic su **Fine** per spostare il processo alla fine dell'elenco di processi come l'ultimo processo nel periodo precedente.</span><span class="sxs-lookup"><span data-stu-id="23593-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="23593-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="23593-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="23593-122">Selezionare un processo con stato **processo Pianificato**, ad esempio un processo programmato il 18 dicembre 2012 nel campo **Periodo pianificato**,</span><span class="sxs-lookup"><span data-stu-id="23593-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="23593-123">quindi spostare il processo al periodo successivo.</span><span class="sxs-lookup"><span data-stu-id="23593-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="23593-124">Fare clic su **Periodo successivo**.</span><span class="sxs-lookup"><span data-stu-id="23593-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="23593-125">Fare clic su **Inizio** per spostare il processo all'inizio dell'elenco di processi come primo processo nel periodo precedente.</span><span class="sxs-lookup"><span data-stu-id="23593-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="23593-126">Spostare un processo all'interno di un periodo.</span><span class="sxs-lookup"><span data-stu-id="23593-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="23593-127">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="23593-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="23593-128">Selezionare un processo con stato Processo pianificato, ad esempio il secondo processo programmato il 19 dicembre 2012 nel campo **Periodo pianificato**,</span><span class="sxs-lookup"><span data-stu-id="23593-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="23593-129">quindi spostare il processo nel periodo pianificato.</span><span class="sxs-lookup"><span data-stu-id="23593-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="23593-130">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="23593-130">Click **Forward**.</span></span> <span data-ttu-id="23593-131">Si noti che il processo viene spostato una riga verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="23593-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="23593-132">Fare clic su **Indietro**.</span><span class="sxs-lookup"><span data-stu-id="23593-132">Click **Backward**.</span></span> <span data-ttu-id="23593-133">Si noti che il processo viene spostato una riga verso l'alto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="23593-133">Notice that the job is moved one line up on the list.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]