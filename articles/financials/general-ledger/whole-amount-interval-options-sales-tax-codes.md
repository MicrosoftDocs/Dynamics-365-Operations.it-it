---
title: Opzioni Importo totale e Intervallo per i codici IVA
description: Questo articolo illustra le opzioni del campo Metodo di calcolo sui codici IVA e come si calcola l'IVA per intervalli e interi importi.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6ac0e2abcb5dce58ad16737a0ef689ceaeb50c44
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="86cfc-103">Opzioni Importo totale e Intervallo per i codici IVA</span><span class="sxs-lookup"><span data-stu-id="86cfc-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]



<span data-ttu-id="86cfc-104">Questo articolo illustra le opzioni del campo Metodo di calcolo sui codici IVA e come si calcola l'IVA per intervalli e interi importi.</span><span class="sxs-lookup"><span data-stu-id="86cfc-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="86cfc-105">È possibile impostare un codice IVA da calcolare in base a un importo totale o a un importo di intervallo.</span><span class="sxs-lookup"><span data-stu-id="86cfc-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="86cfc-106">Nella pagina Codici IVA utilizzare il campo Metodo di calcolo nella Scheda dettaglio Calcolo per selezionare la modalità di calcolo di un codice IVA.</span><span class="sxs-lookup"><span data-stu-id="86cfc-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
-   <span data-ttu-id="86cfc-107">Importo totale - L'aliquota IVA si applica all'intero importo tassabile.</span><span class="sxs-lookup"><span data-stu-id="86cfc-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
-   <span data-ttu-id="86cfc-108">Intervallo - L'importo tassabile è diviso in parti, ognuna delle quali rientra in un intervallo con un'aliquota IVA specifica.</span><span class="sxs-lookup"><span data-stu-id="86cfc-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="86cfc-109">La parte dell'importo che rientra in un determinato intervallo viene tassata in base all'aliquota IVA per tale intervallo.</span><span class="sxs-lookup"><span data-stu-id="86cfc-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="86cfc-110">L'IVA è la somma degli importi delle imposte calcolati per ciascun intervallo di importi.</span><span class="sxs-lookup"><span data-stu-id="86cfc-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
> [!NOTE]                                                                                                                              
> <span data-ttu-id="86cfc-111">L'opzione di intervallo è disponibile solo quando si seleziona la riga nel campo del metodo di calcolo nell'area IVA della pagina dei parametri di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="86cfc-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="86cfc-112">Gli intervalli vengono impostati nella pagina di valori di codice IVA immettendo gli importi limiti minimi e massimi per aliquota.</span><span class="sxs-lookup"><span data-stu-id="86cfc-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="86cfc-113">Per calcolare le imposte per tutti gli importi tassabili, indipendentemente dal metodo selezionato, è necessario che gli intervalli siano conformi alle seguenti regole:</span><span class="sxs-lookup"><span data-stu-id="86cfc-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="86cfc-114">Il primo intervallo deve avere un limite minimo pari a zero.</span><span class="sxs-lookup"><span data-stu-id="86cfc-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="86cfc-115">L'ultimo intervallo deve avere un limite massimo pari a zero, che indica l'infinito.</span><span class="sxs-lookup"><span data-stu-id="86cfc-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="86cfc-116">Il limite massimo di un intervallo deve corrispondere al limite minimo dell'intervallo successivo.</span><span class="sxs-lookup"><span data-stu-id="86cfc-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="86cfc-117">Se un importo corrisponde al limite massimo dell'intervallo precedente e al limite minimo dell'intervallo successivo, all'importo viene applicata l'aliquota IVA del primo intervallo.</span><span class="sxs-lookup"><span data-stu-id="86cfc-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="86cfc-118">Se un importo non è compreso negli intervalli definiti dai limiti superiore e inferiore, viene applicata un'aliquota IVA pari a 0.</span><span class="sxs-lookup"><span data-stu-id="86cfc-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="86cfc-119">Esempio: metodo di calcolo dell'importo totale</span><span class="sxs-lookup"><span data-stu-id="86cfc-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="86cfc-120">Nella pagina dei valori del codice IVA vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="86cfc-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>
|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="86cfc-121">**Limite minimo**</span><span class="sxs-lookup"><span data-stu-id="86cfc-121">**Minimum limit**</span></span> | <span data-ttu-id="86cfc-122">**Limite massimo**</span><span class="sxs-lookup"><span data-stu-id="86cfc-122">**Maximum limit**</span></span> | <span data-ttu-id="86cfc-123">**Aliquota IVA**</span><span class="sxs-lookup"><span data-stu-id="86cfc-123">**Tax rate**</span></span> |
| <span data-ttu-id="86cfc-124">0,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-124">0.00</span></span>              | <span data-ttu-id="86cfc-125">50,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-125">50.00</span></span>             | <span data-ttu-id="86cfc-126">30%</span><span class="sxs-lookup"><span data-stu-id="86cfc-126">30%</span></span>          |
| <span data-ttu-id="86cfc-127">50,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-127">50.00</span></span>             | <span data-ttu-id="86cfc-128">100,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-128">100.00</span></span>            | <span data-ttu-id="86cfc-129">20%</span><span class="sxs-lookup"><span data-stu-id="86cfc-129">20%</span></span>          |
| <span data-ttu-id="86cfc-130">100,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-130">100.00</span></span>            | <span data-ttu-id="86cfc-131">0,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-131">0.00</span></span>              | <span data-ttu-id="86cfc-132">10%</span><span class="sxs-lookup"><span data-stu-id="86cfc-132">10%</span></span>          |

<span data-ttu-id="86cfc-133">L'IVA viene calcolata sull'intero importo tassabile.</span><span class="sxs-lookup"><span data-stu-id="86cfc-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="86cfc-134">Importo tassabile (prezzo)</span><span class="sxs-lookup"><span data-stu-id="86cfc-134">Taxable amount (price)</span></span> | <span data-ttu-id="86cfc-135">Calcolo</span><span class="sxs-lookup"><span data-stu-id="86cfc-135">Calculation</span></span>    | <span data-ttu-id="86cfc-136">IVA</span><span class="sxs-lookup"><span data-stu-id="86cfc-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="86cfc-137">35,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-137">35.00</span></span>                  | <span data-ttu-id="86cfc-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="86cfc-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="86cfc-139">10,50</span><span class="sxs-lookup"><span data-stu-id="86cfc-139">10.50</span></span>     |
| <span data-ttu-id="86cfc-140">50,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-140">50.00</span></span>                  | <span data-ttu-id="86cfc-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="86cfc-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="86cfc-142">15,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-142">15.00</span></span>     |
| <span data-ttu-id="86cfc-143">85,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-143">85.00</span></span>                  | <span data-ttu-id="86cfc-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="86cfc-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="86cfc-145">17,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-145">17.00</span></span>     |
| <span data-ttu-id="86cfc-146">305,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-146">305.00</span></span>                 | <span data-ttu-id="86cfc-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="86cfc-147">305.00 \* 0.10</span></span> | <span data-ttu-id="86cfc-148">30,50</span><span class="sxs-lookup"><span data-stu-id="86cfc-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="86cfc-149">Esempio: metodo di calcolo dell'intervallo</span><span class="sxs-lookup"><span data-stu-id="86cfc-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="86cfc-150">Nella pagina Valori vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="86cfc-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="86cfc-151">**Limite minimo**</span><span class="sxs-lookup"><span data-stu-id="86cfc-151">**Minimum limit**</span></span> | <span data-ttu-id="86cfc-152">**Limite massimo**</span><span class="sxs-lookup"><span data-stu-id="86cfc-152">**Maximum limit**</span></span> | <span data-ttu-id="86cfc-153">**Aliquota IVA**</span><span class="sxs-lookup"><span data-stu-id="86cfc-153">**Tax rate**</span></span> |
| <span data-ttu-id="86cfc-154">0,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-154">0.00</span></span>              | <span data-ttu-id="86cfc-155">50,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-155">50.00</span></span>             | <span data-ttu-id="86cfc-156">30%</span><span class="sxs-lookup"><span data-stu-id="86cfc-156">30%</span></span>          |
| <span data-ttu-id="86cfc-157">50,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-157">50.00</span></span>             | <span data-ttu-id="86cfc-158">100,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-158">100.00</span></span>            | <span data-ttu-id="86cfc-159">20%</span><span class="sxs-lookup"><span data-stu-id="86cfc-159">20%</span></span>          |
| <span data-ttu-id="86cfc-160">100,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-160">100.00</span></span>            | <span data-ttu-id="86cfc-161">0,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-161">0.00</span></span>              | <span data-ttu-id="86cfc-162">10%</span><span class="sxs-lookup"><span data-stu-id="86cfc-162">10%</span></span>          |

<span data-ttu-id="86cfc-163">L'IVA è la somma degli importi delle imposte calcolati per ciascun intervallo di importi.</span><span class="sxs-lookup"><span data-stu-id="86cfc-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="86cfc-164">Importo tassabile (prezzo)</span><span class="sxs-lookup"><span data-stu-id="86cfc-164">Taxable amount (price)</span></span> | <span data-ttu-id="86cfc-165">Calcolo</span><span class="sxs-lookup"><span data-stu-id="86cfc-165">Calculation</span></span>                                                               | <span data-ttu-id="86cfc-166">IVA</span><span class="sxs-lookup"><span data-stu-id="86cfc-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="86cfc-167">35,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-167">35.00</span></span>                  | <span data-ttu-id="86cfc-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="86cfc-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="86cfc-169">10,50</span><span class="sxs-lookup"><span data-stu-id="86cfc-169">10.50</span></span>     |
| <span data-ttu-id="86cfc-170">50,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-170">50.00</span></span>                  | <span data-ttu-id="86cfc-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="86cfc-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="86cfc-172">15,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-172">15.00</span></span>     |
| <span data-ttu-id="86cfc-173">85,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-173">85.00</span></span>                  | <span data-ttu-id="86cfc-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="86cfc-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="86cfc-175">22,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-175">22.00</span></span>     |
| <span data-ttu-id="86cfc-176">305,00</span><span class="sxs-lookup"><span data-stu-id="86cfc-176">305.00</span></span>                 | <span data-ttu-id="86cfc-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="86cfc-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="86cfc-178">45,50</span><span class="sxs-lookup"><span data-stu-id="86cfc-178">45.50</span></span>     |

 

<span data-ttu-id="86cfc-179">Per ulteriori informazioni, vedere [Determinare le aliquote IVA in base ai campi Imponibile marginale e Metodo di calcolo](marginal-base-field.md).</span><span class="sxs-lookup"><span data-stu-id="86cfc-179">For more information, see [Determining sale tax rates based on the Marginal base and Calculation method fields](marginal-base-field.md).</span></span>






