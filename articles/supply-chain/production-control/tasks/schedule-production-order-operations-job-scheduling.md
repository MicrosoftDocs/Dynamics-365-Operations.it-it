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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4932cfa472c34a16249b226aa4a07b8e5f528053
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838489"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="609f0-103">Programmare un ordine di produzione con programmazione di operazioni e processi</span><span class="sxs-lookup"><span data-stu-id="609f0-103">Schedule a production order with operations and job scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="609f0-104">Questa procedura si concentra sulla programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="609f0-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="609f0-105">Nessun processo viene creato con la programmazione delle operazioni, mentre i processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="609f0-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="609f0-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="609f0-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="609f0-107">Questa procedura è destinata al responsabile di produzione, al responsabile della pianificazione della produzione o al supervisore di reparto in un ambiente di produzione discreta.</span><span class="sxs-lookup"><span data-stu-id="609f0-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="609f0-108">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="609f0-108">Create a production order</span></span>
1. <span data-ttu-id="609f0-109">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="609f0-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="609f0-110">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="609f0-110">Click New production order.</span></span>
3. <span data-ttu-id="609f0-111">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="609f0-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="609f0-112">Selezionare il numero articolo D0001.</span><span class="sxs-lookup"><span data-stu-id="609f0-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="609f0-113">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="609f0-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="609f0-114">Programmare operazioni per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="609f0-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="609f0-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="609f0-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="609f0-116">Selezionare l'ordine di produzione appena creato.</span><span class="sxs-lookup"><span data-stu-id="609f0-116">Select the production order that you have just created.</span></span> <span data-ttu-id="609f0-117">Dovrebbe essere nella parte superiore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="609f0-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="609f0-118">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="609f0-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="609f0-119">Fare clic su Programma operazioni.</span><span class="sxs-lookup"><span data-stu-id="609f0-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="609f0-120">Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.</span><span class="sxs-lookup"><span data-stu-id="609f0-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="609f0-121">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="609f0-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="609f0-122">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="609f0-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="609f0-123">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="609f0-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="609f0-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="609f0-124">Click OK.</span></span>
7. <span data-ttu-id="609f0-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="609f0-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="609f0-126">Notare che lo stato viene modificato in Programmato.</span><span class="sxs-lookup"><span data-stu-id="609f0-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="609f0-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="609f0-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="609f0-128">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="609f0-128">Click All jobs.</span></span>
    * <span data-ttu-id="609f0-129">Si noti che nessun processo viene creato con la programmazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="609f0-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="609f0-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="609f0-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="609f0-131">Programmare processi per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="609f0-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="609f0-132">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="609f0-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="609f0-133">Fare clic su Programma processi.</span><span class="sxs-lookup"><span data-stu-id="609f0-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="609f0-134">Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.</span><span class="sxs-lookup"><span data-stu-id="609f0-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="609f0-135">Immettere una data nel campo Data di programmazione.</span><span class="sxs-lookup"><span data-stu-id="609f0-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="609f0-136">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="609f0-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="609f0-137">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="609f0-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="609f0-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="609f0-138">Click OK.</span></span>
6. <span data-ttu-id="609f0-139">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="609f0-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="609f0-140">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="609f0-140">Click All jobs.</span></span>
    * <span data-ttu-id="609f0-141">Si noti che in base al ciclo di lavorazione attivo, 5 processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="609f0-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

