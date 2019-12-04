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
ms.openlocfilehash: 954e0669c3d24bcc20fe667c22b7dcc367aba1e7
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770806"
---
# <a name="overhead-calculation"></a><span data-ttu-id="16ad9-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="16ad9-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16ad9-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="16ad9-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="16ad9-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="16ad9-105">Term definition</span></span>
---------------

<span data-ttu-id="16ad9-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="16ad9-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="16ad9-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="16ad9-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="16ad9-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="16ad9-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="16ad9-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="16ad9-109">Rent</span></span>
-   <span data-ttu-id="16ad9-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-110">Electricity</span></span>
-   <span data-ttu-id="16ad9-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="16ad9-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="16ad9-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="16ad9-112">Overhead calculation overview</span></span>
<span data-ttu-id="16ad9-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="16ad9-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="16ad9-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="16ad9-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="16ad9-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="16ad9-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="16ad9-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="16ad9-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="16ad9-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="16ad9-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="16ad9-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="16ad9-119">Version type</span></span>
-   <span data-ttu-id="16ad9-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="16ad9-120">Date and time</span></span>
-   <span data-ttu-id="16ad9-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="16ad9-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="16ad9-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-122">Fiscal year</span></span>
-   <span data-ttu-id="16ad9-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-123">Fiscal period</span></span>

<span data-ttu-id="16ad9-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="16ad9-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="16ad9-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="16ad9-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="16ad9-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="16ad9-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="16ad9-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="16ad9-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="16ad9-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="16ad9-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="16ad9-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="16ad9-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="16ad9-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="16ad9-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="16ad9-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="16ad9-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="16ad9-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="16ad9-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="16ad9-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="16ad9-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="16ad9-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="16ad9-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="16ad9-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="16ad9-140">Main account</span></span></th>
<th><span data-ttu-id="16ad9-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="16ad9-143">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-143">CC099</span></span></td>
<td><span data-ttu-id="16ad9-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-144">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-145">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-145">10001</span></span></td>
<td><span data-ttu-id="16ad9-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-146">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="16ad9-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="16ad9-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="16ad9-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="16ad9-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="16ad9-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="16ad9-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-151">Define the cost behavior rule</span></span>

<span data-ttu-id="16ad9-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="16ad9-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="16ad9-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="16ad9-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="16ad9-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="16ad9-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="16ad9-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="16ad9-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="16ad9-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="16ad9-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-160">Journal</span></span></th>
<th><span data-ttu-id="16ad9-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="16ad9-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="16ad9-163">Versione</span><span class="sxs-lookup"><span data-stu-id="16ad9-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-164">00001</span><span class="sxs-lookup"><span data-stu-id="16ad9-164">00001</span></span></td>
<td><span data-ttu-id="16ad9-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="16ad9-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-166">Fiscal</span></span></td>
<td><span data-ttu-id="16ad9-167">2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-167">2017</span></span></td>
<td><span data-ttu-id="16ad9-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-168">Period 1</span></span></td>
<td><span data-ttu-id="16ad9-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="16ad9-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="16ad9-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-173">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-174">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-175">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="16ad9-177">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-177">CC099</span></span></td>
<td><span data-ttu-id="16ad9-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-178">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-179">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-179">10001</span></span></td>
<td><span data-ttu-id="16ad9-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-180">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="16ad9-181">Unclassified</span></span></td>
<td><span data-ttu-id="16ad9-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="16ad9-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-185">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-186">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-187">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-187">Amount</span></span></th>
<th><span data-ttu-id="16ad9-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-189">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-189">CC099</span></span></td>
<td><span data-ttu-id="16ad9-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-190">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-191">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-191">10001</span></span></td>
<td><span data-ttu-id="16ad9-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-192">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="16ad9-193">Unclassified</span></span></td>
<td><span data-ttu-id="16ad9-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-194">10,000.00</span></span></td>
<td><span data-ttu-id="16ad9-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-196">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-196">CC099</span></span></td>
<td><span data-ttu-id="16ad9-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-197">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-198">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-198">10001</span></span></td>
<td><span data-ttu-id="16ad9-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-199">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="16ad9-200">Unclassified</span></span></td>
<td><span data-ttu-id="16ad9-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-201">-10,000.00</span></span></td>
<td><span data-ttu-id="16ad9-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-203">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-203">CC099</span></span></td>
<td><span data-ttu-id="16ad9-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-204">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-205">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-205">10001</span></span></td>
<td><span data-ttu-id="16ad9-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-206">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-207">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-208">1,000.00</span></span></td>
<td><span data-ttu-id="16ad9-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-210">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-210">CC099</span></span></td>
<td><span data-ttu-id="16ad9-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-211">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-212">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-212">10001</span></span></td>
<td><span data-ttu-id="16ad9-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-213">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-214">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-215">9,000.00</span></span></td>
<td><span data-ttu-id="16ad9-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="16ad9-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="16ad9-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="16ad9-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="16ad9-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="16ad9-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="16ad9-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="16ad9-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-221">Define the cost distribution rule</span></span>

<span data-ttu-id="16ad9-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="16ad9-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="16ad9-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="16ad9-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="16ad9-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="16ad9-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="16ad9-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="16ad9-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="16ad9-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="16ad9-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="16ad9-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-228">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-229">KWH</span><span class="sxs-lookup"><span data-stu-id="16ad9-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-230">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-230">CC001</span></span></td>
<td><span data-ttu-id="16ad9-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-231">HR</span></span></td>
<td><span data-ttu-id="16ad9-232">1.000</span><span class="sxs-lookup"><span data-stu-id="16ad9-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-233">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-233">CC002</span></span></td>
<td><span data-ttu-id="16ad9-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-234">Finance</span></span></td>
<td><span data-ttu-id="16ad9-235">6.000</span><span class="sxs-lookup"><span data-stu-id="16ad9-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-236">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-236">CC003</span></span></td>
<td><span data-ttu-id="16ad9-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-237">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-238">0</span><span class="sxs-lookup"><span data-stu-id="16ad9-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="16ad9-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-240">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-241">Magnitude</span></span></th>
<th><span data-ttu-id="16ad9-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-242">Allocation factor</span></span></th>
<th><span data-ttu-id="16ad9-243">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-244">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-244">CC001</span></span></td>
<td><span data-ttu-id="16ad9-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-245">HR</span></span></td>
<td><span data-ttu-id="16ad9-246">1.000</span><span class="sxs-lookup"><span data-stu-id="16ad9-246">1,000</span></span></td>
<td><span data-ttu-id="16ad9-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="16ad9-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="16ad9-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-249">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-249">CC002</span></span></td>
<td><span data-ttu-id="16ad9-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-250">Finance</span></span></td>
<td><span data-ttu-id="16ad9-251">6.000</span><span class="sxs-lookup"><span data-stu-id="16ad9-251">6,000</span></span></td>
<td><span data-ttu-id="16ad9-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="16ad9-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="16ad9-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-254">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-254">CC003</span></span></td>
<td><span data-ttu-id="16ad9-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-255">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-256">0</span><span class="sxs-lookup"><span data-stu-id="16ad9-256">0</span></span></td>
<td><span data-ttu-id="16ad9-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="16ad9-258">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="16ad9-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="16ad9-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="16ad9-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-261">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-262">Formula</span><span class="sxs-lookup"><span data-stu-id="16ad9-262">Formula</span></span></th>
<th><span data-ttu-id="16ad9-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-263">Magnitude</span></span></th>
<th><span data-ttu-id="16ad9-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-264">Allocation factor</span></span></th>
<th><span data-ttu-id="16ad9-265">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-266">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-266">CC001</span></span></td>
<td><span data-ttu-id="16ad9-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-267">HR</span></span></td>
<td><span data-ttu-id="16ad9-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="16ad9-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="16ad9-269">1</span><span class="sxs-lookup"><span data-stu-id="16ad9-269">1</span></span></td>
<td><span data-ttu-id="16ad9-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="16ad9-271">500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-272">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-272">CC002</span></span></td>
<td><span data-ttu-id="16ad9-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-273">Finance</span></span></td>
<td><span data-ttu-id="16ad9-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="16ad9-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="16ad9-275">1</span><span class="sxs-lookup"><span data-stu-id="16ad9-275">1</span></span></td>
<td><span data-ttu-id="16ad9-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="16ad9-277">500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-278">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-278">CC003</span></span></td>
<td><span data-ttu-id="16ad9-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-279">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="16ad9-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="16ad9-281">0</span><span class="sxs-lookup"><span data-stu-id="16ad9-281">0</span></span></td>
<td><span data-ttu-id="16ad9-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="16ad9-283">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="16ad9-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-285">Journal</span></span></th>
<th><span data-ttu-id="16ad9-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="16ad9-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="16ad9-288">Versione</span><span class="sxs-lookup"><span data-stu-id="16ad9-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-289">00002</span><span class="sxs-lookup"><span data-stu-id="16ad9-289">00002</span></span></td>
<td><span data-ttu-id="16ad9-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="16ad9-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-291">Fiscal</span></span></td>
<td><span data-ttu-id="16ad9-292">2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-292">2017</span></span></td>
<td><span data-ttu-id="16ad9-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-293">Period 1</span></span></td>
<td><span data-ttu-id="16ad9-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="16ad9-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="16ad9-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-298">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-299">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-300">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-302">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-302">CC099</span></span></td>
<td><span data-ttu-id="16ad9-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-303">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-304">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-304">10001</span></span></td>
<td><span data-ttu-id="16ad9-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-305">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-306">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-309">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-309">CC099</span></span></td>
<td><span data-ttu-id="16ad9-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-310">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-311">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-311">10001</span></span></td>
<td><span data-ttu-id="16ad9-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-312">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-313">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="16ad9-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-317">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-318">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-319">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-319">Amount</span></span></th>
<th><span data-ttu-id="16ad9-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-321">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-321">CC099</span></span></td>
<td><span data-ttu-id="16ad9-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-322">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-323">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-323">10001</span></span></td>
<td><span data-ttu-id="16ad9-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-324">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-325">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-326">-1,000.00</span></span></td>
<td><span data-ttu-id="16ad9-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-328">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-328">CC001</span></span></td>
<td><span data-ttu-id="16ad9-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-329">HR</span></span></td>
<td><span data-ttu-id="16ad9-330">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-330">10001</span></span></td>
<td><span data-ttu-id="16ad9-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-331">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-332">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-333">500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-333">500.00</span></span></td>
<td><span data-ttu-id="16ad9-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-335">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-335">CC002</span></span></td>
<td><span data-ttu-id="16ad9-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-336">Finance</span></span></td>
<td><span data-ttu-id="16ad9-337">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-337">10001</span></span></td>
<td><span data-ttu-id="16ad9-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-338">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-339">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-340">500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-340">500.00</span></span></td>
<td><span data-ttu-id="16ad9-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-342">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-342">CC099</span></span></td>
<td><span data-ttu-id="16ad9-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="16ad9-343">Default cost center</span></span></td>
<td><span data-ttu-id="16ad9-344">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-344">10001</span></span></td>
<td><span data-ttu-id="16ad9-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-345">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-346">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-347">-9,000.00</span></span></td>
<td><span data-ttu-id="16ad9-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-349">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-349">CC001</span></span></td>
<td><span data-ttu-id="16ad9-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-350">HR</span></span></td>
<td><span data-ttu-id="16ad9-351">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-351">10001</span></span></td>
<td><span data-ttu-id="16ad9-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-352">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-353">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="16ad9-354">1,285.71</span></span></td>
<td><span data-ttu-id="16ad9-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-356">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-356">CC002</span></span></td>
<td><span data-ttu-id="16ad9-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-357">Finance</span></span></td>
<td><span data-ttu-id="16ad9-358">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-358">10001</span></span></td>
<td><span data-ttu-id="16ad9-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-359">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-360">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="16ad9-361">7,714.29</span></span></td>
<td><span data-ttu-id="16ad9-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="16ad9-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="16ad9-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="16ad9-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="16ad9-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="16ad9-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="16ad9-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="16ad9-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="16ad9-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="16ad9-367">Define the overhead rate</span></span>

<span data-ttu-id="16ad9-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="16ad9-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="16ad9-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="16ad9-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-370">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-371">Ore</span><span class="sxs-lookup"><span data-stu-id="16ad9-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-372">Proj 1</span></span></td>
<td><span data-ttu-id="16ad9-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-373">Project 1</span></span></td>
<td><span data-ttu-id="16ad9-374">3</span><span class="sxs-lookup"><span data-stu-id="16ad9-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-375">Proj 2</span></span></td>
<td><span data-ttu-id="16ad9-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-376">Project 2</span></span></td>
<td><span data-ttu-id="16ad9-377">1</span><span class="sxs-lookup"><span data-stu-id="16ad9-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="16ad9-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-379">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-380">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-381">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-382">Unità</span><span class="sxs-lookup"><span data-stu-id="16ad9-382">Units</span></span></th>
<th><span data-ttu-id="16ad9-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="16ad9-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-384">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-384">CC001</span></span></td>
<td><span data-ttu-id="16ad9-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-385">HR</span></span></td>
<td><span data-ttu-id="16ad9-386">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-386">10001</span></span></td>
<td><span data-ttu-id="16ad9-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-387">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-388">1</span><span class="sxs-lookup"><span data-stu-id="16ad9-388">1</span></span></td>
<td><span data-ttu-id="16ad9-389">10</span><span class="sxs-lookup"><span data-stu-id="16ad9-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-391">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-392">Magnitude</span></span></th>
<th><span data-ttu-id="16ad9-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-393">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-394">Allocation factor</span></span></th>
<th><span data-ttu-id="16ad9-395">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-396">Proj 1</span></span></td>
<td><span data-ttu-id="16ad9-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-397">Project 1</span></span></td>
<td><span data-ttu-id="16ad9-398">3</span><span class="sxs-lookup"><span data-stu-id="16ad9-398">3</span></span></td>
<td><span data-ttu-id="16ad9-399">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-399">10001</span></span></td>
<td><span data-ttu-id="16ad9-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="16ad9-401">30,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-402">Proj 2</span></span></td>
<td><span data-ttu-id="16ad9-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-403">Project 2</span></span></td>
<td><span data-ttu-id="16ad9-404">1</span><span class="sxs-lookup"><span data-stu-id="16ad9-404">1</span></span></td>
<td><span data-ttu-id="16ad9-405">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-405">10001</span></span></td>
<td><span data-ttu-id="16ad9-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="16ad9-407">10,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="16ad9-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-409">Journal</span></span></th>
<th><span data-ttu-id="16ad9-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="16ad9-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="16ad9-412">Versione</span><span class="sxs-lookup"><span data-stu-id="16ad9-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-413">00003</span><span class="sxs-lookup"><span data-stu-id="16ad9-413">00003</span></span></td>
<td><span data-ttu-id="16ad9-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="16ad9-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="16ad9-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-415">Fiscal</span></span></td>
<td><span data-ttu-id="16ad9-416">2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-416">2017</span></span></td>
<td><span data-ttu-id="16ad9-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-417">Period 1</span></span></td>
<td><span data-ttu-id="16ad9-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="16ad9-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="16ad9-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-421">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-424">Proj 1</span></span></td>
<td><span data-ttu-id="16ad9-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="16ad9-426">3,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-428">Proj 2</span></span></td>
<td><span data-ttu-id="16ad9-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="16ad9-430">1,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="16ad9-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-433">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-434">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-435">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-435">Amount</span></span></th>
<th><span data-ttu-id="16ad9-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="16ad9-437">CC0001</span></span></td>
<td><span data-ttu-id="16ad9-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-438">HR</span></span></td>
<td><span data-ttu-id="16ad9-439">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-439">10001</span></span></td>
<td><span data-ttu-id="16ad9-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-440">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-441">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-442">-30.00</span></span></td>
<td><span data-ttu-id="16ad9-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-444">Proj 1</span></span></td>
<td><span data-ttu-id="16ad9-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="16ad9-446">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-446">10001</span></span></td>
<td><span data-ttu-id="16ad9-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-447">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-448">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-449">30,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-449">30.00</span></span></td>
<td><span data-ttu-id="16ad9-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-451">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-451">CC001</span></span></td>
<td><span data-ttu-id="16ad9-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-452">HR</span></span></td>
<td><span data-ttu-id="16ad9-453">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-453">10001</span></span></td>
<td><span data-ttu-id="16ad9-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-454">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-455">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-456">-10.00</span></span></td>
<td><span data-ttu-id="16ad9-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-458">Proj 2</span></span></td>
<td><span data-ttu-id="16ad9-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="16ad9-460">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-460">10001</span></span></td>
<td><span data-ttu-id="16ad9-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-461">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-462">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-463">10.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-463">10.00</span></span></td>
<td><span data-ttu-id="16ad9-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="16ad9-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="16ad9-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="16ad9-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="16ad9-468">Finance supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="16ad9-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="16ad9-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="16ad9-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="16ad9-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="16ad9-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="16ad9-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="16ad9-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="16ad9-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="16ad9-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="16ad9-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="16ad9-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="16ad9-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="16ad9-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="16ad9-475">Define the cost allocation</span></span>

<span data-ttu-id="16ad9-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="16ad9-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="16ad9-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="16ad9-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-479">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="16ad9-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-481">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-481">CC002</span></span></td>
<td><span data-ttu-id="16ad9-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-482">Finance</span></span></td>
<td><span data-ttu-id="16ad9-483">35</span><span class="sxs-lookup"><span data-stu-id="16ad9-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-484">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-484">CC003</span></span></td>
<td><span data-ttu-id="16ad9-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-485">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-486">55</span><span class="sxs-lookup"><span data-stu-id="16ad9-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-487">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-487">CC004</span></span></td>
<td><span data-ttu-id="16ad9-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-488">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-489">10</span><span class="sxs-lookup"><span data-stu-id="16ad9-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="16ad9-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="16ad9-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-492">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-494">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-494">CC003</span></span></td>
<td><span data-ttu-id="16ad9-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-495">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-496">65</span><span class="sxs-lookup"><span data-stu-id="16ad9-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-497">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-497">CC004</span></span></td>
<td><span data-ttu-id="16ad9-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-498">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-499">35</span><span class="sxs-lookup"><span data-stu-id="16ad9-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="16ad9-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="16ad9-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-502">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="16ad9-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-504">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-505">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-506">60</span><span class="sxs-lookup"><span data-stu-id="16ad9-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-507">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-508">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-509">20</span><span class="sxs-lookup"><span data-stu-id="16ad9-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="16ad9-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="16ad9-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-512">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="16ad9-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-514">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-515">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-516">80</span><span class="sxs-lookup"><span data-stu-id="16ad9-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-517">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-518">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-519">15</span><span class="sxs-lookup"><span data-stu-id="16ad9-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="16ad9-520">Le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="16ad9-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="16ad9-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="16ad9-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="16ad9-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="16ad9-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-523">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-524">Magnitude</span></span></th>
<th><span data-ttu-id="16ad9-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-525">Allocation factor</span></span></th>
<th><span data-ttu-id="16ad9-526">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-526">Amount</span></span></th>
<th><span data-ttu-id="16ad9-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-528">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-528">CC002</span></span></td>
<td><span data-ttu-id="16ad9-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-529">Finance</span></span></td>
<td><span data-ttu-id="16ad9-530">35</span><span class="sxs-lookup"><span data-stu-id="16ad9-530">35</span></span></td>
<td><span data-ttu-id="16ad9-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="16ad9-532">175.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-532">175.00</span></span></td>
<td><span data-ttu-id="16ad9-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-534">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-534">CC003</span></span></td>
<td><span data-ttu-id="16ad9-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-535">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-536">55</span><span class="sxs-lookup"><span data-stu-id="16ad9-536">55</span></span></td>
<td><span data-ttu-id="16ad9-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="16ad9-538">275.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-538">275.00</span></span></td>
<td><span data-ttu-id="16ad9-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-540">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-540">CC004</span></span></td>
<td><span data-ttu-id="16ad9-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-541">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-542">10</span><span class="sxs-lookup"><span data-stu-id="16ad9-542">10</span></span></td>
<td><span data-ttu-id="16ad9-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="16ad9-544">50,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-544">50.00</span></span></td>
<td><span data-ttu-id="16ad9-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-546">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-546">CC002</span></span></td>
<td><span data-ttu-id="16ad9-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-547">Finance</span></span></td>
<td><span data-ttu-id="16ad9-548">35</span><span class="sxs-lookup"><span data-stu-id="16ad9-548">35</span></span></td>
<td><span data-ttu-id="16ad9-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="16ad9-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="16ad9-550">436.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-550">436.00</span></span></td>
<td><span data-ttu-id="16ad9-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-552">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-552">CC003</span></span></td>
<td><span data-ttu-id="16ad9-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-553">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-554">55</span><span class="sxs-lookup"><span data-stu-id="16ad9-554">55</span></span></td>
<td><span data-ttu-id="16ad9-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="16ad9-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="16ad9-556">685.14</span><span class="sxs-lookup"><span data-stu-id="16ad9-556">685.14</span></span></td>
<td><span data-ttu-id="16ad9-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-558">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-558">CC004</span></span></td>
<td><span data-ttu-id="16ad9-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-559">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-560">10</span><span class="sxs-lookup"><span data-stu-id="16ad9-560">10</span></span></td>
<td><span data-ttu-id="16ad9-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="16ad9-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="16ad9-562">124.57</span><span class="sxs-lookup"><span data-stu-id="16ad9-562">124.57</span></span></td>
<td><span data-ttu-id="16ad9-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="16ad9-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-565">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-566">Magnitude</span></span></th>
<th><span data-ttu-id="16ad9-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-567">Allocation factor</span></span></th>
<th><span data-ttu-id="16ad9-568">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-568">Amount</span></span></th>
<th><span data-ttu-id="16ad9-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-570">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-570">CC003</span></span></td>
<td><span data-ttu-id="16ad9-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-571">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-572">65</span><span class="sxs-lookup"><span data-stu-id="16ad9-572">65</span></span></td>
<td><span data-ttu-id="16ad9-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="16ad9-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="16ad9-574">438.75</span><span class="sxs-lookup"><span data-stu-id="16ad9-574">438.75</span></span></td>
<td><span data-ttu-id="16ad9-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-576">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-576">CC004</span></span></td>
<td><span data-ttu-id="16ad9-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-577">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-578">35</span><span class="sxs-lookup"><span data-stu-id="16ad9-578">35</span></span></td>
<td><span data-ttu-id="16ad9-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="16ad9-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="16ad9-580">236.25</span><span class="sxs-lookup"><span data-stu-id="16ad9-580">236.25</span></span></td>
<td><span data-ttu-id="16ad9-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-582">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-582">CC003</span></span></td>
<td><span data-ttu-id="16ad9-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-583">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-584">65</span><span class="sxs-lookup"><span data-stu-id="16ad9-584">65</span></span></td>
<td><span data-ttu-id="16ad9-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="16ad9-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="16ad9-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="16ad9-586">5,297.69</span></span></td>
<td><span data-ttu-id="16ad9-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-588">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-588">CC004</span></span></td>
<td><span data-ttu-id="16ad9-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-589">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-590">35</span><span class="sxs-lookup"><span data-stu-id="16ad9-590">35</span></span></td>
<td><span data-ttu-id="16ad9-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="16ad9-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="16ad9-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="16ad9-592">2,852.60</span></span></td>
<td><span data-ttu-id="16ad9-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="16ad9-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-595">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-596">Magnitude</span></span></th>
<th><span data-ttu-id="16ad9-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-597">Allocation factor</span></span></th>
<th><span data-ttu-id="16ad9-598">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-598">Amount</span></span></th>
<th><span data-ttu-id="16ad9-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-600">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-601">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-602">60</span><span class="sxs-lookup"><span data-stu-id="16ad9-602">60</span></span></td>
<td><span data-ttu-id="16ad9-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="16ad9-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="16ad9-604">535.31</span><span class="sxs-lookup"><span data-stu-id="16ad9-604">535.31</span></span></td>
<td><span data-ttu-id="16ad9-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-606">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-607">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-608">20</span><span class="sxs-lookup"><span data-stu-id="16ad9-608">20</span></span></td>
<td><span data-ttu-id="16ad9-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="16ad9-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="16ad9-610">178.44</span><span class="sxs-lookup"><span data-stu-id="16ad9-610">178.44</span></span></td>
<td><span data-ttu-id="16ad9-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-612">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-613">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-614">60</span><span class="sxs-lookup"><span data-stu-id="16ad9-614">60</span></span></td>
<td><span data-ttu-id="16ad9-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="16ad9-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="16ad9-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="16ad9-616">4,487.12</span></span></td>
<td><span data-ttu-id="16ad9-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-618">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-619">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-620">20</span><span class="sxs-lookup"><span data-stu-id="16ad9-620">20</span></span></td>
<td><span data-ttu-id="16ad9-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="16ad9-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="16ad9-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="16ad9-622">1,495.71</span></span></td>
<td><span data-ttu-id="16ad9-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16ad9-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="16ad9-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-625">Cost object</span></span></th>
<th><span data-ttu-id="16ad9-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="16ad9-626">Magnitude</span></span></th>
<th><span data-ttu-id="16ad9-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-627">Allocation factor</span></span></th>
<th><span data-ttu-id="16ad9-628">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-628">Amount</span></span></th>
<th><span data-ttu-id="16ad9-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-630">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-631">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-632">80</span><span class="sxs-lookup"><span data-stu-id="16ad9-632">80</span></span></td>
<td><span data-ttu-id="16ad9-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="16ad9-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="16ad9-634">241.05</span><span class="sxs-lookup"><span data-stu-id="16ad9-634">241.05</span></span></td>
<td><span data-ttu-id="16ad9-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-636">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-637">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-638">15</span><span class="sxs-lookup"><span data-stu-id="16ad9-638">15</span></span></td>
<td><span data-ttu-id="16ad9-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="16ad9-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="16ad9-640">45.20</span><span class="sxs-lookup"><span data-stu-id="16ad9-640">45.20</span></span></td>
<td><span data-ttu-id="16ad9-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-642">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-643">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-644">80</span><span class="sxs-lookup"><span data-stu-id="16ad9-644">80</span></span></td>
<td><span data-ttu-id="16ad9-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="16ad9-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="16ad9-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="16ad9-646">2,507.09</span></span></td>
<td><span data-ttu-id="16ad9-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-648">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-649">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-650">15</span><span class="sxs-lookup"><span data-stu-id="16ad9-650">15</span></span></td>
<td><span data-ttu-id="16ad9-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="16ad9-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="16ad9-652">470.08</span><span class="sxs-lookup"><span data-stu-id="16ad9-652">470.08</span></span></td>
<td><span data-ttu-id="16ad9-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="16ad9-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="16ad9-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-655">Journal</span></span></th>
<th><span data-ttu-id="16ad9-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="16ad9-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="16ad9-658">Versione</span><span class="sxs-lookup"><span data-stu-id="16ad9-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-659">00004</span><span class="sxs-lookup"><span data-stu-id="16ad9-659">00004</span></span></td>
<td><span data-ttu-id="16ad9-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="16ad9-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="16ad9-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="16ad9-661">Fiscal</span></span></td>
<td><span data-ttu-id="16ad9-662">2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-662">2017</span></span></td>
<td><span data-ttu-id="16ad9-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-663">Period 1</span></span></td>
<td><span data-ttu-id="16ad9-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="16ad9-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="16ad9-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-668">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-669">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-670">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-672">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-672">CC001</span></span></td>
<td><span data-ttu-id="16ad9-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-673">HR</span></span></td>
<td><span data-ttu-id="16ad9-674">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-674">10001</span></span></td>
<td><span data-ttu-id="16ad9-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-675">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-676">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-677">500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-679">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-679">CC001</span></span></td>
<td><span data-ttu-id="16ad9-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-680">HR</span></span></td>
<td><span data-ttu-id="16ad9-681">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-681">10001</span></span></td>
<td><span data-ttu-id="16ad9-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-682">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-683">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="16ad9-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-686">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-686">CC002</span></span></td>
<td><span data-ttu-id="16ad9-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-687">Finance</span></span></td>
<td><span data-ttu-id="16ad9-688">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-688">10001</span></span></td>
<td><span data-ttu-id="16ad9-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-689">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-690">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-691">675.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-693">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-693">CC002</span></span></td>
<td><span data-ttu-id="16ad9-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-694">Finance</span></span></td>
<td><span data-ttu-id="16ad9-695">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-695">10001</span></span></td>
<td><span data-ttu-id="16ad9-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-696">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-697">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="16ad9-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-700">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-700">CC003</span></span></td>
<td><span data-ttu-id="16ad9-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-701">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-702">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-702">10001</span></span></td>
<td><span data-ttu-id="16ad9-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-703">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-704">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-705">713.75</span><span class="sxs-lookup"><span data-stu-id="16ad9-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-707">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-707">CC003</span></span></td>
<td><span data-ttu-id="16ad9-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-708">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-709">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-709">10001</span></span></td>
<td><span data-ttu-id="16ad9-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-710">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-711">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="16ad9-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-714">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-714">CC003</span></span></td>
<td><span data-ttu-id="16ad9-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-715">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-716">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-716">10001</span></span></td>
<td><span data-ttu-id="16ad9-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-717">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-718">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-719">286.25</span><span class="sxs-lookup"><span data-stu-id="16ad9-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-721">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-721">CC003</span></span></td>
<td><span data-ttu-id="16ad9-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-722">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-723">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-723">10001</span></span></td>
<td><span data-ttu-id="16ad9-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-724">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-725">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="16ad9-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-728">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-729">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-730">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-730">10001</span></span></td>
<td><span data-ttu-id="16ad9-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-731">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-732">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-733">776.36</span><span class="sxs-lookup"><span data-stu-id="16ad9-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-735">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-736">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-737">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-737">10001</span></span></td>
<td><span data-ttu-id="16ad9-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-738">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-739">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="16ad9-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-742">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-743">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-744">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-744">10001</span></span></td>
<td><span data-ttu-id="16ad9-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-745">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-746">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-747">223.64</span><span class="sxs-lookup"><span data-stu-id="16ad9-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="16ad9-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-749">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-750">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-751">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-751">10001</span></span></td>
<td><span data-ttu-id="16ad9-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-752">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-753">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="16ad9-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="16ad9-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="16ad9-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="16ad9-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-757">Cost element</span></span></th>
<th><span data-ttu-id="16ad9-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-758">Cost behavior</span></span></th>
<th><span data-ttu-id="16ad9-759">Importo</span><span class="sxs-lookup"><span data-stu-id="16ad9-759">Amount</span></span></th>
<th><span data-ttu-id="16ad9-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="16ad9-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="16ad9-761">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-761">CC001</span></span></td>
<td><span data-ttu-id="16ad9-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-762">HR</span></span></td>
<td><span data-ttu-id="16ad9-763">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-763">10001</span></span></td>
<td><span data-ttu-id="16ad9-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-764">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-765">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-766">-500.00</span></span></td>
<td><span data-ttu-id="16ad9-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-768">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-768">CC002</span></span></td>
<td><span data-ttu-id="16ad9-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-769">Finance</span></span></td>
<td><span data-ttu-id="16ad9-770">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-770">10001</span></span></td>
<td><span data-ttu-id="16ad9-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-771">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-772">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-773">175.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-773">175.00</span></span></td>
<td><span data-ttu-id="16ad9-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-775">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-775">CC003</span></span></td>
<td><span data-ttu-id="16ad9-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-776">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-777">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-777">10001</span></span></td>
<td><span data-ttu-id="16ad9-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-778">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-779">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-780">275.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-780">275.00</span></span></td>
<td><span data-ttu-id="16ad9-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-782">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-782">CC004</span></span></td>
<td><span data-ttu-id="16ad9-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-783">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-784">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-784">10001</span></span></td>
<td><span data-ttu-id="16ad9-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-785">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-786">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-787">50,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-787">50,00</span></span></td>
<td><span data-ttu-id="16ad9-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-789">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-789">CC001</span></span></td>
<td><span data-ttu-id="16ad9-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="16ad9-790">HR</span></span></td>
<td><span data-ttu-id="16ad9-791">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-791">10001</span></span></td>
<td><span data-ttu-id="16ad9-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-792">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-793">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="16ad9-794">-1,245.71</span></span></td>
<td><span data-ttu-id="16ad9-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-796">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-796">CC002</span></span></td>
<td><span data-ttu-id="16ad9-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-797">Finance</span></span></td>
<td><span data-ttu-id="16ad9-798">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-798">10001</span></span></td>
<td><span data-ttu-id="16ad9-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-799">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-800">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-801">436.00</span><span class="sxs-lookup"><span data-stu-id="16ad9-801">436.00</span></span></td>
<td><span data-ttu-id="16ad9-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-803">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-803">CC003</span></span></td>
<td><span data-ttu-id="16ad9-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-804">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-805">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-805">10001</span></span></td>
<td><span data-ttu-id="16ad9-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-806">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-807">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-808">685.14</span><span class="sxs-lookup"><span data-stu-id="16ad9-808">685.14</span></span></td>
<td><span data-ttu-id="16ad9-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-810">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-810">CC004</span></span></td>
<td><span data-ttu-id="16ad9-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-811">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-812">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-812">10001</span></span></td>
<td><span data-ttu-id="16ad9-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-813">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-814">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-815">124.57</span><span class="sxs-lookup"><span data-stu-id="16ad9-815">124.57</span></span></td>
<td><span data-ttu-id="16ad9-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-817">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-817">CC002</span></span></td>
<td><span data-ttu-id="16ad9-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-818">Finance</span></span></td>
<td><span data-ttu-id="16ad9-819">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-819">10001</span></span></td>
<td><span data-ttu-id="16ad9-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-820">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-821">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-822">-675.00</span></span></td>
<td><span data-ttu-id="16ad9-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-824">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-824">CC003</span></span></td>
<td><span data-ttu-id="16ad9-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-825">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-826">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-826">10001</span></span></td>
<td><span data-ttu-id="16ad9-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-827">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-828">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-829">438.75</span><span class="sxs-lookup"><span data-stu-id="16ad9-829">438.75</span></span></td>
<td><span data-ttu-id="16ad9-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-831">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-831">CC004</span></span></td>
<td><span data-ttu-id="16ad9-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-832">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-833">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-833">10001</span></span></td>
<td><span data-ttu-id="16ad9-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-834">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-835">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-836">236.25</span><span class="sxs-lookup"><span data-stu-id="16ad9-836">236.25</span></span></td>
<td><span data-ttu-id="16ad9-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-838">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-838">CC002</span></span></td>
<td><span data-ttu-id="16ad9-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="16ad9-839">Finance</span></span></td>
<td><span data-ttu-id="16ad9-840">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-840">10001</span></span></td>
<td><span data-ttu-id="16ad9-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-841">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-842">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="16ad9-843">-8,150.29</span></span></td>
<td><span data-ttu-id="16ad9-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-845">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-845">CC003</span></span></td>
<td><span data-ttu-id="16ad9-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-846">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-847">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-847">10001</span></span></td>
<td><span data-ttu-id="16ad9-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-848">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-849">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="16ad9-850">5,297.69</span></span></td>
<td><span data-ttu-id="16ad9-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-852">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-852">CC004</span></span></td>
<td><span data-ttu-id="16ad9-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-853">Packaging</span></span></td>
<td><span data-ttu-id="16ad9-854">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-854">10001</span></span></td>
<td><span data-ttu-id="16ad9-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-855">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-856">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="16ad9-857">2,852.60</span></span></td>
<td><span data-ttu-id="16ad9-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-859">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-859">CC003</span></span></td>
<td><span data-ttu-id="16ad9-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-860">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-861">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-861">10001</span></span></td>
<td><span data-ttu-id="16ad9-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-862">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-863">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="16ad9-864">-713.75</span></span></td>
<td><span data-ttu-id="16ad9-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-866">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-867">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-868">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-868">10001</span></span></td>
<td><span data-ttu-id="16ad9-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-869">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-870">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-871">535.31</span><span class="sxs-lookup"><span data-stu-id="16ad9-871">535.31</span></span></td>
<td><span data-ttu-id="16ad9-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-873">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-874">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-875">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-875">10001</span></span></td>
<td><span data-ttu-id="16ad9-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-876">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-877">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-878">178.44</span><span class="sxs-lookup"><span data-stu-id="16ad9-878">178.44</span></span></td>
<td><span data-ttu-id="16ad9-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-880">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-880">CC003</span></span></td>
<td><span data-ttu-id="16ad9-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-881">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-882">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-882">10001</span></span></td>
<td><span data-ttu-id="16ad9-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-883">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-884">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="16ad9-885">-5,982.83</span></span></td>
<td><span data-ttu-id="16ad9-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-887">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-888">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-889">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-889">10001</span></span></td>
<td><span data-ttu-id="16ad9-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-890">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-891">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="16ad9-892">4,487.12</span></span></td>
<td><span data-ttu-id="16ad9-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-894">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-895">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-896">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-896">10001</span></span></td>
<td><span data-ttu-id="16ad9-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-897">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-898">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="16ad9-899">1,495.71</span></span></td>
<td><span data-ttu-id="16ad9-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-901">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-901">CC003</span></span></td>
<td><span data-ttu-id="16ad9-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-902">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-903">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-903">10001</span></span></td>
<td><span data-ttu-id="16ad9-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-904">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-905">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="16ad9-906">-286.25</span></span></td>
<td><span data-ttu-id="16ad9-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-908">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-909">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-910">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-910">10001</span></span></td>
<td><span data-ttu-id="16ad9-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-911">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-912">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-913">241.05</span><span class="sxs-lookup"><span data-stu-id="16ad9-913">241.05</span></span></td>
<td><span data-ttu-id="16ad9-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-915">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-916">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-917">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-917">10001</span></span></td>
<td><span data-ttu-id="16ad9-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-918">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-919">Fixed cost</span></span></td>
<td><span data-ttu-id="16ad9-920">45.20</span><span class="sxs-lookup"><span data-stu-id="16ad9-920">45.20</span></span></td>
<td><span data-ttu-id="16ad9-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-922">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-922">CC003</span></span></td>
<td><span data-ttu-id="16ad9-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="16ad9-923">Assembly</span></span></td>
<td><span data-ttu-id="16ad9-924">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-924">10001</span></span></td>
<td><span data-ttu-id="16ad9-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-925">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-926">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="16ad9-927">-2,977.17</span></span></td>
<td><span data-ttu-id="16ad9-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-929">Prod 1</span></span></td>
<td><span data-ttu-id="16ad9-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-930">Product 1</span></span></td>
<td><span data-ttu-id="16ad9-931">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-931">10001</span></span></td>
<td><span data-ttu-id="16ad9-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-932">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-933">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="16ad9-934">2,507.09</span></span></td>
<td><span data-ttu-id="16ad9-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="16ad9-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-936">Prod 2</span></span></td>
<td><span data-ttu-id="16ad9-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-937">Product 2</span></span></td>
<td><span data-ttu-id="16ad9-938">10001</span><span class="sxs-lookup"><span data-stu-id="16ad9-938">10001</span></span></td>
<td><span data-ttu-id="16ad9-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-939">Electricity</span></span></td>
<td><span data-ttu-id="16ad9-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-940">Variable cost</span></span></td>
<td><span data-ttu-id="16ad9-941">470.08</span><span class="sxs-lookup"><span data-stu-id="16ad9-941">470.08</span></span></td>
<td><span data-ttu-id="16ad9-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="16ad9-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="16ad9-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="16ad9-943">Conclusion</span></span>
<span data-ttu-id="16ad9-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="16ad9-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="16ad9-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="16ad9-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="16ad9-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="16ad9-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="16ad9-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="16ad9-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="16ad9-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="16ad9-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="16ad9-950">Totale</span><span class="sxs-lookup"><span data-stu-id="16ad9-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="16ad9-951">CC099</span><span class="sxs-lookup"><span data-stu-id="16ad9-951">CC099</span></span></th>
<th><span data-ttu-id="16ad9-952">CC001</span><span class="sxs-lookup"><span data-stu-id="16ad9-952">CC001</span></span></th>
<th><span data-ttu-id="16ad9-953">CC002</span><span class="sxs-lookup"><span data-stu-id="16ad9-953">CC002</span></span></th>
<th><span data-ttu-id="16ad9-954">CC003</span><span class="sxs-lookup"><span data-stu-id="16ad9-954">CC003</span></span></th>
<th><span data-ttu-id="16ad9-955">CC004</span><span class="sxs-lookup"><span data-stu-id="16ad9-955">CC004</span></span></th>
<th><span data-ttu-id="16ad9-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-956">Proj 1</span></span></th>
<th><span data-ttu-id="16ad9-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-957">Proj 2</span></span></th>
<th><span data-ttu-id="16ad9-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="16ad9-958">Prod 1</span></span></th>
<th><span data-ttu-id="16ad9-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="16ad9-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="16ad9-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="16ad9-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="16ad9-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="16ad9-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-971">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="16ad9-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="16ad9-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-973">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-974">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-975">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-976">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-977">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-978">776.36</span><span class="sxs-lookup"><span data-stu-id="16ad9-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-979">223.64</span><span class="sxs-lookup"><span data-stu-id="16ad9-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="16ad9-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="16ad9-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-982">000</span><span class="sxs-lookup"><span data-stu-id="16ad9-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-983">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-984">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-985">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-986">0,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-987">30,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-988">10,00</span><span class="sxs-lookup"><span data-stu-id="16ad9-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="16ad9-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="16ad9-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="16ad9-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="16ad9-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="16ad9-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="16ad9-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="16ad9-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="16ad9-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="16ad9-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="16ad9-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="16ad9-996">Per ulteriori informazioni, vedere [Criteri rollup costi e calcolo dei costi generali](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="16ad9-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



