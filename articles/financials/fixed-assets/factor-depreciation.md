---
title: Ammortamento basato su coefficiente
description: Questo articolo fornisce una panoramica del metodo di ammortamento basato su coefficiente.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c36441e926cd5a82c802a350adf6b2ed6d6387
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840531"
---
# <a name="factor-depreciation"></a><span data-ttu-id="7118c-103">Ammortamento basato su coefficiente</span><span class="sxs-lookup"><span data-stu-id="7118c-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7118c-104">Questo articolo fornisce una panoramica del metodo di ammortamento basato su coefficiente.</span><span class="sxs-lookup"><span data-stu-id="7118c-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="7118c-105">I fattori sono percentuali utilizzate per l'ammortamento dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="7118c-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="7118c-106">Quando si imposta un profilo di ammortamento cespiti e si seleziona **Fattore** nel campo **Metodo** della pagna **Profili di ammortamento**, è possibile impostare un ammortamento progressivo, digressivo o a quote costanti.</span><span class="sxs-lookup"><span data-stu-id="7118c-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="7118c-107">Nell'ammortamento progressivo, l'importo di ammortamento aumenta con ogni periodo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="7118c-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="7118c-108">Nell'ammortamento digressivo, l'importo di ammortamento per periodo diminuisce nel tempo.</span><span class="sxs-lookup"><span data-stu-id="7118c-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="7118c-109">Nell'ammortamento a quote costanti, l'ammortamento è lo stesso per ogni periodo.</span><span class="sxs-lookup"><span data-stu-id="7118c-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="7118c-110">Nelle regole e negli esempi illustrati di seguito viene descritto come impostare i fattori per ogni tipo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="7118c-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="7118c-111">Quando si seleziona **Fattore** nel campo **Metodo**, sono visualizzati il campo **Fattore** e il campo **Intervallo**.</span><span class="sxs-lookup"><span data-stu-id="7118c-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="7118c-112">Ammortamento progressivo</span><span class="sxs-lookup"><span data-stu-id="7118c-112">Progressive depreciation</span></span>
<span data-ttu-id="7118c-113">Il valore del campo **Fattore** è maggiore di **50**</span><span class="sxs-lookup"><span data-stu-id="7118c-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="7118c-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7118c-114">Example</span></span>

<span data-ttu-id="7118c-115">Si supponga che il prezzo di acquisizione sia 100.000, il fattore sia 70, la vita utile sia 10 anni e l'ammortamento inizi il 1° gennaio.</span><span class="sxs-lookup"><span data-stu-id="7118c-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="7118c-116">Gli importi di ammortamento e valore contabile netto vengono mostrati solo per i primi sei anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="7118c-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="7118c-117">Anno</span><span class="sxs-lookup"><span data-stu-id="7118c-117">Year</span></span> | <span data-ttu-id="7118c-118">Periodo</span><span class="sxs-lookup"><span data-stu-id="7118c-118">Period</span></span>      | <span data-ttu-id="7118c-119">Importo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="7118c-119">Depreciation amount</span></span> | <span data-ttu-id="7118c-120">Importo valore contabile netto</span><span class="sxs-lookup"><span data-stu-id="7118c-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="7118c-121">1</span><span class="sxs-lookup"><span data-stu-id="7118c-121">1</span></span>    | <span data-ttu-id="7118c-122">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-122">December 31</span></span> | <span data-ttu-id="7118c-123">307,69</span><span class="sxs-lookup"><span data-stu-id="7118c-123">307.69</span></span>              | <span data-ttu-id="7118c-124">99.692,31</span><span class="sxs-lookup"><span data-stu-id="7118c-124">99,692.31</span></span>             |
| <span data-ttu-id="7118c-125">2</span><span class="sxs-lookup"><span data-stu-id="7118c-125">2</span></span>    | <span data-ttu-id="7118c-126">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-126">December 31</span></span> | <span data-ttu-id="7118c-127">1.447,21</span><span class="sxs-lookup"><span data-stu-id="7118c-127">1,447.21</span></span>            | <span data-ttu-id="7118c-128">98.245,10</span><span class="sxs-lookup"><span data-stu-id="7118c-128">98,245.10</span></span>             |
| <span data-ttu-id="7118c-129">3</span><span class="sxs-lookup"><span data-stu-id="7118c-129">3</span></span>    | <span data-ttu-id="7118c-130">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-130">December 31</span></span> | <span data-ttu-id="7118c-131">3.104,50</span><span class="sxs-lookup"><span data-stu-id="7118c-131">3,104.50</span></span>            | <span data-ttu-id="7118c-132">95.140,60</span><span class="sxs-lookup"><span data-stu-id="7118c-132">95,140.60</span></span>             |
| <span data-ttu-id="7118c-133">4</span><span class="sxs-lookup"><span data-stu-id="7118c-133">4</span></span>    | <span data-ttu-id="7118c-134">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-134">December 31</span></span> | <span data-ttu-id="7118c-135">5.150,21</span><span class="sxs-lookup"><span data-stu-id="7118c-135">5,150.21</span></span>            | <span data-ttu-id="7118c-136">89.990,39</span><span class="sxs-lookup"><span data-stu-id="7118c-136">89,990.39</span></span>             |
| <span data-ttu-id="7118c-137">5</span><span class="sxs-lookup"><span data-stu-id="7118c-137">5</span></span>    | <span data-ttu-id="7118c-138">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-138">December 31</span></span> | <span data-ttu-id="7118c-139">7.522,95</span><span class="sxs-lookup"><span data-stu-id="7118c-139">7,522.95</span></span>            | <span data-ttu-id="7118c-140">82.467,44</span><span class="sxs-lookup"><span data-stu-id="7118c-140">82,467.44</span></span>             |
| <span data-ttu-id="7118c-141">6</span><span class="sxs-lookup"><span data-stu-id="7118c-141">6</span></span>    | <span data-ttu-id="7118c-142">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-142">December 31</span></span> | <span data-ttu-id="7118c-143">10.184,06</span><span class="sxs-lookup"><span data-stu-id="7118c-143">10,184.06</span></span>           | <span data-ttu-id="7118c-144">72.283,38</span><span class="sxs-lookup"><span data-stu-id="7118c-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="7118c-145">Ammortamento digressivo</span><span class="sxs-lookup"><span data-stu-id="7118c-145">Digressive depreciation</span></span>
<span data-ttu-id="7118c-146">Il valore del campo **Fattore** è minore di **50**.</span><span class="sxs-lookup"><span data-stu-id="7118c-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="7118c-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="7118c-147">Example</span></span>

<span data-ttu-id="7118c-148">Si supponga che il prezzo di acquisizione sia 100.000, il fattore sia 20, la vita utile sia 10 anni e l'ammortamento inizi il 1° gennaio.</span><span class="sxs-lookup"><span data-stu-id="7118c-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="7118c-149">Gli importi di ammortamento e valore contabile netto vengono mostrati solo per i primi sei anni di vita utile.</span><span class="sxs-lookup"><span data-stu-id="7118c-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="7118c-150">Anno</span><span class="sxs-lookup"><span data-stu-id="7118c-150">Year</span></span> | <span data-ttu-id="7118c-151">Periodo</span><span class="sxs-lookup"><span data-stu-id="7118c-151">Period</span></span>      | <span data-ttu-id="7118c-152">Importo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="7118c-152">Depreciation amount</span></span> | <span data-ttu-id="7118c-153">Importo valore contabile netto</span><span class="sxs-lookup"><span data-stu-id="7118c-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="7118c-154">1</span><span class="sxs-lookup"><span data-stu-id="7118c-154">1</span></span>    | <span data-ttu-id="7118c-155">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-155">December 31</span></span> | <span data-ttu-id="7118c-156">56.080,43</span><span class="sxs-lookup"><span data-stu-id="7118c-156">56,080.43</span></span>           | <span data-ttu-id="7118c-157">43.919,57</span><span class="sxs-lookup"><span data-stu-id="7118c-157">43,919.57</span></span>             |
| <span data-ttu-id="7118c-158">2</span><span class="sxs-lookup"><span data-stu-id="7118c-158">2</span></span>    | <span data-ttu-id="7118c-159">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-159">December 31</span></span> | <span data-ttu-id="7118c-160">10.665,70</span><span class="sxs-lookup"><span data-stu-id="7118c-160">10,665.70</span></span>           | <span data-ttu-id="7118c-161">33.253,87</span><span class="sxs-lookup"><span data-stu-id="7118c-161">33,253.87</span></span>             |
| <span data-ttu-id="7118c-162">3</span><span class="sxs-lookup"><span data-stu-id="7118c-162">3</span></span>    | <span data-ttu-id="7118c-163">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-163">December 31</span></span> | <span data-ttu-id="7118c-164">7.156,22</span><span class="sxs-lookup"><span data-stu-id="7118c-164">7,156.22</span></span>            | <span data-ttu-id="7118c-165">26.097,65</span><span class="sxs-lookup"><span data-stu-id="7118c-165">26,097.65</span></span>             |
| <span data-ttu-id="7118c-166">4</span><span class="sxs-lookup"><span data-stu-id="7118c-166">4</span></span>    | <span data-ttu-id="7118c-167">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-167">December 31</span></span> | <span data-ttu-id="7118c-168">5.538,06</span><span class="sxs-lookup"><span data-stu-id="7118c-168">5,538.06</span></span>            | <span data-ttu-id="7118c-169">20.559,59</span><span class="sxs-lookup"><span data-stu-id="7118c-169">20,559.59</span></span>             |
| <span data-ttu-id="7118c-170">5</span><span class="sxs-lookup"><span data-stu-id="7118c-170">5</span></span>    | <span data-ttu-id="7118c-171">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-171">December 31</span></span> | <span data-ttu-id="7118c-172">4.579,89</span><span class="sxs-lookup"><span data-stu-id="7118c-172">4,579.89</span></span>            | <span data-ttu-id="7118c-173">15.979,70</span><span class="sxs-lookup"><span data-stu-id="7118c-173">15,979.70</span></span>             |
| <span data-ttu-id="7118c-174">6</span><span class="sxs-lookup"><span data-stu-id="7118c-174">6</span></span>    | <span data-ttu-id="7118c-175">31 dicembre</span><span class="sxs-lookup"><span data-stu-id="7118c-175">December 31</span></span> | <span data-ttu-id="7118c-176">3.937,36</span><span class="sxs-lookup"><span data-stu-id="7118c-176">3,937.36</span></span>            | <span data-ttu-id="7118c-177">12.042,34</span><span class="sxs-lookup"><span data-stu-id="7118c-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="7118c-178">Ammortamento a quote costanti</span><span class="sxs-lookup"><span data-stu-id="7118c-178">Straight line depreciation</span></span>
<span data-ttu-id="7118c-179">Il valore del campo **Fattore** è uguale a **50**.</span><span class="sxs-lookup"><span data-stu-id="7118c-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="7118c-180">In questo caso, l'ammortamento è lo stesso in ogni periodo ed è consigliabile prendere in considerazione le implicazioni delle scelte effettuate in altri campi, come descritto in [Ammortamento a quote costanti basato sulla vita utile](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="7118c-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>



