---
title: Riduzione del 125% dell'ammortamento del saldo
description: Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 125%.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8ec88d799c44e035b6490861383557f8c3beda41
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="125-percent-reducing-balance-depreciation"></a><span data-ttu-id="73e09-103">Riduzione del 125% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="73e09-103">125 percent reducing balance depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="73e09-104">Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 125%.</span><span class="sxs-lookup"><span data-stu-id="73e09-104">This article gives an overview of the 125 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="73e09-105">Quando si imposta un profilo di ammortamento cespiti e si seleziona **Saldo decrescente 125%** nel campo **Metodo** della pagina **Profili di ammortamento**, ai cespiti che sono assegnati al profilo di ammortamento verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="73e09-105">When you set up a fixed asset depreciation profile and select **125% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned to the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="73e09-106">Questa percentuale viene calcolata in base alla vita utile del cespite.</span><span class="sxs-lookup"><span data-stu-id="73e09-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="73e09-107">Ad esempio, se un cespite ha una vita utile di cinque anni, la percentuale viene calcolata come 25% (125% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="73e09-107">For example, if an asset has a service life of five years, the percentage is calculated as 25 percent (125% ÷ 5).</span></span>

<span data-ttu-id="73e09-108">Per impostare l'ammortamento a saldi decrescenti del 125%, è inoltre necessario selezionare le opzioni presenti nel campo **Anno di ammortamento** e nel campo **Frequenza periodo** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="73e09-108">To set up 125% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="73e09-109">Le opzioni disponibili nel campo **Frequenza periodo** variano a seconda del valore selezionato in **Anno di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="73e09-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="73e09-110">Selezionare un anno di ammortamento</span><span class="sxs-lookup"><span data-stu-id="73e09-110">Select a depreciation year</span></span>
<span data-ttu-id="73e09-111">È possibile selezionare **Calendario** o **Fiscale** nel campo **Anno di ammortamento** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="73e09-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="73e09-112">Il valore predefinito è **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="73e09-112">The default value is **Calendar**.</span></span> 

<span data-ttu-id="73e09-113">La selezione determina le opzioni disponibili nel campo **Frequenza periodo**.</span><span class="sxs-lookup"><span data-stu-id="73e09-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="73e09-114">Il campo consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario.</span><span class="sxs-lookup"><span data-stu-id="73e09-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="73e09-115">Calendario</span><span class="sxs-lookup"><span data-stu-id="73e09-115">Calendar</span></span>

<span data-ttu-id="73e09-116">È possibile scegliere di mantenere il valore predefinito nel campo **Anno di ammortamento**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="73e09-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="73e09-117">L'opzione **Calendario** aggiorna la base di ammortamento il 1° gennaio di ogni anno.</span><span class="sxs-lookup"><span data-stu-id="73e09-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="73e09-118">In genere, la base di ammortamento corrisponde al valore contabile netto meno il valore di recupero.</span><span class="sxs-lookup"><span data-stu-id="73e09-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="73e09-119">Negli esempi illustrati più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli.</span><span class="sxs-lookup"><span data-stu-id="73e09-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="73e09-120">Se si seleziona **Calendario** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="73e09-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="73e09-121">**Annuale**: viene registrato un importo il 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="73e09-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="73e09-122">**Mensile**: viene registrato un importo mensile alla fine di ciascun mese di calendario.</span><span class="sxs-lookup"><span data-stu-id="73e09-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="73e09-123">**Trimestrale**: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="73e09-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="73e09-124">**Semestrale**: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="73e09-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="73e09-125">**Giornaliero**: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="73e09-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="73e09-126">Fiscale</span><span class="sxs-lookup"><span data-stu-id="73e09-126">Fiscal</span></span>

<span data-ttu-id="73e09-127">Se si seleziona **Fiscale** nel campo **Anno di ammortamento**, l'ammortamento a saldi decrescenti del 125% viene calcolato in base all'anno fiscale del calendario fiscale specificato per il libro oppure del calendario fiscale selezionato nella pagina **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="73e09-127">If you select **Fiscal** in the **Depreciation year** field, 125% reducing depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="73e09-128">I calendari fiscali vengono impostati nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="73e09-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="73e09-129">Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio.</span><span class="sxs-lookup"><span data-stu-id="73e09-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="73e09-130">La durata dell'anno fiscale non deve essere necessariamente di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="73e09-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="73e09-131">L'ammortamento viene rettificato automaticamente per ciascun periodo e la durata dell'anno fiscale successivo dipende dall'impostazione dei periodi nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="73e09-131">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="73e09-132">Se si seleziona **Fiscale** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="73e09-132">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="73e09-133">L'opzione **Annuale** registra l'importo totale dell'ammortamento che viene calcolato per l'anno fiscale come importo unico nell'ultimo giorno dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="73e09-133">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="73e09-134">**Periodo fiscale** registra l'importo totale dell'ammortamento calcolato per l'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="73e09-134">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="73e09-135">Questo importo viene attribuito ai periodi fiscali definiti nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="73e09-135">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-125-reducing-balance-depreciation"></a><span data-ttu-id="73e09-136">Esempio di ammortamento a saldi decrescenti del 125%</span><span class="sxs-lookup"><span data-stu-id="73e09-136">Example of 125% reducing balance depreciation</span></span>
|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="73e09-137">Costo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="73e09-137">Acquisition cost</span></span>               | <span data-ttu-id="73e09-138">11.000</span><span class="sxs-lookup"><span data-stu-id="73e09-138">11,000</span></span> |
| <span data-ttu-id="73e09-139">Valore di realizzo</span><span class="sxs-lookup"><span data-stu-id="73e09-139">Salvage value</span></span>                  | <span data-ttu-id="73e09-140">1.000</span><span class="sxs-lookup"><span data-stu-id="73e09-140">1,000</span></span>  |
| <span data-ttu-id="73e09-141">Base di ammortamento</span><span class="sxs-lookup"><span data-stu-id="73e09-141">Depreciation base</span></span>              | <span data-ttu-id="73e09-142">10.000</span><span class="sxs-lookup"><span data-stu-id="73e09-142">10,000</span></span> |
| <span data-ttu-id="73e09-143">Anni vita utile</span><span class="sxs-lookup"><span data-stu-id="73e09-143">Service life years</span></span>             | <span data-ttu-id="73e09-144">5</span><span class="sxs-lookup"><span data-stu-id="73e09-144">5</span></span>      |
| <span data-ttu-id="73e09-145">Percentuale di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="73e09-145">Yearly depreciation percentage</span></span> | <span data-ttu-id="73e09-146">25%</span><span class="sxs-lookup"><span data-stu-id="73e09-146">25%</span></span>    |

<span data-ttu-id="73e09-147">Il metodo a saldi decrescenti del 125% consente di dividere il 125% per gli anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="73e09-147">The 125% reducing balance method divides 125 percent by the service life years.</span></span> <span data-ttu-id="73e09-148">Tale percentuale verrà moltiplicata per il valore contabile netto del cespite al fine di determinare l'importo dell'ammortamento per l'anno.</span><span class="sxs-lookup"><span data-stu-id="73e09-148">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="73e09-149">Periodo</span><span class="sxs-lookup"><span data-stu-id="73e09-149">Period</span></span> | <span data-ttu-id="73e09-150">Calcolo della quota di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="73e09-150">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="73e09-151">Valore contabile</span><span class="sxs-lookup"><span data-stu-id="73e09-151">Book value</span></span>                    | <span data-ttu-id="73e09-152">Valore contabile netto alla fine dell'anno</span><span class="sxs-lookup"><span data-stu-id="73e09-152">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| <span data-ttu-id="73e09-153">Anno 1</span><span class="sxs-lookup"><span data-stu-id="73e09-153">Year 1</span></span> | <span data-ttu-id="73e09-154">(11.000 - 1-000) × 25% = 2.500</span><span class="sxs-lookup"><span data-stu-id="73e09-154">(11,000 – 1,000) × 25% = 2,500</span></span>                | <span data-ttu-id="73e09-155">(11.000 - 2.500) = 8.500</span><span class="sxs-lookup"><span data-stu-id="73e09-155">(11,000 – 2,500) = 8,500</span></span>      | <span data-ttu-id="73e09-156">(11.000 - 1.000 - 2.500) = 7.500</span><span class="sxs-lookup"><span data-stu-id="73e09-156">(11,000 – 1,000 – 2,500) = 7,500</span></span>      |
| <span data-ttu-id="73e09-157">Anno 2</span><span class="sxs-lookup"><span data-stu-id="73e09-157">Year 2</span></span> | <span data-ttu-id="73e09-158">7.500 × 25% = 1.875</span><span class="sxs-lookup"><span data-stu-id="73e09-158">7,500 × 25% = 1,875</span></span>                           | <span data-ttu-id="73e09-159">(8.500 - 1.875) = 6.625</span><span class="sxs-lookup"><span data-stu-id="73e09-159">(8,500 – 1,875) = 6,625</span></span>       | <span data-ttu-id="73e09-160">(7.500 - 1.875) = 5.625</span><span class="sxs-lookup"><span data-stu-id="73e09-160">(7,500 – 1,875) = 5,625</span></span>               |
| <span data-ttu-id="73e09-161">Anno 3</span><span class="sxs-lookup"><span data-stu-id="73e09-161">Year 3</span></span> | <span data-ttu-id="73e09-162">5.625 × 25% = 1.406,25</span><span class="sxs-lookup"><span data-stu-id="73e09-162">5,625 × 25% = 1,406.25</span></span>                        | <span data-ttu-id="73e09-163">(6.625 - 1.406,25) = 5.218,75</span><span class="sxs-lookup"><span data-stu-id="73e09-163">(6,625 – 1,406.25) = 5,218.75</span></span> | <span data-ttu-id="73e09-164">(5.625 - 1.406,25) = 4.218,75</span><span class="sxs-lookup"><span data-stu-id="73e09-164">(5,625 – 1,406.25) = 4,218.75</span></span>         |

> [!NOTE] 
> <span data-ttu-id="73e09-165">In genere, quando l'importo calcolato utilizzando il metodo di ammortamento a saldi decrescenti del 125% diventa inferiore all'importo che sarà calcolato utilizzando il metodo a quote costanti, si verifica una conversione al metodo a quote costanti per la vita utile rimanente.</span><span class="sxs-lookup"><span data-stu-id="73e09-165">Typically, when the amount that is calculated by using the 125% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




