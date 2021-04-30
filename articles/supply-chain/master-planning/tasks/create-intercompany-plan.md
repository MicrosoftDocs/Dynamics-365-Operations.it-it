---
title: Creare un piano interaziendale
description: In questa procedura viene illustrato come creare un piano interaziendale.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8cf4ed879b6b2202d0b0f1f45052f5e21452967
ms.sourcegitcommit: 9b07d536b4bd8addfbdba42d2429c9fedb664635
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867352"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="ec1df-103">Creare un piano interaziendale</span><span class="sxs-lookup"><span data-stu-id="ec1df-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ec1df-104">In questa procedura viene illustrato come creare un piano interaziendale.</span><span class="sxs-lookup"><span data-stu-id="ec1df-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="ec1df-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="ec1df-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="ec1df-106">Impostare un gruppo di pianificazione interaziendale</span><span class="sxs-lookup"><span data-stu-id="ec1df-106">Set up an intercompany planning group</span></span>

1. <span data-ttu-id="ec1df-107">Nel **pannello di navigazione**,andare a **Moduli > Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="ec1df-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span>
2. <span data-ttu-id="ec1df-108">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="ec1df-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ec1df-109">Ad esempio, applicare un filtro nel campo Nome con un valore "10".</span><span class="sxs-lookup"><span data-stu-id="ec1df-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="ec1df-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec1df-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ec1df-111">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ec1df-111">Select **Delete**.</span></span> <span data-ttu-id="ec1df-112">Questo passaggio è necessario per abbreviare per l'esecuzione di pianificazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="ec1df-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="ec1df-113">La pianificazione interaziendale eseguirà la pianificazione generale in tutte le società in un gruppo di pianificazione, a partire dalla sequenza di programmazione inferiore.</span><span class="sxs-lookup"><span data-stu-id="ec1df-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="ec1df-114">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ec1df-114">Select **Yes**.</span></span>
6. <span data-ttu-id="ec1df-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ec1df-115">Close the page.</span></span>

## <a name="create-an-intercompany-master-plan"></a><span data-ttu-id="ec1df-116">Creare un piano generale interaziendale</span><span class="sxs-lookup"><span data-stu-id="ec1df-116">Create an intercompany master plan</span></span>

1. <span data-ttu-id="ec1df-117">Nel **pannello di navigazione**, andare a **Moduli > Pianificazione generale > Aree di lavoro > Pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="ec1df-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="ec1df-118">Selezionare **Pianificazione generale interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="ec1df-118">Select **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="ec1df-119">Nel campo **Gruppo di pianificazione interaziendale** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec1df-119">In the **Intercompany planning group** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ec1df-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec1df-120">In the list, select the link in the selected row.</span></span> <span data-ttu-id="ec1df-121">Selezionare il gruppo di pianificazione interaziendale 10.</span><span class="sxs-lookup"><span data-stu-id="ec1df-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="ec1df-122">Nel campo **Numero di iterazioni di pianificazione interaziendale**, immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="ec1df-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="ec1df-123">Il gruppo di pianificazione interaziendale 10 ha due membri.</span><span class="sxs-lookup"><span data-stu-id="ec1df-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="ec1df-124">Per propagare i ritardi dalla società di origine (USMF) alla società cliente (DEMF), sarà necessario eseguire la pianificazione interaziendale in entrambe le società due volte.</span><span class="sxs-lookup"><span data-stu-id="ec1df-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="ec1df-125">La prima iterazione propagherà la domanda e identificherà i ritardi nella società di origine (USMF).</span><span class="sxs-lookup"><span data-stu-id="ec1df-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="ec1df-126">La seconda iterazione propagherà i ritardi da USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="ec1df-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="ec1df-127">Nel campo **Prima iterazione** selezionare "Rigenerazione".</span><span class="sxs-lookup"><span data-stu-id="ec1df-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="ec1df-128">Nel campo **Iterazioni successive** selezionare "Rigenerazione".</span><span class="sxs-lookup"><span data-stu-id="ec1df-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="ec1df-129">Nel campo **Numero di thread** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ec1df-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="ec1df-130">Questo rappresenta il numero di thread paralleli utilizzati per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ec1df-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="ec1df-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec1df-131">Select **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="ec1df-132">Visualizzare il risultato del piano</span><span class="sxs-lookup"><span data-stu-id="ec1df-132">View the result of the plan</span></span>

1. <span data-ttu-id="ec1df-133">Nel campo **Piano** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec1df-133">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ec1df-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec1df-134">In the list, select the link in the selected row.</span></span> <span data-ttu-id="ec1df-135">Selezionare il collegamento per StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="ec1df-135">Select the link for StaticPlan.</span></span> <span data-ttu-id="ec1df-136">È necessario essere  nella società USMF.</span><span class="sxs-lookup"><span data-stu-id="ec1df-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="ec1df-137">Selezionare **Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="ec1df-137">Select **Planned orders**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]