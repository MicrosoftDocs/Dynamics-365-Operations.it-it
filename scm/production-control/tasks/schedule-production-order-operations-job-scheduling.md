--- 
title: Programmare un ordine di produzione con programmazione di operazioni e processi
description: Questa procedura si concentra sulla programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
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
ms.openlocfilehash: d4aac437876862e9f776264fc81f246c820bdf45
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="0d79b-103">Programmare un ordine di produzione con programmazione di operazioni e processi</span><span class="sxs-lookup"><span data-stu-id="0d79b-103">Schedule a production order with operations and job scheduling</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d79b-104">Questa procedura si concentra sulla programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="0d79b-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="0d79b-105">Nessun processo viene creato con la programmazione delle operazioni, mentre i processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="0d79b-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="0d79b-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="0d79b-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="0d79b-107">Questa procedura è destinata al responsabile di produzione, al responsabile della pianificazione della produzione o al supervisore di reparto in un ambiente di produzione discreta.</span><span class="sxs-lookup"><span data-stu-id="0d79b-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="0d79b-108">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="0d79b-108">Create a production order</span></span>
1. <span data-ttu-id="0d79b-109">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="0d79b-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="0d79b-110">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="0d79b-110">Click New production order.</span></span>
3. <span data-ttu-id="0d79b-111">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0d79b-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="0d79b-112">Selezionare il numero articolo D0001.</span><span class="sxs-lookup"><span data-stu-id="0d79b-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="0d79b-113">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="0d79b-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="0d79b-114">Programmare operazioni per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="0d79b-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="0d79b-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d79b-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0d79b-116">Selezionare l'ordine di produzione appena creato.</span><span class="sxs-lookup"><span data-stu-id="0d79b-116">Select the production order that you have just created.</span></span> <span data-ttu-id="0d79b-117">Dovrebbe essere nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0d79b-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="0d79b-118">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="0d79b-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="0d79b-119">Fare clic su Programma operazioni.</span><span class="sxs-lookup"><span data-stu-id="0d79b-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="0d79b-120">Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.</span><span class="sxs-lookup"><span data-stu-id="0d79b-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="0d79b-121">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0d79b-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="0d79b-122">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="0d79b-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="0d79b-123">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="0d79b-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="0d79b-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0d79b-124">Click OK.</span></span>
7. <span data-ttu-id="0d79b-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d79b-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0d79b-126">Notare che lo stato viene modificato in Programmato.</span><span class="sxs-lookup"><span data-stu-id="0d79b-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="0d79b-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d79b-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="0d79b-128">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="0d79b-128">Click All jobs.</span></span>
    * <span data-ttu-id="0d79b-129">Si noti che nessun processo viene creato con la programmazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0d79b-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="0d79b-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0d79b-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="0d79b-131">Programmare processi per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="0d79b-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="0d79b-132">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="0d79b-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="0d79b-133">Fare clic su Programma processi.</span><span class="sxs-lookup"><span data-stu-id="0d79b-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="0d79b-134">Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.</span><span class="sxs-lookup"><span data-stu-id="0d79b-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="0d79b-135">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0d79b-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="0d79b-136">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="0d79b-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="0d79b-137">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="0d79b-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="0d79b-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0d79b-138">Click OK.</span></span>
6. <span data-ttu-id="0d79b-139">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="0d79b-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="0d79b-140">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="0d79b-140">Click All jobs.</span></span>
    * <span data-ttu-id="0d79b-141">Si noti che in base al ciclo di lavorazione attivo, 5 processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="0d79b-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

