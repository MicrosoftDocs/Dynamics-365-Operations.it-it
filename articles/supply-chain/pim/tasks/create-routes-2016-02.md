--- 
title: Crea cicli di lavorazione (febbraio 2016)
description: "Questa attività consente di creare i cicli di lavorazione produzione per un prodotto finito e un prodotto semilavorato."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 965826f5fddc2f53f33157434929eb265979376e
ms.openlocfilehash: a68b28c0e0ee14429a23d3241cabdae948d706d2
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="create-routes-february-2016"></a><span data-ttu-id="731ff-103">Crea cicli di lavorazione (febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="731ff-103">Create routes (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="731ff-104">Questa attività consente di creare i cicli di lavorazione produzione per un prodotto finito e un prodotto semilavorato.</span><span class="sxs-lookup"><span data-stu-id="731ff-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="731ff-105">Corrisponde alla quinta attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="731ff-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="731ff-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="731ff-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="731ff-107">Creare un ciclo di lavorazione per un prodotto semilavorato</span><span class="sxs-lookup"><span data-stu-id="731ff-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="731ff-108">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="731ff-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="731ff-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="731ff-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="731ff-110">Selezionare il numero dell'articolo BOM_2.</span><span class="sxs-lookup"><span data-stu-id="731ff-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="731ff-111">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="731ff-112">Fare clic su Ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-112">Click Route.</span></span>
5. <span data-ttu-id="731ff-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="731ff-113">Click New.</span></span>
6. <span data-ttu-id="731ff-114">Fare clic su Ciclo di lavorazione e versione del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-114">Click Route and route version.</span></span>
7. <span data-ttu-id="731ff-115">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="731ff-116">Per questo esempio, digitare ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="731ff-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="731ff-117">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-118">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="731ff-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="731ff-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="731ff-119">Click OK.</span></span>
10. <span data-ttu-id="731ff-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="731ff-120">Click New.</span></span>
11. <span data-ttu-id="731ff-121">Nel campo Operazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-122">Per questo esempio, selezionare Assembly.</span><span class="sxs-lookup"><span data-stu-id="731ff-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="731ff-123">Nel campo Tempo di esecuzione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="731ff-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="731ff-124">Ad esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="731ff-124">For example, type 1.</span></span> <span data-ttu-id="731ff-125">Il tempo di esecuzione spesso fa parte del prezzo calcolato per un articolo.</span><span class="sxs-lookup"><span data-stu-id="731ff-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="731ff-126">Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-127">Per questo esempio, selezionare Std.</span><span class="sxs-lookup"><span data-stu-id="731ff-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="731ff-128">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="731ff-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="731ff-129">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-130">Per questo esempio, selezionare Assembly.</span><span class="sxs-lookup"><span data-stu-id="731ff-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="731ff-131">Fare clic sulla scheda Tempi.</span><span class="sxs-lookup"><span data-stu-id="731ff-131">Click the Times tab.</span></span>
17. <span data-ttu-id="731ff-132">Nel campo Tempo di attrezzaggio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="731ff-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="731ff-133">Per questo esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="731ff-133">For this example, type 1.</span></span> <span data-ttu-id="731ff-134">Il tempo di impostazione spesso fa parte del prezzo calcolato per un articolo.</span><span class="sxs-lookup"><span data-stu-id="731ff-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="731ff-135">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="731ff-136">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="731ff-136">Click Approve.</span></span>
20. <span data-ttu-id="731ff-137">Selezionare Sì nel campo Approvare anche il ciclo di lavorazione? .</span><span class="sxs-lookup"><span data-stu-id="731ff-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="731ff-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="731ff-138">Click OK.</span></span>
22. <span data-ttu-id="731ff-139">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="731ff-140">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="731ff-140">Click Activate.</span></span>
24. <span data-ttu-id="731ff-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="731ff-141">Close the page.</span></span>
25. <span data-ttu-id="731ff-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="731ff-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="731ff-143">Creare un ciclo di lavorazione per un prodotto finito</span><span class="sxs-lookup"><span data-stu-id="731ff-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="731ff-144">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="731ff-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="731ff-145">Selezionare il numero dell'articolo BOM_1.</span><span class="sxs-lookup"><span data-stu-id="731ff-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="731ff-146">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="731ff-147">Fare clic su Ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-147">Click Route.</span></span>
4. <span data-ttu-id="731ff-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="731ff-148">Click New.</span></span>
5. <span data-ttu-id="731ff-149">Fare clic su Ciclo di lavorazione e versione del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-149">Click Route and route version.</span></span>
6. <span data-ttu-id="731ff-150">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="731ff-151">Per questo esempio, digitare ROUTE_1.</span><span class="sxs-lookup"><span data-stu-id="731ff-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="731ff-152">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-153">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="731ff-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="731ff-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="731ff-154">Click OK.</span></span>
9. <span data-ttu-id="731ff-155">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="731ff-155">Click New.</span></span>
10. <span data-ttu-id="731ff-156">Nel campo Operazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-157">Per questo esempio, selezionare Imballaggio.</span><span class="sxs-lookup"><span data-stu-id="731ff-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="731ff-158">Nel campo Tempo di esecuzione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="731ff-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="731ff-159">Per questo esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="731ff-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="731ff-160">Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-161">Per questo esempio, selezionare Std.</span><span class="sxs-lookup"><span data-stu-id="731ff-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="731ff-162">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="731ff-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="731ff-163">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="731ff-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="731ff-164">Per questo esempio, selezionare Imballaggio.</span><span class="sxs-lookup"><span data-stu-id="731ff-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="731ff-165">Fare clic sulla scheda Tempi.</span><span class="sxs-lookup"><span data-stu-id="731ff-165">Click the Times tab.</span></span>
16. <span data-ttu-id="731ff-166">Nel campo Tempo di attrezzaggio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="731ff-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="731ff-167">Per questo esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="731ff-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="731ff-168">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="731ff-169">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="731ff-169">Click Approve.</span></span>
19. <span data-ttu-id="731ff-170">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="731ff-170">Click OK.</span></span>
20. <span data-ttu-id="731ff-171">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="731ff-172">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="731ff-172">Click Activate.</span></span>
22. <span data-ttu-id="731ff-173">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="731ff-173">Close the page.</span></span>
23. <span data-ttu-id="731ff-174">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="731ff-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="731ff-175">Abilitare il consumo automatico del tempo di attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="731ff-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="731ff-176">Passare a Controllo produzione > Impostazioni > Cicli di lavorazione > Gruppi di cicli di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="731ff-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="731ff-177">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="731ff-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="731ff-178">Nell'elenco selezionare Std.</span><span class="sxs-lookup"><span data-stu-id="731ff-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="731ff-179">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="731ff-179">Click Edit.</span></span>
4. <span data-ttu-id="731ff-180">Selezionare Sì nel campo Tempo di attrezzaggio.</span><span class="sxs-lookup"><span data-stu-id="731ff-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="731ff-181">Il tempo di impostazione spesso fa parte del prezzo calcolato per un articolo.</span><span class="sxs-lookup"><span data-stu-id="731ff-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="731ff-182">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="731ff-182">Click Save.</span></span>
6. <span data-ttu-id="731ff-183">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="731ff-183">Close the page.</span></span>


