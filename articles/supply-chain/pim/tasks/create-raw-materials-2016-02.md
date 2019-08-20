---
title: Creare le materie prime (febbraio 2016)
description: Questa attività consente di creare i componenti dei prodotti finiti e semilavorati.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e20abf8a1b211bff2bc73d1a36a1e5c917ffaab
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844587"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="3fa56-103">Creare le materie prime (febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="3fa56-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3fa56-104">Questa attività consente di creare i componenti dei prodotti finiti e semilavorati.</span><span class="sxs-lookup"><span data-stu-id="3fa56-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="3fa56-105">Corrisponde alla terza attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="3fa56-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="3fa56-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="3fa56-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="3fa56-107">Creare il primo materiale</span><span class="sxs-lookup"><span data-stu-id="3fa56-107">Create the first material</span></span>
1. <span data-ttu-id="3fa56-108">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="3fa56-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="3fa56-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-109">Click New.</span></span>
3. <span data-ttu-id="3fa56-110">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="3fa56-111">Per questo esempio, immettere ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="3fa56-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="3fa56-112">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-113">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="3fa56-113">Select STD.</span></span> <span data-ttu-id="3fa56-114">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="3fa56-115">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-116">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="3fa56-116">For example, select Audio.</span></span> <span data-ttu-id="3fa56-117">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="3fa56-118">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-119">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="3fa56-119">Select SiteWH.</span></span> <span data-ttu-id="3fa56-120">Solo sito e magazzino verranno utilizzati per la dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="3fa56-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="3fa56-121">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-122">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3fa56-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="3fa56-123">Selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3fa56-123">Select None.</span></span>  
8. <span data-ttu-id="3fa56-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3fa56-124">Click OK.</span></span>
9. <span data-ttu-id="3fa56-125">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="3fa56-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="3fa56-126">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="3fa56-126">Click Default order settings.</span></span>
11. <span data-ttu-id="3fa56-127">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-128">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="3fa56-129">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-130">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="3fa56-131">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-132">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="3fa56-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-133">Close the page.</span></span>
15. <span data-ttu-id="3fa56-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-134">Close the page.</span></span>
16. <span data-ttu-id="3fa56-135">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3fa56-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3fa56-136">Fare clic su ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="3fa56-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="3fa56-137">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="3fa56-138">Digitare un valore nel campo Gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="3fa56-139">Per questo esempio, digitare M2.</span><span class="sxs-lookup"><span data-stu-id="3fa56-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="3fa56-140">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="3fa56-141">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-141">Click Item price.</span></span>
21. <span data-ttu-id="3fa56-142">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-142">Click New.</span></span>
22. <span data-ttu-id="3fa56-143">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-144">Per questo esempio, selezionare 10, ovvero il tipo di determinazione costi standard.</span><span class="sxs-lookup"><span data-stu-id="3fa56-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="3fa56-145">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-146">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="3fa56-147">Immettere un numero nel campo Prezzo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="3fa56-148">Per questo esempio, digitare 10.</span><span class="sxs-lookup"><span data-stu-id="3fa56-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="3fa56-149">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3fa56-149">Click Save.</span></span>
26. <span data-ttu-id="3fa56-150">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3fa56-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="3fa56-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-151">Close the page.</span></span>
28. <span data-ttu-id="3fa56-152">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="3fa56-153">Creare il secondo materiale</span><span class="sxs-lookup"><span data-stu-id="3fa56-153">Create the second material</span></span>
1. <span data-ttu-id="3fa56-154">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-154">Click New.</span></span>
2. <span data-ttu-id="3fa56-155">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="3fa56-156">Per questo esempio, digitare ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="3fa56-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="3fa56-157">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-158">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="3fa56-158">Select STD.</span></span> <span data-ttu-id="3fa56-159">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="3fa56-160">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-161">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="3fa56-161">For example, select Audio.</span></span> <span data-ttu-id="3fa56-162">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="3fa56-163">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-164">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="3fa56-164">Select SiteWH.</span></span> <span data-ttu-id="3fa56-165">Solo sito e magazzino verranno utilizzati per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3fa56-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="3fa56-166">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-167">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3fa56-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="3fa56-168">Selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3fa56-168">Select None.</span></span>  
7. <span data-ttu-id="3fa56-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3fa56-169">Click OK.</span></span>
8. <span data-ttu-id="3fa56-170">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="3fa56-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="3fa56-171">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="3fa56-171">Click Default order settings.</span></span>
10. <span data-ttu-id="3fa56-172">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-173">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="3fa56-174">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-175">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="3fa56-176">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-177">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="3fa56-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-178">Close the page.</span></span>
14. <span data-ttu-id="3fa56-179">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-179">Close the page.</span></span>
15. <span data-ttu-id="3fa56-180">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3fa56-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3fa56-181">Fare clic su ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="3fa56-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="3fa56-182">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="3fa56-183">Digitare un valore nel campo Gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="3fa56-184">Per questo esempio, digitare M2.</span><span class="sxs-lookup"><span data-stu-id="3fa56-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="3fa56-185">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="3fa56-186">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-186">Click Item price.</span></span>
20. <span data-ttu-id="3fa56-187">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-187">Click New.</span></span>
21. <span data-ttu-id="3fa56-188">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-189">Per questo esempio, selezionare 10.</span><span class="sxs-lookup"><span data-stu-id="3fa56-189">For this example, select 10.</span></span> <span data-ttu-id="3fa56-190">Si tratta del tipo di determinazione costi standard.</span><span class="sxs-lookup"><span data-stu-id="3fa56-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="3fa56-191">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-192">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="3fa56-193">Immettere un numero nel campo Prezzo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="3fa56-194">Per la dimostrazione, digitare 10.</span><span class="sxs-lookup"><span data-stu-id="3fa56-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="3fa56-195">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3fa56-195">Click Save.</span></span>
25. <span data-ttu-id="3fa56-196">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3fa56-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="3fa56-197">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-197">Close the page.</span></span>
27. <span data-ttu-id="3fa56-198">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="3fa56-199">Creare il terzo materiale</span><span class="sxs-lookup"><span data-stu-id="3fa56-199">Create the third material</span></span>
1. <span data-ttu-id="3fa56-200">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-200">Click New.</span></span>
2. <span data-ttu-id="3fa56-201">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="3fa56-202">Per la dimostrazione, digitare ITEM_C</span><span class="sxs-lookup"><span data-stu-id="3fa56-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="3fa56-203">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-204">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="3fa56-204">Select STD.</span></span> <span data-ttu-id="3fa56-205">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="3fa56-206">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-207">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="3fa56-207">For example, select Audio.</span></span> <span data-ttu-id="3fa56-208">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="3fa56-209">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-210">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="3fa56-210">Select SiteWH.</span></span> <span data-ttu-id="3fa56-211">Solo sito e magazzino verranno utilizzati per la dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="3fa56-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="3fa56-212">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-213">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3fa56-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="3fa56-214">Selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3fa56-214">Select None.</span></span>  
7. <span data-ttu-id="3fa56-215">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3fa56-215">Click OK.</span></span>
8. <span data-ttu-id="3fa56-216">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="3fa56-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="3fa56-217">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="3fa56-217">Click Default order settings.</span></span>
10. <span data-ttu-id="3fa56-218">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-219">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="3fa56-220">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-221">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="3fa56-222">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-223">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="3fa56-224">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-224">Close the page.</span></span>
14. <span data-ttu-id="3fa56-225">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-225">Close the page.</span></span>
15. <span data-ttu-id="3fa56-226">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3fa56-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3fa56-227">Fare clic su ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="3fa56-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="3fa56-228">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="3fa56-229">Digitare un valore nel campo Gruppo di costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="3fa56-230">Per questo esempio, digitare M1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="3fa56-231">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="3fa56-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="3fa56-232">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-232">Click Item price.</span></span>
20. <span data-ttu-id="3fa56-233">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-233">Click New.</span></span>
21. <span data-ttu-id="3fa56-234">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-235">Per questo esempio, selezionare 10.</span><span class="sxs-lookup"><span data-stu-id="3fa56-235">For this example, select 10.</span></span> <span data-ttu-id="3fa56-236">Si tratta del tipo di determinazione costi standard.</span><span class="sxs-lookup"><span data-stu-id="3fa56-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="3fa56-237">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3fa56-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3fa56-238">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="3fa56-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="3fa56-239">Immettere un numero nel campo Prezzo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="3fa56-240">Per questo esempio, digitare 10.</span><span class="sxs-lookup"><span data-stu-id="3fa56-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="3fa56-241">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3fa56-241">Click Save.</span></span>
25. <span data-ttu-id="3fa56-242">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3fa56-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="3fa56-243">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-243">Close the page.</span></span>
27. <span data-ttu-id="3fa56-244">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3fa56-244">Close the page.</span></span>

