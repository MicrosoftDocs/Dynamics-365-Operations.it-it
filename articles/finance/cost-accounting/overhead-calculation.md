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
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444894"
---
# <a name="overhead-calculation"></a><span data-ttu-id="5bf14-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="5bf14-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5bf14-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="5bf14-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="5bf14-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="5bf14-105">Term definition</span></span>
---------------

<span data-ttu-id="5bf14-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="5bf14-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="5bf14-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="5bf14-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="5bf14-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="5bf14-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="5bf14-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="5bf14-109">Rent</span></span>
-   <span data-ttu-id="5bf14-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-110">Electricity</span></span>
-   <span data-ttu-id="5bf14-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="5bf14-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="5bf14-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="5bf14-112">Overhead calculation overview</span></span>
<span data-ttu-id="5bf14-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="5bf14-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="5bf14-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="5bf14-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="5bf14-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="5bf14-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="5bf14-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="5bf14-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="5bf14-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="5bf14-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="5bf14-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="5bf14-119">Version type</span></span>
-   <span data-ttu-id="5bf14-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="5bf14-120">Date and time</span></span>
-   <span data-ttu-id="5bf14-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="5bf14-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="5bf14-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-122">Fiscal year</span></span>
-   <span data-ttu-id="5bf14-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-123">Fiscal period</span></span>

<span data-ttu-id="5bf14-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="5bf14-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="5bf14-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="5bf14-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="5bf14-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="5bf14-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="5bf14-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="5bf14-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="5bf14-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="5bf14-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="5bf14-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="5bf14-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="5bf14-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="5bf14-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="5bf14-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="5bf14-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="5bf14-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="5bf14-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="5bf14-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="5bf14-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="5bf14-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="5bf14-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="5bf14-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="5bf14-140">Main account</span></span></th>
<th><span data-ttu-id="5bf14-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="5bf14-143">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-143">CC099</span></span></td>
<td><span data-ttu-id="5bf14-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-144">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-145">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-145">10001</span></span></td>
<td><span data-ttu-id="5bf14-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-146">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="5bf14-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="5bf14-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="5bf14-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="5bf14-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="5bf14-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="5bf14-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-151">Define the cost behavior rule</span></span>

<span data-ttu-id="5bf14-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="5bf14-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="5bf14-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="5bf14-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="5bf14-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="5bf14-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="5bf14-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="5bf14-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="5bf14-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="5bf14-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-160">Journal</span></span></th>
<th><span data-ttu-id="5bf14-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bf14-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bf14-163">Versione</span><span class="sxs-lookup"><span data-stu-id="5bf14-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-164">00001</span><span class="sxs-lookup"><span data-stu-id="5bf14-164">00001</span></span></td>
<td><span data-ttu-id="5bf14-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="5bf14-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-166">Fiscal</span></span></td>
<td><span data-ttu-id="5bf14-167">2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-167">2017</span></span></td>
<td><span data-ttu-id="5bf14-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-168">Period 1</span></span></td>
<td><span data-ttu-id="5bf14-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5bf14-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="5bf14-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-173">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-174">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-175">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="5bf14-177">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-177">CC099</span></span></td>
<td><span data-ttu-id="5bf14-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-178">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-179">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-179">10001</span></span></td>
<td><span data-ttu-id="5bf14-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-180">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="5bf14-181">Unclassified</span></span></td>
<td><span data-ttu-id="5bf14-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bf14-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-185">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-186">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-187">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-187">Amount</span></span></th>
<th><span data-ttu-id="5bf14-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-189">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-189">CC099</span></span></td>
<td><span data-ttu-id="5bf14-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-190">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-191">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-191">10001</span></span></td>
<td><span data-ttu-id="5bf14-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-192">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="5bf14-193">Unclassified</span></span></td>
<td><span data-ttu-id="5bf14-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-194">10,000.00</span></span></td>
<td><span data-ttu-id="5bf14-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-196">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-196">CC099</span></span></td>
<td><span data-ttu-id="5bf14-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-197">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-198">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-198">10001</span></span></td>
<td><span data-ttu-id="5bf14-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-199">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="5bf14-200">Unclassified</span></span></td>
<td><span data-ttu-id="5bf14-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-201">-10,000.00</span></span></td>
<td><span data-ttu-id="5bf14-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-203">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-203">CC099</span></span></td>
<td><span data-ttu-id="5bf14-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-204">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-205">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-205">10001</span></span></td>
<td><span data-ttu-id="5bf14-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-206">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-207">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-208">1,000.00</span></span></td>
<td><span data-ttu-id="5bf14-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-210">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-210">CC099</span></span></td>
<td><span data-ttu-id="5bf14-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-211">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-212">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-212">10001</span></span></td>
<td><span data-ttu-id="5bf14-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-213">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-214">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-215">9,000.00</span></span></td>
<td><span data-ttu-id="5bf14-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5bf14-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="5bf14-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="5bf14-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="5bf14-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="5bf14-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="5bf14-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="5bf14-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-221">Define the cost distribution rule</span></span>

<span data-ttu-id="5bf14-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="5bf14-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="5bf14-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="5bf14-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="5bf14-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="5bf14-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="5bf14-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="5bf14-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="5bf14-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="5bf14-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="5bf14-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-228">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-229">KWH</span><span class="sxs-lookup"><span data-stu-id="5bf14-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-230">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-230">CC001</span></span></td>
<td><span data-ttu-id="5bf14-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-231">HR</span></span></td>
<td><span data-ttu-id="5bf14-232">1.000</span><span class="sxs-lookup"><span data-stu-id="5bf14-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-233">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-233">CC002</span></span></td>
<td><span data-ttu-id="5bf14-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-234">Finance</span></span></td>
<td><span data-ttu-id="5bf14-235">6.000</span><span class="sxs-lookup"><span data-stu-id="5bf14-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-236">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-236">CC003</span></span></td>
<td><span data-ttu-id="5bf14-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-237">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-238">0</span><span class="sxs-lookup"><span data-stu-id="5bf14-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="5bf14-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-240">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-241">Magnitude</span></span></th>
<th><span data-ttu-id="5bf14-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-242">Allocation factor</span></span></th>
<th><span data-ttu-id="5bf14-243">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-244">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-244">CC001</span></span></td>
<td><span data-ttu-id="5bf14-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-245">HR</span></span></td>
<td><span data-ttu-id="5bf14-246">1.000</span><span class="sxs-lookup"><span data-stu-id="5bf14-246">1,000</span></span></td>
<td><span data-ttu-id="5bf14-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5bf14-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5bf14-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-249">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-249">CC002</span></span></td>
<td><span data-ttu-id="5bf14-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-250">Finance</span></span></td>
<td><span data-ttu-id="5bf14-251">6.000</span><span class="sxs-lookup"><span data-stu-id="5bf14-251">6,000</span></span></td>
<td><span data-ttu-id="5bf14-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5bf14-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5bf14-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-254">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-254">CC003</span></span></td>
<td><span data-ttu-id="5bf14-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-255">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-256">0</span><span class="sxs-lookup"><span data-stu-id="5bf14-256">0</span></span></td>
<td><span data-ttu-id="5bf14-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5bf14-258">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="5bf14-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="5bf14-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="5bf14-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-261">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-262">Formula</span><span class="sxs-lookup"><span data-stu-id="5bf14-262">Formula</span></span></th>
<th><span data-ttu-id="5bf14-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-263">Magnitude</span></span></th>
<th><span data-ttu-id="5bf14-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-264">Allocation factor</span></span></th>
<th><span data-ttu-id="5bf14-265">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-266">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-266">CC001</span></span></td>
<td><span data-ttu-id="5bf14-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-267">HR</span></span></td>
<td><span data-ttu-id="5bf14-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5bf14-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5bf14-269">1</span><span class="sxs-lookup"><span data-stu-id="5bf14-269">1</span></span></td>
<td><span data-ttu-id="5bf14-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5bf14-271">500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-272">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-272">CC002</span></span></td>
<td><span data-ttu-id="5bf14-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-273">Finance</span></span></td>
<td><span data-ttu-id="5bf14-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5bf14-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5bf14-275">1</span><span class="sxs-lookup"><span data-stu-id="5bf14-275">1</span></span></td>
<td><span data-ttu-id="5bf14-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5bf14-277">500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-278">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-278">CC003</span></span></td>
<td><span data-ttu-id="5bf14-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-279">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5bf14-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5bf14-281">0</span><span class="sxs-lookup"><span data-stu-id="5bf14-281">0</span></span></td>
<td><span data-ttu-id="5bf14-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5bf14-283">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5bf14-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-285">Journal</span></span></th>
<th><span data-ttu-id="5bf14-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bf14-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bf14-288">Versione</span><span class="sxs-lookup"><span data-stu-id="5bf14-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-289">00002</span><span class="sxs-lookup"><span data-stu-id="5bf14-289">00002</span></span></td>
<td><span data-ttu-id="5bf14-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="5bf14-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-291">Fiscal</span></span></td>
<td><span data-ttu-id="5bf14-292">2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-292">2017</span></span></td>
<td><span data-ttu-id="5bf14-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-293">Period 1</span></span></td>
<td><span data-ttu-id="5bf14-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5bf14-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="5bf14-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-298">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-299">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-300">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-302">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-302">CC099</span></span></td>
<td><span data-ttu-id="5bf14-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-303">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-304">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-304">10001</span></span></td>
<td><span data-ttu-id="5bf14-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-305">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-306">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-309">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-309">CC099</span></span></td>
<td><span data-ttu-id="5bf14-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-310">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-311">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-311">10001</span></span></td>
<td><span data-ttu-id="5bf14-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-312">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-313">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bf14-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-317">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-318">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-319">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-319">Amount</span></span></th>
<th><span data-ttu-id="5bf14-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-321">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-321">CC099</span></span></td>
<td><span data-ttu-id="5bf14-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-322">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-323">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-323">10001</span></span></td>
<td><span data-ttu-id="5bf14-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-324">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-325">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-326">-1,000.00</span></span></td>
<td><span data-ttu-id="5bf14-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-328">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-328">CC001</span></span></td>
<td><span data-ttu-id="5bf14-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-329">HR</span></span></td>
<td><span data-ttu-id="5bf14-330">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-330">10001</span></span></td>
<td><span data-ttu-id="5bf14-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-331">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-332">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-333">500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-333">500.00</span></span></td>
<td><span data-ttu-id="5bf14-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-335">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-335">CC002</span></span></td>
<td><span data-ttu-id="5bf14-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-336">Finance</span></span></td>
<td><span data-ttu-id="5bf14-337">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-337">10001</span></span></td>
<td><span data-ttu-id="5bf14-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-338">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-339">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-340">500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-340">500.00</span></span></td>
<td><span data-ttu-id="5bf14-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-342">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-342">CC099</span></span></td>
<td><span data-ttu-id="5bf14-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="5bf14-343">Default cost center</span></span></td>
<td><span data-ttu-id="5bf14-344">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-344">10001</span></span></td>
<td><span data-ttu-id="5bf14-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-345">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-346">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-347">-9,000.00</span></span></td>
<td><span data-ttu-id="5bf14-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-349">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-349">CC001</span></span></td>
<td><span data-ttu-id="5bf14-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-350">HR</span></span></td>
<td><span data-ttu-id="5bf14-351">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-351">10001</span></span></td>
<td><span data-ttu-id="5bf14-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-352">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-353">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5bf14-354">1,285.71</span></span></td>
<td><span data-ttu-id="5bf14-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-356">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-356">CC002</span></span></td>
<td><span data-ttu-id="5bf14-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-357">Finance</span></span></td>
<td><span data-ttu-id="5bf14-358">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-358">10001</span></span></td>
<td><span data-ttu-id="5bf14-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-359">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-360">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5bf14-361">7,714.29</span></span></td>
<td><span data-ttu-id="5bf14-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5bf14-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="5bf14-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="5bf14-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="5bf14-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="5bf14-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="5bf14-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="5bf14-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="5bf14-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="5bf14-367">Define the overhead rate</span></span>

<span data-ttu-id="5bf14-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="5bf14-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="5bf14-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="5bf14-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-370">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-371">Ore</span><span class="sxs-lookup"><span data-stu-id="5bf14-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-372">Proj 1</span></span></td>
<td><span data-ttu-id="5bf14-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-373">Project 1</span></span></td>
<td><span data-ttu-id="5bf14-374">3</span><span class="sxs-lookup"><span data-stu-id="5bf14-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-375">Proj 2</span></span></td>
<td><span data-ttu-id="5bf14-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-376">Project 2</span></span></td>
<td><span data-ttu-id="5bf14-377">1</span><span class="sxs-lookup"><span data-stu-id="5bf14-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="5bf14-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-379">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-380">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-381">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-382">Unità</span><span class="sxs-lookup"><span data-stu-id="5bf14-382">Units</span></span></th>
<th><span data-ttu-id="5bf14-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="5bf14-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-384">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-384">CC001</span></span></td>
<td><span data-ttu-id="5bf14-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-385">HR</span></span></td>
<td><span data-ttu-id="5bf14-386">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-386">10001</span></span></td>
<td><span data-ttu-id="5bf14-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-387">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-388">1</span><span class="sxs-lookup"><span data-stu-id="5bf14-388">1</span></span></td>
<td><span data-ttu-id="5bf14-389">10</span><span class="sxs-lookup"><span data-stu-id="5bf14-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-391">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-392">Magnitude</span></span></th>
<th><span data-ttu-id="5bf14-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-393">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-394">Allocation factor</span></span></th>
<th><span data-ttu-id="5bf14-395">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-396">Proj 1</span></span></td>
<td><span data-ttu-id="5bf14-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-397">Project 1</span></span></td>
<td><span data-ttu-id="5bf14-398">3</span><span class="sxs-lookup"><span data-stu-id="5bf14-398">3</span></span></td>
<td><span data-ttu-id="5bf14-399">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-399">10001</span></span></td>
<td><span data-ttu-id="5bf14-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5bf14-401">30,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-402">Proj 2</span></span></td>
<td><span data-ttu-id="5bf14-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-403">Project 2</span></span></td>
<td><span data-ttu-id="5bf14-404">1</span><span class="sxs-lookup"><span data-stu-id="5bf14-404">1</span></span></td>
<td><span data-ttu-id="5bf14-405">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-405">10001</span></span></td>
<td><span data-ttu-id="5bf14-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5bf14-407">10,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5bf14-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-409">Journal</span></span></th>
<th><span data-ttu-id="5bf14-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bf14-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bf14-412">Versione</span><span class="sxs-lookup"><span data-stu-id="5bf14-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-413">00003</span><span class="sxs-lookup"><span data-stu-id="5bf14-413">00003</span></span></td>
<td><span data-ttu-id="5bf14-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="5bf14-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="5bf14-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-415">Fiscal</span></span></td>
<td><span data-ttu-id="5bf14-416">2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-416">2017</span></span></td>
<td><span data-ttu-id="5bf14-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-417">Period 1</span></span></td>
<td><span data-ttu-id="5bf14-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="5bf14-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="5bf14-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-421">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-424">Proj 1</span></span></td>
<td><span data-ttu-id="5bf14-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5bf14-426">3,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-428">Proj 2</span></span></td>
<td><span data-ttu-id="5bf14-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5bf14-430">1,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bf14-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-433">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-434">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-435">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-435">Amount</span></span></th>
<th><span data-ttu-id="5bf14-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="5bf14-437">CC0001</span></span></td>
<td><span data-ttu-id="5bf14-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-438">HR</span></span></td>
<td><span data-ttu-id="5bf14-439">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-439">10001</span></span></td>
<td><span data-ttu-id="5bf14-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-440">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-441">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-442">-30.00</span></span></td>
<td><span data-ttu-id="5bf14-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-444">Proj 1</span></span></td>
<td><span data-ttu-id="5bf14-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5bf14-446">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-446">10001</span></span></td>
<td><span data-ttu-id="5bf14-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-447">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-448">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-449">30,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-449">30.00</span></span></td>
<td><span data-ttu-id="5bf14-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-451">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-451">CC001</span></span></td>
<td><span data-ttu-id="5bf14-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-452">HR</span></span></td>
<td><span data-ttu-id="5bf14-453">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-453">10001</span></span></td>
<td><span data-ttu-id="5bf14-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-454">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-455">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-456">-10.00</span></span></td>
<td><span data-ttu-id="5bf14-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-458">Proj 2</span></span></td>
<td><span data-ttu-id="5bf14-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5bf14-460">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-460">10001</span></span></td>
<td><span data-ttu-id="5bf14-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-461">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-462">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-463">10.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-463">10.00</span></span></td>
<td><span data-ttu-id="5bf14-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="5bf14-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="5bf14-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="5bf14-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="5bf14-468">Finance supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="5bf14-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="5bf14-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="5bf14-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="5bf14-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="5bf14-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="5bf14-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="5bf14-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="5bf14-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="5bf14-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="5bf14-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="5bf14-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="5bf14-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="5bf14-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="5bf14-475">Define the cost allocation</span></span>

<span data-ttu-id="5bf14-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="5bf14-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="5bf14-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="5bf14-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-479">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="5bf14-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-481">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-481">CC002</span></span></td>
<td><span data-ttu-id="5bf14-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-482">Finance</span></span></td>
<td><span data-ttu-id="5bf14-483">35</span><span class="sxs-lookup"><span data-stu-id="5bf14-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-484">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-484">CC003</span></span></td>
<td><span data-ttu-id="5bf14-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-485">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-486">55</span><span class="sxs-lookup"><span data-stu-id="5bf14-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-487">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-487">CC004</span></span></td>
<td><span data-ttu-id="5bf14-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-488">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-489">10</span><span class="sxs-lookup"><span data-stu-id="5bf14-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="5bf14-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="5bf14-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-492">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-494">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-494">CC003</span></span></td>
<td><span data-ttu-id="5bf14-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-495">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-496">65</span><span class="sxs-lookup"><span data-stu-id="5bf14-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-497">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-497">CC004</span></span></td>
<td><span data-ttu-id="5bf14-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-498">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-499">35</span><span class="sxs-lookup"><span data-stu-id="5bf14-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="5bf14-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="5bf14-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-502">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="5bf14-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-504">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-505">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-506">60</span><span class="sxs-lookup"><span data-stu-id="5bf14-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-507">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-508">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-509">20</span><span class="sxs-lookup"><span data-stu-id="5bf14-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="5bf14-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="5bf14-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-512">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="5bf14-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-514">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-515">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-516">80</span><span class="sxs-lookup"><span data-stu-id="5bf14-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-517">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-518">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-519">15</span><span class="sxs-lookup"><span data-stu-id="5bf14-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5bf14-520">Le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="5bf14-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="5bf14-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="5bf14-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="5bf14-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="5bf14-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-523">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-524">Magnitude</span></span></th>
<th><span data-ttu-id="5bf14-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-525">Allocation factor</span></span></th>
<th><span data-ttu-id="5bf14-526">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-526">Amount</span></span></th>
<th><span data-ttu-id="5bf14-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-528">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-528">CC002</span></span></td>
<td><span data-ttu-id="5bf14-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-529">Finance</span></span></td>
<td><span data-ttu-id="5bf14-530">35</span><span class="sxs-lookup"><span data-stu-id="5bf14-530">35</span></span></td>
<td><span data-ttu-id="5bf14-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5bf14-532">175.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-532">175.00</span></span></td>
<td><span data-ttu-id="5bf14-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-534">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-534">CC003</span></span></td>
<td><span data-ttu-id="5bf14-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-535">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-536">55</span><span class="sxs-lookup"><span data-stu-id="5bf14-536">55</span></span></td>
<td><span data-ttu-id="5bf14-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5bf14-538">275.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-538">275.00</span></span></td>
<td><span data-ttu-id="5bf14-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-540">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-540">CC004</span></span></td>
<td><span data-ttu-id="5bf14-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-541">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-542">10</span><span class="sxs-lookup"><span data-stu-id="5bf14-542">10</span></span></td>
<td><span data-ttu-id="5bf14-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5bf14-544">50,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-544">50.00</span></span></td>
<td><span data-ttu-id="5bf14-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-546">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-546">CC002</span></span></td>
<td><span data-ttu-id="5bf14-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-547">Finance</span></span></td>
<td><span data-ttu-id="5bf14-548">35</span><span class="sxs-lookup"><span data-stu-id="5bf14-548">35</span></span></td>
<td><span data-ttu-id="5bf14-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="5bf14-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5bf14-550">436.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-550">436.00</span></span></td>
<td><span data-ttu-id="5bf14-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-552">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-552">CC003</span></span></td>
<td><span data-ttu-id="5bf14-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-553">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-554">55</span><span class="sxs-lookup"><span data-stu-id="5bf14-554">55</span></span></td>
<td><span data-ttu-id="5bf14-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="5bf14-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5bf14-556">685.14</span><span class="sxs-lookup"><span data-stu-id="5bf14-556">685.14</span></span></td>
<td><span data-ttu-id="5bf14-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-558">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-558">CC004</span></span></td>
<td><span data-ttu-id="5bf14-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-559">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-560">10</span><span class="sxs-lookup"><span data-stu-id="5bf14-560">10</span></span></td>
<td><span data-ttu-id="5bf14-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="5bf14-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5bf14-562">124.57</span><span class="sxs-lookup"><span data-stu-id="5bf14-562">124.57</span></span></td>
<td><span data-ttu-id="5bf14-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="5bf14-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-565">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-566">Magnitude</span></span></th>
<th><span data-ttu-id="5bf14-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-567">Allocation factor</span></span></th>
<th><span data-ttu-id="5bf14-568">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-568">Amount</span></span></th>
<th><span data-ttu-id="5bf14-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-570">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-570">CC003</span></span></td>
<td><span data-ttu-id="5bf14-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-571">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-572">65</span><span class="sxs-lookup"><span data-stu-id="5bf14-572">65</span></span></td>
<td><span data-ttu-id="5bf14-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5bf14-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5bf14-574">438.75</span><span class="sxs-lookup"><span data-stu-id="5bf14-574">438.75</span></span></td>
<td><span data-ttu-id="5bf14-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-576">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-576">CC004</span></span></td>
<td><span data-ttu-id="5bf14-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-577">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-578">35</span><span class="sxs-lookup"><span data-stu-id="5bf14-578">35</span></span></td>
<td><span data-ttu-id="5bf14-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5bf14-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5bf14-580">236.25</span><span class="sxs-lookup"><span data-stu-id="5bf14-580">236.25</span></span></td>
<td><span data-ttu-id="5bf14-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-582">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-582">CC003</span></span></td>
<td><span data-ttu-id="5bf14-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-583">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-584">65</span><span class="sxs-lookup"><span data-stu-id="5bf14-584">65</span></span></td>
<td><span data-ttu-id="5bf14-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5bf14-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5bf14-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5bf14-586">5,297.69</span></span></td>
<td><span data-ttu-id="5bf14-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-588">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-588">CC004</span></span></td>
<td><span data-ttu-id="5bf14-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-589">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-590">35</span><span class="sxs-lookup"><span data-stu-id="5bf14-590">35</span></span></td>
<td><span data-ttu-id="5bf14-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5bf14-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5bf14-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5bf14-592">2,852.60</span></span></td>
<td><span data-ttu-id="5bf14-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="5bf14-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-595">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-596">Magnitude</span></span></th>
<th><span data-ttu-id="5bf14-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-597">Allocation factor</span></span></th>
<th><span data-ttu-id="5bf14-598">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-598">Amount</span></span></th>
<th><span data-ttu-id="5bf14-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-600">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-601">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-602">60</span><span class="sxs-lookup"><span data-stu-id="5bf14-602">60</span></span></td>
<td><span data-ttu-id="5bf14-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5bf14-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5bf14-604">535.31</span><span class="sxs-lookup"><span data-stu-id="5bf14-604">535.31</span></span></td>
<td><span data-ttu-id="5bf14-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-606">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-607">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-608">20</span><span class="sxs-lookup"><span data-stu-id="5bf14-608">20</span></span></td>
<td><span data-ttu-id="5bf14-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5bf14-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5bf14-610">178.44</span><span class="sxs-lookup"><span data-stu-id="5bf14-610">178.44</span></span></td>
<td><span data-ttu-id="5bf14-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-612">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-613">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-614">60</span><span class="sxs-lookup"><span data-stu-id="5bf14-614">60</span></span></td>
<td><span data-ttu-id="5bf14-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5bf14-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5bf14-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5bf14-616">4,487.12</span></span></td>
<td><span data-ttu-id="5bf14-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-618">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-619">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-620">20</span><span class="sxs-lookup"><span data-stu-id="5bf14-620">20</span></span></td>
<td><span data-ttu-id="5bf14-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5bf14-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5bf14-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5bf14-622">1,495.71</span></span></td>
<td><span data-ttu-id="5bf14-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bf14-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="5bf14-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-625">Cost object</span></span></th>
<th><span data-ttu-id="5bf14-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="5bf14-626">Magnitude</span></span></th>
<th><span data-ttu-id="5bf14-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-627">Allocation factor</span></span></th>
<th><span data-ttu-id="5bf14-628">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-628">Amount</span></span></th>
<th><span data-ttu-id="5bf14-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-630">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-631">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-632">80</span><span class="sxs-lookup"><span data-stu-id="5bf14-632">80</span></span></td>
<td><span data-ttu-id="5bf14-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5bf14-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5bf14-634">241.05</span><span class="sxs-lookup"><span data-stu-id="5bf14-634">241.05</span></span></td>
<td><span data-ttu-id="5bf14-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-636">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-637">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-638">15</span><span class="sxs-lookup"><span data-stu-id="5bf14-638">15</span></span></td>
<td><span data-ttu-id="5bf14-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5bf14-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5bf14-640">45.20</span><span class="sxs-lookup"><span data-stu-id="5bf14-640">45.20</span></span></td>
<td><span data-ttu-id="5bf14-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-642">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-643">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-644">80</span><span class="sxs-lookup"><span data-stu-id="5bf14-644">80</span></span></td>
<td><span data-ttu-id="5bf14-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5bf14-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5bf14-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5bf14-646">2,507.09</span></span></td>
<td><span data-ttu-id="5bf14-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-648">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-649">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-650">15</span><span class="sxs-lookup"><span data-stu-id="5bf14-650">15</span></span></td>
<td><span data-ttu-id="5bf14-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5bf14-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5bf14-652">470.08</span><span class="sxs-lookup"><span data-stu-id="5bf14-652">470.08</span></span></td>
<td><span data-ttu-id="5bf14-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5bf14-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="5bf14-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-655">Journal</span></span></th>
<th><span data-ttu-id="5bf14-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bf14-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bf14-658">Versione</span><span class="sxs-lookup"><span data-stu-id="5bf14-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-659">00004</span><span class="sxs-lookup"><span data-stu-id="5bf14-659">00004</span></span></td>
<td><span data-ttu-id="5bf14-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="5bf14-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="5bf14-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="5bf14-661">Fiscal</span></span></td>
<td><span data-ttu-id="5bf14-662">2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-662">2017</span></span></td>
<td><span data-ttu-id="5bf14-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-663">Period 1</span></span></td>
<td><span data-ttu-id="5bf14-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="5bf14-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bf14-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-668">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-669">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-670">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-672">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-672">CC001</span></span></td>
<td><span data-ttu-id="5bf14-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-673">HR</span></span></td>
<td><span data-ttu-id="5bf14-674">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-674">10001</span></span></td>
<td><span data-ttu-id="5bf14-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-675">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-676">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-677">500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-679">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-679">CC001</span></span></td>
<td><span data-ttu-id="5bf14-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-680">HR</span></span></td>
<td><span data-ttu-id="5bf14-681">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-681">10001</span></span></td>
<td><span data-ttu-id="5bf14-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-682">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-683">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="5bf14-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-686">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-686">CC002</span></span></td>
<td><span data-ttu-id="5bf14-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-687">Finance</span></span></td>
<td><span data-ttu-id="5bf14-688">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-688">10001</span></span></td>
<td><span data-ttu-id="5bf14-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-689">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-690">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-691">675.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-693">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-693">CC002</span></span></td>
<td><span data-ttu-id="5bf14-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-694">Finance</span></span></td>
<td><span data-ttu-id="5bf14-695">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-695">10001</span></span></td>
<td><span data-ttu-id="5bf14-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-696">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-697">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="5bf14-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-700">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-700">CC003</span></span></td>
<td><span data-ttu-id="5bf14-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-701">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-702">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-702">10001</span></span></td>
<td><span data-ttu-id="5bf14-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-703">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-704">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-705">713.75</span><span class="sxs-lookup"><span data-stu-id="5bf14-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-707">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-707">CC003</span></span></td>
<td><span data-ttu-id="5bf14-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-708">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-709">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-709">10001</span></span></td>
<td><span data-ttu-id="5bf14-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-710">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-711">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="5bf14-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-714">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-714">CC003</span></span></td>
<td><span data-ttu-id="5bf14-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-715">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-716">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-716">10001</span></span></td>
<td><span data-ttu-id="5bf14-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-717">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-718">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-719">286.25</span><span class="sxs-lookup"><span data-stu-id="5bf14-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-721">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-721">CC003</span></span></td>
<td><span data-ttu-id="5bf14-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-722">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-723">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-723">10001</span></span></td>
<td><span data-ttu-id="5bf14-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-724">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-725">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="5bf14-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-728">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-729">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-730">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-730">10001</span></span></td>
<td><span data-ttu-id="5bf14-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-731">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-732">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-733">776.36</span><span class="sxs-lookup"><span data-stu-id="5bf14-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-735">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-736">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-737">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-737">10001</span></span></td>
<td><span data-ttu-id="5bf14-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-738">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-739">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5bf14-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-742">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-743">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-744">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-744">10001</span></span></td>
<td><span data-ttu-id="5bf14-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-745">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-746">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-747">223.64</span><span class="sxs-lookup"><span data-stu-id="5bf14-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bf14-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-749">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-750">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-751">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-751">10001</span></span></td>
<td><span data-ttu-id="5bf14-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-752">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-753">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5bf14-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bf14-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bf14-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bf14-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-757">Cost element</span></span></th>
<th><span data-ttu-id="5bf14-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-758">Cost behavior</span></span></th>
<th><span data-ttu-id="5bf14-759">Importo</span><span class="sxs-lookup"><span data-stu-id="5bf14-759">Amount</span></span></th>
<th><span data-ttu-id="5bf14-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="5bf14-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bf14-761">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-761">CC001</span></span></td>
<td><span data-ttu-id="5bf14-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-762">HR</span></span></td>
<td><span data-ttu-id="5bf14-763">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-763">10001</span></span></td>
<td><span data-ttu-id="5bf14-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-764">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-765">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-766">-500.00</span></span></td>
<td><span data-ttu-id="5bf14-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-768">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-768">CC002</span></span></td>
<td><span data-ttu-id="5bf14-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-769">Finance</span></span></td>
<td><span data-ttu-id="5bf14-770">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-770">10001</span></span></td>
<td><span data-ttu-id="5bf14-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-771">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-772">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-773">175.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-773">175.00</span></span></td>
<td><span data-ttu-id="5bf14-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-775">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-775">CC003</span></span></td>
<td><span data-ttu-id="5bf14-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-776">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-777">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-777">10001</span></span></td>
<td><span data-ttu-id="5bf14-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-778">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-779">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-780">275.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-780">275.00</span></span></td>
<td><span data-ttu-id="5bf14-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-782">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-782">CC004</span></span></td>
<td><span data-ttu-id="5bf14-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-783">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-784">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-784">10001</span></span></td>
<td><span data-ttu-id="5bf14-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-785">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-786">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-787">50,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-787">50,00</span></span></td>
<td><span data-ttu-id="5bf14-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-789">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-789">CC001</span></span></td>
<td><span data-ttu-id="5bf14-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="5bf14-790">HR</span></span></td>
<td><span data-ttu-id="5bf14-791">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-791">10001</span></span></td>
<td><span data-ttu-id="5bf14-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-792">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-793">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="5bf14-794">-1,245.71</span></span></td>
<td><span data-ttu-id="5bf14-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-796">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-796">CC002</span></span></td>
<td><span data-ttu-id="5bf14-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-797">Finance</span></span></td>
<td><span data-ttu-id="5bf14-798">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-798">10001</span></span></td>
<td><span data-ttu-id="5bf14-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-799">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-800">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-801">436.00</span><span class="sxs-lookup"><span data-stu-id="5bf14-801">436.00</span></span></td>
<td><span data-ttu-id="5bf14-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-803">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-803">CC003</span></span></td>
<td><span data-ttu-id="5bf14-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-804">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-805">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-805">10001</span></span></td>
<td><span data-ttu-id="5bf14-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-806">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-807">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-808">685.14</span><span class="sxs-lookup"><span data-stu-id="5bf14-808">685.14</span></span></td>
<td><span data-ttu-id="5bf14-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-810">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-810">CC004</span></span></td>
<td><span data-ttu-id="5bf14-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-811">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-812">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-812">10001</span></span></td>
<td><span data-ttu-id="5bf14-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-813">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-814">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-815">124.57</span><span class="sxs-lookup"><span data-stu-id="5bf14-815">124.57</span></span></td>
<td><span data-ttu-id="5bf14-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-817">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-817">CC002</span></span></td>
<td><span data-ttu-id="5bf14-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-818">Finance</span></span></td>
<td><span data-ttu-id="5bf14-819">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-819">10001</span></span></td>
<td><span data-ttu-id="5bf14-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-820">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-821">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-822">-675.00</span></span></td>
<td><span data-ttu-id="5bf14-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-824">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-824">CC003</span></span></td>
<td><span data-ttu-id="5bf14-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-825">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-826">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-826">10001</span></span></td>
<td><span data-ttu-id="5bf14-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-827">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-828">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-829">438.75</span><span class="sxs-lookup"><span data-stu-id="5bf14-829">438.75</span></span></td>
<td><span data-ttu-id="5bf14-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-831">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-831">CC004</span></span></td>
<td><span data-ttu-id="5bf14-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-832">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-833">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-833">10001</span></span></td>
<td><span data-ttu-id="5bf14-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-834">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-835">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-836">236.25</span><span class="sxs-lookup"><span data-stu-id="5bf14-836">236.25</span></span></td>
<td><span data-ttu-id="5bf14-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-838">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-838">CC002</span></span></td>
<td><span data-ttu-id="5bf14-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="5bf14-839">Finance</span></span></td>
<td><span data-ttu-id="5bf14-840">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-840">10001</span></span></td>
<td><span data-ttu-id="5bf14-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-841">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-842">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="5bf14-843">-8,150.29</span></span></td>
<td><span data-ttu-id="5bf14-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-845">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-845">CC003</span></span></td>
<td><span data-ttu-id="5bf14-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-846">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-847">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-847">10001</span></span></td>
<td><span data-ttu-id="5bf14-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-848">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-849">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5bf14-850">5,297.69</span></span></td>
<td><span data-ttu-id="5bf14-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-852">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-852">CC004</span></span></td>
<td><span data-ttu-id="5bf14-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-853">Packaging</span></span></td>
<td><span data-ttu-id="5bf14-854">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-854">10001</span></span></td>
<td><span data-ttu-id="5bf14-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-855">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-856">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5bf14-857">2,852.60</span></span></td>
<td><span data-ttu-id="5bf14-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-859">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-859">CC003</span></span></td>
<td><span data-ttu-id="5bf14-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-860">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-861">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-861">10001</span></span></td>
<td><span data-ttu-id="5bf14-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-862">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-863">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="5bf14-864">-713.75</span></span></td>
<td><span data-ttu-id="5bf14-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-866">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-867">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-868">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-868">10001</span></span></td>
<td><span data-ttu-id="5bf14-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-869">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-870">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-871">535.31</span><span class="sxs-lookup"><span data-stu-id="5bf14-871">535.31</span></span></td>
<td><span data-ttu-id="5bf14-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-873">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-874">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-875">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-875">10001</span></span></td>
<td><span data-ttu-id="5bf14-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-876">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-877">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-878">178.44</span><span class="sxs-lookup"><span data-stu-id="5bf14-878">178.44</span></span></td>
<td><span data-ttu-id="5bf14-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-880">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-880">CC003</span></span></td>
<td><span data-ttu-id="5bf14-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-881">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-882">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-882">10001</span></span></td>
<td><span data-ttu-id="5bf14-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-883">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-884">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="5bf14-885">-5,982.83</span></span></td>
<td><span data-ttu-id="5bf14-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-887">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-888">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-889">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-889">10001</span></span></td>
<td><span data-ttu-id="5bf14-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-890">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-891">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5bf14-892">4,487.12</span></span></td>
<td><span data-ttu-id="5bf14-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-894">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-895">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-896">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-896">10001</span></span></td>
<td><span data-ttu-id="5bf14-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-897">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-898">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5bf14-899">1,495.71</span></span></td>
<td><span data-ttu-id="5bf14-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-901">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-901">CC003</span></span></td>
<td><span data-ttu-id="5bf14-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-902">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-903">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-903">10001</span></span></td>
<td><span data-ttu-id="5bf14-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-904">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-905">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="5bf14-906">-286.25</span></span></td>
<td><span data-ttu-id="5bf14-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-908">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-909">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-910">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-910">10001</span></span></td>
<td><span data-ttu-id="5bf14-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-911">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-912">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-913">241.05</span><span class="sxs-lookup"><span data-stu-id="5bf14-913">241.05</span></span></td>
<td><span data-ttu-id="5bf14-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-915">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-916">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-917">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-917">10001</span></span></td>
<td><span data-ttu-id="5bf14-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-918">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-919">Fixed cost</span></span></td>
<td><span data-ttu-id="5bf14-920">45.20</span><span class="sxs-lookup"><span data-stu-id="5bf14-920">45.20</span></span></td>
<td><span data-ttu-id="5bf14-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-922">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-922">CC003</span></span></td>
<td><span data-ttu-id="5bf14-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="5bf14-923">Assembly</span></span></td>
<td><span data-ttu-id="5bf14-924">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-924">10001</span></span></td>
<td><span data-ttu-id="5bf14-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-925">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-926">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="5bf14-927">-2,977.17</span></span></td>
<td><span data-ttu-id="5bf14-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-929">Prod 1</span></span></td>
<td><span data-ttu-id="5bf14-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-930">Product 1</span></span></td>
<td><span data-ttu-id="5bf14-931">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-931">10001</span></span></td>
<td><span data-ttu-id="5bf14-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-932">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-933">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5bf14-934">2,507.09</span></span></td>
<td><span data-ttu-id="5bf14-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bf14-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-936">Prod 2</span></span></td>
<td><span data-ttu-id="5bf14-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-937">Product 2</span></span></td>
<td><span data-ttu-id="5bf14-938">10001</span><span class="sxs-lookup"><span data-stu-id="5bf14-938">10001</span></span></td>
<td><span data-ttu-id="5bf14-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-939">Electricity</span></span></td>
<td><span data-ttu-id="5bf14-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-940">Variable cost</span></span></td>
<td><span data-ttu-id="5bf14-941">470.08</span><span class="sxs-lookup"><span data-stu-id="5bf14-941">470.08</span></span></td>
<td><span data-ttu-id="5bf14-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="5bf14-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="5bf14-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="5bf14-943">Conclusion</span></span>
<span data-ttu-id="5bf14-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="5bf14-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="5bf14-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="5bf14-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="5bf14-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="5bf14-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="5bf14-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="5bf14-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="5bf14-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="5bf14-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="5bf14-950">Totale</span><span class="sxs-lookup"><span data-stu-id="5bf14-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="5bf14-951">CC099</span><span class="sxs-lookup"><span data-stu-id="5bf14-951">CC099</span></span></th>
<th><span data-ttu-id="5bf14-952">CC001</span><span class="sxs-lookup"><span data-stu-id="5bf14-952">CC001</span></span></th>
<th><span data-ttu-id="5bf14-953">CC002</span><span class="sxs-lookup"><span data-stu-id="5bf14-953">CC002</span></span></th>
<th><span data-ttu-id="5bf14-954">CC003</span><span class="sxs-lookup"><span data-stu-id="5bf14-954">CC003</span></span></th>
<th><span data-ttu-id="5bf14-955">CC004</span><span class="sxs-lookup"><span data-stu-id="5bf14-955">CC004</span></span></th>
<th><span data-ttu-id="5bf14-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-956">Proj 1</span></span></th>
<th><span data-ttu-id="5bf14-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-957">Proj 2</span></span></th>
<th><span data-ttu-id="5bf14-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5bf14-958">Prod 1</span></span></th>
<th><span data-ttu-id="5bf14-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5bf14-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="5bf14-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="5bf14-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="5bf14-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="5bf14-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-971">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="5bf14-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5bf14-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-973">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-974">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-975">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-976">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-977">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-978">776.36</span><span class="sxs-lookup"><span data-stu-id="5bf14-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-979">223.64</span><span class="sxs-lookup"><span data-stu-id="5bf14-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="5bf14-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="5bf14-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-982">000</span><span class="sxs-lookup"><span data-stu-id="5bf14-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-983">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-984">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-985">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-986">0,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-987">30,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-988">10,00</span><span class="sxs-lookup"><span data-stu-id="5bf14-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5bf14-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5bf14-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bf14-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5bf14-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5bf14-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="5bf14-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5bf14-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="5bf14-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="5bf14-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="5bf14-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="5bf14-996">Per ulteriori informazioni, vedere [Criteri rollup costi e calcolo dei costi generali](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="5bf14-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



