---
title: Creare un piano materiali per co-prodotti
description: Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14de9a1085ac1cae88ad93c35385dd43c60ed4d1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431168"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ec6fc-103">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="ec6fc-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ec6fc-104">Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="ec6fc-105">La società di dati dimostrativi utilizzata per creare questa procedura è USP2.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="ec6fc-106">Creare il fabbisogno per un co-prodotto</span><span class="sxs-lookup"><span data-stu-id="ec6fc-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="ec6fc-107">Fare clic su Dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="ec6fc-108">Fare clic su Elaborazione e richiesta di informazioni ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="ec6fc-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-109">Click New.</span></span>
4. <span data-ttu-id="ec6fc-110">Fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-110">Click Sales order.</span></span>
5. <span data-ttu-id="ec6fc-111">Digitare un valore nel campo Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="ec6fc-112">Esempio: US-001</span><span class="sxs-lookup"><span data-stu-id="ec6fc-112">Example: US-001</span></span>  
6. <span data-ttu-id="ec6fc-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-113">Click OK.</span></span>
7. <span data-ttu-id="ec6fc-114">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ec6fc-115">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="ec6fc-115">Example: P6003</span></span>  
8. <span data-ttu-id="ec6fc-116">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ec6fc-117">Esempio: 50000</span><span class="sxs-lookup"><span data-stu-id="ec6fc-117">Example: 50000</span></span>  
9. <span data-ttu-id="ec6fc-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ec6fc-119">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="ec6fc-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="ec6fc-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-120">Close the page.</span></span>
2. <span data-ttu-id="ec6fc-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-121">Close the page.</span></span>
3. <span data-ttu-id="ec6fc-122">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-122">Click Master planning.</span></span>
4. <span data-ttu-id="ec6fc-123">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ec6fc-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ec6fc-125">Esempio: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="ec6fc-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="ec6fc-126">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-126">Click Run.</span></span>
7. <span data-ttu-id="ec6fc-127">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="ec6fc-128">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-128">Click Filter.</span></span>
9. <span data-ttu-id="ec6fc-129">Nell'elenco selezionare la riga per Campo = Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="ec6fc-130">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="ec6fc-131">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="ec6fc-131">Example: P6003</span></span>  
11. <span data-ttu-id="ec6fc-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-132">Click OK.</span></span>
12. <span data-ttu-id="ec6fc-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-133">Click OK.</span></span>
13. <span data-ttu-id="ec6fc-134">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-134">Click Planned orders.</span></span>
14. <span data-ttu-id="ec6fc-135">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ec6fc-136">Ad esempio, filtrare il campo Numero articolo con un valore "P6000".</span><span class="sxs-lookup"><span data-stu-id="ec6fc-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="ec6fc-137">Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="ec6fc-138">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ec6fc-139">Selezionare una delle righe restituite dal filtro.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="ec6fc-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="ec6fc-141">Espandere o comprimere la sezione Pegging.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="ec6fc-142">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ec6fc-143">L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="ec6fc-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="ec6fc-145">Creare il fabbisogno per un co-prodotto</span><span class="sxs-lookup"><span data-stu-id="ec6fc-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="ec6fc-146">Fare clic su Dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="ec6fc-147">Fare clic su Elaborazione e richiesta di informazioni ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="ec6fc-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-148">Click New.</span></span>
4. <span data-ttu-id="ec6fc-149">Fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-149">Click Sales order.</span></span>
5. <span data-ttu-id="ec6fc-150">Digitare un valore nel campo Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="ec6fc-151">Esempio: US-001</span><span class="sxs-lookup"><span data-stu-id="ec6fc-151">Example: US-001</span></span>  
6. <span data-ttu-id="ec6fc-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-152">Click OK.</span></span>
7. <span data-ttu-id="ec6fc-153">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ec6fc-154">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="ec6fc-154">Example: P6003</span></span>  
8. <span data-ttu-id="ec6fc-155">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ec6fc-156">Esempio: 50000</span><span class="sxs-lookup"><span data-stu-id="ec6fc-156">Example: 50000</span></span>  
9. <span data-ttu-id="ec6fc-157">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="ec6fc-158">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="ec6fc-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="ec6fc-159">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ec6fc-160">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ec6fc-161">Esempio: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="ec6fc-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="ec6fc-162">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-162">Click Run.</span></span>
4. <span data-ttu-id="ec6fc-163">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="ec6fc-164">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-164">Click Filter.</span></span>
6. <span data-ttu-id="ec6fc-165">Nell'elenco selezionare la riga per Campo = Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="ec6fc-166">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="ec6fc-167">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="ec6fc-167">Example: P6003</span></span>  
8. <span data-ttu-id="ec6fc-168">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-168">Click OK.</span></span>
9. <span data-ttu-id="ec6fc-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-169">Click OK.</span></span>
10. <span data-ttu-id="ec6fc-170">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-170">Click Planned orders.</span></span>
11. <span data-ttu-id="ec6fc-171">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ec6fc-172">Ad esempio, filtrare il campo Numero articolo con un valore "P6000".</span><span class="sxs-lookup"><span data-stu-id="ec6fc-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="ec6fc-173">Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="ec6fc-174">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ec6fc-175">Selezionare una delle righe restituite dal filtro.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="ec6fc-176">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="ec6fc-177">Espandere o comprimere la sezione Pegging.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="ec6fc-178">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ec6fc-179">L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="ec6fc-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-180">Close the page.</span></span>
17. <span data-ttu-id="ec6fc-181">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-181">Click Master planning.</span></span>
18. <span data-ttu-id="ec6fc-182">Andare a Pianificazione generale > Impostazioni > Parametri di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="ec6fc-183">Selezionare No nel campo Disattiva tutti i processi di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="ec6fc-184">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ec6fc-184">Close the page.</span></span>

