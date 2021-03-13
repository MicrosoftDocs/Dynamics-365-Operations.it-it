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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c368e461860a41d0110f5aed79c2aac49c437d68
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011412"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="ffe3c-103">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="ffe3c-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ffe3c-104">In questa procedura viene illustrato come creare un piano interaziendale.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="ffe3c-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="ffe3c-106">Impostare un gruppo di pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="ffe3c-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="ffe3c-107">Nel **pannello di navigazione**,andare a **Moduli > Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span> 
2. <span data-ttu-id="ffe3c-108">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ffe3c-109">Ad esempio, applicare un filtro nel campo Nome con un valore "10".</span><span class="sxs-lookup"><span data-stu-id="ffe3c-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="ffe3c-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ffe3c-111">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-111">Click **Delete**.</span></span> <span data-ttu-id="ffe3c-112">Questo passaggio è necessario per abbreviare per l'esecuzione di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="ffe3c-113">La pianificazione interaziendale eseguirà la pianificazione generale in tutte le società in un gruppo di pianificazione, a partire dalla sequenza di programmazione inferiore.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="ffe3c-114">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-114">Click **Yes**.</span></span>
6. <span data-ttu-id="ffe3c-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-115">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="ffe3c-116">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="ffe3c-116">Create an intercompany plan</span></span>
1. <span data-ttu-id="ffe3c-117">Nel **pannello di navigazione**,andare a **Moduli > Pianificazione generale > Aree di lavoro > Pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="ffe3c-118">Fare clic su **Pianificazione generale interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-118">Click **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="ffe3c-119">Nel campo **Gruppo di pianificazione interaziendale** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-119">In the **Intercompany planning group** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ffe3c-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-120">In the list, click the link in the selected row.</span></span> <span data-ttu-id="ffe3c-121">Selezionare il gruppo di pianificazione interaziendale 10.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="ffe3c-122">Nel campo **Numero di iterazioni di pianificazione interaziendale**, immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="ffe3c-123">Il gruppo di pianificazione interaziendale 10 ha due membri.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="ffe3c-124">Per propagare i ritardi dalla società di origine (USMF) alla società cliente (DEMF), sarà necessario eseguire la pianificazione interaziendale in entrambe le società due volte.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="ffe3c-125">La prima iterazione propagherà la domanda e identificherà i ritardi nella società di origine (USMF).</span><span class="sxs-lookup"><span data-stu-id="ffe3c-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="ffe3c-126">La seconda iterazione propagherà i ritardi da USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="ffe3c-127">Nel campo **Prima iterazione** selezionare "Rigenerazione".</span><span class="sxs-lookup"><span data-stu-id="ffe3c-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="ffe3c-128">Nel campo **Iterazioni successive** selezionare "Rigenerazione".</span><span class="sxs-lookup"><span data-stu-id="ffe3c-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="ffe3c-129">Nel campo **Numero di thread** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="ffe3c-130">Questo rappresenta il numero di thread paralleli utilizzati per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="ffe3c-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-131">Click **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="ffe3c-132">Visualizzare il risultato del piano</span><span class="sxs-lookup"><span data-stu-id="ffe3c-132">View the result of the plan</span></span>
1. <span data-ttu-id="ffe3c-133">Nel campo **Piano** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-133">In the **Plan** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ffe3c-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-134">In the list, click the link in the selected row.</span></span> <span data-ttu-id="ffe3c-135">Fare clic sul collegamento per StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-135">Click the link for StaticPlan.</span></span> <span data-ttu-id="ffe3c-136">È necessario essere  nella società USMF.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="ffe3c-137">Fare clic su **Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="ffe3c-137">Click **Planned orders**.</span></span>

