---
title: Calcolo generale
description: In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cc6ad48ef80aa01739129b59cc1133d0a1930f24
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759474"
---
# <a name="overhead-calculation"></a><span data-ttu-id="c66d8-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="c66d8-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c66d8-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="c66d8-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="c66d8-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="c66d8-105">Term definition</span></span>
---------------

<span data-ttu-id="c66d8-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="c66d8-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="c66d8-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="c66d8-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="c66d8-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="c66d8-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="c66d8-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="c66d8-109">Rent</span></span>
-   <span data-ttu-id="c66d8-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-110">Electricity</span></span>
-   <span data-ttu-id="c66d8-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="c66d8-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="c66d8-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="c66d8-112">Overhead calculation overview</span></span>
<span data-ttu-id="c66d8-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="c66d8-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="c66d8-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="c66d8-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="c66d8-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="c66d8-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="c66d8-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="c66d8-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="c66d8-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="c66d8-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="c66d8-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="c66d8-119">Version type</span></span>
-   <span data-ttu-id="c66d8-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="c66d8-120">Date and time</span></span>
-   <span data-ttu-id="c66d8-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="c66d8-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="c66d8-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-122">Fiscal year</span></span>
-   <span data-ttu-id="c66d8-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-123">Fiscal period</span></span>

<span data-ttu-id="c66d8-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="c66d8-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="c66d8-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c66d8-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="c66d8-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="c66d8-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="c66d8-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="c66d8-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="c66d8-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="c66d8-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="c66d8-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="c66d8-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="c66d8-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="c66d8-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="c66d8-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="c66d8-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="c66d8-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="c66d8-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="c66d8-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="c66d8-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="c66d8-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="c66d8-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="c66d8-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="c66d8-140">Main account</span></span></th>
<th><span data-ttu-id="c66d8-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="c66d8-143">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-143">CC099</span></span></td>
<td><span data-ttu-id="c66d8-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-144">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-145">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-145">10001</span></span></td>
<td><span data-ttu-id="c66d8-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-146">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="c66d8-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="c66d8-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="c66d8-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="c66d8-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="c66d8-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="c66d8-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-151">Define the cost behavior rule</span></span>

<span data-ttu-id="c66d8-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="c66d8-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="c66d8-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="c66d8-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="c66d8-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="c66d8-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="c66d8-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="c66d8-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="c66d8-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="c66d8-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-160">Journal</span></span></th>
<th><span data-ttu-id="c66d8-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c66d8-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c66d8-163">Versione</span><span class="sxs-lookup"><span data-stu-id="c66d8-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-164">00001</span><span class="sxs-lookup"><span data-stu-id="c66d8-164">00001</span></span></td>
<td><span data-ttu-id="c66d8-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="c66d8-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-166">Fiscal</span></span></td>
<td><span data-ttu-id="c66d8-167">2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-167">2017</span></span></td>
<td><span data-ttu-id="c66d8-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-168">Period 1</span></span></td>
<td><span data-ttu-id="c66d8-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c66d8-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="c66d8-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-173">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-174">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-175">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="c66d8-177">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-177">CC099</span></span></td>
<td><span data-ttu-id="c66d8-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-178">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-179">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-179">10001</span></span></td>
<td><span data-ttu-id="c66d8-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-180">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="c66d8-181">Unclassified</span></span></td>
<td><span data-ttu-id="c66d8-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c66d8-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-185">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-186">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-187">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-187">Amount</span></span></th>
<th><span data-ttu-id="c66d8-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-189">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-189">CC099</span></span></td>
<td><span data-ttu-id="c66d8-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-190">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-191">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-191">10001</span></span></td>
<td><span data-ttu-id="c66d8-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-192">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="c66d8-193">Unclassified</span></span></td>
<td><span data-ttu-id="c66d8-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-194">10,000.00</span></span></td>
<td><span data-ttu-id="c66d8-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-196">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-196">CC099</span></span></td>
<td><span data-ttu-id="c66d8-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-197">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-198">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-198">10001</span></span></td>
<td><span data-ttu-id="c66d8-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-199">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="c66d8-200">Unclassified</span></span></td>
<td><span data-ttu-id="c66d8-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-201">-10,000.00</span></span></td>
<td><span data-ttu-id="c66d8-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-203">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-203">CC099</span></span></td>
<td><span data-ttu-id="c66d8-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-204">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-205">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-205">10001</span></span></td>
<td><span data-ttu-id="c66d8-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-206">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-207">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-208">1,000.00</span></span></td>
<td><span data-ttu-id="c66d8-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-210">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-210">CC099</span></span></td>
<td><span data-ttu-id="c66d8-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-211">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-212">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-212">10001</span></span></td>
<td><span data-ttu-id="c66d8-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-213">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-214">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-215">9,000.00</span></span></td>
<td><span data-ttu-id="c66d8-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="c66d8-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="c66d8-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="c66d8-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="c66d8-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="c66d8-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="c66d8-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="c66d8-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-221">Define the cost distribution rule</span></span>

<span data-ttu-id="c66d8-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="c66d8-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="c66d8-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="c66d8-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="c66d8-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="c66d8-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="c66d8-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="c66d8-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="c66d8-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="c66d8-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="c66d8-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-228">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-229">KWH</span><span class="sxs-lookup"><span data-stu-id="c66d8-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-230">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-230">CC001</span></span></td>
<td><span data-ttu-id="c66d8-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-231">HR</span></span></td>
<td><span data-ttu-id="c66d8-232">1.000</span><span class="sxs-lookup"><span data-stu-id="c66d8-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-233">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-233">CC002</span></span></td>
<td><span data-ttu-id="c66d8-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-234">Finance</span></span></td>
<td><span data-ttu-id="c66d8-235">6.000</span><span class="sxs-lookup"><span data-stu-id="c66d8-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-236">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-236">CC003</span></span></td>
<td><span data-ttu-id="c66d8-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-237">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-238">0</span><span class="sxs-lookup"><span data-stu-id="c66d8-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="c66d8-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-240">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-241">Magnitude</span></span></th>
<th><span data-ttu-id="c66d8-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-242">Allocation factor</span></span></th>
<th><span data-ttu-id="c66d8-243">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-244">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-244">CC001</span></span></td>
<td><span data-ttu-id="c66d8-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-245">HR</span></span></td>
<td><span data-ttu-id="c66d8-246">1.000</span><span class="sxs-lookup"><span data-stu-id="c66d8-246">1,000</span></span></td>
<td><span data-ttu-id="c66d8-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c66d8-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c66d8-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-249">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-249">CC002</span></span></td>
<td><span data-ttu-id="c66d8-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-250">Finance</span></span></td>
<td><span data-ttu-id="c66d8-251">6.000</span><span class="sxs-lookup"><span data-stu-id="c66d8-251">6,000</span></span></td>
<td><span data-ttu-id="c66d8-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c66d8-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c66d8-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-254">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-254">CC003</span></span></td>
<td><span data-ttu-id="c66d8-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-255">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-256">0</span><span class="sxs-lookup"><span data-stu-id="c66d8-256">0</span></span></td>
<td><span data-ttu-id="c66d8-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c66d8-258">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="c66d8-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="c66d8-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="c66d8-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-261">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-262">Formula</span><span class="sxs-lookup"><span data-stu-id="c66d8-262">Formula</span></span></th>
<th><span data-ttu-id="c66d8-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-263">Magnitude</span></span></th>
<th><span data-ttu-id="c66d8-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-264">Allocation factor</span></span></th>
<th><span data-ttu-id="c66d8-265">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-266">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-266">CC001</span></span></td>
<td><span data-ttu-id="c66d8-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-267">HR</span></span></td>
<td><span data-ttu-id="c66d8-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c66d8-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c66d8-269">1</span><span class="sxs-lookup"><span data-stu-id="c66d8-269">1</span></span></td>
<td><span data-ttu-id="c66d8-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c66d8-271">500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-272">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-272">CC002</span></span></td>
<td><span data-ttu-id="c66d8-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-273">Finance</span></span></td>
<td><span data-ttu-id="c66d8-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c66d8-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c66d8-275">1</span><span class="sxs-lookup"><span data-stu-id="c66d8-275">1</span></span></td>
<td><span data-ttu-id="c66d8-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c66d8-277">500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-278">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-278">CC003</span></span></td>
<td><span data-ttu-id="c66d8-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-279">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c66d8-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c66d8-281">0</span><span class="sxs-lookup"><span data-stu-id="c66d8-281">0</span></span></td>
<td><span data-ttu-id="c66d8-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c66d8-283">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c66d8-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-285">Journal</span></span></th>
<th><span data-ttu-id="c66d8-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c66d8-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c66d8-288">Versione</span><span class="sxs-lookup"><span data-stu-id="c66d8-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-289">00002</span><span class="sxs-lookup"><span data-stu-id="c66d8-289">00002</span></span></td>
<td><span data-ttu-id="c66d8-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="c66d8-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-291">Fiscal</span></span></td>
<td><span data-ttu-id="c66d8-292">2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-292">2017</span></span></td>
<td><span data-ttu-id="c66d8-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-293">Period 1</span></span></td>
<td><span data-ttu-id="c66d8-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c66d8-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="c66d8-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-298">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-299">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-300">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-302">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-302">CC099</span></span></td>
<td><span data-ttu-id="c66d8-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-303">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-304">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-304">10001</span></span></td>
<td><span data-ttu-id="c66d8-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-305">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-306">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-309">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-309">CC099</span></span></td>
<td><span data-ttu-id="c66d8-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-310">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-311">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-311">10001</span></span></td>
<td><span data-ttu-id="c66d8-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-312">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-313">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c66d8-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-317">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-318">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-319">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-319">Amount</span></span></th>
<th><span data-ttu-id="c66d8-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-321">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-321">CC099</span></span></td>
<td><span data-ttu-id="c66d8-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-322">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-323">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-323">10001</span></span></td>
<td><span data-ttu-id="c66d8-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-324">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-325">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-326">-1,000.00</span></span></td>
<td><span data-ttu-id="c66d8-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-328">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-328">CC001</span></span></td>
<td><span data-ttu-id="c66d8-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-329">HR</span></span></td>
<td><span data-ttu-id="c66d8-330">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-330">10001</span></span></td>
<td><span data-ttu-id="c66d8-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-331">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-332">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-333">500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-333">500.00</span></span></td>
<td><span data-ttu-id="c66d8-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-335">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-335">CC002</span></span></td>
<td><span data-ttu-id="c66d8-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-336">Finance</span></span></td>
<td><span data-ttu-id="c66d8-337">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-337">10001</span></span></td>
<td><span data-ttu-id="c66d8-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-338">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-339">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-340">500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-340">500.00</span></span></td>
<td><span data-ttu-id="c66d8-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-342">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-342">CC099</span></span></td>
<td><span data-ttu-id="c66d8-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="c66d8-343">Default cost center</span></span></td>
<td><span data-ttu-id="c66d8-344">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-344">10001</span></span></td>
<td><span data-ttu-id="c66d8-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-345">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-346">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-347">-9,000.00</span></span></td>
<td><span data-ttu-id="c66d8-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-349">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-349">CC001</span></span></td>
<td><span data-ttu-id="c66d8-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-350">HR</span></span></td>
<td><span data-ttu-id="c66d8-351">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-351">10001</span></span></td>
<td><span data-ttu-id="c66d8-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-352">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-353">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c66d8-354">1,285.71</span></span></td>
<td><span data-ttu-id="c66d8-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-356">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-356">CC002</span></span></td>
<td><span data-ttu-id="c66d8-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-357">Finance</span></span></td>
<td><span data-ttu-id="c66d8-358">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-358">10001</span></span></td>
<td><span data-ttu-id="c66d8-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-359">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-360">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c66d8-361">7,714.29</span></span></td>
<td><span data-ttu-id="c66d8-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="c66d8-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="c66d8-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="c66d8-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="c66d8-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="c66d8-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="c66d8-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="c66d8-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="c66d8-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="c66d8-367">Define the overhead rate</span></span>

<span data-ttu-id="c66d8-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="c66d8-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="c66d8-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="c66d8-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-370">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-371">Ore</span><span class="sxs-lookup"><span data-stu-id="c66d8-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-372">Proj 1</span></span></td>
<td><span data-ttu-id="c66d8-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-373">Project 1</span></span></td>
<td><span data-ttu-id="c66d8-374">3</span><span class="sxs-lookup"><span data-stu-id="c66d8-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-375">Proj 2</span></span></td>
<td><span data-ttu-id="c66d8-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-376">Project 2</span></span></td>
<td><span data-ttu-id="c66d8-377">1</span><span class="sxs-lookup"><span data-stu-id="c66d8-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="c66d8-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-379">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-380">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-381">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-382">Unità</span><span class="sxs-lookup"><span data-stu-id="c66d8-382">Units</span></span></th>
<th><span data-ttu-id="c66d8-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="c66d8-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-384">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-384">CC001</span></span></td>
<td><span data-ttu-id="c66d8-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-385">HR</span></span></td>
<td><span data-ttu-id="c66d8-386">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-386">10001</span></span></td>
<td><span data-ttu-id="c66d8-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-387">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-388">1</span><span class="sxs-lookup"><span data-stu-id="c66d8-388">1</span></span></td>
<td><span data-ttu-id="c66d8-389">10</span><span class="sxs-lookup"><span data-stu-id="c66d8-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-391">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-392">Magnitude</span></span></th>
<th><span data-ttu-id="c66d8-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-393">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-394">Allocation factor</span></span></th>
<th><span data-ttu-id="c66d8-395">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-396">Proj 1</span></span></td>
<td><span data-ttu-id="c66d8-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-397">Project 1</span></span></td>
<td><span data-ttu-id="c66d8-398">3</span><span class="sxs-lookup"><span data-stu-id="c66d8-398">3</span></span></td>
<td><span data-ttu-id="c66d8-399">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-399">10001</span></span></td>
<td><span data-ttu-id="c66d8-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c66d8-401">30,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-402">Proj 2</span></span></td>
<td><span data-ttu-id="c66d8-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-403">Project 2</span></span></td>
<td><span data-ttu-id="c66d8-404">1</span><span class="sxs-lookup"><span data-stu-id="c66d8-404">1</span></span></td>
<td><span data-ttu-id="c66d8-405">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-405">10001</span></span></td>
<td><span data-ttu-id="c66d8-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c66d8-407">10,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c66d8-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-409">Journal</span></span></th>
<th><span data-ttu-id="c66d8-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c66d8-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c66d8-412">Versione</span><span class="sxs-lookup"><span data-stu-id="c66d8-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-413">00003</span><span class="sxs-lookup"><span data-stu-id="c66d8-413">00003</span></span></td>
<td><span data-ttu-id="c66d8-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="c66d8-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="c66d8-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-415">Fiscal</span></span></td>
<td><span data-ttu-id="c66d8-416">2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-416">2017</span></span></td>
<td><span data-ttu-id="c66d8-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-417">Period 1</span></span></td>
<td><span data-ttu-id="c66d8-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="c66d8-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="c66d8-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-421">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-424">Proj 1</span></span></td>
<td><span data-ttu-id="c66d8-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c66d8-426">3,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-428">Proj 2</span></span></td>
<td><span data-ttu-id="c66d8-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c66d8-430">1,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c66d8-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-433">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-434">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-435">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-435">Amount</span></span></th>
<th><span data-ttu-id="c66d8-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="c66d8-437">CC0001</span></span></td>
<td><span data-ttu-id="c66d8-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-438">HR</span></span></td>
<td><span data-ttu-id="c66d8-439">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-439">10001</span></span></td>
<td><span data-ttu-id="c66d8-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-440">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-441">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-442">-30.00</span></span></td>
<td><span data-ttu-id="c66d8-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-444">Proj 1</span></span></td>
<td><span data-ttu-id="c66d8-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c66d8-446">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-446">10001</span></span></td>
<td><span data-ttu-id="c66d8-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-447">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-448">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-449">30,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-449">30.00</span></span></td>
<td><span data-ttu-id="c66d8-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-451">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-451">CC001</span></span></td>
<td><span data-ttu-id="c66d8-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-452">HR</span></span></td>
<td><span data-ttu-id="c66d8-453">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-453">10001</span></span></td>
<td><span data-ttu-id="c66d8-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-454">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-455">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-456">-10.00</span></span></td>
<td><span data-ttu-id="c66d8-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-458">Proj 2</span></span></td>
<td><span data-ttu-id="c66d8-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c66d8-460">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-460">10001</span></span></td>
<td><span data-ttu-id="c66d8-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-461">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-462">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-463">10.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-463">10.00</span></span></td>
<td><span data-ttu-id="c66d8-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="c66d8-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="c66d8-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="c66d8-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="c66d8-468">Finance supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="c66d8-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="c66d8-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="c66d8-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="c66d8-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="c66d8-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="c66d8-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="c66d8-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="c66d8-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="c66d8-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="c66d8-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="c66d8-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="c66d8-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="c66d8-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="c66d8-475">Define the cost allocation</span></span>

<span data-ttu-id="c66d8-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="c66d8-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="c66d8-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="c66d8-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-479">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="c66d8-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-481">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-481">CC002</span></span></td>
<td><span data-ttu-id="c66d8-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-482">Finance</span></span></td>
<td><span data-ttu-id="c66d8-483">35</span><span class="sxs-lookup"><span data-stu-id="c66d8-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-484">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-484">CC003</span></span></td>
<td><span data-ttu-id="c66d8-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-485">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-486">55</span><span class="sxs-lookup"><span data-stu-id="c66d8-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-487">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-487">CC004</span></span></td>
<td><span data-ttu-id="c66d8-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-488">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-489">10</span><span class="sxs-lookup"><span data-stu-id="c66d8-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="c66d8-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="c66d8-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-492">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-494">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-494">CC003</span></span></td>
<td><span data-ttu-id="c66d8-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-495">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-496">65</span><span class="sxs-lookup"><span data-stu-id="c66d8-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-497">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-497">CC004</span></span></td>
<td><span data-ttu-id="c66d8-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-498">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-499">35</span><span class="sxs-lookup"><span data-stu-id="c66d8-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="c66d8-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="c66d8-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-502">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="c66d8-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-504">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-505">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-506">60</span><span class="sxs-lookup"><span data-stu-id="c66d8-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-507">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-508">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-509">20</span><span class="sxs-lookup"><span data-stu-id="c66d8-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="c66d8-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="c66d8-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-512">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="c66d8-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-514">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-515">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-516">80</span><span class="sxs-lookup"><span data-stu-id="c66d8-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-517">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-518">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-519">15</span><span class="sxs-lookup"><span data-stu-id="c66d8-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c66d8-520">Le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="c66d8-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="c66d8-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="c66d8-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="c66d8-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="c66d8-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-523">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-524">Magnitude</span></span></th>
<th><span data-ttu-id="c66d8-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-525">Allocation factor</span></span></th>
<th><span data-ttu-id="c66d8-526">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-526">Amount</span></span></th>
<th><span data-ttu-id="c66d8-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-528">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-528">CC002</span></span></td>
<td><span data-ttu-id="c66d8-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-529">Finance</span></span></td>
<td><span data-ttu-id="c66d8-530">35</span><span class="sxs-lookup"><span data-stu-id="c66d8-530">35</span></span></td>
<td><span data-ttu-id="c66d8-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c66d8-532">175.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-532">175.00</span></span></td>
<td><span data-ttu-id="c66d8-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-534">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-534">CC003</span></span></td>
<td><span data-ttu-id="c66d8-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-535">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-536">55</span><span class="sxs-lookup"><span data-stu-id="c66d8-536">55</span></span></td>
<td><span data-ttu-id="c66d8-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c66d8-538">275.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-538">275.00</span></span></td>
<td><span data-ttu-id="c66d8-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-540">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-540">CC004</span></span></td>
<td><span data-ttu-id="c66d8-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-541">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-542">10</span><span class="sxs-lookup"><span data-stu-id="c66d8-542">10</span></span></td>
<td><span data-ttu-id="c66d8-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c66d8-544">50,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-544">50.00</span></span></td>
<td><span data-ttu-id="c66d8-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-546">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-546">CC002</span></span></td>
<td><span data-ttu-id="c66d8-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-547">Finance</span></span></td>
<td><span data-ttu-id="c66d8-548">35</span><span class="sxs-lookup"><span data-stu-id="c66d8-548">35</span></span></td>
<td><span data-ttu-id="c66d8-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="c66d8-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c66d8-550">436.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-550">436.00</span></span></td>
<td><span data-ttu-id="c66d8-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-552">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-552">CC003</span></span></td>
<td><span data-ttu-id="c66d8-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-553">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-554">55</span><span class="sxs-lookup"><span data-stu-id="c66d8-554">55</span></span></td>
<td><span data-ttu-id="c66d8-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="c66d8-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c66d8-556">685.14</span><span class="sxs-lookup"><span data-stu-id="c66d8-556">685.14</span></span></td>
<td><span data-ttu-id="c66d8-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-558">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-558">CC004</span></span></td>
<td><span data-ttu-id="c66d8-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-559">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-560">10</span><span class="sxs-lookup"><span data-stu-id="c66d8-560">10</span></span></td>
<td><span data-ttu-id="c66d8-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="c66d8-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c66d8-562">124.57</span><span class="sxs-lookup"><span data-stu-id="c66d8-562">124.57</span></span></td>
<td><span data-ttu-id="c66d8-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="c66d8-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-565">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-566">Magnitude</span></span></th>
<th><span data-ttu-id="c66d8-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-567">Allocation factor</span></span></th>
<th><span data-ttu-id="c66d8-568">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-568">Amount</span></span></th>
<th><span data-ttu-id="c66d8-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-570">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-570">CC003</span></span></td>
<td><span data-ttu-id="c66d8-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-571">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-572">65</span><span class="sxs-lookup"><span data-stu-id="c66d8-572">65</span></span></td>
<td><span data-ttu-id="c66d8-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c66d8-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c66d8-574">438.75</span><span class="sxs-lookup"><span data-stu-id="c66d8-574">438.75</span></span></td>
<td><span data-ttu-id="c66d8-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-576">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-576">CC004</span></span></td>
<td><span data-ttu-id="c66d8-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-577">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-578">35</span><span class="sxs-lookup"><span data-stu-id="c66d8-578">35</span></span></td>
<td><span data-ttu-id="c66d8-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c66d8-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c66d8-580">236.25</span><span class="sxs-lookup"><span data-stu-id="c66d8-580">236.25</span></span></td>
<td><span data-ttu-id="c66d8-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-582">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-582">CC003</span></span></td>
<td><span data-ttu-id="c66d8-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-583">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-584">65</span><span class="sxs-lookup"><span data-stu-id="c66d8-584">65</span></span></td>
<td><span data-ttu-id="c66d8-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c66d8-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c66d8-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c66d8-586">5,297.69</span></span></td>
<td><span data-ttu-id="c66d8-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-588">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-588">CC004</span></span></td>
<td><span data-ttu-id="c66d8-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-589">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-590">35</span><span class="sxs-lookup"><span data-stu-id="c66d8-590">35</span></span></td>
<td><span data-ttu-id="c66d8-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c66d8-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c66d8-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c66d8-592">2,852.60</span></span></td>
<td><span data-ttu-id="c66d8-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="c66d8-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-595">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-596">Magnitude</span></span></th>
<th><span data-ttu-id="c66d8-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-597">Allocation factor</span></span></th>
<th><span data-ttu-id="c66d8-598">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-598">Amount</span></span></th>
<th><span data-ttu-id="c66d8-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-600">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-601">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-602">60</span><span class="sxs-lookup"><span data-stu-id="c66d8-602">60</span></span></td>
<td><span data-ttu-id="c66d8-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c66d8-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c66d8-604">535.31</span><span class="sxs-lookup"><span data-stu-id="c66d8-604">535.31</span></span></td>
<td><span data-ttu-id="c66d8-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-606">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-607">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-608">20</span><span class="sxs-lookup"><span data-stu-id="c66d8-608">20</span></span></td>
<td><span data-ttu-id="c66d8-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c66d8-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c66d8-610">178.44</span><span class="sxs-lookup"><span data-stu-id="c66d8-610">178.44</span></span></td>
<td><span data-ttu-id="c66d8-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-612">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-613">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-614">60</span><span class="sxs-lookup"><span data-stu-id="c66d8-614">60</span></span></td>
<td><span data-ttu-id="c66d8-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c66d8-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c66d8-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c66d8-616">4,487.12</span></span></td>
<td><span data-ttu-id="c66d8-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-618">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-619">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-620">20</span><span class="sxs-lookup"><span data-stu-id="c66d8-620">20</span></span></td>
<td><span data-ttu-id="c66d8-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c66d8-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c66d8-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c66d8-622">1,495.71</span></span></td>
<td><span data-ttu-id="c66d8-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c66d8-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="c66d8-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-625">Cost object</span></span></th>
<th><span data-ttu-id="c66d8-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="c66d8-626">Magnitude</span></span></th>
<th><span data-ttu-id="c66d8-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-627">Allocation factor</span></span></th>
<th><span data-ttu-id="c66d8-628">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-628">Amount</span></span></th>
<th><span data-ttu-id="c66d8-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-630">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-631">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-632">80</span><span class="sxs-lookup"><span data-stu-id="c66d8-632">80</span></span></td>
<td><span data-ttu-id="c66d8-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c66d8-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c66d8-634">241.05</span><span class="sxs-lookup"><span data-stu-id="c66d8-634">241.05</span></span></td>
<td><span data-ttu-id="c66d8-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-636">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-637">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-638">15</span><span class="sxs-lookup"><span data-stu-id="c66d8-638">15</span></span></td>
<td><span data-ttu-id="c66d8-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c66d8-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c66d8-640">45.20</span><span class="sxs-lookup"><span data-stu-id="c66d8-640">45.20</span></span></td>
<td><span data-ttu-id="c66d8-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-642">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-643">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-644">80</span><span class="sxs-lookup"><span data-stu-id="c66d8-644">80</span></span></td>
<td><span data-ttu-id="c66d8-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c66d8-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c66d8-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c66d8-646">2,507.09</span></span></td>
<td><span data-ttu-id="c66d8-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-648">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-649">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-650">15</span><span class="sxs-lookup"><span data-stu-id="c66d8-650">15</span></span></td>
<td><span data-ttu-id="c66d8-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c66d8-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c66d8-652">470.08</span><span class="sxs-lookup"><span data-stu-id="c66d8-652">470.08</span></span></td>
<td><span data-ttu-id="c66d8-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c66d8-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="c66d8-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-655">Journal</span></span></th>
<th><span data-ttu-id="c66d8-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c66d8-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c66d8-658">Versione</span><span class="sxs-lookup"><span data-stu-id="c66d8-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-659">00004</span><span class="sxs-lookup"><span data-stu-id="c66d8-659">00004</span></span></td>
<td><span data-ttu-id="c66d8-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="c66d8-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="c66d8-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="c66d8-661">Fiscal</span></span></td>
<td><span data-ttu-id="c66d8-662">2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-662">2017</span></span></td>
<td><span data-ttu-id="c66d8-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-663">Period 1</span></span></td>
<td><span data-ttu-id="c66d8-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="c66d8-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c66d8-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-668">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-669">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-670">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-672">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-672">CC001</span></span></td>
<td><span data-ttu-id="c66d8-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-673">HR</span></span></td>
<td><span data-ttu-id="c66d8-674">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-674">10001</span></span></td>
<td><span data-ttu-id="c66d8-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-675">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-676">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-677">500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-679">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-679">CC001</span></span></td>
<td><span data-ttu-id="c66d8-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-680">HR</span></span></td>
<td><span data-ttu-id="c66d8-681">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-681">10001</span></span></td>
<td><span data-ttu-id="c66d8-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-682">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-683">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="c66d8-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-686">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-686">CC002</span></span></td>
<td><span data-ttu-id="c66d8-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-687">Finance</span></span></td>
<td><span data-ttu-id="c66d8-688">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-688">10001</span></span></td>
<td><span data-ttu-id="c66d8-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-689">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-690">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-691">675.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-693">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-693">CC002</span></span></td>
<td><span data-ttu-id="c66d8-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-694">Finance</span></span></td>
<td><span data-ttu-id="c66d8-695">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-695">10001</span></span></td>
<td><span data-ttu-id="c66d8-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-696">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-697">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="c66d8-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-700">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-700">CC003</span></span></td>
<td><span data-ttu-id="c66d8-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-701">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-702">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-702">10001</span></span></td>
<td><span data-ttu-id="c66d8-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-703">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-704">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-705">713.75</span><span class="sxs-lookup"><span data-stu-id="c66d8-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-707">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-707">CC003</span></span></td>
<td><span data-ttu-id="c66d8-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-708">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-709">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-709">10001</span></span></td>
<td><span data-ttu-id="c66d8-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-710">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-711">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="c66d8-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-714">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-714">CC003</span></span></td>
<td><span data-ttu-id="c66d8-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-715">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-716">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-716">10001</span></span></td>
<td><span data-ttu-id="c66d8-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-717">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-718">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-719">286.25</span><span class="sxs-lookup"><span data-stu-id="c66d8-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-721">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-721">CC003</span></span></td>
<td><span data-ttu-id="c66d8-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-722">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-723">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-723">10001</span></span></td>
<td><span data-ttu-id="c66d8-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-724">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-725">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="c66d8-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-728">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-729">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-730">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-730">10001</span></span></td>
<td><span data-ttu-id="c66d8-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-731">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-732">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-733">776.36</span><span class="sxs-lookup"><span data-stu-id="c66d8-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-735">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-736">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-737">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-737">10001</span></span></td>
<td><span data-ttu-id="c66d8-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-738">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-739">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c66d8-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-742">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-743">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-744">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-744">10001</span></span></td>
<td><span data-ttu-id="c66d8-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-745">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-746">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-747">223.64</span><span class="sxs-lookup"><span data-stu-id="c66d8-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="c66d8-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-749">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-750">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-751">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-751">10001</span></span></td>
<td><span data-ttu-id="c66d8-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-752">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-753">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c66d8-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c66d8-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c66d8-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c66d8-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-757">Cost element</span></span></th>
<th><span data-ttu-id="c66d8-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-758">Cost behavior</span></span></th>
<th><span data-ttu-id="c66d8-759">Importo</span><span class="sxs-lookup"><span data-stu-id="c66d8-759">Amount</span></span></th>
<th><span data-ttu-id="c66d8-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="c66d8-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c66d8-761">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-761">CC001</span></span></td>
<td><span data-ttu-id="c66d8-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-762">HR</span></span></td>
<td><span data-ttu-id="c66d8-763">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-763">10001</span></span></td>
<td><span data-ttu-id="c66d8-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-764">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-765">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-766">-500.00</span></span></td>
<td><span data-ttu-id="c66d8-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-768">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-768">CC002</span></span></td>
<td><span data-ttu-id="c66d8-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-769">Finance</span></span></td>
<td><span data-ttu-id="c66d8-770">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-770">10001</span></span></td>
<td><span data-ttu-id="c66d8-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-771">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-772">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-773">175.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-773">175.00</span></span></td>
<td><span data-ttu-id="c66d8-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-775">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-775">CC003</span></span></td>
<td><span data-ttu-id="c66d8-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-776">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-777">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-777">10001</span></span></td>
<td><span data-ttu-id="c66d8-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-778">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-779">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-780">275.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-780">275.00</span></span></td>
<td><span data-ttu-id="c66d8-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-782">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-782">CC004</span></span></td>
<td><span data-ttu-id="c66d8-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-783">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-784">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-784">10001</span></span></td>
<td><span data-ttu-id="c66d8-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-785">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-786">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-787">50,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-787">50,00</span></span></td>
<td><span data-ttu-id="c66d8-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-789">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-789">CC001</span></span></td>
<td><span data-ttu-id="c66d8-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="c66d8-790">HR</span></span></td>
<td><span data-ttu-id="c66d8-791">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-791">10001</span></span></td>
<td><span data-ttu-id="c66d8-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-792">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-793">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="c66d8-794">-1,245.71</span></span></td>
<td><span data-ttu-id="c66d8-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-796">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-796">CC002</span></span></td>
<td><span data-ttu-id="c66d8-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-797">Finance</span></span></td>
<td><span data-ttu-id="c66d8-798">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-798">10001</span></span></td>
<td><span data-ttu-id="c66d8-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-799">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-800">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-801">436.00</span><span class="sxs-lookup"><span data-stu-id="c66d8-801">436.00</span></span></td>
<td><span data-ttu-id="c66d8-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-803">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-803">CC003</span></span></td>
<td><span data-ttu-id="c66d8-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-804">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-805">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-805">10001</span></span></td>
<td><span data-ttu-id="c66d8-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-806">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-807">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-808">685.14</span><span class="sxs-lookup"><span data-stu-id="c66d8-808">685.14</span></span></td>
<td><span data-ttu-id="c66d8-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-810">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-810">CC004</span></span></td>
<td><span data-ttu-id="c66d8-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-811">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-812">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-812">10001</span></span></td>
<td><span data-ttu-id="c66d8-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-813">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-814">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-815">124.57</span><span class="sxs-lookup"><span data-stu-id="c66d8-815">124.57</span></span></td>
<td><span data-ttu-id="c66d8-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-817">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-817">CC002</span></span></td>
<td><span data-ttu-id="c66d8-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-818">Finance</span></span></td>
<td><span data-ttu-id="c66d8-819">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-819">10001</span></span></td>
<td><span data-ttu-id="c66d8-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-820">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-821">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-822">-675.00</span></span></td>
<td><span data-ttu-id="c66d8-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-824">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-824">CC003</span></span></td>
<td><span data-ttu-id="c66d8-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-825">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-826">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-826">10001</span></span></td>
<td><span data-ttu-id="c66d8-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-827">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-828">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-829">438.75</span><span class="sxs-lookup"><span data-stu-id="c66d8-829">438.75</span></span></td>
<td><span data-ttu-id="c66d8-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-831">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-831">CC004</span></span></td>
<td><span data-ttu-id="c66d8-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-832">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-833">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-833">10001</span></span></td>
<td><span data-ttu-id="c66d8-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-834">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-835">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-836">236.25</span><span class="sxs-lookup"><span data-stu-id="c66d8-836">236.25</span></span></td>
<td><span data-ttu-id="c66d8-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-838">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-838">CC002</span></span></td>
<td><span data-ttu-id="c66d8-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="c66d8-839">Finance</span></span></td>
<td><span data-ttu-id="c66d8-840">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-840">10001</span></span></td>
<td><span data-ttu-id="c66d8-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-841">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-842">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="c66d8-843">-8,150.29</span></span></td>
<td><span data-ttu-id="c66d8-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-845">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-845">CC003</span></span></td>
<td><span data-ttu-id="c66d8-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-846">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-847">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-847">10001</span></span></td>
<td><span data-ttu-id="c66d8-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-848">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-849">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c66d8-850">5,297.69</span></span></td>
<td><span data-ttu-id="c66d8-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-852">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-852">CC004</span></span></td>
<td><span data-ttu-id="c66d8-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-853">Packaging</span></span></td>
<td><span data-ttu-id="c66d8-854">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-854">10001</span></span></td>
<td><span data-ttu-id="c66d8-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-855">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-856">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c66d8-857">2,852.60</span></span></td>
<td><span data-ttu-id="c66d8-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-859">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-859">CC003</span></span></td>
<td><span data-ttu-id="c66d8-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-860">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-861">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-861">10001</span></span></td>
<td><span data-ttu-id="c66d8-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-862">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-863">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="c66d8-864">-713.75</span></span></td>
<td><span data-ttu-id="c66d8-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-866">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-867">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-868">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-868">10001</span></span></td>
<td><span data-ttu-id="c66d8-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-869">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-870">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-871">535.31</span><span class="sxs-lookup"><span data-stu-id="c66d8-871">535.31</span></span></td>
<td><span data-ttu-id="c66d8-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-873">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-874">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-875">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-875">10001</span></span></td>
<td><span data-ttu-id="c66d8-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-876">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-877">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-878">178.44</span><span class="sxs-lookup"><span data-stu-id="c66d8-878">178.44</span></span></td>
<td><span data-ttu-id="c66d8-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-880">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-880">CC003</span></span></td>
<td><span data-ttu-id="c66d8-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-881">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-882">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-882">10001</span></span></td>
<td><span data-ttu-id="c66d8-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-883">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-884">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="c66d8-885">-5,982.83</span></span></td>
<td><span data-ttu-id="c66d8-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-887">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-888">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-889">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-889">10001</span></span></td>
<td><span data-ttu-id="c66d8-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-890">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-891">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c66d8-892">4,487.12</span></span></td>
<td><span data-ttu-id="c66d8-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-894">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-895">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-896">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-896">10001</span></span></td>
<td><span data-ttu-id="c66d8-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-897">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-898">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c66d8-899">1,495.71</span></span></td>
<td><span data-ttu-id="c66d8-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-901">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-901">CC003</span></span></td>
<td><span data-ttu-id="c66d8-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-902">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-903">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-903">10001</span></span></td>
<td><span data-ttu-id="c66d8-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-904">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-905">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="c66d8-906">-286.25</span></span></td>
<td><span data-ttu-id="c66d8-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-908">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-909">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-910">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-910">10001</span></span></td>
<td><span data-ttu-id="c66d8-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-911">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-912">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-913">241.05</span><span class="sxs-lookup"><span data-stu-id="c66d8-913">241.05</span></span></td>
<td><span data-ttu-id="c66d8-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-915">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-916">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-917">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-917">10001</span></span></td>
<td><span data-ttu-id="c66d8-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-918">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-919">Fixed cost</span></span></td>
<td><span data-ttu-id="c66d8-920">45.20</span><span class="sxs-lookup"><span data-stu-id="c66d8-920">45.20</span></span></td>
<td><span data-ttu-id="c66d8-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-922">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-922">CC003</span></span></td>
<td><span data-ttu-id="c66d8-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="c66d8-923">Assembly</span></span></td>
<td><span data-ttu-id="c66d8-924">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-924">10001</span></span></td>
<td><span data-ttu-id="c66d8-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-925">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-926">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="c66d8-927">-2,977.17</span></span></td>
<td><span data-ttu-id="c66d8-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-929">Prod 1</span></span></td>
<td><span data-ttu-id="c66d8-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-930">Product 1</span></span></td>
<td><span data-ttu-id="c66d8-931">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-931">10001</span></span></td>
<td><span data-ttu-id="c66d8-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-932">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-933">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c66d8-934">2,507.09</span></span></td>
<td><span data-ttu-id="c66d8-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c66d8-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-936">Prod 2</span></span></td>
<td><span data-ttu-id="c66d8-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-937">Product 2</span></span></td>
<td><span data-ttu-id="c66d8-938">10001</span><span class="sxs-lookup"><span data-stu-id="c66d8-938">10001</span></span></td>
<td><span data-ttu-id="c66d8-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-939">Electricity</span></span></td>
<td><span data-ttu-id="c66d8-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-940">Variable cost</span></span></td>
<td><span data-ttu-id="c66d8-941">470.08</span><span class="sxs-lookup"><span data-stu-id="c66d8-941">470.08</span></span></td>
<td><span data-ttu-id="c66d8-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="c66d8-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="c66d8-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="c66d8-943">Conclusion</span></span>
<span data-ttu-id="c66d8-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="c66d8-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="c66d8-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="c66d8-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="c66d8-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="c66d8-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="c66d8-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="c66d8-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="c66d8-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="c66d8-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="c66d8-950">Totale</span><span class="sxs-lookup"><span data-stu-id="c66d8-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c66d8-951">CC099</span><span class="sxs-lookup"><span data-stu-id="c66d8-951">CC099</span></span></th>
<th><span data-ttu-id="c66d8-952">CC001</span><span class="sxs-lookup"><span data-stu-id="c66d8-952">CC001</span></span></th>
<th><span data-ttu-id="c66d8-953">CC002</span><span class="sxs-lookup"><span data-stu-id="c66d8-953">CC002</span></span></th>
<th><span data-ttu-id="c66d8-954">CC003</span><span class="sxs-lookup"><span data-stu-id="c66d8-954">CC003</span></span></th>
<th><span data-ttu-id="c66d8-955">CC004</span><span class="sxs-lookup"><span data-stu-id="c66d8-955">CC004</span></span></th>
<th><span data-ttu-id="c66d8-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-956">Proj 1</span></span></th>
<th><span data-ttu-id="c66d8-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-957">Proj 2</span></span></th>
<th><span data-ttu-id="c66d8-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c66d8-958">Prod 1</span></span></th>
<th><span data-ttu-id="c66d8-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c66d8-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="c66d8-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="c66d8-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="c66d8-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="c66d8-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-971">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-971">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c66d8-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="c66d8-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-973">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-974">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-975">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-976">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-977">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-978">776.36</span><span class="sxs-lookup"><span data-stu-id="c66d8-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-979">223.64</span><span class="sxs-lookup"><span data-stu-id="c66d8-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c66d8-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="c66d8-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-982">000</span><span class="sxs-lookup"><span data-stu-id="c66d8-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-983">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-984">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-985">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-986">0,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-987">30,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-988">10,00</span><span class="sxs-lookup"><span data-stu-id="c66d8-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c66d8-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c66d8-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c66d8-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c66d8-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c66d8-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="c66d8-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c66d8-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="c66d8-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="c66d8-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="c66d8-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="c66d8-996">Per ulteriori informazioni, vedere [Criteri rollup costi e calcolo dei costi generali](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="c66d8-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



