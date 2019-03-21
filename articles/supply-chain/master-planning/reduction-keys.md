---
title: Chiavi di riduzione
description: Questo articolo fornisce esempi che illustrano come impostare una chiave di riduzione. Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna. È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: 7457aca4ca4d5188bafb497d3052276cfc154ad1
ms.sourcegitcommit: 704d273485dcdc25c97a222bc0ef0695aad334d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "770918"
---
# <a name="reduction-keys"></a><span data-ttu-id="e1c33-105">Chiavi di riduzione</span><span class="sxs-lookup"><span data-stu-id="e1c33-105">Reduction keys</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1c33-106">Questo articolo fornisce esempi che illustrano come impostare una chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="e1c33-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="e1c33-107">Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna.</span><span class="sxs-lookup"><span data-stu-id="e1c33-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="e1c33-108">È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione.</span><span class="sxs-lookup"><span data-stu-id="e1c33-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="e1c33-109">Esempio 1: Principio di riduzione previsioni di Percentuale - chiave di riduzione</span><span class="sxs-lookup"><span data-stu-id="e1c33-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="e1c33-110">In questo esempio viene illustrato come una chiave di riduzione riduce i requisiti di previsione della domanda in base alle percentuali e ai periodi definiti dalla chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="e1c33-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1. <span data-ttu-id="e1c33-111">Nella pagina **Chiavi di riduzione** impostare le seguenti righe.</span><span class="sxs-lookup"><span data-stu-id="e1c33-111">On the **Reduction keys** page, set up the following lines.</span></span>

   | <span data-ttu-id="e1c33-112">Cambia</span><span class="sxs-lookup"><span data-stu-id="e1c33-112">Change</span></span> | <span data-ttu-id="e1c33-113">Unità</span><span class="sxs-lookup"><span data-stu-id="e1c33-113">Unit</span></span>  | <span data-ttu-id="e1c33-114">Percentuale</span><span class="sxs-lookup"><span data-stu-id="e1c33-114">Percent</span></span> |
   |--------|-------|---------|
   |   <span data-ttu-id="e1c33-115">1</span><span class="sxs-lookup"><span data-stu-id="e1c33-115">1</span></span>    | <span data-ttu-id="e1c33-116">Mese</span><span class="sxs-lookup"><span data-stu-id="e1c33-116">Month</span></span> |   <span data-ttu-id="e1c33-117">100</span><span class="sxs-lookup"><span data-stu-id="e1c33-117">100</span></span>   |
   |   <span data-ttu-id="e1c33-118">2</span><span class="sxs-lookup"><span data-stu-id="e1c33-118">2</span></span>    | <span data-ttu-id="e1c33-119">Mese</span><span class="sxs-lookup"><span data-stu-id="e1c33-119">Month</span></span> |   <span data-ttu-id="e1c33-120">75</span><span class="sxs-lookup"><span data-stu-id="e1c33-120">75</span></span>    |
   |   <span data-ttu-id="e1c33-121">3</span><span class="sxs-lookup"><span data-stu-id="e1c33-121">3</span></span>    | <span data-ttu-id="e1c33-122">Mese</span><span class="sxs-lookup"><span data-stu-id="e1c33-122">Month</span></span> |   <span data-ttu-id="e1c33-123">50</span><span class="sxs-lookup"><span data-stu-id="e1c33-123">50</span></span>    |
   |   <span data-ttu-id="e1c33-124">4</span><span class="sxs-lookup"><span data-stu-id="e1c33-124">4</span></span>    | <span data-ttu-id="e1c33-125">Mese</span><span class="sxs-lookup"><span data-stu-id="e1c33-125">Month</span></span> |   <span data-ttu-id="e1c33-126">25</span><span class="sxs-lookup"><span data-stu-id="e1c33-126">25</span></span>    |


2. <span data-ttu-id="e1c33-127">Collegare la chiave di riduzione al gruppo di copertura dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="e1c33-127">Link the reduction key to the item's coverage group.</span></span>
3. <span data-ttu-id="e1c33-128">Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Percentuale - chiave di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="e1c33-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4. <span data-ttu-id="e1c33-129">Creare una previsione della domanda di 1.000 pezzi al mese.</span><span class="sxs-lookup"><span data-stu-id="e1c33-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="e1c33-130">Se si esegue una programmazione previsionale il 1° gennaio, i requisiti di previsione della domanda vengono consumati in base alle percentuali definite alla pagina **Chiavi di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="e1c33-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="e1c33-131">Vengono trasferite al piano generale le quantità di requisiti che seguono.</span><span class="sxs-lookup"><span data-stu-id="e1c33-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="e1c33-132">Mese</span><span class="sxs-lookup"><span data-stu-id="e1c33-132">Month</span></span>                | <span data-ttu-id="e1c33-133">Numero di pezzi richiesti</span><span class="sxs-lookup"><span data-stu-id="e1c33-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="e1c33-134">gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-134">January</span></span>              | <span data-ttu-id="e1c33-135">0</span><span class="sxs-lookup"><span data-stu-id="e1c33-135">0</span></span>                         |
| <span data-ttu-id="e1c33-136">febbraio</span><span class="sxs-lookup"><span data-stu-id="e1c33-136">February</span></span>             | <span data-ttu-id="e1c33-137">250</span><span class="sxs-lookup"><span data-stu-id="e1c33-137">250</span></span>                       |
| <span data-ttu-id="e1c33-138">marzo</span><span class="sxs-lookup"><span data-stu-id="e1c33-138">March</span></span>                | <span data-ttu-id="e1c33-139">500</span><span class="sxs-lookup"><span data-stu-id="e1c33-139">500</span></span>                       |
| <span data-ttu-id="e1c33-140">aprile</span><span class="sxs-lookup"><span data-stu-id="e1c33-140">April</span></span>                | <span data-ttu-id="e1c33-141">750</span><span class="sxs-lookup"><span data-stu-id="e1c33-141">750</span></span>                       |
| <span data-ttu-id="e1c33-142">Da maggio a dicembre</span><span class="sxs-lookup"><span data-stu-id="e1c33-142">May through December</span></span> | <span data-ttu-id="e1c33-143">1.000</span><span class="sxs-lookup"><span data-stu-id="e1c33-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="e1c33-144">Esempio 2: Principio di riduzione previsioni di Transazioni - chiave di riduzione</span><span class="sxs-lookup"><span data-stu-id="e1c33-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="e1c33-145">In questo esempio viene illustrato come gli ordini effettivi, che si verificano durante i periodi definiti dalla chiave di riduzione, riducono i requisiti di previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="e1c33-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="e1c33-146">Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Transazioni - chiave di riduzione**.</span><span class="sxs-lookup"><span data-stu-id="e1c33-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="e1c33-147">Al 1° gennaio sono presenti gli ordini cliente che seguono.</span><span class="sxs-lookup"><span data-stu-id="e1c33-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="e1c33-148">Mese</span><span class="sxs-lookup"><span data-stu-id="e1c33-148">Month</span></span>    | <span data-ttu-id="e1c33-149">Numero di pezzi ordinati</span><span class="sxs-lookup"><span data-stu-id="e1c33-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="e1c33-150">gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-150">January</span></span>  | <span data-ttu-id="e1c33-151">956</span><span class="sxs-lookup"><span data-stu-id="e1c33-151">956</span></span>                      |
| <span data-ttu-id="e1c33-152">febbraio</span><span class="sxs-lookup"><span data-stu-id="e1c33-152">February</span></span> | <span data-ttu-id="e1c33-153">1.176</span><span class="sxs-lookup"><span data-stu-id="e1c33-153">1,176</span></span>                    |
| <span data-ttu-id="e1c33-154">marzo</span><span class="sxs-lookup"><span data-stu-id="e1c33-154">March</span></span>    | <span data-ttu-id="e1c33-155">451</span><span class="sxs-lookup"><span data-stu-id="e1c33-155">451</span></span>                      |
| <span data-ttu-id="e1c33-156">aprile</span><span class="sxs-lookup"><span data-stu-id="e1c33-156">April</span></span>    | <span data-ttu-id="e1c33-157">119</span><span class="sxs-lookup"><span data-stu-id="e1c33-157">119</span></span>                      |

<span data-ttu-id="e1c33-158">Utilizzando la stessa previsione della domanda di 1.000 pezzi al mese, vengono trasferite al piano generale le quantità indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="e1c33-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="e1c33-159">Mese</span><span class="sxs-lookup"><span data-stu-id="e1c33-159">Month</span></span>                | <span data-ttu-id="e1c33-160">Numero di pezzi richiesti</span><span class="sxs-lookup"><span data-stu-id="e1c33-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="e1c33-161">gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-161">January</span></span>              | <span data-ttu-id="e1c33-162">44</span><span class="sxs-lookup"><span data-stu-id="e1c33-162">44</span></span>                        |
| <span data-ttu-id="e1c33-163">febbraio</span><span class="sxs-lookup"><span data-stu-id="e1c33-163">February</span></span>             | <span data-ttu-id="e1c33-164">0</span><span class="sxs-lookup"><span data-stu-id="e1c33-164">0</span></span>                         |
| <span data-ttu-id="e1c33-165">marzo</span><span class="sxs-lookup"><span data-stu-id="e1c33-165">March</span></span>                | <span data-ttu-id="e1c33-166">549</span><span class="sxs-lookup"><span data-stu-id="e1c33-166">549</span></span>                       |
| <span data-ttu-id="e1c33-167">aprile</span><span class="sxs-lookup"><span data-stu-id="e1c33-167">April</span></span>                | <span data-ttu-id="e1c33-168">881</span><span class="sxs-lookup"><span data-stu-id="e1c33-168">881</span></span>                       |
| <span data-ttu-id="e1c33-169">Da maggio a dicembre</span><span class="sxs-lookup"><span data-stu-id="e1c33-169">May through December</span></span> | <span data-ttu-id="e1c33-170">1.000</span><span class="sxs-lookup"><span data-stu-id="e1c33-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="e1c33-171">Esempio 3: Principio di riduzione previsioni di Transazioni - periodo dinamico</span><span class="sxs-lookup"><span data-stu-id="e1c33-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="e1c33-172">Nella maggior parte dei casi i sistemi vengono impostati in modo che le transazioni riducano la previsione della domanda entro periodi specifici di previsione: settimane, mesi, ecc.</span><span class="sxs-lookup"><span data-stu-id="e1c33-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="e1c33-173">I periodi vengono sono definiti nella chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="e1c33-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="e1c33-174">Tuttavia, il tempo trascorso tra due righe di previsione della domanda può anche *implicare* un periodo.</span><span class="sxs-lookup"><span data-stu-id="e1c33-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1. <span data-ttu-id="e1c33-175">Creare una previsione della domanda per le seguenti date e quantità.</span><span class="sxs-lookup"><span data-stu-id="e1c33-175">Create a demand forecast for the following dates and quantities.</span></span>

   | <span data-ttu-id="e1c33-176">Data</span><span class="sxs-lookup"><span data-stu-id="e1c33-176">Date</span></span>       | <span data-ttu-id="e1c33-177">Previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="e1c33-177">Demand forecast</span></span> |
   |------------|-----------------|
   | <span data-ttu-id="e1c33-178">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-178">January 1</span></span>  | <span data-ttu-id="e1c33-179">1.000</span><span class="sxs-lookup"><span data-stu-id="e1c33-179">1,000</span></span>           |
   | <span data-ttu-id="e1c33-180">5 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-180">January 5</span></span>  | <span data-ttu-id="e1c33-181">500</span><span class="sxs-lookup"><span data-stu-id="e1c33-181">500</span></span>             |
   | <span data-ttu-id="e1c33-182">12 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-182">January 12</span></span> | <span data-ttu-id="e1c33-183">1.000</span><span class="sxs-lookup"><span data-stu-id="e1c33-183">1,000</span></span>           |

   <span data-ttu-id="e1c33-184">Nella previsione non è presente un periodo chiaro tra le date di previsione: tra le prime e le seconde date vi è un intervallo di quattro giorni e tra la seconde e terze date vi è un intervallo di sette giorni.</span><span class="sxs-lookup"><span data-stu-id="e1c33-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="e1c33-185">I vari intervalli sono i periodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="e1c33-185">These various spans are the dynamic periods.</span></span>
2. <span data-ttu-id="e1c33-186">Creare righe dell'ordine cliente come segue</span><span class="sxs-lookup"><span data-stu-id="e1c33-186">Create sales order lines as follows.</span></span>

   | <span data-ttu-id="e1c33-187">Data</span><span class="sxs-lookup"><span data-stu-id="e1c33-187">Date</span></span>                             | <span data-ttu-id="e1c33-188">Quantità ordine cliente</span><span class="sxs-lookup"><span data-stu-id="e1c33-188">Sales order quantity</span></span> |
   |----------------------------------|----------------------|
   | <span data-ttu-id="e1c33-189">15 dicembre dell'anno precedente</span><span class="sxs-lookup"><span data-stu-id="e1c33-189">December 15 in the previous year</span></span> | <span data-ttu-id="e1c33-190">500</span><span class="sxs-lookup"><span data-stu-id="e1c33-190">500</span></span>                  |
   | <span data-ttu-id="e1c33-191">3 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-191">January 3</span></span>                        | <span data-ttu-id="e1c33-192">100</span><span class="sxs-lookup"><span data-stu-id="e1c33-192">100</span></span>                  |
   | <span data-ttu-id="e1c33-193">10 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-193">January 10</span></span>                       | <span data-ttu-id="e1c33-194">200</span><span class="sxs-lookup"><span data-stu-id="e1c33-194">200</span></span>                  |

<span data-ttu-id="e1c33-195">La previsione verrà ridotta come segue:</span><span class="sxs-lookup"><span data-stu-id="e1c33-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="e1c33-196">Il primo ordine cliente non rientra in alcun periodo, pertanto non ridurrà alcuna previsione.</span><span class="sxs-lookup"><span data-stu-id="e1c33-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="e1c33-197">Il secondo ordine cliente è compreso tra il 1° gennaio e il 5 gennaio, pertanto ridurrà la previsione per il 1° gennaio di 100.</span><span class="sxs-lookup"><span data-stu-id="e1c33-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="e1c33-198">Il terzo ordine cliente è compreso tra il 5 gennaio e il 12 gennaio, pertanto ridurrà la previsione per il 5 gennaio di 200.</span><span class="sxs-lookup"><span data-stu-id="e1c33-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="e1c33-199">Il seguente ordine pianificato verrà creato per soddisfare la previsione.</span><span class="sxs-lookup"><span data-stu-id="e1c33-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="e1c33-200">Data di previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="e1c33-200">Demand forecast date</span></span> | <span data-ttu-id="e1c33-201">Quantità ridotta</span><span class="sxs-lookup"><span data-stu-id="e1c33-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="e1c33-202">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-202">January 1</span></span>            | <span data-ttu-id="e1c33-203">900</span><span class="sxs-lookup"><span data-stu-id="e1c33-203">900</span></span>              |
| <span data-ttu-id="e1c33-204">5 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-204">January 5</span></span>            | <span data-ttu-id="e1c33-205">300</span><span class="sxs-lookup"><span data-stu-id="e1c33-205">300</span></span>              |
| <span data-ttu-id="e1c33-206">12 gennaio</span><span class="sxs-lookup"><span data-stu-id="e1c33-206">January 12</span></span>           | <span data-ttu-id="e1c33-207">1.000</span><span class="sxs-lookup"><span data-stu-id="e1c33-207">1,000</span></span>            |

<span data-ttu-id="e1c33-208">Questo campo è un riepilogo della riduzione **Transazioni - periodo dinamico**:</span><span class="sxs-lookup"><span data-stu-id="e1c33-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="e1c33-209">I requisiti di previsione vengono ridotti in base alle transazioni di ordini effettive effettuate durante il periodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="e1c33-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="e1c33-210">Il periodo dinamico copre le date di previsione correnti e termina all'inizio della previsione successiva.</span><span class="sxs-lookup"><span data-stu-id="e1c33-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="e1c33-211">Per questo metodo non viene utilizzata o richiesta alcuna chiave di riduzione.</span><span class="sxs-lookup"><span data-stu-id="e1c33-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="e1c33-212">Quando questa opzione viene utilizzata, si verifica il seguente comportamento :</span><span class="sxs-lookup"><span data-stu-id="e1c33-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="e1c33-213">Se la previsione viene ridotta completamente, i requisiti per la previsione corrente diventano 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="e1c33-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="e1c33-214">Se non vi è alcuna previsione futura, vengono ridotti i requisiti di previsione dall'ultima previsione immessa.</span><span class="sxs-lookup"><span data-stu-id="e1c33-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="e1c33-215">Gli intervalli temporali vengono inclusi nel calcolo della riduzione previsionale.</span><span class="sxs-lookup"><span data-stu-id="e1c33-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="e1c33-216">I giorni di positività vengono inclusi nel calcolo della riduzione previsionale.</span><span class="sxs-lookup"><span data-stu-id="e1c33-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="e1c33-217">Se le transazioni di ordini effettivi superano i fabbisogni previsti, le transazioni rimanenti non vengono inoltrate al periodo previsionale successivo.</span><span class="sxs-lookup"><span data-stu-id="e1c33-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="additional-resources"></a><span data-ttu-id="e1c33-218">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e1c33-218">Additional resources</span></span>
--------

[<span data-ttu-id="e1c33-219">Piani generali</span><span class="sxs-lookup"><span data-stu-id="e1c33-219">Master plans</span></span>](master-plans.md)



