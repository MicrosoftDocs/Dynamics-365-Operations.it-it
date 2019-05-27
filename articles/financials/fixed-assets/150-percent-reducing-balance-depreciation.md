---
title: Riduzione del 150% dell'ammortamento del saldo
description: Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 150%.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff4b40663f0da6bcc01b00f3f44cd8d8b43b56a1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568896"
---
# <a name="150-percent-reducing-balance-depreciation"></a><span data-ttu-id="edbb3-103">Riduzione del 150% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="edbb3-103">150 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="edbb3-104">Questo articolo offre una panoramica del metodo di ammortamento a saldi decrescenti del 150%.</span><span class="sxs-lookup"><span data-stu-id="edbb3-104">This article gives an overview of the 150 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="edbb3-105">Quando si imposta un profilo di ammortamento cespiti e si seleziona **Saldo decrescente 150%** nel campo **Metodo** della pagina **Profili di ammortamento**, ai cespiti che sono assegnati al profilo di ammortamento verrà applicata la stessa percentuale di ammortamento in ciascun periodo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="edbb3-105">When you set up a fixed asset depreciation profile and select **150% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="edbb3-106">Questa percentuale viene calcolata in base alla vita utile del cespite.</span><span class="sxs-lookup"><span data-stu-id="edbb3-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="edbb3-107">Ad esempio, se un cespite ha una vita utile di cinque anni, la percentuale viene calcolata come 30% (150% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="edbb3-107">For example, if an asset has a service life of five years, the percentage is calculated as 30 percent (150% ÷ 5).</span></span> 

<span data-ttu-id="edbb3-108">Per impostare l'ammortamento a saldi decrescenti del 150%, è inoltre necessario selezionare le opzioni presenti nel campo **Anno di ammortamento** e nel campo **Frequenza periodo** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-108">To set up 150% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="edbb3-109">Le opzioni disponibili nel campo **Frequenza periodo** variano a seconda del valore selezionato in **Anno di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="selection-of-depreciation-year"></a><span data-ttu-id="edbb3-110">Selezione dell'anno di ammortamento</span><span class="sxs-lookup"><span data-stu-id="edbb3-110">Selection of depreciation year</span></span>
<span data-ttu-id="edbb3-111">È possibile selezionare **Calendario** o **Fiscale** nel campo **Anno di ammortamento** della pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> 

<span data-ttu-id="edbb3-112">Il valore predefinito è **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-112">The default value is **Calendar**.</span></span> <span data-ttu-id="edbb3-113">La selezione determina le opzioni disponibili nel campo **Frequenza periodo**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="edbb3-114">Il campo consente di definire gli importi e le date di registrazione dei ratei di ammortamento per l'anno di calendario.</span><span class="sxs-lookup"><span data-stu-id="edbb3-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="edbb3-115">Calendario</span><span class="sxs-lookup"><span data-stu-id="edbb3-115">Calendar</span></span>

<span data-ttu-id="edbb3-116">È possibile scegliere di mantenere il valore predefinito nel campo **Anno di ammortamento**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="edbb3-117">L'opzione **Calendario** aggiorna la base di ammortamento il 1° gennaio di ogni anno.</span><span class="sxs-lookup"><span data-stu-id="edbb3-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="edbb3-118">In genere, la base di ammortamento corrisponde al valore contabile netto meno il valore di recupero.</span><span class="sxs-lookup"><span data-stu-id="edbb3-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="edbb3-119">Negli esempi illustrati più avanti in questo argomento, la base di ammortamento corrisponde al numeratore della prima espressione riportata nella colonna relativa ai calcoli.</span><span class="sxs-lookup"><span data-stu-id="edbb3-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="edbb3-120">Se si seleziona **Calendario** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="edbb3-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="edbb3-121">**Annuale**: viene registrato un importo il 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="edbb3-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="edbb3-122">**Mensile**: viene registrato un importo mensile alla fine di ciascun mese di calendario.</span><span class="sxs-lookup"><span data-stu-id="edbb3-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="edbb3-123">**Trimestrale**: viene registrato un importo trimestrale alla fine di ciascun trimestre di calendario (31 marzo, 30 giugno, 30 settembre e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="edbb3-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="edbb3-124">**Semestrale**: viene registrato un importo semestrale alla fine di ciascun semestre di calendario (30 giugno e 31 dicembre).</span><span class="sxs-lookup"><span data-stu-id="edbb3-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="edbb3-125">**Giornaliero**: viene registrato l'importo di ammortamento per il metodo di ammortamento giornaliero mediante una sola transazione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="edbb3-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="edbb3-126">Fiscale</span><span class="sxs-lookup"><span data-stu-id="edbb3-126">Fiscal</span></span>

<span data-ttu-id="edbb3-127">Se si seleziona **Fiscale** nel campo **Anno di ammortamento**, l'ammortamento a saldi decrescenti del 150% viene calcolato in base all'anno fiscale del calendario fiscale specificato per il libro oppure del calendario fiscale selezionato nella pagina **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-127">If you select **Fiscal** in the **Depreciation year** field, 150% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="edbb3-128">I calendari fiscali vengono impostati nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="edbb3-129">Se ad esempio l'anno fiscale inizia il 1° luglio e termina il 30 giugno, il calcolo dell'ammortamento inizia il 1° luglio.</span><span class="sxs-lookup"><span data-stu-id="edbb3-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="edbb3-130">La durata dell'anno fiscale non deve essere necessariamente di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="edbb3-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="edbb3-131">L'ammortamento viene rettificato per ciascun periodo.</span><span class="sxs-lookup"><span data-stu-id="edbb3-131">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="edbb3-132">La durata dell'anno fiscale successivo si baserà sull'impostazione dei periodi nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-132">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="edbb3-133">Se si seleziona **Fiscale** come anno di ammortamento, nel campo **Frequenza periodo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="edbb3-133">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="edbb3-134">**Annuale**: l'importo totale dell'ammortamento calcolato per l'anno fiscale viene registrato come importo unico nell'ultimo giorno dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="edbb3-134">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="edbb3-135">**Periodo fiscale** registra l'importo totale dell'ammortamento calcolato per l'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="edbb3-135">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="edbb3-136">Questo importo viene attribuito ai periodi fiscali definiti nella pagina **Calendari fiscali**.</span><span class="sxs-lookup"><span data-stu-id="edbb3-136">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-150-reducing-balance-depreciation"></a><span data-ttu-id="edbb3-137">Esempio di ammortamento a saldi decrescenti del 150%</span><span class="sxs-lookup"><span data-stu-id="edbb3-137">Example of 150% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="edbb3-138">Costo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="edbb3-138">Acquisition cost</span></span>               | <span data-ttu-id="edbb3-139">11.000</span><span class="sxs-lookup"><span data-stu-id="edbb3-139">11,000</span></span> |
| <span data-ttu-id="edbb3-140">Valore di realizzo</span><span class="sxs-lookup"><span data-stu-id="edbb3-140">Salvage value</span></span>                  | <span data-ttu-id="edbb3-141">1.000</span><span class="sxs-lookup"><span data-stu-id="edbb3-141">1,000</span></span>  |
| <span data-ttu-id="edbb3-142">Base di ammortamento</span><span class="sxs-lookup"><span data-stu-id="edbb3-142">Depreciation base</span></span>              | <span data-ttu-id="edbb3-143">10.000</span><span class="sxs-lookup"><span data-stu-id="edbb3-143">10,000</span></span> |
| <span data-ttu-id="edbb3-144">Anni vita utile</span><span class="sxs-lookup"><span data-stu-id="edbb3-144">Service life years</span></span>             | <span data-ttu-id="edbb3-145">5</span><span class="sxs-lookup"><span data-stu-id="edbb3-145">5</span></span>      |
| <span data-ttu-id="edbb3-146">Percentuale di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="edbb3-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="edbb3-147">30%</span><span class="sxs-lookup"><span data-stu-id="edbb3-147">30%</span></span>    |

<span data-ttu-id="edbb3-148">Il metodo a saldi decrescenti del 150% consente di dividere il 150% per gli anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="edbb3-148">The 150% reducing balance method divides 150 percent by the service life years.</span></span> <span data-ttu-id="edbb3-149">Tale percentuale verrà moltiplicata per il valore contabile netto del cespite al fine di determinare l'importo dell'ammortamento per l'anno.</span><span class="sxs-lookup"><span data-stu-id="edbb3-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="edbb3-150">Periodo</span><span class="sxs-lookup"><span data-stu-id="edbb3-150">Period</span></span> | <span data-ttu-id="edbb3-151">Calcolo della quota di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="edbb3-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="edbb3-152">Valore contabile</span><span class="sxs-lookup"><span data-stu-id="edbb3-152">Book value</span></span>             | <span data-ttu-id="edbb3-153">Valore contabile netto alla fine dell'anno</span><span class="sxs-lookup"><span data-stu-id="edbb3-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="edbb3-154">Anno 1</span><span class="sxs-lookup"><span data-stu-id="edbb3-154">Year 1</span></span> | <span data-ttu-id="edbb3-155">(11.000 – 1.000) × 30% = 3.000</span><span class="sxs-lookup"><span data-stu-id="edbb3-155">(11,000 – 1,000) × 30% = 3,000</span></span>                | <span data-ttu-id="edbb3-156">11.000 – 3.000 = 8.000</span><span class="sxs-lookup"><span data-stu-id="edbb3-156">11,000 – 3,000 = 8,000</span></span> | <span data-ttu-id="edbb3-157">11.000 – 1.000 – 3.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="edbb3-157">11,000 – 1,000 – 3,000 = 7,000</span></span>        |
| <span data-ttu-id="edbb3-158">Anno 2</span><span class="sxs-lookup"><span data-stu-id="edbb3-158">Year 2</span></span> | <span data-ttu-id="edbb3-159">7.000 × 30% = 2.100</span><span class="sxs-lookup"><span data-stu-id="edbb3-159">7,000 × 30% = 2,100</span></span>                           | <span data-ttu-id="edbb3-160">8.000 – 2.100 = 5.900</span><span class="sxs-lookup"><span data-stu-id="edbb3-160">8,000 – 2,100 = 5,900</span></span>  | <span data-ttu-id="edbb3-161">7.000 – 2.100 = 4.900</span><span class="sxs-lookup"><span data-stu-id="edbb3-161">7,000 – 2,100 = 4,900</span></span>                 |
| <span data-ttu-id="edbb3-162">Anno 3</span><span class="sxs-lookup"><span data-stu-id="edbb3-162">Year 3</span></span> | <span data-ttu-id="edbb3-163">4.900 × 30% = 1.470</span><span class="sxs-lookup"><span data-stu-id="edbb3-163">4,900 × 30% = 1,470</span></span>                           | <span data-ttu-id="edbb3-164">5.900 – 1.470 = 4.430</span><span class="sxs-lookup"><span data-stu-id="edbb3-164">5,900 – 1,470 = 4,430</span></span>  | <span data-ttu-id="edbb3-165">4.900 – 1.470 = 3.430</span><span class="sxs-lookup"><span data-stu-id="edbb3-165">4,900 – 1,470 = 3,430</span></span>                 |

> [!NOTE]
> <span data-ttu-id="edbb3-166">In genere, quando l'importo calcolato utilizzando il metodo di ammortamento a saldi decrescenti del 150% diventa inferiore all'importo che sarà calcolato utilizzando il metodo a quote costanti, si verifica una conversione al metodo a quote costanti per la vita utile rimanente.</span><span class="sxs-lookup"><span data-stu-id="edbb3-166">Typically, when the amount that is calculated by using the 150% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



