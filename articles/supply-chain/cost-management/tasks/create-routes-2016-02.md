--- 
title: Creare cicli di lavorazione (solo febbraio 2016)
description: "Questa attività consente di creare i cicli di lavorazione produzione per un prodotto finito e un prodotto semilavorato."
author: BibiSp
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1c2801af8201865f5ae9233c9729a4d59ef84bcd
ms.openlocfilehash: 2df913543d89a502aecfe7e2fe61265a8a1a121c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-routes-february-2016-only"></a><span data-ttu-id="d5e1b-103">Creare cicli di lavorazione (solo febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="d5e1b-103">Create routes (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d5e1b-104">Questa attività consente di creare i cicli di lavorazione produzione per un prodotto finito e un prodotto semilavorato.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-104">This task focuses on creating the production routes for a finished product and and a semi-finished product.</span></span> <span data-ttu-id="d5e1b-105">Corrisponde alla quinta attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="d5e1b-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="d5e1b-107">Creare un ciclo di lavorazione per un prodotto semilavorato</span><span class="sxs-lookup"><span data-stu-id="d5e1b-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="d5e1b-108">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="d5e1b-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d5e1b-110">Selezionare il numero dell'articolo BOM_2.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="d5e1b-111">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="d5e1b-112">Fare clic su Ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-112">Click Route.</span></span>
5. <span data-ttu-id="d5e1b-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-113">Click New.</span></span>
6. <span data-ttu-id="d5e1b-114">Fare clic su Ciclo di lavorazione e versione del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-114">Click Route and route version.</span></span>
7. <span data-ttu-id="d5e1b-115">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="d5e1b-116">Per questo esempio, digitare ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="d5e1b-117">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-118">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="d5e1b-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-119">Click OK.</span></span>
10. <span data-ttu-id="d5e1b-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-120">Click New.</span></span>
11. <span data-ttu-id="d5e1b-121">Nel campo Operazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-122">Per questo esempio, selezionare Assembly.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="d5e1b-123">Nel campo Tempo di esecuzione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="d5e1b-124">Ad esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-124">For example, type 1.</span></span> <span data-ttu-id="d5e1b-125">Il tempo di esecuzione spesso fa parte del prezzo calcolato per un articolo.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="d5e1b-126">Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-127">Per questo esempio, selezionare Std.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="d5e1b-128">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="d5e1b-129">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-130">Per questo esempio, selezionare Assembly.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="d5e1b-131">Fare clic sulla scheda Tempi.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-131">Click the Times tab.</span></span>
17. <span data-ttu-id="d5e1b-132">Nel campo Tempo di attrezzaggio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="d5e1b-133">Per questo esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-133">For this example, type 1.</span></span> <span data-ttu-id="d5e1b-134">Il tempo di impostazione spesso fa parte del prezzo calcolato per un articolo.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="d5e1b-135">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="d5e1b-136">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-136">Click Approve.</span></span>
20. <span data-ttu-id="d5e1b-137">Selezionare Sì nel campo Approvare anche il ciclo di lavorazione? .</span><span class="sxs-lookup"><span data-stu-id="d5e1b-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="d5e1b-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-138">Click OK.</span></span>
22. <span data-ttu-id="d5e1b-139">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="d5e1b-140">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-140">Click Activate.</span></span>
24. <span data-ttu-id="d5e1b-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-141">Close the page.</span></span>
25. <span data-ttu-id="d5e1b-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="d5e1b-143">Creare un ciclo di lavorazione per un prodotto finito</span><span class="sxs-lookup"><span data-stu-id="d5e1b-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="d5e1b-144">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d5e1b-145">Selezionare il numero dell'articolo BOM_1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="d5e1b-146">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="d5e1b-147">Fare clic su Ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-147">Click Route.</span></span>
4. <span data-ttu-id="d5e1b-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-148">Click New.</span></span>
5. <span data-ttu-id="d5e1b-149">Fare clic su Ciclo di lavorazione e versione del ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-149">Click Route and route version.</span></span>
6. <span data-ttu-id="d5e1b-150">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="d5e1b-151">Per questo esempio, digitare ROUTE_1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="d5e1b-152">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-153">Per questo esempio, immettere o selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="d5e1b-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-154">Click OK.</span></span>
9. <span data-ttu-id="d5e1b-155">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-155">Click New.</span></span>
10. <span data-ttu-id="d5e1b-156">Nel campo Operazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-157">Per questo esempio, selezionare Imballaggio.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="d5e1b-158">Nel campo Tempo di esecuzione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="d5e1b-159">Per questo esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="d5e1b-160">Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-161">Per questo esempio, selezionare Std.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="d5e1b-162">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="d5e1b-163">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="d5e1b-164">Per questo esempio, selezionare Imballaggio.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="d5e1b-165">Fare clic sulla scheda Tempi.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-165">Click the Times tab.</span></span>
16. <span data-ttu-id="d5e1b-166">Nel campo Tempo di attrezzaggio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="d5e1b-167">Per questo esempio, digitare 1.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="d5e1b-168">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="d5e1b-169">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-169">Click Approve.</span></span>
19. <span data-ttu-id="d5e1b-170">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-170">Click OK.</span></span>
20. <span data-ttu-id="d5e1b-171">Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="d5e1b-172">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-172">Click Activate.</span></span>
22. <span data-ttu-id="d5e1b-173">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-173">Close the page.</span></span>
23. <span data-ttu-id="d5e1b-174">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="d5e1b-175">Abilitare il consumo automatico del tempo di attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="d5e1b-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="d5e1b-176">Passare a Controllo produzione > Impostazioni > Cicli di lavorazione > Gruppi di cicli di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="d5e1b-177">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d5e1b-178">Nell'elenco selezionare Std.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="d5e1b-179">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-179">Click Edit.</span></span>
4. <span data-ttu-id="d5e1b-180">Selezionare Sì nel campo Tempo di attrezzaggio.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="d5e1b-181">Il tempo di impostazione spesso fa parte del prezzo calcolato per un articolo.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="d5e1b-182">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-182">Click Save.</span></span>
6. <span data-ttu-id="d5e1b-183">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d5e1b-183">Close the page.</span></span>


