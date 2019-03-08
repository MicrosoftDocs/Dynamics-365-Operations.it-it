---
title: Programmare un ordine di produzione con programmazione di operazioni e processi
description: Questa procedura si concentra sulla programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00698e9cd2ed0481e5fed301c8a8c2e98690a5db
ms.sourcegitcommit: 2ebea3cbddfa0a5ef0e0fd13d3693da6152bc288
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "352461"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="8b590-103">Programmare un ordine di produzione con programmazione di operazioni e processi</span><span class="sxs-lookup"><span data-stu-id="8b590-103">Schedule a production order with operations and job scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b590-104">Questa procedura si concentra sulla programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="8b590-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="8b590-105">Nessun processo viene creato con la programmazione delle operazioni, mentre i processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="8b590-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="8b590-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="8b590-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="8b590-107">Questa procedura è destinata al responsabile di produzione, al responsabile della pianificazione della produzione o al supervisore di reparto in un ambiente di produzione discreta.</span><span class="sxs-lookup"><span data-stu-id="8b590-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="8b590-108">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8b590-108">Create a production order</span></span>
1. <span data-ttu-id="8b590-109">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="8b590-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="8b590-110">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8b590-110">Click New production order.</span></span>
3. <span data-ttu-id="8b590-111">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b590-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="8b590-112">Selezionare il numero articolo D0001.</span><span class="sxs-lookup"><span data-stu-id="8b590-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="8b590-113">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="8b590-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="8b590-114">Programmare operazioni per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8b590-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="8b590-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b590-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8b590-116">Selezionare l'ordine di produzione appena creato.</span><span class="sxs-lookup"><span data-stu-id="8b590-116">Select the production order that you have just created.</span></span> <span data-ttu-id="8b590-117">Dovrebbe essere nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8b590-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="8b590-118">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="8b590-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="8b590-119">Fare clic su Programma operazioni.</span><span class="sxs-lookup"><span data-stu-id="8b590-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="8b590-120">Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.</span><span class="sxs-lookup"><span data-stu-id="8b590-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="8b590-121">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8b590-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="8b590-122">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="8b590-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="8b590-123">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="8b590-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="8b590-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b590-124">Click OK.</span></span>
7. <span data-ttu-id="8b590-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b590-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8b590-126">Notare che lo stato viene modificato in Programmato.</span><span class="sxs-lookup"><span data-stu-id="8b590-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="8b590-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b590-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8b590-128">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="8b590-128">Click All jobs.</span></span>
    * <span data-ttu-id="8b590-129">Si noti che nessun processo viene creato con la programmazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="8b590-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="8b590-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b590-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="8b590-131">Programmare processi per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8b590-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="8b590-132">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="8b590-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="8b590-133">Fare clic su Programma processi.</span><span class="sxs-lookup"><span data-stu-id="8b590-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="8b590-134">Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.</span><span class="sxs-lookup"><span data-stu-id="8b590-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="8b590-135">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8b590-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="8b590-136">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="8b590-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="8b590-137">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="8b590-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="8b590-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8b590-138">Click OK.</span></span>
6. <span data-ttu-id="8b590-139">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8b590-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="8b590-140">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="8b590-140">Click All jobs.</span></span>
    * <span data-ttu-id="8b590-141">Si noti che in base al ciclo di lavorazione attivo, 5 processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="8b590-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

