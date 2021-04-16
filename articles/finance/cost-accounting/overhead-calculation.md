---
title: Calcolo generale
description: In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 2dddc22128621dc148a253cd568430587f294544
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822905"
---
# <a name="overhead-calculation"></a><span data-ttu-id="30560-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="30560-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30560-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="30560-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="30560-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="30560-105">Term definition</span></span>
---------------

<span data-ttu-id="30560-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="30560-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="30560-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="30560-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="30560-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="30560-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="30560-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="30560-109">Rent</span></span>
-   <span data-ttu-id="30560-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-110">Electricity</span></span>
-   <span data-ttu-id="30560-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="30560-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="30560-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="30560-112">Overhead calculation overview</span></span>
<span data-ttu-id="30560-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="30560-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="30560-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="30560-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="30560-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="30560-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="30560-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="30560-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="30560-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="30560-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="30560-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="30560-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="30560-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="30560-119">Version type</span></span>
-   <span data-ttu-id="30560-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="30560-120">Date and time</span></span>
-   <span data-ttu-id="30560-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="30560-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="30560-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-122">Fiscal year</span></span>
-   <span data-ttu-id="30560-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-123">Fiscal period</span></span>

<span data-ttu-id="30560-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="30560-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="30560-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="30560-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="30560-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="30560-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="30560-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="30560-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="30560-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="30560-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="30560-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="30560-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="30560-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="30560-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="30560-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="30560-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="30560-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="30560-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="30560-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="30560-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="30560-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="30560-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="30560-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="30560-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="30560-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="30560-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="30560-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="30560-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="30560-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="30560-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="30560-140">Main account</span></span></th>
<th><span data-ttu-id="30560-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="30560-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="30560-143">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-143">CC099</span></span></td>
<td><span data-ttu-id="30560-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-144">Default cost center</span></span></td>
<td><span data-ttu-id="30560-145">10001</span><span class="sxs-lookup"><span data-stu-id="30560-145">10001</span></span></td>
<td><span data-ttu-id="30560-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-146">Electricity</span></span></td>
<td><span data-ttu-id="30560-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="30560-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="30560-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="30560-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="30560-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="30560-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="30560-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-151">Define the cost behavior rule</span></span>

<span data-ttu-id="30560-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="30560-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="30560-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="30560-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="30560-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="30560-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="30560-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="30560-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="30560-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="30560-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="30560-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="30560-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="30560-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="30560-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-160">Journal</span></span></th>
<th><span data-ttu-id="30560-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="30560-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="30560-163">Versione</span><span class="sxs-lookup"><span data-stu-id="30560-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-164">00001</span><span class="sxs-lookup"><span data-stu-id="30560-164">00001</span></span></td>
<td><span data-ttu-id="30560-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="30560-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-166">Fiscal</span></span></td>
<td><span data-ttu-id="30560-167">2017</span><span class="sxs-lookup"><span data-stu-id="30560-167">2017</span></span></td>
<td><span data-ttu-id="30560-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-168">Period 1</span></span></td>
<td><span data-ttu-id="30560-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="30560-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="30560-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="30560-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="30560-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-173">Cost element</span></span></th>
<th><span data-ttu-id="30560-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-174">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-175">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="30560-177">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-177">CC099</span></span></td>
<td><span data-ttu-id="30560-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-178">Default cost center</span></span></td>
<td><span data-ttu-id="30560-179">10001</span><span class="sxs-lookup"><span data-stu-id="30560-179">10001</span></span></td>
<td><span data-ttu-id="30560-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-180">Electricity</span></span></td>
<td><span data-ttu-id="30560-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="30560-181">Unclassified</span></span></td>
<td><span data-ttu-id="30560-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="30560-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="30560-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="30560-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-185">Cost element</span></span></th>
<th><span data-ttu-id="30560-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-186">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-187">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-187">Amount</span></span></th>
<th><span data-ttu-id="30560-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-189">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-189">CC099</span></span></td>
<td><span data-ttu-id="30560-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-190">Default cost center</span></span></td>
<td><span data-ttu-id="30560-191">10001</span><span class="sxs-lookup"><span data-stu-id="30560-191">10001</span></span></td>
<td><span data-ttu-id="30560-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-192">Electricity</span></span></td>
<td><span data-ttu-id="30560-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="30560-193">Unclassified</span></span></td>
<td><span data-ttu-id="30560-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-194">10,000.00</span></span></td>
<td><span data-ttu-id="30560-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-196">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-196">CC099</span></span></td>
<td><span data-ttu-id="30560-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-197">Default cost center</span></span></td>
<td><span data-ttu-id="30560-198">10001</span><span class="sxs-lookup"><span data-stu-id="30560-198">10001</span></span></td>
<td><span data-ttu-id="30560-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-199">Electricity</span></span></td>
<td><span data-ttu-id="30560-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="30560-200">Unclassified</span></span></td>
<td><span data-ttu-id="30560-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-201">-10,000.00</span></span></td>
<td><span data-ttu-id="30560-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-203">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-203">CC099</span></span></td>
<td><span data-ttu-id="30560-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-204">Default cost center</span></span></td>
<td><span data-ttu-id="30560-205">10001</span><span class="sxs-lookup"><span data-stu-id="30560-205">10001</span></span></td>
<td><span data-ttu-id="30560-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-206">Electricity</span></span></td>
<td><span data-ttu-id="30560-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-207">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-208">1,000.00</span></span></td>
<td><span data-ttu-id="30560-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-210">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-210">CC099</span></span></td>
<td><span data-ttu-id="30560-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-211">Default cost center</span></span></td>
<td><span data-ttu-id="30560-212">10001</span><span class="sxs-lookup"><span data-stu-id="30560-212">10001</span></span></td>
<td><span data-ttu-id="30560-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-213">Electricity</span></span></td>
<td><span data-ttu-id="30560-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-214">Variable cost</span></span></td>
<td><span data-ttu-id="30560-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-215">9,000.00</span></span></td>
<td><span data-ttu-id="30560-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="30560-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="30560-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="30560-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="30560-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="30560-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="30560-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="30560-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="30560-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="30560-221">Define the cost distribution rule</span></span>

<span data-ttu-id="30560-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="30560-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="30560-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="30560-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="30560-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="30560-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="30560-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="30560-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="30560-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="30560-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="30560-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="30560-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-228">Cost object</span></span></th>
<th><span data-ttu-id="30560-229">KWH</span><span class="sxs-lookup"><span data-stu-id="30560-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-230">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-230">CC001</span></span></td>
<td><span data-ttu-id="30560-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-231">HR</span></span></td>
<td><span data-ttu-id="30560-232">1.000</span><span class="sxs-lookup"><span data-stu-id="30560-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-233">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-233">CC002</span></span></td>
<td><span data-ttu-id="30560-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-234">Finance</span></span></td>
<td><span data-ttu-id="30560-235">6.000</span><span class="sxs-lookup"><span data-stu-id="30560-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-236">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-236">CC003</span></span></td>
<td><span data-ttu-id="30560-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-237">Assembly</span></span></td>
<td><span data-ttu-id="30560-238">0</span><span class="sxs-lookup"><span data-stu-id="30560-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="30560-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-240">Cost object</span></span></th>
<th><span data-ttu-id="30560-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-241">Magnitude</span></span></th>
<th><span data-ttu-id="30560-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="30560-242">Allocation factor</span></span></th>
<th><span data-ttu-id="30560-243">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-244">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-244">CC001</span></span></td>
<td><span data-ttu-id="30560-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-245">HR</span></span></td>
<td><span data-ttu-id="30560-246">1.000</span><span class="sxs-lookup"><span data-stu-id="30560-246">1,000</span></span></td>
<td><span data-ttu-id="30560-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="30560-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="30560-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-249">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-249">CC002</span></span></td>
<td><span data-ttu-id="30560-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-250">Finance</span></span></td>
<td><span data-ttu-id="30560-251">6.000</span><span class="sxs-lookup"><span data-stu-id="30560-251">6,000</span></span></td>
<td><span data-ttu-id="30560-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="30560-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="30560-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-254">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-254">CC003</span></span></td>
<td><span data-ttu-id="30560-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-255">Assembly</span></span></td>
<td><span data-ttu-id="30560-256">0</span><span class="sxs-lookup"><span data-stu-id="30560-256">0</span></span></td>
<td><span data-ttu-id="30560-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="30560-258">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="30560-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="30560-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="30560-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-261">Cost object</span></span></th>
<th><span data-ttu-id="30560-262">Formula</span><span class="sxs-lookup"><span data-stu-id="30560-262">Formula</span></span></th>
<th><span data-ttu-id="30560-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-263">Magnitude</span></span></th>
<th><span data-ttu-id="30560-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="30560-264">Allocation factor</span></span></th>
<th><span data-ttu-id="30560-265">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-266">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-266">CC001</span></span></td>
<td><span data-ttu-id="30560-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-267">HR</span></span></td>
<td><span data-ttu-id="30560-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="30560-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="30560-269">1</span><span class="sxs-lookup"><span data-stu-id="30560-269">1</span></span></td>
<td><span data-ttu-id="30560-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="30560-271">500,00</span><span class="sxs-lookup"><span data-stu-id="30560-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-272">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-272">CC002</span></span></td>
<td><span data-ttu-id="30560-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-273">Finance</span></span></td>
<td><span data-ttu-id="30560-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="30560-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="30560-275">1</span><span class="sxs-lookup"><span data-stu-id="30560-275">1</span></span></td>
<td><span data-ttu-id="30560-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="30560-277">500,00</span><span class="sxs-lookup"><span data-stu-id="30560-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-278">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-278">CC003</span></span></td>
<td><span data-ttu-id="30560-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-279">Assembly</span></span></td>
<td><span data-ttu-id="30560-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="30560-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="30560-281">0</span><span class="sxs-lookup"><span data-stu-id="30560-281">0</span></span></td>
<td><span data-ttu-id="30560-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="30560-283">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="30560-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-285">Journal</span></span></th>
<th><span data-ttu-id="30560-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="30560-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="30560-288">Versione</span><span class="sxs-lookup"><span data-stu-id="30560-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-289">00002</span><span class="sxs-lookup"><span data-stu-id="30560-289">00002</span></span></td>
<td><span data-ttu-id="30560-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="30560-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="30560-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-291">Fiscal</span></span></td>
<td><span data-ttu-id="30560-292">2017</span><span class="sxs-lookup"><span data-stu-id="30560-292">2017</span></span></td>
<td><span data-ttu-id="30560-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-293">Period 1</span></span></td>
<td><span data-ttu-id="30560-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="30560-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="30560-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="30560-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="30560-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-298">Cost element</span></span></th>
<th><span data-ttu-id="30560-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-299">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-300">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-302">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-302">CC099</span></span></td>
<td><span data-ttu-id="30560-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-303">Default cost center</span></span></td>
<td><span data-ttu-id="30560-304">10001</span><span class="sxs-lookup"><span data-stu-id="30560-304">10001</span></span></td>
<td><span data-ttu-id="30560-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-305">Electricity</span></span></td>
<td><span data-ttu-id="30560-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-306">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-309">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-309">CC099</span></span></td>
<td><span data-ttu-id="30560-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-310">Default cost center</span></span></td>
<td><span data-ttu-id="30560-311">10001</span><span class="sxs-lookup"><span data-stu-id="30560-311">10001</span></span></td>
<td><span data-ttu-id="30560-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-312">Electricity</span></span></td>
<td><span data-ttu-id="30560-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-313">Variable cost</span></span></td>
<td><span data-ttu-id="30560-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="30560-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="30560-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="30560-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-317">Cost element</span></span></th>
<th><span data-ttu-id="30560-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-318">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-319">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-319">Amount</span></span></th>
<th><span data-ttu-id="30560-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-321">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-321">CC099</span></span></td>
<td><span data-ttu-id="30560-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-322">Default cost center</span></span></td>
<td><span data-ttu-id="30560-323">10001</span><span class="sxs-lookup"><span data-stu-id="30560-323">10001</span></span></td>
<td><span data-ttu-id="30560-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-324">Electricity</span></span></td>
<td><span data-ttu-id="30560-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-325">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-326">-1,000.00</span></span></td>
<td><span data-ttu-id="30560-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-328">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-328">CC001</span></span></td>
<td><span data-ttu-id="30560-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-329">HR</span></span></td>
<td><span data-ttu-id="30560-330">10001</span><span class="sxs-lookup"><span data-stu-id="30560-330">10001</span></span></td>
<td><span data-ttu-id="30560-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-331">Electricity</span></span></td>
<td><span data-ttu-id="30560-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-332">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-333">500,00</span><span class="sxs-lookup"><span data-stu-id="30560-333">500.00</span></span></td>
<td><span data-ttu-id="30560-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-335">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-335">CC002</span></span></td>
<td><span data-ttu-id="30560-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-336">Finance</span></span></td>
<td><span data-ttu-id="30560-337">10001</span><span class="sxs-lookup"><span data-stu-id="30560-337">10001</span></span></td>
<td><span data-ttu-id="30560-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-338">Electricity</span></span></td>
<td><span data-ttu-id="30560-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-339">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-340">500,00</span><span class="sxs-lookup"><span data-stu-id="30560-340">500.00</span></span></td>
<td><span data-ttu-id="30560-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-342">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-342">CC099</span></span></td>
<td><span data-ttu-id="30560-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="30560-343">Default cost center</span></span></td>
<td><span data-ttu-id="30560-344">10001</span><span class="sxs-lookup"><span data-stu-id="30560-344">10001</span></span></td>
<td><span data-ttu-id="30560-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-345">Electricity</span></span></td>
<td><span data-ttu-id="30560-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-346">Variable cost</span></span></td>
<td><span data-ttu-id="30560-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="30560-347">-9,000.00</span></span></td>
<td><span data-ttu-id="30560-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-349">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-349">CC001</span></span></td>
<td><span data-ttu-id="30560-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-350">HR</span></span></td>
<td><span data-ttu-id="30560-351">10001</span><span class="sxs-lookup"><span data-stu-id="30560-351">10001</span></span></td>
<td><span data-ttu-id="30560-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-352">Electricity</span></span></td>
<td><span data-ttu-id="30560-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-353">Variable cost</span></span></td>
<td><span data-ttu-id="30560-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="30560-354">1,285.71</span></span></td>
<td><span data-ttu-id="30560-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-356">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-356">CC002</span></span></td>
<td><span data-ttu-id="30560-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-357">Finance</span></span></td>
<td><span data-ttu-id="30560-358">10001</span><span class="sxs-lookup"><span data-stu-id="30560-358">10001</span></span></td>
<td><span data-ttu-id="30560-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-359">Electricity</span></span></td>
<td><span data-ttu-id="30560-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-360">Variable cost</span></span></td>
<td><span data-ttu-id="30560-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="30560-361">7,714.29</span></span></td>
<td><span data-ttu-id="30560-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="30560-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="30560-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="30560-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="30560-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="30560-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="30560-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="30560-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="30560-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="30560-367">Define the overhead rate</span></span>

<span data-ttu-id="30560-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="30560-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="30560-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="30560-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-370">Cost object</span></span></th>
<th><span data-ttu-id="30560-371">Ore</span><span class="sxs-lookup"><span data-stu-id="30560-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="30560-372">Proj 1</span></span></td>
<td><span data-ttu-id="30560-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="30560-373">Project 1</span></span></td>
<td><span data-ttu-id="30560-374">3</span><span class="sxs-lookup"><span data-stu-id="30560-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="30560-375">Proj 2</span></span></td>
<td><span data-ttu-id="30560-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="30560-376">Project 2</span></span></td>
<td><span data-ttu-id="30560-377">1</span><span class="sxs-lookup"><span data-stu-id="30560-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="30560-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-379">Cost object</span></span></th>
<th><span data-ttu-id="30560-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-380">Cost element</span></span></th>
<th><span data-ttu-id="30560-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-381">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-382">Unità</span><span class="sxs-lookup"><span data-stu-id="30560-382">Units</span></span></th>
<th><span data-ttu-id="30560-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="30560-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-384">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-384">CC001</span></span></td>
<td><span data-ttu-id="30560-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-385">HR</span></span></td>
<td><span data-ttu-id="30560-386">10001</span><span class="sxs-lookup"><span data-stu-id="30560-386">10001</span></span></td>
<td><span data-ttu-id="30560-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-387">Variable cost</span></span></td>
<td><span data-ttu-id="30560-388">1</span><span class="sxs-lookup"><span data-stu-id="30560-388">1</span></span></td>
<td><span data-ttu-id="30560-389">10</span><span class="sxs-lookup"><span data-stu-id="30560-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="30560-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-391">Cost object</span></span></th>
<th><span data-ttu-id="30560-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-392">Magnitude</span></span></th>
<th><span data-ttu-id="30560-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-393">Cost element</span></span></th>
<th><span data-ttu-id="30560-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="30560-394">Allocation factor</span></span></th>
<th><span data-ttu-id="30560-395">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="30560-396">Proj 1</span></span></td>
<td><span data-ttu-id="30560-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="30560-397">Project 1</span></span></td>
<td><span data-ttu-id="30560-398">3</span><span class="sxs-lookup"><span data-stu-id="30560-398">3</span></span></td>
<td><span data-ttu-id="30560-399">10001</span><span class="sxs-lookup"><span data-stu-id="30560-399">10001</span></span></td>
<td><span data-ttu-id="30560-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="30560-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="30560-401">30,00</span><span class="sxs-lookup"><span data-stu-id="30560-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="30560-402">Proj 2</span></span></td>
<td><span data-ttu-id="30560-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="30560-403">Project 2</span></span></td>
<td><span data-ttu-id="30560-404">1</span><span class="sxs-lookup"><span data-stu-id="30560-404">1</span></span></td>
<td><span data-ttu-id="30560-405">10001</span><span class="sxs-lookup"><span data-stu-id="30560-405">10001</span></span></td>
<td><span data-ttu-id="30560-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="30560-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="30560-407">10,00</span><span class="sxs-lookup"><span data-stu-id="30560-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="30560-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-409">Journal</span></span></th>
<th><span data-ttu-id="30560-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="30560-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="30560-412">Versione</span><span class="sxs-lookup"><span data-stu-id="30560-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-413">00003</span><span class="sxs-lookup"><span data-stu-id="30560-413">00003</span></span></td>
<td><span data-ttu-id="30560-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="30560-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="30560-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-415">Fiscal</span></span></td>
<td><span data-ttu-id="30560-416">2017</span><span class="sxs-lookup"><span data-stu-id="30560-416">2017</span></span></td>
<td><span data-ttu-id="30560-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-417">Period 1</span></span></td>
<td><span data-ttu-id="30560-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="30560-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="30560-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="30560-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-421">Cost object</span></span></th>
<th><span data-ttu-id="30560-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="30560-424">Proj 1</span></span></td>
<td><span data-ttu-id="30560-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="30560-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="30560-426">3,00</span><span class="sxs-lookup"><span data-stu-id="30560-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="30560-428">Proj 2</span></span></td>
<td><span data-ttu-id="30560-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="30560-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="30560-430">1,00</span><span class="sxs-lookup"><span data-stu-id="30560-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="30560-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="30560-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="30560-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-433">Cost element</span></span></th>
<th><span data-ttu-id="30560-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-434">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-435">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-435">Amount</span></span></th>
<th><span data-ttu-id="30560-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="30560-437">CC0001</span></span></td>
<td><span data-ttu-id="30560-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-438">HR</span></span></td>
<td><span data-ttu-id="30560-439">10001</span><span class="sxs-lookup"><span data-stu-id="30560-439">10001</span></span></td>
<td><span data-ttu-id="30560-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-440">Electricity</span></span></td>
<td><span data-ttu-id="30560-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-441">Variable cost</span></span></td>
<td><span data-ttu-id="30560-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="30560-442">-30.00</span></span></td>
<td><span data-ttu-id="30560-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="30560-444">Proj 1</span></span></td>
<td><span data-ttu-id="30560-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="30560-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="30560-446">10001</span><span class="sxs-lookup"><span data-stu-id="30560-446">10001</span></span></td>
<td><span data-ttu-id="30560-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-447">Electricity</span></span></td>
<td><span data-ttu-id="30560-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-448">Variable cost</span></span></td>
<td><span data-ttu-id="30560-449">30,00</span><span class="sxs-lookup"><span data-stu-id="30560-449">30.00</span></span></td>
<td><span data-ttu-id="30560-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-451">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-451">CC001</span></span></td>
<td><span data-ttu-id="30560-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-452">HR</span></span></td>
<td><span data-ttu-id="30560-453">10001</span><span class="sxs-lookup"><span data-stu-id="30560-453">10001</span></span></td>
<td><span data-ttu-id="30560-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-454">Electricity</span></span></td>
<td><span data-ttu-id="30560-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-455">Variable cost</span></span></td>
<td><span data-ttu-id="30560-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="30560-456">-10.00</span></span></td>
<td><span data-ttu-id="30560-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="30560-458">Proj 2</span></span></td>
<td><span data-ttu-id="30560-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="30560-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="30560-460">10001</span><span class="sxs-lookup"><span data-stu-id="30560-460">10001</span></span></td>
<td><span data-ttu-id="30560-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-461">Electricity</span></span></td>
<td><span data-ttu-id="30560-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-462">Variable cost</span></span></td>
<td><span data-ttu-id="30560-463">10.00</span><span class="sxs-lookup"><span data-stu-id="30560-463">10.00</span></span></td>
<td><span data-ttu-id="30560-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="30560-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="30560-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="30560-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="30560-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="30560-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="30560-468">Finance supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="30560-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="30560-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="30560-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="30560-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="30560-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="30560-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="30560-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="30560-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="30560-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="30560-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="30560-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="30560-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="30560-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="30560-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="30560-475">Define the cost allocation</span></span>

<span data-ttu-id="30560-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="30560-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="30560-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="30560-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="30560-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="30560-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-479">Cost object</span></span></th>
<th><span data-ttu-id="30560-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="30560-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-481">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-481">CC002</span></span></td>
<td><span data-ttu-id="30560-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-482">Finance</span></span></td>
<td><span data-ttu-id="30560-483">35</span><span class="sxs-lookup"><span data-stu-id="30560-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-484">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-484">CC003</span></span></td>
<td><span data-ttu-id="30560-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-485">Assembly</span></span></td>
<td><span data-ttu-id="30560-486">55</span><span class="sxs-lookup"><span data-stu-id="30560-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-487">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-487">CC004</span></span></td>
<td><span data-ttu-id="30560-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-488">Packaging</span></span></td>
<td><span data-ttu-id="30560-489">10</span><span class="sxs-lookup"><span data-stu-id="30560-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="30560-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="30560-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="30560-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-492">Cost object</span></span></th>
<th><span data-ttu-id="30560-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-494">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-494">CC003</span></span></td>
<td><span data-ttu-id="30560-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-495">Assembly</span></span></td>
<td><span data-ttu-id="30560-496">65</span><span class="sxs-lookup"><span data-stu-id="30560-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-497">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-497">CC004</span></span></td>
<td><span data-ttu-id="30560-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-498">Packaging</span></span></td>
<td><span data-ttu-id="30560-499">35</span><span class="sxs-lookup"><span data-stu-id="30560-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="30560-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="30560-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="30560-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-502">Cost object</span></span></th>
<th><span data-ttu-id="30560-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="30560-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-504">Prod 1</span></span></td>
<td><span data-ttu-id="30560-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-505">Product 1</span></span></td>
<td><span data-ttu-id="30560-506">60</span><span class="sxs-lookup"><span data-stu-id="30560-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-507">Prod 2</span></span></td>
<td><span data-ttu-id="30560-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-508">Product 2</span></span></td>
<td><span data-ttu-id="30560-509">20</span><span class="sxs-lookup"><span data-stu-id="30560-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="30560-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="30560-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="30560-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-512">Cost object</span></span></th>
<th><span data-ttu-id="30560-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="30560-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-514">Prod 1</span></span></td>
<td><span data-ttu-id="30560-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-515">Product 1</span></span></td>
<td><span data-ttu-id="30560-516">80</span><span class="sxs-lookup"><span data-stu-id="30560-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-517">Prod 2</span></span></td>
<td><span data-ttu-id="30560-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-518">Product 2</span></span></td>
<td><span data-ttu-id="30560-519">15</span><span class="sxs-lookup"><span data-stu-id="30560-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="30560-520">Le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="30560-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="30560-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="30560-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="30560-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="30560-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-523">Cost object</span></span></th>
<th><span data-ttu-id="30560-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-524">Magnitude</span></span></th>
<th><span data-ttu-id="30560-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="30560-525">Allocation factor</span></span></th>
<th><span data-ttu-id="30560-526">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-526">Amount</span></span></th>
<th><span data-ttu-id="30560-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-528">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-528">CC002</span></span></td>
<td><span data-ttu-id="30560-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-529">Finance</span></span></td>
<td><span data-ttu-id="30560-530">35</span><span class="sxs-lookup"><span data-stu-id="30560-530">35</span></span></td>
<td><span data-ttu-id="30560-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="30560-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="30560-532">175.00</span><span class="sxs-lookup"><span data-stu-id="30560-532">175.00</span></span></td>
<td><span data-ttu-id="30560-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-534">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-534">CC003</span></span></td>
<td><span data-ttu-id="30560-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-535">Assembly</span></span></td>
<td><span data-ttu-id="30560-536">55</span><span class="sxs-lookup"><span data-stu-id="30560-536">55</span></span></td>
<td><span data-ttu-id="30560-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="30560-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="30560-538">275.00</span><span class="sxs-lookup"><span data-stu-id="30560-538">275.00</span></span></td>
<td><span data-ttu-id="30560-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-540">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-540">CC004</span></span></td>
<td><span data-ttu-id="30560-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-541">Packaging</span></span></td>
<td><span data-ttu-id="30560-542">10</span><span class="sxs-lookup"><span data-stu-id="30560-542">10</span></span></td>
<td><span data-ttu-id="30560-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="30560-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="30560-544">50,00</span><span class="sxs-lookup"><span data-stu-id="30560-544">50.00</span></span></td>
<td><span data-ttu-id="30560-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-546">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-546">CC002</span></span></td>
<td><span data-ttu-id="30560-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-547">Finance</span></span></td>
<td><span data-ttu-id="30560-548">35</span><span class="sxs-lookup"><span data-stu-id="30560-548">35</span></span></td>
<td><span data-ttu-id="30560-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="30560-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="30560-550">436.00</span><span class="sxs-lookup"><span data-stu-id="30560-550">436.00</span></span></td>
<td><span data-ttu-id="30560-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-552">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-552">CC003</span></span></td>
<td><span data-ttu-id="30560-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-553">Assembly</span></span></td>
<td><span data-ttu-id="30560-554">55</span><span class="sxs-lookup"><span data-stu-id="30560-554">55</span></span></td>
<td><span data-ttu-id="30560-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="30560-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="30560-556">685.14</span><span class="sxs-lookup"><span data-stu-id="30560-556">685.14</span></span></td>
<td><span data-ttu-id="30560-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-558">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-558">CC004</span></span></td>
<td><span data-ttu-id="30560-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-559">Packaging</span></span></td>
<td><span data-ttu-id="30560-560">10</span><span class="sxs-lookup"><span data-stu-id="30560-560">10</span></span></td>
<td><span data-ttu-id="30560-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="30560-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="30560-562">124.57</span><span class="sxs-lookup"><span data-stu-id="30560-562">124.57</span></span></td>
<td><span data-ttu-id="30560-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="30560-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-565">Cost object</span></span></th>
<th><span data-ttu-id="30560-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-566">Magnitude</span></span></th>
<th><span data-ttu-id="30560-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="30560-567">Allocation factor</span></span></th>
<th><span data-ttu-id="30560-568">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-568">Amount</span></span></th>
<th><span data-ttu-id="30560-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-570">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-570">CC003</span></span></td>
<td><span data-ttu-id="30560-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-571">Assembly</span></span></td>
<td><span data-ttu-id="30560-572">65</span><span class="sxs-lookup"><span data-stu-id="30560-572">65</span></span></td>
<td><span data-ttu-id="30560-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="30560-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="30560-574">438.75</span><span class="sxs-lookup"><span data-stu-id="30560-574">438.75</span></span></td>
<td><span data-ttu-id="30560-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-576">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-576">CC004</span></span></td>
<td><span data-ttu-id="30560-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-577">Packaging</span></span></td>
<td><span data-ttu-id="30560-578">35</span><span class="sxs-lookup"><span data-stu-id="30560-578">35</span></span></td>
<td><span data-ttu-id="30560-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="30560-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="30560-580">236.25</span><span class="sxs-lookup"><span data-stu-id="30560-580">236.25</span></span></td>
<td><span data-ttu-id="30560-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-582">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-582">CC003</span></span></td>
<td><span data-ttu-id="30560-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-583">Assembly</span></span></td>
<td><span data-ttu-id="30560-584">65</span><span class="sxs-lookup"><span data-stu-id="30560-584">65</span></span></td>
<td><span data-ttu-id="30560-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="30560-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="30560-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="30560-586">5,297.69</span></span></td>
<td><span data-ttu-id="30560-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-588">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-588">CC004</span></span></td>
<td><span data-ttu-id="30560-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-589">Packaging</span></span></td>
<td><span data-ttu-id="30560-590">35</span><span class="sxs-lookup"><span data-stu-id="30560-590">35</span></span></td>
<td><span data-ttu-id="30560-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="30560-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="30560-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="30560-592">2,852.60</span></span></td>
<td><span data-ttu-id="30560-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="30560-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-595">Cost object</span></span></th>
<th><span data-ttu-id="30560-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-596">Magnitude</span></span></th>
<th><span data-ttu-id="30560-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="30560-597">Allocation factor</span></span></th>
<th><span data-ttu-id="30560-598">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-598">Amount</span></span></th>
<th><span data-ttu-id="30560-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-600">Prod 1</span></span></td>
<td><span data-ttu-id="30560-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-601">Product 1</span></span></td>
<td><span data-ttu-id="30560-602">60</span><span class="sxs-lookup"><span data-stu-id="30560-602">60</span></span></td>
<td><span data-ttu-id="30560-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="30560-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="30560-604">535.31</span><span class="sxs-lookup"><span data-stu-id="30560-604">535.31</span></span></td>
<td><span data-ttu-id="30560-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-606">Prod 2</span></span></td>
<td><span data-ttu-id="30560-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-607">Product 2</span></span></td>
<td><span data-ttu-id="30560-608">20</span><span class="sxs-lookup"><span data-stu-id="30560-608">20</span></span></td>
<td><span data-ttu-id="30560-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="30560-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="30560-610">178.44</span><span class="sxs-lookup"><span data-stu-id="30560-610">178.44</span></span></td>
<td><span data-ttu-id="30560-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-612">Prod 1</span></span></td>
<td><span data-ttu-id="30560-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-613">Product 1</span></span></td>
<td><span data-ttu-id="30560-614">60</span><span class="sxs-lookup"><span data-stu-id="30560-614">60</span></span></td>
<td><span data-ttu-id="30560-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="30560-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="30560-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="30560-616">4,487.12</span></span></td>
<td><span data-ttu-id="30560-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-618">Prod 2</span></span></td>
<td><span data-ttu-id="30560-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-619">Product 2</span></span></td>
<td><span data-ttu-id="30560-620">20</span><span class="sxs-lookup"><span data-stu-id="30560-620">20</span></span></td>
<td><span data-ttu-id="30560-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="30560-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="30560-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="30560-622">1,495.71</span></span></td>
<td><span data-ttu-id="30560-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="30560-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="30560-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-625">Cost object</span></span></th>
<th><span data-ttu-id="30560-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="30560-626">Magnitude</span></span></th>
<th><span data-ttu-id="30560-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="30560-627">Allocation factor</span></span></th>
<th><span data-ttu-id="30560-628">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-628">Amount</span></span></th>
<th><span data-ttu-id="30560-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-630">Prod 1</span></span></td>
<td><span data-ttu-id="30560-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-631">Product 1</span></span></td>
<td><span data-ttu-id="30560-632">80</span><span class="sxs-lookup"><span data-stu-id="30560-632">80</span></span></td>
<td><span data-ttu-id="30560-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="30560-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="30560-634">241.05</span><span class="sxs-lookup"><span data-stu-id="30560-634">241.05</span></span></td>
<td><span data-ttu-id="30560-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-636">Prod 2</span></span></td>
<td><span data-ttu-id="30560-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-637">Product 2</span></span></td>
<td><span data-ttu-id="30560-638">15</span><span class="sxs-lookup"><span data-stu-id="30560-638">15</span></span></td>
<td><span data-ttu-id="30560-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="30560-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="30560-640">45.20</span><span class="sxs-lookup"><span data-stu-id="30560-640">45.20</span></span></td>
<td><span data-ttu-id="30560-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-642">Prod 1</span></span></td>
<td><span data-ttu-id="30560-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-643">Product 1</span></span></td>
<td><span data-ttu-id="30560-644">80</span><span class="sxs-lookup"><span data-stu-id="30560-644">80</span></span></td>
<td><span data-ttu-id="30560-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="30560-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="30560-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="30560-646">2,507.09</span></span></td>
<td><span data-ttu-id="30560-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-648">Prod 2</span></span></td>
<td><span data-ttu-id="30560-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-649">Product 2</span></span></td>
<td><span data-ttu-id="30560-650">15</span><span class="sxs-lookup"><span data-stu-id="30560-650">15</span></span></td>
<td><span data-ttu-id="30560-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="30560-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="30560-652">470.08</span><span class="sxs-lookup"><span data-stu-id="30560-652">470.08</span></span></td>
<td><span data-ttu-id="30560-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="30560-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="30560-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-655">Journal</span></span></th>
<th><span data-ttu-id="30560-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="30560-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="30560-658">Versione</span><span class="sxs-lookup"><span data-stu-id="30560-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-659">00004</span><span class="sxs-lookup"><span data-stu-id="30560-659">00004</span></span></td>
<td><span data-ttu-id="30560-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="30560-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="30560-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="30560-661">Fiscal</span></span></td>
<td><span data-ttu-id="30560-662">2017</span><span class="sxs-lookup"><span data-stu-id="30560-662">2017</span></span></td>
<td><span data-ttu-id="30560-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-663">Period 1</span></span></td>
<td><span data-ttu-id="30560-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="30560-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="30560-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="30560-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="30560-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="30560-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-668">Cost element</span></span></th>
<th><span data-ttu-id="30560-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-669">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-670">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-672">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-672">CC001</span></span></td>
<td><span data-ttu-id="30560-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-673">HR</span></span></td>
<td><span data-ttu-id="30560-674">10001</span><span class="sxs-lookup"><span data-stu-id="30560-674">10001</span></span></td>
<td><span data-ttu-id="30560-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-675">Electricity</span></span></td>
<td><span data-ttu-id="30560-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-676">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-677">500,00</span><span class="sxs-lookup"><span data-stu-id="30560-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-679">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-679">CC001</span></span></td>
<td><span data-ttu-id="30560-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-680">HR</span></span></td>
<td><span data-ttu-id="30560-681">10001</span><span class="sxs-lookup"><span data-stu-id="30560-681">10001</span></span></td>
<td><span data-ttu-id="30560-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-682">Electricity</span></span></td>
<td><span data-ttu-id="30560-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-683">Variable cost</span></span></td>
<td><span data-ttu-id="30560-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="30560-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-686">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-686">CC002</span></span></td>
<td><span data-ttu-id="30560-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-687">Finance</span></span></td>
<td><span data-ttu-id="30560-688">10001</span><span class="sxs-lookup"><span data-stu-id="30560-688">10001</span></span></td>
<td><span data-ttu-id="30560-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-689">Electricity</span></span></td>
<td><span data-ttu-id="30560-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-690">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-691">675.00</span><span class="sxs-lookup"><span data-stu-id="30560-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-693">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-693">CC002</span></span></td>
<td><span data-ttu-id="30560-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-694">Finance</span></span></td>
<td><span data-ttu-id="30560-695">10001</span><span class="sxs-lookup"><span data-stu-id="30560-695">10001</span></span></td>
<td><span data-ttu-id="30560-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-696">Electricity</span></span></td>
<td><span data-ttu-id="30560-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-697">Variable cost</span></span></td>
<td><span data-ttu-id="30560-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="30560-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-700">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-700">CC003</span></span></td>
<td><span data-ttu-id="30560-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-701">Assembly</span></span></td>
<td><span data-ttu-id="30560-702">10001</span><span class="sxs-lookup"><span data-stu-id="30560-702">10001</span></span></td>
<td><span data-ttu-id="30560-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-703">Electricity</span></span></td>
<td><span data-ttu-id="30560-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-704">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-705">713.75</span><span class="sxs-lookup"><span data-stu-id="30560-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-707">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-707">CC003</span></span></td>
<td><span data-ttu-id="30560-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-708">Assembly</span></span></td>
<td><span data-ttu-id="30560-709">10001</span><span class="sxs-lookup"><span data-stu-id="30560-709">10001</span></span></td>
<td><span data-ttu-id="30560-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-710">Electricity</span></span></td>
<td><span data-ttu-id="30560-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-711">Variable cost</span></span></td>
<td><span data-ttu-id="30560-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="30560-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-714">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-714">CC003</span></span></td>
<td><span data-ttu-id="30560-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-715">Packaging</span></span></td>
<td><span data-ttu-id="30560-716">10001</span><span class="sxs-lookup"><span data-stu-id="30560-716">10001</span></span></td>
<td><span data-ttu-id="30560-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-717">Electricity</span></span></td>
<td><span data-ttu-id="30560-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-718">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-719">286.25</span><span class="sxs-lookup"><span data-stu-id="30560-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-721">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-721">CC003</span></span></td>
<td><span data-ttu-id="30560-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-722">Packaging</span></span></td>
<td><span data-ttu-id="30560-723">10001</span><span class="sxs-lookup"><span data-stu-id="30560-723">10001</span></span></td>
<td><span data-ttu-id="30560-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-724">Electricity</span></span></td>
<td><span data-ttu-id="30560-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-725">Variable cost</span></span></td>
<td><span data-ttu-id="30560-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="30560-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-728">Prod 1</span></span></td>
<td><span data-ttu-id="30560-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-729">Product 1</span></span></td>
<td><span data-ttu-id="30560-730">10001</span><span class="sxs-lookup"><span data-stu-id="30560-730">10001</span></span></td>
<td><span data-ttu-id="30560-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-731">Electricity</span></span></td>
<td><span data-ttu-id="30560-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-732">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-733">776.36</span><span class="sxs-lookup"><span data-stu-id="30560-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-735">Prod 1</span></span></td>
<td><span data-ttu-id="30560-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-736">Product 1</span></span></td>
<td><span data-ttu-id="30560-737">10001</span><span class="sxs-lookup"><span data-stu-id="30560-737">10001</span></span></td>
<td><span data-ttu-id="30560-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-738">Electricity</span></span></td>
<td><span data-ttu-id="30560-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-739">Variable cost</span></span></td>
<td><span data-ttu-id="30560-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="30560-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-742">Prod 2</span></span></td>
<td><span data-ttu-id="30560-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-743">Product 1</span></span></td>
<td><span data-ttu-id="30560-744">10001</span><span class="sxs-lookup"><span data-stu-id="30560-744">10001</span></span></td>
<td><span data-ttu-id="30560-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-745">Electricity</span></span></td>
<td><span data-ttu-id="30560-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-746">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-747">223.64</span><span class="sxs-lookup"><span data-stu-id="30560-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="30560-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-749">Prod 2</span></span></td>
<td><span data-ttu-id="30560-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-750">Product 1</span></span></td>
<td><span data-ttu-id="30560-751">10001</span><span class="sxs-lookup"><span data-stu-id="30560-751">10001</span></span></td>
<td><span data-ttu-id="30560-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-752">Electricity</span></span></td>
<td><span data-ttu-id="30560-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-753">Variable cost</span></span></td>
<td><span data-ttu-id="30560-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="30560-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="30560-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="30560-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="30560-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="30560-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-757">Cost element</span></span></th>
<th><span data-ttu-id="30560-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="30560-758">Cost behavior</span></span></th>
<th><span data-ttu-id="30560-759">Importo</span><span class="sxs-lookup"><span data-stu-id="30560-759">Amount</span></span></th>
<th><span data-ttu-id="30560-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="30560-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="30560-761">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-761">CC001</span></span></td>
<td><span data-ttu-id="30560-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-762">HR</span></span></td>
<td><span data-ttu-id="30560-763">10001</span><span class="sxs-lookup"><span data-stu-id="30560-763">10001</span></span></td>
<td><span data-ttu-id="30560-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-764">Electricity</span></span></td>
<td><span data-ttu-id="30560-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-765">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="30560-766">-500.00</span></span></td>
<td><span data-ttu-id="30560-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-768">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-768">CC002</span></span></td>
<td><span data-ttu-id="30560-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-769">Finance</span></span></td>
<td><span data-ttu-id="30560-770">10001</span><span class="sxs-lookup"><span data-stu-id="30560-770">10001</span></span></td>
<td><span data-ttu-id="30560-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-771">Electricity</span></span></td>
<td><span data-ttu-id="30560-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-772">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-773">175.00</span><span class="sxs-lookup"><span data-stu-id="30560-773">175.00</span></span></td>
<td><span data-ttu-id="30560-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-775">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-775">CC003</span></span></td>
<td><span data-ttu-id="30560-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-776">Assembly</span></span></td>
<td><span data-ttu-id="30560-777">10001</span><span class="sxs-lookup"><span data-stu-id="30560-777">10001</span></span></td>
<td><span data-ttu-id="30560-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-778">Electricity</span></span></td>
<td><span data-ttu-id="30560-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-779">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-780">275.00</span><span class="sxs-lookup"><span data-stu-id="30560-780">275.00</span></span></td>
<td><span data-ttu-id="30560-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-782">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-782">CC004</span></span></td>
<td><span data-ttu-id="30560-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-783">Packaging</span></span></td>
<td><span data-ttu-id="30560-784">10001</span><span class="sxs-lookup"><span data-stu-id="30560-784">10001</span></span></td>
<td><span data-ttu-id="30560-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-785">Electricity</span></span></td>
<td><span data-ttu-id="30560-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-786">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-787">50,00</span><span class="sxs-lookup"><span data-stu-id="30560-787">50,00</span></span></td>
<td><span data-ttu-id="30560-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-789">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-789">CC001</span></span></td>
<td><span data-ttu-id="30560-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="30560-790">HR</span></span></td>
<td><span data-ttu-id="30560-791">10001</span><span class="sxs-lookup"><span data-stu-id="30560-791">10001</span></span></td>
<td><span data-ttu-id="30560-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-792">Electricity</span></span></td>
<td><span data-ttu-id="30560-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-793">Variable cost</span></span></td>
<td><span data-ttu-id="30560-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="30560-794">-1,245.71</span></span></td>
<td><span data-ttu-id="30560-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-796">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-796">CC002</span></span></td>
<td><span data-ttu-id="30560-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-797">Finance</span></span></td>
<td><span data-ttu-id="30560-798">10001</span><span class="sxs-lookup"><span data-stu-id="30560-798">10001</span></span></td>
<td><span data-ttu-id="30560-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-799">Electricity</span></span></td>
<td><span data-ttu-id="30560-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-800">Variable cost</span></span></td>
<td><span data-ttu-id="30560-801">436.00</span><span class="sxs-lookup"><span data-stu-id="30560-801">436.00</span></span></td>
<td><span data-ttu-id="30560-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-803">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-803">CC003</span></span></td>
<td><span data-ttu-id="30560-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-804">Assembly</span></span></td>
<td><span data-ttu-id="30560-805">10001</span><span class="sxs-lookup"><span data-stu-id="30560-805">10001</span></span></td>
<td><span data-ttu-id="30560-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-806">Electricity</span></span></td>
<td><span data-ttu-id="30560-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-807">Variable cost</span></span></td>
<td><span data-ttu-id="30560-808">685.14</span><span class="sxs-lookup"><span data-stu-id="30560-808">685.14</span></span></td>
<td><span data-ttu-id="30560-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-810">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-810">CC004</span></span></td>
<td><span data-ttu-id="30560-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-811">Packaging</span></span></td>
<td><span data-ttu-id="30560-812">10001</span><span class="sxs-lookup"><span data-stu-id="30560-812">10001</span></span></td>
<td><span data-ttu-id="30560-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-813">Electricity</span></span></td>
<td><span data-ttu-id="30560-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-814">Variable cost</span></span></td>
<td><span data-ttu-id="30560-815">124.57</span><span class="sxs-lookup"><span data-stu-id="30560-815">124.57</span></span></td>
<td><span data-ttu-id="30560-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-817">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-817">CC002</span></span></td>
<td><span data-ttu-id="30560-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-818">Finance</span></span></td>
<td><span data-ttu-id="30560-819">10001</span><span class="sxs-lookup"><span data-stu-id="30560-819">10001</span></span></td>
<td><span data-ttu-id="30560-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-820">Electricity</span></span></td>
<td><span data-ttu-id="30560-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-821">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="30560-822">-675.00</span></span></td>
<td><span data-ttu-id="30560-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-824">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-824">CC003</span></span></td>
<td><span data-ttu-id="30560-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-825">Assembly</span></span></td>
<td><span data-ttu-id="30560-826">10001</span><span class="sxs-lookup"><span data-stu-id="30560-826">10001</span></span></td>
<td><span data-ttu-id="30560-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-827">Electricity</span></span></td>
<td><span data-ttu-id="30560-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-828">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-829">438.75</span><span class="sxs-lookup"><span data-stu-id="30560-829">438.75</span></span></td>
<td><span data-ttu-id="30560-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-831">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-831">CC004</span></span></td>
<td><span data-ttu-id="30560-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-832">Packaging</span></span></td>
<td><span data-ttu-id="30560-833">10001</span><span class="sxs-lookup"><span data-stu-id="30560-833">10001</span></span></td>
<td><span data-ttu-id="30560-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-834">Electricity</span></span></td>
<td><span data-ttu-id="30560-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-835">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-836">236.25</span><span class="sxs-lookup"><span data-stu-id="30560-836">236.25</span></span></td>
<td><span data-ttu-id="30560-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-838">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-838">CC002</span></span></td>
<td><span data-ttu-id="30560-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="30560-839">Finance</span></span></td>
<td><span data-ttu-id="30560-840">10001</span><span class="sxs-lookup"><span data-stu-id="30560-840">10001</span></span></td>
<td><span data-ttu-id="30560-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-841">Electricity</span></span></td>
<td><span data-ttu-id="30560-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-842">Variable cost</span></span></td>
<td><span data-ttu-id="30560-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="30560-843">-8,150.29</span></span></td>
<td><span data-ttu-id="30560-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-845">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-845">CC003</span></span></td>
<td><span data-ttu-id="30560-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-846">Assembly</span></span></td>
<td><span data-ttu-id="30560-847">10001</span><span class="sxs-lookup"><span data-stu-id="30560-847">10001</span></span></td>
<td><span data-ttu-id="30560-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-848">Electricity</span></span></td>
<td><span data-ttu-id="30560-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-849">Variable cost</span></span></td>
<td><span data-ttu-id="30560-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="30560-850">5,297.69</span></span></td>
<td><span data-ttu-id="30560-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-852">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-852">CC004</span></span></td>
<td><span data-ttu-id="30560-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="30560-853">Packaging</span></span></td>
<td><span data-ttu-id="30560-854">10001</span><span class="sxs-lookup"><span data-stu-id="30560-854">10001</span></span></td>
<td><span data-ttu-id="30560-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-855">Electricity</span></span></td>
<td><span data-ttu-id="30560-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-856">Variable cost</span></span></td>
<td><span data-ttu-id="30560-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="30560-857">2,852.60</span></span></td>
<td><span data-ttu-id="30560-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-859">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-859">CC003</span></span></td>
<td><span data-ttu-id="30560-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-860">Assembly</span></span></td>
<td><span data-ttu-id="30560-861">10001</span><span class="sxs-lookup"><span data-stu-id="30560-861">10001</span></span></td>
<td><span data-ttu-id="30560-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-862">Electricity</span></span></td>
<td><span data-ttu-id="30560-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-863">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="30560-864">-713.75</span></span></td>
<td><span data-ttu-id="30560-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-866">Prod 1</span></span></td>
<td><span data-ttu-id="30560-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-867">Product 1</span></span></td>
<td><span data-ttu-id="30560-868">10001</span><span class="sxs-lookup"><span data-stu-id="30560-868">10001</span></span></td>
<td><span data-ttu-id="30560-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-869">Electricity</span></span></td>
<td><span data-ttu-id="30560-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-870">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-871">535.31</span><span class="sxs-lookup"><span data-stu-id="30560-871">535.31</span></span></td>
<td><span data-ttu-id="30560-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-873">Prod 2</span></span></td>
<td><span data-ttu-id="30560-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-874">Product 2</span></span></td>
<td><span data-ttu-id="30560-875">10001</span><span class="sxs-lookup"><span data-stu-id="30560-875">10001</span></span></td>
<td><span data-ttu-id="30560-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-876">Electricity</span></span></td>
<td><span data-ttu-id="30560-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-877">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-878">178.44</span><span class="sxs-lookup"><span data-stu-id="30560-878">178.44</span></span></td>
<td><span data-ttu-id="30560-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-880">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-880">CC003</span></span></td>
<td><span data-ttu-id="30560-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-881">Assembly</span></span></td>
<td><span data-ttu-id="30560-882">10001</span><span class="sxs-lookup"><span data-stu-id="30560-882">10001</span></span></td>
<td><span data-ttu-id="30560-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-883">Electricity</span></span></td>
<td><span data-ttu-id="30560-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-884">Variable cost</span></span></td>
<td><span data-ttu-id="30560-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="30560-885">-5,982.83</span></span></td>
<td><span data-ttu-id="30560-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-887">Prod 1</span></span></td>
<td><span data-ttu-id="30560-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-888">Product 1</span></span></td>
<td><span data-ttu-id="30560-889">10001</span><span class="sxs-lookup"><span data-stu-id="30560-889">10001</span></span></td>
<td><span data-ttu-id="30560-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-890">Electricity</span></span></td>
<td><span data-ttu-id="30560-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-891">Variable cost</span></span></td>
<td><span data-ttu-id="30560-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="30560-892">4,487.12</span></span></td>
<td><span data-ttu-id="30560-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-894">Prod 2</span></span></td>
<td><span data-ttu-id="30560-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-895">Product 2</span></span></td>
<td><span data-ttu-id="30560-896">10001</span><span class="sxs-lookup"><span data-stu-id="30560-896">10001</span></span></td>
<td><span data-ttu-id="30560-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-897">Electricity</span></span></td>
<td><span data-ttu-id="30560-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-898">Variable cost</span></span></td>
<td><span data-ttu-id="30560-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="30560-899">1,495.71</span></span></td>
<td><span data-ttu-id="30560-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-901">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-901">CC003</span></span></td>
<td><span data-ttu-id="30560-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-902">Assembly</span></span></td>
<td><span data-ttu-id="30560-903">10001</span><span class="sxs-lookup"><span data-stu-id="30560-903">10001</span></span></td>
<td><span data-ttu-id="30560-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-904">Electricity</span></span></td>
<td><span data-ttu-id="30560-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-905">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="30560-906">-286.25</span></span></td>
<td><span data-ttu-id="30560-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-908">Prod 1</span></span></td>
<td><span data-ttu-id="30560-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-909">Product 1</span></span></td>
<td><span data-ttu-id="30560-910">10001</span><span class="sxs-lookup"><span data-stu-id="30560-910">10001</span></span></td>
<td><span data-ttu-id="30560-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-911">Electricity</span></span></td>
<td><span data-ttu-id="30560-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-912">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-913">241.05</span><span class="sxs-lookup"><span data-stu-id="30560-913">241.05</span></span></td>
<td><span data-ttu-id="30560-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-915">Prod 2</span></span></td>
<td><span data-ttu-id="30560-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-916">Product 2</span></span></td>
<td><span data-ttu-id="30560-917">10001</span><span class="sxs-lookup"><span data-stu-id="30560-917">10001</span></span></td>
<td><span data-ttu-id="30560-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-918">Electricity</span></span></td>
<td><span data-ttu-id="30560-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-919">Fixed cost</span></span></td>
<td><span data-ttu-id="30560-920">45.20</span><span class="sxs-lookup"><span data-stu-id="30560-920">45.20</span></span></td>
<td><span data-ttu-id="30560-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-922">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-922">CC003</span></span></td>
<td><span data-ttu-id="30560-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="30560-923">Assembly</span></span></td>
<td><span data-ttu-id="30560-924">10001</span><span class="sxs-lookup"><span data-stu-id="30560-924">10001</span></span></td>
<td><span data-ttu-id="30560-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-925">Electricity</span></span></td>
<td><span data-ttu-id="30560-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-926">Variable cost</span></span></td>
<td><span data-ttu-id="30560-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="30560-927">-2,977.17</span></span></td>
<td><span data-ttu-id="30560-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-929">Prod 1</span></span></td>
<td><span data-ttu-id="30560-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="30560-930">Product 1</span></span></td>
<td><span data-ttu-id="30560-931">10001</span><span class="sxs-lookup"><span data-stu-id="30560-931">10001</span></span></td>
<td><span data-ttu-id="30560-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-932">Electricity</span></span></td>
<td><span data-ttu-id="30560-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-933">Variable cost</span></span></td>
<td><span data-ttu-id="30560-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="30560-934">2,507.09</span></span></td>
<td><span data-ttu-id="30560-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="30560-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-936">Prod 2</span></span></td>
<td><span data-ttu-id="30560-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="30560-937">Product 2</span></span></td>
<td><span data-ttu-id="30560-938">10001</span><span class="sxs-lookup"><span data-stu-id="30560-938">10001</span></span></td>
<td><span data-ttu-id="30560-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-939">Electricity</span></span></td>
<td><span data-ttu-id="30560-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-940">Variable cost</span></span></td>
<td><span data-ttu-id="30560-941">470.08</span><span class="sxs-lookup"><span data-stu-id="30560-941">470.08</span></span></td>
<td><span data-ttu-id="30560-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="30560-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="30560-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="30560-943">Conclusion</span></span>
<span data-ttu-id="30560-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="30560-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="30560-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="30560-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="30560-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="30560-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="30560-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="30560-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="30560-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="30560-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="30560-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="30560-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="30560-950">Totale</span><span class="sxs-lookup"><span data-stu-id="30560-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="30560-951">CC099</span><span class="sxs-lookup"><span data-stu-id="30560-951">CC099</span></span></th>
<th><span data-ttu-id="30560-952">CC001</span><span class="sxs-lookup"><span data-stu-id="30560-952">CC001</span></span></th>
<th><span data-ttu-id="30560-953">CC002</span><span class="sxs-lookup"><span data-stu-id="30560-953">CC002</span></span></th>
<th><span data-ttu-id="30560-954">CC003</span><span class="sxs-lookup"><span data-stu-id="30560-954">CC003</span></span></th>
<th><span data-ttu-id="30560-955">CC004</span><span class="sxs-lookup"><span data-stu-id="30560-955">CC004</span></span></th>
<th><span data-ttu-id="30560-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="30560-956">Proj 1</span></span></th>
<th><span data-ttu-id="30560-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="30560-957">Proj 2</span></span></th>
<th><span data-ttu-id="30560-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="30560-958">Prod 1</span></span></th>
<th><span data-ttu-id="30560-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="30560-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="30560-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="30560-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="30560-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="30560-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="30560-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="30560-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="30560-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-971">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="30560-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="30560-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-973">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-974">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-975">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-976">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-977">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="30560-978">776.36</span><span class="sxs-lookup"><span data-stu-id="30560-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-979">223.64</span><span class="sxs-lookup"><span data-stu-id="30560-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="30560-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="30560-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-982">000</span><span class="sxs-lookup"><span data-stu-id="30560-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-983">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-984">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-985">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-986">0,00</span><span class="sxs-lookup"><span data-stu-id="30560-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-987">30,00</span><span class="sxs-lookup"><span data-stu-id="30560-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-988">10,00</span><span class="sxs-lookup"><span data-stu-id="30560-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="30560-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="30560-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="30560-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="30560-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="30560-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="30560-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="30560-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30560-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="30560-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="30560-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="30560-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="30560-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="30560-996">Per ulteriori informazioni, vedere [Criteri rollup costi e calcolo dei costi generali](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="30560-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]