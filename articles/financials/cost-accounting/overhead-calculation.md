---
title: Calcolo generale
description: In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 12ae99c15bafcd9cc08b30903fe3f251f446b17d
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="b13dd-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="b13dd-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b13dd-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="b13dd-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="b13dd-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="b13dd-105">Term definition</span></span>
---------------

<span data-ttu-id="b13dd-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="b13dd-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="b13dd-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="b13dd-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="b13dd-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="b13dd-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="b13dd-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="b13dd-109">Rent</span></span>
-   <span data-ttu-id="b13dd-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-110">Electricity</span></span>
-   <span data-ttu-id="b13dd-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="b13dd-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="b13dd-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="b13dd-112">Overhead calculation overview</span></span>
<span data-ttu-id="b13dd-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="b13dd-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="b13dd-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="b13dd-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="b13dd-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="b13dd-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="b13dd-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="b13dd-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="b13dd-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="b13dd-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="b13dd-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="b13dd-119">Version type</span></span>
-   <span data-ttu-id="b13dd-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="b13dd-120">Date and time</span></span>
-   <span data-ttu-id="b13dd-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="b13dd-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="b13dd-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-122">Fiscal year</span></span>
-   <span data-ttu-id="b13dd-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-123">Fiscal period</span></span>

<span data-ttu-id="b13dd-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="b13dd-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="b13dd-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="b13dd-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="b13dd-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="b13dd-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="b13dd-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="b13dd-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="b13dd-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="b13dd-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="b13dd-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="b13dd-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="b13dd-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="b13dd-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="b13dd-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="b13dd-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="b13dd-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="b13dd-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="b13dd-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="b13dd-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="b13dd-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="b13dd-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="b13dd-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="b13dd-140">Main account</span></span></th>
<th><span data-ttu-id="b13dd-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="b13dd-143">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-143">CC099</span></span></td>
<td><span data-ttu-id="b13dd-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-144">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-145">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-145">10001</span></span></td>
<td><span data-ttu-id="b13dd-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-146">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="b13dd-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="b13dd-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="b13dd-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="b13dd-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="b13dd-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="b13dd-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-151">Define the cost behavior rule</span></span>

<span data-ttu-id="b13dd-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="b13dd-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="b13dd-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="b13dd-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="b13dd-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="b13dd-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="b13dd-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="b13dd-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="b13dd-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="b13dd-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-160">Journal</span></span></th>
<th><span data-ttu-id="b13dd-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="b13dd-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="b13dd-163">Versione</span><span class="sxs-lookup"><span data-stu-id="b13dd-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-164">00001</span><span class="sxs-lookup"><span data-stu-id="b13dd-164">00001</span></span></td>
<td><span data-ttu-id="b13dd-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="b13dd-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-166">Fiscal</span></span></td>
<td><span data-ttu-id="b13dd-167">2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-167">2017</span></span></td>
<td><span data-ttu-id="b13dd-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-168">Period 1</span></span></td>
<td><span data-ttu-id="b13dd-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="b13dd-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="b13dd-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-173">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-174">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-175">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="b13dd-177">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-177">CC099</span></span></td>
<td><span data-ttu-id="b13dd-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-178">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-179">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-179">10001</span></span></td>
<td><span data-ttu-id="b13dd-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-180">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="b13dd-181">Unclassified</span></span></td>
<td><span data-ttu-id="b13dd-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="b13dd-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-185">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-186">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-187">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-187">Amount</span></span></th>
<th><span data-ttu-id="b13dd-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-189">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-189">CC099</span></span></td>
<td><span data-ttu-id="b13dd-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-190">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-191">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-191">10001</span></span></td>
<td><span data-ttu-id="b13dd-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-192">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="b13dd-193">Unclassified</span></span></td>
<td><span data-ttu-id="b13dd-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-194">10,000.00</span></span></td>
<td><span data-ttu-id="b13dd-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-196">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-196">CC099</span></span></td>
<td><span data-ttu-id="b13dd-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-197">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-198">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-198">10001</span></span></td>
<td><span data-ttu-id="b13dd-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-199">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="b13dd-200">Unclassified</span></span></td>
<td><span data-ttu-id="b13dd-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-201">-10,000.00</span></span></td>
<td><span data-ttu-id="b13dd-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-203">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-203">CC099</span></span></td>
<td><span data-ttu-id="b13dd-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-204">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-205">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-205">10001</span></span></td>
<td><span data-ttu-id="b13dd-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-206">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-207">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-208">1,000.00</span></span></td>
<td><span data-ttu-id="b13dd-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-210">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-210">CC099</span></span></td>
<td><span data-ttu-id="b13dd-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-211">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-212">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-212">10001</span></span></td>
<td><span data-ttu-id="b13dd-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-213">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-214">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-215">9,000.00</span></span></td>
<td><span data-ttu-id="b13dd-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="b13dd-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="b13dd-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="b13dd-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="b13dd-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="b13dd-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="b13dd-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="b13dd-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-221">Define the cost distribution rule</span></span>

<span data-ttu-id="b13dd-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="b13dd-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="b13dd-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="b13dd-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="b13dd-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="b13dd-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="b13dd-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="b13dd-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="b13dd-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="b13dd-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="b13dd-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-228">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-229">KWH</span><span class="sxs-lookup"><span data-stu-id="b13dd-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-230">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-230">CC001</span></span></td>
<td><span data-ttu-id="b13dd-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-231">HR</span></span></td>
<td><span data-ttu-id="b13dd-232">1.000</span><span class="sxs-lookup"><span data-stu-id="b13dd-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-233">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-233">CC002</span></span></td>
<td><span data-ttu-id="b13dd-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-234">Finance</span></span></td>
<td><span data-ttu-id="b13dd-235">6.000</span><span class="sxs-lookup"><span data-stu-id="b13dd-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-236">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-236">CC003</span></span></td>
<td><span data-ttu-id="b13dd-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-237">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-238">0</span><span class="sxs-lookup"><span data-stu-id="b13dd-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="b13dd-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-240">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-241">Magnitude</span></span></th>
<th><span data-ttu-id="b13dd-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-242">Allocation factor</span></span></th>
<th><span data-ttu-id="b13dd-243">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-244">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-244">CC001</span></span></td>
<td><span data-ttu-id="b13dd-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-245">HR</span></span></td>
<td><span data-ttu-id="b13dd-246">1.000</span><span class="sxs-lookup"><span data-stu-id="b13dd-246">1,000</span></span></td>
<td><span data-ttu-id="b13dd-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="b13dd-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="b13dd-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-249">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-249">CC002</span></span></td>
<td><span data-ttu-id="b13dd-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-250">Finance</span></span></td>
<td><span data-ttu-id="b13dd-251">6.000</span><span class="sxs-lookup"><span data-stu-id="b13dd-251">6,000</span></span></td>
<td><span data-ttu-id="b13dd-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="b13dd-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="b13dd-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-254">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-254">CC003</span></span></td>
<td><span data-ttu-id="b13dd-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-255">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-256">0</span><span class="sxs-lookup"><span data-stu-id="b13dd-256">0</span></span></td>
<td><span data-ttu-id="b13dd-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="b13dd-258">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="b13dd-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="b13dd-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="b13dd-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-261">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-262">Formula</span><span class="sxs-lookup"><span data-stu-id="b13dd-262">Formula</span></span></th>
<th><span data-ttu-id="b13dd-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-263">Magnitude</span></span></th>
<th><span data-ttu-id="b13dd-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-264">Allocation factor</span></span></th>
<th><span data-ttu-id="b13dd-265">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-266">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-266">CC001</span></span></td>
<td><span data-ttu-id="b13dd-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-267">HR</span></span></td>
<td><span data-ttu-id="b13dd-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="b13dd-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="b13dd-269">1</span><span class="sxs-lookup"><span data-stu-id="b13dd-269">1</span></span></td>
<td><span data-ttu-id="b13dd-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="b13dd-271">500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-272">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-272">CC002</span></span></td>
<td><span data-ttu-id="b13dd-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-273">Finance</span></span></td>
<td><span data-ttu-id="b13dd-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="b13dd-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="b13dd-275">1</span><span class="sxs-lookup"><span data-stu-id="b13dd-275">1</span></span></td>
<td><span data-ttu-id="b13dd-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="b13dd-277">500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-278">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-278">CC003</span></span></td>
<td><span data-ttu-id="b13dd-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-279">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="b13dd-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="b13dd-281">0</span><span class="sxs-lookup"><span data-stu-id="b13dd-281">0</span></span></td>
<td><span data-ttu-id="b13dd-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="b13dd-283">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="b13dd-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-285">Journal</span></span></th>
<th><span data-ttu-id="b13dd-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="b13dd-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="b13dd-288">Versione</span><span class="sxs-lookup"><span data-stu-id="b13dd-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-289">00002</span><span class="sxs-lookup"><span data-stu-id="b13dd-289">00002</span></span></td>
<td><span data-ttu-id="b13dd-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="b13dd-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-291">Fiscal</span></span></td>
<td><span data-ttu-id="b13dd-292">2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-292">2017</span></span></td>
<td><span data-ttu-id="b13dd-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-293">Period 1</span></span></td>
<td><span data-ttu-id="b13dd-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="b13dd-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="b13dd-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-298">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-299">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-300">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-302">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-302">CC099</span></span></td>
<td><span data-ttu-id="b13dd-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-303">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-304">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-304">10001</span></span></td>
<td><span data-ttu-id="b13dd-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-305">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-306">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-309">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-309">CC099</span></span></td>
<td><span data-ttu-id="b13dd-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-310">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-311">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-311">10001</span></span></td>
<td><span data-ttu-id="b13dd-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-312">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-313">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="b13dd-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-317">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-318">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-319">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-319">Amount</span></span></th>
<th><span data-ttu-id="b13dd-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-321">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-321">CC099</span></span></td>
<td><span data-ttu-id="b13dd-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-322">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-323">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-323">10001</span></span></td>
<td><span data-ttu-id="b13dd-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-324">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-325">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-326">-1,000.00</span></span></td>
<td><span data-ttu-id="b13dd-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-328">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-328">CC001</span></span></td>
<td><span data-ttu-id="b13dd-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-329">HR</span></span></td>
<td><span data-ttu-id="b13dd-330">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-330">10001</span></span></td>
<td><span data-ttu-id="b13dd-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-331">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-332">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-333">500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-333">500.00</span></span></td>
<td><span data-ttu-id="b13dd-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-335">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-335">CC002</span></span></td>
<td><span data-ttu-id="b13dd-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-336">Finance</span></span></td>
<td><span data-ttu-id="b13dd-337">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-337">10001</span></span></td>
<td><span data-ttu-id="b13dd-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-338">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-339">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-340">500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-340">500.00</span></span></td>
<td><span data-ttu-id="b13dd-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-342">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-342">CC099</span></span></td>
<td><span data-ttu-id="b13dd-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="b13dd-343">Default cost center</span></span></td>
<td><span data-ttu-id="b13dd-344">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-344">10001</span></span></td>
<td><span data-ttu-id="b13dd-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-345">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-346">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-347">-9,000.00</span></span></td>
<td><span data-ttu-id="b13dd-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-349">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-349">CC001</span></span></td>
<td><span data-ttu-id="b13dd-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-350">HR</span></span></td>
<td><span data-ttu-id="b13dd-351">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-351">10001</span></span></td>
<td><span data-ttu-id="b13dd-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-352">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-353">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="b13dd-354">1,285.71</span></span></td>
<td><span data-ttu-id="b13dd-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-356">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-356">CC002</span></span></td>
<td><span data-ttu-id="b13dd-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-357">Finance</span></span></td>
<td><span data-ttu-id="b13dd-358">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-358">10001</span></span></td>
<td><span data-ttu-id="b13dd-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-359">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-360">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="b13dd-361">7,714.29</span></span></td>
<td><span data-ttu-id="b13dd-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="b13dd-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="b13dd-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="b13dd-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="b13dd-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="b13dd-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="b13dd-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="b13dd-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="b13dd-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="b13dd-367">Define the overhead rate</span></span>

<span data-ttu-id="b13dd-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="b13dd-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="b13dd-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="b13dd-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-370">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-371">Ore</span><span class="sxs-lookup"><span data-stu-id="b13dd-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-372">Proj 1</span></span></td>
<td><span data-ttu-id="b13dd-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-373">Project 1</span></span></td>
<td><span data-ttu-id="b13dd-374">3</span><span class="sxs-lookup"><span data-stu-id="b13dd-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-375">Proj 2</span></span></td>
<td><span data-ttu-id="b13dd-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-376">Project 2</span></span></td>
<td><span data-ttu-id="b13dd-377">1</span><span class="sxs-lookup"><span data-stu-id="b13dd-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="b13dd-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-379">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-380">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-381">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-382">Unità</span><span class="sxs-lookup"><span data-stu-id="b13dd-382">Units</span></span></th>
<th><span data-ttu-id="b13dd-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="b13dd-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-384">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-384">CC001</span></span></td>
<td><span data-ttu-id="b13dd-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-385">HR</span></span></td>
<td><span data-ttu-id="b13dd-386">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-386">10001</span></span></td>
<td><span data-ttu-id="b13dd-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-387">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-388">1</span><span class="sxs-lookup"><span data-stu-id="b13dd-388">1</span></span></td>
<td><span data-ttu-id="b13dd-389">10</span><span class="sxs-lookup"><span data-stu-id="b13dd-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-391">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-392">Magnitude</span></span></th>
<th><span data-ttu-id="b13dd-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-393">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-394">Allocation factor</span></span></th>
<th><span data-ttu-id="b13dd-395">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-396">Proj 1</span></span></td>
<td><span data-ttu-id="b13dd-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-397">Project 1</span></span></td>
<td><span data-ttu-id="b13dd-398">3</span><span class="sxs-lookup"><span data-stu-id="b13dd-398">3</span></span></td>
<td><span data-ttu-id="b13dd-399">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-399">10001</span></span></td>
<td><span data-ttu-id="b13dd-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="b13dd-401">30,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-402">Proj 2</span></span></td>
<td><span data-ttu-id="b13dd-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-403">Project 2</span></span></td>
<td><span data-ttu-id="b13dd-404">1</span><span class="sxs-lookup"><span data-stu-id="b13dd-404">1</span></span></td>
<td><span data-ttu-id="b13dd-405">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-405">10001</span></span></td>
<td><span data-ttu-id="b13dd-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="b13dd-407">10,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="b13dd-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-409">Journal</span></span></th>
<th><span data-ttu-id="b13dd-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="b13dd-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="b13dd-412">Versione</span><span class="sxs-lookup"><span data-stu-id="b13dd-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-413">00003</span><span class="sxs-lookup"><span data-stu-id="b13dd-413">00003</span></span></td>
<td><span data-ttu-id="b13dd-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="b13dd-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="b13dd-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-415">Fiscal</span></span></td>
<td><span data-ttu-id="b13dd-416">2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-416">2017</span></span></td>
<td><span data-ttu-id="b13dd-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-417">Period 1</span></span></td>
<td><span data-ttu-id="b13dd-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="b13dd-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="b13dd-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-421">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-424">Proj 1</span></span></td>
<td><span data-ttu-id="b13dd-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="b13dd-426">3,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-428">Proj 2</span></span></td>
<td><span data-ttu-id="b13dd-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="b13dd-430">1,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="b13dd-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-433">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-434">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-435">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-435">Amount</span></span></th>
<th><span data-ttu-id="b13dd-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="b13dd-437">CC0001</span></span></td>
<td><span data-ttu-id="b13dd-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-438">HR</span></span></td>
<td><span data-ttu-id="b13dd-439">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-439">10001</span></span></td>
<td><span data-ttu-id="b13dd-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-440">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-441">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-442">-30.00</span></span></td>
<td><span data-ttu-id="b13dd-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-444">Proj 1</span></span></td>
<td><span data-ttu-id="b13dd-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="b13dd-446">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-446">10001</span></span></td>
<td><span data-ttu-id="b13dd-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-447">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-448">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-449">30,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-449">30.00</span></span></td>
<td><span data-ttu-id="b13dd-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-451">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-451">CC001</span></span></td>
<td><span data-ttu-id="b13dd-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-452">HR</span></span></td>
<td><span data-ttu-id="b13dd-453">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-453">10001</span></span></td>
<td><span data-ttu-id="b13dd-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-454">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-455">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-456">-10.00</span></span></td>
<td><span data-ttu-id="b13dd-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-458">Proj 2</span></span></td>
<td><span data-ttu-id="b13dd-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="b13dd-460">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-460">10001</span></span></td>
<td><span data-ttu-id="b13dd-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-461">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-462">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-463">10.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-463">10.00</span></span></td>
<td><span data-ttu-id="b13dd-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="b13dd-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="b13dd-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="b13dd-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="b13dd-468">Finance and Operations supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="b13dd-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="b13dd-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="b13dd-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="b13dd-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="b13dd-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="b13dd-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="b13dd-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="b13dd-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="b13dd-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="b13dd-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="b13dd-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="b13dd-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="b13dd-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="b13dd-475">Define the cost allocation</span></span>

<span data-ttu-id="b13dd-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="b13dd-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="b13dd-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="b13dd-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-479">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="b13dd-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-481">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-481">CC002</span></span></td>
<td><span data-ttu-id="b13dd-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-482">Finance</span></span></td>
<td><span data-ttu-id="b13dd-483">35</span><span class="sxs-lookup"><span data-stu-id="b13dd-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-484">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-484">CC003</span></span></td>
<td><span data-ttu-id="b13dd-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-485">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-486">55</span><span class="sxs-lookup"><span data-stu-id="b13dd-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-487">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-487">CC004</span></span></td>
<td><span data-ttu-id="b13dd-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-488">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-489">10</span><span class="sxs-lookup"><span data-stu-id="b13dd-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="b13dd-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="b13dd-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-492">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-494">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-494">CC003</span></span></td>
<td><span data-ttu-id="b13dd-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-495">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-496">65</span><span class="sxs-lookup"><span data-stu-id="b13dd-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-497">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-497">CC004</span></span></td>
<td><span data-ttu-id="b13dd-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-498">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-499">35</span><span class="sxs-lookup"><span data-stu-id="b13dd-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="b13dd-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="b13dd-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-502">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="b13dd-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-504">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-505">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-506">60</span><span class="sxs-lookup"><span data-stu-id="b13dd-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-507">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-508">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-509">20</span><span class="sxs-lookup"><span data-stu-id="b13dd-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="b13dd-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="b13dd-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-512">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="b13dd-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-514">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-515">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-516">80</span><span class="sxs-lookup"><span data-stu-id="b13dd-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-517">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-518">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-519">15</span><span class="sxs-lookup"><span data-stu-id="b13dd-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="b13dd-520">In Finance and Operations, le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="b13dd-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="b13dd-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="b13dd-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="b13dd-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="b13dd-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-523">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-524">Magnitude</span></span></th>
<th><span data-ttu-id="b13dd-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-525">Allocation factor</span></span></th>
<th><span data-ttu-id="b13dd-526">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-526">Amount</span></span></th>
<th><span data-ttu-id="b13dd-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-528">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-528">CC002</span></span></td>
<td><span data-ttu-id="b13dd-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-529">Finance</span></span></td>
<td><span data-ttu-id="b13dd-530">35</span><span class="sxs-lookup"><span data-stu-id="b13dd-530">35</span></span></td>
<td><span data-ttu-id="b13dd-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="b13dd-532">175.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-532">175.00</span></span></td>
<td><span data-ttu-id="b13dd-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-534">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-534">CC003</span></span></td>
<td><span data-ttu-id="b13dd-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-535">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-536">55</span><span class="sxs-lookup"><span data-stu-id="b13dd-536">55</span></span></td>
<td><span data-ttu-id="b13dd-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="b13dd-538">275.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-538">275.00</span></span></td>
<td><span data-ttu-id="b13dd-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-540">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-540">CC004</span></span></td>
<td><span data-ttu-id="b13dd-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-541">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-542">10</span><span class="sxs-lookup"><span data-stu-id="b13dd-542">10</span></span></td>
<td><span data-ttu-id="b13dd-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="b13dd-544">50,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-544">50.00</span></span></td>
<td><span data-ttu-id="b13dd-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-546">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-546">CC002</span></span></td>
<td><span data-ttu-id="b13dd-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-547">Finance</span></span></td>
<td><span data-ttu-id="b13dd-548">35</span><span class="sxs-lookup"><span data-stu-id="b13dd-548">35</span></span></td>
<td><span data-ttu-id="b13dd-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="b13dd-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="b13dd-550">436.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-550">436.00</span></span></td>
<td><span data-ttu-id="b13dd-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-552">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-552">CC003</span></span></td>
<td><span data-ttu-id="b13dd-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-553">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-554">55</span><span class="sxs-lookup"><span data-stu-id="b13dd-554">55</span></span></td>
<td><span data-ttu-id="b13dd-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="b13dd-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="b13dd-556">685.14</span><span class="sxs-lookup"><span data-stu-id="b13dd-556">685.14</span></span></td>
<td><span data-ttu-id="b13dd-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-558">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-558">CC004</span></span></td>
<td><span data-ttu-id="b13dd-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-559">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-560">10</span><span class="sxs-lookup"><span data-stu-id="b13dd-560">10</span></span></td>
<td><span data-ttu-id="b13dd-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="b13dd-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="b13dd-562">124.57</span><span class="sxs-lookup"><span data-stu-id="b13dd-562">124.57</span></span></td>
<td><span data-ttu-id="b13dd-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="b13dd-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-565">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-566">Magnitude</span></span></th>
<th><span data-ttu-id="b13dd-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-567">Allocation factor</span></span></th>
<th><span data-ttu-id="b13dd-568">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-568">Amount</span></span></th>
<th><span data-ttu-id="b13dd-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-570">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-570">CC003</span></span></td>
<td><span data-ttu-id="b13dd-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-571">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-572">65</span><span class="sxs-lookup"><span data-stu-id="b13dd-572">65</span></span></td>
<td><span data-ttu-id="b13dd-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="b13dd-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="b13dd-574">438.75</span><span class="sxs-lookup"><span data-stu-id="b13dd-574">438.75</span></span></td>
<td><span data-ttu-id="b13dd-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-576">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-576">CC004</span></span></td>
<td><span data-ttu-id="b13dd-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-577">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-578">35</span><span class="sxs-lookup"><span data-stu-id="b13dd-578">35</span></span></td>
<td><span data-ttu-id="b13dd-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="b13dd-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="b13dd-580">236.25</span><span class="sxs-lookup"><span data-stu-id="b13dd-580">236.25</span></span></td>
<td><span data-ttu-id="b13dd-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-582">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-582">CC003</span></span></td>
<td><span data-ttu-id="b13dd-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-583">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-584">65</span><span class="sxs-lookup"><span data-stu-id="b13dd-584">65</span></span></td>
<td><span data-ttu-id="b13dd-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="b13dd-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="b13dd-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="b13dd-586">5,297.69</span></span></td>
<td><span data-ttu-id="b13dd-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-588">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-588">CC004</span></span></td>
<td><span data-ttu-id="b13dd-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-589">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-590">35</span><span class="sxs-lookup"><span data-stu-id="b13dd-590">35</span></span></td>
<td><span data-ttu-id="b13dd-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="b13dd-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="b13dd-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="b13dd-592">2,852.60</span></span></td>
<td><span data-ttu-id="b13dd-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="b13dd-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-595">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-596">Magnitude</span></span></th>
<th><span data-ttu-id="b13dd-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-597">Allocation factor</span></span></th>
<th><span data-ttu-id="b13dd-598">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-598">Amount</span></span></th>
<th><span data-ttu-id="b13dd-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-600">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-601">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-602">60</span><span class="sxs-lookup"><span data-stu-id="b13dd-602">60</span></span></td>
<td><span data-ttu-id="b13dd-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="b13dd-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="b13dd-604">535.31</span><span class="sxs-lookup"><span data-stu-id="b13dd-604">535.31</span></span></td>
<td><span data-ttu-id="b13dd-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-606">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-607">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-608">20</span><span class="sxs-lookup"><span data-stu-id="b13dd-608">20</span></span></td>
<td><span data-ttu-id="b13dd-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="b13dd-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="b13dd-610">178.44</span><span class="sxs-lookup"><span data-stu-id="b13dd-610">178.44</span></span></td>
<td><span data-ttu-id="b13dd-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-612">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-613">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-614">60</span><span class="sxs-lookup"><span data-stu-id="b13dd-614">60</span></span></td>
<td><span data-ttu-id="b13dd-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="b13dd-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="b13dd-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="b13dd-616">4,487.12</span></span></td>
<td><span data-ttu-id="b13dd-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-618">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-619">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-620">20</span><span class="sxs-lookup"><span data-stu-id="b13dd-620">20</span></span></td>
<td><span data-ttu-id="b13dd-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="b13dd-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="b13dd-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="b13dd-622">1,495.71</span></span></td>
<td><span data-ttu-id="b13dd-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b13dd-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="b13dd-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-625">Cost object</span></span></th>
<th><span data-ttu-id="b13dd-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="b13dd-626">Magnitude</span></span></th>
<th><span data-ttu-id="b13dd-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-627">Allocation factor</span></span></th>
<th><span data-ttu-id="b13dd-628">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-628">Amount</span></span></th>
<th><span data-ttu-id="b13dd-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-630">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-631">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-632">80</span><span class="sxs-lookup"><span data-stu-id="b13dd-632">80</span></span></td>
<td><span data-ttu-id="b13dd-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="b13dd-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="b13dd-634">241.05</span><span class="sxs-lookup"><span data-stu-id="b13dd-634">241.05</span></span></td>
<td><span data-ttu-id="b13dd-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-636">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-637">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-638">15</span><span class="sxs-lookup"><span data-stu-id="b13dd-638">15</span></span></td>
<td><span data-ttu-id="b13dd-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="b13dd-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="b13dd-640">45.20</span><span class="sxs-lookup"><span data-stu-id="b13dd-640">45.20</span></span></td>
<td><span data-ttu-id="b13dd-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-642">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-643">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-644">80</span><span class="sxs-lookup"><span data-stu-id="b13dd-644">80</span></span></td>
<td><span data-ttu-id="b13dd-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="b13dd-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="b13dd-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="b13dd-646">2,507.09</span></span></td>
<td><span data-ttu-id="b13dd-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-648">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-649">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-650">15</span><span class="sxs-lookup"><span data-stu-id="b13dd-650">15</span></span></td>
<td><span data-ttu-id="b13dd-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="b13dd-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="b13dd-652">470.08</span><span class="sxs-lookup"><span data-stu-id="b13dd-652">470.08</span></span></td>
<td><span data-ttu-id="b13dd-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="b13dd-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="b13dd-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-655">Journal</span></span></th>
<th><span data-ttu-id="b13dd-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="b13dd-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="b13dd-658">Versione</span><span class="sxs-lookup"><span data-stu-id="b13dd-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-659">00004</span><span class="sxs-lookup"><span data-stu-id="b13dd-659">00004</span></span></td>
<td><span data-ttu-id="b13dd-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="b13dd-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="b13dd-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="b13dd-661">Fiscal</span></span></td>
<td><span data-ttu-id="b13dd-662">2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-662">2017</span></span></td>
<td><span data-ttu-id="b13dd-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-663">Period 1</span></span></td>
<td><span data-ttu-id="b13dd-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="b13dd-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13dd-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-668">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-669">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-670">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-672">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-672">CC001</span></span></td>
<td><span data-ttu-id="b13dd-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-673">HR</span></span></td>
<td><span data-ttu-id="b13dd-674">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-674">10001</span></span></td>
<td><span data-ttu-id="b13dd-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-675">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-676">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-677">500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-679">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-679">CC001</span></span></td>
<td><span data-ttu-id="b13dd-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-680">HR</span></span></td>
<td><span data-ttu-id="b13dd-681">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-681">10001</span></span></td>
<td><span data-ttu-id="b13dd-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-682">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-683">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="b13dd-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-686">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-686">CC002</span></span></td>
<td><span data-ttu-id="b13dd-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-687">Finance</span></span></td>
<td><span data-ttu-id="b13dd-688">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-688">10001</span></span></td>
<td><span data-ttu-id="b13dd-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-689">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-690">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-691">675.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-693">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-693">CC002</span></span></td>
<td><span data-ttu-id="b13dd-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-694">Finance</span></span></td>
<td><span data-ttu-id="b13dd-695">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-695">10001</span></span></td>
<td><span data-ttu-id="b13dd-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-696">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-697">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="b13dd-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-700">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-700">CC003</span></span></td>
<td><span data-ttu-id="b13dd-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-701">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-702">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-702">10001</span></span></td>
<td><span data-ttu-id="b13dd-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-703">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-704">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-705">713.75</span><span class="sxs-lookup"><span data-stu-id="b13dd-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-707">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-707">CC003</span></span></td>
<td><span data-ttu-id="b13dd-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-708">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-709">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-709">10001</span></span></td>
<td><span data-ttu-id="b13dd-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-710">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-711">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="b13dd-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-714">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-714">CC003</span></span></td>
<td><span data-ttu-id="b13dd-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-715">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-716">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-716">10001</span></span></td>
<td><span data-ttu-id="b13dd-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-717">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-718">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-719">286.25</span><span class="sxs-lookup"><span data-stu-id="b13dd-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-721">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-721">CC003</span></span></td>
<td><span data-ttu-id="b13dd-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-722">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-723">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-723">10001</span></span></td>
<td><span data-ttu-id="b13dd-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-724">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-725">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="b13dd-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-728">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-729">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-730">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-730">10001</span></span></td>
<td><span data-ttu-id="b13dd-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-731">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-732">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-733">776.36</span><span class="sxs-lookup"><span data-stu-id="b13dd-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-735">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-736">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-737">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-737">10001</span></span></td>
<td><span data-ttu-id="b13dd-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-738">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-739">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="b13dd-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-742">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-743">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-744">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-744">10001</span></span></td>
<td><span data-ttu-id="b13dd-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-745">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-746">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-747">223.64</span><span class="sxs-lookup"><span data-stu-id="b13dd-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="b13dd-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-749">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-750">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-751">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-751">10001</span></span></td>
<td><span data-ttu-id="b13dd-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-752">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-753">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="b13dd-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="b13dd-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="b13dd-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="b13dd-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-757">Cost element</span></span></th>
<th><span data-ttu-id="b13dd-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-758">Cost behavior</span></span></th>
<th><span data-ttu-id="b13dd-759">Importo</span><span class="sxs-lookup"><span data-stu-id="b13dd-759">Amount</span></span></th>
<th><span data-ttu-id="b13dd-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="b13dd-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13dd-761">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-761">CC001</span></span></td>
<td><span data-ttu-id="b13dd-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-762">HR</span></span></td>
<td><span data-ttu-id="b13dd-763">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-763">10001</span></span></td>
<td><span data-ttu-id="b13dd-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-764">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-765">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-766">-500.00</span></span></td>
<td><span data-ttu-id="b13dd-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-768">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-768">CC002</span></span></td>
<td><span data-ttu-id="b13dd-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-769">Finance</span></span></td>
<td><span data-ttu-id="b13dd-770">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-770">10001</span></span></td>
<td><span data-ttu-id="b13dd-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-771">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-772">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-773">175.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-773">175.00</span></span></td>
<td><span data-ttu-id="b13dd-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-775">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-775">CC003</span></span></td>
<td><span data-ttu-id="b13dd-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-776">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-777">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-777">10001</span></span></td>
<td><span data-ttu-id="b13dd-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-778">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-779">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-780">275.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-780">275.00</span></span></td>
<td><span data-ttu-id="b13dd-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-782">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-782">CC004</span></span></td>
<td><span data-ttu-id="b13dd-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-783">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-784">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-784">10001</span></span></td>
<td><span data-ttu-id="b13dd-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-785">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-786">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-787">50,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-787">50,00</span></span></td>
<td><span data-ttu-id="b13dd-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-789">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-789">CC001</span></span></td>
<td><span data-ttu-id="b13dd-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="b13dd-790">HR</span></span></td>
<td><span data-ttu-id="b13dd-791">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-791">10001</span></span></td>
<td><span data-ttu-id="b13dd-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-792">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-793">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="b13dd-794">-1,245.71</span></span></td>
<td><span data-ttu-id="b13dd-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-796">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-796">CC002</span></span></td>
<td><span data-ttu-id="b13dd-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-797">Finance</span></span></td>
<td><span data-ttu-id="b13dd-798">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-798">10001</span></span></td>
<td><span data-ttu-id="b13dd-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-799">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-800">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-801">436.00</span><span class="sxs-lookup"><span data-stu-id="b13dd-801">436.00</span></span></td>
<td><span data-ttu-id="b13dd-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-803">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-803">CC003</span></span></td>
<td><span data-ttu-id="b13dd-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-804">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-805">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-805">10001</span></span></td>
<td><span data-ttu-id="b13dd-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-806">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-807">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-808">685.14</span><span class="sxs-lookup"><span data-stu-id="b13dd-808">685.14</span></span></td>
<td><span data-ttu-id="b13dd-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-810">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-810">CC004</span></span></td>
<td><span data-ttu-id="b13dd-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-811">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-812">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-812">10001</span></span></td>
<td><span data-ttu-id="b13dd-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-813">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-814">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-815">124.57</span><span class="sxs-lookup"><span data-stu-id="b13dd-815">124.57</span></span></td>
<td><span data-ttu-id="b13dd-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-817">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-817">CC002</span></span></td>
<td><span data-ttu-id="b13dd-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-818">Finance</span></span></td>
<td><span data-ttu-id="b13dd-819">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-819">10001</span></span></td>
<td><span data-ttu-id="b13dd-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-820">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-821">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-822">-675.00</span></span></td>
<td><span data-ttu-id="b13dd-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-824">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-824">CC003</span></span></td>
<td><span data-ttu-id="b13dd-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-825">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-826">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-826">10001</span></span></td>
<td><span data-ttu-id="b13dd-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-827">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-828">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-829">438.75</span><span class="sxs-lookup"><span data-stu-id="b13dd-829">438.75</span></span></td>
<td><span data-ttu-id="b13dd-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-831">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-831">CC004</span></span></td>
<td><span data-ttu-id="b13dd-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-832">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-833">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-833">10001</span></span></td>
<td><span data-ttu-id="b13dd-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-834">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-835">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-836">236.25</span><span class="sxs-lookup"><span data-stu-id="b13dd-836">236.25</span></span></td>
<td><span data-ttu-id="b13dd-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-838">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-838">CC002</span></span></td>
<td><span data-ttu-id="b13dd-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="b13dd-839">Finance</span></span></td>
<td><span data-ttu-id="b13dd-840">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-840">10001</span></span></td>
<td><span data-ttu-id="b13dd-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-841">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-842">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="b13dd-843">-8,150.29</span></span></td>
<td><span data-ttu-id="b13dd-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-845">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-845">CC003</span></span></td>
<td><span data-ttu-id="b13dd-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-846">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-847">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-847">10001</span></span></td>
<td><span data-ttu-id="b13dd-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-848">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-849">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="b13dd-850">5,297.69</span></span></td>
<td><span data-ttu-id="b13dd-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-852">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-852">CC004</span></span></td>
<td><span data-ttu-id="b13dd-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-853">Packaging</span></span></td>
<td><span data-ttu-id="b13dd-854">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-854">10001</span></span></td>
<td><span data-ttu-id="b13dd-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-855">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-856">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="b13dd-857">2,852.60</span></span></td>
<td><span data-ttu-id="b13dd-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-859">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-859">CC003</span></span></td>
<td><span data-ttu-id="b13dd-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-860">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-861">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-861">10001</span></span></td>
<td><span data-ttu-id="b13dd-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-862">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-863">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="b13dd-864">-713.75</span></span></td>
<td><span data-ttu-id="b13dd-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-866">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-867">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-868">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-868">10001</span></span></td>
<td><span data-ttu-id="b13dd-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-869">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-870">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-871">535.31</span><span class="sxs-lookup"><span data-stu-id="b13dd-871">535.31</span></span></td>
<td><span data-ttu-id="b13dd-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-873">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-874">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-875">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-875">10001</span></span></td>
<td><span data-ttu-id="b13dd-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-876">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-877">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-878">178.44</span><span class="sxs-lookup"><span data-stu-id="b13dd-878">178.44</span></span></td>
<td><span data-ttu-id="b13dd-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-880">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-880">CC003</span></span></td>
<td><span data-ttu-id="b13dd-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-881">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-882">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-882">10001</span></span></td>
<td><span data-ttu-id="b13dd-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-883">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-884">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="b13dd-885">-5,982.83</span></span></td>
<td><span data-ttu-id="b13dd-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-887">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-888">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-889">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-889">10001</span></span></td>
<td><span data-ttu-id="b13dd-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-890">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-891">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="b13dd-892">4,487.12</span></span></td>
<td><span data-ttu-id="b13dd-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-894">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-895">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-896">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-896">10001</span></span></td>
<td><span data-ttu-id="b13dd-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-897">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-898">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="b13dd-899">1,495.71</span></span></td>
<td><span data-ttu-id="b13dd-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-901">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-901">CC003</span></span></td>
<td><span data-ttu-id="b13dd-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-902">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-903">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-903">10001</span></span></td>
<td><span data-ttu-id="b13dd-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-904">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-905">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="b13dd-906">-286.25</span></span></td>
<td><span data-ttu-id="b13dd-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-908">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-909">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-910">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-910">10001</span></span></td>
<td><span data-ttu-id="b13dd-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-911">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-912">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-913">241.05</span><span class="sxs-lookup"><span data-stu-id="b13dd-913">241.05</span></span></td>
<td><span data-ttu-id="b13dd-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-915">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-916">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-917">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-917">10001</span></span></td>
<td><span data-ttu-id="b13dd-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-918">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-919">Fixed cost</span></span></td>
<td><span data-ttu-id="b13dd-920">45.20</span><span class="sxs-lookup"><span data-stu-id="b13dd-920">45.20</span></span></td>
<td><span data-ttu-id="b13dd-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-922">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-922">CC003</span></span></td>
<td><span data-ttu-id="b13dd-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="b13dd-923">Assembly</span></span></td>
<td><span data-ttu-id="b13dd-924">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-924">10001</span></span></td>
<td><span data-ttu-id="b13dd-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-925">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-926">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="b13dd-927">-2,977.17</span></span></td>
<td><span data-ttu-id="b13dd-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-929">Prod 1</span></span></td>
<td><span data-ttu-id="b13dd-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-930">Product 1</span></span></td>
<td><span data-ttu-id="b13dd-931">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-931">10001</span></span></td>
<td><span data-ttu-id="b13dd-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-932">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-933">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="b13dd-934">2,507.09</span></span></td>
<td><span data-ttu-id="b13dd-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13dd-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-936">Prod 2</span></span></td>
<td><span data-ttu-id="b13dd-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-937">Product 2</span></span></td>
<td><span data-ttu-id="b13dd-938">10001</span><span class="sxs-lookup"><span data-stu-id="b13dd-938">10001</span></span></td>
<td><span data-ttu-id="b13dd-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-939">Electricity</span></span></td>
<td><span data-ttu-id="b13dd-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-940">Variable cost</span></span></td>
<td><span data-ttu-id="b13dd-941">470.08</span><span class="sxs-lookup"><span data-stu-id="b13dd-941">470.08</span></span></td>
<td><span data-ttu-id="b13dd-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="b13dd-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="b13dd-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="b13dd-943">Conclusion</span></span>
<span data-ttu-id="b13dd-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="b13dd-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="b13dd-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="b13dd-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="b13dd-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="b13dd-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="b13dd-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="b13dd-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="b13dd-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b13dd-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="b13dd-950">Totale</span><span class="sxs-lookup"><span data-stu-id="b13dd-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b13dd-951">CC099</span><span class="sxs-lookup"><span data-stu-id="b13dd-951">CC099</span></span></th>
<th><span data-ttu-id="b13dd-952">CC001</span><span class="sxs-lookup"><span data-stu-id="b13dd-952">CC001</span></span></th>
<th><span data-ttu-id="b13dd-953">CC002</span><span class="sxs-lookup"><span data-stu-id="b13dd-953">CC002</span></span></th>
<th><span data-ttu-id="b13dd-954">CC003</span><span class="sxs-lookup"><span data-stu-id="b13dd-954">CC003</span></span></th>
<th><span data-ttu-id="b13dd-955">CC004</span><span class="sxs-lookup"><span data-stu-id="b13dd-955">CC004</span></span></th>
<th><span data-ttu-id="b13dd-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-956">Proj 1</span></span></th>
<th><span data-ttu-id="b13dd-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-957">Proj 2</span></span></th>
<th><span data-ttu-id="b13dd-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="b13dd-958">Prod 1</span></span></th>
<th><span data-ttu-id="b13dd-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="b13dd-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="b13dd-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="b13dd-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="b13dd-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="b13dd-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-971">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="b13dd-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="b13dd-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-973">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-974">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-975">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-976">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-977">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-978">776.36</span><span class="sxs-lookup"><span data-stu-id="b13dd-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-979">223.64</span><span class="sxs-lookup"><span data-stu-id="b13dd-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="b13dd-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="b13dd-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-982">000</span><span class="sxs-lookup"><span data-stu-id="b13dd-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-983">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-984">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-985">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-986">0,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-987">30,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-988">10,00</span><span class="sxs-lookup"><span data-stu-id="b13dd-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="b13dd-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="b13dd-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="b13dd-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="b13dd-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="b13dd-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="b13dd-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b13dd-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="b13dd-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="b13dd-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="b13dd-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="b13dd-996">Per ulteriori informazioni, vedere [Rollup costi](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="b13dd-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>




