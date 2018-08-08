---
title: Chiavi di riduzione
description: "Questo articolo fornisce esempi che illustrano come impostare una chiave di riduzione. Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna. È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 3e62431a1fdbeb81dda68297f034ee00adece079
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="reduction-keys"></a><span data-ttu-id="69aba-105">Chiavi di riduzione</span><span class="sxs-lookup"><span data-stu-id="69aba-105">Reduction keys</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69aba-106">Questo articolo fornisce esempi che illustrano come impostare una chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="69aba-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="69aba-107">Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna.</span><span class="sxs-lookup"><span data-stu-id="69aba-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="69aba-108">È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione.</span><span class="sxs-lookup"><span data-stu-id="69aba-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="69aba-109">Esempio 1: Principio di riduzione previsioni di Percentuale - chiave di riduzione</span><span class="sxs-lookup"><span data-stu-id="69aba-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="69aba-110">In questo esempio viene illustrato come una chiave di riduzione riduce i requisiti di previsione della domanda in base alle percentuali e ai periodi definiti dalla chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="69aba-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1. <span data-ttu-id="69aba-111">Nella pagina **Chiavi di riduzione** impostare le seguenti righe.</span><span class="sxs-lookup"><span data-stu-id="69aba-111">On the **Reduction keys** page, set up the following lines.</span></span>

   | <span data-ttu-id="69aba-112">Cambia</span><span class="sxs-lookup"><span data-stu-id="69aba-112">Change</span></span> | <span data-ttu-id="69aba-113">Unità</span><span class="sxs-lookup"><span data-stu-id="69aba-113">Unit</span></span>  | <span data-ttu-id="69aba-114">Percentuale</span><span class="sxs-lookup"><span data-stu-id="69aba-114">Percent</span></span> |
   |--------|-------|---------|
   |   <span data-ttu-id="69aba-115">1</span><span class="sxs-lookup"><span data-stu-id="69aba-115">1</span></span>    | <span data-ttu-id="69aba-116">Mese</span><span class="sxs-lookup"><span data-stu-id="69aba-116">Month</span></span> |   <span data-ttu-id="69aba-117">100</span><span class="sxs-lookup"><span data-stu-id="69aba-117">100</span></span>   |
   |   <span data-ttu-id="69aba-118">2</span><span class="sxs-lookup"><span data-stu-id="69aba-118">2</span></span>    | <span data-ttu-id="69aba-119">Mese</span><span class="sxs-lookup"><span data-stu-id="69aba-119">Month</span></span> |   <span data-ttu-id="69aba-120">75</span><span class="sxs-lookup"><span data-stu-id="69aba-120">75</span></span>    |
   |   <span data-ttu-id="69aba-121">3</span><span class="sxs-lookup"><span data-stu-id="69aba-121">3</span></span>    | <span data-ttu-id="69aba-122">Mese</span><span class="sxs-lookup"><span data-stu-id="69aba-122">Month</span></span> |   <span data-ttu-id="69aba-123">50</span><span class="sxs-lookup"><span data-stu-id="69aba-123">50</span></span>    |
   |   <span data-ttu-id="69aba-124">4</span><span class="sxs-lookup"><span data-stu-id="69aba-124">4</span></span>    | <span data-ttu-id="69aba-125">Mese</span><span class="sxs-lookup"><span data-stu-id="69aba-125">Month</span></span> |   <span data-ttu-id="69aba-126">25</span><span class="sxs-lookup"><span data-stu-id="69aba-126">25</span></span>    |


2. <span data-ttu-id="69aba-127">Collegare la chiave di riduzione al gruppo di copertura dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="69aba-127">Link the reduction key to the item's coverage group.</span></span>
3. <span data-ttu-id="69aba-128">Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Percentuale - chiave di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="69aba-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4. <span data-ttu-id="69aba-129">Creare una previsione della domanda di 1.000 pezzi al mese.</span><span class="sxs-lookup"><span data-stu-id="69aba-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="69aba-130">Se si esegue una programmazione previsionale il 1° gennaio, i requisiti di previsione della domanda vengono consumati in base alle percentuali definite alla pagina **Chiavi di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="69aba-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="69aba-131">Vengono trasferite al piano generale le quantità di requisiti che seguono.</span><span class="sxs-lookup"><span data-stu-id="69aba-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="69aba-132">Mese</span><span class="sxs-lookup"><span data-stu-id="69aba-132">Month</span></span>                | <span data-ttu-id="69aba-133">Numero di pezzi richiesti</span><span class="sxs-lookup"><span data-stu-id="69aba-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="69aba-134">gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-134">January</span></span>              | <span data-ttu-id="69aba-135">0</span><span class="sxs-lookup"><span data-stu-id="69aba-135">0</span></span>                         |
| <span data-ttu-id="69aba-136">febbraio</span><span class="sxs-lookup"><span data-stu-id="69aba-136">February</span></span>             | <span data-ttu-id="69aba-137">250</span><span class="sxs-lookup"><span data-stu-id="69aba-137">250</span></span>                       |
| <span data-ttu-id="69aba-138">marzo</span><span class="sxs-lookup"><span data-stu-id="69aba-138">March</span></span>                | <span data-ttu-id="69aba-139">500</span><span class="sxs-lookup"><span data-stu-id="69aba-139">500</span></span>                       |
| <span data-ttu-id="69aba-140">aprile</span><span class="sxs-lookup"><span data-stu-id="69aba-140">April</span></span>                | <span data-ttu-id="69aba-141">750</span><span class="sxs-lookup"><span data-stu-id="69aba-141">750</span></span>                       |
| <span data-ttu-id="69aba-142">Da maggio a dicembre</span><span class="sxs-lookup"><span data-stu-id="69aba-142">May through December</span></span> | <span data-ttu-id="69aba-143">1.000</span><span class="sxs-lookup"><span data-stu-id="69aba-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="69aba-144">Esempio 2: Principio di riduzione previsioni di Transazioni - chiave di riduzione</span><span class="sxs-lookup"><span data-stu-id="69aba-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="69aba-145">In questo esempio viene illustrato come gli ordini effettivi, che si verificano durante i periodi definiti dalla chiave di riduzione, riducono i requisiti di previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="69aba-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="69aba-146">Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Transazioni - chiave di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="69aba-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="69aba-147">Al 1° gennaio sono presenti gli ordini cliente che seguono.</span><span class="sxs-lookup"><span data-stu-id="69aba-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="69aba-148">Mese</span><span class="sxs-lookup"><span data-stu-id="69aba-148">Month</span></span>    | <span data-ttu-id="69aba-149">Numero di pezzi ordinati</span><span class="sxs-lookup"><span data-stu-id="69aba-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="69aba-150">gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-150">January</span></span>  | <span data-ttu-id="69aba-151">956</span><span class="sxs-lookup"><span data-stu-id="69aba-151">956</span></span>                      |
| <span data-ttu-id="69aba-152">febbraio</span><span class="sxs-lookup"><span data-stu-id="69aba-152">February</span></span> | <span data-ttu-id="69aba-153">1.176</span><span class="sxs-lookup"><span data-stu-id="69aba-153">1,176</span></span>                    |
| <span data-ttu-id="69aba-154">marzo</span><span class="sxs-lookup"><span data-stu-id="69aba-154">March</span></span>    | <span data-ttu-id="69aba-155">451</span><span class="sxs-lookup"><span data-stu-id="69aba-155">451</span></span>                      |
| <span data-ttu-id="69aba-156">aprile</span><span class="sxs-lookup"><span data-stu-id="69aba-156">April</span></span>    | <span data-ttu-id="69aba-157">119</span><span class="sxs-lookup"><span data-stu-id="69aba-157">119</span></span>                      |

<span data-ttu-id="69aba-158">Utilizzando la stessa previsione della domanda di 1.000 pezzi al mese, vengono trasferite al piano generale le quantità indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="69aba-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="69aba-159">Mese</span><span class="sxs-lookup"><span data-stu-id="69aba-159">Month</span></span>                | <span data-ttu-id="69aba-160">Numero di pezzi richiesti</span><span class="sxs-lookup"><span data-stu-id="69aba-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="69aba-161">gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-161">January</span></span>              | <span data-ttu-id="69aba-162">44</span><span class="sxs-lookup"><span data-stu-id="69aba-162">44</span></span>                        |
| <span data-ttu-id="69aba-163">febbraio</span><span class="sxs-lookup"><span data-stu-id="69aba-163">February</span></span>             | <span data-ttu-id="69aba-164">0</span><span class="sxs-lookup"><span data-stu-id="69aba-164">0</span></span>                         |
| <span data-ttu-id="69aba-165">marzo</span><span class="sxs-lookup"><span data-stu-id="69aba-165">March</span></span>                | <span data-ttu-id="69aba-166">549</span><span class="sxs-lookup"><span data-stu-id="69aba-166">549</span></span>                       |
| <span data-ttu-id="69aba-167">aprile</span><span class="sxs-lookup"><span data-stu-id="69aba-167">April</span></span>                | <span data-ttu-id="69aba-168">881</span><span class="sxs-lookup"><span data-stu-id="69aba-168">881</span></span>                       |
| <span data-ttu-id="69aba-169">Da maggio a dicembre</span><span class="sxs-lookup"><span data-stu-id="69aba-169">May through December</span></span> | <span data-ttu-id="69aba-170">1.000</span><span class="sxs-lookup"><span data-stu-id="69aba-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="69aba-171">Esempio 3: Principio di riduzione previsioni di Transazioni - periodo dinamico</span><span class="sxs-lookup"><span data-stu-id="69aba-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="69aba-172">Nella maggior parte dei casi i sistemi vengono impostati in modo che le transazioni riducano la previsione della domanda entro periodi specifici di previsione: settimane, mesi, ecc.</span><span class="sxs-lookup"><span data-stu-id="69aba-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="69aba-173">I periodi vengono sono definiti nella chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="69aba-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="69aba-174">Tuttavia, il tempo trascorso tra due righe di previsione della domanda può anche *implicare* un periodo.</span><span class="sxs-lookup"><span data-stu-id="69aba-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1. <span data-ttu-id="69aba-175">Creare una previsione della domanda per le seguenti date e quantità.</span><span class="sxs-lookup"><span data-stu-id="69aba-175">Create a demand forecast for the following dates and quantities.</span></span>

   | <span data-ttu-id="69aba-176">Data</span><span class="sxs-lookup"><span data-stu-id="69aba-176">Date</span></span>       | <span data-ttu-id="69aba-177">Previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="69aba-177">Demand forecast</span></span> |
   |------------|-----------------|
   | <span data-ttu-id="69aba-178">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-178">January 1</span></span>  | <span data-ttu-id="69aba-179">1.000</span><span class="sxs-lookup"><span data-stu-id="69aba-179">1,000</span></span>           |
   | <span data-ttu-id="69aba-180">5 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-180">January 5</span></span>  | <span data-ttu-id="69aba-181">500</span><span class="sxs-lookup"><span data-stu-id="69aba-181">500</span></span>             |
   | <span data-ttu-id="69aba-182">12 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-182">January 12</span></span> | <span data-ttu-id="69aba-183">1.000</span><span class="sxs-lookup"><span data-stu-id="69aba-183">1,000</span></span>           |

   <span data-ttu-id="69aba-184">Nella previsione non è presente un periodo chiaro tra le date di previsione: tra le prime e le seconde date vi è un intervallo di quattro giorni e tra la seconde e terze date vi è un intervallo di sette giorni.</span><span class="sxs-lookup"><span data-stu-id="69aba-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="69aba-185">I vari intervalli sono i periodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="69aba-185">These various spans are the dynamic periods.</span></span>
2. <span data-ttu-id="69aba-186">Creare righe dell'ordine cliente come segue</span><span class="sxs-lookup"><span data-stu-id="69aba-186">Create sales order lines as follows.</span></span>
   | <span data-ttu-id="69aba-187">Data</span><span class="sxs-lookup"><span data-stu-id="69aba-187">Date</span></span>                             | <span data-ttu-id="69aba-188">Quantità ordine cliente</span><span class="sxs-lookup"><span data-stu-id="69aba-188">Sales order quantity</span></span> |
   |----------------------------------|----------------------|
   | <span data-ttu-id="69aba-189">15 dicembre dell'anno precedente</span><span class="sxs-lookup"><span data-stu-id="69aba-189">December 15 in the previous year</span></span> | <span data-ttu-id="69aba-190">500</span><span class="sxs-lookup"><span data-stu-id="69aba-190">500</span></span>                  |
   | <span data-ttu-id="69aba-191">3 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-191">January 3</span></span>                        | <span data-ttu-id="69aba-192">100</span><span class="sxs-lookup"><span data-stu-id="69aba-192">100</span></span>                  |
   | <span data-ttu-id="69aba-193">10 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-193">January 10</span></span>                       | <span data-ttu-id="69aba-194">200</span><span class="sxs-lookup"><span data-stu-id="69aba-194">200</span></span>                  |

<span data-ttu-id="69aba-195">La previsione verrà ridotta come segue:</span><span class="sxs-lookup"><span data-stu-id="69aba-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="69aba-196">Il primo ordine cliente non rientra in alcun periodo, pertanto non ridurrà alcuna previsione.</span><span class="sxs-lookup"><span data-stu-id="69aba-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="69aba-197">Il secondo ordine cliente è compreso tra il 1° gennaio e il 5 gennaio, pertanto ridurrà la previsione per il 1° gennaio di 100.</span><span class="sxs-lookup"><span data-stu-id="69aba-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="69aba-198">Il terzo ordine cliente è compreso tra il 5 gennaio e il 12 gennaio, pertanto ridurrà la previsione per il 5 gennaio di 200.</span><span class="sxs-lookup"><span data-stu-id="69aba-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="69aba-199">Il seguente ordine pianificato verrà creato per soddisfare la previsione.</span><span class="sxs-lookup"><span data-stu-id="69aba-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="69aba-200">Data di previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="69aba-200">Demand forecast date</span></span> | <span data-ttu-id="69aba-201">Quantità ridotta</span><span class="sxs-lookup"><span data-stu-id="69aba-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="69aba-202">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-202">January 1</span></span>            | <span data-ttu-id="69aba-203">900</span><span class="sxs-lookup"><span data-stu-id="69aba-203">900</span></span>              |
| <span data-ttu-id="69aba-204">5 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-204">January 5</span></span>            | <span data-ttu-id="69aba-205">300</span><span class="sxs-lookup"><span data-stu-id="69aba-205">300</span></span>              |
| <span data-ttu-id="69aba-206">12 gennaio</span><span class="sxs-lookup"><span data-stu-id="69aba-206">January 12</span></span>           | <span data-ttu-id="69aba-207">1.000</span><span class="sxs-lookup"><span data-stu-id="69aba-207">1,000</span></span>            |

<span data-ttu-id="69aba-208">Questo campo è un riepilogo della riduzione **Transazioni - periodo dinamico**:</span><span class="sxs-lookup"><span data-stu-id="69aba-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="69aba-209">I requisiti di previsione vengono ridotti in base alle transazioni di ordini effettive effettuate durante il periodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="69aba-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="69aba-210">Il periodo dinamico copre le date di previsione correnti e termina all'inizio della previsione successiva.</span><span class="sxs-lookup"><span data-stu-id="69aba-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="69aba-211">Per questo metodo non viene utilizzata o richiesta alcuna chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="69aba-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="69aba-212">Quando questa opzione viene utilizzata, si verifica il seguente comportamento :</span><span class="sxs-lookup"><span data-stu-id="69aba-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="69aba-213">Se la previsione viene ridotta completamente, i requisiti per la previsione corrente diventano 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="69aba-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="69aba-214">Se non vi è alcuna previsione futura, vengono ridotti i requisiti di previsione dall'ultima previsione immessa.</span><span class="sxs-lookup"><span data-stu-id="69aba-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="69aba-215">Gli intervalli temporali vengono inclusi nel calcolo della riduzione previsionale.</span><span class="sxs-lookup"><span data-stu-id="69aba-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="69aba-216">I giorni di positività vengono inclusi nel calcolo della riduzione previsionale.</span><span class="sxs-lookup"><span data-stu-id="69aba-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="69aba-217">Se le transazioni di ordini effettivi superano i fabbisogni previsti, le transazioni rimanenti non vengono inoltrate al periodo previsionale successivo.</span><span class="sxs-lookup"><span data-stu-id="69aba-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="additional-resources"></a><span data-ttu-id="69aba-218">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="69aba-218">Additional resources</span></span>
--------

[<span data-ttu-id="69aba-219">Piani generali</span><span class="sxs-lookup"><span data-stu-id="69aba-219">Master plans</span></span>](master-plans.md)




