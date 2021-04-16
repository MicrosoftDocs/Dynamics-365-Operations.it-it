---
title: Ammortamento a saldi decrescenti del 175%
description: Questo argomento offre una panoramica del metodo di ammortamento a saldi decrescenti del 175%.
author: saraschi2
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0747c34a4b28340227209adadf367f672deb1ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827148"
---
# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="02a60-103">Ammortamento a saldi decrescenti del 175%</span><span class="sxs-lookup"><span data-stu-id="02a60-103">175 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02a60-104">Questo argomento offre una panoramica del metodo di ammortamento a saldi decrescenti del 175%.</span><span class="sxs-lookup"><span data-stu-id="02a60-104">This topic gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="02a60-105">Quando si imposta un profilo di ammortamento cespiti e si seleziona **Saldo decrescente 175%** nel campo **Metodo** della pagina **Profili di ammortamento**, ai cespiti che sono assegnati al profilo di ammortamento verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="02a60-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="02a60-106">Per impostare l'ammortamento a saldi decrescenti del 175%, è inoltre necessario selezionare le opzioni presenti nel campo **Anno di ammortamento** e nel campo **Frequenza periodo** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="02a60-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="02a60-107">Le opzioni disponibili nel campo **Frequenza periodo** variano a seconda del valore selezionato in **Anno di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="02a60-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="02a60-108">Selezionare un anno di ammortamento</span><span class="sxs-lookup"><span data-stu-id="02a60-108">Select a depreciation year</span></span>
<span data-ttu-id="02a60-109">È possibile selezionare **Calendario** o **Fiscale** nel campo **Anno di ammortamento** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="02a60-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="02a60-110">Il valore predefinito è **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="02a60-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="02a60-111">La selezione determina le opzioni disponibili nel campo **Frequenza periodo**.</span><span class="sxs-lookup"><span data-stu-id="02a60-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="02a60-112">Il campo consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario.</span><span class="sxs-lookup"><span data-stu-id="02a60-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="02a60-113">Calendario</span><span class="sxs-lookup"><span data-stu-id="02a60-113">Calendar</span></span>

<span data-ttu-id="02a60-114">È possibile scegliere di mantenere il valore predefinito nel campo **Anno di ammortamento**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="02a60-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="02a60-115">L'opzione **Calendario** aggiorna la base di ammortamento il 1° gennaio di ogni anno.</span><span class="sxs-lookup"><span data-stu-id="02a60-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="02a60-116">In genere, la base di ammortamento corrisponde al valore contabile netto meno il valore di recupero.</span><span class="sxs-lookup"><span data-stu-id="02a60-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="02a60-117">Negli esempi illustrati più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli.</span><span class="sxs-lookup"><span data-stu-id="02a60-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="02a60-118">Se si seleziona **Calendario** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02a60-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="02a60-119">**Annuale**: viene registrato un importo il 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="02a60-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="02a60-120">**Mensile**: viene registrato un importo mensile alla fine di ciascun mese di calendario.</span><span class="sxs-lookup"><span data-stu-id="02a60-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="02a60-121">**Trimestrale**: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="02a60-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="02a60-122">**Semestrale**: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="02a60-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="02a60-123">**Giornaliero**: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="02a60-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="02a60-124">Fiscale</span><span class="sxs-lookup"><span data-stu-id="02a60-124">Fiscal</span></span>

<span data-ttu-id="02a60-125">Se si seleziona **Fiscale** nel campo **Anno di ammortamento**, l'ammortamento a saldi decrescenti del 175% viene calcolato in base all'anno fiscale del calendario fiscale specificato per il libro oppure del calendario fiscale selezionato nella pagina **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="02a60-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="02a60-126">I calendari fiscali vengono impostati nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="02a60-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="02a60-127">Per ulteriori informazioni, vedere [Calendari fiscali, anni fiscali e periodi](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="02a60-127">For more information, see [Fiscal calendars, fiscal years, and periods](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="02a60-128">Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio.</span><span class="sxs-lookup"><span data-stu-id="02a60-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="02a60-129">La durata dell'anno fiscale non deve essere necessariamente di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="02a60-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="02a60-130">L'ammortamento viene rettificato automaticamente per ciascun periodo e la durata dell'anno fiscale successivo dipende dall'impostazione dei periodi nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="02a60-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="02a60-131">Se si seleziona **Fiscale** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02a60-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="02a60-132">**Annuale**: l'importo totale dell'ammortamento calcolato per l'anno fiscale viene registrato come importo unico nell'ultimo giorno dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="02a60-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="02a60-133">**Periodo fiscale**: calcola l'importo totale dell'ammortamento per l'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="02a60-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="02a60-134">Questo importo viene attribuito ai periodi fiscali definiti nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="02a60-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="02a60-135">Esempio di ammortamento a saldi decrescenti del 175%</span><span class="sxs-lookup"><span data-stu-id="02a60-135">Example of 175% reducing balance depreciation</span></span>

| <span data-ttu-id="02a60-136">Campo</span><span class="sxs-lookup"><span data-stu-id="02a60-136">Field</span></span>                          | <span data-ttu-id="02a60-137">Valore</span><span class="sxs-lookup"><span data-stu-id="02a60-137">Value</span></span>  |
|--------------------------------|--------|
| <span data-ttu-id="02a60-138">Costo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="02a60-138">Acquisition cost</span></span>               | <span data-ttu-id="02a60-139">11,000</span><span class="sxs-lookup"><span data-stu-id="02a60-139">11,000</span></span> |
| <span data-ttu-id="02a60-140">Valore di realizzo</span><span class="sxs-lookup"><span data-stu-id="02a60-140">Salvage value</span></span>                  | <span data-ttu-id="02a60-141">1.000</span><span class="sxs-lookup"><span data-stu-id="02a60-141">1,000</span></span>  |
| <span data-ttu-id="02a60-142">Base di ammortamento</span><span class="sxs-lookup"><span data-stu-id="02a60-142">Depreciation base</span></span>              | <span data-ttu-id="02a60-143">10.000</span><span class="sxs-lookup"><span data-stu-id="02a60-143">10,000</span></span> |
| <span data-ttu-id="02a60-144">Anni vita utile</span><span class="sxs-lookup"><span data-stu-id="02a60-144">Service life years</span></span>             | <span data-ttu-id="02a60-145">5</span><span class="sxs-lookup"><span data-stu-id="02a60-145">5</span></span>      |
| <span data-ttu-id="02a60-146">Percentuale di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="02a60-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="02a60-147">35%</span><span class="sxs-lookup"><span data-stu-id="02a60-147">35%</span></span>    |

<span data-ttu-id="02a60-148">Il metodo di ammortamento a saldi decrescenti del 175% divide il 175% per gli anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="02a60-148">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="02a60-149">Tale percentuale verrà moltiplicata per il valore contabile netto del cespite al fine di determinare l'importo dell'ammortamento per l'anno.</span><span class="sxs-lookup"><span data-stu-id="02a60-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="02a60-150">Periodo</span><span class="sxs-lookup"><span data-stu-id="02a60-150">Period</span></span> | <span data-ttu-id="02a60-151">Calcolo della quota di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="02a60-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="02a60-152">Valore contabile</span><span class="sxs-lookup"><span data-stu-id="02a60-152">Book value</span></span>                  | <span data-ttu-id="02a60-153">Valore contabile netto alla fine dell'anno</span><span class="sxs-lookup"><span data-stu-id="02a60-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="02a60-154">Anno 1</span><span class="sxs-lookup"><span data-stu-id="02a60-154">Year 1</span></span> | <span data-ttu-id="02a60-155">(11.000 – 1.000) × 35% = 3.500</span><span class="sxs-lookup"><span data-stu-id="02a60-155">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="02a60-156">11.000 – 3.500 = 7.500</span><span class="sxs-lookup"><span data-stu-id="02a60-156">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="02a60-157">11.000 – 1.000 – 3.500 = 6.500</span><span class="sxs-lookup"><span data-stu-id="02a60-157">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="02a60-158">Anno 2</span><span class="sxs-lookup"><span data-stu-id="02a60-158">Year 2</span></span> | <span data-ttu-id="02a60-159">6.500 × 35% = 2.275</span><span class="sxs-lookup"><span data-stu-id="02a60-159">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="02a60-160">7.500 – 2.275 = 5.225</span><span class="sxs-lookup"><span data-stu-id="02a60-160">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="02a60-161">6.500 – 2.275 = 4.225</span><span class="sxs-lookup"><span data-stu-id="02a60-161">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="02a60-162">Anno 3</span><span class="sxs-lookup"><span data-stu-id="02a60-162">Year 3</span></span> | <span data-ttu-id="02a60-163">4.225 × 35% = 1.478,75</span><span class="sxs-lookup"><span data-stu-id="02a60-163">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="02a60-164">5.225 – 1.478,75 = 3.746,25</span><span class="sxs-lookup"><span data-stu-id="02a60-164">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="02a60-165">4.225 – 1.478,75 = 2.746,25</span><span class="sxs-lookup"><span data-stu-id="02a60-165">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="02a60-166">In genere, quando l'importo calcolato utilizzando il metodo di ammortamento a saldi decrescenti del 175% diventa inferiore all'importo che sarà calcolato utilizzando il metodo a quote costanti, si verifica una conversione al metodo a quote costanti per la vita utile rimanente.</span><span class="sxs-lookup"><span data-stu-id="02a60-166">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]