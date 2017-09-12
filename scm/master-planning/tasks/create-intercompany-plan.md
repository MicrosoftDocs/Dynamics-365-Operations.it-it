--- 
title: Creare un piano interaziendale
description: In questa procedura viene illustrato come creare un piano interaziendale.
author: YuyuScheller
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
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: da186f7ad74bb607fd6e7220d77c2f414789f29c
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="894a1-103">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="894a1-103">Create an intercompany plan</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="894a1-104">In questa procedura viene illustrato come creare un piano interaziendale.</span><span class="sxs-lookup"><span data-stu-id="894a1-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="894a1-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="894a1-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="894a1-106">Impostare un gruppo di pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="894a1-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="894a1-107">Andare a Gruppi di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="894a1-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="894a1-108">Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="894a1-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="894a1-109">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="894a1-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="894a1-110">Ad esempio, applicare un filtro nel campo Nome con un valore "10".</span><span class="sxs-lookup"><span data-stu-id="894a1-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="894a1-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="894a1-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="894a1-112">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="894a1-112">Click Delete.</span></span>
    * <span data-ttu-id="894a1-113">Questo passaggio è necessario per abbreviare per l'esecuzione di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="894a1-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="894a1-114">La pianificazione interaziendale eseguirà la pianificazione generale in tutte le società in un gruppo di pianificazione, a partire dalla sequenza di programmazione inferiore.</span><span class="sxs-lookup"><span data-stu-id="894a1-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="894a1-115">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="894a1-115">Click Yes.</span></span>
6. <span data-ttu-id="894a1-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="894a1-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="894a1-117">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="894a1-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="894a1-118">Fare clic su Pianificazione generale interaziendale.</span><span class="sxs-lookup"><span data-stu-id="894a1-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="894a1-119">Ciò avviene nell'area di lavoro Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="894a1-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="894a1-120">Nel campo Gruppo di pianificazione interaziendale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="894a1-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="894a1-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="894a1-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="894a1-122">Selezionare il gruppo di pianificazione interaziendale 10.</span><span class="sxs-lookup"><span data-stu-id="894a1-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="894a1-123">Nel campo Numero di iterazioni di pianificazione interaziendale, immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="894a1-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="894a1-124">Il gruppo di pianificazione interaziendale 10 ha due membri.</span><span class="sxs-lookup"><span data-stu-id="894a1-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="894a1-125">Per propagare i ritardi dalla società di origine (USMF) alla società cliente (DEMF), sarà necessario eseguire la pianificazione interaziendale in entrambe le società due volte.</span><span class="sxs-lookup"><span data-stu-id="894a1-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="894a1-126">La prima iterazione propagherà la domanda e identificherà i ritardi nella società di origine (USMF).</span><span class="sxs-lookup"><span data-stu-id="894a1-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="894a1-127">La seconda iterazione propagherà i ritardi da USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="894a1-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="894a1-128">Nel campo Prima iterazione selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="894a1-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="894a1-129">Nel campo Prima iterazione selezionare 'Rigenerazione'.</span><span class="sxs-lookup"><span data-stu-id="894a1-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="894a1-130">Nel campo Iterazioni successive selezionare 'Rigenerazione'.</span><span class="sxs-lookup"><span data-stu-id="894a1-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="894a1-131">Nel campo Numero di thread immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="894a1-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="894a1-132">Questo rappresenta il numero di thread paralleli utilizzati per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="894a1-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="894a1-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="894a1-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="894a1-134">Visualizzare il risultato del piano</span><span class="sxs-lookup"><span data-stu-id="894a1-134">View the result of the plan</span></span>
1. <span data-ttu-id="894a1-135">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="894a1-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="894a1-136">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="894a1-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="894a1-137">Fare clic sul collegamento per StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="894a1-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="894a1-138">È necessario essere  nella società USMF.</span><span class="sxs-lookup"><span data-stu-id="894a1-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="894a1-139">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="894a1-139">Click Planned orders.</span></span>

