---
title: "Rivalutazione della valuta in una società di consolidamento"
description: "In questo argomento viene descritto come rivalutare la valuta in una società di consolidamento."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 4aadfb6383b7bae1d9c68de78f9aa91a31433475
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="c6c64-103">Rivalutazione della valuta in una società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="c6c64-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6c64-104">Quando si consolidano i dati da una valuta di contabilizzazione a un'altra, è necessario eseguire la rivalutazione della valuta in presenza di una variazione nei tassi di cambio, affinché i saldi dei conti vengano rivalutati correttamente.</span><span class="sxs-lookup"><span data-stu-id="c6c64-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="c6c64-105">Quando si consolidano i dati, utilizzare la scheda **Conversione valuta** per selezionare i tassi di cambio iniziali per la conversione durante il processo di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="c6c64-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="c6c64-106">Dopo che si è inserito un nuovo tasso di cambio (ad esempio nel mese successivo), è necessario rivalutare i saldi dei conti.</span><span class="sxs-lookup"><span data-stu-id="c6c64-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="c6c64-107">I profitti non realizzati o le perdite non realizzate vengono aggiornati di conseguenza, in base al nuovo tasso di cambio e alla data.</span><span class="sxs-lookup"><span data-stu-id="c6c64-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="c6c64-108">Nell'esempio riportato di seguito vengono mostrare le registrazioni contabili che vengono create durante il processo.</span><span class="sxs-lookup"><span data-stu-id="c6c64-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="c6c64-109">Impostazione società</span><span class="sxs-lookup"><span data-stu-id="c6c64-109">Company setup</span></span>
-   <span data-ttu-id="c6c64-110">**Società operative/di origine (USMF)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c6c64-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="c6c64-111">**Società consolidata (CON)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c6c64-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="c6c64-112">**Profitto realizzato** - Conto CoGe 801500</span><span class="sxs-lookup"><span data-stu-id="c6c64-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="c6c64-113">**Perdita realizzata** - Conto CoGe 801600</span><span class="sxs-lookup"><span data-stu-id="c6c64-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="c6c64-114">**Profitto realizzato**- - Conto CoGe 801600</span><span class="sxs-lookup"><span data-stu-id="c6c64-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="c6c64-115">**Perdita realizzata** - Conto CoGe 801400</span><span class="sxs-lookup"><span data-stu-id="c6c64-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="c6c64-116">Conversioni originali</span><span class="sxs-lookup"><span data-stu-id="c6c64-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="c6c64-117">Transazioni di ricevuta in USMF</span><span class="sxs-lookup"><span data-stu-id="c6c64-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="c6c64-118">Data</span><span class="sxs-lookup"><span data-stu-id="c6c64-118">Date</span></span>       | <span data-ttu-id="c6c64-119">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="c6c64-119">Ledger account</span></span>               | <span data-ttu-id="c6c64-120">Valuta</span><span class="sxs-lookup"><span data-stu-id="c6c64-120">Currency</span></span> | <span data-ttu-id="c6c64-121">Importo</span><span class="sxs-lookup"><span data-stu-id="c6c64-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="c6c64-122">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="c6c64-122">10/11/2015</span></span> | <span data-ttu-id="c6c64-123">110110 – Contanti</span><span class="sxs-lookup"><span data-stu-id="c6c64-123">110110 – Cash</span></span>                | <span data-ttu-id="c6c64-124">GBP</span><span class="sxs-lookup"><span data-stu-id="c6c64-124">USD</span></span>      | <span data-ttu-id="c6c64-125">500</span><span class="sxs-lookup"><span data-stu-id="c6c64-125">500</span></span>    |
| <span data-ttu-id="c6c64-126">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="c6c64-126">10/11/2015</span></span> | <span data-ttu-id="c6c64-127">130100 – Contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="c6c64-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="c6c64-128">GBP</span><span class="sxs-lookup"><span data-stu-id="c6c64-128">USD</span></span>      | <span data-ttu-id="c6c64-129">-500</span><span class="sxs-lookup"><span data-stu-id="c6c64-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="c6c64-130">Tassi di cambio</span><span class="sxs-lookup"><span data-stu-id="c6c64-130">Exchange rates</span></span>

| <span data-ttu-id="c6c64-131">Dalla valuta</span><span class="sxs-lookup"><span data-stu-id="c6c64-131">From currency</span></span> | <span data-ttu-id="c6c64-132">Alla valuta</span><span class="sxs-lookup"><span data-stu-id="c6c64-132">To currency</span></span> | <span data-ttu-id="c6c64-133">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="c6c64-133">Start date</span></span> | <span data-ttu-id="c6c64-134">Tasso di cambio</span><span class="sxs-lookup"><span data-stu-id="c6c64-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="c6c64-135">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-135">EUR</span></span>           | <span data-ttu-id="c6c64-136">GBP</span><span class="sxs-lookup"><span data-stu-id="c6c64-136">USD</span></span>         | <span data-ttu-id="c6c64-137">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="c6c64-137">10/1/2015</span></span>  | <span data-ttu-id="c6c64-138">200</span><span class="sxs-lookup"><span data-stu-id="c6c64-138">200</span></span>           |
| <span data-ttu-id="c6c64-139">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-139">EUR</span></span>           | <span data-ttu-id="c6c64-140">GBP</span><span class="sxs-lookup"><span data-stu-id="c6c64-140">USD</span></span>         | <span data-ttu-id="c6c64-141">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="c6c64-141">11/1/2015</span></span>  | <span data-ttu-id="c6c64-142">150</span><span class="sxs-lookup"><span data-stu-id="c6c64-142">150</span></span>           |
| <span data-ttu-id="c6c64-143">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-143">EUR</span></span>           | <span data-ttu-id="c6c64-144">GBP</span><span class="sxs-lookup"><span data-stu-id="c6c64-144">USD</span></span>         | <span data-ttu-id="c6c64-145">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="c6c64-145">12/1/2012</span></span>  | <span data-ttu-id="c6c64-146">100</span><span class="sxs-lookup"><span data-stu-id="c6c64-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="c6c64-147">Eseguire il consolidamento per ottobre 2015</span><span class="sxs-lookup"><span data-stu-id="c6c64-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="c6c64-148">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="c6c64-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="c6c64-149">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="c6c64-149">Ledger account</span></span> | <span data-ttu-id="c6c64-150">Valuta</span><span class="sxs-lookup"><span data-stu-id="c6c64-150">Currency</span></span> | <span data-ttu-id="c6c64-151">Importo</span><span class="sxs-lookup"><span data-stu-id="c6c64-151">Amount</span></span> | <span data-ttu-id="c6c64-152">Calcolo</span><span class="sxs-lookup"><span data-stu-id="c6c64-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="c6c64-153">110110</span><span class="sxs-lookup"><span data-stu-id="c6c64-153">110110</span></span>         | <span data-ttu-id="c6c64-154">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-154">EUR</span></span>      | <span data-ttu-id="c6c64-155">250</span><span class="sxs-lookup"><span data-stu-id="c6c64-155">250</span></span>    | <span data-ttu-id="c6c64-156">500 EUR × 50%</span><span class="sxs-lookup"><span data-stu-id="c6c64-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="c6c64-157">130100</span><span class="sxs-lookup"><span data-stu-id="c6c64-157">130100</span></span>         | <span data-ttu-id="c6c64-158">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-158">EUR</span></span>      | <span data-ttu-id="c6c64-159">-250</span><span class="sxs-lookup"><span data-stu-id="c6c64-159">-250</span></span>   | <span data-ttu-id="c6c64-160">-500 EUR × 50%</span><span class="sxs-lookup"><span data-stu-id="c6c64-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="c6c64-161">Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 30 novembre 2015</span><span class="sxs-lookup"><span data-stu-id="c6c64-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="c6c64-162">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="c6c64-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="c6c64-163">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="c6c64-163">Ledger account</span></span> | <span data-ttu-id="c6c64-164">Valuta</span><span class="sxs-lookup"><span data-stu-id="c6c64-164">Currency</span></span> | <span data-ttu-id="c6c64-165">Importo</span><span class="sxs-lookup"><span data-stu-id="c6c64-165">Amount</span></span>  | <span data-ttu-id="c6c64-166">Calcolo</span><span class="sxs-lookup"><span data-stu-id="c6c64-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="c6c64-167">110110</span><span class="sxs-lookup"><span data-stu-id="c6c64-167">110110</span></span>         | <span data-ttu-id="c6c64-168">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-168">EUR</span></span>      | <span data-ttu-id="c6c64-169">333,33</span><span class="sxs-lookup"><span data-stu-id="c6c64-169">333.33</span></span>  | <span data-ttu-id="c6c64-170">Importo originale di 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="c6c64-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="c6c64-171">130100</span><span class="sxs-lookup"><span data-stu-id="c6c64-171">130100</span></span>         | <span data-ttu-id="c6c64-172">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-172">EUR</span></span>      | <span data-ttu-id="c6c64-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="c6c64-173">-333.33</span></span> | <span data-ttu-id="c6c64-174">Importo originale di -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="c6c64-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="c6c64-175">801400</span><span class="sxs-lookup"><span data-stu-id="c6c64-175">801400</span></span>         | <span data-ttu-id="c6c64-176">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-176">EUR</span></span>      | <span data-ttu-id="c6c64-177">83,33</span><span class="sxs-lookup"><span data-stu-id="c6c64-177">83.33</span></span>   | <span data-ttu-id="c6c64-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="c6c64-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="c6c64-179">801600</span><span class="sxs-lookup"><span data-stu-id="c6c64-179">801600</span></span>         | <span data-ttu-id="c6c64-180">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-180">EUR</span></span>      | <span data-ttu-id="c6c64-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="c6c64-181">-83.33</span></span>  | <span data-ttu-id="c6c64-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="c6c64-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="c6c64-183">Verranno visualizzate transazioni aggiuntive per gli importi in valuta di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c6c64-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="c6c64-184">Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 31 dicembre 2015</span><span class="sxs-lookup"><span data-stu-id="c6c64-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="c6c64-185">Saldi della società di consolidamento</span><span class="sxs-lookup"><span data-stu-id="c6c64-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="c6c64-186">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="c6c64-186">Ledger account</span></span> | <span data-ttu-id="c6c64-187">Valuta</span><span class="sxs-lookup"><span data-stu-id="c6c64-187">Currency</span></span> | <span data-ttu-id="c6c64-188">Importo</span><span class="sxs-lookup"><span data-stu-id="c6c64-188">Amount</span></span>  | <span data-ttu-id="c6c64-189">Calcolo</span><span class="sxs-lookup"><span data-stu-id="c6c64-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="c6c64-190">110110</span><span class="sxs-lookup"><span data-stu-id="c6c64-190">110110</span></span>         | <span data-ttu-id="c6c64-191">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-191">EUR</span></span>      | <span data-ttu-id="c6c64-192">500,00</span><span class="sxs-lookup"><span data-stu-id="c6c64-192">500.00</span></span>  | <span data-ttu-id="c6c64-193">Importo originale di 500 × 1</span><span class="sxs-lookup"><span data-stu-id="c6c64-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="c6c64-194">130100</span><span class="sxs-lookup"><span data-stu-id="c6c64-194">130100</span></span>         | <span data-ttu-id="c6c64-195">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-195">EUR</span></span>      | <span data-ttu-id="c6c64-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="c6c64-196">-500.00</span></span> | <span data-ttu-id="c6c64-197">Importo originale di -500 × 1</span><span class="sxs-lookup"><span data-stu-id="c6c64-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="c6c64-198">801400</span><span class="sxs-lookup"><span data-stu-id="c6c64-198">801400</span></span>         | <span data-ttu-id="c6c64-199">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-199">EUR</span></span>      | <span data-ttu-id="c6c64-200">250</span><span class="sxs-lookup"><span data-stu-id="c6c64-200">250</span></span>     | <span data-ttu-id="c6c64-201">500 – 333.33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="c6c64-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="c6c64-202">801600</span><span class="sxs-lookup"><span data-stu-id="c6c64-202">801600</span></span>         | <span data-ttu-id="c6c64-203">EUR</span><span class="sxs-lookup"><span data-stu-id="c6c64-203">EUR</span></span>      | <span data-ttu-id="c6c64-204">-250</span><span class="sxs-lookup"><span data-stu-id="c6c64-204">-250</span></span>    | <span data-ttu-id="c6c64-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="c6c64-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






