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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: e57db8f4b692aa9c27916625897e268f63031782
ms.openlocfilehash: 285799d70a945c2dae1e3c65296282d5c432a243
ms.contentlocale: it-it
ms.lasthandoff: 10/30/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="d0e1c-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d0e1c-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="d0e1c-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="d0e1c-105">Term definition</span></span>
---------------

<span data-ttu-id="d0e1c-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="d0e1c-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="d0e1c-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="d0e1c-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="d0e1c-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="d0e1c-109">Rent</span></span>
-   <span data-ttu-id="d0e1c-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-110">Electricity</span></span>
-   <span data-ttu-id="d0e1c-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="d0e1c-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="d0e1c-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="d0e1c-112">Overhead calculation overview</span></span>
<span data-ttu-id="d0e1c-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="d0e1c-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="d0e1c-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="d0e1c-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="d0e1c-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="d0e1c-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="d0e1c-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="d0e1c-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-119">Version type</span></span>
-   <span data-ttu-id="d0e1c-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="d0e1c-120">Date and time</span></span>
-   <span data-ttu-id="d0e1c-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="d0e1c-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-122">Fiscal year</span></span>
-   <span data-ttu-id="d0e1c-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-123">Fiscal period</span></span>

<span data-ttu-id="d0e1c-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="d0e1c-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="d0e1c-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="d0e1c-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="d0e1c-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="d0e1c-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="d0e1c-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="d0e1c-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="d0e1c-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="d0e1c-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="d0e1c-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="d0e1c-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="d0e1c-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="d0e1c-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-140">Main account</span></span></th>
<th><span data-ttu-id="d0e1c-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-143">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-143">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-144">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-145">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-145">10001</span></span></td>
<td><span data-ttu-id="d0e1c-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-146">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="d0e1c-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="d0e1c-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="d0e1c-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="d0e1c-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-151">Define the cost behavior rule</span></span>

<span data-ttu-id="d0e1c-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="d0e1c-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="d0e1c-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="d0e1c-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="d0e1c-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="d0e1c-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="d0e1c-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="d0e1c-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="d0e1c-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-160">Journal</span></span></th>
<th><span data-ttu-id="d0e1c-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d0e1c-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d0e1c-163">Versione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-164">00001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-164">00001</span></span></td>
<td><span data-ttu-id="d0e1c-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="d0e1c-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-166">Fiscal</span></span></td>
<td><span data-ttu-id="d0e1c-167">2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-167">2017</span></span></td>
<td><span data-ttu-id="d0e1c-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-168">Period 1</span></span></td>
<td><span data-ttu-id="d0e1c-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d0e1c-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-173">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-174">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-175">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-177">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-177">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-178">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-179">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-179">10001</span></span></td>
<td><span data-ttu-id="d0e1c-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-180">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="d0e1c-181">Unclassified</span></span></td>
<td><span data-ttu-id="d0e1c-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d0e1c-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-185">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-186">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-187">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-187">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-189">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-189">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-190">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-191">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-191">10001</span></span></td>
<td><span data-ttu-id="d0e1c-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-192">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="d0e1c-193">Unclassified</span></span></td>
<td><span data-ttu-id="d0e1c-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-194">10,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-196">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-196">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-197">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-198">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-198">10001</span></span></td>
<td><span data-ttu-id="d0e1c-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-199">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="d0e1c-200">Unclassified</span></span></td>
<td><span data-ttu-id="d0e1c-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-201">-10,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-203">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-203">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-204">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-205">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-205">10001</span></span></td>
<td><span data-ttu-id="d0e1c-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-206">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-207">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-208">1,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-210">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-210">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-211">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-212">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-212">10001</span></span></td>
<td><span data-ttu-id="d0e1c-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-213">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-214">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-215">9,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-217">Per informazioni dettagliate sul comportamento costo, vedere Criteri di comportamento costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="d0e1c-218">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="d0e1c-219">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="d0e1c-220">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="d0e1c-221">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="d0e1c-222">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-222">Define the cost distribution rule</span></span>

<span data-ttu-id="d0e1c-223">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="d0e1c-224">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="d0e1c-225">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="d0e1c-226">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="d0e1c-227">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="d0e1c-228">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-229">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-229">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-230">KWH</span><span class="sxs-lookup"><span data-stu-id="d0e1c-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-231">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-231">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-232">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-232">HR</span></span></td>
<td><span data-ttu-id="d0e1c-233">1.000</span><span class="sxs-lookup"><span data-stu-id="d0e1c-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-234">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-234">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-235">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-235">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-236">6.000</span><span class="sxs-lookup"><span data-stu-id="d0e1c-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-237">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-237">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-238">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-238">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-239">0</span><span class="sxs-lookup"><span data-stu-id="d0e1c-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-240">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-241">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-241">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-242">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-242">Magnitude</span></span></th>
<th><span data-ttu-id="d0e1c-243">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-243">Allocation factor</span></span></th>
<th><span data-ttu-id="d0e1c-244">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-245">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-245">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-246">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-246">HR</span></span></td>
<td><span data-ttu-id="d0e1c-247">1.000</span><span class="sxs-lookup"><span data-stu-id="d0e1c-247">1,000</span></span></td>
<td><span data-ttu-id="d0e1c-248">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-250">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-250">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-251">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-251">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-252">6.000</span><span class="sxs-lookup"><span data-stu-id="d0e1c-252">6,000</span></span></td>
<td><span data-ttu-id="d0e1c-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d0e1c-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-255">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-255">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-256">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-256">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-257">0</span><span class="sxs-lookup"><span data-stu-id="d0e1c-257">0</span></span></td>
<td><span data-ttu-id="d0e1c-258">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-259">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-260">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="d0e1c-261">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-262">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-262">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-263">Formula</span><span class="sxs-lookup"><span data-stu-id="d0e1c-263">Formula</span></span></th>
<th><span data-ttu-id="d0e1c-264">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-264">Magnitude</span></span></th>
<th><span data-ttu-id="d0e1c-265">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-265">Allocation factor</span></span></th>
<th><span data-ttu-id="d0e1c-266">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-267">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-267">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-268">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-268">HR</span></span></td>
<td><span data-ttu-id="d0e1c-269">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d0e1c-270">1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-270">1</span></span></td>
<td><span data-ttu-id="d0e1c-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-272">500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-273">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-273">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-274">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-274">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d0e1c-276">1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-276">1</span></span></td>
<td><span data-ttu-id="d0e1c-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-278">500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-279">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-279">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-280">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-280">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d0e1c-282">0</span><span class="sxs-lookup"><span data-stu-id="d0e1c-282">0</span></span></td>
<td><span data-ttu-id="d0e1c-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-284">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d0e1c-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-286">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-286">Journal</span></span></th>
<th><span data-ttu-id="d0e1c-287">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d0e1c-288">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d0e1c-289">Versione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-290">00002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-290">00002</span></span></td>
<td><span data-ttu-id="d0e1c-291">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="d0e1c-292">Fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-292">Fiscal</span></span></td>
<td><span data-ttu-id="d0e1c-293">2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-293">2017</span></span></td>
<td><span data-ttu-id="d0e1c-294">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-294">Period 1</span></span></td>
<td><span data-ttu-id="d0e1c-295">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d0e1c-296">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-297">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-298">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-299">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-299">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-300">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-300">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-301">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-302">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-303">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-303">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-304">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-304">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-305">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-305">10001</span></span></td>
<td><span data-ttu-id="d0e1c-306">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-306">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-307">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-307">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-309">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-310">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-310">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-311">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-311">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-312">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-312">10001</span></span></td>
<td><span data-ttu-id="d0e1c-313">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-313">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-314">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-314">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-315">9.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d0e1c-316">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-317">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-318">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-318">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-319">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-319">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-320">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-320">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-321">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-322">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-322">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-323">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-323">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-324">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-324">10001</span></span></td>
<td><span data-ttu-id="d0e1c-325">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-325">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-326">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-326">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-327">-1,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-328">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-329">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-329">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-330">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-330">HR</span></span></td>
<td><span data-ttu-id="d0e1c-331">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-331">10001</span></span></td>
<td><span data-ttu-id="d0e1c-332">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-332">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-333">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-333">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-334">500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-334">500.00</span></span></td>
<td><span data-ttu-id="d0e1c-335">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-336">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-336">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-337">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-337">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-338">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-338">10001</span></span></td>
<td><span data-ttu-id="d0e1c-339">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-339">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-340">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-340">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-341">500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-341">500.00</span></span></td>
<td><span data-ttu-id="d0e1c-342">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-343">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-343">CC099</span></span></td>
<td><span data-ttu-id="d0e1c-344">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="d0e1c-344">Default cost center</span></span></td>
<td><span data-ttu-id="d0e1c-345">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-345">10001</span></span></td>
<td><span data-ttu-id="d0e1c-346">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-346">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-347">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-347">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-348">-9,000.00</span></span></td>
<td><span data-ttu-id="d0e1c-349">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-350">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-350">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-351">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-351">HR</span></span></td>
<td><span data-ttu-id="d0e1c-352">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-352">10001</span></span></td>
<td><span data-ttu-id="d0e1c-353">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-353">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-354">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-354">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-355">1,285.71</span></span></td>
<td><span data-ttu-id="d0e1c-356">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-357">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-357">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-358">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-358">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-359">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-359">10001</span></span></td>
<td><span data-ttu-id="d0e1c-360">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-360">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-361">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-361">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d0e1c-362">7,714.29</span></span></td>
<td><span data-ttu-id="d0e1c-363">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-364">Per informazioni dettagliate sulla base di allocazione e distribuzione costo, vedere Criteri di distribuzione costi e Basi di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="d0e1c-365">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="d0e1c-366">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="d0e1c-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="d0e1c-367">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="d0e1c-368">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="d0e1c-369">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="d0e1c-369">Define the overhead rate</span></span>

<span data-ttu-id="d0e1c-370">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="d0e1c-371">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-372">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-372">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-373">Ore</span><span class="sxs-lookup"><span data-stu-id="d0e1c-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-374">Proj 1</span></span></td>
<td><span data-ttu-id="d0e1c-375">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-375">Project 1</span></span></td>
<td><span data-ttu-id="d0e1c-376">3</span><span class="sxs-lookup"><span data-stu-id="d0e1c-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-377">Proj 2</span></span></td>
<td><span data-ttu-id="d0e1c-378">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-378">Project 2</span></span></td>
<td><span data-ttu-id="d0e1c-379">1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-380">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-381">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-381">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-382">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-382">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-383">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-383">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-384">Unità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-384">Units</span></span></th>
<th><span data-ttu-id="d0e1c-385">Tasso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-386">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-386">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-387">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-387">HR</span></span></td>
<td><span data-ttu-id="d0e1c-388">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-388">10001</span></span></td>
<td><span data-ttu-id="d0e1c-389">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-389">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-390">1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-390">1</span></span></td>
<td><span data-ttu-id="d0e1c-391">10</span><span class="sxs-lookup"><span data-stu-id="d0e1c-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-392">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-393">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-393">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-394">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-394">Magnitude</span></span></th>
<th><span data-ttu-id="d0e1c-395">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-395">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-396">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-396">Allocation factor</span></span></th>
<th><span data-ttu-id="d0e1c-397">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-398">Proj 1</span></span></td>
<td><span data-ttu-id="d0e1c-399">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-399">Project 1</span></span></td>
<td><span data-ttu-id="d0e1c-400">3</span><span class="sxs-lookup"><span data-stu-id="d0e1c-400">3</span></span></td>
<td><span data-ttu-id="d0e1c-401">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-401">10001</span></span></td>
<td><span data-ttu-id="d0e1c-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d0e1c-403">30,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-404">Proj 2</span></span></td>
<td><span data-ttu-id="d0e1c-405">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-405">Project 2</span></span></td>
<td><span data-ttu-id="d0e1c-406">1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-406">1</span></span></td>
<td><span data-ttu-id="d0e1c-407">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-407">10001</span></span></td>
<td><span data-ttu-id="d0e1c-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d0e1c-409">10,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d0e1c-410">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-411">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-411">Journal</span></span></th>
<th><span data-ttu-id="d0e1c-412">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d0e1c-413">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d0e1c-414">Versione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-415">00003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-415">00003</span></span></td>
<td><span data-ttu-id="d0e1c-416">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="d0e1c-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="d0e1c-417">Fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-417">Fiscal</span></span></td>
<td><span data-ttu-id="d0e1c-418">2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-418">2017</span></span></td>
<td><span data-ttu-id="d0e1c-419">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-419">Period 1</span></span></td>
<td><span data-ttu-id="d0e1c-420">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="d0e1c-421">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-422">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-423">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-423">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-424">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-425">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-426">Proj 1</span></span></td>
<td><span data-ttu-id="d0e1c-427">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d0e1c-428">3,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-429">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-430">Proj 2</span></span></td>
<td><span data-ttu-id="d0e1c-431">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d0e1c-432">1,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d0e1c-433">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-434">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-435">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-435">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-436">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-436">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-437">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-437">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-438">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-439">CC0001</span></span></td>
<td><span data-ttu-id="d0e1c-440">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-440">HR</span></span></td>
<td><span data-ttu-id="d0e1c-441">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-441">10001</span></span></td>
<td><span data-ttu-id="d0e1c-442">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-442">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-443">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-443">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-444">-30.00</span></span></td>
<td><span data-ttu-id="d0e1c-445">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-446">Proj 1</span></span></td>
<td><span data-ttu-id="d0e1c-447">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d0e1c-448">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-448">10001</span></span></td>
<td><span data-ttu-id="d0e1c-449">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-449">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-450">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-450">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-451">30,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-451">30.00</span></span></td>
<td><span data-ttu-id="d0e1c-452">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-453">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-453">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-454">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-454">HR</span></span></td>
<td><span data-ttu-id="d0e1c-455">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-455">10001</span></span></td>
<td><span data-ttu-id="d0e1c-456">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-456">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-457">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-457">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-458">-10.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-458">-10.00</span></span></td>
<td><span data-ttu-id="d0e1c-459">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-460">Proj 2</span></span></td>
<td><span data-ttu-id="d0e1c-461">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d0e1c-462">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-462">10001</span></span></td>
<td><span data-ttu-id="d0e1c-463">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-463">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-464">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-464">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-465">10,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-465">10.00</span></span></td>
<td><span data-ttu-id="d0e1c-466">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-467">Per informazioni dettagliate sui criteri di tasso generali, vedere Criterio di tasso generale e Basi di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="d0e1c-468">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="d0e1c-469">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="d0e1c-470">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="d0e1c-471">Finance and Operations supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="d0e1c-472">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="d0e1c-473">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="d0e1c-474">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="d0e1c-475">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="d0e1c-476">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="d0e1c-477">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="d0e1c-478">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="d0e1c-478">Define the cost allocation</span></span>

<span data-ttu-id="d0e1c-479">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="d0e1c-480">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="d0e1c-481">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-482">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-482">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-483">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="d0e1c-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-484">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-484">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-485">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-485">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-486">35</span><span class="sxs-lookup"><span data-stu-id="d0e1c-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-487">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-487">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-488">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-488">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-489">55</span><span class="sxs-lookup"><span data-stu-id="d0e1c-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-490">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-490">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-491">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-491">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-492">10</span><span class="sxs-lookup"><span data-stu-id="d0e1c-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-493">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="d0e1c-494">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-495">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-495">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-496">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-497">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-497">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-498">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-498">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-499">65</span><span class="sxs-lookup"><span data-stu-id="d0e1c-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-500">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-500">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-501">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-501">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-502">35</span><span class="sxs-lookup"><span data-stu-id="d0e1c-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-503">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="d0e1c-504">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-505">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-505">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-506">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-507">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-508">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-508">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-509">60</span><span class="sxs-lookup"><span data-stu-id="d0e1c-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-510">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-511">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-511">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-512">20</span><span class="sxs-lookup"><span data-stu-id="d0e1c-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-513">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="d0e1c-514">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-515">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-515">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-516">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-517">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-518">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-518">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-519">80</span><span class="sxs-lookup"><span data-stu-id="d0e1c-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-520">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-521">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-521">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-522">15</span><span class="sxs-lookup"><span data-stu-id="d0e1c-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-523">**Nota**: in Finance and Operations, le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="d0e1c-524">Per informazioni più dettagliate sui provider misure statistiche, vedere il modello provider misure statistiche.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="d0e1c-525">(Nota: questo argomento non è ancora completo ma sarà presto disponibile). Nella tabella seguente viene illustrato il risultato ottenuto quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-526">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-526">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-527">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-527">Magnitude</span></span></th>
<th><span data-ttu-id="d0e1c-528">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-528">Allocation factor</span></span></th>
<th><span data-ttu-id="d0e1c-529">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-529">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-530">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-531">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-531">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-532">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-532">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-533">35</span><span class="sxs-lookup"><span data-stu-id="d0e1c-533">35</span></span></td>
<td><span data-ttu-id="d0e1c-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d0e1c-535">175.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-535">175.00</span></span></td>
<td><span data-ttu-id="d0e1c-536">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-537">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-537">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-538">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-538">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-539">55</span><span class="sxs-lookup"><span data-stu-id="d0e1c-539">55</span></span></td>
<td><span data-ttu-id="d0e1c-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d0e1c-541">275.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-541">275.00</span></span></td>
<td><span data-ttu-id="d0e1c-542">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-543">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-543">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-544">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-544">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-545">10</span><span class="sxs-lookup"><span data-stu-id="d0e1c-545">10</span></span></td>
<td><span data-ttu-id="d0e1c-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d0e1c-547">50,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-547">50.00</span></span></td>
<td><span data-ttu-id="d0e1c-548">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-549">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-549">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-550">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-550">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-551">35</span><span class="sxs-lookup"><span data-stu-id="d0e1c-551">35</span></span></td>
<td><span data-ttu-id="d0e1c-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d0e1c-553">436.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-553">436.00</span></span></td>
<td><span data-ttu-id="d0e1c-554">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-555">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-555">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-556">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-556">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-557">55</span><span class="sxs-lookup"><span data-stu-id="d0e1c-557">55</span></span></td>
<td><span data-ttu-id="d0e1c-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d0e1c-559">685.14</span><span class="sxs-lookup"><span data-stu-id="d0e1c-559">685.14</span></span></td>
<td><span data-ttu-id="d0e1c-560">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-561">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-561">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-562">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-562">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-563">10</span><span class="sxs-lookup"><span data-stu-id="d0e1c-563">10</span></span></td>
<td><span data-ttu-id="d0e1c-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d0e1c-565">124.57</span><span class="sxs-lookup"><span data-stu-id="d0e1c-565">124.57</span></span></td>
<td><span data-ttu-id="d0e1c-566">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-567">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-568">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-568">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-569">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-569">Magnitude</span></span></th>
<th><span data-ttu-id="d0e1c-570">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-570">Allocation factor</span></span></th>
<th><span data-ttu-id="d0e1c-571">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-571">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-572">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-573">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-573">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-574">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-574">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-575">65</span><span class="sxs-lookup"><span data-stu-id="d0e1c-575">65</span></span></td>
<td><span data-ttu-id="d0e1c-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d0e1c-577">438.75</span><span class="sxs-lookup"><span data-stu-id="d0e1c-577">438.75</span></span></td>
<td><span data-ttu-id="d0e1c-578">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-579">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-579">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-580">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-580">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-581">35</span><span class="sxs-lookup"><span data-stu-id="d0e1c-581">35</span></span></td>
<td><span data-ttu-id="d0e1c-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d0e1c-583">236.25</span><span class="sxs-lookup"><span data-stu-id="d0e1c-583">236.25</span></span></td>
<td><span data-ttu-id="d0e1c-584">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-585">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-585">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-586">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-586">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-587">65</span><span class="sxs-lookup"><span data-stu-id="d0e1c-587">65</span></span></td>
<td><span data-ttu-id="d0e1c-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d0e1c-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d0e1c-589">5,297.69</span></span></td>
<td><span data-ttu-id="d0e1c-590">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-591">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-591">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-592">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-592">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-593">35</span><span class="sxs-lookup"><span data-stu-id="d0e1c-593">35</span></span></td>
<td><span data-ttu-id="d0e1c-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d0e1c-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d0e1c-595">2,852.60</span></span></td>
<td><span data-ttu-id="d0e1c-596">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-597">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-598">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-598">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-599">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-599">Magnitude</span></span></th>
<th><span data-ttu-id="d0e1c-600">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-600">Allocation factor</span></span></th>
<th><span data-ttu-id="d0e1c-601">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-601">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-602">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-603">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-604">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-604">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-605">60</span><span class="sxs-lookup"><span data-stu-id="d0e1c-605">60</span></span></td>
<td><span data-ttu-id="d0e1c-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d0e1c-607">535.31</span><span class="sxs-lookup"><span data-stu-id="d0e1c-607">535.31</span></span></td>
<td><span data-ttu-id="d0e1c-608">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-609">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-610">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-610">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-611">20</span><span class="sxs-lookup"><span data-stu-id="d0e1c-611">20</span></span></td>
<td><span data-ttu-id="d0e1c-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d0e1c-613">178.44</span><span class="sxs-lookup"><span data-stu-id="d0e1c-613">178.44</span></span></td>
<td><span data-ttu-id="d0e1c-614">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-615">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-616">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-616">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-617">60</span><span class="sxs-lookup"><span data-stu-id="d0e1c-617">60</span></span></td>
<td><span data-ttu-id="d0e1c-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d0e1c-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d0e1c-619">4,487.12</span></span></td>
<td><span data-ttu-id="d0e1c-620">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-621">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-622">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-622">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-623">20</span><span class="sxs-lookup"><span data-stu-id="d0e1c-623">20</span></span></td>
<td><span data-ttu-id="d0e1c-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d0e1c-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-625">1,495.71</span></span></td>
<td><span data-ttu-id="d0e1c-626">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d0e1c-627">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-628">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-628">Cost object</span></span></th>
<th><span data-ttu-id="d0e1c-629">Grandezza</span><span class="sxs-lookup"><span data-stu-id="d0e1c-629">Magnitude</span></span></th>
<th><span data-ttu-id="d0e1c-630">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-630">Allocation factor</span></span></th>
<th><span data-ttu-id="d0e1c-631">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-631">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-632">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-633">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-634">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-634">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-635">80</span><span class="sxs-lookup"><span data-stu-id="d0e1c-635">80</span></span></td>
<td><span data-ttu-id="d0e1c-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d0e1c-637">241.05</span><span class="sxs-lookup"><span data-stu-id="d0e1c-637">241.05</span></span></td>
<td><span data-ttu-id="d0e1c-638">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-639">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-640">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-640">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-641">15</span><span class="sxs-lookup"><span data-stu-id="d0e1c-641">15</span></span></td>
<td><span data-ttu-id="d0e1c-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d0e1c-643">45.20</span><span class="sxs-lookup"><span data-stu-id="d0e1c-643">45.20</span></span></td>
<td><span data-ttu-id="d0e1c-644">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-645">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-646">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-646">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-647">80</span><span class="sxs-lookup"><span data-stu-id="d0e1c-647">80</span></span></td>
<td><span data-ttu-id="d0e1c-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d0e1c-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d0e1c-649">2,507.09</span></span></td>
<td><span data-ttu-id="d0e1c-650">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-651">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-652">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-652">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-653">15</span><span class="sxs-lookup"><span data-stu-id="d0e1c-653">15</span></span></td>
<td><span data-ttu-id="d0e1c-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d0e1c-655">470.08</span><span class="sxs-lookup"><span data-stu-id="d0e1c-655">470.08</span></span></td>
<td><span data-ttu-id="d0e1c-656">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d0e1c-657">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="d0e1c-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-658">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-658">Journal</span></span></th>
<th><span data-ttu-id="d0e1c-659">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d0e1c-660">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d0e1c-661">Versione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-662">00004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-662">00004</span></span></td>
<td><span data-ttu-id="d0e1c-663">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="d0e1c-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="d0e1c-664">Fiscale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-664">Fiscal</span></span></td>
<td><span data-ttu-id="d0e1c-665">2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-665">2017</span></span></td>
<td><span data-ttu-id="d0e1c-666">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-666">Period 1</span></span></td>
<td><span data-ttu-id="d0e1c-667">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="d0e1c-668">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d0e1c-669">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-670">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-671">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-671">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-672">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-672">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-673">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-674">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-675">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-675">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-676">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-676">HR</span></span></td>
<td><span data-ttu-id="d0e1c-677">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-677">10001</span></span></td>
<td><span data-ttu-id="d0e1c-678">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-678">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-679">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-679">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-680">500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-681">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-682">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-682">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-683">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-683">HR</span></span></td>
<td><span data-ttu-id="d0e1c-684">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-684">10001</span></span></td>
<td><span data-ttu-id="d0e1c-685">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-685">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-686">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-686">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-688">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-689">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-689">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-690">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-690">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-691">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-691">10001</span></span></td>
<td><span data-ttu-id="d0e1c-692">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-692">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-693">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-693">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-694">675.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-695">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-696">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-696">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-697">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-697">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-698">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-698">10001</span></span></td>
<td><span data-ttu-id="d0e1c-699">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-699">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-700">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-700">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="d0e1c-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-702">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-703">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-703">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-704">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-704">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-705">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-705">10001</span></span></td>
<td><span data-ttu-id="d0e1c-706">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-706">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-707">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-707">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-708">713.75</span><span class="sxs-lookup"><span data-stu-id="d0e1c-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-709">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-710">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-710">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-711">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-711">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-712">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-712">10001</span></span></td>
<td><span data-ttu-id="d0e1c-713">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-713">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-714">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-714">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="d0e1c-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-716">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-717">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-717">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-718">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-718">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-719">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-719">10001</span></span></td>
<td><span data-ttu-id="d0e1c-720">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-720">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-721">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-721">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-722">286.25</span><span class="sxs-lookup"><span data-stu-id="d0e1c-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-723">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-724">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-724">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-725">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-725">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-726">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-726">10001</span></span></td>
<td><span data-ttu-id="d0e1c-727">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-727">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-728">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-728">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="d0e1c-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-730">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-731">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-732">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-732">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-733">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-733">10001</span></span></td>
<td><span data-ttu-id="d0e1c-734">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-734">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-735">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-735">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-736">776.36</span><span class="sxs-lookup"><span data-stu-id="d0e1c-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-737">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-738">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-739">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-739">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-740">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-740">10001</span></span></td>
<td><span data-ttu-id="d0e1c-741">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-741">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-742">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-742">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d0e1c-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-744">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-745">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-746">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-746">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-747">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-747">10001</span></span></td>
<td><span data-ttu-id="d0e1c-748">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-748">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-749">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-749">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-750">223.64</span><span class="sxs-lookup"><span data-stu-id="d0e1c-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-751">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="d0e1c-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-752">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-753">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-753">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-754">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-754">10001</span></span></td>
<td><span data-ttu-id="d0e1c-755">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-755">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-756">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-756">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d0e1c-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d0e1c-758">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d0e1c-759">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d0e1c-760">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-760">Cost element</span></span></th>
<th><span data-ttu-id="d0e1c-761">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-761">Cost behavior</span></span></th>
<th><span data-ttu-id="d0e1c-762">Importo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-762">Amount</span></span></th>
<th><span data-ttu-id="d0e1c-763">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d0e1c-764">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-764">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-765">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-765">HR</span></span></td>
<td><span data-ttu-id="d0e1c-766">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-766">10001</span></span></td>
<td><span data-ttu-id="d0e1c-767">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-767">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-768">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-768">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-769">-500.00</span></span></td>
<td><span data-ttu-id="d0e1c-770">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-771">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-771">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-772">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-772">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-773">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-773">10001</span></span></td>
<td><span data-ttu-id="d0e1c-774">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-774">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-775">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-775">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-776">175.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-776">175.00</span></span></td>
<td><span data-ttu-id="d0e1c-777">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-778">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-778">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-779">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-779">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-780">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-780">10001</span></span></td>
<td><span data-ttu-id="d0e1c-781">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-781">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-782">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-782">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-783">275.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-783">275.00</span></span></td>
<td><span data-ttu-id="d0e1c-784">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-785">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-785">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-786">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-786">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-787">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-787">10001</span></span></td>
<td><span data-ttu-id="d0e1c-788">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-788">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-789">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-789">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-790">50,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-790">50,00</span></span></td>
<td><span data-ttu-id="d0e1c-791">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-792">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-792">CC001</span></span></td>
<td><span data-ttu-id="d0e1c-793">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="d0e1c-793">HR</span></span></td>
<td><span data-ttu-id="d0e1c-794">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-794">10001</span></span></td>
<td><span data-ttu-id="d0e1c-795">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-795">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-796">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-796">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-797">-1,245.71</span></span></td>
<td><span data-ttu-id="d0e1c-798">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-799">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-799">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-800">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-800">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-801">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-801">10001</span></span></td>
<td><span data-ttu-id="d0e1c-802">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-802">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-803">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-803">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-804">436.00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-804">436.00</span></span></td>
<td><span data-ttu-id="d0e1c-805">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-806">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-806">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-807">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-807">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-808">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-808">10001</span></span></td>
<td><span data-ttu-id="d0e1c-809">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-809">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-810">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-810">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-811">685.14</span><span class="sxs-lookup"><span data-stu-id="d0e1c-811">685.14</span></span></td>
<td><span data-ttu-id="d0e1c-812">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-813">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-813">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-814">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-814">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-815">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-815">10001</span></span></td>
<td><span data-ttu-id="d0e1c-816">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-816">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-817">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-817">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-818">124.57</span><span class="sxs-lookup"><span data-stu-id="d0e1c-818">124.57</span></span></td>
<td><span data-ttu-id="d0e1c-819">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-820">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-820">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-821">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-821">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-822">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-822">10001</span></span></td>
<td><span data-ttu-id="d0e1c-823">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-823">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-824">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-824">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-825">-675.00</span></span></td>
<td><span data-ttu-id="d0e1c-826">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-827">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-827">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-828">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-828">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-829">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-829">10001</span></span></td>
<td><span data-ttu-id="d0e1c-830">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-830">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-831">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-831">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-832">438.75</span><span class="sxs-lookup"><span data-stu-id="d0e1c-832">438.75</span></span></td>
<td><span data-ttu-id="d0e1c-833">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-834">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-834">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-835">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-835">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-836">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-836">10001</span></span></td>
<td><span data-ttu-id="d0e1c-837">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-837">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-838">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-838">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-839">236.25</span><span class="sxs-lookup"><span data-stu-id="d0e1c-839">236.25</span></span></td>
<td><span data-ttu-id="d0e1c-840">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-841">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-841">CC002</span></span></td>
<td><span data-ttu-id="d0e1c-842">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="d0e1c-842">Finance</span></span></td>
<td><span data-ttu-id="d0e1c-843">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-843">10001</span></span></td>
<td><span data-ttu-id="d0e1c-844">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-844">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-845">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-845">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="d0e1c-846">-8,150.29</span></span></td>
<td><span data-ttu-id="d0e1c-847">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-848">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-848">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-849">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-849">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-850">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-850">10001</span></span></td>
<td><span data-ttu-id="d0e1c-851">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-851">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-852">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-852">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d0e1c-853">5,297.69</span></span></td>
<td><span data-ttu-id="d0e1c-854">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-855">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-855">CC004</span></span></td>
<td><span data-ttu-id="d0e1c-856">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-856">Packaging</span></span></td>
<td><span data-ttu-id="d0e1c-857">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-857">10001</span></span></td>
<td><span data-ttu-id="d0e1c-858">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-858">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-859">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-859">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d0e1c-860">2,852.60</span></span></td>
<td><span data-ttu-id="d0e1c-861">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-862">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-862">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-863">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-863">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-864">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-864">10001</span></span></td>
<td><span data-ttu-id="d0e1c-865">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-865">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-866">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-866">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="d0e1c-867">-713.75</span></span></td>
<td><span data-ttu-id="d0e1c-868">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-869">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-870">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-870">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-871">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-871">10001</span></span></td>
<td><span data-ttu-id="d0e1c-872">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-872">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-873">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-873">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-874">535.31</span><span class="sxs-lookup"><span data-stu-id="d0e1c-874">535.31</span></span></td>
<td><span data-ttu-id="d0e1c-875">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-876">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-877">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-877">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-878">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-878">10001</span></span></td>
<td><span data-ttu-id="d0e1c-879">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-879">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-880">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-880">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-881">178.44</span><span class="sxs-lookup"><span data-stu-id="d0e1c-881">178.44</span></span></td>
<td><span data-ttu-id="d0e1c-882">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-883">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-883">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-884">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-884">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-885">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-885">10001</span></span></td>
<td><span data-ttu-id="d0e1c-886">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-886">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-887">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-887">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="d0e1c-888">-5,982.83</span></span></td>
<td><span data-ttu-id="d0e1c-889">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-890">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-891">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-891">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-892">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-892">10001</span></span></td>
<td><span data-ttu-id="d0e1c-893">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-893">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-894">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-894">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d0e1c-895">4,487.12</span></span></td>
<td><span data-ttu-id="d0e1c-896">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-897">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-898">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-898">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-899">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-899">10001</span></span></td>
<td><span data-ttu-id="d0e1c-900">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-900">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-901">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-901">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d0e1c-902">1,495.71</span></span></td>
<td><span data-ttu-id="d0e1c-903">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-904">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-904">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-905">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-905">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-906">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-906">10001</span></span></td>
<td><span data-ttu-id="d0e1c-907">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-907">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-908">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-908">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="d0e1c-909">-286.25</span></span></td>
<td><span data-ttu-id="d0e1c-910">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-911">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-912">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-912">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-913">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-913">10001</span></span></td>
<td><span data-ttu-id="d0e1c-914">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-914">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-915">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-915">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-916">241.05</span><span class="sxs-lookup"><span data-stu-id="d0e1c-916">241.05</span></span></td>
<td><span data-ttu-id="d0e1c-917">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-918">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-919">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-919">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-920">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-920">10001</span></span></td>
<td><span data-ttu-id="d0e1c-921">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-921">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-922">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-922">Fixed cost</span></span></td>
<td><span data-ttu-id="d0e1c-923">45.20</span><span class="sxs-lookup"><span data-stu-id="d0e1c-923">45.20</span></span></td>
<td><span data-ttu-id="d0e1c-924">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-925">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-925">CC003</span></span></td>
<td><span data-ttu-id="d0e1c-926">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="d0e1c-926">Assembly</span></span></td>
<td><span data-ttu-id="d0e1c-927">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-927">10001</span></span></td>
<td><span data-ttu-id="d0e1c-928">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-928">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-929">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-929">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="d0e1c-930">-2,977.17</span></span></td>
<td><span data-ttu-id="d0e1c-931">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-932">Prod 1</span></span></td>
<td><span data-ttu-id="d0e1c-933">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-933">Product 1</span></span></td>
<td><span data-ttu-id="d0e1c-934">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-934">10001</span></span></td>
<td><span data-ttu-id="d0e1c-935">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-935">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-936">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-936">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d0e1c-937">2,507.09</span></span></td>
<td><span data-ttu-id="d0e1c-938">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d0e1c-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-939">Prod 2</span></span></td>
<td><span data-ttu-id="d0e1c-940">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-940">Product 2</span></span></td>
<td><span data-ttu-id="d0e1c-941">10001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-941">10001</span></span></td>
<td><span data-ttu-id="d0e1c-942">Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-942">Electricity</span></span></td>
<td><span data-ttu-id="d0e1c-943">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-943">Variable cost</span></span></td>
<td><span data-ttu-id="d0e1c-944">470.08</span><span class="sxs-lookup"><span data-stu-id="d0e1c-944">470.08</span></span></td>
<td><span data-ttu-id="d0e1c-945">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="d0e1c-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="d0e1c-946">Conclusione</span><span class="sxs-lookup"><span data-stu-id="d0e1c-946">Conclusion</span></span>
<span data-ttu-id="d0e1c-947">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="d0e1c-948">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="d0e1c-949">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="d0e1c-950">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="d0e1c-951">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="d0e1c-952">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="d0e1c-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="d0e1c-953">Totale</span><span class="sxs-lookup"><span data-stu-id="d0e1c-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d0e1c-954">CC099</span><span class="sxs-lookup"><span data-stu-id="d0e1c-954">CC099</span></span></th>
<th><span data-ttu-id="d0e1c-955">CC001</span><span class="sxs-lookup"><span data-stu-id="d0e1c-955">CC001</span></span></th>
<th><span data-ttu-id="d0e1c-956">CC002</span><span class="sxs-lookup"><span data-stu-id="d0e1c-956">CC002</span></span></th>
<th><span data-ttu-id="d0e1c-957">CC003</span><span class="sxs-lookup"><span data-stu-id="d0e1c-957">CC003</span></span></th>
<th><span data-ttu-id="d0e1c-958">CC004</span><span class="sxs-lookup"><span data-stu-id="d0e1c-958">CC004</span></span></th>
<th><span data-ttu-id="d0e1c-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-959">Proj 1</span></span></th>
<th><span data-ttu-id="d0e1c-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-960">Proj 2</span></span></th>
<th><span data-ttu-id="d0e1c-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d0e1c-961">Prod 1</span></span></th>
<th><span data-ttu-id="d0e1c-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d0e1c-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="d0e1c-963">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="d0e1c-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="d0e1c-973">Non classificato</span><span class="sxs-lookup"><span data-stu-id="d0e1c-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-974">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="d0e1c-975">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="d0e1c-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-976">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-977">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-978">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-979">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-980">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-981">776.36</span><span class="sxs-lookup"><span data-stu-id="d0e1c-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-982">223.64</span><span class="sxs-lookup"><span data-stu-id="d0e1c-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="d0e1c-984">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="d0e1c-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-985">000</span><span class="sxs-lookup"><span data-stu-id="d0e1c-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-986">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-987">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-988">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-989">0,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-990">30,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-991">10,00</span><span class="sxs-lookup"><span data-stu-id="d0e1c-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d0e1c-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d0e1c-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d0e1c-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d0e1c-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d0e1c-995">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="d0e1c-996">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="d0e1c-997">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="d0e1c-998">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="d0e1c-999">Per ulteriori informazioni, vedere i Criteri di rollup del costo.</span><span class="sxs-lookup"><span data-stu-id="d0e1c-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="d0e1c-1000">(Nota: questo argomento non è ancora completo ma sarà presto disponibile).</span><span class="sxs-lookup"><span data-stu-id="d0e1c-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




