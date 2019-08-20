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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cef4a80aa12927fdbffea4bb6bcb108ad81494a6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841491"
---
# <a name="overhead-calculation"></a><span data-ttu-id="cc5cc-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc5cc-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="cc5cc-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="cc5cc-105">Term definition</span></span>
---------------

<span data-ttu-id="cc5cc-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="cc5cc-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="cc5cc-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="cc5cc-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="cc5cc-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="cc5cc-109">Rent</span></span>
-   <span data-ttu-id="cc5cc-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-110">Electricity</span></span>
-   <span data-ttu-id="cc5cc-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="cc5cc-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="cc5cc-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="cc5cc-112">Overhead calculation overview</span></span>
<span data-ttu-id="cc5cc-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="cc5cc-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="cc5cc-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="cc5cc-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="cc5cc-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="cc5cc-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="cc5cc-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="cc5cc-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-119">Version type</span></span>
-   <span data-ttu-id="cc5cc-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="cc5cc-120">Date and time</span></span>
-   <span data-ttu-id="cc5cc-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="cc5cc-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-122">Fiscal year</span></span>
-   <span data-ttu-id="cc5cc-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-123">Fiscal period</span></span>

<span data-ttu-id="cc5cc-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="cc5cc-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="cc5cc-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="cc5cc-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="cc5cc-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="cc5cc-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="cc5cc-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="cc5cc-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="cc5cc-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="cc5cc-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="cc5cc-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="cc5cc-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="cc5cc-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="cc5cc-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-140">Main account</span></span></th>
<th><span data-ttu-id="cc5cc-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-143">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-143">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-144">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-145">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-145">10001</span></span></td>
<td><span data-ttu-id="cc5cc-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-146">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="cc5cc-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="cc5cc-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="cc5cc-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="cc5cc-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-151">Define the cost behavior rule</span></span>

<span data-ttu-id="cc5cc-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="cc5cc-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="cc5cc-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="cc5cc-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="cc5cc-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="cc5cc-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="cc5cc-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="cc5cc-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="cc5cc-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-160">Journal</span></span></th>
<th><span data-ttu-id="cc5cc-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="cc5cc-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="cc5cc-163">Versione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-164">00001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-164">00001</span></span></td>
<td><span data-ttu-id="cc5cc-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="cc5cc-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-166">Fiscal</span></span></td>
<td><span data-ttu-id="cc5cc-167">2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-167">2017</span></span></td>
<td><span data-ttu-id="cc5cc-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-168">Period 1</span></span></td>
<td><span data-ttu-id="cc5cc-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="cc5cc-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-173">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-174">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-175">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-177">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-177">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-178">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-179">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-179">10001</span></span></td>
<td><span data-ttu-id="cc5cc-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-180">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="cc5cc-181">Unclassified</span></span></td>
<td><span data-ttu-id="cc5cc-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="cc5cc-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-185">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-186">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-187">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-187">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-189">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-189">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-190">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-191">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-191">10001</span></span></td>
<td><span data-ttu-id="cc5cc-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-192">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="cc5cc-193">Unclassified</span></span></td>
<td><span data-ttu-id="cc5cc-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-194">10,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-196">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-196">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-197">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-198">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-198">10001</span></span></td>
<td><span data-ttu-id="cc5cc-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-199">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="cc5cc-200">Unclassified</span></span></td>
<td><span data-ttu-id="cc5cc-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-201">-10,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-203">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-203">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-204">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-205">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-205">10001</span></span></td>
<td><span data-ttu-id="cc5cc-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-206">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-207">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-208">1,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-210">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-210">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-211">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-212">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-212">10001</span></span></td>
<td><span data-ttu-id="cc5cc-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-213">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-214">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-215">9,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="cc5cc-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="cc5cc-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="cc5cc-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="cc5cc-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-221">Define the cost distribution rule</span></span>

<span data-ttu-id="cc5cc-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="cc5cc-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="cc5cc-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="cc5cc-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="cc5cc-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="cc5cc-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-228">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-229">KWH</span><span class="sxs-lookup"><span data-stu-id="cc5cc-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-230">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-230">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-231">HR</span></span></td>
<td><span data-ttu-id="cc5cc-232">1.000</span><span class="sxs-lookup"><span data-stu-id="cc5cc-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-233">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-233">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-234">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-235">6.000</span><span class="sxs-lookup"><span data-stu-id="cc5cc-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-236">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-236">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-237">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-238">0</span><span class="sxs-lookup"><span data-stu-id="cc5cc-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-240">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-241">Magnitude</span></span></th>
<th><span data-ttu-id="cc5cc-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-242">Allocation factor</span></span></th>
<th><span data-ttu-id="cc5cc-243">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-244">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-244">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-245">HR</span></span></td>
<td><span data-ttu-id="cc5cc-246">1.000</span><span class="sxs-lookup"><span data-stu-id="cc5cc-246">1,000</span></span></td>
<td><span data-ttu-id="cc5cc-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-249">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-249">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-250">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-251">6.000</span><span class="sxs-lookup"><span data-stu-id="cc5cc-251">6,000</span></span></td>
<td><span data-ttu-id="cc5cc-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="cc5cc-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-254">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-254">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-255">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-256">0</span><span class="sxs-lookup"><span data-stu-id="cc5cc-256">0</span></span></td>
<td><span data-ttu-id="cc5cc-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-258">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="cc5cc-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-261">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-262">Formula</span><span class="sxs-lookup"><span data-stu-id="cc5cc-262">Formula</span></span></th>
<th><span data-ttu-id="cc5cc-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-263">Magnitude</span></span></th>
<th><span data-ttu-id="cc5cc-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-264">Allocation factor</span></span></th>
<th><span data-ttu-id="cc5cc-265">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-266">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-266">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-267">HR</span></span></td>
<td><span data-ttu-id="cc5cc-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="cc5cc-269">1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-269">1</span></span></td>
<td><span data-ttu-id="cc5cc-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-271">500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-272">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-272">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-273">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="cc5cc-275">1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-275">1</span></span></td>
<td><span data-ttu-id="cc5cc-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-277">500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-278">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-278">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-279">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="cc5cc-281">0</span><span class="sxs-lookup"><span data-stu-id="cc5cc-281">0</span></span></td>
<td><span data-ttu-id="cc5cc-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-283">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="cc5cc-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-285">Journal</span></span></th>
<th><span data-ttu-id="cc5cc-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="cc5cc-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="cc5cc-288">Versione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-289">00002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-289">00002</span></span></td>
<td><span data-ttu-id="cc5cc-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="cc5cc-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-291">Fiscal</span></span></td>
<td><span data-ttu-id="cc5cc-292">2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-292">2017</span></span></td>
<td><span data-ttu-id="cc5cc-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-293">Period 1</span></span></td>
<td><span data-ttu-id="cc5cc-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="cc5cc-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-298">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-299">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-300">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-302">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-302">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-303">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-304">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-304">10001</span></span></td>
<td><span data-ttu-id="cc5cc-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-305">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-306">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-309">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-309">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-310">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-311">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-311">10001</span></span></td>
<td><span data-ttu-id="cc5cc-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-312">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-313">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="cc5cc-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-317">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-318">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-319">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-319">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-321">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-321">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-322">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-323">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-323">10001</span></span></td>
<td><span data-ttu-id="cc5cc-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-324">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-325">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-326">-1,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-328">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-328">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-329">HR</span></span></td>
<td><span data-ttu-id="cc5cc-330">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-330">10001</span></span></td>
<td><span data-ttu-id="cc5cc-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-331">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-332">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-333">500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-333">500.00</span></span></td>
<td><span data-ttu-id="cc5cc-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-335">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-335">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-336">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-337">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-337">10001</span></span></td>
<td><span data-ttu-id="cc5cc-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-338">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-339">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-340">500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-340">500.00</span></span></td>
<td><span data-ttu-id="cc5cc-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-342">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-342">CC099</span></span></td>
<td><span data-ttu-id="cc5cc-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="cc5cc-343">Default cost center</span></span></td>
<td><span data-ttu-id="cc5cc-344">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-344">10001</span></span></td>
<td><span data-ttu-id="cc5cc-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-345">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-346">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-347">-9,000.00</span></span></td>
<td><span data-ttu-id="cc5cc-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-349">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-349">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-350">HR</span></span></td>
<td><span data-ttu-id="cc5cc-351">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-351">10001</span></span></td>
<td><span data-ttu-id="cc5cc-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-352">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-353">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-354">1,285.71</span></span></td>
<td><span data-ttu-id="cc5cc-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-356">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-356">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-357">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-358">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-358">10001</span></span></td>
<td><span data-ttu-id="cc5cc-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-359">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-360">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="cc5cc-361">7,714.29</span></span></td>
<td><span data-ttu-id="cc5cc-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="cc5cc-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="cc5cc-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="cc5cc-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="cc5cc-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="cc5cc-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="cc5cc-367">Define the overhead rate</span></span>

<span data-ttu-id="cc5cc-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="cc5cc-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-370">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-371">Ore</span><span class="sxs-lookup"><span data-stu-id="cc5cc-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-372">Proj 1</span></span></td>
<td><span data-ttu-id="cc5cc-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-373">Project 1</span></span></td>
<td><span data-ttu-id="cc5cc-374">3</span><span class="sxs-lookup"><span data-stu-id="cc5cc-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-375">Proj 2</span></span></td>
<td><span data-ttu-id="cc5cc-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-376">Project 2</span></span></td>
<td><span data-ttu-id="cc5cc-377">1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-379">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-380">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-381">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-382">Unità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-382">Units</span></span></th>
<th><span data-ttu-id="cc5cc-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-384">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-384">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-385">HR</span></span></td>
<td><span data-ttu-id="cc5cc-386">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-386">10001</span></span></td>
<td><span data-ttu-id="cc5cc-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-387">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-388">1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-388">1</span></span></td>
<td><span data-ttu-id="cc5cc-389">10</span><span class="sxs-lookup"><span data-stu-id="cc5cc-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-391">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-392">Magnitude</span></span></th>
<th><span data-ttu-id="cc5cc-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-393">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-394">Allocation factor</span></span></th>
<th><span data-ttu-id="cc5cc-395">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-396">Proj 1</span></span></td>
<td><span data-ttu-id="cc5cc-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-397">Project 1</span></span></td>
<td><span data-ttu-id="cc5cc-398">3</span><span class="sxs-lookup"><span data-stu-id="cc5cc-398">3</span></span></td>
<td><span data-ttu-id="cc5cc-399">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-399">10001</span></span></td>
<td><span data-ttu-id="cc5cc-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="cc5cc-401">30,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-402">Proj 2</span></span></td>
<td><span data-ttu-id="cc5cc-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-403">Project 2</span></span></td>
<td><span data-ttu-id="cc5cc-404">1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-404">1</span></span></td>
<td><span data-ttu-id="cc5cc-405">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-405">10001</span></span></td>
<td><span data-ttu-id="cc5cc-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="cc5cc-407">10,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="cc5cc-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-409">Journal</span></span></th>
<th><span data-ttu-id="cc5cc-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="cc5cc-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="cc5cc-412">Versione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-413">00003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-413">00003</span></span></td>
<td><span data-ttu-id="cc5cc-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="cc5cc-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="cc5cc-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-415">Fiscal</span></span></td>
<td><span data-ttu-id="cc5cc-416">2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-416">2017</span></span></td>
<td><span data-ttu-id="cc5cc-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-417">Period 1</span></span></td>
<td><span data-ttu-id="cc5cc-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="cc5cc-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-421">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-424">Proj 1</span></span></td>
<td><span data-ttu-id="cc5cc-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="cc5cc-426">3,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-428">Proj 2</span></span></td>
<td><span data-ttu-id="cc5cc-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="cc5cc-430">1,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="cc5cc-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-433">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-434">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-435">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-435">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-437">CC0001</span></span></td>
<td><span data-ttu-id="cc5cc-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-438">HR</span></span></td>
<td><span data-ttu-id="cc5cc-439">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-439">10001</span></span></td>
<td><span data-ttu-id="cc5cc-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-440">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-441">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-442">-30.00</span></span></td>
<td><span data-ttu-id="cc5cc-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-444">Proj 1</span></span></td>
<td><span data-ttu-id="cc5cc-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="cc5cc-446">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-446">10001</span></span></td>
<td><span data-ttu-id="cc5cc-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-447">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-448">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-449">30,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-449">30.00</span></span></td>
<td><span data-ttu-id="cc5cc-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-451">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-451">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-452">HR</span></span></td>
<td><span data-ttu-id="cc5cc-453">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-453">10001</span></span></td>
<td><span data-ttu-id="cc5cc-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-454">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-455">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-456">-10.00</span></span></td>
<td><span data-ttu-id="cc5cc-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-458">Proj 2</span></span></td>
<td><span data-ttu-id="cc5cc-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="cc5cc-460">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-460">10001</span></span></td>
<td><span data-ttu-id="cc5cc-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-461">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-462">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-463">10.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-463">10.00</span></span></td>
<td><span data-ttu-id="cc5cc-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="cc5cc-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="cc5cc-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="cc5cc-468">Finance and Operations supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="cc5cc-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="cc5cc-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="cc5cc-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="cc5cc-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="cc5cc-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="cc5cc-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="cc5cc-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="cc5cc-475">Define the cost allocation</span></span>

<span data-ttu-id="cc5cc-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="cc5cc-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="cc5cc-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-479">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="cc5cc-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-481">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-481">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-482">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-483">35</span><span class="sxs-lookup"><span data-stu-id="cc5cc-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-484">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-484">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-485">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-486">55</span><span class="sxs-lookup"><span data-stu-id="cc5cc-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-487">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-487">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-488">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-489">10</span><span class="sxs-lookup"><span data-stu-id="cc5cc-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="cc5cc-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-492">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-494">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-494">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-495">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-496">65</span><span class="sxs-lookup"><span data-stu-id="cc5cc-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-497">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-497">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-498">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-499">35</span><span class="sxs-lookup"><span data-stu-id="cc5cc-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="cc5cc-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-502">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-504">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-505">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-506">60</span><span class="sxs-lookup"><span data-stu-id="cc5cc-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-507">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-508">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-509">20</span><span class="sxs-lookup"><span data-stu-id="cc5cc-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="cc5cc-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-512">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-514">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-515">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-516">80</span><span class="sxs-lookup"><span data-stu-id="cc5cc-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-517">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-518">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-519">15</span><span class="sxs-lookup"><span data-stu-id="cc5cc-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="cc5cc-520">In Finance and Operations, le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="cc5cc-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="cc5cc-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-523">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-524">Magnitude</span></span></th>
<th><span data-ttu-id="cc5cc-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-525">Allocation factor</span></span></th>
<th><span data-ttu-id="cc5cc-526">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-526">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-528">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-528">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-529">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-530">35</span><span class="sxs-lookup"><span data-stu-id="cc5cc-530">35</span></span></td>
<td><span data-ttu-id="cc5cc-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="cc5cc-532">175.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-532">175.00</span></span></td>
<td><span data-ttu-id="cc5cc-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-534">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-534">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-535">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-536">55</span><span class="sxs-lookup"><span data-stu-id="cc5cc-536">55</span></span></td>
<td><span data-ttu-id="cc5cc-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="cc5cc-538">275.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-538">275.00</span></span></td>
<td><span data-ttu-id="cc5cc-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-540">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-540">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-541">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-542">10</span><span class="sxs-lookup"><span data-stu-id="cc5cc-542">10</span></span></td>
<td><span data-ttu-id="cc5cc-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="cc5cc-544">50,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-544">50.00</span></span></td>
<td><span data-ttu-id="cc5cc-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-546">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-546">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-547">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-548">35</span><span class="sxs-lookup"><span data-stu-id="cc5cc-548">35</span></span></td>
<td><span data-ttu-id="cc5cc-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="cc5cc-550">436.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-550">436.00</span></span></td>
<td><span data-ttu-id="cc5cc-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-552">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-552">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-553">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-554">55</span><span class="sxs-lookup"><span data-stu-id="cc5cc-554">55</span></span></td>
<td><span data-ttu-id="cc5cc-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="cc5cc-556">685.14</span><span class="sxs-lookup"><span data-stu-id="cc5cc-556">685.14</span></span></td>
<td><span data-ttu-id="cc5cc-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-558">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-558">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-559">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-560">10</span><span class="sxs-lookup"><span data-stu-id="cc5cc-560">10</span></span></td>
<td><span data-ttu-id="cc5cc-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="cc5cc-562">124.57</span><span class="sxs-lookup"><span data-stu-id="cc5cc-562">124.57</span></span></td>
<td><span data-ttu-id="cc5cc-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-565">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-566">Magnitude</span></span></th>
<th><span data-ttu-id="cc5cc-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-567">Allocation factor</span></span></th>
<th><span data-ttu-id="cc5cc-568">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-568">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-570">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-570">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-571">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-572">65</span><span class="sxs-lookup"><span data-stu-id="cc5cc-572">65</span></span></td>
<td><span data-ttu-id="cc5cc-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="cc5cc-574">438.75</span><span class="sxs-lookup"><span data-stu-id="cc5cc-574">438.75</span></span></td>
<td><span data-ttu-id="cc5cc-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-576">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-576">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-577">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-578">35</span><span class="sxs-lookup"><span data-stu-id="cc5cc-578">35</span></span></td>
<td><span data-ttu-id="cc5cc-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="cc5cc-580">236.25</span><span class="sxs-lookup"><span data-stu-id="cc5cc-580">236.25</span></span></td>
<td><span data-ttu-id="cc5cc-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-582">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-582">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-583">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-584">65</span><span class="sxs-lookup"><span data-stu-id="cc5cc-584">65</span></span></td>
<td><span data-ttu-id="cc5cc-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="cc5cc-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="cc5cc-586">5,297.69</span></span></td>
<td><span data-ttu-id="cc5cc-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-588">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-588">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-589">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-590">35</span><span class="sxs-lookup"><span data-stu-id="cc5cc-590">35</span></span></td>
<td><span data-ttu-id="cc5cc-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="cc5cc-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="cc5cc-592">2,852.60</span></span></td>
<td><span data-ttu-id="cc5cc-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-595">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-596">Magnitude</span></span></th>
<th><span data-ttu-id="cc5cc-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-597">Allocation factor</span></span></th>
<th><span data-ttu-id="cc5cc-598">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-598">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-600">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-601">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-602">60</span><span class="sxs-lookup"><span data-stu-id="cc5cc-602">60</span></span></td>
<td><span data-ttu-id="cc5cc-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="cc5cc-604">535.31</span><span class="sxs-lookup"><span data-stu-id="cc5cc-604">535.31</span></span></td>
<td><span data-ttu-id="cc5cc-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-606">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-607">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-608">20</span><span class="sxs-lookup"><span data-stu-id="cc5cc-608">20</span></span></td>
<td><span data-ttu-id="cc5cc-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="cc5cc-610">178.44</span><span class="sxs-lookup"><span data-stu-id="cc5cc-610">178.44</span></span></td>
<td><span data-ttu-id="cc5cc-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-612">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-613">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-614">60</span><span class="sxs-lookup"><span data-stu-id="cc5cc-614">60</span></span></td>
<td><span data-ttu-id="cc5cc-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="cc5cc-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="cc5cc-616">4,487.12</span></span></td>
<td><span data-ttu-id="cc5cc-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-618">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-619">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-620">20</span><span class="sxs-lookup"><span data-stu-id="cc5cc-620">20</span></span></td>
<td><span data-ttu-id="cc5cc-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="cc5cc-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-622">1,495.71</span></span></td>
<td><span data-ttu-id="cc5cc-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cc5cc-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-625">Cost object</span></span></th>
<th><span data-ttu-id="cc5cc-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="cc5cc-626">Magnitude</span></span></th>
<th><span data-ttu-id="cc5cc-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-627">Allocation factor</span></span></th>
<th><span data-ttu-id="cc5cc-628">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-628">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-630">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-631">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-632">80</span><span class="sxs-lookup"><span data-stu-id="cc5cc-632">80</span></span></td>
<td><span data-ttu-id="cc5cc-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="cc5cc-634">241.05</span><span class="sxs-lookup"><span data-stu-id="cc5cc-634">241.05</span></span></td>
<td><span data-ttu-id="cc5cc-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-636">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-637">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-638">15</span><span class="sxs-lookup"><span data-stu-id="cc5cc-638">15</span></span></td>
<td><span data-ttu-id="cc5cc-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="cc5cc-640">45.20</span><span class="sxs-lookup"><span data-stu-id="cc5cc-640">45.20</span></span></td>
<td><span data-ttu-id="cc5cc-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-642">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-643">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-644">80</span><span class="sxs-lookup"><span data-stu-id="cc5cc-644">80</span></span></td>
<td><span data-ttu-id="cc5cc-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="cc5cc-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="cc5cc-646">2,507.09</span></span></td>
<td><span data-ttu-id="cc5cc-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-648">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-649">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-650">15</span><span class="sxs-lookup"><span data-stu-id="cc5cc-650">15</span></span></td>
<td><span data-ttu-id="cc5cc-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="cc5cc-652">470.08</span><span class="sxs-lookup"><span data-stu-id="cc5cc-652">470.08</span></span></td>
<td><span data-ttu-id="cc5cc-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="cc5cc-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="cc5cc-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-655">Journal</span></span></th>
<th><span data-ttu-id="cc5cc-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="cc5cc-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="cc5cc-658">Versione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-659">00004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-659">00004</span></span></td>
<td><span data-ttu-id="cc5cc-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="cc5cc-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="cc5cc-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-661">Fiscal</span></span></td>
<td><span data-ttu-id="cc5cc-662">2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-662">2017</span></span></td>
<td><span data-ttu-id="cc5cc-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-663">Period 1</span></span></td>
<td><span data-ttu-id="cc5cc-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="cc5cc-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="cc5cc-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-668">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-669">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-670">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-672">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-672">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-673">HR</span></span></td>
<td><span data-ttu-id="cc5cc-674">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-674">10001</span></span></td>
<td><span data-ttu-id="cc5cc-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-675">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-676">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-677">500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-679">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-679">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-680">HR</span></span></td>
<td><span data-ttu-id="cc5cc-681">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-681">10001</span></span></td>
<td><span data-ttu-id="cc5cc-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-682">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-683">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-686">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-686">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-687">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-688">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-688">10001</span></span></td>
<td><span data-ttu-id="cc5cc-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-689">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-690">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-691">675.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-693">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-693">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-694">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-695">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-695">10001</span></span></td>
<td><span data-ttu-id="cc5cc-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-696">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-697">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="cc5cc-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-700">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-700">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-701">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-702">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-702">10001</span></span></td>
<td><span data-ttu-id="cc5cc-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-703">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-704">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-705">713.75</span><span class="sxs-lookup"><span data-stu-id="cc5cc-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-707">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-707">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-708">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-709">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-709">10001</span></span></td>
<td><span data-ttu-id="cc5cc-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-710">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-711">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="cc5cc-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-714">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-714">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-715">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-716">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-716">10001</span></span></td>
<td><span data-ttu-id="cc5cc-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-717">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-718">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-719">286.25</span><span class="sxs-lookup"><span data-stu-id="cc5cc-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-721">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-721">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-722">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-723">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-723">10001</span></span></td>
<td><span data-ttu-id="cc5cc-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-724">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-725">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="cc5cc-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-728">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-729">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-730">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-730">10001</span></span></td>
<td><span data-ttu-id="cc5cc-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-731">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-732">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-733">776.36</span><span class="sxs-lookup"><span data-stu-id="cc5cc-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-735">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-736">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-737">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-737">10001</span></span></td>
<td><span data-ttu-id="cc5cc-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-738">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-739">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="cc5cc-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-742">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-743">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-744">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-744">10001</span></span></td>
<td><span data-ttu-id="cc5cc-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-745">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-746">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-747">223.64</span><span class="sxs-lookup"><span data-stu-id="cc5cc-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="cc5cc-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-749">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-750">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-751">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-751">10001</span></span></td>
<td><span data-ttu-id="cc5cc-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-752">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-753">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="cc5cc-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="cc5cc-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="cc5cc-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="cc5cc-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-757">Cost element</span></span></th>
<th><span data-ttu-id="cc5cc-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-758">Cost behavior</span></span></th>
<th><span data-ttu-id="cc5cc-759">Importo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-759">Amount</span></span></th>
<th><span data-ttu-id="cc5cc-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="cc5cc-761">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-761">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-762">HR</span></span></td>
<td><span data-ttu-id="cc5cc-763">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-763">10001</span></span></td>
<td><span data-ttu-id="cc5cc-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-764">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-765">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-766">-500.00</span></span></td>
<td><span data-ttu-id="cc5cc-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-768">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-768">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-769">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-770">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-770">10001</span></span></td>
<td><span data-ttu-id="cc5cc-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-771">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-772">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-773">175.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-773">175.00</span></span></td>
<td><span data-ttu-id="cc5cc-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-775">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-775">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-776">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-777">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-777">10001</span></span></td>
<td><span data-ttu-id="cc5cc-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-778">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-779">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-780">275.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-780">275.00</span></span></td>
<td><span data-ttu-id="cc5cc-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-782">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-782">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-783">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-784">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-784">10001</span></span></td>
<td><span data-ttu-id="cc5cc-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-785">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-786">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-787">50,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-787">50,00</span></span></td>
<td><span data-ttu-id="cc5cc-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-789">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-789">CC001</span></span></td>
<td><span data-ttu-id="cc5cc-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="cc5cc-790">HR</span></span></td>
<td><span data-ttu-id="cc5cc-791">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-791">10001</span></span></td>
<td><span data-ttu-id="cc5cc-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-792">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-793">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-794">-1,245.71</span></span></td>
<td><span data-ttu-id="cc5cc-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-796">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-796">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-797">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-798">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-798">10001</span></span></td>
<td><span data-ttu-id="cc5cc-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-799">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-800">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-801">436.00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-801">436.00</span></span></td>
<td><span data-ttu-id="cc5cc-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-803">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-803">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-804">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-805">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-805">10001</span></span></td>
<td><span data-ttu-id="cc5cc-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-806">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-807">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-808">685.14</span><span class="sxs-lookup"><span data-stu-id="cc5cc-808">685.14</span></span></td>
<td><span data-ttu-id="cc5cc-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-810">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-810">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-811">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-812">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-812">10001</span></span></td>
<td><span data-ttu-id="cc5cc-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-813">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-814">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-815">124.57</span><span class="sxs-lookup"><span data-stu-id="cc5cc-815">124.57</span></span></td>
<td><span data-ttu-id="cc5cc-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-817">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-817">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-818">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-819">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-819">10001</span></span></td>
<td><span data-ttu-id="cc5cc-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-820">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-821">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-822">-675.00</span></span></td>
<td><span data-ttu-id="cc5cc-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-824">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-824">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-825">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-826">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-826">10001</span></span></td>
<td><span data-ttu-id="cc5cc-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-827">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-828">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-829">438.75</span><span class="sxs-lookup"><span data-stu-id="cc5cc-829">438.75</span></span></td>
<td><span data-ttu-id="cc5cc-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-831">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-831">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-832">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-833">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-833">10001</span></span></td>
<td><span data-ttu-id="cc5cc-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-834">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-835">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-836">236.25</span><span class="sxs-lookup"><span data-stu-id="cc5cc-836">236.25</span></span></td>
<td><span data-ttu-id="cc5cc-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-838">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-838">CC002</span></span></td>
<td><span data-ttu-id="cc5cc-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="cc5cc-839">Finance</span></span></td>
<td><span data-ttu-id="cc5cc-840">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-840">10001</span></span></td>
<td><span data-ttu-id="cc5cc-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-841">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-842">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="cc5cc-843">-8,150.29</span></span></td>
<td><span data-ttu-id="cc5cc-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-845">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-845">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-846">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-847">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-847">10001</span></span></td>
<td><span data-ttu-id="cc5cc-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-848">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-849">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="cc5cc-850">5,297.69</span></span></td>
<td><span data-ttu-id="cc5cc-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-852">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-852">CC004</span></span></td>
<td><span data-ttu-id="cc5cc-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-853">Packaging</span></span></td>
<td><span data-ttu-id="cc5cc-854">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-854">10001</span></span></td>
<td><span data-ttu-id="cc5cc-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-855">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-856">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="cc5cc-857">2,852.60</span></span></td>
<td><span data-ttu-id="cc5cc-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-859">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-859">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-860">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-861">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-861">10001</span></span></td>
<td><span data-ttu-id="cc5cc-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-862">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-863">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="cc5cc-864">-713.75</span></span></td>
<td><span data-ttu-id="cc5cc-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-866">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-867">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-868">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-868">10001</span></span></td>
<td><span data-ttu-id="cc5cc-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-869">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-870">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-871">535.31</span><span class="sxs-lookup"><span data-stu-id="cc5cc-871">535.31</span></span></td>
<td><span data-ttu-id="cc5cc-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-873">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-874">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-875">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-875">10001</span></span></td>
<td><span data-ttu-id="cc5cc-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-876">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-877">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-878">178.44</span><span class="sxs-lookup"><span data-stu-id="cc5cc-878">178.44</span></span></td>
<td><span data-ttu-id="cc5cc-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-880">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-880">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-881">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-882">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-882">10001</span></span></td>
<td><span data-ttu-id="cc5cc-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-883">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-884">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="cc5cc-885">-5,982.83</span></span></td>
<td><span data-ttu-id="cc5cc-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-887">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-888">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-889">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-889">10001</span></span></td>
<td><span data-ttu-id="cc5cc-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-890">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-891">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="cc5cc-892">4,487.12</span></span></td>
<td><span data-ttu-id="cc5cc-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-894">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-895">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-896">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-896">10001</span></span></td>
<td><span data-ttu-id="cc5cc-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-897">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-898">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="cc5cc-899">1,495.71</span></span></td>
<td><span data-ttu-id="cc5cc-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-901">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-901">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-902">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-903">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-903">10001</span></span></td>
<td><span data-ttu-id="cc5cc-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-904">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-905">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="cc5cc-906">-286.25</span></span></td>
<td><span data-ttu-id="cc5cc-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-908">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-909">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-910">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-910">10001</span></span></td>
<td><span data-ttu-id="cc5cc-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-911">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-912">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-913">241.05</span><span class="sxs-lookup"><span data-stu-id="cc5cc-913">241.05</span></span></td>
<td><span data-ttu-id="cc5cc-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-915">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-916">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-917">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-917">10001</span></span></td>
<td><span data-ttu-id="cc5cc-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-918">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-919">Fixed cost</span></span></td>
<td><span data-ttu-id="cc5cc-920">45.20</span><span class="sxs-lookup"><span data-stu-id="cc5cc-920">45.20</span></span></td>
<td><span data-ttu-id="cc5cc-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-922">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-922">CC003</span></span></td>
<td><span data-ttu-id="cc5cc-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="cc5cc-923">Assembly</span></span></td>
<td><span data-ttu-id="cc5cc-924">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-924">10001</span></span></td>
<td><span data-ttu-id="cc5cc-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-925">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-926">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="cc5cc-927">-2,977.17</span></span></td>
<td><span data-ttu-id="cc5cc-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-929">Prod 1</span></span></td>
<td><span data-ttu-id="cc5cc-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-930">Product 1</span></span></td>
<td><span data-ttu-id="cc5cc-931">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-931">10001</span></span></td>
<td><span data-ttu-id="cc5cc-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-932">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-933">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="cc5cc-934">2,507.09</span></span></td>
<td><span data-ttu-id="cc5cc-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="cc5cc-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-936">Prod 2</span></span></td>
<td><span data-ttu-id="cc5cc-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-937">Product 2</span></span></td>
<td><span data-ttu-id="cc5cc-938">10001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-938">10001</span></span></td>
<td><span data-ttu-id="cc5cc-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-939">Electricity</span></span></td>
<td><span data-ttu-id="cc5cc-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-940">Variable cost</span></span></td>
<td><span data-ttu-id="cc5cc-941">470.08</span><span class="sxs-lookup"><span data-stu-id="cc5cc-941">470.08</span></span></td>
<td><span data-ttu-id="cc5cc-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="cc5cc-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="cc5cc-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="cc5cc-943">Conclusion</span></span>
<span data-ttu-id="cc5cc-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="cc5cc-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="cc5cc-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="cc5cc-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="cc5cc-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="cc5cc-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="cc5cc-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="cc5cc-950">Totale</span><span class="sxs-lookup"><span data-stu-id="cc5cc-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="cc5cc-951">CC099</span><span class="sxs-lookup"><span data-stu-id="cc5cc-951">CC099</span></span></th>
<th><span data-ttu-id="cc5cc-952">CC001</span><span class="sxs-lookup"><span data-stu-id="cc5cc-952">CC001</span></span></th>
<th><span data-ttu-id="cc5cc-953">CC002</span><span class="sxs-lookup"><span data-stu-id="cc5cc-953">CC002</span></span></th>
<th><span data-ttu-id="cc5cc-954">CC003</span><span class="sxs-lookup"><span data-stu-id="cc5cc-954">CC003</span></span></th>
<th><span data-ttu-id="cc5cc-955">CC004</span><span class="sxs-lookup"><span data-stu-id="cc5cc-955">CC004</span></span></th>
<th><span data-ttu-id="cc5cc-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-956">Proj 1</span></span></th>
<th><span data-ttu-id="cc5cc-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-957">Proj 2</span></span></th>
<th><span data-ttu-id="cc5cc-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="cc5cc-958">Prod 1</span></span></th>
<th><span data-ttu-id="cc5cc-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="cc5cc-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="cc5cc-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="cc5cc-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="cc5cc-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="cc5cc-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-971">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="cc5cc-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="cc5cc-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-973">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-974">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-975">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-976">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-977">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-978">776.36</span><span class="sxs-lookup"><span data-stu-id="cc5cc-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-979">223.64</span><span class="sxs-lookup"><span data-stu-id="cc5cc-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="cc5cc-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="cc5cc-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-982">000</span><span class="sxs-lookup"><span data-stu-id="cc5cc-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-983">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-984">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-985">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-986">0,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-987">30,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-988">10,00</span><span class="sxs-lookup"><span data-stu-id="cc5cc-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="cc5cc-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="cc5cc-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="cc5cc-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="cc5cc-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="cc5cc-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="cc5cc-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="cc5cc-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="cc5cc-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="cc5cc-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="cc5cc-996">Per ulteriori informazioni, vedere [Rollup costi](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="cc5cc-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



