---
title: Creare un piano interaziendale
description: In questa procedura viene illustrato come creare un piano interaziendale.
author: ShylaThompson
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ae3d8a7c437ffd41a4864bd8548aa84c8ab8f32
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978275"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="ba8af-103">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="ba8af-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba8af-104">In questa procedura viene illustrato come creare un piano interaziendale.</span><span class="sxs-lookup"><span data-stu-id="ba8af-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="ba8af-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="ba8af-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="ba8af-106">Impostare un gruppo di pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="ba8af-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="ba8af-107">Nel **pannello di navigazione**,andare a **Moduli > Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="ba8af-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span> 
2. <span data-ttu-id="ba8af-108">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="ba8af-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ba8af-109">Ad esempio, applicare un filtro nel campo Nome con un valore "10".</span><span class="sxs-lookup"><span data-stu-id="ba8af-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="ba8af-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ba8af-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ba8af-111">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ba8af-111">Click **Delete**.</span></span> <span data-ttu-id="ba8af-112">Questo passaggio è necessario per abbreviare per l'esecuzione di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="ba8af-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="ba8af-113">La pianificazione interaziendale eseguirà la pianificazione generale in tutte le società in un gruppo di pianificazione, a partire dalla sequenza di programmazione inferiore.</span><span class="sxs-lookup"><span data-stu-id="ba8af-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="ba8af-114">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ba8af-114">Click **Yes**.</span></span>
6. <span data-ttu-id="ba8af-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ba8af-115">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="ba8af-116">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="ba8af-116">Create an intercompany plan</span></span>
1. <span data-ttu-id="ba8af-117">Nel **pannello di navigazione**,andare a **Moduli > Pianificazione generale > Aree di lavoro > Pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="ba8af-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="ba8af-118">Fare clic su **Pianificazione generale interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="ba8af-118">Click **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="ba8af-119">Nel campo **Gruppo di pianificazione interaziendale** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ba8af-119">In the **Intercompany planning group** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ba8af-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ba8af-120">In the list, click the link in the selected row.</span></span> <span data-ttu-id="ba8af-121">Selezionare il gruppo di pianificazione interaziendale 10.</span><span class="sxs-lookup"><span data-stu-id="ba8af-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="ba8af-122">Nel campo **Numero di iterazioni di pianificazione interaziendale**, immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="ba8af-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="ba8af-123">Il gruppo di pianificazione interaziendale 10 ha due membri.</span><span class="sxs-lookup"><span data-stu-id="ba8af-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="ba8af-124">Per propagare i ritardi dalla società di origine (USMF) alla società cliente (DEMF), sarà necessario eseguire la pianificazione interaziendale in entrambe le società due volte.</span><span class="sxs-lookup"><span data-stu-id="ba8af-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="ba8af-125">La prima iterazione propagherà la domanda e identificherà i ritardi nella società di origine (USMF).</span><span class="sxs-lookup"><span data-stu-id="ba8af-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="ba8af-126">La seconda iterazione propagherà i ritardi da USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="ba8af-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="ba8af-127">Nel campo **Prima iterazione** selezionare "Rigenerazione".</span><span class="sxs-lookup"><span data-stu-id="ba8af-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="ba8af-128">Nel campo **Iterazioni successive** selezionare "Rigenerazione".</span><span class="sxs-lookup"><span data-stu-id="ba8af-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="ba8af-129">Nel campo **Numero di thread** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ba8af-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="ba8af-130">Questo rappresenta il numero di thread paralleli utilizzati per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ba8af-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="ba8af-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba8af-131">Click **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="ba8af-132">Visualizzare il risultato del piano</span><span class="sxs-lookup"><span data-stu-id="ba8af-132">View the result of the plan</span></span>
1. <span data-ttu-id="ba8af-133">Nel campo **Piano** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ba8af-133">In the **Plan** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ba8af-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ba8af-134">In the list, click the link in the selected row.</span></span> <span data-ttu-id="ba8af-135">Fare clic sul collegamento per StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="ba8af-135">Click the link for StaticPlan.</span></span> <span data-ttu-id="ba8af-136">È necessario essere  nella società USMF.</span><span class="sxs-lookup"><span data-stu-id="ba8af-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="ba8af-137">Fare clic su **Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="ba8af-137">Click **Planned orders**.</span></span>

