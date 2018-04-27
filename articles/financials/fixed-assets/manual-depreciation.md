---
title: Ammortamento manuale
description: Questo articolo fornisce una panoramica del metodo di ammortamento manuale.
author: twheeloc
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
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5081b3ff940167f305a6e17f97e246e5f8000185
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="manual-depreciation"></a><span data-ttu-id="eecfb-103">Ammortamento manuale</span><span class="sxs-lookup"><span data-stu-id="eecfb-103">Manual depreciation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="eecfb-104">Questo articolo fornisce una panoramica del metodo di ammortamento manuale.</span><span class="sxs-lookup"><span data-stu-id="eecfb-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="eecfb-105">Quando si imposta un profilo di ammortamento cespiti e si seleziona **Manuale** nel campo **Metodo** della pagina **Profili di ammortamento**, l'ammortamento dei cespiti assegnati a questo profilo viene determinato dalla percentuale immessa per ciascun intervallo nell'anno di calendario.</span><span class="sxs-lookup"><span data-stu-id="eecfb-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="eecfb-106">Gli intervalli per cui si impostano percentuali vengono registrati in base al valore selezionato nel campo **Frequenza periodo** della scheda dettaglio **Generale** nella pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="eecfb-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="eecfb-107">È possibile selezionare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="eecfb-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="eecfb-108">Annuale</span><span class="sxs-lookup"><span data-stu-id="eecfb-108">Yearly</span></span>
-   <span data-ttu-id="eecfb-109">Mensile</span><span class="sxs-lookup"><span data-stu-id="eecfb-109">Monthly</span></span>
-   <span data-ttu-id="eecfb-110">Trimestrale</span><span class="sxs-lookup"><span data-stu-id="eecfb-110">Quarterly</span></span>
-   <span data-ttu-id="eecfb-111">Semestrale</span><span class="sxs-lookup"><span data-stu-id="eecfb-111">Half-Yearly</span></span>
-   <span data-ttu-id="eecfb-112">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="eecfb-112">Daily</span></span>

<span data-ttu-id="eecfb-113">Dopo che si seleziona la frequenza del periodo, fare clic su **Programmi manuali** e impostare le percentuali per ciascun intervallo.</span><span class="sxs-lookup"><span data-stu-id="eecfb-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="eecfb-114">I programmi manuali e gli intervalli di registrazione consentono di definire la quota di ammortamento, come illustrato negli esempi più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="eecfb-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="eecfb-115">L'ammortamento manuale viene sempre calcolato come una percentuale del prezzo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="eecfb-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="eecfb-116">Con l'ammortamento manuale, non è necessario che il totale delle percentuali immesse negli intervalli dell'ammortamento ammonti al 100%.</span><span class="sxs-lookup"><span data-stu-id="eecfb-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="eecfb-117">Ammortamento manuale è un metodo di ammortamento flessibile spesso utilizzato per definire un profilo di ammortamento straordinario nella pagina **Libri**, quale un ammortamento non periodico per scopi speciali (ad esempio fiscali).</span><span class="sxs-lookup"><span data-stu-id="eecfb-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="eecfb-118">Esempi</span><span class="sxs-lookup"><span data-stu-id="eecfb-118">Examples</span></span>
<span data-ttu-id="eecfb-119">Prezzo di acquisizione: 11.000,00 Valore di scarto atteso: 1.000,00 Nella seguente tabella vengono visualizzati gli intervalli e le percentuali impostati **Programmazioni profilo di ammortamento cespiti** nella pagina.</span><span class="sxs-lookup"><span data-stu-id="eecfb-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="eecfb-120">Numero intervallo</span><span class="sxs-lookup"><span data-stu-id="eecfb-120">Interval number</span></span> | <span data-ttu-id="eecfb-121">Percentuale</span><span class="sxs-lookup"><span data-stu-id="eecfb-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="eecfb-122">1</span><span class="sxs-lookup"><span data-stu-id="eecfb-122">1</span></span>               | <span data-ttu-id="eecfb-123">10,00</span><span class="sxs-lookup"><span data-stu-id="eecfb-123">10.00</span></span>      |
| <span data-ttu-id="eecfb-124">2</span><span class="sxs-lookup"><span data-stu-id="eecfb-124">2</span></span>               | <span data-ttu-id="eecfb-125">50,00</span><span class="sxs-lookup"><span data-stu-id="eecfb-125">50.00</span></span>      |
| <span data-ttu-id="eecfb-126">3</span><span class="sxs-lookup"><span data-stu-id="eecfb-126">3</span></span>               | <span data-ttu-id="eecfb-127">8,00</span><span class="sxs-lookup"><span data-stu-id="eecfb-127">8.00</span></span>       |

<span data-ttu-id="eecfb-128">L'ammortamento per periodo viene calcolato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="eecfb-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="eecfb-129">Numero intervallo</span><span class="sxs-lookup"><span data-stu-id="eecfb-129">Interval number</span></span> | <span data-ttu-id="eecfb-130">Calcolo della quota di ammortamento annuale</span><span class="sxs-lookup"><span data-stu-id="eecfb-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="eecfb-131">Valore contabile netto alla fine dell'intervallo</span><span class="sxs-lookup"><span data-stu-id="eecfb-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="eecfb-132">1</span><span class="sxs-lookup"><span data-stu-id="eecfb-132">1</span></span>                | <span data-ttu-id="eecfb-133">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="eecfb-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="eecfb-134">10.000 (11.000 – 1.000)</span><span class="sxs-lookup"><span data-stu-id="eecfb-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="eecfb-135">2</span><span class="sxs-lookup"><span data-stu-id="eecfb-135">2</span></span>                | <span data-ttu-id="eecfb-136">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="eecfb-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="eecfb-137">5.000 (10.000 – 5.000)</span><span class="sxs-lookup"><span data-stu-id="eecfb-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="eecfb-138">3</span><span class="sxs-lookup"><span data-stu-id="eecfb-138">3</span></span>                | <span data-ttu-id="eecfb-139">(11.000 – 1.000) × 8% = 800</span><span class="sxs-lookup"><span data-stu-id="eecfb-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="eecfb-140">4.200 (5.000 – 800)</span><span class="sxs-lookup"><span data-stu-id="eecfb-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="eecfb-141">Se si seleziona **Mensile**nel campo **Frequenza periodo**, vengono impostati 12 intervalli di programmi manuali.</span><span class="sxs-lookup"><span data-stu-id="eecfb-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="eecfb-142">Le quote di ammortamento per i primi due intervalli sono mostrate nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="eecfb-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="eecfb-143">Intervallo</span><span class="sxs-lookup"><span data-stu-id="eecfb-143">Interval</span></span> | <span data-ttu-id="eecfb-144">Importo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="eecfb-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="eecfb-145">gennaio</span><span class="sxs-lookup"><span data-stu-id="eecfb-145">January</span></span>  | <span data-ttu-id="eecfb-146">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="eecfb-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="eecfb-147">febbraio</span><span class="sxs-lookup"><span data-stu-id="eecfb-147">February</span></span> | <span data-ttu-id="eecfb-148">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="eecfb-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="eecfb-149">Se si seleziona <strong>Semestrale</strong> nel campo *<strong><em>Frequenza periodo</em>*</strong>, si configurano due intervalli di programmazione manuale.</span><span class="sxs-lookup"><span data-stu-id="eecfb-149">If you select <strong>Half-Yearly</strong> in the *<strong><em>Period frequency</em>* field</strong>, you set up two manual schedule intervals.</span></span> <span data-ttu-id="eecfb-150">Le quote di ammortamento per i primi due intervalli sono mostrate nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="eecfb-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="eecfb-151">Intervallo</span><span class="sxs-lookup"><span data-stu-id="eecfb-151">Interval</span></span>    | <span data-ttu-id="eecfb-152">Importo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="eecfb-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="eecfb-153">30 giugno</span><span class="sxs-lookup"><span data-stu-id="eecfb-153">June 30</span></span>     | <span data-ttu-id="eecfb-154">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="eecfb-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="eecfb-155">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="eecfb-155">December 31</span></span> | <span data-ttu-id="eecfb-156">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="eecfb-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="eecfb-157">Non è necessario che il totale delle percentuali per tutti gli intervalli ammonti a 100.</span><span class="sxs-lookup"><span data-stu-id="eecfb-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="eecfb-158">Tuttavia, verrà visualizzato un messaggio se il valore nel campo **Percentuale cumulativa** della pagina **Programmi profili di ammortamento cespiti** non è **100**.</span><span class="sxs-lookup"><span data-stu-id="eecfb-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>




