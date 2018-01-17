---
title: Calcolo generale
description: In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 936e54c0ef1de449afda2392cd1fbb304eed631b
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="57950-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="57950-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="57950-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="57950-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="57950-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="57950-105">Term definition</span></span>
---------------

<span data-ttu-id="57950-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="57950-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="57950-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="57950-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="57950-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="57950-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="57950-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="57950-109">Rent</span></span>
-   <span data-ttu-id="57950-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-110">Electricity</span></span>
-   <span data-ttu-id="57950-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="57950-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="57950-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="57950-112">Overhead calculation overview</span></span>
<span data-ttu-id="57950-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="57950-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="57950-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="57950-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="57950-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="57950-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="57950-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="57950-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="57950-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="57950-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="57950-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="57950-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="57950-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="57950-119">Version type</span></span>
-   <span data-ttu-id="57950-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="57950-120">Date and time</span></span>
-   <span data-ttu-id="57950-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="57950-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="57950-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-122">Fiscal year</span></span>
-   <span data-ttu-id="57950-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-123">Fiscal period</span></span>

<span data-ttu-id="57950-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="57950-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="57950-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="57950-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="57950-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="57950-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="57950-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="57950-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="57950-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="57950-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="57950-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="57950-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="57950-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="57950-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="57950-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="57950-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="57950-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="57950-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="57950-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="57950-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="57950-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="57950-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="57950-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="57950-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="57950-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="57950-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="57950-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="57950-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="57950-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="57950-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="57950-140">Main account</span></span></th>
<th><span data-ttu-id="57950-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="57950-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="57950-143">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-143">CC099</span></span></td>
<td><span data-ttu-id="57950-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-144">Default cost center</span></span></td>
<td><span data-ttu-id="57950-145">10001</span><span class="sxs-lookup"><span data-stu-id="57950-145">10001</span></span></td>
<td><span data-ttu-id="57950-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-146">Electricity</span></span></td>
<td><span data-ttu-id="57950-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="57950-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="57950-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="57950-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="57950-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="57950-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="57950-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-151">Define the cost behavior rule</span></span>

<span data-ttu-id="57950-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="57950-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="57950-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="57950-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="57950-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="57950-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="57950-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="57950-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="57950-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="57950-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="57950-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="57950-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="57950-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="57950-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-160">Journal</span></span></th>
<th><span data-ttu-id="57950-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="57950-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="57950-163">Versione</span><span class="sxs-lookup"><span data-stu-id="57950-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-164">00001</span><span class="sxs-lookup"><span data-stu-id="57950-164">00001</span></span></td>
<td><span data-ttu-id="57950-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="57950-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-166">Fiscal</span></span></td>
<td><span data-ttu-id="57950-167">2017</span><span class="sxs-lookup"><span data-stu-id="57950-167">2017</span></span></td>
<td><span data-ttu-id="57950-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-168">Period 1</span></span></td>
<td><span data-ttu-id="57950-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="57950-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="57950-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="57950-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="57950-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-173">Cost element</span></span></th>
<th><span data-ttu-id="57950-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-174">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-175">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="57950-177">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-177">CC099</span></span></td>
<td><span data-ttu-id="57950-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-178">Default cost center</span></span></td>
<td><span data-ttu-id="57950-179">10001</span><span class="sxs-lookup"><span data-stu-id="57950-179">10001</span></span></td>
<td><span data-ttu-id="57950-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-180">Electricity</span></span></td>
<td><span data-ttu-id="57950-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="57950-181">Unclassified</span></span></td>
<td><span data-ttu-id="57950-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="57950-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="57950-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="57950-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-185">Cost element</span></span></th>
<th><span data-ttu-id="57950-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-186">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-187">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-187">Amount</span></span></th>
<th><span data-ttu-id="57950-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-189">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-189">CC099</span></span></td>
<td><span data-ttu-id="57950-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-190">Default cost center</span></span></td>
<td><span data-ttu-id="57950-191">10001</span><span class="sxs-lookup"><span data-stu-id="57950-191">10001</span></span></td>
<td><span data-ttu-id="57950-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-192">Electricity</span></span></td>
<td><span data-ttu-id="57950-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="57950-193">Unclassified</span></span></td>
<td><span data-ttu-id="57950-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-194">10,000.00</span></span></td>
<td><span data-ttu-id="57950-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-196">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-196">CC099</span></span></td>
<td><span data-ttu-id="57950-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-197">Default cost center</span></span></td>
<td><span data-ttu-id="57950-198">10001</span><span class="sxs-lookup"><span data-stu-id="57950-198">10001</span></span></td>
<td><span data-ttu-id="57950-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-199">Electricity</span></span></td>
<td><span data-ttu-id="57950-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="57950-200">Unclassified</span></span></td>
<td><span data-ttu-id="57950-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-201">-10,000.00</span></span></td>
<td><span data-ttu-id="57950-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-203">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-203">CC099</span></span></td>
<td><span data-ttu-id="57950-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-204">Default cost center</span></span></td>
<td><span data-ttu-id="57950-205">10001</span><span class="sxs-lookup"><span data-stu-id="57950-205">10001</span></span></td>
<td><span data-ttu-id="57950-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-206">Electricity</span></span></td>
<td><span data-ttu-id="57950-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-207">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-208">1,000.00</span></span></td>
<td><span data-ttu-id="57950-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-210">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-210">CC099</span></span></td>
<td><span data-ttu-id="57950-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-211">Default cost center</span></span></td>
<td><span data-ttu-id="57950-212">10001</span><span class="sxs-lookup"><span data-stu-id="57950-212">10001</span></span></td>
<td><span data-ttu-id="57950-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-213">Electricity</span></span></td>
<td><span data-ttu-id="57950-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-214">Variable cost</span></span></td>
<td><span data-ttu-id="57950-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-215">9,000.00</span></span></td>
<td><span data-ttu-id="57950-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-217">Per informazioni dettagliate sul comportamento costo, vedere Criteri di comportamento costo.</span><span class="sxs-lookup"><span data-stu-id="57950-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="57950-218">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="57950-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="57950-219">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="57950-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="57950-220">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="57950-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="57950-221">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="57950-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="57950-222">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="57950-222">Define the cost distribution rule</span></span>

<span data-ttu-id="57950-223">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="57950-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="57950-224">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="57950-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="57950-225">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="57950-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="57950-226">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="57950-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="57950-227">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="57950-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="57950-228">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="57950-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-229">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-229">Cost object</span></span></th>
<th><span data-ttu-id="57950-230">KWH</span><span class="sxs-lookup"><span data-stu-id="57950-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-231">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-231">CC001</span></span></td>
<td><span data-ttu-id="57950-232">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-232">HR</span></span></td>
<td><span data-ttu-id="57950-233">1.000</span><span class="sxs-lookup"><span data-stu-id="57950-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-234">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-234">CC002</span></span></td>
<td><span data-ttu-id="57950-235">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-235">Finance</span></span></td>
<td><span data-ttu-id="57950-236">6.000</span><span class="sxs-lookup"><span data-stu-id="57950-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-237">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-237">CC003</span></span></td>
<td><span data-ttu-id="57950-238">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-238">Assembly</span></span></td>
<td><span data-ttu-id="57950-239">0</span><span class="sxs-lookup"><span data-stu-id="57950-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-240">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="57950-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-241">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-241">Cost object</span></span></th>
<th><span data-ttu-id="57950-242">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-242">Magnitude</span></span></th>
<th><span data-ttu-id="57950-243">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="57950-243">Allocation factor</span></span></th>
<th><span data-ttu-id="57950-244">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-245">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-245">CC001</span></span></td>
<td><span data-ttu-id="57950-246">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-246">HR</span></span></td>
<td><span data-ttu-id="57950-247">1.000</span><span class="sxs-lookup"><span data-stu-id="57950-247">1,000</span></span></td>
<td><span data-ttu-id="57950-248">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="57950-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="57950-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-250">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-250">CC002</span></span></td>
<td><span data-ttu-id="57950-251">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-251">Finance</span></span></td>
<td><span data-ttu-id="57950-252">6.000</span><span class="sxs-lookup"><span data-stu-id="57950-252">6,000</span></span></td>
<td><span data-ttu-id="57950-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="57950-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="57950-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-255">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-255">CC003</span></span></td>
<td><span data-ttu-id="57950-256">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-256">Assembly</span></span></td>
<td><span data-ttu-id="57950-257">0</span><span class="sxs-lookup"><span data-stu-id="57950-257">0</span></span></td>
<td><span data-ttu-id="57950-258">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="57950-259">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-260">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="57950-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="57950-261">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="57950-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-262">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-262">Cost object</span></span></th>
<th><span data-ttu-id="57950-263">Formula</span><span class="sxs-lookup"><span data-stu-id="57950-263">Formula</span></span></th>
<th><span data-ttu-id="57950-264">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-264">Magnitude</span></span></th>
<th><span data-ttu-id="57950-265">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="57950-265">Allocation factor</span></span></th>
<th><span data-ttu-id="57950-266">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-267">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-267">CC001</span></span></td>
<td><span data-ttu-id="57950-268">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-268">HR</span></span></td>
<td><span data-ttu-id="57950-269">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="57950-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="57950-270">1</span><span class="sxs-lookup"><span data-stu-id="57950-270">1</span></span></td>
<td><span data-ttu-id="57950-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="57950-272">500,00</span><span class="sxs-lookup"><span data-stu-id="57950-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-273">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-273">CC002</span></span></td>
<td><span data-ttu-id="57950-274">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-274">Finance</span></span></td>
<td><span data-ttu-id="57950-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="57950-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="57950-276">1</span><span class="sxs-lookup"><span data-stu-id="57950-276">1</span></span></td>
<td><span data-ttu-id="57950-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="57950-278">500,00</span><span class="sxs-lookup"><span data-stu-id="57950-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-279">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-279">CC003</span></span></td>
<td><span data-ttu-id="57950-280">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-280">Assembly</span></span></td>
<td><span data-ttu-id="57950-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="57950-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="57950-282">0</span><span class="sxs-lookup"><span data-stu-id="57950-282">0</span></span></td>
<td><span data-ttu-id="57950-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="57950-284">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="57950-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-286">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-286">Journal</span></span></th>
<th><span data-ttu-id="57950-287">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="57950-288">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="57950-289">Versione</span><span class="sxs-lookup"><span data-stu-id="57950-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-290">00002</span><span class="sxs-lookup"><span data-stu-id="57950-290">00002</span></span></td>
<td><span data-ttu-id="57950-291">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="57950-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="57950-292">Fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-292">Fiscal</span></span></td>
<td><span data-ttu-id="57950-293">2017</span><span class="sxs-lookup"><span data-stu-id="57950-293">2017</span></span></td>
<td><span data-ttu-id="57950-294">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-294">Period 1</span></span></td>
<td><span data-ttu-id="57950-295">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="57950-296">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="57950-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-297">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="57950-298">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="57950-299">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-299">Cost element</span></span></th>
<th><span data-ttu-id="57950-300">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-300">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-301">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-302">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-303">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-303">CC099</span></span></td>
<td><span data-ttu-id="57950-304">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-304">Default cost center</span></span></td>
<td><span data-ttu-id="57950-305">10001</span><span class="sxs-lookup"><span data-stu-id="57950-305">10001</span></span></td>
<td><span data-ttu-id="57950-306">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-306">Electricity</span></span></td>
<td><span data-ttu-id="57950-307">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-307">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-309">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-310">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-310">CC099</span></span></td>
<td><span data-ttu-id="57950-311">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-311">Default cost center</span></span></td>
<td><span data-ttu-id="57950-312">10001</span><span class="sxs-lookup"><span data-stu-id="57950-312">10001</span></span></td>
<td><span data-ttu-id="57950-313">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-313">Electricity</span></span></td>
<td><span data-ttu-id="57950-314">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-314">Variable cost</span></span></td>
<td><span data-ttu-id="57950-315">9.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="57950-316">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="57950-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-317">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="57950-318">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-318">Cost element</span></span></th>
<th><span data-ttu-id="57950-319">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-319">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-320">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-320">Amount</span></span></th>
<th><span data-ttu-id="57950-321">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-322">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-322">CC099</span></span></td>
<td><span data-ttu-id="57950-323">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-323">Default cost center</span></span></td>
<td><span data-ttu-id="57950-324">10001</span><span class="sxs-lookup"><span data-stu-id="57950-324">10001</span></span></td>
<td><span data-ttu-id="57950-325">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-325">Electricity</span></span></td>
<td><span data-ttu-id="57950-326">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-326">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-327">-1,000.00</span></span></td>
<td><span data-ttu-id="57950-328">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-329">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-329">CC001</span></span></td>
<td><span data-ttu-id="57950-330">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-330">HR</span></span></td>
<td><span data-ttu-id="57950-331">10001</span><span class="sxs-lookup"><span data-stu-id="57950-331">10001</span></span></td>
<td><span data-ttu-id="57950-332">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-332">Electricity</span></span></td>
<td><span data-ttu-id="57950-333">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-333">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-334">500,00</span><span class="sxs-lookup"><span data-stu-id="57950-334">500.00</span></span></td>
<td><span data-ttu-id="57950-335">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-336">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-336">CC002</span></span></td>
<td><span data-ttu-id="57950-337">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-337">Finance</span></span></td>
<td><span data-ttu-id="57950-338">10001</span><span class="sxs-lookup"><span data-stu-id="57950-338">10001</span></span></td>
<td><span data-ttu-id="57950-339">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-339">Electricity</span></span></td>
<td><span data-ttu-id="57950-340">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-340">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-341">500,00</span><span class="sxs-lookup"><span data-stu-id="57950-341">500.00</span></span></td>
<td><span data-ttu-id="57950-342">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-343">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-343">CC099</span></span></td>
<td><span data-ttu-id="57950-344">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="57950-344">Default cost center</span></span></td>
<td><span data-ttu-id="57950-345">10001</span><span class="sxs-lookup"><span data-stu-id="57950-345">10001</span></span></td>
<td><span data-ttu-id="57950-346">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-346">Electricity</span></span></td>
<td><span data-ttu-id="57950-347">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-347">Variable cost</span></span></td>
<td><span data-ttu-id="57950-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="57950-348">-9,000.00</span></span></td>
<td><span data-ttu-id="57950-349">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-350">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-350">CC001</span></span></td>
<td><span data-ttu-id="57950-351">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-351">HR</span></span></td>
<td><span data-ttu-id="57950-352">10001</span><span class="sxs-lookup"><span data-stu-id="57950-352">10001</span></span></td>
<td><span data-ttu-id="57950-353">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-353">Electricity</span></span></td>
<td><span data-ttu-id="57950-354">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-354">Variable cost</span></span></td>
<td><span data-ttu-id="57950-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="57950-355">1,285.71</span></span></td>
<td><span data-ttu-id="57950-356">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-357">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-357">CC002</span></span></td>
<td><span data-ttu-id="57950-358">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-358">Finance</span></span></td>
<td><span data-ttu-id="57950-359">10001</span><span class="sxs-lookup"><span data-stu-id="57950-359">10001</span></span></td>
<td><span data-ttu-id="57950-360">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-360">Electricity</span></span></td>
<td><span data-ttu-id="57950-361">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-361">Variable cost</span></span></td>
<td><span data-ttu-id="57950-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="57950-362">7,714.29</span></span></td>
<td><span data-ttu-id="57950-363">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-364">Per informazioni dettagliate sulla base di allocazione e distribuzione costo, vedere Criteri di distribuzione costi e Basi di allocazione.</span><span class="sxs-lookup"><span data-stu-id="57950-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="57950-365">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="57950-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="57950-366">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="57950-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="57950-367">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="57950-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="57950-368">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="57950-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="57950-369">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="57950-369">Define the overhead rate</span></span>

<span data-ttu-id="57950-370">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="57950-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="57950-371">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="57950-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-372">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-372">Cost object</span></span></th>
<th><span data-ttu-id="57950-373">Ore</span><span class="sxs-lookup"><span data-stu-id="57950-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="57950-374">Proj 1</span></span></td>
<td><span data-ttu-id="57950-375">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="57950-375">Project 1</span></span></td>
<td><span data-ttu-id="57950-376">3</span><span class="sxs-lookup"><span data-stu-id="57950-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="57950-377">Proj 2</span></span></td>
<td><span data-ttu-id="57950-378">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="57950-378">Project 2</span></span></td>
<td><span data-ttu-id="57950-379">1</span><span class="sxs-lookup"><span data-stu-id="57950-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-380">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="57950-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-381">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-381">Cost object</span></span></th>
<th><span data-ttu-id="57950-382">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-382">Cost element</span></span></th>
<th><span data-ttu-id="57950-383">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-383">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-384">Unità</span><span class="sxs-lookup"><span data-stu-id="57950-384">Units</span></span></th>
<th><span data-ttu-id="57950-385">Tasso</span><span class="sxs-lookup"><span data-stu-id="57950-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-386">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-386">CC001</span></span></td>
<td><span data-ttu-id="57950-387">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-387">HR</span></span></td>
<td><span data-ttu-id="57950-388">10001</span><span class="sxs-lookup"><span data-stu-id="57950-388">10001</span></span></td>
<td><span data-ttu-id="57950-389">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-389">Variable cost</span></span></td>
<td><span data-ttu-id="57950-390">1</span><span class="sxs-lookup"><span data-stu-id="57950-390">1</span></span></td>
<td><span data-ttu-id="57950-391">10</span><span class="sxs-lookup"><span data-stu-id="57950-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-392">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="57950-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-393">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-393">Cost object</span></span></th>
<th><span data-ttu-id="57950-394">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-394">Magnitude</span></span></th>
<th><span data-ttu-id="57950-395">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-395">Cost element</span></span></th>
<th><span data-ttu-id="57950-396">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="57950-396">Allocation factor</span></span></th>
<th><span data-ttu-id="57950-397">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="57950-398">Proj 1</span></span></td>
<td><span data-ttu-id="57950-399">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="57950-399">Project 1</span></span></td>
<td><span data-ttu-id="57950-400">3</span><span class="sxs-lookup"><span data-stu-id="57950-400">3</span></span></td>
<td><span data-ttu-id="57950-401">10001</span><span class="sxs-lookup"><span data-stu-id="57950-401">10001</span></span></td>
<td><span data-ttu-id="57950-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="57950-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="57950-403">30,00</span><span class="sxs-lookup"><span data-stu-id="57950-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="57950-404">Proj 2</span></span></td>
<td><span data-ttu-id="57950-405">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="57950-405">Project 2</span></span></td>
<td><span data-ttu-id="57950-406">1</span><span class="sxs-lookup"><span data-stu-id="57950-406">1</span></span></td>
<td><span data-ttu-id="57950-407">10001</span><span class="sxs-lookup"><span data-stu-id="57950-407">10001</span></span></td>
<td><span data-ttu-id="57950-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="57950-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="57950-409">10,00</span><span class="sxs-lookup"><span data-stu-id="57950-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="57950-410">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-411">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-411">Journal</span></span></th>
<th><span data-ttu-id="57950-412">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="57950-413">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="57950-414">Versione</span><span class="sxs-lookup"><span data-stu-id="57950-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-415">00003</span><span class="sxs-lookup"><span data-stu-id="57950-415">00003</span></span></td>
<td><span data-ttu-id="57950-416">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="57950-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="57950-417">Fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-417">Fiscal</span></span></td>
<td><span data-ttu-id="57950-418">2017</span><span class="sxs-lookup"><span data-stu-id="57950-418">2017</span></span></td>
<td><span data-ttu-id="57950-419">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-419">Period 1</span></span></td>
<td><span data-ttu-id="57950-420">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="57950-421">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="57950-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-422">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="57950-423">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-423">Cost object</span></span></th>
<th><span data-ttu-id="57950-424">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-425">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="57950-426">Proj 1</span></span></td>
<td><span data-ttu-id="57950-427">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="57950-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="57950-428">3,00</span><span class="sxs-lookup"><span data-stu-id="57950-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-429">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="57950-430">Proj 2</span></span></td>
<td><span data-ttu-id="57950-431">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="57950-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="57950-432">1,00</span><span class="sxs-lookup"><span data-stu-id="57950-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="57950-433">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="57950-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-434">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="57950-435">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-435">Cost element</span></span></th>
<th><span data-ttu-id="57950-436">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-436">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-437">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-437">Amount</span></span></th>
<th><span data-ttu-id="57950-438">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="57950-439">CC0001</span></span></td>
<td><span data-ttu-id="57950-440">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-440">HR</span></span></td>
<td><span data-ttu-id="57950-441">10001</span><span class="sxs-lookup"><span data-stu-id="57950-441">10001</span></span></td>
<td><span data-ttu-id="57950-442">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-442">Electricity</span></span></td>
<td><span data-ttu-id="57950-443">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-443">Variable cost</span></span></td>
<td><span data-ttu-id="57950-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="57950-444">-30.00</span></span></td>
<td><span data-ttu-id="57950-445">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="57950-446">Proj 1</span></span></td>
<td><span data-ttu-id="57950-447">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="57950-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="57950-448">10001</span><span class="sxs-lookup"><span data-stu-id="57950-448">10001</span></span></td>
<td><span data-ttu-id="57950-449">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-449">Electricity</span></span></td>
<td><span data-ttu-id="57950-450">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-450">Variable cost</span></span></td>
<td><span data-ttu-id="57950-451">30,00</span><span class="sxs-lookup"><span data-stu-id="57950-451">30.00</span></span></td>
<td><span data-ttu-id="57950-452">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-453">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-453">CC001</span></span></td>
<td><span data-ttu-id="57950-454">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-454">HR</span></span></td>
<td><span data-ttu-id="57950-455">10001</span><span class="sxs-lookup"><span data-stu-id="57950-455">10001</span></span></td>
<td><span data-ttu-id="57950-456">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-456">Electricity</span></span></td>
<td><span data-ttu-id="57950-457">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-457">Variable cost</span></span></td>
<td><span data-ttu-id="57950-458">-10.00</span><span class="sxs-lookup"><span data-stu-id="57950-458">-10.00</span></span></td>
<td><span data-ttu-id="57950-459">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="57950-460">Proj 2</span></span></td>
<td><span data-ttu-id="57950-461">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="57950-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="57950-462">10001</span><span class="sxs-lookup"><span data-stu-id="57950-462">10001</span></span></td>
<td><span data-ttu-id="57950-463">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-463">Electricity</span></span></td>
<td><span data-ttu-id="57950-464">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-464">Variable cost</span></span></td>
<td><span data-ttu-id="57950-465">10,00</span><span class="sxs-lookup"><span data-stu-id="57950-465">10.00</span></span></td>
<td><span data-ttu-id="57950-466">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-467">Per informazioni dettagliate sui criteri di tasso generali, vedere Criterio di tasso generale e Basi di allocazione.</span><span class="sxs-lookup"><span data-stu-id="57950-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="57950-468">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="57950-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="57950-469">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="57950-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="57950-470">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="57950-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="57950-471">Finance and Operations supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="57950-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="57950-472">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="57950-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="57950-473">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="57950-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="57950-474">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="57950-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="57950-475">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="57950-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="57950-476">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="57950-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="57950-477">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="57950-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="57950-478">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="57950-478">Define the cost allocation</span></span>

<span data-ttu-id="57950-479">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="57950-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="57950-480">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="57950-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="57950-481">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="57950-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-482">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-482">Cost object</span></span></th>
<th><span data-ttu-id="57950-483">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="57950-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-484">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-484">CC002</span></span></td>
<td><span data-ttu-id="57950-485">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-485">Finance</span></span></td>
<td><span data-ttu-id="57950-486">35</span><span class="sxs-lookup"><span data-stu-id="57950-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-487">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-487">CC003</span></span></td>
<td><span data-ttu-id="57950-488">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-488">Assembly</span></span></td>
<td><span data-ttu-id="57950-489">55</span><span class="sxs-lookup"><span data-stu-id="57950-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-490">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-490">CC004</span></span></td>
<td><span data-ttu-id="57950-491">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-491">Packaging</span></span></td>
<td><span data-ttu-id="57950-492">10</span><span class="sxs-lookup"><span data-stu-id="57950-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-493">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="57950-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="57950-494">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="57950-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-495">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-495">Cost object</span></span></th>
<th><span data-ttu-id="57950-496">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-497">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-497">CC003</span></span></td>
<td><span data-ttu-id="57950-498">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-498">Assembly</span></span></td>
<td><span data-ttu-id="57950-499">65</span><span class="sxs-lookup"><span data-stu-id="57950-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-500">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-500">CC004</span></span></td>
<td><span data-ttu-id="57950-501">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-501">Packaging</span></span></td>
<td><span data-ttu-id="57950-502">35</span><span class="sxs-lookup"><span data-stu-id="57950-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-503">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="57950-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="57950-504">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="57950-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-505">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-505">Cost object</span></span></th>
<th><span data-ttu-id="57950-506">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="57950-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-507">Prod 1</span></span></td>
<td><span data-ttu-id="57950-508">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-508">Product 1</span></span></td>
<td><span data-ttu-id="57950-509">60</span><span class="sxs-lookup"><span data-stu-id="57950-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-510">Prod 2</span></span></td>
<td><span data-ttu-id="57950-511">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-511">Product 2</span></span></td>
<td><span data-ttu-id="57950-512">20</span><span class="sxs-lookup"><span data-stu-id="57950-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-513">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="57950-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="57950-514">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="57950-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-515">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-515">Cost object</span></span></th>
<th><span data-ttu-id="57950-516">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="57950-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-517">Prod 1</span></span></td>
<td><span data-ttu-id="57950-518">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-518">Product 1</span></span></td>
<td><span data-ttu-id="57950-519">80</span><span class="sxs-lookup"><span data-stu-id="57950-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-520">Prod 2</span></span></td>
<td><span data-ttu-id="57950-521">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-521">Product 2</span></span></td>
<td><span data-ttu-id="57950-522">15</span><span class="sxs-lookup"><span data-stu-id="57950-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-523">**Nota**: in Finance and Operations, le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="57950-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="57950-524">Per informazioni più dettagliate sui provider misure statistiche, vedere il modello provider misure statistiche.</span><span class="sxs-lookup"><span data-stu-id="57950-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="57950-525">(Nota: questo argomento non è ancora completo ma sarà presto disponibile). Nella tabella seguente viene illustrato il risultato ottenuto quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="57950-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-526">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-526">Cost object</span></span></th>
<th><span data-ttu-id="57950-527">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-527">Magnitude</span></span></th>
<th><span data-ttu-id="57950-528">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="57950-528">Allocation factor</span></span></th>
<th><span data-ttu-id="57950-529">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-529">Amount</span></span></th>
<th><span data-ttu-id="57950-530">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-531">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-531">CC002</span></span></td>
<td><span data-ttu-id="57950-532">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-532">Finance</span></span></td>
<td><span data-ttu-id="57950-533">35</span><span class="sxs-lookup"><span data-stu-id="57950-533">35</span></span></td>
<td><span data-ttu-id="57950-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="57950-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="57950-535">175.00</span><span class="sxs-lookup"><span data-stu-id="57950-535">175.00</span></span></td>
<td><span data-ttu-id="57950-536">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-537">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-537">CC003</span></span></td>
<td><span data-ttu-id="57950-538">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-538">Assembly</span></span></td>
<td><span data-ttu-id="57950-539">55</span><span class="sxs-lookup"><span data-stu-id="57950-539">55</span></span></td>
<td><span data-ttu-id="57950-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="57950-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="57950-541">275.00</span><span class="sxs-lookup"><span data-stu-id="57950-541">275.00</span></span></td>
<td><span data-ttu-id="57950-542">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-543">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-543">CC004</span></span></td>
<td><span data-ttu-id="57950-544">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-544">Packaging</span></span></td>
<td><span data-ttu-id="57950-545">10</span><span class="sxs-lookup"><span data-stu-id="57950-545">10</span></span></td>
<td><span data-ttu-id="57950-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="57950-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="57950-547">50,00</span><span class="sxs-lookup"><span data-stu-id="57950-547">50.00</span></span></td>
<td><span data-ttu-id="57950-548">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-549">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-549">CC002</span></span></td>
<td><span data-ttu-id="57950-550">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-550">Finance</span></span></td>
<td><span data-ttu-id="57950-551">35</span><span class="sxs-lookup"><span data-stu-id="57950-551">35</span></span></td>
<td><span data-ttu-id="57950-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="57950-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="57950-553">436.00</span><span class="sxs-lookup"><span data-stu-id="57950-553">436.00</span></span></td>
<td><span data-ttu-id="57950-554">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-555">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-555">CC003</span></span></td>
<td><span data-ttu-id="57950-556">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-556">Assembly</span></span></td>
<td><span data-ttu-id="57950-557">55</span><span class="sxs-lookup"><span data-stu-id="57950-557">55</span></span></td>
<td><span data-ttu-id="57950-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="57950-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="57950-559">685.14</span><span class="sxs-lookup"><span data-stu-id="57950-559">685.14</span></span></td>
<td><span data-ttu-id="57950-560">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-561">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-561">CC004</span></span></td>
<td><span data-ttu-id="57950-562">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-562">Packaging</span></span></td>
<td><span data-ttu-id="57950-563">10</span><span class="sxs-lookup"><span data-stu-id="57950-563">10</span></span></td>
<td><span data-ttu-id="57950-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="57950-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="57950-565">124.57</span><span class="sxs-lookup"><span data-stu-id="57950-565">124.57</span></span></td>
<td><span data-ttu-id="57950-566">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-567">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="57950-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-568">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-568">Cost object</span></span></th>
<th><span data-ttu-id="57950-569">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-569">Magnitude</span></span></th>
<th><span data-ttu-id="57950-570">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="57950-570">Allocation factor</span></span></th>
<th><span data-ttu-id="57950-571">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-571">Amount</span></span></th>
<th><span data-ttu-id="57950-572">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-573">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-573">CC003</span></span></td>
<td><span data-ttu-id="57950-574">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-574">Assembly</span></span></td>
<td><span data-ttu-id="57950-575">65</span><span class="sxs-lookup"><span data-stu-id="57950-575">65</span></span></td>
<td><span data-ttu-id="57950-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="57950-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="57950-577">438.75</span><span class="sxs-lookup"><span data-stu-id="57950-577">438.75</span></span></td>
<td><span data-ttu-id="57950-578">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-579">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-579">CC004</span></span></td>
<td><span data-ttu-id="57950-580">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-580">Packaging</span></span></td>
<td><span data-ttu-id="57950-581">35</span><span class="sxs-lookup"><span data-stu-id="57950-581">35</span></span></td>
<td><span data-ttu-id="57950-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="57950-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="57950-583">236.25</span><span class="sxs-lookup"><span data-stu-id="57950-583">236.25</span></span></td>
<td><span data-ttu-id="57950-584">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-585">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-585">CC003</span></span></td>
<td><span data-ttu-id="57950-586">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-586">Assembly</span></span></td>
<td><span data-ttu-id="57950-587">65</span><span class="sxs-lookup"><span data-stu-id="57950-587">65</span></span></td>
<td><span data-ttu-id="57950-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="57950-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="57950-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="57950-589">5,297.69</span></span></td>
<td><span data-ttu-id="57950-590">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-591">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-591">CC004</span></span></td>
<td><span data-ttu-id="57950-592">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-592">Packaging</span></span></td>
<td><span data-ttu-id="57950-593">35</span><span class="sxs-lookup"><span data-stu-id="57950-593">35</span></span></td>
<td><span data-ttu-id="57950-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="57950-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="57950-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="57950-595">2,852.60</span></span></td>
<td><span data-ttu-id="57950-596">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-597">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="57950-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-598">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-598">Cost object</span></span></th>
<th><span data-ttu-id="57950-599">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-599">Magnitude</span></span></th>
<th><span data-ttu-id="57950-600">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="57950-600">Allocation factor</span></span></th>
<th><span data-ttu-id="57950-601">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-601">Amount</span></span></th>
<th><span data-ttu-id="57950-602">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-603">Prod 1</span></span></td>
<td><span data-ttu-id="57950-604">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-604">Product 1</span></span></td>
<td><span data-ttu-id="57950-605">60</span><span class="sxs-lookup"><span data-stu-id="57950-605">60</span></span></td>
<td><span data-ttu-id="57950-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="57950-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="57950-607">535.31</span><span class="sxs-lookup"><span data-stu-id="57950-607">535.31</span></span></td>
<td><span data-ttu-id="57950-608">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-609">Prod 2</span></span></td>
<td><span data-ttu-id="57950-610">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-610">Product 2</span></span></td>
<td><span data-ttu-id="57950-611">20</span><span class="sxs-lookup"><span data-stu-id="57950-611">20</span></span></td>
<td><span data-ttu-id="57950-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="57950-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="57950-613">178.44</span><span class="sxs-lookup"><span data-stu-id="57950-613">178.44</span></span></td>
<td><span data-ttu-id="57950-614">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-615">Prod 1</span></span></td>
<td><span data-ttu-id="57950-616">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-616">Product 1</span></span></td>
<td><span data-ttu-id="57950-617">60</span><span class="sxs-lookup"><span data-stu-id="57950-617">60</span></span></td>
<td><span data-ttu-id="57950-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="57950-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="57950-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="57950-619">4,487.12</span></span></td>
<td><span data-ttu-id="57950-620">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-621">Prod 2</span></span></td>
<td><span data-ttu-id="57950-622">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-622">Product 2</span></span></td>
<td><span data-ttu-id="57950-623">20</span><span class="sxs-lookup"><span data-stu-id="57950-623">20</span></span></td>
<td><span data-ttu-id="57950-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="57950-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="57950-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="57950-625">1,495.71</span></span></td>
<td><span data-ttu-id="57950-626">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57950-627">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="57950-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-628">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-628">Cost object</span></span></th>
<th><span data-ttu-id="57950-629">Grandezza</span><span class="sxs-lookup"><span data-stu-id="57950-629">Magnitude</span></span></th>
<th><span data-ttu-id="57950-630">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="57950-630">Allocation factor</span></span></th>
<th><span data-ttu-id="57950-631">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-631">Amount</span></span></th>
<th><span data-ttu-id="57950-632">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-633">Prod 1</span></span></td>
<td><span data-ttu-id="57950-634">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-634">Product 1</span></span></td>
<td><span data-ttu-id="57950-635">80</span><span class="sxs-lookup"><span data-stu-id="57950-635">80</span></span></td>
<td><span data-ttu-id="57950-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="57950-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="57950-637">241.05</span><span class="sxs-lookup"><span data-stu-id="57950-637">241.05</span></span></td>
<td><span data-ttu-id="57950-638">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-639">Prod 2</span></span></td>
<td><span data-ttu-id="57950-640">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-640">Product 2</span></span></td>
<td><span data-ttu-id="57950-641">15</span><span class="sxs-lookup"><span data-stu-id="57950-641">15</span></span></td>
<td><span data-ttu-id="57950-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="57950-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="57950-643">45.20</span><span class="sxs-lookup"><span data-stu-id="57950-643">45.20</span></span></td>
<td><span data-ttu-id="57950-644">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-645">Prod 1</span></span></td>
<td><span data-ttu-id="57950-646">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-646">Product 1</span></span></td>
<td><span data-ttu-id="57950-647">80</span><span class="sxs-lookup"><span data-stu-id="57950-647">80</span></span></td>
<td><span data-ttu-id="57950-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="57950-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="57950-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="57950-649">2,507.09</span></span></td>
<td><span data-ttu-id="57950-650">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-651">Prod 2</span></span></td>
<td><span data-ttu-id="57950-652">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-652">Product 2</span></span></td>
<td><span data-ttu-id="57950-653">15</span><span class="sxs-lookup"><span data-stu-id="57950-653">15</span></span></td>
<td><span data-ttu-id="57950-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="57950-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="57950-655">470.08</span><span class="sxs-lookup"><span data-stu-id="57950-655">470.08</span></span></td>
<td><span data-ttu-id="57950-656">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="57950-657">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="57950-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-658">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-658">Journal</span></span></th>
<th><span data-ttu-id="57950-659">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="57950-660">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="57950-661">Versione</span><span class="sxs-lookup"><span data-stu-id="57950-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-662">00004</span><span class="sxs-lookup"><span data-stu-id="57950-662">00004</span></span></td>
<td><span data-ttu-id="57950-663">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="57950-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="57950-664">Fiscale</span><span class="sxs-lookup"><span data-stu-id="57950-664">Fiscal</span></span></td>
<td><span data-ttu-id="57950-665">2017</span><span class="sxs-lookup"><span data-stu-id="57950-665">2017</span></span></td>
<td><span data-ttu-id="57950-666">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-666">Period 1</span></span></td>
<td><span data-ttu-id="57950-667">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="57950-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="57950-668">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="57950-669">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="57950-670">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="57950-671">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-671">Cost element</span></span></th>
<th><span data-ttu-id="57950-672">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-672">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-673">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-674">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-675">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-675">CC001</span></span></td>
<td><span data-ttu-id="57950-676">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-676">HR</span></span></td>
<td><span data-ttu-id="57950-677">10001</span><span class="sxs-lookup"><span data-stu-id="57950-677">10001</span></span></td>
<td><span data-ttu-id="57950-678">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-678">Electricity</span></span></td>
<td><span data-ttu-id="57950-679">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-679">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-680">500,00</span><span class="sxs-lookup"><span data-stu-id="57950-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-681">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-682">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-682">CC001</span></span></td>
<td><span data-ttu-id="57950-683">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-683">HR</span></span></td>
<td><span data-ttu-id="57950-684">10001</span><span class="sxs-lookup"><span data-stu-id="57950-684">10001</span></span></td>
<td><span data-ttu-id="57950-685">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-685">Electricity</span></span></td>
<td><span data-ttu-id="57950-686">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-686">Variable cost</span></span></td>
<td><span data-ttu-id="57950-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="57950-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-688">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-689">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-689">CC002</span></span></td>
<td><span data-ttu-id="57950-690">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-690">Finance</span></span></td>
<td><span data-ttu-id="57950-691">10001</span><span class="sxs-lookup"><span data-stu-id="57950-691">10001</span></span></td>
<td><span data-ttu-id="57950-692">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-692">Electricity</span></span></td>
<td><span data-ttu-id="57950-693">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-693">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-694">675.00</span><span class="sxs-lookup"><span data-stu-id="57950-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-695">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-696">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-696">CC002</span></span></td>
<td><span data-ttu-id="57950-697">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-697">Finance</span></span></td>
<td><span data-ttu-id="57950-698">10001</span><span class="sxs-lookup"><span data-stu-id="57950-698">10001</span></span></td>
<td><span data-ttu-id="57950-699">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-699">Electricity</span></span></td>
<td><span data-ttu-id="57950-700">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-700">Variable cost</span></span></td>
<td><span data-ttu-id="57950-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="57950-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-702">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-703">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-703">CC003</span></span></td>
<td><span data-ttu-id="57950-704">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-704">Assembly</span></span></td>
<td><span data-ttu-id="57950-705">10001</span><span class="sxs-lookup"><span data-stu-id="57950-705">10001</span></span></td>
<td><span data-ttu-id="57950-706">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-706">Electricity</span></span></td>
<td><span data-ttu-id="57950-707">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-707">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-708">713.75</span><span class="sxs-lookup"><span data-stu-id="57950-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-709">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-710">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-710">CC003</span></span></td>
<td><span data-ttu-id="57950-711">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-711">Assembly</span></span></td>
<td><span data-ttu-id="57950-712">10001</span><span class="sxs-lookup"><span data-stu-id="57950-712">10001</span></span></td>
<td><span data-ttu-id="57950-713">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-713">Electricity</span></span></td>
<td><span data-ttu-id="57950-714">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-714">Variable cost</span></span></td>
<td><span data-ttu-id="57950-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="57950-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-716">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-717">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-717">CC003</span></span></td>
<td><span data-ttu-id="57950-718">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-718">Packaging</span></span></td>
<td><span data-ttu-id="57950-719">10001</span><span class="sxs-lookup"><span data-stu-id="57950-719">10001</span></span></td>
<td><span data-ttu-id="57950-720">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-720">Electricity</span></span></td>
<td><span data-ttu-id="57950-721">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-721">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-722">286.25</span><span class="sxs-lookup"><span data-stu-id="57950-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-723">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-724">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-724">CC003</span></span></td>
<td><span data-ttu-id="57950-725">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-725">Packaging</span></span></td>
<td><span data-ttu-id="57950-726">10001</span><span class="sxs-lookup"><span data-stu-id="57950-726">10001</span></span></td>
<td><span data-ttu-id="57950-727">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-727">Electricity</span></span></td>
<td><span data-ttu-id="57950-728">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-728">Variable cost</span></span></td>
<td><span data-ttu-id="57950-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="57950-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-730">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-731">Prod 1</span></span></td>
<td><span data-ttu-id="57950-732">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-732">Product 1</span></span></td>
<td><span data-ttu-id="57950-733">10001</span><span class="sxs-lookup"><span data-stu-id="57950-733">10001</span></span></td>
<td><span data-ttu-id="57950-734">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-734">Electricity</span></span></td>
<td><span data-ttu-id="57950-735">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-735">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-736">776.36</span><span class="sxs-lookup"><span data-stu-id="57950-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-737">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-738">Prod 1</span></span></td>
<td><span data-ttu-id="57950-739">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-739">Product 1</span></span></td>
<td><span data-ttu-id="57950-740">10001</span><span class="sxs-lookup"><span data-stu-id="57950-740">10001</span></span></td>
<td><span data-ttu-id="57950-741">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-741">Electricity</span></span></td>
<td><span data-ttu-id="57950-742">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-742">Variable cost</span></span></td>
<td><span data-ttu-id="57950-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="57950-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-744">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-745">Prod 2</span></span></td>
<td><span data-ttu-id="57950-746">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-746">Product 1</span></span></td>
<td><span data-ttu-id="57950-747">10001</span><span class="sxs-lookup"><span data-stu-id="57950-747">10001</span></span></td>
<td><span data-ttu-id="57950-748">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-748">Electricity</span></span></td>
<td><span data-ttu-id="57950-749">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-749">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-750">223.64</span><span class="sxs-lookup"><span data-stu-id="57950-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-751">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="57950-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-752">Prod 2</span></span></td>
<td><span data-ttu-id="57950-753">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-753">Product 1</span></span></td>
<td><span data-ttu-id="57950-754">10001</span><span class="sxs-lookup"><span data-stu-id="57950-754">10001</span></span></td>
<td><span data-ttu-id="57950-755">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-755">Electricity</span></span></td>
<td><span data-ttu-id="57950-756">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-756">Variable cost</span></span></td>
<td><span data-ttu-id="57950-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="57950-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="57950-758">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="57950-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="57950-759">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="57950-760">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-760">Cost element</span></span></th>
<th><span data-ttu-id="57950-761">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="57950-761">Cost behavior</span></span></th>
<th><span data-ttu-id="57950-762">Importo</span><span class="sxs-lookup"><span data-stu-id="57950-762">Amount</span></span></th>
<th><span data-ttu-id="57950-763">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="57950-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57950-764">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-764">CC001</span></span></td>
<td><span data-ttu-id="57950-765">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-765">HR</span></span></td>
<td><span data-ttu-id="57950-766">10001</span><span class="sxs-lookup"><span data-stu-id="57950-766">10001</span></span></td>
<td><span data-ttu-id="57950-767">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-767">Electricity</span></span></td>
<td><span data-ttu-id="57950-768">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-768">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="57950-769">-500.00</span></span></td>
<td><span data-ttu-id="57950-770">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-771">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-771">CC002</span></span></td>
<td><span data-ttu-id="57950-772">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-772">Finance</span></span></td>
<td><span data-ttu-id="57950-773">10001</span><span class="sxs-lookup"><span data-stu-id="57950-773">10001</span></span></td>
<td><span data-ttu-id="57950-774">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-774">Electricity</span></span></td>
<td><span data-ttu-id="57950-775">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-775">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-776">175.00</span><span class="sxs-lookup"><span data-stu-id="57950-776">175.00</span></span></td>
<td><span data-ttu-id="57950-777">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-778">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-778">CC003</span></span></td>
<td><span data-ttu-id="57950-779">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-779">Assembly</span></span></td>
<td><span data-ttu-id="57950-780">10001</span><span class="sxs-lookup"><span data-stu-id="57950-780">10001</span></span></td>
<td><span data-ttu-id="57950-781">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-781">Electricity</span></span></td>
<td><span data-ttu-id="57950-782">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-782">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-783">275.00</span><span class="sxs-lookup"><span data-stu-id="57950-783">275.00</span></span></td>
<td><span data-ttu-id="57950-784">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-785">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-785">CC004</span></span></td>
<td><span data-ttu-id="57950-786">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-786">Packaging</span></span></td>
<td><span data-ttu-id="57950-787">10001</span><span class="sxs-lookup"><span data-stu-id="57950-787">10001</span></span></td>
<td><span data-ttu-id="57950-788">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-788">Electricity</span></span></td>
<td><span data-ttu-id="57950-789">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-789">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-790">50,00</span><span class="sxs-lookup"><span data-stu-id="57950-790">50,00</span></span></td>
<td><span data-ttu-id="57950-791">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-792">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-792">CC001</span></span></td>
<td><span data-ttu-id="57950-793">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="57950-793">HR</span></span></td>
<td><span data-ttu-id="57950-794">10001</span><span class="sxs-lookup"><span data-stu-id="57950-794">10001</span></span></td>
<td><span data-ttu-id="57950-795">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-795">Electricity</span></span></td>
<td><span data-ttu-id="57950-796">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-796">Variable cost</span></span></td>
<td><span data-ttu-id="57950-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="57950-797">-1,245.71</span></span></td>
<td><span data-ttu-id="57950-798">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-799">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-799">CC002</span></span></td>
<td><span data-ttu-id="57950-800">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-800">Finance</span></span></td>
<td><span data-ttu-id="57950-801">10001</span><span class="sxs-lookup"><span data-stu-id="57950-801">10001</span></span></td>
<td><span data-ttu-id="57950-802">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-802">Electricity</span></span></td>
<td><span data-ttu-id="57950-803">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-803">Variable cost</span></span></td>
<td><span data-ttu-id="57950-804">436.00</span><span class="sxs-lookup"><span data-stu-id="57950-804">436.00</span></span></td>
<td><span data-ttu-id="57950-805">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-806">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-806">CC003</span></span></td>
<td><span data-ttu-id="57950-807">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-807">Assembly</span></span></td>
<td><span data-ttu-id="57950-808">10001</span><span class="sxs-lookup"><span data-stu-id="57950-808">10001</span></span></td>
<td><span data-ttu-id="57950-809">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-809">Electricity</span></span></td>
<td><span data-ttu-id="57950-810">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-810">Variable cost</span></span></td>
<td><span data-ttu-id="57950-811">685.14</span><span class="sxs-lookup"><span data-stu-id="57950-811">685.14</span></span></td>
<td><span data-ttu-id="57950-812">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-813">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-813">CC004</span></span></td>
<td><span data-ttu-id="57950-814">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-814">Packaging</span></span></td>
<td><span data-ttu-id="57950-815">10001</span><span class="sxs-lookup"><span data-stu-id="57950-815">10001</span></span></td>
<td><span data-ttu-id="57950-816">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-816">Electricity</span></span></td>
<td><span data-ttu-id="57950-817">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-817">Variable cost</span></span></td>
<td><span data-ttu-id="57950-818">124.57</span><span class="sxs-lookup"><span data-stu-id="57950-818">124.57</span></span></td>
<td><span data-ttu-id="57950-819">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-820">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-820">CC002</span></span></td>
<td><span data-ttu-id="57950-821">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-821">Finance</span></span></td>
<td><span data-ttu-id="57950-822">10001</span><span class="sxs-lookup"><span data-stu-id="57950-822">10001</span></span></td>
<td><span data-ttu-id="57950-823">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-823">Electricity</span></span></td>
<td><span data-ttu-id="57950-824">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-824">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="57950-825">-675.00</span></span></td>
<td><span data-ttu-id="57950-826">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-827">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-827">CC003</span></span></td>
<td><span data-ttu-id="57950-828">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-828">Assembly</span></span></td>
<td><span data-ttu-id="57950-829">10001</span><span class="sxs-lookup"><span data-stu-id="57950-829">10001</span></span></td>
<td><span data-ttu-id="57950-830">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-830">Electricity</span></span></td>
<td><span data-ttu-id="57950-831">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-831">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-832">438.75</span><span class="sxs-lookup"><span data-stu-id="57950-832">438.75</span></span></td>
<td><span data-ttu-id="57950-833">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-834">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-834">CC004</span></span></td>
<td><span data-ttu-id="57950-835">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-835">Packaging</span></span></td>
<td><span data-ttu-id="57950-836">10001</span><span class="sxs-lookup"><span data-stu-id="57950-836">10001</span></span></td>
<td><span data-ttu-id="57950-837">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-837">Electricity</span></span></td>
<td><span data-ttu-id="57950-838">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-838">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-839">236.25</span><span class="sxs-lookup"><span data-stu-id="57950-839">236.25</span></span></td>
<td><span data-ttu-id="57950-840">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-841">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-841">CC002</span></span></td>
<td><span data-ttu-id="57950-842">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="57950-842">Finance</span></span></td>
<td><span data-ttu-id="57950-843">10001</span><span class="sxs-lookup"><span data-stu-id="57950-843">10001</span></span></td>
<td><span data-ttu-id="57950-844">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-844">Electricity</span></span></td>
<td><span data-ttu-id="57950-845">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-845">Variable cost</span></span></td>
<td><span data-ttu-id="57950-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="57950-846">-8,150.29</span></span></td>
<td><span data-ttu-id="57950-847">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-848">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-848">CC003</span></span></td>
<td><span data-ttu-id="57950-849">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-849">Assembly</span></span></td>
<td><span data-ttu-id="57950-850">10001</span><span class="sxs-lookup"><span data-stu-id="57950-850">10001</span></span></td>
<td><span data-ttu-id="57950-851">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-851">Electricity</span></span></td>
<td><span data-ttu-id="57950-852">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-852">Variable cost</span></span></td>
<td><span data-ttu-id="57950-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="57950-853">5,297.69</span></span></td>
<td><span data-ttu-id="57950-854">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-855">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-855">CC004</span></span></td>
<td><span data-ttu-id="57950-856">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="57950-856">Packaging</span></span></td>
<td><span data-ttu-id="57950-857">10001</span><span class="sxs-lookup"><span data-stu-id="57950-857">10001</span></span></td>
<td><span data-ttu-id="57950-858">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-858">Electricity</span></span></td>
<td><span data-ttu-id="57950-859">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-859">Variable cost</span></span></td>
<td><span data-ttu-id="57950-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="57950-860">2,852.60</span></span></td>
<td><span data-ttu-id="57950-861">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-862">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-862">CC003</span></span></td>
<td><span data-ttu-id="57950-863">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-863">Assembly</span></span></td>
<td><span data-ttu-id="57950-864">10001</span><span class="sxs-lookup"><span data-stu-id="57950-864">10001</span></span></td>
<td><span data-ttu-id="57950-865">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-865">Electricity</span></span></td>
<td><span data-ttu-id="57950-866">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-866">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="57950-867">-713.75</span></span></td>
<td><span data-ttu-id="57950-868">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-869">Prod 1</span></span></td>
<td><span data-ttu-id="57950-870">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-870">Product 1</span></span></td>
<td><span data-ttu-id="57950-871">10001</span><span class="sxs-lookup"><span data-stu-id="57950-871">10001</span></span></td>
<td><span data-ttu-id="57950-872">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-872">Electricity</span></span></td>
<td><span data-ttu-id="57950-873">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-873">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-874">535.31</span><span class="sxs-lookup"><span data-stu-id="57950-874">535.31</span></span></td>
<td><span data-ttu-id="57950-875">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-876">Prod 2</span></span></td>
<td><span data-ttu-id="57950-877">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-877">Product 2</span></span></td>
<td><span data-ttu-id="57950-878">10001</span><span class="sxs-lookup"><span data-stu-id="57950-878">10001</span></span></td>
<td><span data-ttu-id="57950-879">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-879">Electricity</span></span></td>
<td><span data-ttu-id="57950-880">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-880">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-881">178.44</span><span class="sxs-lookup"><span data-stu-id="57950-881">178.44</span></span></td>
<td><span data-ttu-id="57950-882">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-883">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-883">CC003</span></span></td>
<td><span data-ttu-id="57950-884">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-884">Assembly</span></span></td>
<td><span data-ttu-id="57950-885">10001</span><span class="sxs-lookup"><span data-stu-id="57950-885">10001</span></span></td>
<td><span data-ttu-id="57950-886">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-886">Electricity</span></span></td>
<td><span data-ttu-id="57950-887">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-887">Variable cost</span></span></td>
<td><span data-ttu-id="57950-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="57950-888">-5,982.83</span></span></td>
<td><span data-ttu-id="57950-889">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-890">Prod 1</span></span></td>
<td><span data-ttu-id="57950-891">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-891">Product 1</span></span></td>
<td><span data-ttu-id="57950-892">10001</span><span class="sxs-lookup"><span data-stu-id="57950-892">10001</span></span></td>
<td><span data-ttu-id="57950-893">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-893">Electricity</span></span></td>
<td><span data-ttu-id="57950-894">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-894">Variable cost</span></span></td>
<td><span data-ttu-id="57950-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="57950-895">4,487.12</span></span></td>
<td><span data-ttu-id="57950-896">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-897">Prod 2</span></span></td>
<td><span data-ttu-id="57950-898">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-898">Product 2</span></span></td>
<td><span data-ttu-id="57950-899">10001</span><span class="sxs-lookup"><span data-stu-id="57950-899">10001</span></span></td>
<td><span data-ttu-id="57950-900">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-900">Electricity</span></span></td>
<td><span data-ttu-id="57950-901">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-901">Variable cost</span></span></td>
<td><span data-ttu-id="57950-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="57950-902">1,495.71</span></span></td>
<td><span data-ttu-id="57950-903">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-904">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-904">CC003</span></span></td>
<td><span data-ttu-id="57950-905">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-905">Assembly</span></span></td>
<td><span data-ttu-id="57950-906">10001</span><span class="sxs-lookup"><span data-stu-id="57950-906">10001</span></span></td>
<td><span data-ttu-id="57950-907">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-907">Electricity</span></span></td>
<td><span data-ttu-id="57950-908">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-908">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="57950-909">-286.25</span></span></td>
<td><span data-ttu-id="57950-910">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-911">Prod 1</span></span></td>
<td><span data-ttu-id="57950-912">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-912">Product 1</span></span></td>
<td><span data-ttu-id="57950-913">10001</span><span class="sxs-lookup"><span data-stu-id="57950-913">10001</span></span></td>
<td><span data-ttu-id="57950-914">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-914">Electricity</span></span></td>
<td><span data-ttu-id="57950-915">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-915">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-916">241.05</span><span class="sxs-lookup"><span data-stu-id="57950-916">241.05</span></span></td>
<td><span data-ttu-id="57950-917">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-918">Prod 2</span></span></td>
<td><span data-ttu-id="57950-919">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-919">Product 2</span></span></td>
<td><span data-ttu-id="57950-920">10001</span><span class="sxs-lookup"><span data-stu-id="57950-920">10001</span></span></td>
<td><span data-ttu-id="57950-921">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-921">Electricity</span></span></td>
<td><span data-ttu-id="57950-922">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-922">Fixed cost</span></span></td>
<td><span data-ttu-id="57950-923">45.20</span><span class="sxs-lookup"><span data-stu-id="57950-923">45.20</span></span></td>
<td><span data-ttu-id="57950-924">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-925">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-925">CC003</span></span></td>
<td><span data-ttu-id="57950-926">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="57950-926">Assembly</span></span></td>
<td><span data-ttu-id="57950-927">10001</span><span class="sxs-lookup"><span data-stu-id="57950-927">10001</span></span></td>
<td><span data-ttu-id="57950-928">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-928">Electricity</span></span></td>
<td><span data-ttu-id="57950-929">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-929">Variable cost</span></span></td>
<td><span data-ttu-id="57950-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="57950-930">-2,977.17</span></span></td>
<td><span data-ttu-id="57950-931">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-932">Prod 1</span></span></td>
<td><span data-ttu-id="57950-933">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="57950-933">Product 1</span></span></td>
<td><span data-ttu-id="57950-934">10001</span><span class="sxs-lookup"><span data-stu-id="57950-934">10001</span></span></td>
<td><span data-ttu-id="57950-935">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-935">Electricity</span></span></td>
<td><span data-ttu-id="57950-936">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-936">Variable cost</span></span></td>
<td><span data-ttu-id="57950-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="57950-937">2,507.09</span></span></td>
<td><span data-ttu-id="57950-938">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57950-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-939">Prod 2</span></span></td>
<td><span data-ttu-id="57950-940">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="57950-940">Product 2</span></span></td>
<td><span data-ttu-id="57950-941">10001</span><span class="sxs-lookup"><span data-stu-id="57950-941">10001</span></span></td>
<td><span data-ttu-id="57950-942">Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-942">Electricity</span></span></td>
<td><span data-ttu-id="57950-943">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-943">Variable cost</span></span></td>
<td><span data-ttu-id="57950-944">470.08</span><span class="sxs-lookup"><span data-stu-id="57950-944">470.08</span></span></td>
<td><span data-ttu-id="57950-945">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="57950-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="57950-946">Conclusione</span><span class="sxs-lookup"><span data-stu-id="57950-946">Conclusion</span></span>
<span data-ttu-id="57950-947">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="57950-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="57950-948">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="57950-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="57950-949">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="57950-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="57950-950">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="57950-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="57950-951">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="57950-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="57950-952">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="57950-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="57950-953">Totale</span><span class="sxs-lookup"><span data-stu-id="57950-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="57950-954">CC099</span><span class="sxs-lookup"><span data-stu-id="57950-954">CC099</span></span></th>
<th><span data-ttu-id="57950-955">CC001</span><span class="sxs-lookup"><span data-stu-id="57950-955">CC001</span></span></th>
<th><span data-ttu-id="57950-956">CC002</span><span class="sxs-lookup"><span data-stu-id="57950-956">CC002</span></span></th>
<th><span data-ttu-id="57950-957">CC003</span><span class="sxs-lookup"><span data-stu-id="57950-957">CC003</span></span></th>
<th><span data-ttu-id="57950-958">CC004</span><span class="sxs-lookup"><span data-stu-id="57950-958">CC004</span></span></th>
<th><span data-ttu-id="57950-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="57950-959">Proj 1</span></span></th>
<th><span data-ttu-id="57950-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="57950-960">Proj 2</span></span></th>
<th><span data-ttu-id="57950-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="57950-961">Prod 1</span></span></th>
<th><span data-ttu-id="57950-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="57950-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="57950-963">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="57950-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="57950-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="57950-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="57950-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="57950-973">Non classificato</span><span class="sxs-lookup"><span data-stu-id="57950-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-974">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="57950-975">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="57950-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-976">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-977">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-978">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-979">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-980">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="57950-981">776.36</span><span class="sxs-lookup"><span data-stu-id="57950-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-982">223.64</span><span class="sxs-lookup"><span data-stu-id="57950-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="57950-984">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="57950-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-985">000</span><span class="sxs-lookup"><span data-stu-id="57950-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-986">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-987">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-988">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-989">0,00</span><span class="sxs-lookup"><span data-stu-id="57950-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-990">30,00</span><span class="sxs-lookup"><span data-stu-id="57950-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-991">10,00</span><span class="sxs-lookup"><span data-stu-id="57950-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="57950-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="57950-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="57950-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="57950-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="57950-995">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="57950-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="57950-996">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="57950-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="57950-997">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="57950-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="57950-998">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="57950-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="57950-999">Per ulteriori informazioni, vedere i Criteri di rollup del costo.</span><span class="sxs-lookup"><span data-stu-id="57950-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="57950-1000">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="57950-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




