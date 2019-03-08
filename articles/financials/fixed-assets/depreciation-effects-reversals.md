---
title: Effetti di ammortamento con storni
description: In questo articolo vengono illustrate le implicazioni potenziali dello storno di una transazione cespiti.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d624fa998329680d9fa471fa325f6fcfd3920c6a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "320146"
---
# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="4cbfe-103">Effetti di ammortamento con storni</span><span class="sxs-lookup"><span data-stu-id="4cbfe-103">Depreciation effects with reversals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4cbfe-104">In questo articolo vengono illustrate le implicazioni potenziali dello storno di una transazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="4cbfe-105">È possibile stornare le transazioni cespiti e le transazioni associate a un cespite.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="4cbfe-106">Una transazione stornata può anche essere revocata.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="4cbfe-107">È possibile stornare o revocare una transazione se non è la più recente registrata nel libro per il cespite.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="4cbfe-108">È innanzitutto necessario determinare se sono state registrate transazioni di ammortamento dopo la transazione da stornare.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="4cbfe-109">Ciò è dovuto al fatto che l'ammortamento non viene ricalcolato quando si storna una transazione.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="4cbfe-110">Pertanto, l'ammortamento viene spesso sopravvalutato o sottovalutato dopo lo storno, come illustrato negli esempi.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="4cbfe-111">Per assicurarsi che l'ammortamento sia corretto quando si storna una transazione, sospendere l'operazione di storno se si riceve un messaggio in cui viene segnalato che l'ammortamento non verrà ricalcolato.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="4cbfe-112">Sarà necessario prima stornare la transazione di ammortamento registrata dopo la transazione che si è tentato di stornare, quindi procedere con lo storno.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="4cbfe-113">Non verrà visualizzato alcun avviso relativo al ricalcolo dell'ammortamento e sarà possibile procedere con lo storno.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="4cbfe-114">Negli esempi riportati di seguito vengono illustrati i calcoli che verranno eseguiti se si sceglie di continuare nonostante il messaggio di avviso senza stornare prima le transazioni di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="4cbfe-115">Esempio 1: ammortamento sopravvalutato</span><span class="sxs-lookup"><span data-stu-id="4cbfe-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="4cbfe-116">Un cespite viene impostato con una vita utile di 5 anni e un ammortamento a quote costanti (60 periodi di ammortamento).</span><span class="sxs-lookup"><span data-stu-id="4cbfe-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="4cbfe-117">In questo esempio l'ammortamento è sopravvalutato.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="4cbfe-118">Storico transazioni cespiti</span><span class="sxs-lookup"><span data-stu-id="4cbfe-118">Asset transaction history</span></span>

| <span data-ttu-id="4cbfe-119">Data</span><span class="sxs-lookup"><span data-stu-id="4cbfe-119">Date</span></span>       | <span data-ttu-id="4cbfe-120">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-120">Transaction type</span></span>                                                          | <span data-ttu-id="4cbfe-121">Importo</span><span class="sxs-lookup"><span data-stu-id="4cbfe-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="4cbfe-122">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-122">January 1</span></span>  | <span data-ttu-id="4cbfe-123">Acquisizione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-123">Acquisition</span></span>                                                               | <span data-ttu-id="4cbfe-124">59.000,00</span><span class="sxs-lookup"><span data-stu-id="4cbfe-124">59,000.00</span></span>                                 |
| <span data-ttu-id="4cbfe-125">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-125">January 1</span></span>  | <span data-ttu-id="4cbfe-126">Rettifica acquisizione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="4cbfe-127">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4cbfe-127">1,000.00</span></span>                                  |
| <span data-ttu-id="4cbfe-128">31 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-128">January 31</span></span> | <span data-ttu-id="4cbfe-129">Ammortamento (creato mediante una proposta per un periodo di ammortamento)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="4cbfe-130">1.000,00Calcolo: Valore contabile (59.000 + 1.000) / Numero di periodi di ammortamento rimanenti (60)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="4cbfe-131">Azione di storno</span><span class="sxs-lookup"><span data-stu-id="4cbfe-131">Reversal action</span></span>

| <span data-ttu-id="4cbfe-132">Data</span><span class="sxs-lookup"><span data-stu-id="4cbfe-132">Date</span></span>      | <span data-ttu-id="4cbfe-133">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-133">Transaction type</span></span>                | <span data-ttu-id="4cbfe-134">Importo</span><span class="sxs-lookup"><span data-stu-id="4cbfe-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="4cbfe-135">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-135">January 1</span></span> | <span data-ttu-id="4cbfe-136">Storno rettifica acquisizione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="4cbfe-137">–1.000,00</span><span class="sxs-lookup"><span data-stu-id="4cbfe-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="4cbfe-138">Effetto dell'ammortamento</span><span class="sxs-lookup"><span data-stu-id="4cbfe-138">Depreciation effect</span></span>

| <span data-ttu-id="4cbfe-139">Data</span><span class="sxs-lookup"><span data-stu-id="4cbfe-139">Date</span></span>        | <span data-ttu-id="4cbfe-140">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-140">Transaction type</span></span>        | <span data-ttu-id="4cbfe-141">Importo</span><span class="sxs-lookup"><span data-stu-id="4cbfe-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="4cbfe-142">28 febbraio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-142">February 28</span></span> | <span data-ttu-id="4cbfe-143">Ammortamento (proposta)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-143">Depreciation (proposal)</span></span> | <span data-ttu-id="4cbfe-144">983,05Calcolo: Valore contabile (59.000 - 1.000 ammortamento) / Numero di periodi di ammortamento rimanenti (59)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="4cbfe-145">L'ammortamento è sopravvalutato di 16,95 (1000 - 983,05).</span><span class="sxs-lookup"><span data-stu-id="4cbfe-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="4cbfe-146">Esempio 2: ammortamento sottovalutato</span><span class="sxs-lookup"><span data-stu-id="4cbfe-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="4cbfe-147">Un cespite viene impostato con una vita utile di 5 anni e un ammortamento a quote costanti (60 periodi di ammortamento).</span><span class="sxs-lookup"><span data-stu-id="4cbfe-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="4cbfe-148">In questo esempio l'ammortamento è sottovalutato.</span><span class="sxs-lookup"><span data-stu-id="4cbfe-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="4cbfe-149">Storico transazioni cespiti</span><span class="sxs-lookup"><span data-stu-id="4cbfe-149">Asset transaction history</span></span>

| <span data-ttu-id="4cbfe-150">Data</span><span class="sxs-lookup"><span data-stu-id="4cbfe-150">Date</span></span>       | <span data-ttu-id="4cbfe-151">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-151">Transaction type</span></span>                                                          | <span data-ttu-id="4cbfe-152">Importo</span><span class="sxs-lookup"><span data-stu-id="4cbfe-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="4cbfe-153">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-153">January 1</span></span>  | <span data-ttu-id="4cbfe-154">Acquisizione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-154">Acquisition</span></span>                                                               | <span data-ttu-id="4cbfe-155">59.000,00</span><span class="sxs-lookup"><span data-stu-id="4cbfe-155">59,000.00</span></span>                                   |
| <span data-ttu-id="4cbfe-156">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-156">January 1</span></span>  | <span data-ttu-id="4cbfe-157">Rettifica di svalutazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="4cbfe-158">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4cbfe-158">1,000.00</span></span>                                    |
| <span data-ttu-id="4cbfe-159">31 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-159">January 31</span></span> | <span data-ttu-id="4cbfe-160">Ammortamento (creato mediante una proposta per un periodo di ammortamento)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="4cbfe-161">966,67Calcolo: Valore contabile (59.000 - 1.000) / Numero di periodi di ammortamento rimanenti (60)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="4cbfe-162">Azione di storno</span><span class="sxs-lookup"><span data-stu-id="4cbfe-162">Reversal action</span></span>

| <span data-ttu-id="4cbfe-163">Data</span><span class="sxs-lookup"><span data-stu-id="4cbfe-163">Date</span></span>      | <span data-ttu-id="4cbfe-164">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-164">Transaction type</span></span>               | <span data-ttu-id="4cbfe-165">Importo</span><span class="sxs-lookup"><span data-stu-id="4cbfe-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="4cbfe-166">1 gennaio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-166">January 1</span></span> | <span data-ttu-id="4cbfe-167">Storno rettifica di svalutazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="4cbfe-168">–1.000,00</span><span class="sxs-lookup"><span data-stu-id="4cbfe-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="4cbfe-169">Effetto dell'ammortamento</span><span class="sxs-lookup"><span data-stu-id="4cbfe-169">Depreciation effect</span></span>

| <span data-ttu-id="4cbfe-170">Data</span><span class="sxs-lookup"><span data-stu-id="4cbfe-170">Date</span></span>        | <span data-ttu-id="4cbfe-171">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="4cbfe-171">Transaction type</span></span>        | <span data-ttu-id="4cbfe-172">Importo</span><span class="sxs-lookup"><span data-stu-id="4cbfe-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="4cbfe-173">28 febbraio</span><span class="sxs-lookup"><span data-stu-id="4cbfe-173">February 28</span></span> | <span data-ttu-id="4cbfe-174">Ammortamento (proposta)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-174">Depreciation (proposal)</span></span> | <span data-ttu-id="4cbfe-175">983,62Calcolo: Valore contabile (59.000 - 966,67 ammortamento) / Numero di periodi di ammortamento rimanenti (59)</span><span class="sxs-lookup"><span data-stu-id="4cbfe-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="4cbfe-176">L'ammortamento è sottovalutato di 16,95 (983,62 - 966,67).</span><span class="sxs-lookup"><span data-stu-id="4cbfe-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="additional-resources"></a><span data-ttu-id="4cbfe-177">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4cbfe-177">Additional resources</span></span>
--------

[<span data-ttu-id="4cbfe-178">Ammortamento dei cespiti</span><span class="sxs-lookup"><span data-stu-id="4cbfe-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)



