---
title: "Rivalutazione della valuta in una società di consolidamento"
description: 
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 643af8d771685fe8fd652b353d41f2679e0bef8b
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="36c03-102">Rivalutazione della valuta in una società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="36c03-102">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="36c03-103">Quando si consolidano i dati da una valuta di contabilizzazione a un'altra, è necessario eseguire la rivalutazione della valuta in presenza di una variazione nei tassi di cambio, affinché i saldi dei conti vengano rivalutati correttamente.</span><span class="sxs-lookup"><span data-stu-id="36c03-103">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="36c03-104">Quando si consolidano i dati, utilizzare la scheda **Conversione valuta** per selezionare i tassi di cambio iniziali per la conversione durante il processo di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="36c03-104">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="36c03-105">Dopo che si è inserito un nuovo tasso di cambio (ad esempio nel mese successivo), è necessario rivalutare i saldi dei conti.</span><span class="sxs-lookup"><span data-stu-id="36c03-105">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="36c03-106">I profitti non realizzati o le perdite non realizzate vengono aggiornati di conseguenza, in base al nuovo tasso di cambio e alla data.</span><span class="sxs-lookup"><span data-stu-id="36c03-106">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="36c03-107">Nell'esempio riportato di seguito vengono mostrare le registrazioni contabili che vengono create durante il processo.</span><span class="sxs-lookup"><span data-stu-id="36c03-107">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="36c03-108">Impostazione società</span><span class="sxs-lookup"><span data-stu-id="36c03-108">Company setup</span></span>
-   <span data-ttu-id="36c03-109">**Società operative/di origine (USMF)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="36c03-109">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="36c03-110">**Società consolidata (CON)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="36c03-110">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="36c03-111">**Profitto realizzato** - Conto CoGe 801500</span><span class="sxs-lookup"><span data-stu-id="36c03-111">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="36c03-112">**Perdita realizzata** - Conto CoGe 801600</span><span class="sxs-lookup"><span data-stu-id="36c03-112">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="36c03-113">**Profitto realizzato**- - Conto CoGe 801600</span><span class="sxs-lookup"><span data-stu-id="36c03-113">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="36c03-114">**Perdita realizzata** - Conto CoGe 801400</span><span class="sxs-lookup"><span data-stu-id="36c03-114">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="36c03-115">Conversioni originali</span><span class="sxs-lookup"><span data-stu-id="36c03-115">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="36c03-116">Transazioni di ricevuta in USMF</span><span class="sxs-lookup"><span data-stu-id="36c03-116">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="36c03-117">Data</span><span class="sxs-lookup"><span data-stu-id="36c03-117">Date</span></span>       | <span data-ttu-id="36c03-118">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="36c03-118">Ledger account</span></span>               | <span data-ttu-id="36c03-119">Valuta</span><span class="sxs-lookup"><span data-stu-id="36c03-119">Currency</span></span> | <span data-ttu-id="36c03-120">Importo</span><span class="sxs-lookup"><span data-stu-id="36c03-120">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="36c03-121">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="36c03-121">10/11/2015</span></span> | <span data-ttu-id="36c03-122">110110 – Contanti</span><span class="sxs-lookup"><span data-stu-id="36c03-122">110110 – Cash</span></span>                | <span data-ttu-id="36c03-123">GBP</span><span class="sxs-lookup"><span data-stu-id="36c03-123">USD</span></span>      | <span data-ttu-id="36c03-124">500</span><span class="sxs-lookup"><span data-stu-id="36c03-124">500</span></span>    |
| <span data-ttu-id="36c03-125">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="36c03-125">10/11/2015</span></span> | <span data-ttu-id="36c03-126">130100 – Contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="36c03-126">130100 – Accounts Receivable</span></span> | <span data-ttu-id="36c03-127">GBP</span><span class="sxs-lookup"><span data-stu-id="36c03-127">USD</span></span>      | <span data-ttu-id="36c03-128">-500</span><span class="sxs-lookup"><span data-stu-id="36c03-128">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="36c03-129">Tassi di cambio</span><span class="sxs-lookup"><span data-stu-id="36c03-129">Exchange rates</span></span>
| <span data-ttu-id="36c03-130">Dalla valuta</span><span class="sxs-lookup"><span data-stu-id="36c03-130">From currency</span></span> | <span data-ttu-id="36c03-131">Alla valuta</span><span class="sxs-lookup"><span data-stu-id="36c03-131">To currency</span></span> | <span data-ttu-id="36c03-132">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="36c03-132">Start date</span></span> | <span data-ttu-id="36c03-133">Tasso di cambio</span><span class="sxs-lookup"><span data-stu-id="36c03-133">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="36c03-134">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-134">EUR</span></span>           | <span data-ttu-id="36c03-135">GBP</span><span class="sxs-lookup"><span data-stu-id="36c03-135">USD</span></span>         | <span data-ttu-id="36c03-136">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="36c03-136">10/1/2015</span></span>  | <span data-ttu-id="36c03-137">200</span><span class="sxs-lookup"><span data-stu-id="36c03-137">200</span></span>           |
| <span data-ttu-id="36c03-138">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-138">EUR</span></span>           | <span data-ttu-id="36c03-139">GBP</span><span class="sxs-lookup"><span data-stu-id="36c03-139">USD</span></span>         | <span data-ttu-id="36c03-140">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="36c03-140">11/1/2015</span></span>  | <span data-ttu-id="36c03-141">150</span><span class="sxs-lookup"><span data-stu-id="36c03-141">150</span></span>           |
| <span data-ttu-id="36c03-142">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-142">EUR</span></span>           | <span data-ttu-id="36c03-143">GBP</span><span class="sxs-lookup"><span data-stu-id="36c03-143">USD</span></span>         | <span data-ttu-id="36c03-144">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="36c03-144">12/1/2012</span></span>  | <span data-ttu-id="36c03-145">100</span><span class="sxs-lookup"><span data-stu-id="36c03-145">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="36c03-146">Eseguire il consolidamento per ottobre 2015</span><span class="sxs-lookup"><span data-stu-id="36c03-146">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="36c03-147">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="36c03-147">Balances in the consolidation company</span></span>

| <span data-ttu-id="36c03-148">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="36c03-148">Ledger account</span></span> | <span data-ttu-id="36c03-149">Valuta</span><span class="sxs-lookup"><span data-stu-id="36c03-149">Currency</span></span> | <span data-ttu-id="36c03-150">Importo</span><span class="sxs-lookup"><span data-stu-id="36c03-150">Amount</span></span> | <span data-ttu-id="36c03-151">Calcolo</span><span class="sxs-lookup"><span data-stu-id="36c03-151">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="36c03-152">110110</span><span class="sxs-lookup"><span data-stu-id="36c03-152">110110</span></span>         | <span data-ttu-id="36c03-153">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-153">EUR</span></span>      | <span data-ttu-id="36c03-154">250</span><span class="sxs-lookup"><span data-stu-id="36c03-154">250</span></span>    | <span data-ttu-id="36c03-155">500 EUR × 50%</span><span class="sxs-lookup"><span data-stu-id="36c03-155">500 USD × 50%</span></span>  |
| <span data-ttu-id="36c03-156">130100</span><span class="sxs-lookup"><span data-stu-id="36c03-156">130100</span></span>         | <span data-ttu-id="36c03-157">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-157">EUR</span></span>      | <span data-ttu-id="36c03-158">-250</span><span class="sxs-lookup"><span data-stu-id="36c03-158">-250</span></span>   | <span data-ttu-id="36c03-159">-500 EUR × 50%</span><span class="sxs-lookup"><span data-stu-id="36c03-159">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="36c03-160">Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 30 novembre 2015</span><span class="sxs-lookup"><span data-stu-id="36c03-160">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="36c03-161">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="36c03-161">Balances in the consolidation company</span></span>

| <span data-ttu-id="36c03-162">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="36c03-162">Ledger account</span></span> | <span data-ttu-id="36c03-163">Valuta</span><span class="sxs-lookup"><span data-stu-id="36c03-163">Currency</span></span> | <span data-ttu-id="36c03-164">Importo</span><span class="sxs-lookup"><span data-stu-id="36c03-164">Amount</span></span>  | <span data-ttu-id="36c03-165">Calcolo</span><span class="sxs-lookup"><span data-stu-id="36c03-165">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="36c03-166">110110</span><span class="sxs-lookup"><span data-stu-id="36c03-166">110110</span></span>         | <span data-ttu-id="36c03-167">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-167">EUR</span></span>      | <span data-ttu-id="36c03-168">333,33</span><span class="sxs-lookup"><span data-stu-id="36c03-168">333.33</span></span>  | <span data-ttu-id="36c03-169">Importo originale di 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="36c03-169">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="36c03-170">130100</span><span class="sxs-lookup"><span data-stu-id="36c03-170">130100</span></span>         | <span data-ttu-id="36c03-171">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-171">EUR</span></span>      | <span data-ttu-id="36c03-172">-333,33</span><span class="sxs-lookup"><span data-stu-id="36c03-172">-333.33</span></span> | <span data-ttu-id="36c03-173">Importo originale di -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="36c03-173">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="36c03-174">801400</span><span class="sxs-lookup"><span data-stu-id="36c03-174">801400</span></span>         | <span data-ttu-id="36c03-175">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-175">EUR</span></span>      | <span data-ttu-id="36c03-176">83,33</span><span class="sxs-lookup"><span data-stu-id="36c03-176">83.33</span></span>   | <span data-ttu-id="36c03-177">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="36c03-177">333.33 – 250</span></span>                       |
| <span data-ttu-id="36c03-178">801600</span><span class="sxs-lookup"><span data-stu-id="36c03-178">801600</span></span>         | <span data-ttu-id="36c03-179">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-179">EUR</span></span>      | <span data-ttu-id="36c03-180">-83,33</span><span class="sxs-lookup"><span data-stu-id="36c03-180">-83.33</span></span>  | <span data-ttu-id="36c03-181">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="36c03-181">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="36c03-182">Verranno visualizzate transazioni aggiuntive per gli importi in valuta di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="36c03-182">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="36c03-183">Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 31 dicembre 2015</span><span class="sxs-lookup"><span data-stu-id="36c03-183">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="36c03-184">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="36c03-184">Balances in the consolidation company</span></span>

| <span data-ttu-id="36c03-185">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="36c03-185">Ledger account</span></span> | <span data-ttu-id="36c03-186">Valuta</span><span class="sxs-lookup"><span data-stu-id="36c03-186">Currency</span></span> | <span data-ttu-id="36c03-187">Importo</span><span class="sxs-lookup"><span data-stu-id="36c03-187">Amount</span></span>  | <span data-ttu-id="36c03-188">Calcolo</span><span class="sxs-lookup"><span data-stu-id="36c03-188">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="36c03-189">110110</span><span class="sxs-lookup"><span data-stu-id="36c03-189">110110</span></span>         | <span data-ttu-id="36c03-190">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-190">EUR</span></span>      | <span data-ttu-id="36c03-191">500,00</span><span class="sxs-lookup"><span data-stu-id="36c03-191">500.00</span></span>  | <span data-ttu-id="36c03-192">Importo originale di 500 × 1</span><span class="sxs-lookup"><span data-stu-id="36c03-192">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="36c03-193">130100</span><span class="sxs-lookup"><span data-stu-id="36c03-193">130100</span></span>         | <span data-ttu-id="36c03-194">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-194">EUR</span></span>      | <span data-ttu-id="36c03-195">-500,00</span><span class="sxs-lookup"><span data-stu-id="36c03-195">-500.00</span></span> | <span data-ttu-id="36c03-196">Importo originale di -500 × 1</span><span class="sxs-lookup"><span data-stu-id="36c03-196">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="36c03-197">801400</span><span class="sxs-lookup"><span data-stu-id="36c03-197">801400</span></span>         | <span data-ttu-id="36c03-198">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-198">EUR</span></span>      | <span data-ttu-id="36c03-199">250</span><span class="sxs-lookup"><span data-stu-id="36c03-199">250</span></span>     | <span data-ttu-id="36c03-200">500 – 333.33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="36c03-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="36c03-201">801600</span><span class="sxs-lookup"><span data-stu-id="36c03-201">801600</span></span>         | <span data-ttu-id="36c03-202">EUR</span><span class="sxs-lookup"><span data-stu-id="36c03-202">EUR</span></span>      | <span data-ttu-id="36c03-203">-250</span><span class="sxs-lookup"><span data-stu-id="36c03-203">-250</span></span>    | <span data-ttu-id="36c03-204">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="36c03-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






