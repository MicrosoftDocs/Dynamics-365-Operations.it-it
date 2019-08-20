---
title: Creare DBA (febbraio 2016)
description: Questa attività consente di creare la struttura della distinta base per un prodotto finito e un prodotto semilavorato.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0087c53d9cdc3bb65e6fa446c193c752d0f9b4fc
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845091"
---
# <a name="create-boms-february-2016"></a><span data-ttu-id="52ba2-103">Creare DBA (febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="52ba2-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="52ba2-104">Questa attività consente di creare la struttura della distinta base per un prodotto finito e un prodotto semilavorato.</span><span class="sxs-lookup"><span data-stu-id="52ba2-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="52ba2-105">Corrisponde alla quarta attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="52ba2-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="52ba2-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="52ba2-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="52ba2-107">Creare una DBA per un prodotto semilavorato</span><span class="sxs-lookup"><span data-stu-id="52ba2-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="52ba2-108">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="52ba2-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="52ba2-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="52ba2-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="52ba2-110">Selezionare il numero dell'articolo BOM_2.</span><span class="sxs-lookup"><span data-stu-id="52ba2-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="52ba2-111">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="52ba2-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="52ba2-112">Fare clic su Versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="52ba2-112">Click BOM versions.</span></span>
5. <span data-ttu-id="52ba2-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="52ba2-113">Click New.</span></span>
6. <span data-ttu-id="52ba2-114">Fare clic su DBA e versione DBA.</span><span class="sxs-lookup"><span data-stu-id="52ba2-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="52ba2-115">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="52ba2-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="52ba2-116">Ad esempio, digitare BOM_2.</span><span class="sxs-lookup"><span data-stu-id="52ba2-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="52ba2-117">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="52ba2-118">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="52ba2-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="52ba2-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="52ba2-119">Click OK.</span></span>
10. <span data-ttu-id="52ba2-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="52ba2-120">Click New.</span></span>
11. <span data-ttu-id="52ba2-121">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="52ba2-122">Per questo esempio, digitare ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="52ba2-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="52ba2-123">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="52ba2-124">Ad esempio, immettere o selezionare 11.</span><span class="sxs-lookup"><span data-stu-id="52ba2-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="52ba2-125">Fare clic su Intestazione.</span><span class="sxs-lookup"><span data-stu-id="52ba2-125">Click Header.</span></span>
14. <span data-ttu-id="52ba2-126">Fare clic Approva per approvare le distinte base.</span><span class="sxs-lookup"><span data-stu-id="52ba2-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="52ba2-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="52ba2-127">Click OK.</span></span>
16. <span data-ttu-id="52ba2-128">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="52ba2-128">Click Approve.</span></span>
    * <span data-ttu-id="52ba2-129">Il pulsante Approva nella barra degli strumenti dell'area delle versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="52ba2-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="52ba2-130">Se non è visibile, fare clic su Intestazione nella parte superiore destra della pagina delle distinte base per visualizzare Approva.</span><span class="sxs-lookup"><span data-stu-id="52ba2-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="52ba2-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="52ba2-131">Click OK.</span></span>
18. <span data-ttu-id="52ba2-132">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="52ba2-132">Click Activate.</span></span>
19. <span data-ttu-id="52ba2-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="52ba2-133">Close the page.</span></span>
20. <span data-ttu-id="52ba2-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="52ba2-134">Close the page.</span></span>
21. <span data-ttu-id="52ba2-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="52ba2-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="52ba2-136">Creare una DBA per un prodotto semilavorato</span><span class="sxs-lookup"><span data-stu-id="52ba2-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="52ba2-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="52ba2-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="52ba2-138">Selezionare il numero dell'articolo BOM_1.</span><span class="sxs-lookup"><span data-stu-id="52ba2-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="52ba2-139">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="52ba2-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="52ba2-140">Fare clic su Versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="52ba2-140">Click BOM versions.</span></span>
4. <span data-ttu-id="52ba2-141">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="52ba2-141">Click New.</span></span>
5. <span data-ttu-id="52ba2-142">Fare clic su DBA e versione DBA.</span><span class="sxs-lookup"><span data-stu-id="52ba2-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="52ba2-143">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="52ba2-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="52ba2-144">Ad esempio, digitare BOM_1.</span><span class="sxs-lookup"><span data-stu-id="52ba2-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="52ba2-145">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="52ba2-146">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="52ba2-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="52ba2-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="52ba2-147">Click OK.</span></span>
9. <span data-ttu-id="52ba2-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="52ba2-148">Click New.</span></span>
10. <span data-ttu-id="52ba2-149">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="52ba2-150">Per questo esempio, digitare ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="52ba2-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="52ba2-151">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="52ba2-152">Per questo esempio, selezionare 11.</span><span class="sxs-lookup"><span data-stu-id="52ba2-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="52ba2-153">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="52ba2-153">Click New.</span></span>
13. <span data-ttu-id="52ba2-154">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="52ba2-155">Per questo esempio, digitare ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="52ba2-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="52ba2-156">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="52ba2-157">Ad esempio, immettere o selezionare 11.</span><span class="sxs-lookup"><span data-stu-id="52ba2-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="52ba2-158">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="52ba2-158">Click New.</span></span>
16. <span data-ttu-id="52ba2-159">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="52ba2-160">Per questo esempio, digitare BOM_2.</span><span class="sxs-lookup"><span data-stu-id="52ba2-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="52ba2-161">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="52ba2-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="52ba2-162">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="52ba2-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="52ba2-163">Ad esempio, immettere o selezionare il magazzino 11.</span><span class="sxs-lookup"><span data-stu-id="52ba2-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="52ba2-164">Fare clic su Intestazione.</span><span class="sxs-lookup"><span data-stu-id="52ba2-164">Click Header.</span></span>
20. <span data-ttu-id="52ba2-165">Fare clic Approva per approvare le distinte base.</span><span class="sxs-lookup"><span data-stu-id="52ba2-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="52ba2-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="52ba2-166">Click OK.</span></span>
22. <span data-ttu-id="52ba2-167">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="52ba2-167">Click Approve.</span></span>
    * <span data-ttu-id="52ba2-168">Il pulsante Approva nella barra degli strumenti dell'area delle versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="52ba2-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="52ba2-169">Se non è visibile, fare clic su Intestazione nella parte superiore destra della pagina delle distinte base per visualizzare Approva.</span><span class="sxs-lookup"><span data-stu-id="52ba2-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="52ba2-170">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="52ba2-170">Click OK.</span></span>
24. <span data-ttu-id="52ba2-171">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="52ba2-171">Click Activate.</span></span>
25. <span data-ttu-id="52ba2-172">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="52ba2-172">Close the page.</span></span>
26. <span data-ttu-id="52ba2-173">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="52ba2-173">Close the page.</span></span>
27. <span data-ttu-id="52ba2-174">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="52ba2-174">Close the page.</span></span>

