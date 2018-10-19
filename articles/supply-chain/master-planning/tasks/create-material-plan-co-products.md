--- 
title: Creare un piano materiali per co-prodotti
description: Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 2958f1e5c2e8a0cfa9cc6312f688d3b11b8e013c
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="241dd-103">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="241dd-103">Create a material plan for co products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="241dd-104">Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.</span><span class="sxs-lookup"><span data-stu-id="241dd-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="241dd-105">La società di dati dimostrativi utilizzata per creare questa procedura è USP2.</span><span class="sxs-lookup"><span data-stu-id="241dd-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="241dd-106">Creare il fabbisogno per un co-prodotto</span><span class="sxs-lookup"><span data-stu-id="241dd-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="241dd-107">Fare clic su Dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="241dd-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="241dd-108">Fare clic su Elaborazione e richiesta di informazioni ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="241dd-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="241dd-109">Click New.</span></span>
4. <span data-ttu-id="241dd-110">Fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-110">Click Sales order.</span></span>
5. <span data-ttu-id="241dd-111">Digitare un valore nel campo Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="241dd-112">Esempio: US-001</span><span class="sxs-lookup"><span data-stu-id="241dd-112">Example: US-001</span></span>  
6. <span data-ttu-id="241dd-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="241dd-113">Click OK.</span></span>
7. <span data-ttu-id="241dd-114">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="241dd-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="241dd-115">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="241dd-115">Example: P6003</span></span>  
8. <span data-ttu-id="241dd-116">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="241dd-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="241dd-117">Esempio: 50000</span><span class="sxs-lookup"><span data-stu-id="241dd-117">Example: 50000</span></span>  
9. <span data-ttu-id="241dd-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="241dd-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="241dd-119">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="241dd-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="241dd-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="241dd-120">Close the page.</span></span>
2. <span data-ttu-id="241dd-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="241dd-121">Close the page.</span></span>
3. <span data-ttu-id="241dd-122">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="241dd-122">Click Master planning.</span></span>
4. <span data-ttu-id="241dd-123">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="241dd-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="241dd-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="241dd-125">Esempio: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="241dd-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="241dd-126">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="241dd-126">Click Run.</span></span>
7. <span data-ttu-id="241dd-127">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="241dd-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="241dd-128">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="241dd-128">Click Filter.</span></span>
9. <span data-ttu-id="241dd-129">Nell'elenco selezionare la riga per Campo = Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="241dd-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="241dd-130">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="241dd-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="241dd-131">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="241dd-131">Example: P6003</span></span>  
11. <span data-ttu-id="241dd-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="241dd-132">Click OK.</span></span>
12. <span data-ttu-id="241dd-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="241dd-133">Click OK.</span></span>
13. <span data-ttu-id="241dd-134">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="241dd-134">Click Planned orders.</span></span>
14. <span data-ttu-id="241dd-135">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="241dd-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="241dd-136">Ad esempio, filtrare il campo Numero articolo con un valore "P6000".</span><span class="sxs-lookup"><span data-stu-id="241dd-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="241dd-137">Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="241dd-138">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="241dd-139">Selezionare una delle righe restituite dal filtro.</span><span class="sxs-lookup"><span data-stu-id="241dd-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="241dd-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="241dd-141">Espandere o comprimere la sezione Pegging.</span><span class="sxs-lookup"><span data-stu-id="241dd-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="241dd-142">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="241dd-143">L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.</span><span class="sxs-lookup"><span data-stu-id="241dd-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="241dd-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="241dd-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="241dd-145">Creare il fabbisogno per un co-prodotto</span><span class="sxs-lookup"><span data-stu-id="241dd-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="241dd-146">Fare clic su Dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="241dd-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="241dd-147">Fare clic su Elaborazione e richiesta di informazioni ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="241dd-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="241dd-148">Click New.</span></span>
4. <span data-ttu-id="241dd-149">Fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-149">Click Sales order.</span></span>
5. <span data-ttu-id="241dd-150">Digitare un valore nel campo Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="241dd-151">Esempio: US-001</span><span class="sxs-lookup"><span data-stu-id="241dd-151">Example: US-001</span></span>  
6. <span data-ttu-id="241dd-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="241dd-152">Click OK.</span></span>
7. <span data-ttu-id="241dd-153">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="241dd-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="241dd-154">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="241dd-154">Example: P6003</span></span>  
8. <span data-ttu-id="241dd-155">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="241dd-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="241dd-156">Esempio: 50000</span><span class="sxs-lookup"><span data-stu-id="241dd-156">Example: 50000</span></span>  
9. <span data-ttu-id="241dd-157">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="241dd-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="241dd-158">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="241dd-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="241dd-159">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="241dd-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="241dd-160">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="241dd-161">Esempio: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="241dd-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="241dd-162">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="241dd-162">Click Run.</span></span>
4. <span data-ttu-id="241dd-163">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="241dd-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="241dd-164">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="241dd-164">Click Filter.</span></span>
6. <span data-ttu-id="241dd-165">Nell'elenco selezionare la riga per Campo = Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="241dd-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="241dd-166">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="241dd-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="241dd-167">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="241dd-167">Example: P6003</span></span>  
8. <span data-ttu-id="241dd-168">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="241dd-168">Click OK.</span></span>
9. <span data-ttu-id="241dd-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="241dd-169">Click OK.</span></span>
10. <span data-ttu-id="241dd-170">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="241dd-170">Click Planned orders.</span></span>
11. <span data-ttu-id="241dd-171">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="241dd-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="241dd-172">Ad esempio, filtrare il campo Numero articolo con un valore "P6000".</span><span class="sxs-lookup"><span data-stu-id="241dd-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="241dd-173">Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="241dd-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="241dd-174">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="241dd-175">Selezionare una delle righe restituite dal filtro.</span><span class="sxs-lookup"><span data-stu-id="241dd-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="241dd-176">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="241dd-177">Espandere o comprimere la sezione Pegging.</span><span class="sxs-lookup"><span data-stu-id="241dd-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="241dd-178">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="241dd-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="241dd-179">L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.</span><span class="sxs-lookup"><span data-stu-id="241dd-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="241dd-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="241dd-180">Close the page.</span></span>
17. <span data-ttu-id="241dd-181">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="241dd-181">Click Master planning.</span></span>
18. <span data-ttu-id="241dd-182">Andare a Pianificazione generale > Impostazioni > Parametri di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="241dd-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="241dd-183">Selezionare No nel campo Disattiva tutti i processi di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="241dd-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="241dd-184">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="241dd-184">Close the page.</span></span>


