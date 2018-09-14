--- 
title: Creare un piano interaziendale
description: In questa procedura viene illustrato come creare un piano interaziendale.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d378a89bbb4de6d67db0019dc72a27945d50c4e9
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="6fe6e-103">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="6fe6e-103">Create an intercompany plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6fe6e-104">In questa procedura viene illustrato come creare un piano interaziendale.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="6fe6e-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="6fe6e-106">Impostare un gruppo di pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="6fe6e-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="6fe6e-107">Andare a Gruppi di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="6fe6e-108">Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="6fe6e-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="6fe6e-109">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="6fe6e-110">Ad esempio, applicare un filtro nel campo Nome con un valore "10".</span><span class="sxs-lookup"><span data-stu-id="6fe6e-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="6fe6e-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6fe6e-112">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-112">Click Delete.</span></span>
    * <span data-ttu-id="6fe6e-113">Questo passaggio è necessario per abbreviare per l'esecuzione di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="6fe6e-114">La pianificazione interaziendale eseguirà la pianificazione generale in tutte le società in un gruppo di pianificazione, a partire dalla sequenza di programmazione inferiore.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="6fe6e-115">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-115">Click Yes.</span></span>
6. <span data-ttu-id="6fe6e-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="6fe6e-117">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="6fe6e-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="6fe6e-118">Fare clic su Pianificazione generale interaziendale.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="6fe6e-119">Ciò avviene nell'area di lavoro Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="6fe6e-120">Nel campo Gruppo di pianificazione interaziendale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="6fe6e-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6fe6e-122">Selezionare il gruppo di pianificazione interaziendale 10.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="6fe6e-123">Nel campo Numero di iterazioni di pianificazione interaziendale, immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="6fe6e-124">Il gruppo di pianificazione interaziendale 10 ha due membri.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="6fe6e-125">Per propagare i ritardi dalla società di origine (USMF) alla società cliente (DEMF), sarà necessario eseguire la pianificazione interaziendale in entrambe le società due volte.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="6fe6e-126">La prima iterazione propagherà la domanda e identificherà i ritardi nella società di origine (USMF).</span><span class="sxs-lookup"><span data-stu-id="6fe6e-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="6fe6e-127">La seconda iterazione propagherà i ritardi da USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="6fe6e-128">Nel campo Prima iterazione selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="6fe6e-129">Nel campo Prima iterazione selezionare 'Rigenerazione'.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="6fe6e-130">Nel campo Iterazioni successive selezionare 'Rigenerazione'.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="6fe6e-131">Nel campo Numero di thread immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="6fe6e-132">Questo rappresenta il numero di thread paralleli utilizzati per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="6fe6e-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="6fe6e-134">Visualizzare il risultato del piano</span><span class="sxs-lookup"><span data-stu-id="6fe6e-134">View the result of the plan</span></span>
1. <span data-ttu-id="6fe6e-135">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="6fe6e-136">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6fe6e-137">Fare clic sul collegamento per StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="6fe6e-138">È necessario essere  nella società USMF.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="6fe6e-139">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="6fe6e-139">Click Planned orders.</span></span>


