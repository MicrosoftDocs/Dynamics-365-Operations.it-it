---
title: Programmare un ordine di produzione con programmazione di operazioni e processi
description: In questo argomento viene descritta la programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.
author: ChristianRytt
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ace204f1ec79cc8f9ce10ebfdc3606879e40d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215843"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="bc5fe-103">Programmare un ordine di produzione con programmazione di operazioni e processi</span><span class="sxs-lookup"><span data-stu-id="bc5fe-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc5fe-104">In questo argomento viene descritta la programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="bc5fe-105">Nessun processo viene creato con la programmazione delle operazioni, mentre i processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="bc5fe-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="bc5fe-107">Questa procedura è destinata al responsabile di produzione, al responsabile della pianificazione della produzione o al supervisore di reparto in un ambiente di produzione discreta.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="bc5fe-108">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="bc5fe-108">Create a production order</span></span>
1. <span data-ttu-id="bc5fe-109">Nel pannello di navigazione, andare a **Moduli > Controllo produzione > Comune > Ordini di produzione > Tutti gli ordini di produzione**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="bc5fe-110">Selezionare **Nuovo ordine di produzione**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-110">Select **New production order**.</span></span>
3. <span data-ttu-id="bc5fe-111">Nel campo **Numero articolo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="bc5fe-112">Selezionare il numero articolo **D0001**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="bc5fe-113">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="bc5fe-114">Programmare operazioni per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="bc5fe-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="bc5fe-115">Selezionare la riga appena creata.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="bc5fe-116">Nel riquadro azioni selezionare **Programma**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="bc5fe-117">Selezionare **Programma operazioni**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="bc5fe-118">Nel campo **Direzione programmazione**, selezionare **Avanti da data programmazione**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="bc5fe-119">Immettere una data nel campo **Data di programmazione**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="bc5fe-120">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="bc5fe-121">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="bc5fe-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-122">Select **OK**.</span></span>
7. <span data-ttu-id="bc5fe-123">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-123">In the list, mark the selected row.</span></span> <span data-ttu-id="bc5fe-124">Notare che lo stato viene modificato in **Programmato**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="bc5fe-125">Selezionare **Tutti i processi**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-125">Select **All jobs**.</span></span> <span data-ttu-id="bc5fe-126">Si noti che nessun processo viene creato con la programmazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="bc5fe-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="bc5fe-128">Programmare processi per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="bc5fe-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="bc5fe-129">Nel riquadro azioni selezionare **Programma**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="bc5fe-130">Selezionare **Programma processi**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="bc5fe-131">Nel campo **Direzione programmazione**, selezionare **Avanti da data programmazione**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="bc5fe-132">Immettere una data nel campo **Data di programmazione**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="bc5fe-133">Selezionare una data futura, ad esempio, oggi più una settimana.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="bc5fe-134">Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="bc5fe-135">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-135">Select **OK**.</span></span>
6. <span data-ttu-id="bc5fe-136">Nel riquadro azioni, selezionare **Ordine di produzione**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="bc5fe-137">Selezionare **Tutti i processi**.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-137">Select **All jobs**.</span></span> <span data-ttu-id="bc5fe-138">Si noti che in base al ciclo di lavorazione attivo, 5 processi vengono creati con la programmazione dei processi.</span><span class="sxs-lookup"><span data-stu-id="bc5fe-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]