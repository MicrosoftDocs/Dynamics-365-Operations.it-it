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
ms.openlocfilehash: 6c045f82f3288dba193721dd80c90e68750af9a7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178484"
---
# <a name="overhead-calculation"></a><span data-ttu-id="a014d-103">Calcolo generale</span><span class="sxs-lookup"><span data-stu-id="a014d-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a014d-104">In questo argomento vengono descritti i processi tipici per il calcolo e l'assegnazione dei costi generali.</span><span class="sxs-lookup"><span data-stu-id="a014d-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="a014d-105">Definizione del termine</span><span class="sxs-lookup"><span data-stu-id="a014d-105">Term definition</span></span>
---------------

<span data-ttu-id="a014d-106">I costi generali sono i costi sostenuti per la normale gestione di una società, ma che non possono essere direttamente attribuiti a nessuna attività aziendale, prodotto o servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="a014d-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="a014d-107">I costi generali forniscono supporto cruciale per la generazione di attività che producono profitto.</span><span class="sxs-lookup"><span data-stu-id="a014d-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="a014d-108">Di seguito sono riportati alcuni esempi di costi generali:</span><span class="sxs-lookup"><span data-stu-id="a014d-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="a014d-109">Affitto</span><span class="sxs-lookup"><span data-stu-id="a014d-109">Rent</span></span>
-   <span data-ttu-id="a014d-110">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-110">Electricity</span></span>
-   <span data-ttu-id="a014d-111">Stipendi amministrativi</span><span class="sxs-lookup"><span data-stu-id="a014d-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="a014d-112">Panoramica del calcolo dei costi generali</span><span class="sxs-lookup"><span data-stu-id="a014d-112">Overhead calculation overview</span></span>
<span data-ttu-id="a014d-113">Il calcolo dei costi generali si basa sui criteri di contabilità industriale eseguiti nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="a014d-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="a014d-114">È possibile eseguire più volte il calcolo dei costi generali per lo stesso periodo fiscale se i criteri di contabilità industriale sono stati modificati o se sono stati rilevati errori specifici.</span><span class="sxs-lookup"><span data-stu-id="a014d-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="a014d-115">Ogni esecuzione del calcolo dei costi generali viene memorizzata e riceve un ID univoco di versione che consente di confrontare i calcoli di diverse versioni.</span><span class="sxs-lookup"><span data-stu-id="a014d-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="a014d-116">Le voci di costo generate dal calcolo dei costi generali ricevono una data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a014d-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="a014d-117">Questa data di registrazione corrisponde alla data di fine del periodo fiscale utilizzato nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="a014d-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="a014d-118">L'ID univoco della versione è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="a014d-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="a014d-119">Tipo di versione</span><span class="sxs-lookup"><span data-stu-id="a014d-119">Version type</span></span>
-   <span data-ttu-id="a014d-120">Data e ora</span><span class="sxs-lookup"><span data-stu-id="a014d-120">Date and time</span></span>
-   <span data-ttu-id="a014d-121">Movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="a014d-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="a014d-122">Anno fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-122">Fiscal year</span></span>
-   <span data-ttu-id="a014d-123">Periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-123">Fiscal period</span></span>

<span data-ttu-id="a014d-124">Il calcolo dei costi generali viene eseguito indipendentemente dalla versione.</span><span class="sxs-lookup"><span data-stu-id="a014d-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="a014d-125">Di conseguenza, è possibile calcolare la versione Budget prima della versione Effettivo.</span><span class="sxs-lookup"><span data-stu-id="a014d-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="a014d-126">Il calcolo dei costi generali è costituito da quattro passaggi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="a014d-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="a014d-127">A ogni passaggio, un'intestazione del giornale di registrazione viene creata con voci del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a014d-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="a014d-128">In questa intestazione del giornale di registrazione sono archiviati i dati di input per ogni passaggio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="a014d-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="a014d-129">I criteri e le regole vengono applicati a ogni riga del giornale di registrazione e le voci di costo vengono generate come output.</span><span class="sxs-lookup"><span data-stu-id="a014d-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="a014d-130">Di conseguenza, la tracciabilità è sempre completa.</span><span class="sxs-lookup"><span data-stu-id="a014d-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="a014d-131">[![Calcolo dei costi generali](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="a014d-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="a014d-132">Calcolare e allocare il costo generale dell'elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="a014d-133">Nella contabilità finanziaria, alcuni costi, ad esempio l'elettricità, vengono registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="a014d-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="a014d-134">Di conseguenza, l'analisi manageriale dettagliata non viene fornita per la contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="a014d-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="a014d-135">In contabilità industriale, per fornire l'analisi manageriale dettagliata corretta in tutte le unità organizzative e livelli, i costi devono essere trasferiti attraverso le unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="a014d-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="a014d-136">Questo flusso deve basarsi su un record accurato del consumo o su una valutazione equa.</span><span class="sxs-lookup"><span data-stu-id="a014d-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="a014d-137">Nella contabilità generale, il costo di elettricità può essere registrato come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="a014d-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-138">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-139">Centro di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-140">Conto principale</span><span class="sxs-lookup"><span data-stu-id="a014d-140">Main account</span></span></th>
<th><span data-ttu-id="a014d-141">Importo nella valuta di contabilizzazione</span><span class="sxs-lookup"><span data-stu-id="a014d-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-142">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="a014d-143">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-143">CC099</span></span></td>
<td><span data-ttu-id="a014d-144">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-144">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-145">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-145">10001</span></span></td>
<td><span data-ttu-id="a014d-146">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-146">Electricity</span></span></td>
<td><span data-ttu-id="a014d-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="a014d-148">Passaggio 1: Elaborare il calcolo comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="a014d-149">Per impostazione predefinita, quando le voci dei costi vengono importate dai dati di origine, viene assegnata la classificazione comportamento costo **Non classificato** nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="a014d-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="a014d-150">Applicando le regole dei criteri comportamento costo, è possibile riclassificare le voci dei costi come **Costo fisso** o **Costo variabile**.</span><span class="sxs-lookup"><span data-stu-id="a014d-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="a014d-151">Definire la regola di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-151">Define the cost behavior rule</span></span>

<span data-ttu-id="a014d-152">In alcuni casi, parte del costo è una commissione fissa e il costo rimanente è basato su consumo.</span><span class="sxs-lookup"><span data-stu-id="a014d-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="a014d-153">Le bollette elettricità spesso corrispondono a questa definizione.</span><span class="sxs-lookup"><span data-stu-id="a014d-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="a014d-154">Una volta pagata una commissione fissa specifica, si paga quindi il consumo kilowattora (KWH).</span><span class="sxs-lookup"><span data-stu-id="a014d-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="a014d-155">Ad esempio, se la commissione di costo fisso è 1.000,00, questo è il modo in cui la regola di comportamento costo viene definita:</span><span class="sxs-lookup"><span data-stu-id="a014d-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="a014d-156">Importo fisso 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="a014d-157">0 &lt;= 1.000,00 = Fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="a014d-158">1.000,01 &lt; N = Variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="a014d-159">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-160">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-160">Journal</span></span></th>
<th><span data-ttu-id="a014d-161">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a014d-162">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a014d-163">Versione</span><span class="sxs-lookup"><span data-stu-id="a014d-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-164">00001</span><span class="sxs-lookup"><span data-stu-id="a014d-164">00001</span></span></td>
<td><span data-ttu-id="a014d-165">Giornale di registrazione calcoli comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="a014d-166">Fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-166">Fiscal</span></span></td>
<td><span data-ttu-id="a014d-167">2017</span><span class="sxs-lookup"><span data-stu-id="a014d-167">2017</span></span></td>
<td><span data-ttu-id="a014d-168">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-168">Period 1</span></span></td>
<td><span data-ttu-id="a014d-169">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a014d-170">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="a014d-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-171">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-172">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-173">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-173">Cost element</span></span></th>
<th><span data-ttu-id="a014d-174">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-174">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-175">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-176">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="a014d-177">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-177">CC099</span></span></td>
<td><span data-ttu-id="a014d-178">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-178">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-179">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-179">10001</span></span></td>
<td><span data-ttu-id="a014d-180">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-180">Electricity</span></span></td>
<td><span data-ttu-id="a014d-181">Non classificato</span><span class="sxs-lookup"><span data-stu-id="a014d-181">Unclassified</span></span></td>
<td><span data-ttu-id="a014d-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a014d-183">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-184">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-185">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-185">Cost element</span></span></th>
<th><span data-ttu-id="a014d-186">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-186">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-187">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-187">Amount</span></span></th>
<th><span data-ttu-id="a014d-188">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-189">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-189">CC099</span></span></td>
<td><span data-ttu-id="a014d-190">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-190">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-191">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-191">10001</span></span></td>
<td><span data-ttu-id="a014d-192">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-192">Electricity</span></span></td>
<td><span data-ttu-id="a014d-193">Non classificato</span><span class="sxs-lookup"><span data-stu-id="a014d-193">Unclassified</span></span></td>
<td><span data-ttu-id="a014d-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-194">10,000.00</span></span></td>
<td><span data-ttu-id="a014d-195">3 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-196">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-196">CC099</span></span></td>
<td><span data-ttu-id="a014d-197">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-197">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-198">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-198">10001</span></span></td>
<td><span data-ttu-id="a014d-199">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-199">Electricity</span></span></td>
<td><span data-ttu-id="a014d-200">Non classificato</span><span class="sxs-lookup"><span data-stu-id="a014d-200">Unclassified</span></span></td>
<td><span data-ttu-id="a014d-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-201">-10,000.00</span></span></td>
<td><span data-ttu-id="a014d-202">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-203">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-203">CC099</span></span></td>
<td><span data-ttu-id="a014d-204">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-204">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-205">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-205">10001</span></span></td>
<td><span data-ttu-id="a014d-206">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-206">Electricity</span></span></td>
<td><span data-ttu-id="a014d-207">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-207">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-208">1,000.00</span></span></td>
<td><span data-ttu-id="a014d-209">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-210">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-210">CC099</span></span></td>
<td><span data-ttu-id="a014d-211">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-211">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-212">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-212">10001</span></span></td>
<td><span data-ttu-id="a014d-213">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-213">Electricity</span></span></td>
<td><span data-ttu-id="a014d-214">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-214">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-215">9,000.00</span></span></td>
<td><span data-ttu-id="a014d-216">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-217">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a014d-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="a014d-218">Passaggio 2: Elaborare il calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="a014d-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="a014d-219">La distribuzione costo viene utilizzata per ridistribuire i costi da un oggetto costo a uno o più oggetti costo applicando una base di allocazione rilevante.</span><span class="sxs-lookup"><span data-stu-id="a014d-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="a014d-220">La distribuzione costo e l'allocazione costo differiscono per il fatto che la distribuzione costo si verifica sempre a livello dell'elemento di costo primario del costo originale.</span><span class="sxs-lookup"><span data-stu-id="a014d-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="a014d-221">Definire la regola di distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="a014d-221">Define the cost distribution rule</span></span>

<span data-ttu-id="a014d-222">Nella contabilità finanziaria, i costi dell'elettricità, vengono spesso registrati come somma forfettaria.</span><span class="sxs-lookup"><span data-stu-id="a014d-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="a014d-223">Nella contabilità industriale, questo approccio non è sufficientemente dettagliato.</span><span class="sxs-lookup"><span data-stu-id="a014d-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="a014d-224">Il costo di variabile deve essere distribuito ai singoli oggetti costo su base equa.</span><span class="sxs-lookup"><span data-stu-id="a014d-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="a014d-225">La base di allocazione più logica è il consumo di elettricità (KWH).</span><span class="sxs-lookup"><span data-stu-id="a014d-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="a014d-226">Verrà creato un membro di dimensione statistica denominato Elettricità e verrà registrato il consumo di elettricità.</span><span class="sxs-lookup"><span data-stu-id="a014d-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="a014d-227">Per impostazione predefinita, tutti i membri di dimensione statistica sono disponibili come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="a014d-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-228">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-228">Cost object</span></span></th>
<th><span data-ttu-id="a014d-229">KWH</span><span class="sxs-lookup"><span data-stu-id="a014d-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-230">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-230">CC001</span></span></td>
<td><span data-ttu-id="a014d-231">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-231">HR</span></span></td>
<td><span data-ttu-id="a014d-232">1.000</span><span class="sxs-lookup"><span data-stu-id="a014d-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-233">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-233">CC002</span></span></td>
<td><span data-ttu-id="a014d-234">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-234">Finance</span></span></td>
<td><span data-ttu-id="a014d-235">6.000</span><span class="sxs-lookup"><span data-stu-id="a014d-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-236">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-236">CC003</span></span></td>
<td><span data-ttu-id="a014d-237">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-237">Assembly</span></span></td>
<td><span data-ttu-id="a014d-238">0</span><span class="sxs-lookup"><span data-stu-id="a014d-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-239">Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="a014d-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-240">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-240">Cost object</span></span></th>
<th><span data-ttu-id="a014d-241">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-241">Magnitude</span></span></th>
<th><span data-ttu-id="a014d-242">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="a014d-242">Allocation factor</span></span></th>
<th><span data-ttu-id="a014d-243">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-244">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-244">CC001</span></span></td>
<td><span data-ttu-id="a014d-245">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-245">HR</span></span></td>
<td><span data-ttu-id="a014d-246">1.000</span><span class="sxs-lookup"><span data-stu-id="a014d-246">1,000</span></span></td>
<td><span data-ttu-id="a014d-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a014d-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a014d-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-249">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-249">CC002</span></span></td>
<td><span data-ttu-id="a014d-250">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-250">Finance</span></span></td>
<td><span data-ttu-id="a014d-251">6.000</span><span class="sxs-lookup"><span data-stu-id="a014d-251">6,000</span></span></td>
<td><span data-ttu-id="a014d-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a014d-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a014d-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-254">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-254">CC003</span></span></td>
<td><span data-ttu-id="a014d-255">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-255">Assembly</span></span></td>
<td><span data-ttu-id="a014d-256">0</span><span class="sxs-lookup"><span data-stu-id="a014d-256">0</span></span></td>
<td><span data-ttu-id="a014d-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a014d-258">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-259">Il costo fisso deve essere distribuito equamente ai singoli oggetti costo che hanno consumato elettricità.</span><span class="sxs-lookup"><span data-stu-id="a014d-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="a014d-260">È possibile ottenere questo risultato utilizzando il membro dimensione statistica in una base di allocazione della formula: (Elettricità &gt; 0,00) Nella tabella seguente viene illustrato il risultato ottenuto quando il consumo di elettricità viene applicato come base di allocazione per i costi variabili.</span><span class="sxs-lookup"><span data-stu-id="a014d-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-261">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-261">Cost object</span></span></th>
<th><span data-ttu-id="a014d-262">Formula</span><span class="sxs-lookup"><span data-stu-id="a014d-262">Formula</span></span></th>
<th><span data-ttu-id="a014d-263">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-263">Magnitude</span></span></th>
<th><span data-ttu-id="a014d-264">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="a014d-264">Allocation factor</span></span></th>
<th><span data-ttu-id="a014d-265">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-266">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-266">CC001</span></span></td>
<td><span data-ttu-id="a014d-267">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-267">HR</span></span></td>
<td><span data-ttu-id="a014d-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a014d-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a014d-269">1</span><span class="sxs-lookup"><span data-stu-id="a014d-269">1</span></span></td>
<td><span data-ttu-id="a014d-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a014d-271">500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-272">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-272">CC002</span></span></td>
<td><span data-ttu-id="a014d-273">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-273">Finance</span></span></td>
<td><span data-ttu-id="a014d-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a014d-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a014d-275">1</span><span class="sxs-lookup"><span data-stu-id="a014d-275">1</span></span></td>
<td><span data-ttu-id="a014d-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a014d-277">500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-278">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-278">CC003</span></span></td>
<td><span data-ttu-id="a014d-279">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-279">Assembly</span></span></td>
<td><span data-ttu-id="a014d-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a014d-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a014d-281">0</span><span class="sxs-lookup"><span data-stu-id="a014d-281">0</span></span></td>
<td><span data-ttu-id="a014d-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a014d-283">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a014d-284">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-285">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-285">Journal</span></span></th>
<th><span data-ttu-id="a014d-286">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a014d-287">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a014d-288">Versione</span><span class="sxs-lookup"><span data-stu-id="a014d-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-289">00002</span><span class="sxs-lookup"><span data-stu-id="a014d-289">00002</span></span></td>
<td><span data-ttu-id="a014d-290">Giornale di registrazione calcolo distribuzione costo</span><span class="sxs-lookup"><span data-stu-id="a014d-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="a014d-291">Fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-291">Fiscal</span></span></td>
<td><span data-ttu-id="a014d-292">2017</span><span class="sxs-lookup"><span data-stu-id="a014d-292">2017</span></span></td>
<td><span data-ttu-id="a014d-293">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-293">Period 1</span></span></td>
<td><span data-ttu-id="a014d-294">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a014d-295">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="a014d-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-296">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-297">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-298">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-298">Cost element</span></span></th>
<th><span data-ttu-id="a014d-299">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-299">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-300">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-301">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-302">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-302">CC099</span></span></td>
<td><span data-ttu-id="a014d-303">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-303">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-304">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-304">10001</span></span></td>
<td><span data-ttu-id="a014d-305">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-305">Electricity</span></span></td>
<td><span data-ttu-id="a014d-306">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-306">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-308">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-309">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-309">CC099</span></span></td>
<td><span data-ttu-id="a014d-310">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-310">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-311">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-311">10001</span></span></td>
<td><span data-ttu-id="a014d-312">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-312">Electricity</span></span></td>
<td><span data-ttu-id="a014d-313">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-313">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a014d-315">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-316">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-317">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-317">Cost element</span></span></th>
<th><span data-ttu-id="a014d-318">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-318">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-319">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-319">Amount</span></span></th>
<th><span data-ttu-id="a014d-320">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-321">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-321">CC099</span></span></td>
<td><span data-ttu-id="a014d-322">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-322">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-323">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-323">10001</span></span></td>
<td><span data-ttu-id="a014d-324">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-324">Electricity</span></span></td>
<td><span data-ttu-id="a014d-325">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-325">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-326">-1,000.00</span></span></td>
<td><span data-ttu-id="a014d-327">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-328">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-328">CC001</span></span></td>
<td><span data-ttu-id="a014d-329">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-329">HR</span></span></td>
<td><span data-ttu-id="a014d-330">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-330">10001</span></span></td>
<td><span data-ttu-id="a014d-331">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-331">Electricity</span></span></td>
<td><span data-ttu-id="a014d-332">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-332">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-333">500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-333">500.00</span></span></td>
<td><span data-ttu-id="a014d-334">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-335">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-335">CC002</span></span></td>
<td><span data-ttu-id="a014d-336">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-336">Finance</span></span></td>
<td><span data-ttu-id="a014d-337">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-337">10001</span></span></td>
<td><span data-ttu-id="a014d-338">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-338">Electricity</span></span></td>
<td><span data-ttu-id="a014d-339">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-339">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-340">500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-340">500.00</span></span></td>
<td><span data-ttu-id="a014d-341">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-342">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-342">CC099</span></span></td>
<td><span data-ttu-id="a014d-343">Centro di costo predefinito</span><span class="sxs-lookup"><span data-stu-id="a014d-343">Default cost center</span></span></td>
<td><span data-ttu-id="a014d-344">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-344">10001</span></span></td>
<td><span data-ttu-id="a014d-345">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-345">Electricity</span></span></td>
<td><span data-ttu-id="a014d-346">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-346">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="a014d-347">-9,000.00</span></span></td>
<td><span data-ttu-id="a014d-348">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-349">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-349">CC001</span></span></td>
<td><span data-ttu-id="a014d-350">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-350">HR</span></span></td>
<td><span data-ttu-id="a014d-351">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-351">10001</span></span></td>
<td><span data-ttu-id="a014d-352">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-352">Electricity</span></span></td>
<td><span data-ttu-id="a014d-353">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-353">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a014d-354">1,285.71</span></span></td>
<td><span data-ttu-id="a014d-355">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-356">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-356">CC002</span></span></td>
<td><span data-ttu-id="a014d-357">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-357">Finance</span></span></td>
<td><span data-ttu-id="a014d-358">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-358">10001</span></span></td>
<td><span data-ttu-id="a014d-359">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-359">Electricity</span></span></td>
<td><span data-ttu-id="a014d-360">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-360">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a014d-361">7,714.29</span></span></td>
<td><span data-ttu-id="a014d-362">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-363">Per ulteriori informazioni, vedere [Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a014d-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="a014d-364">Passaggio 3: Elaborare il calcolo tassi generali</span><span class="sxs-lookup"><span data-stu-id="a014d-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="a014d-365">Il tasso generali viene utilizzato per effettuare un addebito a uno o più oggetti costo specifici.</span><span class="sxs-lookup"><span data-stu-id="a014d-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="a014d-366">L'addebito è basato su un tasso costo predeterminato e la grandezza della base di allocazione assegnata.</span><span class="sxs-lookup"><span data-stu-id="a014d-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="a014d-367">Definire il tasso generali</span><span class="sxs-lookup"><span data-stu-id="a014d-367">Define the overhead rate</span></span>

<span data-ttu-id="a014d-368">L'oggetto costo CC001 HR contribuisce a un gruppo di progetti interni.</span><span class="sxs-lookup"><span data-stu-id="a014d-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="a014d-369">Viene creato un membro di dimensione statistica denominato Progetti HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="a014d-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-370">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-370">Cost object</span></span></th>
<th><span data-ttu-id="a014d-371">Ore</span><span class="sxs-lookup"><span data-stu-id="a014d-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a014d-372">Proj 1</span></span></td>
<td><span data-ttu-id="a014d-373">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-373">Project 1</span></span></td>
<td><span data-ttu-id="a014d-374">3</span><span class="sxs-lookup"><span data-stu-id="a014d-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a014d-375">Proj 2</span></span></td>
<td><span data-ttu-id="a014d-376">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-376">Project 2</span></span></td>
<td><span data-ttu-id="a014d-377">1</span><span class="sxs-lookup"><span data-stu-id="a014d-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-378">È stato definito un tasso costo predeterminato per il supporto di progetti di costi.</span><span class="sxs-lookup"><span data-stu-id="a014d-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-379">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-379">Cost object</span></span></th>
<th><span data-ttu-id="a014d-380">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-380">Cost element</span></span></th>
<th><span data-ttu-id="a014d-381">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-381">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-382">Unità</span><span class="sxs-lookup"><span data-stu-id="a014d-382">Units</span></span></th>
<th><span data-ttu-id="a014d-383">Tasso</span><span class="sxs-lookup"><span data-stu-id="a014d-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-384">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-384">CC001</span></span></td>
<td><span data-ttu-id="a014d-385">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-385">HR</span></span></td>
<td><span data-ttu-id="a014d-386">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-386">10001</span></span></td>
<td><span data-ttu-id="a014d-387">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-387">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-388">1</span><span class="sxs-lookup"><span data-stu-id="a014d-388">1</span></span></td>
<td><span data-ttu-id="a014d-389">10</span><span class="sxs-lookup"><span data-stu-id="a014d-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-390">Nella tabella seguente viene illustrato il risultato ottenuto quando i progetti HR vengono applicati come base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="a014d-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-391">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-391">Cost object</span></span></th>
<th><span data-ttu-id="a014d-392">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-392">Magnitude</span></span></th>
<th><span data-ttu-id="a014d-393">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-393">Cost element</span></span></th>
<th><span data-ttu-id="a014d-394">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="a014d-394">Allocation factor</span></span></th>
<th><span data-ttu-id="a014d-395">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a014d-396">Proj 1</span></span></td>
<td><span data-ttu-id="a014d-397">Progetto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-397">Project 1</span></span></td>
<td><span data-ttu-id="a014d-398">3</span><span class="sxs-lookup"><span data-stu-id="a014d-398">3</span></span></td>
<td><span data-ttu-id="a014d-399">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-399">10001</span></span></td>
<td><span data-ttu-id="a014d-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a014d-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a014d-401">30,00</span><span class="sxs-lookup"><span data-stu-id="a014d-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a014d-402">Proj 2</span></span></td>
<td><span data-ttu-id="a014d-403">Progetto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-403">Project 2</span></span></td>
<td><span data-ttu-id="a014d-404">1</span><span class="sxs-lookup"><span data-stu-id="a014d-404">1</span></span></td>
<td><span data-ttu-id="a014d-405">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-405">10001</span></span></td>
<td><span data-ttu-id="a014d-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a014d-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a014d-407">10,00</span><span class="sxs-lookup"><span data-stu-id="a014d-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a014d-408">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-409">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-409">Journal</span></span></th>
<th><span data-ttu-id="a014d-410">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a014d-411">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a014d-412">Versione</span><span class="sxs-lookup"><span data-stu-id="a014d-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-413">00003</span><span class="sxs-lookup"><span data-stu-id="a014d-413">00003</span></span></td>
<td><span data-ttu-id="a014d-414">Giornale di registrazione calcoli tassi generali</span><span class="sxs-lookup"><span data-stu-id="a014d-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="a014d-415">Fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-415">Fiscal</span></span></td>
<td><span data-ttu-id="a014d-416">2017</span><span class="sxs-lookup"><span data-stu-id="a014d-416">2017</span></span></td>
<td><span data-ttu-id="a014d-417">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-417">Period 1</span></span></td>
<td><span data-ttu-id="a014d-418">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="a014d-419">Scritture contabili (Scritture contabili per calcolo tassi generali)</span><span class="sxs-lookup"><span data-stu-id="a014d-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-420">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-421">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-421">Cost object</span></span></th>
<th><span data-ttu-id="a014d-422">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-423">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a014d-424">Proj 1</span></span></td>
<td><span data-ttu-id="a014d-425">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="a014d-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a014d-426">3,00</span><span class="sxs-lookup"><span data-stu-id="a014d-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-427">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a014d-428">Proj 2</span></span></td>
<td><span data-ttu-id="a014d-429">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="a014d-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a014d-430">1,00</span><span class="sxs-lookup"><span data-stu-id="a014d-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a014d-431">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-432">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-433">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-433">Cost element</span></span></th>
<th><span data-ttu-id="a014d-434">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-434">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-435">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-435">Amount</span></span></th>
<th><span data-ttu-id="a014d-436">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="a014d-437">CC0001</span></span></td>
<td><span data-ttu-id="a014d-438">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-438">HR</span></span></td>
<td><span data-ttu-id="a014d-439">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-439">10001</span></span></td>
<td><span data-ttu-id="a014d-440">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-440">Electricity</span></span></td>
<td><span data-ttu-id="a014d-441">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-441">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="a014d-442">-30.00</span></span></td>
<td><span data-ttu-id="a014d-443">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a014d-444">Proj 1</span></span></td>
<td><span data-ttu-id="a014d-445">Progetto interno 1</span><span class="sxs-lookup"><span data-stu-id="a014d-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a014d-446">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-446">10001</span></span></td>
<td><span data-ttu-id="a014d-447">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-447">Electricity</span></span></td>
<td><span data-ttu-id="a014d-448">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-448">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-449">30,00</span><span class="sxs-lookup"><span data-stu-id="a014d-449">30.00</span></span></td>
<td><span data-ttu-id="a014d-450">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-451">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-451">CC001</span></span></td>
<td><span data-ttu-id="a014d-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-452">HR</span></span></td>
<td><span data-ttu-id="a014d-453">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-453">10001</span></span></td>
<td><span data-ttu-id="a014d-454">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-454">Electricity</span></span></td>
<td><span data-ttu-id="a014d-455">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-455">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="a014d-456">-10.00</span></span></td>
<td><span data-ttu-id="a014d-457">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a014d-458">Proj 2</span></span></td>
<td><span data-ttu-id="a014d-459">Progetto interno 2</span><span class="sxs-lookup"><span data-stu-id="a014d-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a014d-460">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-460">10001</span></span></td>
<td><span data-ttu-id="a014d-461">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-461">Electricity</span></span></td>
<td><span data-ttu-id="a014d-462">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-462">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-463">10.00</span><span class="sxs-lookup"><span data-stu-id="a014d-463">10.00</span></span></td>
<td><span data-ttu-id="a014d-464">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-465">Per ulteriori informazioni, vedere [Eseguire il calcolo generale](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="a014d-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="a014d-466">Passaggio 4: Elaborare il calcolo allocazione costo</span><span class="sxs-lookup"><span data-stu-id="a014d-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="a014d-467">L'allocazione è utilizzata per assegnare il saldo di un oggetto costo ad altri oggetti costo applicando una base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="a014d-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="a014d-468">Finance supporta il metodo di allocazione reciproco.</span><span class="sxs-lookup"><span data-stu-id="a014d-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="a014d-469">Nel metodo di allocazione reciproco, i servizi reciproci che gli oggetti costo ausiliario si scambiano sono completamente riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="a014d-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="a014d-470">Il sistema determina automaticamente l'ordine corretto per eseguire le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="a014d-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="a014d-471">Il saldo di un oggetto costo viene assegnato da una singola base di allocazione.</span><span class="sxs-lookup"><span data-stu-id="a014d-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="a014d-472">Le allocazioni in più dimensioni di oggetti costo e i rispettivi membri sono supportate.</span><span class="sxs-lookup"><span data-stu-id="a014d-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="a014d-473">L'ordine di allocazione è controllato dall'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="a014d-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="a014d-474">[![Metodo reciproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="a014d-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="a014d-475">Definizione dell'allocazione costi</span><span class="sxs-lookup"><span data-stu-id="a014d-475">Define the cost allocation</span></span>

<span data-ttu-id="a014d-476">Di seguito è riportato un esempio semplice che illustra come tenere traccia del flusso di costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="a014d-477">L'oggetto di costo CC001 HR contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="a014d-478">Viene creato un membro di dimensione statistica denominato Servizi HR per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="a014d-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-479">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-479">Cost object</span></span></th>
<th><span data-ttu-id="a014d-480">Servizi HR</span><span class="sxs-lookup"><span data-stu-id="a014d-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-481">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-481">CC002</span></span></td>
<td><span data-ttu-id="a014d-482">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-482">Finance</span></span></td>
<td><span data-ttu-id="a014d-483">35</span><span class="sxs-lookup"><span data-stu-id="a014d-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-484">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-484">CC003</span></span></td>
<td><span data-ttu-id="a014d-485">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-485">Assembly</span></span></td>
<td><span data-ttu-id="a014d-486">55</span><span class="sxs-lookup"><span data-stu-id="a014d-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-487">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-487">CC004</span></span></td>
<td><span data-ttu-id="a014d-488">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-488">Packaging</span></span></td>
<td><span data-ttu-id="a014d-489">10</span><span class="sxs-lookup"><span data-stu-id="a014d-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-490">L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="a014d-491">Viene creato un membro di dimensione statistica denominato Servizi finanziari per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="a014d-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-492">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-492">Cost object</span></span></th>
<th><span data-ttu-id="a014d-493">Servizi finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-494">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-494">CC003</span></span></td>
<td><span data-ttu-id="a014d-495">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-495">Assembly</span></span></td>
<td><span data-ttu-id="a014d-496">65</span><span class="sxs-lookup"><span data-stu-id="a014d-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-497">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-497">CC004</span></span></td>
<td><span data-ttu-id="a014d-498">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-498">Packaging</span></span></td>
<td><span data-ttu-id="a014d-499">35</span><span class="sxs-lookup"><span data-stu-id="a014d-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-500">L'oggetto di costo CC003 Assemblaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="a014d-501">Viene creato un membro di dimensione statistica denominato Servizi assemblaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="a014d-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-502">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-502">Cost object</span></span></th>
<th><span data-ttu-id="a014d-503">Servizi assemblaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="a014d-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-504">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-505">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-505">Product 1</span></span></td>
<td><span data-ttu-id="a014d-506">60</span><span class="sxs-lookup"><span data-stu-id="a014d-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-507">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-508">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-508">Product 2</span></span></td>
<td><span data-ttu-id="a014d-509">20</span><span class="sxs-lookup"><span data-stu-id="a014d-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-510">L'oggetto di costo CC004 imballaggio contribuisce a più oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="a014d-511">Viene creato un membro di dimensione statistica denominato Servizi imballaggio per misurare la grandezza consumata.</span><span class="sxs-lookup"><span data-stu-id="a014d-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-512">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-512">Cost object</span></span></th>
<th><span data-ttu-id="a014d-513">Servizi di imballaggio (ore)</span><span class="sxs-lookup"><span data-stu-id="a014d-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-514">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-515">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-515">Product 1</span></span></td>
<td><span data-ttu-id="a014d-516">80</span><span class="sxs-lookup"><span data-stu-id="a014d-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-517">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-518">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-518">Product 2</span></span></td>
<td><span data-ttu-id="a014d-519">15</span><span class="sxs-lookup"><span data-stu-id="a014d-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a014d-520">Le misure statistiche, ad esempio le ore di produzione che un prodotto consuma, possono essere derivate dai dati di origine.</span><span class="sxs-lookup"><span data-stu-id="a014d-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="a014d-521">Per altre informazioni vedere [Modello provider misure statistiche](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="a014d-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="a014d-522">Nella tabella seguente viene illustrato il risultato quando i servizi HR vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="a014d-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-523">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-523">Cost object</span></span></th>
<th><span data-ttu-id="a014d-524">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-524">Magnitude</span></span></th>
<th><span data-ttu-id="a014d-525">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="a014d-525">Allocation factor</span></span></th>
<th><span data-ttu-id="a014d-526">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-526">Amount</span></span></th>
<th><span data-ttu-id="a014d-527">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-528">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-528">CC002</span></span></td>
<td><span data-ttu-id="a014d-529">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-529">Finance</span></span></td>
<td><span data-ttu-id="a014d-530">35</span><span class="sxs-lookup"><span data-stu-id="a014d-530">35</span></span></td>
<td><span data-ttu-id="a014d-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a014d-532">175.00</span><span class="sxs-lookup"><span data-stu-id="a014d-532">175.00</span></span></td>
<td><span data-ttu-id="a014d-533">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-534">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-534">CC003</span></span></td>
<td><span data-ttu-id="a014d-535">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-535">Assembly</span></span></td>
<td><span data-ttu-id="a014d-536">55</span><span class="sxs-lookup"><span data-stu-id="a014d-536">55</span></span></td>
<td><span data-ttu-id="a014d-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a014d-538">275.00</span><span class="sxs-lookup"><span data-stu-id="a014d-538">275.00</span></span></td>
<td><span data-ttu-id="a014d-539">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-540">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-540">CC004</span></span></td>
<td><span data-ttu-id="a014d-541">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-541">Packaging</span></span></td>
<td><span data-ttu-id="a014d-542">10</span><span class="sxs-lookup"><span data-stu-id="a014d-542">10</span></span></td>
<td><span data-ttu-id="a014d-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a014d-544">50,00</span><span class="sxs-lookup"><span data-stu-id="a014d-544">50.00</span></span></td>
<td><span data-ttu-id="a014d-545">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-546">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-546">CC002</span></span></td>
<td><span data-ttu-id="a014d-547">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-547">Finance</span></span></td>
<td><span data-ttu-id="a014d-548">35</span><span class="sxs-lookup"><span data-stu-id="a014d-548">35</span></span></td>
<td><span data-ttu-id="a014d-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="a014d-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a014d-550">436.00</span><span class="sxs-lookup"><span data-stu-id="a014d-550">436.00</span></span></td>
<td><span data-ttu-id="a014d-551">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-552">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-552">CC003</span></span></td>
<td><span data-ttu-id="a014d-553">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-553">Assembly</span></span></td>
<td><span data-ttu-id="a014d-554">55</span><span class="sxs-lookup"><span data-stu-id="a014d-554">55</span></span></td>
<td><span data-ttu-id="a014d-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="a014d-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a014d-556">685.14</span><span class="sxs-lookup"><span data-stu-id="a014d-556">685.14</span></span></td>
<td><span data-ttu-id="a014d-557">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-558">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-558">CC004</span></span></td>
<td><span data-ttu-id="a014d-559">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-559">Packaging</span></span></td>
<td><span data-ttu-id="a014d-560">10</span><span class="sxs-lookup"><span data-stu-id="a014d-560">10</span></span></td>
<td><span data-ttu-id="a014d-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="a014d-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a014d-562">124.57</span><span class="sxs-lookup"><span data-stu-id="a014d-562">124.57</span></span></td>
<td><span data-ttu-id="a014d-563">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-564">Nella tabella seguente viene illustrato il risultato quando i servizi finanziari vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="a014d-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-565">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-565">Cost object</span></span></th>
<th><span data-ttu-id="a014d-566">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-566">Magnitude</span></span></th>
<th><span data-ttu-id="a014d-567">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="a014d-567">Allocation factor</span></span></th>
<th><span data-ttu-id="a014d-568">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-568">Amount</span></span></th>
<th><span data-ttu-id="a014d-569">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-570">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-570">CC003</span></span></td>
<td><span data-ttu-id="a014d-571">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-571">Assembly</span></span></td>
<td><span data-ttu-id="a014d-572">65</span><span class="sxs-lookup"><span data-stu-id="a014d-572">65</span></span></td>
<td><span data-ttu-id="a014d-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a014d-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a014d-574">438.75</span><span class="sxs-lookup"><span data-stu-id="a014d-574">438.75</span></span></td>
<td><span data-ttu-id="a014d-575">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-576">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-576">CC004</span></span></td>
<td><span data-ttu-id="a014d-577">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-577">Packaging</span></span></td>
<td><span data-ttu-id="a014d-578">35</span><span class="sxs-lookup"><span data-stu-id="a014d-578">35</span></span></td>
<td><span data-ttu-id="a014d-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a014d-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a014d-580">236.25</span><span class="sxs-lookup"><span data-stu-id="a014d-580">236.25</span></span></td>
<td><span data-ttu-id="a014d-581">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-582">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-582">CC003</span></span></td>
<td><span data-ttu-id="a014d-583">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-583">Assembly</span></span></td>
<td><span data-ttu-id="a014d-584">65</span><span class="sxs-lookup"><span data-stu-id="a014d-584">65</span></span></td>
<td><span data-ttu-id="a014d-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a014d-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a014d-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a014d-586">5,297.69</span></span></td>
<td><span data-ttu-id="a014d-587">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-588">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-588">CC004</span></span></td>
<td><span data-ttu-id="a014d-589">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-589">Packaging</span></span></td>
<td><span data-ttu-id="a014d-590">35</span><span class="sxs-lookup"><span data-stu-id="a014d-590">35</span></span></td>
<td><span data-ttu-id="a014d-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a014d-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a014d-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a014d-592">2,852.60</span></span></td>
<td><span data-ttu-id="a014d-593">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-594">Nella tabella seguente viene illustrato il risultato quando i servizi assemblaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="a014d-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-595">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-595">Cost object</span></span></th>
<th><span data-ttu-id="a014d-596">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-596">Magnitude</span></span></th>
<th><span data-ttu-id="a014d-597">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="a014d-597">Allocation factor</span></span></th>
<th><span data-ttu-id="a014d-598">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-598">Amount</span></span></th>
<th><span data-ttu-id="a014d-599">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-600">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-601">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-601">Product 1</span></span></td>
<td><span data-ttu-id="a014d-602">60</span><span class="sxs-lookup"><span data-stu-id="a014d-602">60</span></span></td>
<td><span data-ttu-id="a014d-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a014d-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a014d-604">535.31</span><span class="sxs-lookup"><span data-stu-id="a014d-604">535.31</span></span></td>
<td><span data-ttu-id="a014d-605">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-606">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-607">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-607">Product 2</span></span></td>
<td><span data-ttu-id="a014d-608">20</span><span class="sxs-lookup"><span data-stu-id="a014d-608">20</span></span></td>
<td><span data-ttu-id="a014d-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a014d-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a014d-610">178.44</span><span class="sxs-lookup"><span data-stu-id="a014d-610">178.44</span></span></td>
<td><span data-ttu-id="a014d-611">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-612">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-613">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-613">Product 1</span></span></td>
<td><span data-ttu-id="a014d-614">60</span><span class="sxs-lookup"><span data-stu-id="a014d-614">60</span></span></td>
<td><span data-ttu-id="a014d-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a014d-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a014d-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a014d-616">4,487.12</span></span></td>
<td><span data-ttu-id="a014d-617">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-618">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-619">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-619">Product 2</span></span></td>
<td><span data-ttu-id="a014d-620">20</span><span class="sxs-lookup"><span data-stu-id="a014d-620">20</span></span></td>
<td><span data-ttu-id="a014d-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a014d-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a014d-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a014d-622">1,495.71</span></span></td>
<td><span data-ttu-id="a014d-623">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a014d-624">Nella tabella seguente viene illustrato il risultato quando i servizi imballaggio vengono applicati come base di allocazione per il costo totale (costo fisso e costo variabile).</span><span class="sxs-lookup"><span data-stu-id="a014d-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-625">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-625">Cost object</span></span></th>
<th><span data-ttu-id="a014d-626">Grandezza</span><span class="sxs-lookup"><span data-stu-id="a014d-626">Magnitude</span></span></th>
<th><span data-ttu-id="a014d-627">Fattore di allocazione</span><span class="sxs-lookup"><span data-stu-id="a014d-627">Allocation factor</span></span></th>
<th><span data-ttu-id="a014d-628">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-628">Amount</span></span></th>
<th><span data-ttu-id="a014d-629">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-630">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-631">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-631">Product 1</span></span></td>
<td><span data-ttu-id="a014d-632">80</span><span class="sxs-lookup"><span data-stu-id="a014d-632">80</span></span></td>
<td><span data-ttu-id="a014d-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a014d-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a014d-634">241.05</span><span class="sxs-lookup"><span data-stu-id="a014d-634">241.05</span></span></td>
<td><span data-ttu-id="a014d-635">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-636">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-637">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-637">Product 2</span></span></td>
<td><span data-ttu-id="a014d-638">15</span><span class="sxs-lookup"><span data-stu-id="a014d-638">15</span></span></td>
<td><span data-ttu-id="a014d-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a014d-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a014d-640">45.20</span><span class="sxs-lookup"><span data-stu-id="a014d-640">45.20</span></span></td>
<td><span data-ttu-id="a014d-641">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-642">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-643">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-643">Product 1</span></span></td>
<td><span data-ttu-id="a014d-644">80</span><span class="sxs-lookup"><span data-stu-id="a014d-644">80</span></span></td>
<td><span data-ttu-id="a014d-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a014d-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a014d-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a014d-646">2,507.09</span></span></td>
<td><span data-ttu-id="a014d-647">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-648">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-649">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-649">Product 2</span></span></td>
<td><span data-ttu-id="a014d-650">15</span><span class="sxs-lookup"><span data-stu-id="a014d-650">15</span></span></td>
<td><span data-ttu-id="a014d-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a014d-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a014d-652">470.08</span><span class="sxs-lookup"><span data-stu-id="a014d-652">470.08</span></span></td>
<td><span data-ttu-id="a014d-653">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a014d-654">Scritture contabili (scritture contabili saldo oggetto di costo)</span><span class="sxs-lookup"><span data-stu-id="a014d-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-655">Giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-655">Journal</span></span></th>
<th><span data-ttu-id="a014d-656">Tipo giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a014d-657">Periodo di calendario fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a014d-658">Versione</span><span class="sxs-lookup"><span data-stu-id="a014d-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-659">00004</span><span class="sxs-lookup"><span data-stu-id="a014d-659">00004</span></span></td>
<td><span data-ttu-id="a014d-660">Giornale di registrazione allocazione costi</span><span class="sxs-lookup"><span data-stu-id="a014d-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="a014d-661">Fiscale</span><span class="sxs-lookup"><span data-stu-id="a014d-661">Fiscal</span></span></td>
<td><span data-ttu-id="a014d-662">2017</span><span class="sxs-lookup"><span data-stu-id="a014d-662">2017</span></span></td>
<td><span data-ttu-id="a014d-663">Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-663">Period 1</span></span></td>
<td><span data-ttu-id="a014d-664">Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1</span><span class="sxs-lookup"><span data-stu-id="a014d-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="a014d-665">Righe giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a014d-666">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-667">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-668">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-668">Cost element</span></span></th>
<th><span data-ttu-id="a014d-669">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-669">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-670">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-671">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-672">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-672">CC001</span></span></td>
<td><span data-ttu-id="a014d-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-673">HR</span></span></td>
<td><span data-ttu-id="a014d-674">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-674">10001</span></span></td>
<td><span data-ttu-id="a014d-675">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-675">Electricity</span></span></td>
<td><span data-ttu-id="a014d-676">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-676">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-677">500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-678">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-679">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-679">CC001</span></span></td>
<td><span data-ttu-id="a014d-680">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-680">HR</span></span></td>
<td><span data-ttu-id="a014d-681">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-681">10001</span></span></td>
<td><span data-ttu-id="a014d-682">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-682">Electricity</span></span></td>
<td><span data-ttu-id="a014d-683">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-683">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="a014d-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-685">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-686">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-686">CC002</span></span></td>
<td><span data-ttu-id="a014d-687">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-687">Finance</span></span></td>
<td><span data-ttu-id="a014d-688">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-688">10001</span></span></td>
<td><span data-ttu-id="a014d-689">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-689">Electricity</span></span></td>
<td><span data-ttu-id="a014d-690">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-690">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-691">675.00</span><span class="sxs-lookup"><span data-stu-id="a014d-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-692">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-693">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-693">CC002</span></span></td>
<td><span data-ttu-id="a014d-694">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-694">Finance</span></span></td>
<td><span data-ttu-id="a014d-695">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-695">10001</span></span></td>
<td><span data-ttu-id="a014d-696">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-696">Electricity</span></span></td>
<td><span data-ttu-id="a014d-697">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-697">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="a014d-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-699">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-700">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-700">CC003</span></span></td>
<td><span data-ttu-id="a014d-701">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-701">Assembly</span></span></td>
<td><span data-ttu-id="a014d-702">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-702">10001</span></span></td>
<td><span data-ttu-id="a014d-703">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-703">Electricity</span></span></td>
<td><span data-ttu-id="a014d-704">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-704">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-705">713.75</span><span class="sxs-lookup"><span data-stu-id="a014d-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-706">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-707">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-707">CC003</span></span></td>
<td><span data-ttu-id="a014d-708">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-708">Assembly</span></span></td>
<td><span data-ttu-id="a014d-709">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-709">10001</span></span></td>
<td><span data-ttu-id="a014d-710">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-710">Electricity</span></span></td>
<td><span data-ttu-id="a014d-711">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-711">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="a014d-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-713">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-714">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-714">CC003</span></span></td>
<td><span data-ttu-id="a014d-715">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-715">Packaging</span></span></td>
<td><span data-ttu-id="a014d-716">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-716">10001</span></span></td>
<td><span data-ttu-id="a014d-717">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-717">Electricity</span></span></td>
<td><span data-ttu-id="a014d-718">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-718">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-719">286.25</span><span class="sxs-lookup"><span data-stu-id="a014d-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-720">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-721">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-721">CC003</span></span></td>
<td><span data-ttu-id="a014d-722">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-722">Packaging</span></span></td>
<td><span data-ttu-id="a014d-723">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-723">10001</span></span></td>
<td><span data-ttu-id="a014d-724">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-724">Electricity</span></span></td>
<td><span data-ttu-id="a014d-725">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-725">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="a014d-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-727">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-728">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-729">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-729">Product 1</span></span></td>
<td><span data-ttu-id="a014d-730">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-730">10001</span></span></td>
<td><span data-ttu-id="a014d-731">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-731">Electricity</span></span></td>
<td><span data-ttu-id="a014d-732">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-732">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-733">776.36</span><span class="sxs-lookup"><span data-stu-id="a014d-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-734">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-735">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-736">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-736">Product 1</span></span></td>
<td><span data-ttu-id="a014d-737">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-737">10001</span></span></td>
<td><span data-ttu-id="a014d-738">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-738">Electricity</span></span></td>
<td><span data-ttu-id="a014d-739">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-739">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a014d-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-741">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-742">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-743">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-743">Product 1</span></span></td>
<td><span data-ttu-id="a014d-744">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-744">10001</span></span></td>
<td><span data-ttu-id="a014d-745">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-745">Electricity</span></span></td>
<td><span data-ttu-id="a014d-746">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-746">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-747">223.64</span><span class="sxs-lookup"><span data-stu-id="a014d-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-748">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="a014d-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-749">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-750">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-750">Product 1</span></span></td>
<td><span data-ttu-id="a014d-751">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-751">10001</span></span></td>
<td><span data-ttu-id="a014d-752">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-752">Electricity</span></span></td>
<td><span data-ttu-id="a014d-753">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-753">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a014d-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a014d-755">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a014d-756">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a014d-757">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-757">Cost element</span></span></th>
<th><span data-ttu-id="a014d-758">Comportamento costo</span><span class="sxs-lookup"><span data-stu-id="a014d-758">Cost behavior</span></span></th>
<th><span data-ttu-id="a014d-759">Importo</span><span class="sxs-lookup"><span data-stu-id="a014d-759">Amount</span></span></th>
<th><span data-ttu-id="a014d-760">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="a014d-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a014d-761">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-761">CC001</span></span></td>
<td><span data-ttu-id="a014d-762">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-762">HR</span></span></td>
<td><span data-ttu-id="a014d-763">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-763">10001</span></span></td>
<td><span data-ttu-id="a014d-764">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-764">Electricity</span></span></td>
<td><span data-ttu-id="a014d-765">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-765">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="a014d-766">-500.00</span></span></td>
<td><span data-ttu-id="a014d-767">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-768">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-768">CC002</span></span></td>
<td><span data-ttu-id="a014d-769">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-769">Finance</span></span></td>
<td><span data-ttu-id="a014d-770">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-770">10001</span></span></td>
<td><span data-ttu-id="a014d-771">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-771">Electricity</span></span></td>
<td><span data-ttu-id="a014d-772">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-772">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-773">175.00</span><span class="sxs-lookup"><span data-stu-id="a014d-773">175.00</span></span></td>
<td><span data-ttu-id="a014d-774">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-775">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-775">CC003</span></span></td>
<td><span data-ttu-id="a014d-776">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-776">Assembly</span></span></td>
<td><span data-ttu-id="a014d-777">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-777">10001</span></span></td>
<td><span data-ttu-id="a014d-778">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-778">Electricity</span></span></td>
<td><span data-ttu-id="a014d-779">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-779">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-780">275.00</span><span class="sxs-lookup"><span data-stu-id="a014d-780">275.00</span></span></td>
<td><span data-ttu-id="a014d-781">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-782">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-782">CC004</span></span></td>
<td><span data-ttu-id="a014d-783">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-783">Packaging</span></span></td>
<td><span data-ttu-id="a014d-784">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-784">10001</span></span></td>
<td><span data-ttu-id="a014d-785">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-785">Electricity</span></span></td>
<td><span data-ttu-id="a014d-786">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-786">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-787">50,00</span><span class="sxs-lookup"><span data-stu-id="a014d-787">50,00</span></span></td>
<td><span data-ttu-id="a014d-788">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-789">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-789">CC001</span></span></td>
<td><span data-ttu-id="a014d-790">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="a014d-790">HR</span></span></td>
<td><span data-ttu-id="a014d-791">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-791">10001</span></span></td>
<td><span data-ttu-id="a014d-792">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-792">Electricity</span></span></td>
<td><span data-ttu-id="a014d-793">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-793">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="a014d-794">-1,245.71</span></span></td>
<td><span data-ttu-id="a014d-795">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-796">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-796">CC002</span></span></td>
<td><span data-ttu-id="a014d-797">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-797">Finance</span></span></td>
<td><span data-ttu-id="a014d-798">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-798">10001</span></span></td>
<td><span data-ttu-id="a014d-799">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-799">Electricity</span></span></td>
<td><span data-ttu-id="a014d-800">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-800">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-801">436.00</span><span class="sxs-lookup"><span data-stu-id="a014d-801">436.00</span></span></td>
<td><span data-ttu-id="a014d-802">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-803">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-803">CC003</span></span></td>
<td><span data-ttu-id="a014d-804">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-804">Assembly</span></span></td>
<td><span data-ttu-id="a014d-805">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-805">10001</span></span></td>
<td><span data-ttu-id="a014d-806">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-806">Electricity</span></span></td>
<td><span data-ttu-id="a014d-807">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-807">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-808">685.14</span><span class="sxs-lookup"><span data-stu-id="a014d-808">685.14</span></span></td>
<td><span data-ttu-id="a014d-809">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-810">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-810">CC004</span></span></td>
<td><span data-ttu-id="a014d-811">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-811">Packaging</span></span></td>
<td><span data-ttu-id="a014d-812">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-812">10001</span></span></td>
<td><span data-ttu-id="a014d-813">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-813">Electricity</span></span></td>
<td><span data-ttu-id="a014d-814">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-814">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-815">124.57</span><span class="sxs-lookup"><span data-stu-id="a014d-815">124.57</span></span></td>
<td><span data-ttu-id="a014d-816">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-817">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-817">CC002</span></span></td>
<td><span data-ttu-id="a014d-818">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-818">Finance</span></span></td>
<td><span data-ttu-id="a014d-819">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-819">10001</span></span></td>
<td><span data-ttu-id="a014d-820">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-820">Electricity</span></span></td>
<td><span data-ttu-id="a014d-821">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-821">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="a014d-822">-675.00</span></span></td>
<td><span data-ttu-id="a014d-823">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-824">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-824">CC003</span></span></td>
<td><span data-ttu-id="a014d-825">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-825">Assembly</span></span></td>
<td><span data-ttu-id="a014d-826">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-826">10001</span></span></td>
<td><span data-ttu-id="a014d-827">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-827">Electricity</span></span></td>
<td><span data-ttu-id="a014d-828">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-828">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-829">438.75</span><span class="sxs-lookup"><span data-stu-id="a014d-829">438.75</span></span></td>
<td><span data-ttu-id="a014d-830">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-831">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-831">CC004</span></span></td>
<td><span data-ttu-id="a014d-832">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-832">Packaging</span></span></td>
<td><span data-ttu-id="a014d-833">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-833">10001</span></span></td>
<td><span data-ttu-id="a014d-834">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-834">Electricity</span></span></td>
<td><span data-ttu-id="a014d-835">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-835">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-836">236.25</span><span class="sxs-lookup"><span data-stu-id="a014d-836">236.25</span></span></td>
<td><span data-ttu-id="a014d-837">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-838">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-838">CC002</span></span></td>
<td><span data-ttu-id="a014d-839">Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="a014d-839">Finance</span></span></td>
<td><span data-ttu-id="a014d-840">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-840">10001</span></span></td>
<td><span data-ttu-id="a014d-841">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-841">Electricity</span></span></td>
<td><span data-ttu-id="a014d-842">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-842">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="a014d-843">-8,150.29</span></span></td>
<td><span data-ttu-id="a014d-844">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-845">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-845">CC003</span></span></td>
<td><span data-ttu-id="a014d-846">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-846">Assembly</span></span></td>
<td><span data-ttu-id="a014d-847">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-847">10001</span></span></td>
<td><span data-ttu-id="a014d-848">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-848">Electricity</span></span></td>
<td><span data-ttu-id="a014d-849">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-849">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a014d-850">5,297.69</span></span></td>
<td><span data-ttu-id="a014d-851">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-852">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-852">CC004</span></span></td>
<td><span data-ttu-id="a014d-853">Imballaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-853">Packaging</span></span></td>
<td><span data-ttu-id="a014d-854">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-854">10001</span></span></td>
<td><span data-ttu-id="a014d-855">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-855">Electricity</span></span></td>
<td><span data-ttu-id="a014d-856">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-856">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a014d-857">2,852.60</span></span></td>
<td><span data-ttu-id="a014d-858">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-859">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-859">CC003</span></span></td>
<td><span data-ttu-id="a014d-860">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-860">Assembly</span></span></td>
<td><span data-ttu-id="a014d-861">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-861">10001</span></span></td>
<td><span data-ttu-id="a014d-862">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-862">Electricity</span></span></td>
<td><span data-ttu-id="a014d-863">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-863">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="a014d-864">-713.75</span></span></td>
<td><span data-ttu-id="a014d-865">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-866">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-867">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-867">Product 1</span></span></td>
<td><span data-ttu-id="a014d-868">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-868">10001</span></span></td>
<td><span data-ttu-id="a014d-869">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-869">Electricity</span></span></td>
<td><span data-ttu-id="a014d-870">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-870">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-871">535.31</span><span class="sxs-lookup"><span data-stu-id="a014d-871">535.31</span></span></td>
<td><span data-ttu-id="a014d-872">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-873">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-874">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-874">Product 2</span></span></td>
<td><span data-ttu-id="a014d-875">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-875">10001</span></span></td>
<td><span data-ttu-id="a014d-876">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-876">Electricity</span></span></td>
<td><span data-ttu-id="a014d-877">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-877">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-878">178.44</span><span class="sxs-lookup"><span data-stu-id="a014d-878">178.44</span></span></td>
<td><span data-ttu-id="a014d-879">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-880">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-880">CC003</span></span></td>
<td><span data-ttu-id="a014d-881">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-881">Assembly</span></span></td>
<td><span data-ttu-id="a014d-882">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-882">10001</span></span></td>
<td><span data-ttu-id="a014d-883">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-883">Electricity</span></span></td>
<td><span data-ttu-id="a014d-884">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-884">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="a014d-885">-5,982.83</span></span></td>
<td><span data-ttu-id="a014d-886">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-887">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-888">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-888">Product 1</span></span></td>
<td><span data-ttu-id="a014d-889">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-889">10001</span></span></td>
<td><span data-ttu-id="a014d-890">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-890">Electricity</span></span></td>
<td><span data-ttu-id="a014d-891">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-891">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a014d-892">4,487.12</span></span></td>
<td><span data-ttu-id="a014d-893">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-894">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-895">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-895">Product 2</span></span></td>
<td><span data-ttu-id="a014d-896">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-896">10001</span></span></td>
<td><span data-ttu-id="a014d-897">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-897">Electricity</span></span></td>
<td><span data-ttu-id="a014d-898">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-898">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a014d-899">1,495.71</span></span></td>
<td><span data-ttu-id="a014d-900">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-901">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-901">CC003</span></span></td>
<td><span data-ttu-id="a014d-902">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-902">Assembly</span></span></td>
<td><span data-ttu-id="a014d-903">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-903">10001</span></span></td>
<td><span data-ttu-id="a014d-904">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-904">Electricity</span></span></td>
<td><span data-ttu-id="a014d-905">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-905">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="a014d-906">-286.25</span></span></td>
<td><span data-ttu-id="a014d-907">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-908">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-909">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-909">Product 1</span></span></td>
<td><span data-ttu-id="a014d-910">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-910">10001</span></span></td>
<td><span data-ttu-id="a014d-911">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-911">Electricity</span></span></td>
<td><span data-ttu-id="a014d-912">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-912">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-913">241.05</span><span class="sxs-lookup"><span data-stu-id="a014d-913">241.05</span></span></td>
<td><span data-ttu-id="a014d-914">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-915">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-916">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-916">Product 2</span></span></td>
<td><span data-ttu-id="a014d-917">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-917">10001</span></span></td>
<td><span data-ttu-id="a014d-918">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-918">Electricity</span></span></td>
<td><span data-ttu-id="a014d-919">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-919">Fixed cost</span></span></td>
<td><span data-ttu-id="a014d-920">45.20</span><span class="sxs-lookup"><span data-stu-id="a014d-920">45.20</span></span></td>
<td><span data-ttu-id="a014d-921">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-922">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-922">CC003</span></span></td>
<td><span data-ttu-id="a014d-923">Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="a014d-923">Assembly</span></span></td>
<td><span data-ttu-id="a014d-924">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-924">10001</span></span></td>
<td><span data-ttu-id="a014d-925">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-925">Electricity</span></span></td>
<td><span data-ttu-id="a014d-926">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-926">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="a014d-927">-2,977.17</span></span></td>
<td><span data-ttu-id="a014d-928">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-929">Prod 1</span></span></td>
<td><span data-ttu-id="a014d-930">Prodotto 1</span><span class="sxs-lookup"><span data-stu-id="a014d-930">Product 1</span></span></td>
<td><span data-ttu-id="a014d-931">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-931">10001</span></span></td>
<td><span data-ttu-id="a014d-932">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-932">Electricity</span></span></td>
<td><span data-ttu-id="a014d-933">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-933">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a014d-934">2,507.09</span></span></td>
<td><span data-ttu-id="a014d-935">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a014d-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-936">Prod 2</span></span></td>
<td><span data-ttu-id="a014d-937">Prodotto 2</span><span class="sxs-lookup"><span data-stu-id="a014d-937">Product 2</span></span></td>
<td><span data-ttu-id="a014d-938">10001</span><span class="sxs-lookup"><span data-stu-id="a014d-938">10001</span></span></td>
<td><span data-ttu-id="a014d-939">Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-939">Electricity</span></span></td>
<td><span data-ttu-id="a014d-940">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-940">Variable cost</span></span></td>
<td><span data-ttu-id="a014d-941">470.08</span><span class="sxs-lookup"><span data-stu-id="a014d-941">470.08</span></span></td>
<td><span data-ttu-id="a014d-942">31 gennaio 2017</span><span class="sxs-lookup"><span data-stu-id="a014d-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="a014d-943">Conclusione</span><span class="sxs-lookup"><span data-stu-id="a014d-943">Conclusion</span></span>
<span data-ttu-id="a014d-944">Nella contabilità finanziaria, il costo di 10.000,00 dell'elettricità viene registrato in un ID fittizio del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="a014d-945">Di conseguenza, i contabili capiranno che il costo deve essere allocato.</span><span class="sxs-lookup"><span data-stu-id="a014d-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="a014d-946">Nella contabilità industriale, il flusso dei costi nelle unità organizzative e nei livelli, in base ai criteri e alle regole che vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="a014d-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="a014d-947">Ogni costo è stato associato a una base di allocazione che offre la migliore valutazione per l'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="a014d-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="a014d-948">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="a014d-949">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a014d-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="a014d-950">Totale</span><span class="sxs-lookup"><span data-stu-id="a014d-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a014d-951">CC099</span><span class="sxs-lookup"><span data-stu-id="a014d-951">CC099</span></span></th>
<th><span data-ttu-id="a014d-952">CC001</span><span class="sxs-lookup"><span data-stu-id="a014d-952">CC001</span></span></th>
<th><span data-ttu-id="a014d-953">CC002</span><span class="sxs-lookup"><span data-stu-id="a014d-953">CC002</span></span></th>
<th><span data-ttu-id="a014d-954">CC003</span><span class="sxs-lookup"><span data-stu-id="a014d-954">CC003</span></span></th>
<th><span data-ttu-id="a014d-955">CC004</span><span class="sxs-lookup"><span data-stu-id="a014d-955">CC004</span></span></th>
<th><span data-ttu-id="a014d-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a014d-956">Proj 1</span></span></th>
<th><span data-ttu-id="a014d-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a014d-957">Proj 2</span></span></th>
<th><span data-ttu-id="a014d-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a014d-958">Prod 1</span></span></th>
<th><span data-ttu-id="a014d-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a014d-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="a014d-960">10001 Elettricità</span><span class="sxs-lookup"><span data-stu-id="a014d-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a014d-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="a014d-970">Non classificato</span><span class="sxs-lookup"><span data-stu-id="a014d-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-971">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="a014d-972">Costo fisso</span><span class="sxs-lookup"><span data-stu-id="a014d-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-973">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-974">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-975">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-976">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-977">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a014d-978">776.36</span><span class="sxs-lookup"><span data-stu-id="a014d-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-979">223.64</span><span class="sxs-lookup"><span data-stu-id="a014d-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="a014d-981">Costo variabile</span><span class="sxs-lookup"><span data-stu-id="a014d-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-982">000</span><span class="sxs-lookup"><span data-stu-id="a014d-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-983">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-984">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-985">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-986">0,00</span><span class="sxs-lookup"><span data-stu-id="a014d-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-987">30,00</span><span class="sxs-lookup"><span data-stu-id="a014d-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-988">10,00</span><span class="sxs-lookup"><span data-stu-id="a014d-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a014d-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a014d-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a014d-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a014d-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a014d-992">In questo argomento viene illustrato come una voce di costo principale, 10001 Elettricità, viene trasferita tra gli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="a014d-993">Di conseguenza, questo costo generale viene allocato al livello più basso dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a014d-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="a014d-994">In altre parole, gli oggetti costo al livello più basso sostengono il costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="a014d-995">Se si richiede un flusso visivo del costo tra gli oggetti costo, è possibile utilizzare le regole dei criteri di rollup del costo per visualizzare il flusso del costo.</span><span class="sxs-lookup"><span data-stu-id="a014d-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="a014d-996">Per ulteriori informazioni, vedere [Rollup costi](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="a014d-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



