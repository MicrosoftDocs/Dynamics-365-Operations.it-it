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
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: d60248f2bd6774b2e9afdb3632b6eb31d67349ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009520"
---
# <a name="overhead-calculation"></a><span data-ttu-id="6ddb0-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ddb0-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="6ddb0-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="6ddb0-105">Term definition</span></span>
---------------

<span data-ttu-id="6ddb0-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="6ddb0-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="6ddb0-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="6ddb0-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="6ddb0-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="6ddb0-109">Rent</span></span>
-   <span data-ttu-id="6ddb0-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-110">Electricity</span></span>
-   <span data-ttu-id="6ddb0-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="6ddb0-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="6ddb0-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="6ddb0-112">Overhead calculation overview</span></span>
<span data-ttu-id="6ddb0-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="6ddb0-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="6ddb0-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="6ddb0-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="6ddb0-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="6ddb0-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="6ddb0-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="6ddb0-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-119">Version type</span></span>
-   <span data-ttu-id="6ddb0-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="6ddb0-120">Date and time</span></span>
-   <span data-ttu-id="6ddb0-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="6ddb0-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-122">Fiscal year</span></span>
-   <span data-ttu-id="6ddb0-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-123">Fiscal period</span></span>

<span data-ttu-id="6ddb0-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="6ddb0-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="6ddb0-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="6ddb0-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="6ddb0-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="6ddb0-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="6ddb0-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="6ddb0-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="6ddb0-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="6ddb0-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="6ddb0-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="6ddb0-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="6ddb0-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="6ddb0-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-140">Main account</span></span></th>
<th><span data-ttu-id="6ddb0-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-143">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-143">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-144">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-145">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-145">10001</span></span></td>
<td><span data-ttu-id="6ddb0-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-146">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="6ddb0-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="6ddb0-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="6ddb0-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="6ddb0-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-151">Define the cost behavior rule</span></span>

<span data-ttu-id="6ddb0-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="6ddb0-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="6ddb0-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="6ddb0-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="6ddb0-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="6ddb0-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="6ddb0-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="6ddb0-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="6ddb0-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-160">Journal</span></span></th>
<th><span data-ttu-id="6ddb0-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6ddb0-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6ddb0-163">Versione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-164">00001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-164">00001</span></span></td>
<td><span data-ttu-id="6ddb0-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="6ddb0-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-166">Fiscal</span></span></td>
<td><span data-ttu-id="6ddb0-167">2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-167">2017</span></span></td>
<td><span data-ttu-id="6ddb0-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-168">Period 1</span></span></td>
<td><span data-ttu-id="6ddb0-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="6ddb0-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-173">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-174">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-175">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-177">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-177">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-178">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-179">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-179">10001</span></span></td>
<td><span data-ttu-id="6ddb0-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-180">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="6ddb0-181">Unclassified</span></span></td>
<td><span data-ttu-id="6ddb0-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6ddb0-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-185">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-186">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-187">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-187">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-189">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-189">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-190">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-191">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-191">10001</span></span></td>
<td><span data-ttu-id="6ddb0-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-192">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="6ddb0-193">Unclassified</span></span></td>
<td><span data-ttu-id="6ddb0-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-194">10,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-196">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-196">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-197">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-198">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-198">10001</span></span></td>
<td><span data-ttu-id="6ddb0-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-199">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="6ddb0-200">Unclassified</span></span></td>
<td><span data-ttu-id="6ddb0-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-201">-10,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-203">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-203">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-204">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-205">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-205">10001</span></span></td>
<td><span data-ttu-id="6ddb0-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-206">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-207">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-208">1,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-210">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-210">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-211">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-212">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-212">10001</span></span></td>
<td><span data-ttu-id="6ddb0-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-213">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-214">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-215">9,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="6ddb0-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="6ddb0-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="6ddb0-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="6ddb0-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-221">Define the cost distribution rule</span></span>

<span data-ttu-id="6ddb0-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="6ddb0-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="6ddb0-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="6ddb0-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="6ddb0-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="6ddb0-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-228">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-229">KWH</span><span class="sxs-lookup"><span data-stu-id="6ddb0-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-230">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-230">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-231">HR</span></span></td>
<td><span data-ttu-id="6ddb0-232">1.000</span><span class="sxs-lookup"><span data-stu-id="6ddb0-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-233">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-233">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-234">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-235">6.000</span><span class="sxs-lookup"><span data-stu-id="6ddb0-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-236">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-236">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-237">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-238">0</span><span class="sxs-lookup"><span data-stu-id="6ddb0-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-240">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-241">Magnitude</span></span></th>
<th><span data-ttu-id="6ddb0-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-242">Allocation factor</span></span></th>
<th><span data-ttu-id="6ddb0-243">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-244">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-244">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-245">HR</span></span></td>
<td><span data-ttu-id="6ddb0-246">1.000</span><span class="sxs-lookup"><span data-stu-id="6ddb0-246">1,000</span></span></td>
<td><span data-ttu-id="6ddb0-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-249">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-249">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-250">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-251">6.000</span><span class="sxs-lookup"><span data-stu-id="6ddb0-251">6,000</span></span></td>
<td><span data-ttu-id="6ddb0-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="6ddb0-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-254">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-254">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-255">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-256">0</span><span class="sxs-lookup"><span data-stu-id="6ddb0-256">0</span></span></td>
<td><span data-ttu-id="6ddb0-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-258">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="6ddb0-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-261">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-262">Formula</span><span class="sxs-lookup"><span data-stu-id="6ddb0-262">Formula</span></span></th>
<th><span data-ttu-id="6ddb0-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-263">Magnitude</span></span></th>
<th><span data-ttu-id="6ddb0-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-264">Allocation factor</span></span></th>
<th><span data-ttu-id="6ddb0-265">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-266">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-266">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-267">HR</span></span></td>
<td><span data-ttu-id="6ddb0-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="6ddb0-269">1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-269">1</span></span></td>
<td><span data-ttu-id="6ddb0-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-271">500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-272">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-272">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-273">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="6ddb0-275">1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-275">1</span></span></td>
<td><span data-ttu-id="6ddb0-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-277">500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-278">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-278">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-279">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="6ddb0-281">0</span><span class="sxs-lookup"><span data-stu-id="6ddb0-281">0</span></span></td>
<td><span data-ttu-id="6ddb0-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-283">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="6ddb0-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-285">Journal</span></span></th>
<th><span data-ttu-id="6ddb0-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6ddb0-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6ddb0-288">Versione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-289">00002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-289">00002</span></span></td>
<td><span data-ttu-id="6ddb0-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="6ddb0-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-291">Fiscal</span></span></td>
<td><span data-ttu-id="6ddb0-292">2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-292">2017</span></span></td>
<td><span data-ttu-id="6ddb0-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-293">Period 1</span></span></td>
<td><span data-ttu-id="6ddb0-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="6ddb0-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-298">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-299">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-300">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-302">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-302">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-303">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-304">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-304">10001</span></span></td>
<td><span data-ttu-id="6ddb0-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-305">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-306">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-309">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-309">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-310">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-311">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-311">10001</span></span></td>
<td><span data-ttu-id="6ddb0-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-312">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-313">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6ddb0-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-317">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-318">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-319">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-319">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-321">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-321">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-322">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-323">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-323">10001</span></span></td>
<td><span data-ttu-id="6ddb0-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-324">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-325">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-326">-1,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-328">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-328">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-329">HR</span></span></td>
<td><span data-ttu-id="6ddb0-330">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-330">10001</span></span></td>
<td><span data-ttu-id="6ddb0-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-331">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-332">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-333">500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-333">500.00</span></span></td>
<td><span data-ttu-id="6ddb0-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-335">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-335">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-336">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-337">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-337">10001</span></span></td>
<td><span data-ttu-id="6ddb0-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-338">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-339">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-340">500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-340">500.00</span></span></td>
<td><span data-ttu-id="6ddb0-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-342">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-342">CC099</span></span></td>
<td><span data-ttu-id="6ddb0-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="6ddb0-343">Default cost center</span></span></td>
<td><span data-ttu-id="6ddb0-344">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-344">10001</span></span></td>
<td><span data-ttu-id="6ddb0-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-345">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-346">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-347">-9,000.00</span></span></td>
<td><span data-ttu-id="6ddb0-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-349">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-349">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-350">HR</span></span></td>
<td><span data-ttu-id="6ddb0-351">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-351">10001</span></span></td>
<td><span data-ttu-id="6ddb0-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-352">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-353">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-354">1,285.71</span></span></td>
<td><span data-ttu-id="6ddb0-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-356">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-356">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-357">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-358">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-358">10001</span></span></td>
<td><span data-ttu-id="6ddb0-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-359">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-360">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="6ddb0-361">7,714.29</span></span></td>
<td><span data-ttu-id="6ddb0-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="6ddb0-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="6ddb0-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="6ddb0-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="6ddb0-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="6ddb0-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="6ddb0-367">Define the overhead rate</span></span>

<span data-ttu-id="6ddb0-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="6ddb0-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-370">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-371">Ore</span><span class="sxs-lookup"><span data-stu-id="6ddb0-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-372">Proj 1</span></span></td>
<td><span data-ttu-id="6ddb0-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-373">Project 1</span></span></td>
<td><span data-ttu-id="6ddb0-374">3</span><span class="sxs-lookup"><span data-stu-id="6ddb0-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-375">Proj 2</span></span></td>
<td><span data-ttu-id="6ddb0-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-376">Project 2</span></span></td>
<td><span data-ttu-id="6ddb0-377">1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-379">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-380">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-381">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-382">Unità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-382">Units</span></span></th>
<th><span data-ttu-id="6ddb0-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-384">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-384">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-385">HR</span></span></td>
<td><span data-ttu-id="6ddb0-386">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-386">10001</span></span></td>
<td><span data-ttu-id="6ddb0-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-387">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-388">1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-388">1</span></span></td>
<td><span data-ttu-id="6ddb0-389">10</span><span class="sxs-lookup"><span data-stu-id="6ddb0-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-391">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-392">Magnitude</span></span></th>
<th><span data-ttu-id="6ddb0-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-393">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-394">Allocation factor</span></span></th>
<th><span data-ttu-id="6ddb0-395">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-396">Proj 1</span></span></td>
<td><span data-ttu-id="6ddb0-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-397">Project 1</span></span></td>
<td><span data-ttu-id="6ddb0-398">3</span><span class="sxs-lookup"><span data-stu-id="6ddb0-398">3</span></span></td>
<td><span data-ttu-id="6ddb0-399">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-399">10001</span></span></td>
<td><span data-ttu-id="6ddb0-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="6ddb0-401">30,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-402">Proj 2</span></span></td>
<td><span data-ttu-id="6ddb0-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-403">Project 2</span></span></td>
<td><span data-ttu-id="6ddb0-404">1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-404">1</span></span></td>
<td><span data-ttu-id="6ddb0-405">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-405">10001</span></span></td>
<td><span data-ttu-id="6ddb0-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="6ddb0-407">10,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="6ddb0-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-409">Journal</span></span></th>
<th><span data-ttu-id="6ddb0-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6ddb0-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6ddb0-412">Versione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-413">00003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-413">00003</span></span></td>
<td><span data-ttu-id="6ddb0-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="6ddb0-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="6ddb0-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-415">Fiscal</span></span></td>
<td><span data-ttu-id="6ddb0-416">2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-416">2017</span></span></td>
<td><span data-ttu-id="6ddb0-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-417">Period 1</span></span></td>
<td><span data-ttu-id="6ddb0-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="6ddb0-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-421">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-424">Proj 1</span></span></td>
<td><span data-ttu-id="6ddb0-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="6ddb0-426">3,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-428">Proj 2</span></span></td>
<td><span data-ttu-id="6ddb0-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="6ddb0-430">1,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6ddb0-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-433">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-434">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-435">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-435">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-437">CC0001</span></span></td>
<td><span data-ttu-id="6ddb0-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-438">HR</span></span></td>
<td><span data-ttu-id="6ddb0-439">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-439">10001</span></span></td>
<td><span data-ttu-id="6ddb0-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-440">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-441">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-442">-30.00</span></span></td>
<td><span data-ttu-id="6ddb0-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-444">Proj 1</span></span></td>
<td><span data-ttu-id="6ddb0-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="6ddb0-446">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-446">10001</span></span></td>
<td><span data-ttu-id="6ddb0-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-447">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-448">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-449">30,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-449">30.00</span></span></td>
<td><span data-ttu-id="6ddb0-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-451">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-451">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-452">HR</span></span></td>
<td><span data-ttu-id="6ddb0-453">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-453">10001</span></span></td>
<td><span data-ttu-id="6ddb0-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-454">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-455">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-456">-10.00</span></span></td>
<td><span data-ttu-id="6ddb0-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-458">Proj 2</span></span></td>
<td><span data-ttu-id="6ddb0-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="6ddb0-460">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-460">10001</span></span></td>
<td><span data-ttu-id="6ddb0-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-461">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-462">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-463">10.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-463">10.00</span></span></td>
<td><span data-ttu-id="6ddb0-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="6ddb0-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="6ddb0-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="6ddb0-468">Finance supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="6ddb0-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="6ddb0-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="6ddb0-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="6ddb0-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="6ddb0-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="6ddb0-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="6ddb0-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="6ddb0-475">Define the cost allocation</span></span>

<span data-ttu-id="6ddb0-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="6ddb0-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="6ddb0-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-479">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="6ddb0-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-481">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-481">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-482">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-483">35</span><span class="sxs-lookup"><span data-stu-id="6ddb0-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-484">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-484">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-485">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-486">55</span><span class="sxs-lookup"><span data-stu-id="6ddb0-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-487">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-487">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-488">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-489">10</span><span class="sxs-lookup"><span data-stu-id="6ddb0-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="6ddb0-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-492">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-494">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-494">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-495">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-496">65</span><span class="sxs-lookup"><span data-stu-id="6ddb0-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-497">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-497">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-498">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-499">35</span><span class="sxs-lookup"><span data-stu-id="6ddb0-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="6ddb0-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-502">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-504">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-505">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-506">60</span><span class="sxs-lookup"><span data-stu-id="6ddb0-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-507">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-508">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-509">20</span><span class="sxs-lookup"><span data-stu-id="6ddb0-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="6ddb0-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-512">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-514">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-515">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-516">80</span><span class="sxs-lookup"><span data-stu-id="6ddb0-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-517">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-518">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-519">15</span><span class="sxs-lookup"><span data-stu-id="6ddb0-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="6ddb0-520">Le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="6ddb0-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="6ddb0-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-523">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-524">Magnitude</span></span></th>
<th><span data-ttu-id="6ddb0-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-525">Allocation factor</span></span></th>
<th><span data-ttu-id="6ddb0-526">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-526">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-528">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-528">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-529">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-530">35</span><span class="sxs-lookup"><span data-stu-id="6ddb0-530">35</span></span></td>
<td><span data-ttu-id="6ddb0-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="6ddb0-532">175.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-532">175.00</span></span></td>
<td><span data-ttu-id="6ddb0-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-534">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-534">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-535">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-536">55</span><span class="sxs-lookup"><span data-stu-id="6ddb0-536">55</span></span></td>
<td><span data-ttu-id="6ddb0-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="6ddb0-538">275.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-538">275.00</span></span></td>
<td><span data-ttu-id="6ddb0-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-540">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-540">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-541">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-542">10</span><span class="sxs-lookup"><span data-stu-id="6ddb0-542">10</span></span></td>
<td><span data-ttu-id="6ddb0-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="6ddb0-544">50,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-544">50.00</span></span></td>
<td><span data-ttu-id="6ddb0-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-546">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-546">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-547">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-548">35</span><span class="sxs-lookup"><span data-stu-id="6ddb0-548">35</span></span></td>
<td><span data-ttu-id="6ddb0-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="6ddb0-550">436.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-550">436.00</span></span></td>
<td><span data-ttu-id="6ddb0-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-552">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-552">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-553">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-554">55</span><span class="sxs-lookup"><span data-stu-id="6ddb0-554">55</span></span></td>
<td><span data-ttu-id="6ddb0-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="6ddb0-556">685.14</span><span class="sxs-lookup"><span data-stu-id="6ddb0-556">685.14</span></span></td>
<td><span data-ttu-id="6ddb0-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-558">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-558">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-559">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-560">10</span><span class="sxs-lookup"><span data-stu-id="6ddb0-560">10</span></span></td>
<td><span data-ttu-id="6ddb0-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="6ddb0-562">124.57</span><span class="sxs-lookup"><span data-stu-id="6ddb0-562">124.57</span></span></td>
<td><span data-ttu-id="6ddb0-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-565">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-566">Magnitude</span></span></th>
<th><span data-ttu-id="6ddb0-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-567">Allocation factor</span></span></th>
<th><span data-ttu-id="6ddb0-568">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-568">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-570">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-570">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-571">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-572">65</span><span class="sxs-lookup"><span data-stu-id="6ddb0-572">65</span></span></td>
<td><span data-ttu-id="6ddb0-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="6ddb0-574">438.75</span><span class="sxs-lookup"><span data-stu-id="6ddb0-574">438.75</span></span></td>
<td><span data-ttu-id="6ddb0-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-576">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-576">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-577">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-578">35</span><span class="sxs-lookup"><span data-stu-id="6ddb0-578">35</span></span></td>
<td><span data-ttu-id="6ddb0-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="6ddb0-580">236.25</span><span class="sxs-lookup"><span data-stu-id="6ddb0-580">236.25</span></span></td>
<td><span data-ttu-id="6ddb0-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-582">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-582">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-583">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-584">65</span><span class="sxs-lookup"><span data-stu-id="6ddb0-584">65</span></span></td>
<td><span data-ttu-id="6ddb0-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="6ddb0-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="6ddb0-586">5,297.69</span></span></td>
<td><span data-ttu-id="6ddb0-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-588">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-588">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-589">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-590">35</span><span class="sxs-lookup"><span data-stu-id="6ddb0-590">35</span></span></td>
<td><span data-ttu-id="6ddb0-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="6ddb0-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="6ddb0-592">2,852.60</span></span></td>
<td><span data-ttu-id="6ddb0-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-595">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-596">Magnitude</span></span></th>
<th><span data-ttu-id="6ddb0-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-597">Allocation factor</span></span></th>
<th><span data-ttu-id="6ddb0-598">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-598">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-600">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-601">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-602">60</span><span class="sxs-lookup"><span data-stu-id="6ddb0-602">60</span></span></td>
<td><span data-ttu-id="6ddb0-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="6ddb0-604">535.31</span><span class="sxs-lookup"><span data-stu-id="6ddb0-604">535.31</span></span></td>
<td><span data-ttu-id="6ddb0-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-606">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-607">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-608">20</span><span class="sxs-lookup"><span data-stu-id="6ddb0-608">20</span></span></td>
<td><span data-ttu-id="6ddb0-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="6ddb0-610">178.44</span><span class="sxs-lookup"><span data-stu-id="6ddb0-610">178.44</span></span></td>
<td><span data-ttu-id="6ddb0-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-612">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-613">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-614">60</span><span class="sxs-lookup"><span data-stu-id="6ddb0-614">60</span></span></td>
<td><span data-ttu-id="6ddb0-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="6ddb0-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="6ddb0-616">4,487.12</span></span></td>
<td><span data-ttu-id="6ddb0-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-618">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-619">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-620">20</span><span class="sxs-lookup"><span data-stu-id="6ddb0-620">20</span></span></td>
<td><span data-ttu-id="6ddb0-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="6ddb0-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-622">1,495.71</span></span></td>
<td><span data-ttu-id="6ddb0-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ddb0-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-625">Cost object</span></span></th>
<th><span data-ttu-id="6ddb0-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="6ddb0-626">Magnitude</span></span></th>
<th><span data-ttu-id="6ddb0-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-627">Allocation factor</span></span></th>
<th><span data-ttu-id="6ddb0-628">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-628">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-630">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-631">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-632">80</span><span class="sxs-lookup"><span data-stu-id="6ddb0-632">80</span></span></td>
<td><span data-ttu-id="6ddb0-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="6ddb0-634">241.05</span><span class="sxs-lookup"><span data-stu-id="6ddb0-634">241.05</span></span></td>
<td><span data-ttu-id="6ddb0-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-636">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-637">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-638">15</span><span class="sxs-lookup"><span data-stu-id="6ddb0-638">15</span></span></td>
<td><span data-ttu-id="6ddb0-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="6ddb0-640">45.20</span><span class="sxs-lookup"><span data-stu-id="6ddb0-640">45.20</span></span></td>
<td><span data-ttu-id="6ddb0-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-642">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-643">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-644">80</span><span class="sxs-lookup"><span data-stu-id="6ddb0-644">80</span></span></td>
<td><span data-ttu-id="6ddb0-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="6ddb0-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="6ddb0-646">2,507.09</span></span></td>
<td><span data-ttu-id="6ddb0-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-648">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-649">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-650">15</span><span class="sxs-lookup"><span data-stu-id="6ddb0-650">15</span></span></td>
<td><span data-ttu-id="6ddb0-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="6ddb0-652">470.08</span><span class="sxs-lookup"><span data-stu-id="6ddb0-652">470.08</span></span></td>
<td><span data-ttu-id="6ddb0-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="6ddb0-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="6ddb0-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-655">Journal</span></span></th>
<th><span data-ttu-id="6ddb0-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6ddb0-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6ddb0-658">Versione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-659">00004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-659">00004</span></span></td>
<td><span data-ttu-id="6ddb0-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="6ddb0-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="6ddb0-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-661">Fiscal</span></span></td>
<td><span data-ttu-id="6ddb0-662">2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-662">2017</span></span></td>
<td><span data-ttu-id="6ddb0-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-663">Period 1</span></span></td>
<td><span data-ttu-id="6ddb0-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="6ddb0-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6ddb0-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-668">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-669">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-670">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-672">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-672">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-673">HR</span></span></td>
<td><span data-ttu-id="6ddb0-674">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-674">10001</span></span></td>
<td><span data-ttu-id="6ddb0-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-675">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-676">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-677">500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-679">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-679">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-680">HR</span></span></td>
<td><span data-ttu-id="6ddb0-681">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-681">10001</span></span></td>
<td><span data-ttu-id="6ddb0-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-682">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-683">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-686">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-686">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-687">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-688">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-688">10001</span></span></td>
<td><span data-ttu-id="6ddb0-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-689">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-690">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-691">675.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-693">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-693">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-694">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-695">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-695">10001</span></span></td>
<td><span data-ttu-id="6ddb0-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-696">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-697">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="6ddb0-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-700">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-700">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-701">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-702">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-702">10001</span></span></td>
<td><span data-ttu-id="6ddb0-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-703">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-704">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-705">713.75</span><span class="sxs-lookup"><span data-stu-id="6ddb0-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-707">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-707">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-708">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-709">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-709">10001</span></span></td>
<td><span data-ttu-id="6ddb0-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-710">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-711">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="6ddb0-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-714">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-714">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-715">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-716">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-716">10001</span></span></td>
<td><span data-ttu-id="6ddb0-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-717">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-718">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-719">286.25</span><span class="sxs-lookup"><span data-stu-id="6ddb0-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-721">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-721">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-722">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-723">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-723">10001</span></span></td>
<td><span data-ttu-id="6ddb0-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-724">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-725">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="6ddb0-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-728">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-729">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-730">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-730">10001</span></span></td>
<td><span data-ttu-id="6ddb0-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-731">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-732">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-733">776.36</span><span class="sxs-lookup"><span data-stu-id="6ddb0-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-735">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-736">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-737">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-737">10001</span></span></td>
<td><span data-ttu-id="6ddb0-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-738">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-739">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="6ddb0-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-742">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-743">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-744">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-744">10001</span></span></td>
<td><span data-ttu-id="6ddb0-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-745">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-746">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-747">223.64</span><span class="sxs-lookup"><span data-stu-id="6ddb0-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="6ddb0-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-749">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-750">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-751">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-751">10001</span></span></td>
<td><span data-ttu-id="6ddb0-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-752">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-753">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="6ddb0-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6ddb0-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6ddb0-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6ddb0-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-757">Cost element</span></span></th>
<th><span data-ttu-id="6ddb0-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-758">Cost behavior</span></span></th>
<th><span data-ttu-id="6ddb0-759">Importo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-759">Amount</span></span></th>
<th><span data-ttu-id="6ddb0-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6ddb0-761">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-761">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-762">HR</span></span></td>
<td><span data-ttu-id="6ddb0-763">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-763">10001</span></span></td>
<td><span data-ttu-id="6ddb0-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-764">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-765">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-766">-500.00</span></span></td>
<td><span data-ttu-id="6ddb0-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-768">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-768">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-769">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-770">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-770">10001</span></span></td>
<td><span data-ttu-id="6ddb0-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-771">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-772">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-773">175.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-773">175.00</span></span></td>
<td><span data-ttu-id="6ddb0-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-775">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-775">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-776">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-777">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-777">10001</span></span></td>
<td><span data-ttu-id="6ddb0-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-778">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-779">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-780">275.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-780">275.00</span></span></td>
<td><span data-ttu-id="6ddb0-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-782">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-782">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-783">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-784">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-784">10001</span></span></td>
<td><span data-ttu-id="6ddb0-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-785">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-786">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-787">50,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-787">50,00</span></span></td>
<td><span data-ttu-id="6ddb0-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-789">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-789">CC001</span></span></td>
<td><span data-ttu-id="6ddb0-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6ddb0-790">HR</span></span></td>
<td><span data-ttu-id="6ddb0-791">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-791">10001</span></span></td>
<td><span data-ttu-id="6ddb0-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-792">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-793">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-794">-1,245.71</span></span></td>
<td><span data-ttu-id="6ddb0-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-796">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-796">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-797">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-798">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-798">10001</span></span></td>
<td><span data-ttu-id="6ddb0-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-799">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-800">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-801">436.00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-801">436.00</span></span></td>
<td><span data-ttu-id="6ddb0-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-803">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-803">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-804">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-805">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-805">10001</span></span></td>
<td><span data-ttu-id="6ddb0-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-806">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-807">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-808">685.14</span><span class="sxs-lookup"><span data-stu-id="6ddb0-808">685.14</span></span></td>
<td><span data-ttu-id="6ddb0-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-810">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-810">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-811">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-812">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-812">10001</span></span></td>
<td><span data-ttu-id="6ddb0-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-813">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-814">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-815">124.57</span><span class="sxs-lookup"><span data-stu-id="6ddb0-815">124.57</span></span></td>
<td><span data-ttu-id="6ddb0-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-817">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-817">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-818">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-819">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-819">10001</span></span></td>
<td><span data-ttu-id="6ddb0-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-820">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-821">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-822">-675.00</span></span></td>
<td><span data-ttu-id="6ddb0-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-824">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-824">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-825">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-826">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-826">10001</span></span></td>
<td><span data-ttu-id="6ddb0-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-827">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-828">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-829">438.75</span><span class="sxs-lookup"><span data-stu-id="6ddb0-829">438.75</span></span></td>
<td><span data-ttu-id="6ddb0-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-831">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-831">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-832">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-833">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-833">10001</span></span></td>
<td><span data-ttu-id="6ddb0-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-834">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-835">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-836">236.25</span><span class="sxs-lookup"><span data-stu-id="6ddb0-836">236.25</span></span></td>
<td><span data-ttu-id="6ddb0-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-838">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-838">CC002</span></span></td>
<td><span data-ttu-id="6ddb0-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="6ddb0-839">Finance</span></span></td>
<td><span data-ttu-id="6ddb0-840">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-840">10001</span></span></td>
<td><span data-ttu-id="6ddb0-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-841">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-842">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="6ddb0-843">-8,150.29</span></span></td>
<td><span data-ttu-id="6ddb0-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-845">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-845">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-846">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-847">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-847">10001</span></span></td>
<td><span data-ttu-id="6ddb0-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-848">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-849">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="6ddb0-850">5,297.69</span></span></td>
<td><span data-ttu-id="6ddb0-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-852">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-852">CC004</span></span></td>
<td><span data-ttu-id="6ddb0-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-853">Packaging</span></span></td>
<td><span data-ttu-id="6ddb0-854">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-854">10001</span></span></td>
<td><span data-ttu-id="6ddb0-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-855">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-856">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="6ddb0-857">2,852.60</span></span></td>
<td><span data-ttu-id="6ddb0-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-859">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-859">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-860">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-861">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-861">10001</span></span></td>
<td><span data-ttu-id="6ddb0-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-862">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-863">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="6ddb0-864">-713.75</span></span></td>
<td><span data-ttu-id="6ddb0-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-866">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-867">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-868">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-868">10001</span></span></td>
<td><span data-ttu-id="6ddb0-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-869">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-870">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-871">535.31</span><span class="sxs-lookup"><span data-stu-id="6ddb0-871">535.31</span></span></td>
<td><span data-ttu-id="6ddb0-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-873">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-874">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-875">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-875">10001</span></span></td>
<td><span data-ttu-id="6ddb0-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-876">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-877">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-878">178.44</span><span class="sxs-lookup"><span data-stu-id="6ddb0-878">178.44</span></span></td>
<td><span data-ttu-id="6ddb0-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-880">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-880">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-881">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-882">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-882">10001</span></span></td>
<td><span data-ttu-id="6ddb0-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-883">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-884">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="6ddb0-885">-5,982.83</span></span></td>
<td><span data-ttu-id="6ddb0-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-887">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-888">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-889">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-889">10001</span></span></td>
<td><span data-ttu-id="6ddb0-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-890">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-891">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="6ddb0-892">4,487.12</span></span></td>
<td><span data-ttu-id="6ddb0-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-894">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-895">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-896">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-896">10001</span></span></td>
<td><span data-ttu-id="6ddb0-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-897">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-898">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="6ddb0-899">1,495.71</span></span></td>
<td><span data-ttu-id="6ddb0-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-901">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-901">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-902">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-903">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-903">10001</span></span></td>
<td><span data-ttu-id="6ddb0-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-904">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-905">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="6ddb0-906">-286.25</span></span></td>
<td><span data-ttu-id="6ddb0-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-908">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-909">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-910">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-910">10001</span></span></td>
<td><span data-ttu-id="6ddb0-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-911">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-912">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-913">241.05</span><span class="sxs-lookup"><span data-stu-id="6ddb0-913">241.05</span></span></td>
<td><span data-ttu-id="6ddb0-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-915">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-916">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-917">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-917">10001</span></span></td>
<td><span data-ttu-id="6ddb0-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-918">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-919">Fixed cost</span></span></td>
<td><span data-ttu-id="6ddb0-920">45.20</span><span class="sxs-lookup"><span data-stu-id="6ddb0-920">45.20</span></span></td>
<td><span data-ttu-id="6ddb0-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-922">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-922">CC003</span></span></td>
<td><span data-ttu-id="6ddb0-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="6ddb0-923">Assembly</span></span></td>
<td><span data-ttu-id="6ddb0-924">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-924">10001</span></span></td>
<td><span data-ttu-id="6ddb0-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-925">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-926">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="6ddb0-927">-2,977.17</span></span></td>
<td><span data-ttu-id="6ddb0-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-929">Prod 1</span></span></td>
<td><span data-ttu-id="6ddb0-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-930">Product 1</span></span></td>
<td><span data-ttu-id="6ddb0-931">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-931">10001</span></span></td>
<td><span data-ttu-id="6ddb0-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-932">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-933">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="6ddb0-934">2,507.09</span></span></td>
<td><span data-ttu-id="6ddb0-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6ddb0-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-936">Prod 2</span></span></td>
<td><span data-ttu-id="6ddb0-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-937">Product 2</span></span></td>
<td><span data-ttu-id="6ddb0-938">10001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-938">10001</span></span></td>
<td><span data-ttu-id="6ddb0-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-939">Electricity</span></span></td>
<td><span data-ttu-id="6ddb0-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-940">Variable cost</span></span></td>
<td><span data-ttu-id="6ddb0-941">470.08</span><span class="sxs-lookup"><span data-stu-id="6ddb0-941">470.08</span></span></td>
<td><span data-ttu-id="6ddb0-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="6ddb0-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="6ddb0-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="6ddb0-943">Conclusion</span></span>
<span data-ttu-id="6ddb0-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="6ddb0-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="6ddb0-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="6ddb0-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="6ddb0-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="6ddb0-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="6ddb0-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="6ddb0-950">Totale</span><span class="sxs-lookup"><span data-stu-id="6ddb0-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="6ddb0-951">CC099</span><span class="sxs-lookup"><span data-stu-id="6ddb0-951">CC099</span></span></th>
<th><span data-ttu-id="6ddb0-952">CC001</span><span class="sxs-lookup"><span data-stu-id="6ddb0-952">CC001</span></span></th>
<th><span data-ttu-id="6ddb0-953">CC002</span><span class="sxs-lookup"><span data-stu-id="6ddb0-953">CC002</span></span></th>
<th><span data-ttu-id="6ddb0-954">CC003</span><span class="sxs-lookup"><span data-stu-id="6ddb0-954">CC003</span></span></th>
<th><span data-ttu-id="6ddb0-955">CC004</span><span class="sxs-lookup"><span data-stu-id="6ddb0-955">CC004</span></span></th>
<th><span data-ttu-id="6ddb0-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-956">Proj 1</span></span></th>
<th><span data-ttu-id="6ddb0-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-957">Proj 2</span></span></th>
<th><span data-ttu-id="6ddb0-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="6ddb0-958">Prod 1</span></span></th>
<th><span data-ttu-id="6ddb0-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="6ddb0-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="6ddb0-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="6ddb0-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="6ddb0-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="6ddb0-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-971">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="6ddb0-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="6ddb0-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-973">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-974">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-975">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-976">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-977">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-978">776.36</span><span class="sxs-lookup"><span data-stu-id="6ddb0-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-979">223.64</span><span class="sxs-lookup"><span data-stu-id="6ddb0-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="6ddb0-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="6ddb0-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-982">000</span><span class="sxs-lookup"><span data-stu-id="6ddb0-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-983">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-984">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-985">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-986">0,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-987">30,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-988">10,00</span><span class="sxs-lookup"><span data-stu-id="6ddb0-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="6ddb0-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="6ddb0-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6ddb0-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb0-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="6ddb0-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="6ddb0-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="6ddb0-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="6ddb0-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="6ddb0-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="6ddb0-996">Per ulteriori informazioni, vedere [Criteri rollup costi e calcolo dei costi generali](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="6ddb0-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



