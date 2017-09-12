---
title: Calcolo generale
description: In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 1eb5560ba795ab6df61b5af889049810dd00d79e
ms.contentlocale: it-it
ms.lasthandoff: 06/29/2017


---

# <a name="overhead-calculation"></a><span data-ttu-id="2b281-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="2b281-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2b281-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="2b281-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="2b281-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="2b281-105">Term definition</span></span>
---------------

<span data-ttu-id="2b281-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="2b281-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="2b281-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="2b281-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="2b281-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="2b281-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="2b281-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="2b281-109">Rent</span></span>
-   <span data-ttu-id="2b281-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-110">Electricity</span></span>
-   <span data-ttu-id="2b281-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="2b281-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="2b281-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="2b281-112">Overhead calculation overview</span></span>
<span data-ttu-id="2b281-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="2b281-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="2b281-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="2b281-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="2b281-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="2b281-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="2b281-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="2b281-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="2b281-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="2b281-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="2b281-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="2b281-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="2b281-119">Version type</span></span>
-   <span data-ttu-id="2b281-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="2b281-120">Date and time</span></span>
-   <span data-ttu-id="2b281-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="2b281-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="2b281-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-122">Fiscal year</span></span>
-   <span data-ttu-id="2b281-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-123">Fiscal period</span></span>

<span data-ttu-id="2b281-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="2b281-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="2b281-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="2b281-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="2b281-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="2b281-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="2b281-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="2b281-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="2b281-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="2b281-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="2b281-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="2b281-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="2b281-130">Therefore, you always have full traceability.</span></span> 
<span data-ttu-id="2b281-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="2b281-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="2b281-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="2b281-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="2b281-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="2b281-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="2b281-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="2b281-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="2b281-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="2b281-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="2b281-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="2b281-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="2b281-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="2b281-140">Main account</span></span></th>
<th><span data-ttu-id="2b281-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="2b281-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="2b281-143">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-143">CC099</span></span></td>
<td><span data-ttu-id="2b281-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-144">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-145">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-145">10001</span></span></td>
<td><span data-ttu-id="2b281-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-146">Electricity</span></span></td>
<td><span data-ttu-id="2b281-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="2b281-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="2b281-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="2b281-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="2b281-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="2b281-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="2b281-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-151">Define the cost behavior rule</span></span>

<span data-ttu-id="2b281-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="2b281-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="2b281-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="2b281-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="2b281-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="2b281-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="2b281-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="2b281-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="2b281-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="2b281-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="2b281-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="2b281-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-160">Journal</span></span></th>
<th><span data-ttu-id="2b281-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2b281-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2b281-163">Versione</span><span class="sxs-lookup"><span data-stu-id="2b281-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-164">00001</span><span class="sxs-lookup"><span data-stu-id="2b281-164">00001</span></span></td>
<td><span data-ttu-id="2b281-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="2b281-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-166">Fiscal</span></span></td>
<td><span data-ttu-id="2b281-167">2017</span><span class="sxs-lookup"><span data-stu-id="2b281-167">2017</span></span></td>
<td><span data-ttu-id="2b281-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-168">Period 1</span></span></td>
<td><span data-ttu-id="2b281-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2b281-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="2b281-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-173">Cost element</span></span></th>
<th><span data-ttu-id="2b281-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-174">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-175">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="2b281-177">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-177">CC099</span></span></td>
<td><span data-ttu-id="2b281-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-178">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-179">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-179">10001</span></span></td>
<td><span data-ttu-id="2b281-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-180">Electricity</span></span></td>
<td><span data-ttu-id="2b281-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="2b281-181">Unclassified</span></span></td>
<td><span data-ttu-id="2b281-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2b281-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-185">Cost element</span></span></th>
<th><span data-ttu-id="2b281-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-186">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-187">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-187">Amount</span></span></th>
<th><span data-ttu-id="2b281-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-189">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-189">CC099</span></span></td>
<td><span data-ttu-id="2b281-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-190">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-191">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-191">10001</span></span></td>
<td><span data-ttu-id="2b281-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-192">Electricity</span></span></td>
<td><span data-ttu-id="2b281-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="2b281-193">Unclassified</span></span></td>
<td><span data-ttu-id="2b281-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-194">10,000.00</span></span></td>
<td><span data-ttu-id="2b281-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-196">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-196">CC099</span></span></td>
<td><span data-ttu-id="2b281-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-197">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-198">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-198">10001</span></span></td>
<td><span data-ttu-id="2b281-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-199">Electricity</span></span></td>
<td><span data-ttu-id="2b281-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="2b281-200">Unclassified</span></span></td>
<td><span data-ttu-id="2b281-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-201">-10,000.00</span></span></td>
<td><span data-ttu-id="2b281-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-203">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-203">CC099</span></span></td>
<td><span data-ttu-id="2b281-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-204">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-205">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-205">10001</span></span></td>
<td><span data-ttu-id="2b281-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-206">Electricity</span></span></td>
<td><span data-ttu-id="2b281-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-207">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-208">1,000.00</span></span></td>
<td><span data-ttu-id="2b281-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-210">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-210">CC099</span></span></td>
<td><span data-ttu-id="2b281-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-211">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-212">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-212">10001</span></span></td>
<td><span data-ttu-id="2b281-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-213">Electricity</span></span></td>
<td><span data-ttu-id="2b281-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-214">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-215">9,000.00</span></span></td>
<td><span data-ttu-id="2b281-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-217">Per informazioni dettagliate sul comportamento costo, vedere Criteri di comportamento costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="2b281-218">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="2b281-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="2b281-219">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="2b281-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="2b281-220">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="2b281-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="2b281-221">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="2b281-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="2b281-222">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="2b281-222">Define the cost distribution rule</span></span>

<span data-ttu-id="2b281-223">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="2b281-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="2b281-224">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="2b281-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="2b281-225">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="2b281-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="2b281-226">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="2b281-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="2b281-227">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="2b281-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="2b281-228">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-229">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-229">Cost object</span></span></th>
<th><span data-ttu-id="2b281-230">KWH</span><span class="sxs-lookup"><span data-stu-id="2b281-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-231">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-231">CC001</span></span></td>
<td><span data-ttu-id="2b281-232">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-232">HR</span></span></td>
<td><span data-ttu-id="2b281-233">1.000</span><span class="sxs-lookup"><span data-stu-id="2b281-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-234">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-234">CC002</span></span></td>
<td><span data-ttu-id="2b281-235">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-235">Finance</span></span></td>
<td><span data-ttu-id="2b281-236">6.000</span><span class="sxs-lookup"><span data-stu-id="2b281-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-237">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-237">CC003</span></span></td>
<td><span data-ttu-id="2b281-238">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-238">Assembly</span></span></td>
<td><span data-ttu-id="2b281-239">0</span><span class="sxs-lookup"><span data-stu-id="2b281-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-240">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="2b281-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-241">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-241">Cost object</span></span></th>
<th><span data-ttu-id="2b281-242">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-242">Magnitude</span></span></th>
<th><span data-ttu-id="2b281-243">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="2b281-243">Allocation factor</span></span></th>
<th><span data-ttu-id="2b281-244">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-245">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-245">CC001</span></span></td>
<td><span data-ttu-id="2b281-246">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-246">HR</span></span></td>
<td><span data-ttu-id="2b281-247">1.000</span><span class="sxs-lookup"><span data-stu-id="2b281-247">1,000</span></span></td>
<td><span data-ttu-id="2b281-248">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2b281-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2b281-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-250">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-250">CC002</span></span></td>
<td><span data-ttu-id="2b281-251">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-251">Finance</span></span></td>
<td><span data-ttu-id="2b281-252">6.000</span><span class="sxs-lookup"><span data-stu-id="2b281-252">6,000</span></span></td>
<td><span data-ttu-id="2b281-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2b281-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2b281-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-255">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-255">CC003</span></span></td>
<td><span data-ttu-id="2b281-256">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-256">Assembly</span></span></td>
<td><span data-ttu-id="2b281-257">0</span><span class="sxs-lookup"><span data-stu-id="2b281-257">0</span></span></td>
<td><span data-ttu-id="2b281-258">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2b281-259">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-260">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="2b281-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="2b281-261">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="2b281-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-262">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-262">Cost object</span></span></th>
<th><span data-ttu-id="2b281-263">Formula</span><span class="sxs-lookup"><span data-stu-id="2b281-263">Formula</span></span></th>
<th><span data-ttu-id="2b281-264">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-264">Magnitude</span></span></th>
<th><span data-ttu-id="2b281-265">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="2b281-265">Allocation factor</span></span></th>
<th><span data-ttu-id="2b281-266">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-267">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-267">CC001</span></span></td>
<td><span data-ttu-id="2b281-268">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-268">HR</span></span></td>
<td><span data-ttu-id="2b281-269">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2b281-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2b281-270">1</span><span class="sxs-lookup"><span data-stu-id="2b281-270">1</span></span></td>
<td><span data-ttu-id="2b281-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2b281-272">500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-273">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-273">CC002</span></span></td>
<td><span data-ttu-id="2b281-274">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-274">Finance</span></span></td>
<td><span data-ttu-id="2b281-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2b281-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2b281-276">1</span><span class="sxs-lookup"><span data-stu-id="2b281-276">1</span></span></td>
<td><span data-ttu-id="2b281-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2b281-278">500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-279">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-279">CC003</span></span></td>
<td><span data-ttu-id="2b281-280">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-280">Assembly</span></span></td>
<td><span data-ttu-id="2b281-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2b281-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2b281-282">0</span><span class="sxs-lookup"><span data-stu-id="2b281-282">0</span></span></td>
<td><span data-ttu-id="2b281-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2b281-284">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2b281-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-286">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-286">Journal</span></span></th>
<th><span data-ttu-id="2b281-287">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2b281-288">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2b281-289">Versione</span><span class="sxs-lookup"><span data-stu-id="2b281-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-290">00002</span><span class="sxs-lookup"><span data-stu-id="2b281-290">00002</span></span></td>
<td><span data-ttu-id="2b281-291">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="2b281-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="2b281-292">Fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-292">Fiscal</span></span></td>
<td><span data-ttu-id="2b281-293">2017</span><span class="sxs-lookup"><span data-stu-id="2b281-293">2017</span></span></td>
<td><span data-ttu-id="2b281-294">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-294">Period 1</span></span></td>
<td><span data-ttu-id="2b281-295">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2b281-296">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="2b281-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-297">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-298">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-299">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-299">Cost element</span></span></th>
<th><span data-ttu-id="2b281-300">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-300">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-301">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-302">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-303">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-303">CC099</span></span></td>
<td><span data-ttu-id="2b281-304">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-304">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-305">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-305">10001</span></span></td>
<td><span data-ttu-id="2b281-306">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-306">Electricity</span></span></td>
<td><span data-ttu-id="2b281-307">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-307">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-309">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-310">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-310">CC099</span></span></td>
<td><span data-ttu-id="2b281-311">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-311">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-312">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-312">10001</span></span></td>
<td><span data-ttu-id="2b281-313">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-313">Electricity</span></span></td>
<td><span data-ttu-id="2b281-314">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-314">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-315">9.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2b281-316">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-317">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-318">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-318">Cost element</span></span></th>
<th><span data-ttu-id="2b281-319">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-319">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-320">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-320">Amount</span></span></th>
<th><span data-ttu-id="2b281-321">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-322">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-322">CC099</span></span></td>
<td><span data-ttu-id="2b281-323">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-323">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-324">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-324">10001</span></span></td>
<td><span data-ttu-id="2b281-325">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-325">Electricity</span></span></td>
<td><span data-ttu-id="2b281-326">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-326">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-327">-1,000.00</span></span></td>
<td><span data-ttu-id="2b281-328">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-329">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-329">CC001</span></span></td>
<td><span data-ttu-id="2b281-330">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-330">HR</span></span></td>
<td><span data-ttu-id="2b281-331">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-331">10001</span></span></td>
<td><span data-ttu-id="2b281-332">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-332">Electricity</span></span></td>
<td><span data-ttu-id="2b281-333">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-333">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-334">500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-334">500.00</span></span></td>
<td><span data-ttu-id="2b281-335">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-336">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-336">CC002</span></span></td>
<td><span data-ttu-id="2b281-337">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-337">Finance</span></span></td>
<td><span data-ttu-id="2b281-338">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-338">10001</span></span></td>
<td><span data-ttu-id="2b281-339">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-339">Electricity</span></span></td>
<td><span data-ttu-id="2b281-340">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-340">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-341">500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-341">500.00</span></span></td>
<td><span data-ttu-id="2b281-342">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-343">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-343">CC099</span></span></td>
<td><span data-ttu-id="2b281-344">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="2b281-344">Default cost center</span></span></td>
<td><span data-ttu-id="2b281-345">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-345">10001</span></span></td>
<td><span data-ttu-id="2b281-346">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-346">Electricity</span></span></td>
<td><span data-ttu-id="2b281-347">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-347">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="2b281-348">-9,000.00</span></span></td>
<td><span data-ttu-id="2b281-349">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-350">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-350">CC001</span></span></td>
<td><span data-ttu-id="2b281-351">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-351">HR</span></span></td>
<td><span data-ttu-id="2b281-352">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-352">10001</span></span></td>
<td><span data-ttu-id="2b281-353">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-353">Electricity</span></span></td>
<td><span data-ttu-id="2b281-354">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-354">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2b281-355">1,285.71</span></span></td>
<td><span data-ttu-id="2b281-356">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-357">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-357">CC002</span></span></td>
<td><span data-ttu-id="2b281-358">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-358">Finance</span></span></td>
<td><span data-ttu-id="2b281-359">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-359">10001</span></span></td>
<td><span data-ttu-id="2b281-360">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-360">Electricity</span></span></td>
<td><span data-ttu-id="2b281-361">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-361">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2b281-362">7,714.29</span></span></td>
<td><span data-ttu-id="2b281-363">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-364">Per informazioni dettagliate sulla base di allocazione e distribuzione costo, vedere Criteri di distribuzione costi e Basi di allocazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="2b281-365">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="2b281-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="2b281-366">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="2b281-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="2b281-367">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="2b281-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="2b281-368">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="2b281-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="2b281-369">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="2b281-369">Define the overhead rate</span></span>

<span data-ttu-id="2b281-370">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="2b281-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="2b281-371">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="2b281-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-372">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-372">Cost object</span></span></th>
<th><span data-ttu-id="2b281-373">Ore</span><span class="sxs-lookup"><span data-stu-id="2b281-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2b281-374">Proj 1</span></span></td>
<td><span data-ttu-id="2b281-375">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-375">Project 1</span></span></td>
<td><span data-ttu-id="2b281-376">3</span><span class="sxs-lookup"><span data-stu-id="2b281-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2b281-377">Proj 2</span></span></td>
<td><span data-ttu-id="2b281-378">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-378">Project 2</span></span></td>
<td><span data-ttu-id="2b281-379">1</span><span class="sxs-lookup"><span data-stu-id="2b281-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-380">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="2b281-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-381">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-381">Cost object</span></span></th>
<th><span data-ttu-id="2b281-382">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-382">Cost element</span></span></th>
<th><span data-ttu-id="2b281-383">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-383">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-384">Unità</span><span class="sxs-lookup"><span data-stu-id="2b281-384">Units</span></span></th>
<th><span data-ttu-id="2b281-385">Tasso</span><span class="sxs-lookup"><span data-stu-id="2b281-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-386">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-386">CC001</span></span></td>
<td><span data-ttu-id="2b281-387">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-387">HR</span></span></td>
<td><span data-ttu-id="2b281-388">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-388">10001</span></span></td>
<td><span data-ttu-id="2b281-389">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-389">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-390">1</span><span class="sxs-lookup"><span data-stu-id="2b281-390">1</span></span></td>
<td><span data-ttu-id="2b281-391">10</span><span class="sxs-lookup"><span data-stu-id="2b281-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-392">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-393">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-393">Cost object</span></span></th>
<th><span data-ttu-id="2b281-394">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-394">Magnitude</span></span></th>
<th><span data-ttu-id="2b281-395">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-395">Cost element</span></span></th>
<th><span data-ttu-id="2b281-396">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="2b281-396">Allocation factor</span></span></th>
<th><span data-ttu-id="2b281-397">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2b281-398">Proj 1</span></span></td>
<td><span data-ttu-id="2b281-399">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-399">Project 1</span></span></td>
<td><span data-ttu-id="2b281-400">3</span><span class="sxs-lookup"><span data-stu-id="2b281-400">3</span></span></td>
<td><span data-ttu-id="2b281-401">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-401">10001</span></span></td>
<td><span data-ttu-id="2b281-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="2b281-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2b281-403">30,00</span><span class="sxs-lookup"><span data-stu-id="2b281-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2b281-404">Proj 2</span></span></td>
<td><span data-ttu-id="2b281-405">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-405">Project 2</span></span></td>
<td><span data-ttu-id="2b281-406">1</span><span class="sxs-lookup"><span data-stu-id="2b281-406">1</span></span></td>
<td><span data-ttu-id="2b281-407">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-407">10001</span></span></td>
<td><span data-ttu-id="2b281-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="2b281-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2b281-409">10,00</span><span class="sxs-lookup"><span data-stu-id="2b281-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2b281-410">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-411">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-411">Journal</span></span></th>
<th><span data-ttu-id="2b281-412">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2b281-413">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2b281-414">Versione</span><span class="sxs-lookup"><span data-stu-id="2b281-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-415">00003</span><span class="sxs-lookup"><span data-stu-id="2b281-415">00003</span></span></td>
<td><span data-ttu-id="2b281-416">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="2b281-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="2b281-417">Fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-417">Fiscal</span></span></td>
<td><span data-ttu-id="2b281-418">2017</span><span class="sxs-lookup"><span data-stu-id="2b281-418">2017</span></span></td>
<td><span data-ttu-id="2b281-419">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-419">Period 1</span></span></td>
<td><span data-ttu-id="2b281-420">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="2b281-421">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="2b281-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-422">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-423">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-423">Cost object</span></span></th>
<th><span data-ttu-id="2b281-424">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-425">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2b281-426">Proj 1</span></span></td>
<td><span data-ttu-id="2b281-427">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="2b281-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2b281-428">3,00</span><span class="sxs-lookup"><span data-stu-id="2b281-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-429">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2b281-430">Proj 2</span></span></td>
<td><span data-ttu-id="2b281-431">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="2b281-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2b281-432">1,00</span><span class="sxs-lookup"><span data-stu-id="2b281-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2b281-433">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-434">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-435">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-435">Cost element</span></span></th>
<th><span data-ttu-id="2b281-436">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-436">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-437">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-437">Amount</span></span></th>
<th><span data-ttu-id="2b281-438">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="2b281-439">CC0001</span></span></td>
<td><span data-ttu-id="2b281-440">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-440">HR</span></span></td>
<td><span data-ttu-id="2b281-441">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-441">10001</span></span></td>
<td><span data-ttu-id="2b281-442">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-442">Electricity</span></span></td>
<td><span data-ttu-id="2b281-443">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-443">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="2b281-444">-30.00</span></span></td>
<td><span data-ttu-id="2b281-445">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2b281-446">Proj 1</span></span></td>
<td><span data-ttu-id="2b281-447">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="2b281-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2b281-448">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-448">10001</span></span></td>
<td><span data-ttu-id="2b281-449">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-449">Electricity</span></span></td>
<td><span data-ttu-id="2b281-450">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-450">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-451">30,00</span><span class="sxs-lookup"><span data-stu-id="2b281-451">30.00</span></span></td>
<td><span data-ttu-id="2b281-452">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-453">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-453">CC001</span></span></td>
<td><span data-ttu-id="2b281-454">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-454">HR</span></span></td>
<td><span data-ttu-id="2b281-455">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-455">10001</span></span></td>
<td><span data-ttu-id="2b281-456">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-456">Electricity</span></span></td>
<td><span data-ttu-id="2b281-457">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-457">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-458">-10.00</span><span class="sxs-lookup"><span data-stu-id="2b281-458">-10.00</span></span></td>
<td><span data-ttu-id="2b281-459">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2b281-460">Proj 2</span></span></td>
<td><span data-ttu-id="2b281-461">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="2b281-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2b281-462">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-462">10001</span></span></td>
<td><span data-ttu-id="2b281-463">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-463">Electricity</span></span></td>
<td><span data-ttu-id="2b281-464">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-464">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-465">10,00</span><span class="sxs-lookup"><span data-stu-id="2b281-465">10.00</span></span></td>
<td><span data-ttu-id="2b281-466">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-467">Per informazioni dettagliate sui criteri di tasso generali, vedere Criterio di tasso generale e Basi di allocazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="2b281-468">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="2b281-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="2b281-469">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="2b281-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="2b281-470">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="2b281-471">Finance and Operations supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="2b281-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="2b281-472">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="2b281-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="2b281-473">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="2b281-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="2b281-474">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="2b281-475">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="2b281-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="2b281-476">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="2b281-476">The allocation order is controlled by the cost control unit.</span></span> <span data-ttu-id="2b281-477">[![Metodo reciproco](./media/reciprocal-method.png)]</span><span class="sxs-lookup"><span data-stu-id="2b281-477">[![Reciprocal method](./media/reciprocal-method.png)]</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="2b281-478">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="2b281-478">Define the cost allocation</span></span>

<span data-ttu-id="2b281-479">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="2b281-480">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="2b281-481">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="2b281-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-482">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-482">Cost object</span></span></th>
<th><span data-ttu-id="2b281-483">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="2b281-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-484">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-484">CC002</span></span></td>
<td><span data-ttu-id="2b281-485">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-485">Finance</span></span></td>
<td><span data-ttu-id="2b281-486">35</span><span class="sxs-lookup"><span data-stu-id="2b281-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-487">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-487">CC003</span></span></td>
<td><span data-ttu-id="2b281-488">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-488">Assembly</span></span></td>
<td><span data-ttu-id="2b281-489">55</span><span class="sxs-lookup"><span data-stu-id="2b281-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-490">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-490">CC004</span></span></td>
<td><span data-ttu-id="2b281-491">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-491">Packaging</span></span></td>
<td><span data-ttu-id="2b281-492">10</span><span class="sxs-lookup"><span data-stu-id="2b281-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-493">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="2b281-494">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="2b281-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-495">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-495">Cost object</span></span></th>
<th><span data-ttu-id="2b281-496">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-497">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-497">CC003</span></span></td>
<td><span data-ttu-id="2b281-498">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-498">Assembly</span></span></td>
<td><span data-ttu-id="2b281-499">65</span><span class="sxs-lookup"><span data-stu-id="2b281-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-500">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-500">CC004</span></span></td>
<td><span data-ttu-id="2b281-501">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-501">Packaging</span></span></td>
<td><span data-ttu-id="2b281-502">35</span><span class="sxs-lookup"><span data-stu-id="2b281-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-503">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="2b281-504">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="2b281-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-505">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-505">Cost object</span></span></th>
<th><span data-ttu-id="2b281-506">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="2b281-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-507">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-508">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-508">Product 1</span></span></td>
<td><span data-ttu-id="2b281-509">60</span><span class="sxs-lookup"><span data-stu-id="2b281-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-510">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-511">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-511">Product 2</span></span></td>
<td><span data-ttu-id="2b281-512">20</span><span class="sxs-lookup"><span data-stu-id="2b281-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-513">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="2b281-514">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="2b281-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-515">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-515">Cost object</span></span></th>
<th><span data-ttu-id="2b281-516">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="2b281-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-517">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-518">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-518">Product 1</span></span></td>
<td><span data-ttu-id="2b281-519">80</span><span class="sxs-lookup"><span data-stu-id="2b281-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-520">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-521">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-521">Product 2</span></span></td>
<td><span data-ttu-id="2b281-522">15</span><span class="sxs-lookup"><span data-stu-id="2b281-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-523">**Nota**: in Finance and Operations, le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="2b281-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="2b281-524">Per informazioni più dettagliate sui provider misure statistiche, vedere il modello provider misure statistiche.</span><span class="sxs-lookup"><span data-stu-id="2b281-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="2b281-525">(Nota: questo argomento non è ancora completo ma sarà presto disponibile). Nella tabella seguente viene illustrato il risultato ottenuto quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="2b281-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-526">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-526">Cost object</span></span></th>
<th><span data-ttu-id="2b281-527">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-527">Magnitude</span></span></th>
<th><span data-ttu-id="2b281-528">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="2b281-528">Allocation factor</span></span></th>
<th><span data-ttu-id="2b281-529">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-529">Amount</span></span></th>
<th><span data-ttu-id="2b281-530">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-531">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-531">CC002</span></span></td>
<td><span data-ttu-id="2b281-532">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-532">Finance</span></span></td>
<td><span data-ttu-id="2b281-533">35</span><span class="sxs-lookup"><span data-stu-id="2b281-533">35</span></span></td>
<td><span data-ttu-id="2b281-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2b281-535">175.00</span><span class="sxs-lookup"><span data-stu-id="2b281-535">175.00</span></span></td>
<td><span data-ttu-id="2b281-536">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-537">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-537">CC003</span></span></td>
<td><span data-ttu-id="2b281-538">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-538">Assembly</span></span></td>
<td><span data-ttu-id="2b281-539">55</span><span class="sxs-lookup"><span data-stu-id="2b281-539">55</span></span></td>
<td><span data-ttu-id="2b281-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2b281-541">275.00</span><span class="sxs-lookup"><span data-stu-id="2b281-541">275.00</span></span></td>
<td><span data-ttu-id="2b281-542">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-543">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-543">CC004</span></span></td>
<td><span data-ttu-id="2b281-544">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-544">Packaging</span></span></td>
<td><span data-ttu-id="2b281-545">10</span><span class="sxs-lookup"><span data-stu-id="2b281-545">10</span></span></td>
<td><span data-ttu-id="2b281-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2b281-547">50,00</span><span class="sxs-lookup"><span data-stu-id="2b281-547">50.00</span></span></td>
<td><span data-ttu-id="2b281-548">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-549">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-549">CC002</span></span></td>
<td><span data-ttu-id="2b281-550">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-550">Finance</span></span></td>
<td><span data-ttu-id="2b281-551">35</span><span class="sxs-lookup"><span data-stu-id="2b281-551">35</span></span></td>
<td><span data-ttu-id="2b281-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="2b281-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2b281-553">436.00</span><span class="sxs-lookup"><span data-stu-id="2b281-553">436.00</span></span></td>
<td><span data-ttu-id="2b281-554">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-555">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-555">CC003</span></span></td>
<td><span data-ttu-id="2b281-556">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-556">Assembly</span></span></td>
<td><span data-ttu-id="2b281-557">55</span><span class="sxs-lookup"><span data-stu-id="2b281-557">55</span></span></td>
<td><span data-ttu-id="2b281-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="2b281-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2b281-559">685.14</span><span class="sxs-lookup"><span data-stu-id="2b281-559">685.14</span></span></td>
<td><span data-ttu-id="2b281-560">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-561">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-561">CC004</span></span></td>
<td><span data-ttu-id="2b281-562">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-562">Packaging</span></span></td>
<td><span data-ttu-id="2b281-563">10</span><span class="sxs-lookup"><span data-stu-id="2b281-563">10</span></span></td>
<td><span data-ttu-id="2b281-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="2b281-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2b281-565">124.57</span><span class="sxs-lookup"><span data-stu-id="2b281-565">124.57</span></span></td>
<td><span data-ttu-id="2b281-566">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-567">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="2b281-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-568">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-568">Cost object</span></span></th>
<th><span data-ttu-id="2b281-569">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-569">Magnitude</span></span></th>
<th><span data-ttu-id="2b281-570">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="2b281-570">Allocation factor</span></span></th>
<th><span data-ttu-id="2b281-571">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-571">Amount</span></span></th>
<th><span data-ttu-id="2b281-572">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-573">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-573">CC003</span></span></td>
<td><span data-ttu-id="2b281-574">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-574">Assembly</span></span></td>
<td><span data-ttu-id="2b281-575">65</span><span class="sxs-lookup"><span data-stu-id="2b281-575">65</span></span></td>
<td><span data-ttu-id="2b281-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="2b281-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2b281-577">438.75</span><span class="sxs-lookup"><span data-stu-id="2b281-577">438.75</span></span></td>
<td><span data-ttu-id="2b281-578">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-579">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-579">CC004</span></span></td>
<td><span data-ttu-id="2b281-580">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-580">Packaging</span></span></td>
<td><span data-ttu-id="2b281-581">35</span><span class="sxs-lookup"><span data-stu-id="2b281-581">35</span></span></td>
<td><span data-ttu-id="2b281-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="2b281-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2b281-583">236.25</span><span class="sxs-lookup"><span data-stu-id="2b281-583">236.25</span></span></td>
<td><span data-ttu-id="2b281-584">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-585">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-585">CC003</span></span></td>
<td><span data-ttu-id="2b281-586">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-586">Assembly</span></span></td>
<td><span data-ttu-id="2b281-587">65</span><span class="sxs-lookup"><span data-stu-id="2b281-587">65</span></span></td>
<td><span data-ttu-id="2b281-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="2b281-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2b281-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2b281-589">5,297.69</span></span></td>
<td><span data-ttu-id="2b281-590">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-591">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-591">CC004</span></span></td>
<td><span data-ttu-id="2b281-592">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-592">Packaging</span></span></td>
<td><span data-ttu-id="2b281-593">35</span><span class="sxs-lookup"><span data-stu-id="2b281-593">35</span></span></td>
<td><span data-ttu-id="2b281-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="2b281-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2b281-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2b281-595">2,852.60</span></span></td>
<td><span data-ttu-id="2b281-596">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-597">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="2b281-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-598">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-598">Cost object</span></span></th>
<th><span data-ttu-id="2b281-599">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-599">Magnitude</span></span></th>
<th><span data-ttu-id="2b281-600">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="2b281-600">Allocation factor</span></span></th>
<th><span data-ttu-id="2b281-601">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-601">Amount</span></span></th>
<th><span data-ttu-id="2b281-602">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-603">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-604">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-604">Product 1</span></span></td>
<td><span data-ttu-id="2b281-605">60</span><span class="sxs-lookup"><span data-stu-id="2b281-605">60</span></span></td>
<td><span data-ttu-id="2b281-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="2b281-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2b281-607">535.31</span><span class="sxs-lookup"><span data-stu-id="2b281-607">535.31</span></span></td>
<td><span data-ttu-id="2b281-608">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-609">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-610">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-610">Product 2</span></span></td>
<td><span data-ttu-id="2b281-611">20</span><span class="sxs-lookup"><span data-stu-id="2b281-611">20</span></span></td>
<td><span data-ttu-id="2b281-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="2b281-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2b281-613">178.44</span><span class="sxs-lookup"><span data-stu-id="2b281-613">178.44</span></span></td>
<td><span data-ttu-id="2b281-614">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-615">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-616">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-616">Product 1</span></span></td>
<td><span data-ttu-id="2b281-617">60</span><span class="sxs-lookup"><span data-stu-id="2b281-617">60</span></span></td>
<td><span data-ttu-id="2b281-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="2b281-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2b281-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2b281-619">4,487.12</span></span></td>
<td><span data-ttu-id="2b281-620">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-621">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-622">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-622">Product 2</span></span></td>
<td><span data-ttu-id="2b281-623">20</span><span class="sxs-lookup"><span data-stu-id="2b281-623">20</span></span></td>
<td><span data-ttu-id="2b281-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="2b281-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2b281-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2b281-625">1,495.71</span></span></td>
<td><span data-ttu-id="2b281-626">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2b281-627">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="2b281-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-628">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-628">Cost object</span></span></th>
<th><span data-ttu-id="2b281-629">Grandezza</span><span class="sxs-lookup"><span data-stu-id="2b281-629">Magnitude</span></span></th>
<th><span data-ttu-id="2b281-630">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="2b281-630">Allocation factor</span></span></th>
<th><span data-ttu-id="2b281-631">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-631">Amount</span></span></th>
<th><span data-ttu-id="2b281-632">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-633">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-634">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-634">Product 1</span></span></td>
<td><span data-ttu-id="2b281-635">80</span><span class="sxs-lookup"><span data-stu-id="2b281-635">80</span></span></td>
<td><span data-ttu-id="2b281-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="2b281-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2b281-637">241.05</span><span class="sxs-lookup"><span data-stu-id="2b281-637">241.05</span></span></td>
<td><span data-ttu-id="2b281-638">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-639">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-640">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-640">Product 2</span></span></td>
<td><span data-ttu-id="2b281-641">15</span><span class="sxs-lookup"><span data-stu-id="2b281-641">15</span></span></td>
<td><span data-ttu-id="2b281-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="2b281-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2b281-643">45.20</span><span class="sxs-lookup"><span data-stu-id="2b281-643">45.20</span></span></td>
<td><span data-ttu-id="2b281-644">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-645">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-646">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-646">Product 1</span></span></td>
<td><span data-ttu-id="2b281-647">80</span><span class="sxs-lookup"><span data-stu-id="2b281-647">80</span></span></td>
<td><span data-ttu-id="2b281-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="2b281-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2b281-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2b281-649">2,507.09</span></span></td>
<td><span data-ttu-id="2b281-650">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-651">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-652">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-652">Product 2</span></span></td>
<td><span data-ttu-id="2b281-653">15</span><span class="sxs-lookup"><span data-stu-id="2b281-653">15</span></span></td>
<td><span data-ttu-id="2b281-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="2b281-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2b281-655">470.08</span><span class="sxs-lookup"><span data-stu-id="2b281-655">470.08</span></span></td>
<td><span data-ttu-id="2b281-656">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2b281-657">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="2b281-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-658">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-658">Journal</span></span></th>
<th><span data-ttu-id="2b281-659">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2b281-660">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2b281-661">Versione</span><span class="sxs-lookup"><span data-stu-id="2b281-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-662">00004</span><span class="sxs-lookup"><span data-stu-id="2b281-662">00004</span></span></td>
<td><span data-ttu-id="2b281-663">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="2b281-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="2b281-664">Fiscale</span><span class="sxs-lookup"><span data-stu-id="2b281-664">Fiscal</span></span></td>
<td><span data-ttu-id="2b281-665">2017</span><span class="sxs-lookup"><span data-stu-id="2b281-665">2017</span></span></td>
<td><span data-ttu-id="2b281-666">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-666">Period 1</span></span></td>
<td><span data-ttu-id="2b281-667">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="2b281-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="2b281-668">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2b281-669">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-670">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-671">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-671">Cost element</span></span></th>
<th><span data-ttu-id="2b281-672">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-672">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-673">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-674">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-675">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-675">CC001</span></span></td>
<td><span data-ttu-id="2b281-676">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-676">HR</span></span></td>
<td><span data-ttu-id="2b281-677">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-677">10001</span></span></td>
<td><span data-ttu-id="2b281-678">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-678">Electricity</span></span></td>
<td><span data-ttu-id="2b281-679">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-679">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-680">500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-681">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-682">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-682">CC001</span></span></td>
<td><span data-ttu-id="2b281-683">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-683">HR</span></span></td>
<td><span data-ttu-id="2b281-684">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-684">10001</span></span></td>
<td><span data-ttu-id="2b281-685">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-685">Electricity</span></span></td>
<td><span data-ttu-id="2b281-686">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-686">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="2b281-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-688">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-689">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-689">CC002</span></span></td>
<td><span data-ttu-id="2b281-690">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-690">Finance</span></span></td>
<td><span data-ttu-id="2b281-691">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-691">10001</span></span></td>
<td><span data-ttu-id="2b281-692">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-692">Electricity</span></span></td>
<td><span data-ttu-id="2b281-693">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-693">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-694">675.00</span><span class="sxs-lookup"><span data-stu-id="2b281-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-695">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-696">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-696">CC002</span></span></td>
<td><span data-ttu-id="2b281-697">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-697">Finance</span></span></td>
<td><span data-ttu-id="2b281-698">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-698">10001</span></span></td>
<td><span data-ttu-id="2b281-699">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-699">Electricity</span></span></td>
<td><span data-ttu-id="2b281-700">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-700">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="2b281-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-702">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-703">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-703">CC003</span></span></td>
<td><span data-ttu-id="2b281-704">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-704">Assembly</span></span></td>
<td><span data-ttu-id="2b281-705">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-705">10001</span></span></td>
<td><span data-ttu-id="2b281-706">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-706">Electricity</span></span></td>
<td><span data-ttu-id="2b281-707">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-707">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-708">713.75</span><span class="sxs-lookup"><span data-stu-id="2b281-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-709">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-710">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-710">CC003</span></span></td>
<td><span data-ttu-id="2b281-711">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-711">Assembly</span></span></td>
<td><span data-ttu-id="2b281-712">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-712">10001</span></span></td>
<td><span data-ttu-id="2b281-713">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-713">Electricity</span></span></td>
<td><span data-ttu-id="2b281-714">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-714">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="2b281-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-716">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-717">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-717">CC003</span></span></td>
<td><span data-ttu-id="2b281-718">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-718">Packaging</span></span></td>
<td><span data-ttu-id="2b281-719">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-719">10001</span></span></td>
<td><span data-ttu-id="2b281-720">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-720">Electricity</span></span></td>
<td><span data-ttu-id="2b281-721">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-721">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-722">286.25</span><span class="sxs-lookup"><span data-stu-id="2b281-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-723">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-724">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-724">CC003</span></span></td>
<td><span data-ttu-id="2b281-725">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-725">Packaging</span></span></td>
<td><span data-ttu-id="2b281-726">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-726">10001</span></span></td>
<td><span data-ttu-id="2b281-727">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-727">Electricity</span></span></td>
<td><span data-ttu-id="2b281-728">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-728">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="2b281-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-730">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-731">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-732">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-732">Product 1</span></span></td>
<td><span data-ttu-id="2b281-733">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-733">10001</span></span></td>
<td><span data-ttu-id="2b281-734">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-734">Electricity</span></span></td>
<td><span data-ttu-id="2b281-735">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-735">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-736">776.36</span><span class="sxs-lookup"><span data-stu-id="2b281-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-737">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-738">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-739">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-739">Product 1</span></span></td>
<td><span data-ttu-id="2b281-740">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-740">10001</span></span></td>
<td><span data-ttu-id="2b281-741">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-741">Electricity</span></span></td>
<td><span data-ttu-id="2b281-742">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-742">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2b281-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-744">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-745">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-746">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-746">Product 1</span></span></td>
<td><span data-ttu-id="2b281-747">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-747">10001</span></span></td>
<td><span data-ttu-id="2b281-748">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-748">Electricity</span></span></td>
<td><span data-ttu-id="2b281-749">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-749">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-750">223.64</span><span class="sxs-lookup"><span data-stu-id="2b281-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-751">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="2b281-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-752">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-753">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-753">Product 1</span></span></td>
<td><span data-ttu-id="2b281-754">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-754">10001</span></span></td>
<td><span data-ttu-id="2b281-755">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-755">Electricity</span></span></td>
<td><span data-ttu-id="2b281-756">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-756">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2b281-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2b281-758">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2b281-759">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2b281-760">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-760">Cost element</span></span></th>
<th><span data-ttu-id="2b281-761">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="2b281-761">Cost behavior</span></span></th>
<th><span data-ttu-id="2b281-762">Importo</span><span class="sxs-lookup"><span data-stu-id="2b281-762">Amount</span></span></th>
<th><span data-ttu-id="2b281-763">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="2b281-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2b281-764">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-764">CC001</span></span></td>
<td><span data-ttu-id="2b281-765">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-765">HR</span></span></td>
<td><span data-ttu-id="2b281-766">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-766">10001</span></span></td>
<td><span data-ttu-id="2b281-767">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-767">Electricity</span></span></td>
<td><span data-ttu-id="2b281-768">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-768">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="2b281-769">-500.00</span></span></td>
<td><span data-ttu-id="2b281-770">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-771">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-771">CC002</span></span></td>
<td><span data-ttu-id="2b281-772">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-772">Finance</span></span></td>
<td><span data-ttu-id="2b281-773">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-773">10001</span></span></td>
<td><span data-ttu-id="2b281-774">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-774">Electricity</span></span></td>
<td><span data-ttu-id="2b281-775">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-775">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-776">175.00</span><span class="sxs-lookup"><span data-stu-id="2b281-776">175.00</span></span></td>
<td><span data-ttu-id="2b281-777">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-778">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-778">CC003</span></span></td>
<td><span data-ttu-id="2b281-779">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-779">Assembly</span></span></td>
<td><span data-ttu-id="2b281-780">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-780">10001</span></span></td>
<td><span data-ttu-id="2b281-781">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-781">Electricity</span></span></td>
<td><span data-ttu-id="2b281-782">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-782">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-783">275.00</span><span class="sxs-lookup"><span data-stu-id="2b281-783">275.00</span></span></td>
<td><span data-ttu-id="2b281-784">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-785">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-785">CC004</span></span></td>
<td><span data-ttu-id="2b281-786">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-786">Packaging</span></span></td>
<td><span data-ttu-id="2b281-787">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-787">10001</span></span></td>
<td><span data-ttu-id="2b281-788">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-788">Electricity</span></span></td>
<td><span data-ttu-id="2b281-789">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-789">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-790">50,00</span><span class="sxs-lookup"><span data-stu-id="2b281-790">50,00</span></span></td>
<td><span data-ttu-id="2b281-791">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-792">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-792">CC001</span></span></td>
<td><span data-ttu-id="2b281-793">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="2b281-793">HR</span></span></td>
<td><span data-ttu-id="2b281-794">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-794">10001</span></span></td>
<td><span data-ttu-id="2b281-795">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-795">Electricity</span></span></td>
<td><span data-ttu-id="2b281-796">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-796">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="2b281-797">-1,245.71</span></span></td>
<td><span data-ttu-id="2b281-798">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-799">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-799">CC002</span></span></td>
<td><span data-ttu-id="2b281-800">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-800">Finance</span></span></td>
<td><span data-ttu-id="2b281-801">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-801">10001</span></span></td>
<td><span data-ttu-id="2b281-802">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-802">Electricity</span></span></td>
<td><span data-ttu-id="2b281-803">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-803">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-804">436.00</span><span class="sxs-lookup"><span data-stu-id="2b281-804">436.00</span></span></td>
<td><span data-ttu-id="2b281-805">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-806">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-806">CC003</span></span></td>
<td><span data-ttu-id="2b281-807">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-807">Assembly</span></span></td>
<td><span data-ttu-id="2b281-808">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-808">10001</span></span></td>
<td><span data-ttu-id="2b281-809">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-809">Electricity</span></span></td>
<td><span data-ttu-id="2b281-810">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-810">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-811">685.14</span><span class="sxs-lookup"><span data-stu-id="2b281-811">685.14</span></span></td>
<td><span data-ttu-id="2b281-812">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-813">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-813">CC004</span></span></td>
<td><span data-ttu-id="2b281-814">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-814">Packaging</span></span></td>
<td><span data-ttu-id="2b281-815">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-815">10001</span></span></td>
<td><span data-ttu-id="2b281-816">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-816">Electricity</span></span></td>
<td><span data-ttu-id="2b281-817">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-817">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-818">124.57</span><span class="sxs-lookup"><span data-stu-id="2b281-818">124.57</span></span></td>
<td><span data-ttu-id="2b281-819">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-820">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-820">CC002</span></span></td>
<td><span data-ttu-id="2b281-821">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-821">Finance</span></span></td>
<td><span data-ttu-id="2b281-822">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-822">10001</span></span></td>
<td><span data-ttu-id="2b281-823">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-823">Electricity</span></span></td>
<td><span data-ttu-id="2b281-824">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-824">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="2b281-825">-675.00</span></span></td>
<td><span data-ttu-id="2b281-826">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-827">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-827">CC003</span></span></td>
<td><span data-ttu-id="2b281-828">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-828">Assembly</span></span></td>
<td><span data-ttu-id="2b281-829">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-829">10001</span></span></td>
<td><span data-ttu-id="2b281-830">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-830">Electricity</span></span></td>
<td><span data-ttu-id="2b281-831">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-831">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-832">438.75</span><span class="sxs-lookup"><span data-stu-id="2b281-832">438.75</span></span></td>
<td><span data-ttu-id="2b281-833">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-834">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-834">CC004</span></span></td>
<td><span data-ttu-id="2b281-835">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-835">Packaging</span></span></td>
<td><span data-ttu-id="2b281-836">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-836">10001</span></span></td>
<td><span data-ttu-id="2b281-837">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-837">Electricity</span></span></td>
<td><span data-ttu-id="2b281-838">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-838">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-839">236.25</span><span class="sxs-lookup"><span data-stu-id="2b281-839">236.25</span></span></td>
<td><span data-ttu-id="2b281-840">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-841">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-841">CC002</span></span></td>
<td><span data-ttu-id="2b281-842">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="2b281-842">Finance</span></span></td>
<td><span data-ttu-id="2b281-843">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-843">10001</span></span></td>
<td><span data-ttu-id="2b281-844">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-844">Electricity</span></span></td>
<td><span data-ttu-id="2b281-845">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-845">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="2b281-846">-8,150.29</span></span></td>
<td><span data-ttu-id="2b281-847">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-848">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-848">CC003</span></span></td>
<td><span data-ttu-id="2b281-849">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-849">Assembly</span></span></td>
<td><span data-ttu-id="2b281-850">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-850">10001</span></span></td>
<td><span data-ttu-id="2b281-851">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-851">Electricity</span></span></td>
<td><span data-ttu-id="2b281-852">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-852">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2b281-853">5,297.69</span></span></td>
<td><span data-ttu-id="2b281-854">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-855">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-855">CC004</span></span></td>
<td><span data-ttu-id="2b281-856">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-856">Packaging</span></span></td>
<td><span data-ttu-id="2b281-857">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-857">10001</span></span></td>
<td><span data-ttu-id="2b281-858">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-858">Electricity</span></span></td>
<td><span data-ttu-id="2b281-859">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-859">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2b281-860">2,852.60</span></span></td>
<td><span data-ttu-id="2b281-861">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-862">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-862">CC003</span></span></td>
<td><span data-ttu-id="2b281-863">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-863">Assembly</span></span></td>
<td><span data-ttu-id="2b281-864">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-864">10001</span></span></td>
<td><span data-ttu-id="2b281-865">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-865">Electricity</span></span></td>
<td><span data-ttu-id="2b281-866">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-866">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="2b281-867">-713.75</span></span></td>
<td><span data-ttu-id="2b281-868">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-869">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-870">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-870">Product 1</span></span></td>
<td><span data-ttu-id="2b281-871">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-871">10001</span></span></td>
<td><span data-ttu-id="2b281-872">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-872">Electricity</span></span></td>
<td><span data-ttu-id="2b281-873">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-873">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-874">535.31</span><span class="sxs-lookup"><span data-stu-id="2b281-874">535.31</span></span></td>
<td><span data-ttu-id="2b281-875">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-876">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-877">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-877">Product 2</span></span></td>
<td><span data-ttu-id="2b281-878">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-878">10001</span></span></td>
<td><span data-ttu-id="2b281-879">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-879">Electricity</span></span></td>
<td><span data-ttu-id="2b281-880">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-880">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-881">178.44</span><span class="sxs-lookup"><span data-stu-id="2b281-881">178.44</span></span></td>
<td><span data-ttu-id="2b281-882">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-883">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-883">CC003</span></span></td>
<td><span data-ttu-id="2b281-884">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-884">Assembly</span></span></td>
<td><span data-ttu-id="2b281-885">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-885">10001</span></span></td>
<td><span data-ttu-id="2b281-886">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-886">Electricity</span></span></td>
<td><span data-ttu-id="2b281-887">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-887">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="2b281-888">-5,982.83</span></span></td>
<td><span data-ttu-id="2b281-889">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-890">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-891">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-891">Product 1</span></span></td>
<td><span data-ttu-id="2b281-892">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-892">10001</span></span></td>
<td><span data-ttu-id="2b281-893">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-893">Electricity</span></span></td>
<td><span data-ttu-id="2b281-894">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-894">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2b281-895">4,487.12</span></span></td>
<td><span data-ttu-id="2b281-896">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-897">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-898">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-898">Product 2</span></span></td>
<td><span data-ttu-id="2b281-899">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-899">10001</span></span></td>
<td><span data-ttu-id="2b281-900">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-900">Electricity</span></span></td>
<td><span data-ttu-id="2b281-901">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-901">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2b281-902">1,495.71</span></span></td>
<td><span data-ttu-id="2b281-903">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-904">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-904">CC003</span></span></td>
<td><span data-ttu-id="2b281-905">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-905">Assembly</span></span></td>
<td><span data-ttu-id="2b281-906">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-906">10001</span></span></td>
<td><span data-ttu-id="2b281-907">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-907">Electricity</span></span></td>
<td><span data-ttu-id="2b281-908">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-908">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="2b281-909">-286.25</span></span></td>
<td><span data-ttu-id="2b281-910">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-911">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-912">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-912">Product 1</span></span></td>
<td><span data-ttu-id="2b281-913">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-913">10001</span></span></td>
<td><span data-ttu-id="2b281-914">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-914">Electricity</span></span></td>
<td><span data-ttu-id="2b281-915">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-915">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-916">241.05</span><span class="sxs-lookup"><span data-stu-id="2b281-916">241.05</span></span></td>
<td><span data-ttu-id="2b281-917">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-918">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-919">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-919">Product 2</span></span></td>
<td><span data-ttu-id="2b281-920">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-920">10001</span></span></td>
<td><span data-ttu-id="2b281-921">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-921">Electricity</span></span></td>
<td><span data-ttu-id="2b281-922">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-922">Fixed cost</span></span></td>
<td><span data-ttu-id="2b281-923">45.20</span><span class="sxs-lookup"><span data-stu-id="2b281-923">45.20</span></span></td>
<td><span data-ttu-id="2b281-924">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-925">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-925">CC003</span></span></td>
<td><span data-ttu-id="2b281-926">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="2b281-926">Assembly</span></span></td>
<td><span data-ttu-id="2b281-927">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-927">10001</span></span></td>
<td><span data-ttu-id="2b281-928">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-928">Electricity</span></span></td>
<td><span data-ttu-id="2b281-929">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-929">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="2b281-930">-2,977.17</span></span></td>
<td><span data-ttu-id="2b281-931">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-932">Prod 1</span></span></td>
<td><span data-ttu-id="2b281-933">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="2b281-933">Product 1</span></span></td>
<td><span data-ttu-id="2b281-934">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-934">10001</span></span></td>
<td><span data-ttu-id="2b281-935">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-935">Electricity</span></span></td>
<td><span data-ttu-id="2b281-936">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-936">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2b281-937">2,507.09</span></span></td>
<td><span data-ttu-id="2b281-938">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b281-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-939">Prod 2</span></span></td>
<td><span data-ttu-id="2b281-940">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="2b281-940">Product 2</span></span></td>
<td><span data-ttu-id="2b281-941">10001</span><span class="sxs-lookup"><span data-stu-id="2b281-941">10001</span></span></td>
<td><span data-ttu-id="2b281-942">Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-942">Electricity</span></span></td>
<td><span data-ttu-id="2b281-943">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-943">Variable cost</span></span></td>
<td><span data-ttu-id="2b281-944">470.08</span><span class="sxs-lookup"><span data-stu-id="2b281-944">470.08</span></span></td>
<td><span data-ttu-id="2b281-945">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="2b281-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="2b281-946">Conclusione</span><span class="sxs-lookup"><span data-stu-id="2b281-946">Conclusion</span></span>
<span data-ttu-id="2b281-947">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="2b281-948">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="2b281-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="2b281-949">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="2b281-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="2b281-950">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="2b281-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="2b281-951">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="2b281-952">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="2b281-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="2b281-953">Totale</span><span class="sxs-lookup"><span data-stu-id="2b281-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2b281-954">CC099</span><span class="sxs-lookup"><span data-stu-id="2b281-954">CC099</span></span></th>
<th><span data-ttu-id="2b281-955">CC001</span><span class="sxs-lookup"><span data-stu-id="2b281-955">CC001</span></span></th>
<th><span data-ttu-id="2b281-956">CC002</span><span class="sxs-lookup"><span data-stu-id="2b281-956">CC002</span></span></th>
<th><span data-ttu-id="2b281-957">CC003</span><span class="sxs-lookup"><span data-stu-id="2b281-957">CC003</span></span></th>
<th><span data-ttu-id="2b281-958">CC004</span><span class="sxs-lookup"><span data-stu-id="2b281-958">CC004</span></span></th>
<th><span data-ttu-id="2b281-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2b281-959">Proj 1</span></span></th>
<th><span data-ttu-id="2b281-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2b281-960">Proj 2</span></span></th>
<th><span data-ttu-id="2b281-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2b281-961">Prod 1</span></span></th>
<th><span data-ttu-id="2b281-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2b281-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="2b281-963">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="2b281-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2b281-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="2b281-973">Non classificato</span><span class="sxs-lookup"><span data-stu-id="2b281-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-974">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="2b281-975">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="2b281-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-976">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-977">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-978">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-979">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-980">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2b281-981">776.36</span><span class="sxs-lookup"><span data-stu-id="2b281-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-982">223.64</span><span class="sxs-lookup"><span data-stu-id="2b281-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="2b281-984">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="2b281-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-985">000</span><span class="sxs-lookup"><span data-stu-id="2b281-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-986">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-987">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-988">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-989">0,00</span><span class="sxs-lookup"><span data-stu-id="2b281-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-990">30,00</span><span class="sxs-lookup"><span data-stu-id="2b281-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-991">10,00</span><span class="sxs-lookup"><span data-stu-id="2b281-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2b281-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2b281-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2b281-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2b281-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2b281-995">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="2b281-996">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b281-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="2b281-997">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="2b281-998">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="2b281-999">Per ulteriori informazioni, vedere i Criteri di rollup del costo.</span><span class="sxs-lookup"><span data-stu-id="2b281-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="2b281-1000">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="2b281-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




