---
title: Creare un piano materiali per co-prodotti
description: Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920731"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="3b6f1-103">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="3b6f1-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3b6f1-104">Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="3b6f1-105">La società di dati dimostrativi utilizzata per creare questa procedura è USP2.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-105">The demo data company used to create this procedure is USP2.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="3b6f1-106">Creare il fabbisogno per un co-prodotto</span><span class="sxs-lookup"><span data-stu-id="3b6f1-106">Create requirement for a co-product</span></span>

1. <span data-ttu-id="3b6f1-107">Vai a **Vendite e marketing \> Aree di lavoro \> Elaborazione e richiesta di informazioni ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-107">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="3b6f1-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-108">Select **New**.</span></span>
1. <span data-ttu-id="3b6f1-109">Selezionare **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-109">Select **Sales order**.</span></span>
1. <span data-ttu-id="3b6f1-110">Digitare un valore nel campo **Conto cliente**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-110">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="3b6f1-111">Esempio: US-001</span><span class="sxs-lookup"><span data-stu-id="3b6f1-111">Example: US-001</span></span>  
1. <span data-ttu-id="3b6f1-112">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-112">Select **OK**.</span></span>
1. <span data-ttu-id="3b6f1-113">Nel campo **Numero articolo**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-113">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="3b6f1-114">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="3b6f1-114">Example: P6003</span></span>  
1. <span data-ttu-id="3b6f1-115">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-115">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="3b6f1-116">Esempio: 50000</span><span class="sxs-lookup"><span data-stu-id="3b6f1-116">Example: 50000</span></span>  
1. <span data-ttu-id="3b6f1-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-117">Select **Save**.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="3b6f1-118">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="3b6f1-118">Create a material plan for co-products</span></span>

1. <span data-ttu-id="3b6f1-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-119">Close the page.</span></span>
1. <span data-ttu-id="3b6f1-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-120">Close the page.</span></span>
1. <span data-ttu-id="3b6f1-121">Selezionare **Pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-121">Select **Master planning**.</span></span>
1. <span data-ttu-id="3b6f1-122">Nel campo **Piano** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-122">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
1. <span data-ttu-id="3b6f1-123">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-123">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="3b6f1-124">Esempio: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="3b6f1-124">Example: MasterPlan</span></span>  
1. <span data-ttu-id="3b6f1-125">Selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-125">Select **Run**.</span></span>
1. <span data-ttu-id="3b6f1-126">Espandere o comprimere la sezione **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-126">Expand or collapse the **Records to include** section.</span></span>
1. <span data-ttu-id="3b6f1-127">Seleziona **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-127">Select **Filter**.</span></span>
1. <span data-ttu-id="3b6f1-128">Nell'elenco selezionare la riga per **Campo** = *Numero articolo*.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-128">In the list, select the row for **Field** = *Item number*.</span></span>
1. <span data-ttu-id="3b6f1-129">Digitare un valore nel campo **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-129">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="3b6f1-130">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="3b6f1-130">Example: P6003</span></span>  
1. <span data-ttu-id="3b6f1-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-131">Select **OK**.</span></span>
1. <span data-ttu-id="3b6f1-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-132">Select **OK**.</span></span>
1. <span data-ttu-id="3b6f1-133">Selezionare **Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-133">Select **Planned orders**.</span></span>
1. <span data-ttu-id="3b6f1-134">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3b6f1-135">Ad esempio, filtrare il campo **Numero articolo** con un valore "P6000".</span><span class="sxs-lookup"><span data-stu-id="3b6f1-135">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="3b6f1-136">Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-136">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
1. <span data-ttu-id="3b6f1-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3b6f1-138">Selezionare una delle righe restituite dal filtro.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-138">Select any of the rows returned by the filter.</span></span>  
1. <span data-ttu-id="3b6f1-139">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-139">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="3b6f1-140">Espandere la sezione **Pegging**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-140">Expand the **Pegging** section.</span></span>
1. <span data-ttu-id="3b6f1-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-141">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="3b6f1-142">L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-142">The planned order is pegged to the sales order for the co-product.</span></span>  
1. <span data-ttu-id="3b6f1-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-143">Close the page.</span></span>

## <a name="create-a-second-requirement-for-a-co-product"></a><span data-ttu-id="3b6f1-144">Creare un secondo fabbisogno per un co-prodotto</span><span class="sxs-lookup"><span data-stu-id="3b6f1-144">Create a second requirement for a co-product</span></span>

1. <span data-ttu-id="3b6f1-145">Vai a **Vendite e marketing \> Aree di lavoro \> Elaborazione e richiesta di informazioni ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-145">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="3b6f1-146">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-146">Select **New**.</span></span>
1. <span data-ttu-id="3b6f1-147">Selezionare **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-147">Select **Sales order**.</span></span>
1. <span data-ttu-id="3b6f1-148">Digitare un valore nel campo **Conto cliente**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-148">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="3b6f1-149">Esempio: US-001</span><span class="sxs-lookup"><span data-stu-id="3b6f1-149">Example: US-001</span></span>  
1. <span data-ttu-id="3b6f1-150">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-150">Select **OK**.</span></span>
1. <span data-ttu-id="3b6f1-151">Nel campo **Numero articolo**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-151">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="3b6f1-152">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="3b6f1-152">Example: P6003</span></span>  
1. <span data-ttu-id="3b6f1-153">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-153">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="3b6f1-154">Esempio: 50000</span><span class="sxs-lookup"><span data-stu-id="3b6f1-154">Example: 50000</span></span>  
1. <span data-ttu-id="3b6f1-155">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-155">Select **Save**.</span></span>

## <a name="create-a-second-material-plan-for-co-products"></a><span data-ttu-id="3b6f1-156">Creare un secondo piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="3b6f1-156">Create a second material plan for co-products</span></span>

1. <span data-ttu-id="3b6f1-157">Nel campo **Piano** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-157">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="3b6f1-158">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-158">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="3b6f1-159">Esempio: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="3b6f1-159">Example: MasterPlan</span></span>  
3. <span data-ttu-id="3b6f1-160">Selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-160">Select **Run**.</span></span>
4. <span data-ttu-id="3b6f1-161">Espandere o comprimere la sezione **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-161">Expand or collapse the **Records to include** section.</span></span>
5. <span data-ttu-id="3b6f1-162">Seleziona **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-162">Select **Filter**.</span></span>
6. <span data-ttu-id="3b6f1-163">Nell'elenco selezionare la riga per **Campo** = *Numero articolo*.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-163">In the list, select the row for **Field** = *Item number*.</span></span>
7. <span data-ttu-id="3b6f1-164">Digitare un valore nel campo *Criteri*.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-164">In the *Criteria* field, type a value.</span></span>
    * <span data-ttu-id="3b6f1-165">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="3b6f1-165">Example: P6003</span></span>  
8. <span data-ttu-id="3b6f1-166">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-166">Select **OK**.</span></span>
9. <span data-ttu-id="3b6f1-167">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-167">Select **OK**.</span></span>
10. <span data-ttu-id="3b6f1-168">Selezionare **Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-168">Select **Planned orders**.</span></span>
11. <span data-ttu-id="3b6f1-169">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-169">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3b6f1-170">Ad esempio, filtrare il campo **Numero articolo** con un valore "P6000".</span><span class="sxs-lookup"><span data-stu-id="3b6f1-170">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="3b6f1-171">Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-171">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="3b6f1-172">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-172">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3b6f1-173">Selezionare una delle righe restituite dal filtro.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-173">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="3b6f1-174">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-174">In the list, select the link in the selected row.</span></span>
14. <span data-ttu-id="3b6f1-175">Espandere o comprimere la sezione **Pegging**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-175">Expand or collapse the **Pegging** section.</span></span>
15. <span data-ttu-id="3b6f1-176">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-176">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="3b6f1-177">L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-177">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="3b6f1-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-178">Close the page.</span></span>
17. <span data-ttu-id="3b6f1-179">Selezionare **Pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-179">Select **Master planning**.</span></span>
18. <span data-ttu-id="3b6f1-180">Andare a **Pianificazione generale \> Impostazioni \>Parametri di pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-180">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
19. <span data-ttu-id="3b6f1-181">Selezionare *No* nel campo **Disattiva tutti i processi di pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-181">Select *No* in the **Disable all planning processes** field.</span></span>
20. <span data-ttu-id="3b6f1-182">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3b6f1-182">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]