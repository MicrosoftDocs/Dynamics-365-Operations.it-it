--- 
title: Creare materie prime (solo febbraio 2016)
description: "Questa attività consente di creare i componenti dei prodotti finiti e semilavorati."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3d77dcc20fe7402af83dd724e7fef848977e5bf8
ms.openlocfilehash: f6af7b93d8d1d9a6f7474f24177b16e5295e90d6
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="ee514-103">Creare materie prime (solo febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="ee514-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee514-104">Questa attività consente di creare i componenti dei prodotti finiti e semilavorati.</span><span class="sxs-lookup"><span data-stu-id="ee514-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="ee514-105">Corrisponde alla terza attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="ee514-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="ee514-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="ee514-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="ee514-107">Creare il primo materiale</span><span class="sxs-lookup"><span data-stu-id="ee514-107">Create the first material</span></span>
1. <span data-ttu-id="ee514-108">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="ee514-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ee514-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee514-109">Click New.</span></span>
3. <span data-ttu-id="ee514-110">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ee514-111">Per questo esempio, immettere ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ee514-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="ee514-112">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-113">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="ee514-113">Select STD.</span></span> <span data-ttu-id="ee514-114">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="ee514-115">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-116">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="ee514-116">For example, select Audio.</span></span> <span data-ttu-id="ee514-117">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="ee514-118">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-119">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ee514-119">Select SiteWH.</span></span> <span data-ttu-id="ee514-120">Solo sito e magazzino verranno utilizzati per la dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="ee514-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="ee514-121">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-122">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="ee514-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ee514-123">Selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ee514-123">Select None.</span></span>  
8. <span data-ttu-id="ee514-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ee514-124">Click OK.</span></span>
9. <span data-ttu-id="ee514-125">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="ee514-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="ee514-126">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="ee514-126">Click Default order settings.</span></span>
11. <span data-ttu-id="ee514-127">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-128">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ee514-129">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-130">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ee514-131">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-132">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="ee514-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-133">Close the page.</span></span>
15. <span data-ttu-id="ee514-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-134">Close the page.</span></span>
16. <span data-ttu-id="ee514-135">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee514-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ee514-136">Fare clic su ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="ee514-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="ee514-137">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="ee514-138">Digitare un valore nel campo Gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ee514-139">Per questo esempio, digitare M2.</span><span class="sxs-lookup"><span data-stu-id="ee514-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="ee514-140">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="ee514-141">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="ee514-141">Click Item price.</span></span>
21. <span data-ttu-id="ee514-142">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee514-142">Click New.</span></span>
22. <span data-ttu-id="ee514-143">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-144">Per questo esempio, selezionare 10, ovvero il tipo di determinazione costi standard.</span><span class="sxs-lookup"><span data-stu-id="ee514-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="ee514-145">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-146">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="ee514-147">Immettere un numero nel campo Prezzo.</span><span class="sxs-lookup"><span data-stu-id="ee514-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ee514-148">Per questo esempio, digitare 10.</span><span class="sxs-lookup"><span data-stu-id="ee514-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="ee514-149">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ee514-149">Click Save.</span></span>
26. <span data-ttu-id="ee514-150">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="ee514-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="ee514-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-151">Close the page.</span></span>
28. <span data-ttu-id="ee514-152">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="ee514-153">Creare il secondo materiale</span><span class="sxs-lookup"><span data-stu-id="ee514-153">Create the second material</span></span>
1. <span data-ttu-id="ee514-154">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee514-154">Click New.</span></span>
2. <span data-ttu-id="ee514-155">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ee514-156">Per questo esempio, digitare ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ee514-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="ee514-157">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-158">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="ee514-158">Select STD.</span></span> <span data-ttu-id="ee514-159">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ee514-160">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-161">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="ee514-161">For example, select Audio.</span></span> <span data-ttu-id="ee514-162">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ee514-163">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-164">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ee514-164">Select SiteWH.</span></span> <span data-ttu-id="ee514-165">Solo sito e magazzino verranno utilizzati per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="ee514-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="ee514-166">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-167">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="ee514-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ee514-168">Selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ee514-168">Select None.</span></span>  
7. <span data-ttu-id="ee514-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ee514-169">Click OK.</span></span>
8. <span data-ttu-id="ee514-170">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="ee514-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ee514-171">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="ee514-171">Click Default order settings.</span></span>
10. <span data-ttu-id="ee514-172">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-173">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ee514-174">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-175">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ee514-176">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-177">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ee514-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-178">Close the page.</span></span>
14. <span data-ttu-id="ee514-179">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-179">Close the page.</span></span>
15. <span data-ttu-id="ee514-180">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee514-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ee514-181">Fare clic su ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="ee514-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="ee514-182">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ee514-183">Digitare un valore nel campo Gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ee514-184">Per questo esempio, digitare M2.</span><span class="sxs-lookup"><span data-stu-id="ee514-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="ee514-185">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ee514-186">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="ee514-186">Click Item price.</span></span>
20. <span data-ttu-id="ee514-187">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee514-187">Click New.</span></span>
21. <span data-ttu-id="ee514-188">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-189">Per questo esempio, selezionare 10.</span><span class="sxs-lookup"><span data-stu-id="ee514-189">For this example, select 10.</span></span> <span data-ttu-id="ee514-190">Si tratta del tipo di determinazione costi standard.</span><span class="sxs-lookup"><span data-stu-id="ee514-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ee514-191">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-192">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ee514-193">Immettere un numero nel campo Prezzo.</span><span class="sxs-lookup"><span data-stu-id="ee514-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ee514-194">Per la dimostrazione, digitare 10.</span><span class="sxs-lookup"><span data-stu-id="ee514-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="ee514-195">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ee514-195">Click Save.</span></span>
25. <span data-ttu-id="ee514-196">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="ee514-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ee514-197">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-197">Close the page.</span></span>
27. <span data-ttu-id="ee514-198">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="ee514-199">Creare il terzo materiale</span><span class="sxs-lookup"><span data-stu-id="ee514-199">Create the third material</span></span>
1. <span data-ttu-id="ee514-200">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee514-200">Click New.</span></span>
2. <span data-ttu-id="ee514-201">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ee514-202">Per la dimostrazione, digitare ITEM_C</span><span class="sxs-lookup"><span data-stu-id="ee514-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="ee514-203">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-204">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="ee514-204">Select STD.</span></span> <span data-ttu-id="ee514-205">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="ee514-206">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-207">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="ee514-207">For example, select Audio.</span></span> <span data-ttu-id="ee514-208">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="ee514-209">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-210">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="ee514-210">Select SiteWH.</span></span> <span data-ttu-id="ee514-211">Solo sito e magazzino verranno utilizzati per la dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="ee514-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="ee514-212">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-213">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="ee514-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="ee514-214">Selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ee514-214">Select None.</span></span>  
7. <span data-ttu-id="ee514-215">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ee514-215">Click OK.</span></span>
8. <span data-ttu-id="ee514-216">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="ee514-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="ee514-217">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="ee514-217">Click Default order settings.</span></span>
10. <span data-ttu-id="ee514-218">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-219">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="ee514-220">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-221">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="ee514-222">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-223">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="ee514-224">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-224">Close the page.</span></span>
14. <span data-ttu-id="ee514-225">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-225">Close the page.</span></span>
15. <span data-ttu-id="ee514-226">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee514-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ee514-227">Fare clic su ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="ee514-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="ee514-228">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="ee514-229">Digitare un valore nel campo Gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="ee514-230">Per questo esempio, digitare M1.</span><span class="sxs-lookup"><span data-stu-id="ee514-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="ee514-231">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="ee514-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="ee514-232">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="ee514-232">Click Item price.</span></span>
20. <span data-ttu-id="ee514-233">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee514-233">Click New.</span></span>
21. <span data-ttu-id="ee514-234">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-235">Per questo esempio, selezionare 10.</span><span class="sxs-lookup"><span data-stu-id="ee514-235">For this example, select 10.</span></span> <span data-ttu-id="ee514-236">Si tratta del tipo di determinazione costi standard.</span><span class="sxs-lookup"><span data-stu-id="ee514-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="ee514-237">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee514-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ee514-238">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="ee514-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="ee514-239">Immettere un numero nel campo Prezzo.</span><span class="sxs-lookup"><span data-stu-id="ee514-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="ee514-240">Per questo esempio, digitare 10.</span><span class="sxs-lookup"><span data-stu-id="ee514-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="ee514-241">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ee514-241">Click Save.</span></span>
25. <span data-ttu-id="ee514-242">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="ee514-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="ee514-243">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-243">Close the page.</span></span>
27. <span data-ttu-id="ee514-244">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ee514-244">Close the page.</span></span>


