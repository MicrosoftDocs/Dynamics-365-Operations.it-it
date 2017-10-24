---
title: "Rivalutazione della valuta in una società di consolidamento"
description: "In questo argomento viene descritto come rivalutare la valuta in una società di consolidamento."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c91399e96c54f7cf9968a15e3fff90c3a71ca6
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="528d9-103">Rivalutazione della valuta in una società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="528d9-103">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="528d9-104">Quando si consolidano i dati da una valuta di contabilizzazione a un'altra, è necessario eseguire la rivalutazione della valuta in presenza di una variazione nei tassi di cambio, affinché i saldi dei conti vengano rivalutati correttamente.</span><span class="sxs-lookup"><span data-stu-id="528d9-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="528d9-105">Quando si consolidano i dati, utilizzare la scheda **Conversione valuta** per selezionare i tassi di cambio iniziali per la conversione durante il processo di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="528d9-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="528d9-106">Dopo che si è inserito un nuovo tasso di cambio (ad esempio nel mese successivo), è necessario rivalutare i saldi dei conti.</span><span class="sxs-lookup"><span data-stu-id="528d9-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="528d9-107">I profitti non realizzati o le perdite non realizzate vengono aggiornati di conseguenza, in base al nuovo tasso di cambio e alla data.</span><span class="sxs-lookup"><span data-stu-id="528d9-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="528d9-108">Nell'esempio riportato di seguito vengono mostrare le registrazioni contabili che vengono create durante il processo.</span><span class="sxs-lookup"><span data-stu-id="528d9-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="528d9-109">Impostazione società</span><span class="sxs-lookup"><span data-stu-id="528d9-109">Company setup</span></span>
-   <span data-ttu-id="528d9-110">**Società operative/di origine (USMF)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="528d9-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="528d9-111">**Società consolidata (CON)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="528d9-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="528d9-112">**Profitto realizzato** - Conto CoGe 801500</span><span class="sxs-lookup"><span data-stu-id="528d9-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="528d9-113">**Perdita realizzata** - Conto CoGe 801600</span><span class="sxs-lookup"><span data-stu-id="528d9-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="528d9-114">**Profitto realizzato**- - Conto CoGe 801600</span><span class="sxs-lookup"><span data-stu-id="528d9-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="528d9-115">**Perdita realizzata** - Conto CoGe 801400</span><span class="sxs-lookup"><span data-stu-id="528d9-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="528d9-116">Conversioni originali</span><span class="sxs-lookup"><span data-stu-id="528d9-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="528d9-117">Transazioni di ricevuta in USMF</span><span class="sxs-lookup"><span data-stu-id="528d9-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="528d9-118">Data</span><span class="sxs-lookup"><span data-stu-id="528d9-118">Date</span></span>       | <span data-ttu-id="528d9-119">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="528d9-119">Ledger account</span></span>               | <span data-ttu-id="528d9-120">Valuta</span><span class="sxs-lookup"><span data-stu-id="528d9-120">Currency</span></span> | <span data-ttu-id="528d9-121">Importo</span><span class="sxs-lookup"><span data-stu-id="528d9-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="528d9-122">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="528d9-122">10/11/2015</span></span> | <span data-ttu-id="528d9-123">110110 – Contanti</span><span class="sxs-lookup"><span data-stu-id="528d9-123">110110 – Cash</span></span>                | <span data-ttu-id="528d9-124">GBP</span><span class="sxs-lookup"><span data-stu-id="528d9-124">USD</span></span>      | <span data-ttu-id="528d9-125">500</span><span class="sxs-lookup"><span data-stu-id="528d9-125">500</span></span>    |
| <span data-ttu-id="528d9-126">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="528d9-126">10/11/2015</span></span> | <span data-ttu-id="528d9-127">130100 – Contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="528d9-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="528d9-128">GBP</span><span class="sxs-lookup"><span data-stu-id="528d9-128">USD</span></span>      | <span data-ttu-id="528d9-129">-500</span><span class="sxs-lookup"><span data-stu-id="528d9-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="528d9-130">Tassi di cambio</span><span class="sxs-lookup"><span data-stu-id="528d9-130">Exchange rates</span></span>
| <span data-ttu-id="528d9-131">Dalla valuta</span><span class="sxs-lookup"><span data-stu-id="528d9-131">From currency</span></span> | <span data-ttu-id="528d9-132">Alla valuta</span><span class="sxs-lookup"><span data-stu-id="528d9-132">To currency</span></span> | <span data-ttu-id="528d9-133">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="528d9-133">Start date</span></span> | <span data-ttu-id="528d9-134">Tasso di cambio</span><span class="sxs-lookup"><span data-stu-id="528d9-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="528d9-135">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-135">EUR</span></span>           | <span data-ttu-id="528d9-136">GBP</span><span class="sxs-lookup"><span data-stu-id="528d9-136">USD</span></span>         | <span data-ttu-id="528d9-137">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="528d9-137">10/1/2015</span></span>  | <span data-ttu-id="528d9-138">200</span><span class="sxs-lookup"><span data-stu-id="528d9-138">200</span></span>           |
| <span data-ttu-id="528d9-139">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-139">EUR</span></span>           | <span data-ttu-id="528d9-140">GBP</span><span class="sxs-lookup"><span data-stu-id="528d9-140">USD</span></span>         | <span data-ttu-id="528d9-141">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="528d9-141">11/1/2015</span></span>  | <span data-ttu-id="528d9-142">150</span><span class="sxs-lookup"><span data-stu-id="528d9-142">150</span></span>           |
| <span data-ttu-id="528d9-143">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-143">EUR</span></span>           | <span data-ttu-id="528d9-144">GBP</span><span class="sxs-lookup"><span data-stu-id="528d9-144">USD</span></span>         | <span data-ttu-id="528d9-145">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="528d9-145">12/1/2012</span></span>  | <span data-ttu-id="528d9-146">100</span><span class="sxs-lookup"><span data-stu-id="528d9-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="528d9-147">Eseguire il consolidamento per ottobre 2015</span><span class="sxs-lookup"><span data-stu-id="528d9-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="528d9-148">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="528d9-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="528d9-149">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="528d9-149">Ledger account</span></span> | <span data-ttu-id="528d9-150">Valuta</span><span class="sxs-lookup"><span data-stu-id="528d9-150">Currency</span></span> | <span data-ttu-id="528d9-151">Importo</span><span class="sxs-lookup"><span data-stu-id="528d9-151">Amount</span></span> | <span data-ttu-id="528d9-152">Calcolo</span><span class="sxs-lookup"><span data-stu-id="528d9-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="528d9-153">110110</span><span class="sxs-lookup"><span data-stu-id="528d9-153">110110</span></span>         | <span data-ttu-id="528d9-154">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-154">EUR</span></span>      | <span data-ttu-id="528d9-155">250</span><span class="sxs-lookup"><span data-stu-id="528d9-155">250</span></span>    | <span data-ttu-id="528d9-156">500 EUR × 50%</span><span class="sxs-lookup"><span data-stu-id="528d9-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="528d9-157">130100</span><span class="sxs-lookup"><span data-stu-id="528d9-157">130100</span></span>         | <span data-ttu-id="528d9-158">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-158">EUR</span></span>      | <span data-ttu-id="528d9-159">-250</span><span class="sxs-lookup"><span data-stu-id="528d9-159">-250</span></span>   | <span data-ttu-id="528d9-160">-500 EUR × 50%</span><span class="sxs-lookup"><span data-stu-id="528d9-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="528d9-161">Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 30 novembre 2015</span><span class="sxs-lookup"><span data-stu-id="528d9-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="528d9-162">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="528d9-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="528d9-163">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="528d9-163">Ledger account</span></span> | <span data-ttu-id="528d9-164">Valuta</span><span class="sxs-lookup"><span data-stu-id="528d9-164">Currency</span></span> | <span data-ttu-id="528d9-165">Importo</span><span class="sxs-lookup"><span data-stu-id="528d9-165">Amount</span></span>  | <span data-ttu-id="528d9-166">Calcolo</span><span class="sxs-lookup"><span data-stu-id="528d9-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="528d9-167">110110</span><span class="sxs-lookup"><span data-stu-id="528d9-167">110110</span></span>         | <span data-ttu-id="528d9-168">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-168">EUR</span></span>      | <span data-ttu-id="528d9-169">333,33</span><span class="sxs-lookup"><span data-stu-id="528d9-169">333.33</span></span>  | <span data-ttu-id="528d9-170">Importo originale di 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="528d9-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="528d9-171">130100</span><span class="sxs-lookup"><span data-stu-id="528d9-171">130100</span></span>         | <span data-ttu-id="528d9-172">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-172">EUR</span></span>      | <span data-ttu-id="528d9-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="528d9-173">-333.33</span></span> | <span data-ttu-id="528d9-174">Importo originale di -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="528d9-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="528d9-175">801400</span><span class="sxs-lookup"><span data-stu-id="528d9-175">801400</span></span>         | <span data-ttu-id="528d9-176">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-176">EUR</span></span>      | <span data-ttu-id="528d9-177">83,33</span><span class="sxs-lookup"><span data-stu-id="528d9-177">83.33</span></span>   | <span data-ttu-id="528d9-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="528d9-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="528d9-179">801600</span><span class="sxs-lookup"><span data-stu-id="528d9-179">801600</span></span>         | <span data-ttu-id="528d9-180">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-180">EUR</span></span>      | <span data-ttu-id="528d9-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="528d9-181">-83.33</span></span>  | <span data-ttu-id="528d9-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="528d9-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="528d9-183">Verranno visualizzate transazioni aggiuntive per gli importi in valuta di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="528d9-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="528d9-184">Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 31 dicembre 2015</span><span class="sxs-lookup"><span data-stu-id="528d9-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="528d9-185">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="528d9-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="528d9-186">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="528d9-186">Ledger account</span></span> | <span data-ttu-id="528d9-187">Valuta</span><span class="sxs-lookup"><span data-stu-id="528d9-187">Currency</span></span> | <span data-ttu-id="528d9-188">Importo</span><span class="sxs-lookup"><span data-stu-id="528d9-188">Amount</span></span>  | <span data-ttu-id="528d9-189">Calcolo</span><span class="sxs-lookup"><span data-stu-id="528d9-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="528d9-190">110110</span><span class="sxs-lookup"><span data-stu-id="528d9-190">110110</span></span>         | <span data-ttu-id="528d9-191">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-191">EUR</span></span>      | <span data-ttu-id="528d9-192">500,00</span><span class="sxs-lookup"><span data-stu-id="528d9-192">500.00</span></span>  | <span data-ttu-id="528d9-193">Importo originale di 500 × 1</span><span class="sxs-lookup"><span data-stu-id="528d9-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="528d9-194">130100</span><span class="sxs-lookup"><span data-stu-id="528d9-194">130100</span></span>         | <span data-ttu-id="528d9-195">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-195">EUR</span></span>      | <span data-ttu-id="528d9-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="528d9-196">-500.00</span></span> | <span data-ttu-id="528d9-197">Importo originale di -500 × 1</span><span class="sxs-lookup"><span data-stu-id="528d9-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="528d9-198">801400</span><span class="sxs-lookup"><span data-stu-id="528d9-198">801400</span></span>         | <span data-ttu-id="528d9-199">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-199">EUR</span></span>      | <span data-ttu-id="528d9-200">250</span><span class="sxs-lookup"><span data-stu-id="528d9-200">250</span></span>     | <span data-ttu-id="528d9-201">500 – 333.33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="528d9-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="528d9-202">801600</span><span class="sxs-lookup"><span data-stu-id="528d9-202">801600</span></span>         | <span data-ttu-id="528d9-203">EUR</span><span class="sxs-lookup"><span data-stu-id="528d9-203">EUR</span></span>      | <span data-ttu-id="528d9-204">-250</span><span class="sxs-lookup"><span data-stu-id="528d9-204">-250</span></span>    | <span data-ttu-id="528d9-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="528d9-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






