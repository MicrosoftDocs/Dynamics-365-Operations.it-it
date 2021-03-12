---
title: Tipi di registrazione di leasing
description: In questo argomento vengono descritti i tipi di registrazione utilizzati per le transazioni di leasing di cespiti.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b79b02f7e241783d19a315ccff5bb6874a238c38
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995420"
---
# <a name="lease-posting-types"></a><span data-ttu-id="47404-103">Tipi di registrazione di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47404-104">In questo argomento vengono descritti i tipi di registrazione utilizzati per le transazioni di leasing di cespiti.</span><span class="sxs-lookup"><span data-stu-id="47404-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="47404-105">Cespite di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-105">Lease asset</span></span>

<span data-ttu-id="47404-106">L'account è associato all'Asset Right of use.</span><span class="sxs-lookup"><span data-stu-id="47404-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="47404-107">Su questo conto viene effettuato un addebito quando un leasing viene inizialmente riconosciuto in base ai nuovi principi contabili di leasing, Accounting Standards Codification Topic 842 (ASC 842) e International Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="47404-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="47404-108">Per un leasing modificato, su questo conto potrebbe essere effettuato un addebito o un accredito, a seconda che la modifica aumenti o diminuisca l'obbligazione sul leasing.</span><span class="sxs-lookup"><span data-stu-id="47404-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="47404-109">**Scritture contabili di esempio:** riconoscimento iniziale</span><span class="sxs-lookup"><span data-stu-id="47404-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="47404-110">**Dare:** cespite leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="47404-111">**Avere:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="47404-112">Obbligazione sul leasing</span><span class="sxs-lookup"><span data-stu-id="47404-112">Lease liability</span></span>

<span data-ttu-id="47404-113">Il conto è associato all'obbligazione sul leasing che si verifica quando i pagamenti vengono scontati secondo i nuovi standard IFRS 16 e ASC 842.</span><span class="sxs-lookup"><span data-stu-id="47404-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="47404-114">Su questo conto viene effettuato un accredito un leasing viene inizialmente riconosciuto secondo i nuovi standard.</span><span class="sxs-lookup"><span data-stu-id="47404-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="47404-115">Viene effettuato un addebito per i canoni di leasing e accreditato per gli interessi maturati.</span><span class="sxs-lookup"><span data-stu-id="47404-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="47404-116">**Scritture contabili di esempio:** riconoscimento iniziale</span><span class="sxs-lookup"><span data-stu-id="47404-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="47404-117">**Dare:** cespite leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="47404-118">**Avere:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="47404-119">**Esempi di scritture contabili:** interessi maturati</span><span class="sxs-lookup"><span data-stu-id="47404-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="47404-120">**Dare:** interesse passivo XXX</span><span class="sxs-lookup"><span data-stu-id="47404-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="47404-121">**Avere:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="47404-122">**Scritture contabili di esempio:** canone di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="47404-123">**Dare:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="47404-124">**Avere:** debito fornitore/canone di leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="47404-125">Obbligazione sul leasing a breve termine</span><span class="sxs-lookup"><span data-stu-id="47404-125">Short-term lease liability</span></span>

<span data-ttu-id="47404-126">Il conto è associato all'obbligazione sul leasing a breve termine quando viene registrata la scrittura contabile di riclassificazione dell'obbligazione sul leasing a breve termine.</span><span class="sxs-lookup"><span data-stu-id="47404-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="47404-127">Su questo conto viene effettuato un accredito per la passività a breve termine dal piano di ammortamento l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="47404-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="47404-128">Tuttavia, lo stesso importo viene addebitato il primo giorno del mese successivo.</span><span class="sxs-lookup"><span data-stu-id="47404-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="47404-129">**Registrazioni contabili di esempio:** riclassificazione dell'obbligazione sul leasing a breve termine</span><span class="sxs-lookup"><span data-stu-id="47404-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="47404-130">**Dare:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="47404-131">**Avere:** obbligazione sul leasing a breve termine XXX</span><span class="sxs-lookup"><span data-stu-id="47404-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="47404-132">**Dare:** obbligazione sul leasing a breve termine XXX</span><span class="sxs-lookup"><span data-stu-id="47404-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="47404-133">**Avere:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="47404-134">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="47404-134">Depreciation expense</span></span>

<span data-ttu-id="47404-135">Il conto è associato alla spesa correlata all'ammortamento del'Asset ROU ai sensi di IFRS 16, ASC 842 e ai leasing finanziari secondo lo IAS 17 e l'ASC 840.</span><span class="sxs-lookup"><span data-stu-id="47404-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="47404-136">Su questo conto viene effettuato un addebito quando un asset ROU viene ammortizzato ogni mese.</span><span class="sxs-lookup"><span data-stu-id="47404-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="47404-137">**Esempi di scritture contabili:** ratei di ammortamento</span><span class="sxs-lookup"><span data-stu-id="47404-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="47404-138">**Dare:** spesa di ammortamento XXX</span><span class="sxs-lookup"><span data-stu-id="47404-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="47404-139">**Avere:** Ammortamento accumulato XXX</span><span class="sxs-lookup"><span data-stu-id="47404-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="47404-140">Profitti/Perdite per la modifica del leasing</span><span class="sxs-lookup"><span data-stu-id="47404-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="47404-141">Il conto è associato a eventuali guadagni o perdite derivanti da modifiche del leasing.</span><span class="sxs-lookup"><span data-stu-id="47404-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="47404-142">Un guadagno potrebbe verificarsi durante una modifica del leasing se la modifica riduce l'obbligazione sul leasing di un importo che supera il valore contabile dell'asset ROU.</span><span class="sxs-lookup"><span data-stu-id="47404-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="47404-143">Ad esempio, un leasing ha un valore contabile corrente dell'obbligazione sul leasing di $150.000 e un valore contabile dell'asset ROU di $100.000.</span><span class="sxs-lookup"><span data-stu-id="47404-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="47404-144">Il leasing viene modificato e questa modifica produce un nuovo valore attuale dei canoni di leasing futuri(PVFMLP) di $40.000.</span><span class="sxs-lookup"><span data-stu-id="47404-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="47404-145">Pertanto, l'obbligazione sul leasing verrà addebitata da $110.000 ($ 150.000 - $40.000).</span><span class="sxs-lookup"><span data-stu-id="47404-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="47404-146">Poiché l'asset ROU è pari solo a $100.000, la diminuzione di $110.000 farà diminuire l'asset oltre 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="47404-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="47404-147">Pertanto, la guida contabile afferma che il resto deve essere registrato in un conto di guadagno.</span><span class="sxs-lookup"><span data-stu-id="47404-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="47404-148">In questo caso, l'ultima scrittura contabile sarà un addebito sull'obbligazione sul leasing per $110.000, un accredito sul cespite del leasing di $100.000 e un accredito sul conto guadagni per $10.000.</span><span class="sxs-lookup"><span data-stu-id="47404-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="47404-149">**Scritture contabili di esempio:** modifica del leasing</span><span class="sxs-lookup"><span data-stu-id="47404-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="47404-150">**Dare:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="47404-151">**Avere:** cespite del leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="47404-152">**Avere:** guadagno XXX</span><span class="sxs-lookup"><span data-stu-id="47404-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="47404-153">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="47404-153">Accumulated depreciation</span></span>

<span data-ttu-id="47404-154">Il conto è associato al conto contro-asset dell'asset ROU.</span><span class="sxs-lookup"><span data-stu-id="47404-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="47404-155">Viene eseguito un accredito sul conto quando viene registrata una spesa di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="47404-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="47404-156">**Esempi di scritture contabili:** ratei di ammortamento</span><span class="sxs-lookup"><span data-stu-id="47404-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="47404-157">**Dare:** spesa di ammortamento XXX</span><span class="sxs-lookup"><span data-stu-id="47404-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="47404-158">**Avere:** Ammortamento accumulato XXX</span><span class="sxs-lookup"><span data-stu-id="47404-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="retained-earnings"></a><span data-ttu-id="47404-159">Utili non distribuiti</span><span class="sxs-lookup"><span data-stu-id="47404-159">Retained earnings</span></span>

<span data-ttu-id="47404-160">Il conto è associato agli utili non distribuiti.</span><span class="sxs-lookup"><span data-stu-id="47404-160">The account is associated with retained earnings.</span></span> <span data-ttu-id="47404-161">Questo conto potrebbe essere addebitato o accreditato in una registrazione contabile di rettifica di transizione utilizzando il metodo retrospettivo completo o il metodo dell'opzione di recupero cumulativo A.</span><span class="sxs-lookup"><span data-stu-id="47404-161">This account might be either debited or credited in a transition adjustment journal entry by using the full retrospective method or the cumulative catch-up option A method.</span></span> <span data-ttu-id="47404-162">La differenza tra l'asset ROU iniziale e l'obbligazione sul leasing viene registrata negli utili non distribuiti.</span><span class="sxs-lookup"><span data-stu-id="47404-162">The difference between the initial ROU asset and lease liability is booked to retained earnings.</span></span> <span data-ttu-id="47404-163">In rari casi, gli utili non distribuiti potrebbero essere influenzati anche durante la modifica del leasing, se la classificazione di un leasing viene modificata da finanziaria a operativa per aumentare o diminuire l'asset ROU in modo che sia uguale all'obbligazione sul leasing.</span><span class="sxs-lookup"><span data-stu-id="47404-163">In rare cases, the retained earnings might also be affected during lease modification, if the classification of a lease is changed from finance to operating to write the ROU asset up or down so that it equals the lease liability.</span></span>

<span data-ttu-id="47404-164">**Scritture contabili di esempio:** rettifica di transizione (metodo retrospettivo completo o dell'opzione A di recupero cumulativo)</span><span class="sxs-lookup"><span data-stu-id="47404-164">**Example journal entries:** Transition adjustment (full retrospective or cumulative catch-up option A method)</span></span><br>
<span data-ttu-id="47404-165">**Dare:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-165">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="47404-166">**Avere:** cespite del leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-166">**Credit:** Lease asset XXX</span></span><br>
<span data-ttu-id="47404-167">**Avere:** utili non distribuiti XXX</span><span class="sxs-lookup"><span data-stu-id="47404-167">**Credit:** Retained earnings XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="47404-168">Pagamento variabile</span><span class="sxs-lookup"><span data-stu-id="47404-168">Variable payment</span></span>

<span data-ttu-id="47404-169">Il conto è associato a canoni di leasing variabili prodotti da una rivalutazione dell'indice ai sensi dei leasing ASC 842, ASC 840 e IAS 17.</span><span class="sxs-lookup"><span data-stu-id="47404-169">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="47404-170">Nello scadenziario dei canoni di leasing, i pagamenti variabili sono inclusi nella colonna **Pagamento variabile**.</span><span class="sxs-lookup"><span data-stu-id="47404-170">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="47404-171">Su questo conto viene effettuato un addebito quando viene creata una fattura su una riga di scadenziario di pagamento che contiene un pagamento variabile.</span><span class="sxs-lookup"><span data-stu-id="47404-171">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="47404-172">**Scritture contabili di esempio:** canone di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-172">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="47404-173">**Dare:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-173">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="47404-174">**Dare:** pagamento variabile XXX</span><span class="sxs-lookup"><span data-stu-id="47404-174">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="47404-175">**Avere:** debito fornitore/canone di leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-175">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="47404-176">Cespite passività sui contratti (passività)</span><span class="sxs-lookup"><span data-stu-id="47404-176">Deferred rent asset (liability)</span></span>

<span data-ttu-id="47404-177">Il conto è associato alla passività di cespiti passività sui contratti o passività prodotta da un leasing per passività sui contratti.</span><span class="sxs-lookup"><span data-stu-id="47404-177">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="47404-178">Su questo conto viene effettuato un addebito quando una fattura viene registrata a fronte di un leasing con trattamento di passività sui contratti, se l'importo del canone del leasing è superiore al costo del leasing a quote costanti del periodo.</span><span class="sxs-lookup"><span data-stu-id="47404-178">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="47404-179">Viene accreditato se il canone di leasing è inferiore al costo del leasing a quote costanti del periodo.</span><span class="sxs-lookup"><span data-stu-id="47404-179">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="47404-180">**Scritture contabili di esempio:** canone di leasing (leasing con trattamento di passività sui contratti)</span><span class="sxs-lookup"><span data-stu-id="47404-180">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="47404-181">**Dare:** costo di leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-181">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="47404-182">**Avere:** passività sui contratti XXX</span><span class="sxs-lookup"><span data-stu-id="47404-182">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="47404-183">**Avere:** debito fornitore/canone di leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-183">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="47404-184">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-184">Lease expense</span></span>

<span data-ttu-id="47404-185">Il conto è associato al costo del leasing se il leasing è classificato come leasing per trattamento passività sui contratti.</span><span class="sxs-lookup"><span data-stu-id="47404-185">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="47404-186">Su questo conto viene effettuato un addebito quando una fattura viene registrata a fronte di un leasing con trattamento di passività sui contratti.</span><span class="sxs-lookup"><span data-stu-id="47404-186">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="47404-187">**Scritture contabili di esempio:** canone di leasing (leasing con trattamento di passività sui contratti)</span><span class="sxs-lookup"><span data-stu-id="47404-187">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="47404-188">**Dare:** costo di leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-188">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="47404-189">**Avere:** passività sui contratti XXX</span><span class="sxs-lookup"><span data-stu-id="47404-189">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="47404-190">**Avere:** debito fornitore/canone di leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-190">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="47404-191">Spesa di svalutazione</span><span class="sxs-lookup"><span data-stu-id="47404-191">Impairment expense</span></span>

<span data-ttu-id="47404-192">Il conto viene registrato a fronte di un leasing compromesso.</span><span class="sxs-lookup"><span data-stu-id="47404-192">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="47404-193">Su questo conto viene effettuato un addebito, mentre sul conto asset ROU viene direttamente effettuato un accredito.</span><span class="sxs-lookup"><span data-stu-id="47404-193">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="47404-194">**Scritture contabili di esempio:** canone di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-194">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="47404-195">**Dare:** Spesa di riduzione del valore XXX</span><span class="sxs-lookup"><span data-stu-id="47404-195">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="47404-196">**Avere:** Asset ROU XXX</span><span class="sxs-lookup"><span data-stu-id="47404-196">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="47404-197">Canone di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-197">Lease payment</span></span>

<span data-ttu-id="47404-198">L'account viene registrato a fronte se il parametro **Paga al fornitore** è disattivato.</span><span class="sxs-lookup"><span data-stu-id="47404-198">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="47404-199">Su questo conto viene effettuato invece un accredito se il parametro pagabile al fornitore è disattivato.</span><span class="sxs-lookup"><span data-stu-id="47404-199">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="47404-200">**Scritture contabili di esempio:** canone di leasing</span><span class="sxs-lookup"><span data-stu-id="47404-200">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="47404-201">**Dare:** obbligazione sul leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-201">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="47404-202">**Avere:** canone di leasing XXX</span><span class="sxs-lookup"><span data-stu-id="47404-202">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="47404-203">Registrazioni del tipo di spesa</span><span class="sxs-lookup"><span data-stu-id="47404-203">Expense type postings</span></span>

<span data-ttu-id="47404-204">Sul conto selezionato per ogni tipo di spesa viene effettuato un addebito quando viene generato un pagamento per quel tipo di spesa.</span><span class="sxs-lookup"><span data-stu-id="47404-204">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="47404-205">Ad esempio, sul conto specificato per il tipo di spesa **Assicurazione** viene effettuato un addebito ogni volta che viene creata una fattura o una scrittura contabile di pagamento dalla pianificazione del costo esecutivo per le spese assicurative.</span><span class="sxs-lookup"><span data-stu-id="47404-205">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="47404-206">**Scritture contabili di esempio:** pagamento assicurazione</span><span class="sxs-lookup"><span data-stu-id="47404-206">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="47404-207">**Dare:** conto tipo di spesa assicurativa XXX</span><span class="sxs-lookup"><span data-stu-id="47404-207">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="47404-208">**Avere:** conto di contropartita XXX</span><span class="sxs-lookup"><span data-stu-id="47404-208">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="47404-209">Il conto di contropartita viene selezionato a livello di leasing nelle righe per il programma di pagamento del costo esecutivo.</span><span class="sxs-lookup"><span data-stu-id="47404-209">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="47404-210">Questo conto di contropartita può essere associato al fornitore o a un conto CoGe.</span><span class="sxs-lookup"><span data-stu-id="47404-210">This offset account can associated with the vendor, or with a ledger account.</span></span>
