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
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 506ca3aac7ad271ca7472f3b74627e94d97a74ee
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="reduction-keys"></a><span data-ttu-id="61980-105">Chiavi di riduzione</span><span class="sxs-lookup"><span data-stu-id="61980-105">Reduction keys</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="61980-106">Questo articolo fornisce esempi che illustrano come impostare una chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="61980-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="61980-107">Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna.</span><span class="sxs-lookup"><span data-stu-id="61980-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="61980-108">È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione.</span><span class="sxs-lookup"><span data-stu-id="61980-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="61980-109">Esempio 1: Principio di riduzione previsioni di Percentuale - chiave di riduzione</span><span class="sxs-lookup"><span data-stu-id="61980-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="61980-110">In questo esempio viene illustrato come una chiave di riduzione riduce i requisiti di previsione della domanda in base alle percentuali e ai periodi definiti dalla chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="61980-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1.  <span data-ttu-id="61980-111">Nella pagina **Chiavi di riduzione** impostare le seguenti righe.</span><span class="sxs-lookup"><span data-stu-id="61980-111">On the **Reduction keys** page, set up the following lines.</span></span>
    | <span data-ttu-id="61980-112">Cambia</span><span class="sxs-lookup"><span data-stu-id="61980-112">Change</span></span> | <span data-ttu-id="61980-113">Unità</span><span class="sxs-lookup"><span data-stu-id="61980-113">Unit</span></span>  | <span data-ttu-id="61980-114">Percentuale</span><span class="sxs-lookup"><span data-stu-id="61980-114">Percent</span></span> |
    |--------|-------|---------|
    | <span data-ttu-id="61980-115">1</span><span class="sxs-lookup"><span data-stu-id="61980-115">1</span></span>      | <span data-ttu-id="61980-116">Mese</span><span class="sxs-lookup"><span data-stu-id="61980-116">Month</span></span> | <span data-ttu-id="61980-117">100</span><span class="sxs-lookup"><span data-stu-id="61980-117">100</span></span>     |
    | <span data-ttu-id="61980-118">2</span><span class="sxs-lookup"><span data-stu-id="61980-118">2</span></span>      | <span data-ttu-id="61980-119">Mese</span><span class="sxs-lookup"><span data-stu-id="61980-119">Month</span></span> | <span data-ttu-id="61980-120">75</span><span class="sxs-lookup"><span data-stu-id="61980-120">75</span></span>      |
    | <span data-ttu-id="61980-121">3</span><span class="sxs-lookup"><span data-stu-id="61980-121">3</span></span>      | <span data-ttu-id="61980-122">Mese</span><span class="sxs-lookup"><span data-stu-id="61980-122">Month</span></span> | <span data-ttu-id="61980-123">50</span><span class="sxs-lookup"><span data-stu-id="61980-123">50</span></span>      |
    | <span data-ttu-id="61980-124">4</span><span class="sxs-lookup"><span data-stu-id="61980-124">4</span></span>      | <span data-ttu-id="61980-125">Mese</span><span class="sxs-lookup"><span data-stu-id="61980-125">Month</span></span> | <span data-ttu-id="61980-126">25</span><span class="sxs-lookup"><span data-stu-id="61980-126">25</span></span>      |

2.  <span data-ttu-id="61980-127">Collegare la chiave di riduzione al gruppo di copertura dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="61980-127">Link the reduction key to the item's coverage group.</span></span>
3.  <span data-ttu-id="61980-128">Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Percentuale - chiave di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="61980-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4.  <span data-ttu-id="61980-129">Creare una previsione della domanda di 1.000 pezzi al mese.</span><span class="sxs-lookup"><span data-stu-id="61980-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="61980-130">Se si esegue una programmazione previsionale il 1° gennaio, i requisiti di previsione della domanda vengono consumati in base alle percentuali definite alla pagina **Chiavi di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="61980-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="61980-131">Vengono trasferite al piano generale le quantità di requisiti che seguono.</span><span class="sxs-lookup"><span data-stu-id="61980-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="61980-132">Mese</span><span class="sxs-lookup"><span data-stu-id="61980-132">Month</span></span>                | <span data-ttu-id="61980-133">Numero di pezzi richiesti</span><span class="sxs-lookup"><span data-stu-id="61980-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="61980-134">gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-134">January</span></span>              | <span data-ttu-id="61980-135">0</span><span class="sxs-lookup"><span data-stu-id="61980-135">0</span></span>                         |
| <span data-ttu-id="61980-136">febbraio</span><span class="sxs-lookup"><span data-stu-id="61980-136">February</span></span>             | <span data-ttu-id="61980-137">250</span><span class="sxs-lookup"><span data-stu-id="61980-137">250</span></span>                       |
| <span data-ttu-id="61980-138">marzo</span><span class="sxs-lookup"><span data-stu-id="61980-138">March</span></span>                | <span data-ttu-id="61980-139">500</span><span class="sxs-lookup"><span data-stu-id="61980-139">500</span></span>                       |
| <span data-ttu-id="61980-140">aprile</span><span class="sxs-lookup"><span data-stu-id="61980-140">April</span></span>                | <span data-ttu-id="61980-141">750</span><span class="sxs-lookup"><span data-stu-id="61980-141">750</span></span>                       |
| <span data-ttu-id="61980-142">Da maggio a dicembre</span><span class="sxs-lookup"><span data-stu-id="61980-142">May through December</span></span> | <span data-ttu-id="61980-143">1.000</span><span class="sxs-lookup"><span data-stu-id="61980-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="61980-144">Esempio 2: Principio di riduzione previsioni di Transazioni - chiave di riduzione</span><span class="sxs-lookup"><span data-stu-id="61980-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="61980-145">In questo esempio viene illustrato come gli ordini effettivi, che si verificano durante i periodi definiti dalla chiave di riduzione, riducono i requisiti di previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="61980-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="61980-146">Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Transazioni - chiave di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="61980-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="61980-147">Al 1° gennaio sono presenti gli ordini cliente che seguono.</span><span class="sxs-lookup"><span data-stu-id="61980-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="61980-148">Mese</span><span class="sxs-lookup"><span data-stu-id="61980-148">Month</span></span>    | <span data-ttu-id="61980-149">Numero di pezzi ordinati</span><span class="sxs-lookup"><span data-stu-id="61980-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="61980-150">gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-150">January</span></span>  | <span data-ttu-id="61980-151">956</span><span class="sxs-lookup"><span data-stu-id="61980-151">956</span></span>                      |
| <span data-ttu-id="61980-152">febbraio</span><span class="sxs-lookup"><span data-stu-id="61980-152">February</span></span> | <span data-ttu-id="61980-153">1.176</span><span class="sxs-lookup"><span data-stu-id="61980-153">1,176</span></span>                    |
| <span data-ttu-id="61980-154">marzo</span><span class="sxs-lookup"><span data-stu-id="61980-154">March</span></span>    | <span data-ttu-id="61980-155">451</span><span class="sxs-lookup"><span data-stu-id="61980-155">451</span></span>                      |
| <span data-ttu-id="61980-156">aprile</span><span class="sxs-lookup"><span data-stu-id="61980-156">April</span></span>    | <span data-ttu-id="61980-157">119</span><span class="sxs-lookup"><span data-stu-id="61980-157">119</span></span>                      |

<span data-ttu-id="61980-158">Utilizzando la stessa previsione della domanda di 1.000 pezzi al mese, vengono trasferite al piano generale le quantità indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="61980-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="61980-159">Mese</span><span class="sxs-lookup"><span data-stu-id="61980-159">Month</span></span>                | <span data-ttu-id="61980-160">Numero di pezzi richiesti</span><span class="sxs-lookup"><span data-stu-id="61980-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="61980-161">gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-161">January</span></span>              | <span data-ttu-id="61980-162">44</span><span class="sxs-lookup"><span data-stu-id="61980-162">44</span></span>                        |
| <span data-ttu-id="61980-163">febbraio</span><span class="sxs-lookup"><span data-stu-id="61980-163">February</span></span>             | <span data-ttu-id="61980-164">0</span><span class="sxs-lookup"><span data-stu-id="61980-164">0</span></span>                         |
| <span data-ttu-id="61980-165">marzo</span><span class="sxs-lookup"><span data-stu-id="61980-165">March</span></span>                | <span data-ttu-id="61980-166">549</span><span class="sxs-lookup"><span data-stu-id="61980-166">549</span></span>                       |
| <span data-ttu-id="61980-167">aprile</span><span class="sxs-lookup"><span data-stu-id="61980-167">April</span></span>                | <span data-ttu-id="61980-168">881</span><span class="sxs-lookup"><span data-stu-id="61980-168">881</span></span>                       |
| <span data-ttu-id="61980-169">Da maggio a dicembre</span><span class="sxs-lookup"><span data-stu-id="61980-169">May through December</span></span> | <span data-ttu-id="61980-170">1.000</span><span class="sxs-lookup"><span data-stu-id="61980-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="61980-171">Esempio 3: Principio di riduzione previsioni di Transazioni - periodo dinamico</span><span class="sxs-lookup"><span data-stu-id="61980-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="61980-172">Nella maggior parte dei casi i sistemi vengono impostati in modo che le transazioni riducano la previsione della domanda entro periodi specifici di previsione: settimane, mesi, ecc.</span><span class="sxs-lookup"><span data-stu-id="61980-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="61980-173">I periodi vengono sono definiti nella chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="61980-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="61980-174">Tuttavia, il tempo trascorso tra due righe di previsione della domanda può anche *implicare* un periodo.</span><span class="sxs-lookup"><span data-stu-id="61980-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1.  <span data-ttu-id="61980-175">Creare una previsione della domanda per le seguenti date e quantità.</span><span class="sxs-lookup"><span data-stu-id="61980-175">Create a demand forecast for the following dates and quantities.</span></span>
    | <span data-ttu-id="61980-176">Data</span><span class="sxs-lookup"><span data-stu-id="61980-176">Date</span></span>       | <span data-ttu-id="61980-177">Previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="61980-177">Demand forecast</span></span> |
    |------------|-----------------|
    | <span data-ttu-id="61980-178">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-178">January 1</span></span>  | <span data-ttu-id="61980-179">1.000</span><span class="sxs-lookup"><span data-stu-id="61980-179">1,000</span></span>           |
    | <span data-ttu-id="61980-180">5 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-180">January 5</span></span>  | <span data-ttu-id="61980-181">500</span><span class="sxs-lookup"><span data-stu-id="61980-181">500</span></span>             |
    | <span data-ttu-id="61980-182">12 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-182">January 12</span></span> | <span data-ttu-id="61980-183">1.000</span><span class="sxs-lookup"><span data-stu-id="61980-183">1,000</span></span>           |

    <span data-ttu-id="61980-184">Nella previsione non è presente un periodo chiaro tra le date di previsione: tra le prime e le seconde date vi è un intervallo di quattro giorni e tra la seconde e terze date vi è un intervallo di sette giorni.</span><span class="sxs-lookup"><span data-stu-id="61980-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="61980-185">I vari intervalli sono i periodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="61980-185">These various spans are the dynamic periods.</span></span>
2.  <span data-ttu-id="61980-186">Creare righe dell'ordine cliente come segue</span><span class="sxs-lookup"><span data-stu-id="61980-186">Create sales order lines as follows.</span></span>
    | <span data-ttu-id="61980-187">Data</span><span class="sxs-lookup"><span data-stu-id="61980-187">Date</span></span>                             | <span data-ttu-id="61980-188">Quantità ordine cliente</span><span class="sxs-lookup"><span data-stu-id="61980-188">Sales order quantity</span></span> |
    |----------------------------------|----------------------|
    | <span data-ttu-id="61980-189">15 dicembre dell'anno precedente</span><span class="sxs-lookup"><span data-stu-id="61980-189">December 15 in the previous year</span></span> | <span data-ttu-id="61980-190">500</span><span class="sxs-lookup"><span data-stu-id="61980-190">500</span></span>                  |
    | <span data-ttu-id="61980-191">3 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-191">January 3</span></span>                        | <span data-ttu-id="61980-192">100</span><span class="sxs-lookup"><span data-stu-id="61980-192">100</span></span>                  |
    | <span data-ttu-id="61980-193">10 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-193">January 10</span></span>                       | <span data-ttu-id="61980-194">200</span><span class="sxs-lookup"><span data-stu-id="61980-194">200</span></span>                  |

<span data-ttu-id="61980-195">La previsione verrà ridotta come segue:</span><span class="sxs-lookup"><span data-stu-id="61980-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="61980-196">Il primo ordine cliente non rientra in alcun periodo, pertanto non ridurrà alcuna previsione.</span><span class="sxs-lookup"><span data-stu-id="61980-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="61980-197">Il secondo ordine cliente è compreso tra il 1° gennaio e il 5 gennaio, pertanto ridurrà la previsione per il 1° gennaio di 100.</span><span class="sxs-lookup"><span data-stu-id="61980-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="61980-198">Il terzo ordine cliente è compreso tra il 5 gennaio e il 12 gennaio, pertanto ridurrà la previsione per il 5 gennaio di 200.</span><span class="sxs-lookup"><span data-stu-id="61980-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="61980-199">Il seguente ordine pianificato verrà creato per soddisfare la previsione.</span><span class="sxs-lookup"><span data-stu-id="61980-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="61980-200">Data di previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="61980-200">Demand forecast date</span></span> | <span data-ttu-id="61980-201">Quantità ridotta</span><span class="sxs-lookup"><span data-stu-id="61980-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="61980-202">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-202">January 1</span></span>            | <span data-ttu-id="61980-203">900</span><span class="sxs-lookup"><span data-stu-id="61980-203">900</span></span>              |
| <span data-ttu-id="61980-204">5 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-204">January 5</span></span>            | <span data-ttu-id="61980-205">300</span><span class="sxs-lookup"><span data-stu-id="61980-205">300</span></span>              |
| <span data-ttu-id="61980-206">12 gennaio</span><span class="sxs-lookup"><span data-stu-id="61980-206">January 12</span></span>           | <span data-ttu-id="61980-207">1.000</span><span class="sxs-lookup"><span data-stu-id="61980-207">1,000</span></span>            |

<span data-ttu-id="61980-208">Questo campo è un riepilogo della riduzione **Transazioni - periodo dinamico**:</span><span class="sxs-lookup"><span data-stu-id="61980-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="61980-209">I requisiti di previsione vengono ridotti in base alle transazioni di ordini effettive effettuate durante il periodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="61980-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="61980-210">Il periodo dinamico copre le date di previsione correnti e termina all'inizio della previsione successiva.</span><span class="sxs-lookup"><span data-stu-id="61980-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="61980-211">Per questo metodo non viene utilizzata o richiesta alcuna chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="61980-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="61980-212">Quando questa opzione viene utilizzata, si verifica il seguente comportamento :</span><span class="sxs-lookup"><span data-stu-id="61980-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="61980-213">Se la previsione viene ridotta completamente, i requisiti per la previsione corrente diventano 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="61980-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="61980-214">Se non vi è alcuna previsione futura, vengono ridotti i requisiti di previsione dall'ultima previsione immessa.</span><span class="sxs-lookup"><span data-stu-id="61980-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="61980-215">Gli intervalli temporali vengono inclusi nel calcolo della riduzione previsionale.</span><span class="sxs-lookup"><span data-stu-id="61980-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="61980-216">I giorni di positività vengono inclusi nel calcolo della riduzione previsionale.</span><span class="sxs-lookup"><span data-stu-id="61980-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="61980-217">Se le transazioni di ordini effettivi superano i fabbisogni previsti, le transazioni rimanenti non vengono inoltrate al periodo previsionale successivo.</span><span class="sxs-lookup"><span data-stu-id="61980-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="see-also"></a><span data-ttu-id="61980-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61980-218">See also</span></span>
--------

[<span data-ttu-id="61980-219">Piani generali</span><span class="sxs-lookup"><span data-stu-id="61980-219">Master plans</span></span>](master-plans.md)




