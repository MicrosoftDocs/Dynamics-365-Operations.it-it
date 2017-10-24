---
title: Ammortamento basato su coefficiente
description: Questo articolo fornisce una panoramica del metodo di ammortamento basato su coefficiente.
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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b87d96e80b343a2b57db59b5d4c19e70d0a94ea
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="factor-depreciation"></a><span data-ttu-id="0c69f-103">Ammortamento basato su coefficiente</span><span class="sxs-lookup"><span data-stu-id="0c69f-103">Factor depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0c69f-104">Questo articolo fornisce una panoramica del metodo di ammortamento basato su coefficiente.</span><span class="sxs-lookup"><span data-stu-id="0c69f-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="0c69f-105">I fattori sono percentuali utilizzate per l'ammortamento dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="0c69f-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="0c69f-106">Quando si imposta un profilo di ammortamento cespiti e si seleziona **Fattore** nel campo **Metodo** della pagna **Profili di ammortamento**, è possibile impostare un ammortamento progressivo, digressivo o a quote costanti.</span><span class="sxs-lookup"><span data-stu-id="0c69f-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="0c69f-107">Nell'ammortamento progressivo, l'importo di ammortamento aumenta con ogni periodo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="0c69f-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="0c69f-108">Nell'ammortamento digressivo, l'importo di ammortamento per periodo diminuisce nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0c69f-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="0c69f-109">Nell'ammortamento a quote costanti, l'ammortamento è lo stesso per ogni periodo.</span><span class="sxs-lookup"><span data-stu-id="0c69f-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="0c69f-110">Nelle regole e negli esempi illustrati di seguito viene descritto come impostare i fattori per ogni tipo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="0c69f-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="0c69f-111">Quando si seleziona **Fattore** nel campo **Metodo**, sono visualizzati il campo **Fattore** e il campo **Intervallo**.</span><span class="sxs-lookup"><span data-stu-id="0c69f-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="0c69f-112">Ammortamento progressivo</span><span class="sxs-lookup"><span data-stu-id="0c69f-112">Progressive depreciation</span></span>
<span data-ttu-id="0c69f-113">Il valore del campo **Fattore** è maggiore di **50**</span><span class="sxs-lookup"><span data-stu-id="0c69f-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="0c69f-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c69f-114">Example</span></span>

<span data-ttu-id="0c69f-115">Si supponga che il prezzo di acquisizione sia 100.000, il fattore sia 70, la vita utile sia 10 anni e l'ammortamento inizi il 1° gennaio.</span><span class="sxs-lookup"><span data-stu-id="0c69f-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="0c69f-116">Gli importi di ammortamento e valore contabile netto vengono mostrati solo per i primi sei anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="0c69f-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="0c69f-117">Anno</span><span class="sxs-lookup"><span data-stu-id="0c69f-117">Year</span></span> | <span data-ttu-id="0c69f-118">Periodo</span><span class="sxs-lookup"><span data-stu-id="0c69f-118">Period</span></span>      | <span data-ttu-id="0c69f-119">Importo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="0c69f-119">Depreciation amount</span></span> | <span data-ttu-id="0c69f-120">Importo valore contabile netto</span><span class="sxs-lookup"><span data-stu-id="0c69f-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="0c69f-121">1</span><span class="sxs-lookup"><span data-stu-id="0c69f-121">1</span></span>    | <span data-ttu-id="0c69f-122">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-122">December 31</span></span> | <span data-ttu-id="0c69f-123">307,69</span><span class="sxs-lookup"><span data-stu-id="0c69f-123">307.69</span></span>              | <span data-ttu-id="0c69f-124">99.692,31</span><span class="sxs-lookup"><span data-stu-id="0c69f-124">99,692.31</span></span>             |
| <span data-ttu-id="0c69f-125">2</span><span class="sxs-lookup"><span data-stu-id="0c69f-125">2</span></span>    | <span data-ttu-id="0c69f-126">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-126">December 31</span></span> | <span data-ttu-id="0c69f-127">1.447,21</span><span class="sxs-lookup"><span data-stu-id="0c69f-127">1,447.21</span></span>            | <span data-ttu-id="0c69f-128">98.245,10</span><span class="sxs-lookup"><span data-stu-id="0c69f-128">98,245.10</span></span>             |
| <span data-ttu-id="0c69f-129">3</span><span class="sxs-lookup"><span data-stu-id="0c69f-129">3</span></span>    | <span data-ttu-id="0c69f-130">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-130">December 31</span></span> | <span data-ttu-id="0c69f-131">3.104,50</span><span class="sxs-lookup"><span data-stu-id="0c69f-131">3,104.50</span></span>            | <span data-ttu-id="0c69f-132">95.140,60</span><span class="sxs-lookup"><span data-stu-id="0c69f-132">95,140.60</span></span>             |
| <span data-ttu-id="0c69f-133">4</span><span class="sxs-lookup"><span data-stu-id="0c69f-133">4</span></span>    | <span data-ttu-id="0c69f-134">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-134">December 31</span></span> | <span data-ttu-id="0c69f-135">5.150,21</span><span class="sxs-lookup"><span data-stu-id="0c69f-135">5,150.21</span></span>            | <span data-ttu-id="0c69f-136">89.990,39</span><span class="sxs-lookup"><span data-stu-id="0c69f-136">89,990.39</span></span>             |
| <span data-ttu-id="0c69f-137">5</span><span class="sxs-lookup"><span data-stu-id="0c69f-137">5</span></span>    | <span data-ttu-id="0c69f-138">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-138">December 31</span></span> | <span data-ttu-id="0c69f-139">7.522,95</span><span class="sxs-lookup"><span data-stu-id="0c69f-139">7,522.95</span></span>            | <span data-ttu-id="0c69f-140">82.467,44</span><span class="sxs-lookup"><span data-stu-id="0c69f-140">82,467.44</span></span>             |
| <span data-ttu-id="0c69f-141">6</span><span class="sxs-lookup"><span data-stu-id="0c69f-141">6</span></span>    | <span data-ttu-id="0c69f-142">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-142">December 31</span></span> | <span data-ttu-id="0c69f-143">10.184,06</span><span class="sxs-lookup"><span data-stu-id="0c69f-143">10,184.06</span></span>           | <span data-ttu-id="0c69f-144">72.283,38</span><span class="sxs-lookup"><span data-stu-id="0c69f-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="0c69f-145">Ammortamento digressivo</span><span class="sxs-lookup"><span data-stu-id="0c69f-145">Digressive depreciation</span></span>
<span data-ttu-id="0c69f-146">Il valore del campo **Fattore** è minore di **50**.</span><span class="sxs-lookup"><span data-stu-id="0c69f-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="0c69f-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c69f-147">Example</span></span>

<span data-ttu-id="0c69f-148">Si supponga che il prezzo di acquisizione sia 100.000, il fattore sia 20, la vita utile sia 10 anni e l'ammortamento inizi il 1° gennaio.</span><span class="sxs-lookup"><span data-stu-id="0c69f-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="0c69f-149">Gli importi di ammortamento e valore contabile netto vengono mostrati solo per i primi sei anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="0c69f-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="0c69f-150">Anno</span><span class="sxs-lookup"><span data-stu-id="0c69f-150">Year</span></span> | <span data-ttu-id="0c69f-151">Periodo</span><span class="sxs-lookup"><span data-stu-id="0c69f-151">Period</span></span>      | <span data-ttu-id="0c69f-152">Importo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="0c69f-152">Depreciation amount</span></span> | <span data-ttu-id="0c69f-153">Importo valore contabile netto</span><span class="sxs-lookup"><span data-stu-id="0c69f-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="0c69f-154">1</span><span class="sxs-lookup"><span data-stu-id="0c69f-154">1</span></span>    | <span data-ttu-id="0c69f-155">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-155">December 31</span></span> | <span data-ttu-id="0c69f-156">56.080,43</span><span class="sxs-lookup"><span data-stu-id="0c69f-156">56,080.43</span></span>           | <span data-ttu-id="0c69f-157">43.919,57</span><span class="sxs-lookup"><span data-stu-id="0c69f-157">43,919.57</span></span>             |
| <span data-ttu-id="0c69f-158">2</span><span class="sxs-lookup"><span data-stu-id="0c69f-158">2</span></span>    | <span data-ttu-id="0c69f-159">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-159">December 31</span></span> | <span data-ttu-id="0c69f-160">10.665,70</span><span class="sxs-lookup"><span data-stu-id="0c69f-160">10,665.70</span></span>           | <span data-ttu-id="0c69f-161">33.253,87</span><span class="sxs-lookup"><span data-stu-id="0c69f-161">33,253.87</span></span>             |
| <span data-ttu-id="0c69f-162">3</span><span class="sxs-lookup"><span data-stu-id="0c69f-162">3</span></span>    | <span data-ttu-id="0c69f-163">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-163">December 31</span></span> | <span data-ttu-id="0c69f-164">7.156,22</span><span class="sxs-lookup"><span data-stu-id="0c69f-164">7,156.22</span></span>            | <span data-ttu-id="0c69f-165">26.097,65</span><span class="sxs-lookup"><span data-stu-id="0c69f-165">26,097.65</span></span>             |
| <span data-ttu-id="0c69f-166">4</span><span class="sxs-lookup"><span data-stu-id="0c69f-166">4</span></span>    | <span data-ttu-id="0c69f-167">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-167">December 31</span></span> | <span data-ttu-id="0c69f-168">5.538,06</span><span class="sxs-lookup"><span data-stu-id="0c69f-168">5,538.06</span></span>            | <span data-ttu-id="0c69f-169">20.559,59</span><span class="sxs-lookup"><span data-stu-id="0c69f-169">20,559.59</span></span>             |
| <span data-ttu-id="0c69f-170">5</span><span class="sxs-lookup"><span data-stu-id="0c69f-170">5</span></span>    | <span data-ttu-id="0c69f-171">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-171">December 31</span></span> | <span data-ttu-id="0c69f-172">4.579,89</span><span class="sxs-lookup"><span data-stu-id="0c69f-172">4,579.89</span></span>            | <span data-ttu-id="0c69f-173">15.979,70</span><span class="sxs-lookup"><span data-stu-id="0c69f-173">15,979.70</span></span>             |
| <span data-ttu-id="0c69f-174">6</span><span class="sxs-lookup"><span data-stu-id="0c69f-174">6</span></span>    | <span data-ttu-id="0c69f-175">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="0c69f-175">December 31</span></span> | <span data-ttu-id="0c69f-176">3.937,36</span><span class="sxs-lookup"><span data-stu-id="0c69f-176">3,937.36</span></span>            | <span data-ttu-id="0c69f-177">12.042,34</span><span class="sxs-lookup"><span data-stu-id="0c69f-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="0c69f-178">Ammortamento a quote costanti</span><span class="sxs-lookup"><span data-stu-id="0c69f-178">Straight line depreciation</span></span>
<span data-ttu-id="0c69f-179">Il valore del campo **Fattore** è uguale a **50**.</span><span class="sxs-lookup"><span data-stu-id="0c69f-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="0c69f-180">In questo caso, l'ammortamento è lo stesso in ogni periodo ed è consigliabile prendere in considerazione le implicazioni delle scelte effettuate in altri campi, come descritto in [Ammortamento a quote costanti basato sulla vita utile](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="0c69f-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>




