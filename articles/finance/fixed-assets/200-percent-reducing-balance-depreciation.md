---
title: Riduzione del 200% dell'ammortamento del saldo
description: Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 200%.
author: saraschi2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e5a548f7963fad2b249c36c90ac19b812131d56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827076"
---
# <a name="200-percent-reducing-balance-depreciation"></a><span data-ttu-id="ded23-103">Riduzione del 200% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="ded23-103">200 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ded23-104">Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 200%.</span><span class="sxs-lookup"><span data-stu-id="ded23-104">This article gives an overview of the 200 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="ded23-105">Quando si imposta un profilo di ammortamento cespiti e si seleziona **Saldo decrescente 200%** nel campo **Metodo** della pagina **Profili di ammortamento**, ai cespiti che sono assegnati al profilo di ammortamento verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="ded23-105">When you set up a fixed asset depreciation profile and select **200% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="ded23-106">Questa percentuale viene calcolata in base alla vita utile del cespite.</span><span class="sxs-lookup"><span data-stu-id="ded23-106">The percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="ded23-107">Ad esempio, se un cespite ha una vita utile di cinque anni, la percentuale viene calcolata come 40% (200% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="ded23-107">For example, if an asset has a service life of five years, the percentage is calculated as 40 percent (200% ÷ 5).</span></span> 

<span data-ttu-id="ded23-108">Questo metodo è detto anche metodo a doppie quote proporzionali.</span><span class="sxs-lookup"><span data-stu-id="ded23-108">This method is also known as double declining balance.</span></span>

<span data-ttu-id="ded23-109">Per impostare l'ammortamento a saldi decrescenti del 200%, è inoltre necessario selezionare le opzioni presenti nel campo **Anno di ammortamento** e nel campo **Frequenza periodo** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="ded23-109">To set up 200% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="ded23-110">Le opzioni disponibili nel campo **Frequenza periodo** variano a seconda del valore selezionato in **Anno di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="ded23-110">The options that are available in the **Period frequency** field vary, depending on the value that you select in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="ded23-111">Selezionare un anno di ammortamento</span><span class="sxs-lookup"><span data-stu-id="ded23-111">Select a depreciation year</span></span>
<span data-ttu-id="ded23-112">È possibile selezionare **Calendario** o **Fiscale** nel campo **Anno di ammortamento** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="ded23-112">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="ded23-113">Il valore predefinito è **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="ded23-113">The default value is **Calendar**.</span></span> 

<span data-ttu-id="ded23-114">La selezione determina le opzioni disponibili nel campo **Frequenza periodo**.</span><span class="sxs-lookup"><span data-stu-id="ded23-114">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="ded23-115">Il campo consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario.</span><span class="sxs-lookup"><span data-stu-id="ded23-115">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="ded23-116">Calendario</span><span class="sxs-lookup"><span data-stu-id="ded23-116">Calendar</span></span>

<span data-ttu-id="ded23-117">È possibile scegliere di mantenere il valore predefinito nel campo **Anno di ammortamento**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="ded23-117">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="ded23-118">L'opzione **Calendario** aggiorna la base di ammortamento il 1° gennaio di ogni anno.</span><span class="sxs-lookup"><span data-stu-id="ded23-118">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="ded23-119">In genere, l'ammortamento corrisponde al valore contabile netto meno il valore di recupero.</span><span class="sxs-lookup"><span data-stu-id="ded23-119">Typically, the depreciation is the net book value minus the scrap value.</span></span> <span data-ttu-id="ded23-120">Negli esempi illustrati più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli.</span><span class="sxs-lookup"><span data-stu-id="ded23-120">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="ded23-121">Se si seleziona **Calendario** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ded23-121">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="ded23-122">**Annuale**: viene registrato un importo il 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="ded23-122">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="ded23-123">**Mensile**: viene registrato un importo mensile alla fine di ciascun mese di calendario.</span><span class="sxs-lookup"><span data-stu-id="ded23-123">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="ded23-124">**Trimestrale**: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="ded23-124">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="ded23-125">**Semestrale**: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="ded23-125">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="ded23-126">**Giornaliero**: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="ded23-126">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="ded23-127">Fiscale</span><span class="sxs-lookup"><span data-stu-id="ded23-127">Fiscal</span></span>

<span data-ttu-id="ded23-128">Se si seleziona **Fiscale** nel campo **Anno di ammortamento**, l'ammortamento a saldi decrescenti del 200% viene calcolato in base all'anno fiscale del calendario fiscale specificato per il libro oppure del calendario fiscale selezionato nella pagina **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="ded23-128">If you select **Fiscal** in the **Depreciation** year field, 200% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="ded23-129">I calendari fiscali vengono impostati nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="ded23-129">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="ded23-130">Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio.</span><span class="sxs-lookup"><span data-stu-id="ded23-130">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="ded23-131">La durata dell'anno fiscale non deve essere necessariamente di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="ded23-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="ded23-132">L'ammortamento viene rettificato per ciascun periodo.</span><span class="sxs-lookup"><span data-stu-id="ded23-132">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="ded23-133">La durata dell'anno fiscale successivo si baserà sull'impostazione dei periodi nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="ded23-133">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="ded23-134">Se si seleziona **Fiscale** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ded23-134">When **Fiscal** is selected as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="ded23-135">L'opzione **Annuale** registra l'importo totale dell'ammortamento che viene calcolato per l'anno fiscale come importo unico nell'ultimo giorno dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="ded23-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="ded23-136">**Periodo fiscale** registra l'importo totale dell'ammortamento calcolato per l'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="ded23-136">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="ded23-137">Questo importo viene attribuito ai periodi fiscali definiti nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="ded23-137">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-200-reducing-balance-depreciation"></a><span data-ttu-id="ded23-138">Esempio di ammortamento a saldi decrescenti del 200%</span><span class="sxs-lookup"><span data-stu-id="ded23-138">Example of 200% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="ded23-139">Costo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="ded23-139">Acquisition cost</span></span>               | <span data-ttu-id="ded23-140">11.000</span><span class="sxs-lookup"><span data-stu-id="ded23-140">11,000</span></span> |
| <span data-ttu-id="ded23-141">Valore di realizzo</span><span class="sxs-lookup"><span data-stu-id="ded23-141">Salvage value</span></span>                  | <span data-ttu-id="ded23-142">1. 000</span><span class="sxs-lookup"><span data-stu-id="ded23-142">1, 000</span></span> |
| <span data-ttu-id="ded23-143">Base di ammortamento</span><span class="sxs-lookup"><span data-stu-id="ded23-143">Depreciation base</span></span>              | <span data-ttu-id="ded23-144">10.000</span><span class="sxs-lookup"><span data-stu-id="ded23-144">10,000</span></span> |
| <span data-ttu-id="ded23-145">Anni vita utile</span><span class="sxs-lookup"><span data-stu-id="ded23-145">Service life years</span></span>             | <span data-ttu-id="ded23-146">5</span><span class="sxs-lookup"><span data-stu-id="ded23-146">5</span></span>      |
| <span data-ttu-id="ded23-147">Percentuale di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="ded23-147">Yearly depreciation percentage</span></span> | <span data-ttu-id="ded23-148">40%</span><span class="sxs-lookup"><span data-stu-id="ded23-148">40%</span></span>    |

<span data-ttu-id="ded23-149">Il metodo a saldi decrescenti del 200% consente di dividere il 200% per gli anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="ded23-149">The 200% reducing balance method divides 200 percent by the service life years.</span></span> <span data-ttu-id="ded23-150">Tale percentuale verrà moltiplicata per il valore contabile netto del cespite al fine di determinare l'importo dell'ammortamento per l'anno.</span><span class="sxs-lookup"><span data-stu-id="ded23-150">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="ded23-151">Periodo</span><span class="sxs-lookup"><span data-stu-id="ded23-151">Period</span></span> | <span data-ttu-id="ded23-152">Calcolo della quota di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="ded23-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="ded23-153">Valore contabile</span><span class="sxs-lookup"><span data-stu-id="ded23-153">Book value</span></span>             | <span data-ttu-id="ded23-154">Valore contabile netto alla fine dell'anno</span><span class="sxs-lookup"><span data-stu-id="ded23-154">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="ded23-155">Anno 1</span><span class="sxs-lookup"><span data-stu-id="ded23-155">Year 1</span></span> | <span data-ttu-id="ded23-156">(11.000 – 1.000) × 40% = 4.000</span><span class="sxs-lookup"><span data-stu-id="ded23-156">(11,000 – 1,000) × 40% = 4,000</span></span>                | <span data-ttu-id="ded23-157">11.000 – 4.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="ded23-157">11,000 – 4,000 = 7,000</span></span> | <span data-ttu-id="ded23-158">11.000 – 1.000 – 4.000 = 6.000</span><span class="sxs-lookup"><span data-stu-id="ded23-158">11,000 – 1,000 – 4,000 = 6,000</span></span>        |
| <span data-ttu-id="ded23-159">Anno 2</span><span class="sxs-lookup"><span data-stu-id="ded23-159">Year 2</span></span> | <span data-ttu-id="ded23-160">6.000 × 40% = 2.400</span><span class="sxs-lookup"><span data-stu-id="ded23-160">6,000 × 40% = 2,400</span></span>                           | <span data-ttu-id="ded23-161">7.000 – 2.400 = 4.600</span><span class="sxs-lookup"><span data-stu-id="ded23-161">7,000 – 2,400 = 4,600</span></span>  | <span data-ttu-id="ded23-162">6.000 – 2.400 = 3.600</span><span class="sxs-lookup"><span data-stu-id="ded23-162">6,000 – 2,400 = 3,600</span></span>                 |
| <span data-ttu-id="ded23-163">Anno 3</span><span class="sxs-lookup"><span data-stu-id="ded23-163">Year 3</span></span> | <span data-ttu-id="ded23-164">3.600 × 40% = 1.440</span><span class="sxs-lookup"><span data-stu-id="ded23-164">3,600 × 40% = 1,440</span></span>                           | <span data-ttu-id="ded23-165">4.600 – 1.440 = 3.160</span><span class="sxs-lookup"><span data-stu-id="ded23-165">4,600 – 1,440 = 3,160</span></span>  | <span data-ttu-id="ded23-166">3.600 – 1.440 = 2.160</span><span class="sxs-lookup"><span data-stu-id="ded23-166">3,600 – 1,440 = 2,160</span></span>                 |

> [!NOTE] 
> <span data-ttu-id="ded23-167">In genere, quando l'importo calcolato utilizzando il metodo di ammortamento a saldi decrescenti del 200% diventa inferiore all'importo che sarà calcolato utilizzando il metodo a quote costanti, si verifica una conversione al metodo a quote costanti per la vita utile rimanente.</span><span class="sxs-lookup"><span data-stu-id="ded23-167">Typically, when the amount that is calculated by using the 200% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]