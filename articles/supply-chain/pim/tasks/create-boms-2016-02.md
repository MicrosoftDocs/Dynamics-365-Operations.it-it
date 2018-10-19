--- 
title: Creare DBA (febbraio 2016)
description: "Questa attività consente di creare la struttura della distinta base per un prodotto finito e un prodotto semilavorato."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6c5cfb8aae1a61d14f7a7969f688cb282530840d
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="create-boms-february-2016"></a><span data-ttu-id="b7e61-103">Creare DBA (febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="b7e61-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b7e61-104">Questa attività consente di creare la struttura della distinta base per un prodotto finito e un prodotto semilavorato.</span><span class="sxs-lookup"><span data-stu-id="b7e61-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="b7e61-105">Corrisponde alla quarta attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="b7e61-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="b7e61-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="b7e61-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="b7e61-107">Creare una DBA per un prodotto semilavorato</span><span class="sxs-lookup"><span data-stu-id="b7e61-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="b7e61-108">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="b7e61-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="b7e61-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b7e61-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b7e61-110">Selezionare il numero dell'articolo BOM_2.</span><span class="sxs-lookup"><span data-stu-id="b7e61-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="b7e61-111">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="b7e61-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="b7e61-112">Fare clic su Versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="b7e61-112">Click BOM versions.</span></span>
5. <span data-ttu-id="b7e61-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b7e61-113">Click New.</span></span>
6. <span data-ttu-id="b7e61-114">Fare clic su DBA e versione DBA.</span><span class="sxs-lookup"><span data-stu-id="b7e61-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="b7e61-115">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b7e61-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="b7e61-116">Ad esempio, digitare BOM_2.</span><span class="sxs-lookup"><span data-stu-id="b7e61-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="b7e61-117">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="b7e61-118">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="b7e61-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="b7e61-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b7e61-119">Click OK.</span></span>
10. <span data-ttu-id="b7e61-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b7e61-120">Click New.</span></span>
11. <span data-ttu-id="b7e61-121">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b7e61-122">Per questo esempio, digitare ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="b7e61-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="b7e61-123">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b7e61-124">Ad esempio, immettere o selezionare 11.</span><span class="sxs-lookup"><span data-stu-id="b7e61-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="b7e61-125">Fare clic su Intestazione.</span><span class="sxs-lookup"><span data-stu-id="b7e61-125">Click Header.</span></span>
14. <span data-ttu-id="b7e61-126">Fare clic Approva per approvare le distinte base.</span><span class="sxs-lookup"><span data-stu-id="b7e61-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="b7e61-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b7e61-127">Click OK.</span></span>
16. <span data-ttu-id="b7e61-128">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="b7e61-128">Click Approve.</span></span>
    * <span data-ttu-id="b7e61-129">Il pulsante Approva nella barra degli strumenti dell'area delle versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="b7e61-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="b7e61-130">Se non è visibile, fare clic su Intestazione nella parte superiore destra della pagina delle distinte base per visualizzare Approva.</span><span class="sxs-lookup"><span data-stu-id="b7e61-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="b7e61-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b7e61-131">Click OK.</span></span>
18. <span data-ttu-id="b7e61-132">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="b7e61-132">Click Activate.</span></span>
19. <span data-ttu-id="b7e61-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b7e61-133">Close the page.</span></span>
20. <span data-ttu-id="b7e61-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b7e61-134">Close the page.</span></span>
21. <span data-ttu-id="b7e61-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b7e61-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="b7e61-136">Creare una DBA per un prodotto semilavorato</span><span class="sxs-lookup"><span data-stu-id="b7e61-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="b7e61-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b7e61-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b7e61-138">Selezionare il numero dell'articolo BOM_1.</span><span class="sxs-lookup"><span data-stu-id="b7e61-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="b7e61-139">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="b7e61-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="b7e61-140">Fare clic su Versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="b7e61-140">Click BOM versions.</span></span>
4. <span data-ttu-id="b7e61-141">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b7e61-141">Click New.</span></span>
5. <span data-ttu-id="b7e61-142">Fare clic su DBA e versione DBA.</span><span class="sxs-lookup"><span data-stu-id="b7e61-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="b7e61-143">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b7e61-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="b7e61-144">Ad esempio, digitare BOM_1.</span><span class="sxs-lookup"><span data-stu-id="b7e61-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="b7e61-145">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="b7e61-146">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="b7e61-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="b7e61-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b7e61-147">Click OK.</span></span>
9. <span data-ttu-id="b7e61-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b7e61-148">Click New.</span></span>
10. <span data-ttu-id="b7e61-149">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b7e61-150">Per questo esempio, digitare ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="b7e61-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="b7e61-151">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b7e61-152">Per questo esempio, selezionare 11.</span><span class="sxs-lookup"><span data-stu-id="b7e61-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="b7e61-153">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b7e61-153">Click New.</span></span>
13. <span data-ttu-id="b7e61-154">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b7e61-155">Per questo esempio, digitare ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="b7e61-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="b7e61-156">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b7e61-157">Ad esempio, immettere o selezionare 11.</span><span class="sxs-lookup"><span data-stu-id="b7e61-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="b7e61-158">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b7e61-158">Click New.</span></span>
16. <span data-ttu-id="b7e61-159">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b7e61-160">Per questo esempio, digitare BOM_2.</span><span class="sxs-lookup"><span data-stu-id="b7e61-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="b7e61-161">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b7e61-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="b7e61-162">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b7e61-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b7e61-163">Ad esempio, immettere o selezionare il magazzino 11.</span><span class="sxs-lookup"><span data-stu-id="b7e61-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="b7e61-164">Fare clic su Intestazione.</span><span class="sxs-lookup"><span data-stu-id="b7e61-164">Click Header.</span></span>
20. <span data-ttu-id="b7e61-165">Fare clic Approva per approvare le distinte base.</span><span class="sxs-lookup"><span data-stu-id="b7e61-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="b7e61-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b7e61-166">Click OK.</span></span>
22. <span data-ttu-id="b7e61-167">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="b7e61-167">Click Approve.</span></span>
    * <span data-ttu-id="b7e61-168">Il pulsante Approva nella barra degli strumenti dell'area delle versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="b7e61-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="b7e61-169">Se non è visibile, fare clic su Intestazione nella parte superiore destra della pagina delle distinte base per visualizzare Approva.</span><span class="sxs-lookup"><span data-stu-id="b7e61-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="b7e61-170">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b7e61-170">Click OK.</span></span>
24. <span data-ttu-id="b7e61-171">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="b7e61-171">Click Activate.</span></span>
25. <span data-ttu-id="b7e61-172">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b7e61-172">Close the page.</span></span>
26. <span data-ttu-id="b7e61-173">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b7e61-173">Close the page.</span></span>
27. <span data-ttu-id="b7e61-174">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b7e61-174">Close the page.</span></span>


