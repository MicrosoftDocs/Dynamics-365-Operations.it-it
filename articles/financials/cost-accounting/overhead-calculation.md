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
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "335119"
---
# <a name="overhead-calculation"></a><span data-ttu-id="12629-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="12629-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12629-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="12629-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="12629-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="12629-105">Term definition</span></span>
---------------

<span data-ttu-id="12629-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="12629-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="12629-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="12629-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="12629-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="12629-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="12629-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="12629-109">Rent</span></span>
-   <span data-ttu-id="12629-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-110">Electricity</span></span>
-   <span data-ttu-id="12629-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="12629-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="12629-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="12629-112">Overhead calculation overview</span></span>
<span data-ttu-id="12629-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="12629-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="12629-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="12629-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="12629-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="12629-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="12629-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="12629-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="12629-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="12629-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="12629-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="12629-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="12629-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="12629-119">Version type</span></span>
-   <span data-ttu-id="12629-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="12629-120">Date and time</span></span>
-   <span data-ttu-id="12629-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="12629-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="12629-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-122">Fiscal year</span></span>
-   <span data-ttu-id="12629-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-123">Fiscal period</span></span>

<span data-ttu-id="12629-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="12629-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="12629-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="12629-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="12629-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="12629-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="12629-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="12629-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="12629-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="12629-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="12629-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="12629-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="12629-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="12629-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="12629-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="12629-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="12629-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="12629-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="12629-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="12629-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="12629-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="12629-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="12629-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="12629-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="12629-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="12629-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="12629-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="12629-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="12629-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="12629-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="12629-140">Main account</span></span></th>
<th><span data-ttu-id="12629-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="12629-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="12629-143">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-143">CC099</span></span></td>
<td><span data-ttu-id="12629-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-144">Default cost center</span></span></td>
<td><span data-ttu-id="12629-145">10001</span><span class="sxs-lookup"><span data-stu-id="12629-145">10001</span></span></td>
<td><span data-ttu-id="12629-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-146">Electricity</span></span></td>
<td><span data-ttu-id="12629-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="12629-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="12629-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="12629-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="12629-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="12629-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="12629-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-151">Define the cost behavior rule</span></span>

<span data-ttu-id="12629-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="12629-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="12629-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="12629-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="12629-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="12629-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="12629-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="12629-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="12629-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="12629-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="12629-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="12629-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="12629-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="12629-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-160">Journal</span></span></th>
<th><span data-ttu-id="12629-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="12629-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="12629-163">Versione</span><span class="sxs-lookup"><span data-stu-id="12629-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-164">00001</span><span class="sxs-lookup"><span data-stu-id="12629-164">00001</span></span></td>
<td><span data-ttu-id="12629-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="12629-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-166">Fiscal</span></span></td>
<td><span data-ttu-id="12629-167">2017</span><span class="sxs-lookup"><span data-stu-id="12629-167">2017</span></span></td>
<td><span data-ttu-id="12629-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-168">Period 1</span></span></td>
<td><span data-ttu-id="12629-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="12629-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="12629-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="12629-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="12629-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-173">Cost element</span></span></th>
<th><span data-ttu-id="12629-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-174">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-175">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="12629-177">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-177">CC099</span></span></td>
<td><span data-ttu-id="12629-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-178">Default cost center</span></span></td>
<td><span data-ttu-id="12629-179">10001</span><span class="sxs-lookup"><span data-stu-id="12629-179">10001</span></span></td>
<td><span data-ttu-id="12629-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-180">Electricity</span></span></td>
<td><span data-ttu-id="12629-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="12629-181">Unclassified</span></span></td>
<td><span data-ttu-id="12629-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="12629-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="12629-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="12629-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-185">Cost element</span></span></th>
<th><span data-ttu-id="12629-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-186">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-187">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-187">Amount</span></span></th>
<th><span data-ttu-id="12629-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-189">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-189">CC099</span></span></td>
<td><span data-ttu-id="12629-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-190">Default cost center</span></span></td>
<td><span data-ttu-id="12629-191">10001</span><span class="sxs-lookup"><span data-stu-id="12629-191">10001</span></span></td>
<td><span data-ttu-id="12629-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-192">Electricity</span></span></td>
<td><span data-ttu-id="12629-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="12629-193">Unclassified</span></span></td>
<td><span data-ttu-id="12629-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-194">10,000.00</span></span></td>
<td><span data-ttu-id="12629-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-196">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-196">CC099</span></span></td>
<td><span data-ttu-id="12629-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-197">Default cost center</span></span></td>
<td><span data-ttu-id="12629-198">10001</span><span class="sxs-lookup"><span data-stu-id="12629-198">10001</span></span></td>
<td><span data-ttu-id="12629-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-199">Electricity</span></span></td>
<td><span data-ttu-id="12629-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="12629-200">Unclassified</span></span></td>
<td><span data-ttu-id="12629-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-201">-10,000.00</span></span></td>
<td><span data-ttu-id="12629-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-203">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-203">CC099</span></span></td>
<td><span data-ttu-id="12629-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-204">Default cost center</span></span></td>
<td><span data-ttu-id="12629-205">10001</span><span class="sxs-lookup"><span data-stu-id="12629-205">10001</span></span></td>
<td><span data-ttu-id="12629-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-206">Electricity</span></span></td>
<td><span data-ttu-id="12629-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-207">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-208">1,000.00</span></span></td>
<td><span data-ttu-id="12629-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-210">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-210">CC099</span></span></td>
<td><span data-ttu-id="12629-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-211">Default cost center</span></span></td>
<td><span data-ttu-id="12629-212">10001</span><span class="sxs-lookup"><span data-stu-id="12629-212">10001</span></span></td>
<td><span data-ttu-id="12629-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-213">Electricity</span></span></td>
<td><span data-ttu-id="12629-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-214">Variable cost</span></span></td>
<td><span data-ttu-id="12629-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-215">9,000.00</span></span></td>
<td><span data-ttu-id="12629-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="12629-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="12629-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="12629-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="12629-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="12629-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="12629-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="12629-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="12629-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="12629-221">Define the cost distribution rule</span></span>

<span data-ttu-id="12629-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="12629-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="12629-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="12629-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="12629-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="12629-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="12629-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="12629-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="12629-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="12629-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="12629-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="12629-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-228">Cost object</span></span></th>
<th><span data-ttu-id="12629-229">KWH</span><span class="sxs-lookup"><span data-stu-id="12629-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-230">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-230">CC001</span></span></td>
<td><span data-ttu-id="12629-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-231">HR</span></span></td>
<td><span data-ttu-id="12629-232">1.000</span><span class="sxs-lookup"><span data-stu-id="12629-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-233">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-233">CC002</span></span></td>
<td><span data-ttu-id="12629-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-234">Finance</span></span></td>
<td><span data-ttu-id="12629-235">6.000</span><span class="sxs-lookup"><span data-stu-id="12629-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-236">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-236">CC003</span></span></td>
<td><span data-ttu-id="12629-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-237">Assembly</span></span></td>
<td><span data-ttu-id="12629-238">0</span><span class="sxs-lookup"><span data-stu-id="12629-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="12629-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-240">Cost object</span></span></th>
<th><span data-ttu-id="12629-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-241">Magnitude</span></span></th>
<th><span data-ttu-id="12629-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="12629-242">Allocation factor</span></span></th>
<th><span data-ttu-id="12629-243">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-244">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-244">CC001</span></span></td>
<td><span data-ttu-id="12629-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-245">HR</span></span></td>
<td><span data-ttu-id="12629-246">1.000</span><span class="sxs-lookup"><span data-stu-id="12629-246">1,000</span></span></td>
<td><span data-ttu-id="12629-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="12629-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="12629-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-249">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-249">CC002</span></span></td>
<td><span data-ttu-id="12629-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-250">Finance</span></span></td>
<td><span data-ttu-id="12629-251">6.000</span><span class="sxs-lookup"><span data-stu-id="12629-251">6,000</span></span></td>
<td><span data-ttu-id="12629-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="12629-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="12629-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-254">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-254">CC003</span></span></td>
<td><span data-ttu-id="12629-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-255">Assembly</span></span></td>
<td><span data-ttu-id="12629-256">0</span><span class="sxs-lookup"><span data-stu-id="12629-256">0</span></span></td>
<td><span data-ttu-id="12629-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="12629-258">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="12629-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="12629-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="12629-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-261">Cost object</span></span></th>
<th><span data-ttu-id="12629-262">Formula</span><span class="sxs-lookup"><span data-stu-id="12629-262">Formula</span></span></th>
<th><span data-ttu-id="12629-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-263">Magnitude</span></span></th>
<th><span data-ttu-id="12629-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="12629-264">Allocation factor</span></span></th>
<th><span data-ttu-id="12629-265">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-266">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-266">CC001</span></span></td>
<td><span data-ttu-id="12629-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-267">HR</span></span></td>
<td><span data-ttu-id="12629-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="12629-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="12629-269">1</span><span class="sxs-lookup"><span data-stu-id="12629-269">1</span></span></td>
<td><span data-ttu-id="12629-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="12629-271">500,00</span><span class="sxs-lookup"><span data-stu-id="12629-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-272">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-272">CC002</span></span></td>
<td><span data-ttu-id="12629-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-273">Finance</span></span></td>
<td><span data-ttu-id="12629-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="12629-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="12629-275">1</span><span class="sxs-lookup"><span data-stu-id="12629-275">1</span></span></td>
<td><span data-ttu-id="12629-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="12629-277">500,00</span><span class="sxs-lookup"><span data-stu-id="12629-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-278">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-278">CC003</span></span></td>
<td><span data-ttu-id="12629-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-279">Assembly</span></span></td>
<td><span data-ttu-id="12629-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="12629-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="12629-281">0</span><span class="sxs-lookup"><span data-stu-id="12629-281">0</span></span></td>
<td><span data-ttu-id="12629-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="12629-283">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="12629-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-285">Journal</span></span></th>
<th><span data-ttu-id="12629-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="12629-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="12629-288">Versione</span><span class="sxs-lookup"><span data-stu-id="12629-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-289">00002</span><span class="sxs-lookup"><span data-stu-id="12629-289">00002</span></span></td>
<td><span data-ttu-id="12629-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="12629-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="12629-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-291">Fiscal</span></span></td>
<td><span data-ttu-id="12629-292">2017</span><span class="sxs-lookup"><span data-stu-id="12629-292">2017</span></span></td>
<td><span data-ttu-id="12629-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-293">Period 1</span></span></td>
<td><span data-ttu-id="12629-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="12629-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="12629-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="12629-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="12629-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-298">Cost element</span></span></th>
<th><span data-ttu-id="12629-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-299">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-300">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-302">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-302">CC099</span></span></td>
<td><span data-ttu-id="12629-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-303">Default cost center</span></span></td>
<td><span data-ttu-id="12629-304">10001</span><span class="sxs-lookup"><span data-stu-id="12629-304">10001</span></span></td>
<td><span data-ttu-id="12629-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-305">Electricity</span></span></td>
<td><span data-ttu-id="12629-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-306">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-309">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-309">CC099</span></span></td>
<td><span data-ttu-id="12629-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-310">Default cost center</span></span></td>
<td><span data-ttu-id="12629-311">10001</span><span class="sxs-lookup"><span data-stu-id="12629-311">10001</span></span></td>
<td><span data-ttu-id="12629-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-312">Electricity</span></span></td>
<td><span data-ttu-id="12629-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-313">Variable cost</span></span></td>
<td><span data-ttu-id="12629-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="12629-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="12629-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="12629-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-317">Cost element</span></span></th>
<th><span data-ttu-id="12629-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-318">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-319">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-319">Amount</span></span></th>
<th><span data-ttu-id="12629-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-321">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-321">CC099</span></span></td>
<td><span data-ttu-id="12629-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-322">Default cost center</span></span></td>
<td><span data-ttu-id="12629-323">10001</span><span class="sxs-lookup"><span data-stu-id="12629-323">10001</span></span></td>
<td><span data-ttu-id="12629-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-324">Electricity</span></span></td>
<td><span data-ttu-id="12629-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-325">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-326">-1,000.00</span></span></td>
<td><span data-ttu-id="12629-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-328">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-328">CC001</span></span></td>
<td><span data-ttu-id="12629-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-329">HR</span></span></td>
<td><span data-ttu-id="12629-330">10001</span><span class="sxs-lookup"><span data-stu-id="12629-330">10001</span></span></td>
<td><span data-ttu-id="12629-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-331">Electricity</span></span></td>
<td><span data-ttu-id="12629-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-332">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-333">500,00</span><span class="sxs-lookup"><span data-stu-id="12629-333">500.00</span></span></td>
<td><span data-ttu-id="12629-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-335">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-335">CC002</span></span></td>
<td><span data-ttu-id="12629-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-336">Finance</span></span></td>
<td><span data-ttu-id="12629-337">10001</span><span class="sxs-lookup"><span data-stu-id="12629-337">10001</span></span></td>
<td><span data-ttu-id="12629-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-338">Electricity</span></span></td>
<td><span data-ttu-id="12629-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-339">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-340">500,00</span><span class="sxs-lookup"><span data-stu-id="12629-340">500.00</span></span></td>
<td><span data-ttu-id="12629-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-342">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-342">CC099</span></span></td>
<td><span data-ttu-id="12629-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="12629-343">Default cost center</span></span></td>
<td><span data-ttu-id="12629-344">10001</span><span class="sxs-lookup"><span data-stu-id="12629-344">10001</span></span></td>
<td><span data-ttu-id="12629-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-345">Electricity</span></span></td>
<td><span data-ttu-id="12629-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-346">Variable cost</span></span></td>
<td><span data-ttu-id="12629-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="12629-347">-9,000.00</span></span></td>
<td><span data-ttu-id="12629-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-349">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-349">CC001</span></span></td>
<td><span data-ttu-id="12629-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-350">HR</span></span></td>
<td><span data-ttu-id="12629-351">10001</span><span class="sxs-lookup"><span data-stu-id="12629-351">10001</span></span></td>
<td><span data-ttu-id="12629-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-352">Electricity</span></span></td>
<td><span data-ttu-id="12629-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-353">Variable cost</span></span></td>
<td><span data-ttu-id="12629-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="12629-354">1,285.71</span></span></td>
<td><span data-ttu-id="12629-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-356">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-356">CC002</span></span></td>
<td><span data-ttu-id="12629-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-357">Finance</span></span></td>
<td><span data-ttu-id="12629-358">10001</span><span class="sxs-lookup"><span data-stu-id="12629-358">10001</span></span></td>
<td><span data-ttu-id="12629-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-359">Electricity</span></span></td>
<td><span data-ttu-id="12629-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-360">Variable cost</span></span></td>
<td><span data-ttu-id="12629-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="12629-361">7,714.29</span></span></td>
<td><span data-ttu-id="12629-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="12629-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="12629-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="12629-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="12629-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="12629-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="12629-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="12629-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="12629-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="12629-367">Define the overhead rate</span></span>

<span data-ttu-id="12629-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="12629-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="12629-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="12629-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-370">Cost object</span></span></th>
<th><span data-ttu-id="12629-371">Ore</span><span class="sxs-lookup"><span data-stu-id="12629-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="12629-372">Proj 1</span></span></td>
<td><span data-ttu-id="12629-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="12629-373">Project 1</span></span></td>
<td><span data-ttu-id="12629-374">3</span><span class="sxs-lookup"><span data-stu-id="12629-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="12629-375">Proj 2</span></span></td>
<td><span data-ttu-id="12629-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="12629-376">Project 2</span></span></td>
<td><span data-ttu-id="12629-377">1</span><span class="sxs-lookup"><span data-stu-id="12629-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="12629-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-379">Cost object</span></span></th>
<th><span data-ttu-id="12629-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-380">Cost element</span></span></th>
<th><span data-ttu-id="12629-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-381">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-382">Unità</span><span class="sxs-lookup"><span data-stu-id="12629-382">Units</span></span></th>
<th><span data-ttu-id="12629-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="12629-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-384">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-384">CC001</span></span></td>
<td><span data-ttu-id="12629-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-385">HR</span></span></td>
<td><span data-ttu-id="12629-386">10001</span><span class="sxs-lookup"><span data-stu-id="12629-386">10001</span></span></td>
<td><span data-ttu-id="12629-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-387">Variable cost</span></span></td>
<td><span data-ttu-id="12629-388">1</span><span class="sxs-lookup"><span data-stu-id="12629-388">1</span></span></td>
<td><span data-ttu-id="12629-389">10</span><span class="sxs-lookup"><span data-stu-id="12629-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="12629-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-391">Cost object</span></span></th>
<th><span data-ttu-id="12629-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-392">Magnitude</span></span></th>
<th><span data-ttu-id="12629-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-393">Cost element</span></span></th>
<th><span data-ttu-id="12629-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="12629-394">Allocation factor</span></span></th>
<th><span data-ttu-id="12629-395">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="12629-396">Proj 1</span></span></td>
<td><span data-ttu-id="12629-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="12629-397">Project 1</span></span></td>
<td><span data-ttu-id="12629-398">3</span><span class="sxs-lookup"><span data-stu-id="12629-398">3</span></span></td>
<td><span data-ttu-id="12629-399">10001</span><span class="sxs-lookup"><span data-stu-id="12629-399">10001</span></span></td>
<td><span data-ttu-id="12629-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="12629-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="12629-401">30,00</span><span class="sxs-lookup"><span data-stu-id="12629-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="12629-402">Proj 2</span></span></td>
<td><span data-ttu-id="12629-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="12629-403">Project 2</span></span></td>
<td><span data-ttu-id="12629-404">1</span><span class="sxs-lookup"><span data-stu-id="12629-404">1</span></span></td>
<td><span data-ttu-id="12629-405">10001</span><span class="sxs-lookup"><span data-stu-id="12629-405">10001</span></span></td>
<td><span data-ttu-id="12629-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="12629-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="12629-407">10,00</span><span class="sxs-lookup"><span data-stu-id="12629-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="12629-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-409">Journal</span></span></th>
<th><span data-ttu-id="12629-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="12629-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="12629-412">Versione</span><span class="sxs-lookup"><span data-stu-id="12629-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-413">00003</span><span class="sxs-lookup"><span data-stu-id="12629-413">00003</span></span></td>
<td><span data-ttu-id="12629-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="12629-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="12629-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-415">Fiscal</span></span></td>
<td><span data-ttu-id="12629-416">2017</span><span class="sxs-lookup"><span data-stu-id="12629-416">2017</span></span></td>
<td><span data-ttu-id="12629-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-417">Period 1</span></span></td>
<td><span data-ttu-id="12629-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="12629-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="12629-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="12629-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-421">Cost object</span></span></th>
<th><span data-ttu-id="12629-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="12629-424">Proj 1</span></span></td>
<td><span data-ttu-id="12629-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="12629-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="12629-426">3,00</span><span class="sxs-lookup"><span data-stu-id="12629-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="12629-428">Proj 2</span></span></td>
<td><span data-ttu-id="12629-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="12629-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="12629-430">1,00</span><span class="sxs-lookup"><span data-stu-id="12629-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="12629-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="12629-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="12629-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-433">Cost element</span></span></th>
<th><span data-ttu-id="12629-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-434">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-435">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-435">Amount</span></span></th>
<th><span data-ttu-id="12629-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="12629-437">CC0001</span></span></td>
<td><span data-ttu-id="12629-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-438">HR</span></span></td>
<td><span data-ttu-id="12629-439">10001</span><span class="sxs-lookup"><span data-stu-id="12629-439">10001</span></span></td>
<td><span data-ttu-id="12629-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-440">Electricity</span></span></td>
<td><span data-ttu-id="12629-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-441">Variable cost</span></span></td>
<td><span data-ttu-id="12629-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="12629-442">-30.00</span></span></td>
<td><span data-ttu-id="12629-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="12629-444">Proj 1</span></span></td>
<td><span data-ttu-id="12629-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="12629-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="12629-446">10001</span><span class="sxs-lookup"><span data-stu-id="12629-446">10001</span></span></td>
<td><span data-ttu-id="12629-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-447">Electricity</span></span></td>
<td><span data-ttu-id="12629-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-448">Variable cost</span></span></td>
<td><span data-ttu-id="12629-449">30,00</span><span class="sxs-lookup"><span data-stu-id="12629-449">30.00</span></span></td>
<td><span data-ttu-id="12629-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-451">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-451">CC001</span></span></td>
<td><span data-ttu-id="12629-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-452">HR</span></span></td>
<td><span data-ttu-id="12629-453">10001</span><span class="sxs-lookup"><span data-stu-id="12629-453">10001</span></span></td>
<td><span data-ttu-id="12629-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-454">Electricity</span></span></td>
<td><span data-ttu-id="12629-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-455">Variable cost</span></span></td>
<td><span data-ttu-id="12629-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="12629-456">-10.00</span></span></td>
<td><span data-ttu-id="12629-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="12629-458">Proj 2</span></span></td>
<td><span data-ttu-id="12629-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="12629-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="12629-460">10001</span><span class="sxs-lookup"><span data-stu-id="12629-460">10001</span></span></td>
<td><span data-ttu-id="12629-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-461">Electricity</span></span></td>
<td><span data-ttu-id="12629-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-462">Variable cost</span></span></td>
<td><span data-ttu-id="12629-463">10.00</span><span class="sxs-lookup"><span data-stu-id="12629-463">10.00</span></span></td>
<td><span data-ttu-id="12629-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="12629-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="12629-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="12629-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="12629-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="12629-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="12629-468">Finance and Operations supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="12629-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="12629-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="12629-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="12629-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="12629-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="12629-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="12629-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="12629-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="12629-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="12629-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="12629-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="12629-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="12629-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="12629-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="12629-475">Define the cost allocation</span></span>

<span data-ttu-id="12629-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="12629-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="12629-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="12629-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="12629-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="12629-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-479">Cost object</span></span></th>
<th><span data-ttu-id="12629-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="12629-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-481">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-481">CC002</span></span></td>
<td><span data-ttu-id="12629-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-482">Finance</span></span></td>
<td><span data-ttu-id="12629-483">35</span><span class="sxs-lookup"><span data-stu-id="12629-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-484">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-484">CC003</span></span></td>
<td><span data-ttu-id="12629-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-485">Assembly</span></span></td>
<td><span data-ttu-id="12629-486">55</span><span class="sxs-lookup"><span data-stu-id="12629-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-487">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-487">CC004</span></span></td>
<td><span data-ttu-id="12629-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-488">Packaging</span></span></td>
<td><span data-ttu-id="12629-489">10</span><span class="sxs-lookup"><span data-stu-id="12629-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="12629-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="12629-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="12629-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-492">Cost object</span></span></th>
<th><span data-ttu-id="12629-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-494">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-494">CC003</span></span></td>
<td><span data-ttu-id="12629-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-495">Assembly</span></span></td>
<td><span data-ttu-id="12629-496">65</span><span class="sxs-lookup"><span data-stu-id="12629-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-497">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-497">CC004</span></span></td>
<td><span data-ttu-id="12629-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-498">Packaging</span></span></td>
<td><span data-ttu-id="12629-499">35</span><span class="sxs-lookup"><span data-stu-id="12629-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="12629-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="12629-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="12629-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-502">Cost object</span></span></th>
<th><span data-ttu-id="12629-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="12629-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-504">Prod 1</span></span></td>
<td><span data-ttu-id="12629-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-505">Product 1</span></span></td>
<td><span data-ttu-id="12629-506">60</span><span class="sxs-lookup"><span data-stu-id="12629-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-507">Prod 2</span></span></td>
<td><span data-ttu-id="12629-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-508">Product 2</span></span></td>
<td><span data-ttu-id="12629-509">20</span><span class="sxs-lookup"><span data-stu-id="12629-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="12629-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="12629-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="12629-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-512">Cost object</span></span></th>
<th><span data-ttu-id="12629-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="12629-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-514">Prod 1</span></span></td>
<td><span data-ttu-id="12629-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-515">Product 1</span></span></td>
<td><span data-ttu-id="12629-516">80</span><span class="sxs-lookup"><span data-stu-id="12629-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-517">Prod 2</span></span></td>
<td><span data-ttu-id="12629-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-518">Product 2</span></span></td>
<td><span data-ttu-id="12629-519">15</span><span class="sxs-lookup"><span data-stu-id="12629-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="12629-520">In Finance and Operations, le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="12629-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="12629-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="12629-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="12629-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="12629-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-523">Cost object</span></span></th>
<th><span data-ttu-id="12629-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-524">Magnitude</span></span></th>
<th><span data-ttu-id="12629-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="12629-525">Allocation factor</span></span></th>
<th><span data-ttu-id="12629-526">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-526">Amount</span></span></th>
<th><span data-ttu-id="12629-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-528">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-528">CC002</span></span></td>
<td><span data-ttu-id="12629-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-529">Finance</span></span></td>
<td><span data-ttu-id="12629-530">35</span><span class="sxs-lookup"><span data-stu-id="12629-530">35</span></span></td>
<td><span data-ttu-id="12629-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="12629-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="12629-532">175.00</span><span class="sxs-lookup"><span data-stu-id="12629-532">175.00</span></span></td>
<td><span data-ttu-id="12629-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-534">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-534">CC003</span></span></td>
<td><span data-ttu-id="12629-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-535">Assembly</span></span></td>
<td><span data-ttu-id="12629-536">55</span><span class="sxs-lookup"><span data-stu-id="12629-536">55</span></span></td>
<td><span data-ttu-id="12629-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="12629-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="12629-538">275.00</span><span class="sxs-lookup"><span data-stu-id="12629-538">275.00</span></span></td>
<td><span data-ttu-id="12629-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-540">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-540">CC004</span></span></td>
<td><span data-ttu-id="12629-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-541">Packaging</span></span></td>
<td><span data-ttu-id="12629-542">10</span><span class="sxs-lookup"><span data-stu-id="12629-542">10</span></span></td>
<td><span data-ttu-id="12629-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="12629-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="12629-544">50,00</span><span class="sxs-lookup"><span data-stu-id="12629-544">50.00</span></span></td>
<td><span data-ttu-id="12629-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-546">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-546">CC002</span></span></td>
<td><span data-ttu-id="12629-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-547">Finance</span></span></td>
<td><span data-ttu-id="12629-548">35</span><span class="sxs-lookup"><span data-stu-id="12629-548">35</span></span></td>
<td><span data-ttu-id="12629-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="12629-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="12629-550">436.00</span><span class="sxs-lookup"><span data-stu-id="12629-550">436.00</span></span></td>
<td><span data-ttu-id="12629-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-552">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-552">CC003</span></span></td>
<td><span data-ttu-id="12629-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-553">Assembly</span></span></td>
<td><span data-ttu-id="12629-554">55</span><span class="sxs-lookup"><span data-stu-id="12629-554">55</span></span></td>
<td><span data-ttu-id="12629-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="12629-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="12629-556">685.14</span><span class="sxs-lookup"><span data-stu-id="12629-556">685.14</span></span></td>
<td><span data-ttu-id="12629-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-558">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-558">CC004</span></span></td>
<td><span data-ttu-id="12629-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-559">Packaging</span></span></td>
<td><span data-ttu-id="12629-560">10</span><span class="sxs-lookup"><span data-stu-id="12629-560">10</span></span></td>
<td><span data-ttu-id="12629-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="12629-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="12629-562">124.57</span><span class="sxs-lookup"><span data-stu-id="12629-562">124.57</span></span></td>
<td><span data-ttu-id="12629-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="12629-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-565">Cost object</span></span></th>
<th><span data-ttu-id="12629-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-566">Magnitude</span></span></th>
<th><span data-ttu-id="12629-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="12629-567">Allocation factor</span></span></th>
<th><span data-ttu-id="12629-568">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-568">Amount</span></span></th>
<th><span data-ttu-id="12629-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-570">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-570">CC003</span></span></td>
<td><span data-ttu-id="12629-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-571">Assembly</span></span></td>
<td><span data-ttu-id="12629-572">65</span><span class="sxs-lookup"><span data-stu-id="12629-572">65</span></span></td>
<td><span data-ttu-id="12629-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="12629-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="12629-574">438.75</span><span class="sxs-lookup"><span data-stu-id="12629-574">438.75</span></span></td>
<td><span data-ttu-id="12629-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-576">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-576">CC004</span></span></td>
<td><span data-ttu-id="12629-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-577">Packaging</span></span></td>
<td><span data-ttu-id="12629-578">35</span><span class="sxs-lookup"><span data-stu-id="12629-578">35</span></span></td>
<td><span data-ttu-id="12629-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="12629-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="12629-580">236.25</span><span class="sxs-lookup"><span data-stu-id="12629-580">236.25</span></span></td>
<td><span data-ttu-id="12629-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-582">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-582">CC003</span></span></td>
<td><span data-ttu-id="12629-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-583">Assembly</span></span></td>
<td><span data-ttu-id="12629-584">65</span><span class="sxs-lookup"><span data-stu-id="12629-584">65</span></span></td>
<td><span data-ttu-id="12629-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="12629-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="12629-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="12629-586">5,297.69</span></span></td>
<td><span data-ttu-id="12629-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-588">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-588">CC004</span></span></td>
<td><span data-ttu-id="12629-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-589">Packaging</span></span></td>
<td><span data-ttu-id="12629-590">35</span><span class="sxs-lookup"><span data-stu-id="12629-590">35</span></span></td>
<td><span data-ttu-id="12629-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="12629-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="12629-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="12629-592">2,852.60</span></span></td>
<td><span data-ttu-id="12629-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="12629-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-595">Cost object</span></span></th>
<th><span data-ttu-id="12629-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-596">Magnitude</span></span></th>
<th><span data-ttu-id="12629-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="12629-597">Allocation factor</span></span></th>
<th><span data-ttu-id="12629-598">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-598">Amount</span></span></th>
<th><span data-ttu-id="12629-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-600">Prod 1</span></span></td>
<td><span data-ttu-id="12629-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-601">Product 1</span></span></td>
<td><span data-ttu-id="12629-602">60</span><span class="sxs-lookup"><span data-stu-id="12629-602">60</span></span></td>
<td><span data-ttu-id="12629-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="12629-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="12629-604">535.31</span><span class="sxs-lookup"><span data-stu-id="12629-604">535.31</span></span></td>
<td><span data-ttu-id="12629-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-606">Prod 2</span></span></td>
<td><span data-ttu-id="12629-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-607">Product 2</span></span></td>
<td><span data-ttu-id="12629-608">20</span><span class="sxs-lookup"><span data-stu-id="12629-608">20</span></span></td>
<td><span data-ttu-id="12629-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="12629-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="12629-610">178.44</span><span class="sxs-lookup"><span data-stu-id="12629-610">178.44</span></span></td>
<td><span data-ttu-id="12629-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-612">Prod 1</span></span></td>
<td><span data-ttu-id="12629-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-613">Product 1</span></span></td>
<td><span data-ttu-id="12629-614">60</span><span class="sxs-lookup"><span data-stu-id="12629-614">60</span></span></td>
<td><span data-ttu-id="12629-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="12629-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="12629-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="12629-616">4,487.12</span></span></td>
<td><span data-ttu-id="12629-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-618">Prod 2</span></span></td>
<td><span data-ttu-id="12629-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-619">Product 2</span></span></td>
<td><span data-ttu-id="12629-620">20</span><span class="sxs-lookup"><span data-stu-id="12629-620">20</span></span></td>
<td><span data-ttu-id="12629-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="12629-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="12629-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="12629-622">1,495.71</span></span></td>
<td><span data-ttu-id="12629-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="12629-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="12629-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-625">Cost object</span></span></th>
<th><span data-ttu-id="12629-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="12629-626">Magnitude</span></span></th>
<th><span data-ttu-id="12629-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="12629-627">Allocation factor</span></span></th>
<th><span data-ttu-id="12629-628">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-628">Amount</span></span></th>
<th><span data-ttu-id="12629-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-630">Prod 1</span></span></td>
<td><span data-ttu-id="12629-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-631">Product 1</span></span></td>
<td><span data-ttu-id="12629-632">80</span><span class="sxs-lookup"><span data-stu-id="12629-632">80</span></span></td>
<td><span data-ttu-id="12629-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="12629-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="12629-634">241.05</span><span class="sxs-lookup"><span data-stu-id="12629-634">241.05</span></span></td>
<td><span data-ttu-id="12629-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-636">Prod 2</span></span></td>
<td><span data-ttu-id="12629-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-637">Product 2</span></span></td>
<td><span data-ttu-id="12629-638">15</span><span class="sxs-lookup"><span data-stu-id="12629-638">15</span></span></td>
<td><span data-ttu-id="12629-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="12629-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="12629-640">45.20</span><span class="sxs-lookup"><span data-stu-id="12629-640">45.20</span></span></td>
<td><span data-ttu-id="12629-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-642">Prod 1</span></span></td>
<td><span data-ttu-id="12629-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-643">Product 1</span></span></td>
<td><span data-ttu-id="12629-644">80</span><span class="sxs-lookup"><span data-stu-id="12629-644">80</span></span></td>
<td><span data-ttu-id="12629-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="12629-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="12629-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="12629-646">2,507.09</span></span></td>
<td><span data-ttu-id="12629-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-648">Prod 2</span></span></td>
<td><span data-ttu-id="12629-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-649">Product 2</span></span></td>
<td><span data-ttu-id="12629-650">15</span><span class="sxs-lookup"><span data-stu-id="12629-650">15</span></span></td>
<td><span data-ttu-id="12629-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="12629-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="12629-652">470.08</span><span class="sxs-lookup"><span data-stu-id="12629-652">470.08</span></span></td>
<td><span data-ttu-id="12629-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="12629-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="12629-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-655">Journal</span></span></th>
<th><span data-ttu-id="12629-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="12629-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="12629-658">Versione</span><span class="sxs-lookup"><span data-stu-id="12629-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-659">00004</span><span class="sxs-lookup"><span data-stu-id="12629-659">00004</span></span></td>
<td><span data-ttu-id="12629-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="12629-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="12629-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="12629-661">Fiscal</span></span></td>
<td><span data-ttu-id="12629-662">2017</span><span class="sxs-lookup"><span data-stu-id="12629-662">2017</span></span></td>
<td><span data-ttu-id="12629-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-663">Period 1</span></span></td>
<td><span data-ttu-id="12629-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="12629-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="12629-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="12629-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="12629-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="12629-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-668">Cost element</span></span></th>
<th><span data-ttu-id="12629-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-669">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-670">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-672">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-672">CC001</span></span></td>
<td><span data-ttu-id="12629-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-673">HR</span></span></td>
<td><span data-ttu-id="12629-674">10001</span><span class="sxs-lookup"><span data-stu-id="12629-674">10001</span></span></td>
<td><span data-ttu-id="12629-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-675">Electricity</span></span></td>
<td><span data-ttu-id="12629-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-676">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-677">500,00</span><span class="sxs-lookup"><span data-stu-id="12629-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-679">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-679">CC001</span></span></td>
<td><span data-ttu-id="12629-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-680">HR</span></span></td>
<td><span data-ttu-id="12629-681">10001</span><span class="sxs-lookup"><span data-stu-id="12629-681">10001</span></span></td>
<td><span data-ttu-id="12629-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-682">Electricity</span></span></td>
<td><span data-ttu-id="12629-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-683">Variable cost</span></span></td>
<td><span data-ttu-id="12629-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="12629-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-686">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-686">CC002</span></span></td>
<td><span data-ttu-id="12629-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-687">Finance</span></span></td>
<td><span data-ttu-id="12629-688">10001</span><span class="sxs-lookup"><span data-stu-id="12629-688">10001</span></span></td>
<td><span data-ttu-id="12629-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-689">Electricity</span></span></td>
<td><span data-ttu-id="12629-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-690">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-691">675.00</span><span class="sxs-lookup"><span data-stu-id="12629-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-693">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-693">CC002</span></span></td>
<td><span data-ttu-id="12629-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-694">Finance</span></span></td>
<td><span data-ttu-id="12629-695">10001</span><span class="sxs-lookup"><span data-stu-id="12629-695">10001</span></span></td>
<td><span data-ttu-id="12629-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-696">Electricity</span></span></td>
<td><span data-ttu-id="12629-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-697">Variable cost</span></span></td>
<td><span data-ttu-id="12629-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="12629-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-700">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-700">CC003</span></span></td>
<td><span data-ttu-id="12629-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-701">Assembly</span></span></td>
<td><span data-ttu-id="12629-702">10001</span><span class="sxs-lookup"><span data-stu-id="12629-702">10001</span></span></td>
<td><span data-ttu-id="12629-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-703">Electricity</span></span></td>
<td><span data-ttu-id="12629-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-704">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-705">713.75</span><span class="sxs-lookup"><span data-stu-id="12629-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-707">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-707">CC003</span></span></td>
<td><span data-ttu-id="12629-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-708">Assembly</span></span></td>
<td><span data-ttu-id="12629-709">10001</span><span class="sxs-lookup"><span data-stu-id="12629-709">10001</span></span></td>
<td><span data-ttu-id="12629-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-710">Electricity</span></span></td>
<td><span data-ttu-id="12629-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-711">Variable cost</span></span></td>
<td><span data-ttu-id="12629-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="12629-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-714">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-714">CC003</span></span></td>
<td><span data-ttu-id="12629-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-715">Packaging</span></span></td>
<td><span data-ttu-id="12629-716">10001</span><span class="sxs-lookup"><span data-stu-id="12629-716">10001</span></span></td>
<td><span data-ttu-id="12629-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-717">Electricity</span></span></td>
<td><span data-ttu-id="12629-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-718">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-719">286.25</span><span class="sxs-lookup"><span data-stu-id="12629-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-721">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-721">CC003</span></span></td>
<td><span data-ttu-id="12629-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-722">Packaging</span></span></td>
<td><span data-ttu-id="12629-723">10001</span><span class="sxs-lookup"><span data-stu-id="12629-723">10001</span></span></td>
<td><span data-ttu-id="12629-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-724">Electricity</span></span></td>
<td><span data-ttu-id="12629-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-725">Variable cost</span></span></td>
<td><span data-ttu-id="12629-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="12629-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-728">Prod 1</span></span></td>
<td><span data-ttu-id="12629-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-729">Product 1</span></span></td>
<td><span data-ttu-id="12629-730">10001</span><span class="sxs-lookup"><span data-stu-id="12629-730">10001</span></span></td>
<td><span data-ttu-id="12629-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-731">Electricity</span></span></td>
<td><span data-ttu-id="12629-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-732">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-733">776.36</span><span class="sxs-lookup"><span data-stu-id="12629-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-735">Prod 1</span></span></td>
<td><span data-ttu-id="12629-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-736">Product 1</span></span></td>
<td><span data-ttu-id="12629-737">10001</span><span class="sxs-lookup"><span data-stu-id="12629-737">10001</span></span></td>
<td><span data-ttu-id="12629-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-738">Electricity</span></span></td>
<td><span data-ttu-id="12629-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-739">Variable cost</span></span></td>
<td><span data-ttu-id="12629-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="12629-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-742">Prod 2</span></span></td>
<td><span data-ttu-id="12629-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-743">Product 1</span></span></td>
<td><span data-ttu-id="12629-744">10001</span><span class="sxs-lookup"><span data-stu-id="12629-744">10001</span></span></td>
<td><span data-ttu-id="12629-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-745">Electricity</span></span></td>
<td><span data-ttu-id="12629-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-746">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-747">223.64</span><span class="sxs-lookup"><span data-stu-id="12629-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="12629-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-749">Prod 2</span></span></td>
<td><span data-ttu-id="12629-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-750">Product 1</span></span></td>
<td><span data-ttu-id="12629-751">10001</span><span class="sxs-lookup"><span data-stu-id="12629-751">10001</span></span></td>
<td><span data-ttu-id="12629-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-752">Electricity</span></span></td>
<td><span data-ttu-id="12629-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-753">Variable cost</span></span></td>
<td><span data-ttu-id="12629-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="12629-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="12629-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="12629-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="12629-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="12629-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-757">Cost element</span></span></th>
<th><span data-ttu-id="12629-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="12629-758">Cost behavior</span></span></th>
<th><span data-ttu-id="12629-759">Importo</span><span class="sxs-lookup"><span data-stu-id="12629-759">Amount</span></span></th>
<th><span data-ttu-id="12629-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="12629-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="12629-761">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-761">CC001</span></span></td>
<td><span data-ttu-id="12629-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-762">HR</span></span></td>
<td><span data-ttu-id="12629-763">10001</span><span class="sxs-lookup"><span data-stu-id="12629-763">10001</span></span></td>
<td><span data-ttu-id="12629-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-764">Electricity</span></span></td>
<td><span data-ttu-id="12629-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-765">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="12629-766">-500.00</span></span></td>
<td><span data-ttu-id="12629-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-768">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-768">CC002</span></span></td>
<td><span data-ttu-id="12629-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-769">Finance</span></span></td>
<td><span data-ttu-id="12629-770">10001</span><span class="sxs-lookup"><span data-stu-id="12629-770">10001</span></span></td>
<td><span data-ttu-id="12629-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-771">Electricity</span></span></td>
<td><span data-ttu-id="12629-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-772">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-773">175.00</span><span class="sxs-lookup"><span data-stu-id="12629-773">175.00</span></span></td>
<td><span data-ttu-id="12629-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-775">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-775">CC003</span></span></td>
<td><span data-ttu-id="12629-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-776">Assembly</span></span></td>
<td><span data-ttu-id="12629-777">10001</span><span class="sxs-lookup"><span data-stu-id="12629-777">10001</span></span></td>
<td><span data-ttu-id="12629-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-778">Electricity</span></span></td>
<td><span data-ttu-id="12629-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-779">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-780">275.00</span><span class="sxs-lookup"><span data-stu-id="12629-780">275.00</span></span></td>
<td><span data-ttu-id="12629-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-782">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-782">CC004</span></span></td>
<td><span data-ttu-id="12629-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-783">Packaging</span></span></td>
<td><span data-ttu-id="12629-784">10001</span><span class="sxs-lookup"><span data-stu-id="12629-784">10001</span></span></td>
<td><span data-ttu-id="12629-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-785">Electricity</span></span></td>
<td><span data-ttu-id="12629-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-786">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-787">50,00</span><span class="sxs-lookup"><span data-stu-id="12629-787">50,00</span></span></td>
<td><span data-ttu-id="12629-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-789">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-789">CC001</span></span></td>
<td><span data-ttu-id="12629-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="12629-790">HR</span></span></td>
<td><span data-ttu-id="12629-791">10001</span><span class="sxs-lookup"><span data-stu-id="12629-791">10001</span></span></td>
<td><span data-ttu-id="12629-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-792">Electricity</span></span></td>
<td><span data-ttu-id="12629-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-793">Variable cost</span></span></td>
<td><span data-ttu-id="12629-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="12629-794">-1,245.71</span></span></td>
<td><span data-ttu-id="12629-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-796">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-796">CC002</span></span></td>
<td><span data-ttu-id="12629-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-797">Finance</span></span></td>
<td><span data-ttu-id="12629-798">10001</span><span class="sxs-lookup"><span data-stu-id="12629-798">10001</span></span></td>
<td><span data-ttu-id="12629-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-799">Electricity</span></span></td>
<td><span data-ttu-id="12629-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-800">Variable cost</span></span></td>
<td><span data-ttu-id="12629-801">436.00</span><span class="sxs-lookup"><span data-stu-id="12629-801">436.00</span></span></td>
<td><span data-ttu-id="12629-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-803">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-803">CC003</span></span></td>
<td><span data-ttu-id="12629-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-804">Assembly</span></span></td>
<td><span data-ttu-id="12629-805">10001</span><span class="sxs-lookup"><span data-stu-id="12629-805">10001</span></span></td>
<td><span data-ttu-id="12629-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-806">Electricity</span></span></td>
<td><span data-ttu-id="12629-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-807">Variable cost</span></span></td>
<td><span data-ttu-id="12629-808">685.14</span><span class="sxs-lookup"><span data-stu-id="12629-808">685.14</span></span></td>
<td><span data-ttu-id="12629-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-810">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-810">CC004</span></span></td>
<td><span data-ttu-id="12629-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-811">Packaging</span></span></td>
<td><span data-ttu-id="12629-812">10001</span><span class="sxs-lookup"><span data-stu-id="12629-812">10001</span></span></td>
<td><span data-ttu-id="12629-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-813">Electricity</span></span></td>
<td><span data-ttu-id="12629-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-814">Variable cost</span></span></td>
<td><span data-ttu-id="12629-815">124.57</span><span class="sxs-lookup"><span data-stu-id="12629-815">124.57</span></span></td>
<td><span data-ttu-id="12629-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-817">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-817">CC002</span></span></td>
<td><span data-ttu-id="12629-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-818">Finance</span></span></td>
<td><span data-ttu-id="12629-819">10001</span><span class="sxs-lookup"><span data-stu-id="12629-819">10001</span></span></td>
<td><span data-ttu-id="12629-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-820">Electricity</span></span></td>
<td><span data-ttu-id="12629-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-821">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="12629-822">-675.00</span></span></td>
<td><span data-ttu-id="12629-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-824">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-824">CC003</span></span></td>
<td><span data-ttu-id="12629-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-825">Assembly</span></span></td>
<td><span data-ttu-id="12629-826">10001</span><span class="sxs-lookup"><span data-stu-id="12629-826">10001</span></span></td>
<td><span data-ttu-id="12629-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-827">Electricity</span></span></td>
<td><span data-ttu-id="12629-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-828">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-829">438.75</span><span class="sxs-lookup"><span data-stu-id="12629-829">438.75</span></span></td>
<td><span data-ttu-id="12629-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-831">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-831">CC004</span></span></td>
<td><span data-ttu-id="12629-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-832">Packaging</span></span></td>
<td><span data-ttu-id="12629-833">10001</span><span class="sxs-lookup"><span data-stu-id="12629-833">10001</span></span></td>
<td><span data-ttu-id="12629-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-834">Electricity</span></span></td>
<td><span data-ttu-id="12629-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-835">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-836">236.25</span><span class="sxs-lookup"><span data-stu-id="12629-836">236.25</span></span></td>
<td><span data-ttu-id="12629-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-838">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-838">CC002</span></span></td>
<td><span data-ttu-id="12629-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="12629-839">Finance</span></span></td>
<td><span data-ttu-id="12629-840">10001</span><span class="sxs-lookup"><span data-stu-id="12629-840">10001</span></span></td>
<td><span data-ttu-id="12629-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-841">Electricity</span></span></td>
<td><span data-ttu-id="12629-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-842">Variable cost</span></span></td>
<td><span data-ttu-id="12629-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="12629-843">-8,150.29</span></span></td>
<td><span data-ttu-id="12629-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-845">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-845">CC003</span></span></td>
<td><span data-ttu-id="12629-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-846">Assembly</span></span></td>
<td><span data-ttu-id="12629-847">10001</span><span class="sxs-lookup"><span data-stu-id="12629-847">10001</span></span></td>
<td><span data-ttu-id="12629-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-848">Electricity</span></span></td>
<td><span data-ttu-id="12629-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-849">Variable cost</span></span></td>
<td><span data-ttu-id="12629-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="12629-850">5,297.69</span></span></td>
<td><span data-ttu-id="12629-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-852">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-852">CC004</span></span></td>
<td><span data-ttu-id="12629-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="12629-853">Packaging</span></span></td>
<td><span data-ttu-id="12629-854">10001</span><span class="sxs-lookup"><span data-stu-id="12629-854">10001</span></span></td>
<td><span data-ttu-id="12629-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-855">Electricity</span></span></td>
<td><span data-ttu-id="12629-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-856">Variable cost</span></span></td>
<td><span data-ttu-id="12629-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="12629-857">2,852.60</span></span></td>
<td><span data-ttu-id="12629-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-859">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-859">CC003</span></span></td>
<td><span data-ttu-id="12629-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-860">Assembly</span></span></td>
<td><span data-ttu-id="12629-861">10001</span><span class="sxs-lookup"><span data-stu-id="12629-861">10001</span></span></td>
<td><span data-ttu-id="12629-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-862">Electricity</span></span></td>
<td><span data-ttu-id="12629-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-863">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="12629-864">-713.75</span></span></td>
<td><span data-ttu-id="12629-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-866">Prod 1</span></span></td>
<td><span data-ttu-id="12629-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-867">Product 1</span></span></td>
<td><span data-ttu-id="12629-868">10001</span><span class="sxs-lookup"><span data-stu-id="12629-868">10001</span></span></td>
<td><span data-ttu-id="12629-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-869">Electricity</span></span></td>
<td><span data-ttu-id="12629-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-870">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-871">535.31</span><span class="sxs-lookup"><span data-stu-id="12629-871">535.31</span></span></td>
<td><span data-ttu-id="12629-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-873">Prod 2</span></span></td>
<td><span data-ttu-id="12629-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-874">Product 2</span></span></td>
<td><span data-ttu-id="12629-875">10001</span><span class="sxs-lookup"><span data-stu-id="12629-875">10001</span></span></td>
<td><span data-ttu-id="12629-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-876">Electricity</span></span></td>
<td><span data-ttu-id="12629-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-877">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-878">178.44</span><span class="sxs-lookup"><span data-stu-id="12629-878">178.44</span></span></td>
<td><span data-ttu-id="12629-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-880">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-880">CC003</span></span></td>
<td><span data-ttu-id="12629-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-881">Assembly</span></span></td>
<td><span data-ttu-id="12629-882">10001</span><span class="sxs-lookup"><span data-stu-id="12629-882">10001</span></span></td>
<td><span data-ttu-id="12629-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-883">Electricity</span></span></td>
<td><span data-ttu-id="12629-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-884">Variable cost</span></span></td>
<td><span data-ttu-id="12629-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="12629-885">-5,982.83</span></span></td>
<td><span data-ttu-id="12629-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-887">Prod 1</span></span></td>
<td><span data-ttu-id="12629-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-888">Product 1</span></span></td>
<td><span data-ttu-id="12629-889">10001</span><span class="sxs-lookup"><span data-stu-id="12629-889">10001</span></span></td>
<td><span data-ttu-id="12629-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-890">Electricity</span></span></td>
<td><span data-ttu-id="12629-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-891">Variable cost</span></span></td>
<td><span data-ttu-id="12629-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="12629-892">4,487.12</span></span></td>
<td><span data-ttu-id="12629-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-894">Prod 2</span></span></td>
<td><span data-ttu-id="12629-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-895">Product 2</span></span></td>
<td><span data-ttu-id="12629-896">10001</span><span class="sxs-lookup"><span data-stu-id="12629-896">10001</span></span></td>
<td><span data-ttu-id="12629-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-897">Electricity</span></span></td>
<td><span data-ttu-id="12629-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-898">Variable cost</span></span></td>
<td><span data-ttu-id="12629-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="12629-899">1,495.71</span></span></td>
<td><span data-ttu-id="12629-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-901">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-901">CC003</span></span></td>
<td><span data-ttu-id="12629-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-902">Assembly</span></span></td>
<td><span data-ttu-id="12629-903">10001</span><span class="sxs-lookup"><span data-stu-id="12629-903">10001</span></span></td>
<td><span data-ttu-id="12629-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-904">Electricity</span></span></td>
<td><span data-ttu-id="12629-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-905">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="12629-906">-286.25</span></span></td>
<td><span data-ttu-id="12629-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-908">Prod 1</span></span></td>
<td><span data-ttu-id="12629-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-909">Product 1</span></span></td>
<td><span data-ttu-id="12629-910">10001</span><span class="sxs-lookup"><span data-stu-id="12629-910">10001</span></span></td>
<td><span data-ttu-id="12629-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-911">Electricity</span></span></td>
<td><span data-ttu-id="12629-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-912">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-913">241.05</span><span class="sxs-lookup"><span data-stu-id="12629-913">241.05</span></span></td>
<td><span data-ttu-id="12629-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-915">Prod 2</span></span></td>
<td><span data-ttu-id="12629-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-916">Product 2</span></span></td>
<td><span data-ttu-id="12629-917">10001</span><span class="sxs-lookup"><span data-stu-id="12629-917">10001</span></span></td>
<td><span data-ttu-id="12629-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-918">Electricity</span></span></td>
<td><span data-ttu-id="12629-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-919">Fixed cost</span></span></td>
<td><span data-ttu-id="12629-920">45.20</span><span class="sxs-lookup"><span data-stu-id="12629-920">45.20</span></span></td>
<td><span data-ttu-id="12629-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-922">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-922">CC003</span></span></td>
<td><span data-ttu-id="12629-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="12629-923">Assembly</span></span></td>
<td><span data-ttu-id="12629-924">10001</span><span class="sxs-lookup"><span data-stu-id="12629-924">10001</span></span></td>
<td><span data-ttu-id="12629-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-925">Electricity</span></span></td>
<td><span data-ttu-id="12629-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-926">Variable cost</span></span></td>
<td><span data-ttu-id="12629-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="12629-927">-2,977.17</span></span></td>
<td><span data-ttu-id="12629-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-929">Prod 1</span></span></td>
<td><span data-ttu-id="12629-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="12629-930">Product 1</span></span></td>
<td><span data-ttu-id="12629-931">10001</span><span class="sxs-lookup"><span data-stu-id="12629-931">10001</span></span></td>
<td><span data-ttu-id="12629-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-932">Electricity</span></span></td>
<td><span data-ttu-id="12629-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-933">Variable cost</span></span></td>
<td><span data-ttu-id="12629-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="12629-934">2,507.09</span></span></td>
<td><span data-ttu-id="12629-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="12629-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-936">Prod 2</span></span></td>
<td><span data-ttu-id="12629-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="12629-937">Product 2</span></span></td>
<td><span data-ttu-id="12629-938">10001</span><span class="sxs-lookup"><span data-stu-id="12629-938">10001</span></span></td>
<td><span data-ttu-id="12629-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-939">Electricity</span></span></td>
<td><span data-ttu-id="12629-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-940">Variable cost</span></span></td>
<td><span data-ttu-id="12629-941">470.08</span><span class="sxs-lookup"><span data-stu-id="12629-941">470.08</span></span></td>
<td><span data-ttu-id="12629-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="12629-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="12629-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="12629-943">Conclusion</span></span>
<span data-ttu-id="12629-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="12629-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="12629-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="12629-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="12629-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="12629-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="12629-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="12629-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="12629-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="12629-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="12629-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="12629-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="12629-950">Totale</span><span class="sxs-lookup"><span data-stu-id="12629-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="12629-951">CC099</span><span class="sxs-lookup"><span data-stu-id="12629-951">CC099</span></span></th>
<th><span data-ttu-id="12629-952">CC001</span><span class="sxs-lookup"><span data-stu-id="12629-952">CC001</span></span></th>
<th><span data-ttu-id="12629-953">CC002</span><span class="sxs-lookup"><span data-stu-id="12629-953">CC002</span></span></th>
<th><span data-ttu-id="12629-954">CC003</span><span class="sxs-lookup"><span data-stu-id="12629-954">CC003</span></span></th>
<th><span data-ttu-id="12629-955">CC004</span><span class="sxs-lookup"><span data-stu-id="12629-955">CC004</span></span></th>
<th><span data-ttu-id="12629-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="12629-956">Proj 1</span></span></th>
<th><span data-ttu-id="12629-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="12629-957">Proj 2</span></span></th>
<th><span data-ttu-id="12629-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="12629-958">Prod 1</span></span></th>
<th><span data-ttu-id="12629-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="12629-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="12629-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="12629-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="12629-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="12629-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="12629-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="12629-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="12629-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-971">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="12629-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="12629-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-973">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-974">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-975">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-976">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-977">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="12629-978">776.36</span><span class="sxs-lookup"><span data-stu-id="12629-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-979">223.64</span><span class="sxs-lookup"><span data-stu-id="12629-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="12629-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="12629-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-982">000</span><span class="sxs-lookup"><span data-stu-id="12629-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-983">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-984">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-985">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-986">0,00</span><span class="sxs-lookup"><span data-stu-id="12629-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-987">30,00</span><span class="sxs-lookup"><span data-stu-id="12629-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-988">10,00</span><span class="sxs-lookup"><span data-stu-id="12629-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="12629-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="12629-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="12629-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="12629-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="12629-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="12629-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="12629-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="12629-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="12629-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="12629-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="12629-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="12629-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="12629-996">Per ulteriori informazioni, vedere [Rollup costi](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="12629-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



