---
title: Panoramica sulla gestione della qualità
description: In questo argomento viene descritto come utilizzare la gestione della qualità in Dynamics 365 Supply Chain Management per migliorare la qualità del prodotto all'interno della supply chain.
author: perlynne
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2d51c659d9d06f075458359d81de978e7a6d14b
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814400"
---
# <a name="quality-management-overview"></a><span data-ttu-id="dfebb-103">Panoramica sulla gestione della qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfebb-104">In questo argomento viene descritto come utilizzare la gestione della qualità in Dynamics 365 Supply Chain Management per migliorare la qualità del prodotto all'interno della supply chain.</span><span class="sxs-lookup"><span data-stu-id="dfebb-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="dfebb-105">La gestione della qualità può favorire la gestione dei tempi di completamento quando ci si occupa di prodotti non conformi, indipendentemente dal punto di origine dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="dfebb-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="dfebb-106">Poiché i tipi di diagnostica sono collegati alla dichiarazione di correzione, Supply Chain Management consente di programmare le attività per correggere i problemi e impedire che si ripetano.</span><span class="sxs-lookup"><span data-stu-id="dfebb-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="dfebb-107">Oltre alla funzionalità per gestire la non conformità, la gestione della qualità include la funzionalità per tenere traccia dei problemi in base al tipo (anche i problemi interni) e per l'identificazione di soluzioni a breve termine o a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="dfebb-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="dfebb-108">Le statistiche relative agli indicatori di prestazioni chiave (KPI) forniscono un'analisi dei problemi di non conformità che si sono precedentemente verificati e le soluzioni applicate per correggerli.</span><span class="sxs-lookup"><span data-stu-id="dfebb-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="dfebb-109">È possibile utilizzare i dati storici per analizzare l'efficienza delle misure di qualità che sono state adottate in precedenza e determinare le misure appropriate in futuro.</span><span class="sxs-lookup"><span data-stu-id="dfebb-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="dfebb-110">Quando si imposta un'associazione di controllo qualità, Supply Chain Management può generare ordini di controllo qualità per diversi processi aziendali, eventi e condizioni.</span><span class="sxs-lookup"><span data-stu-id="dfebb-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="dfebb-111">L'associazione di controllo qualità può coprire un articolo specifico, un determinato gruppo di articoli oppure tutti gli articoli.</span><span class="sxs-lookup"><span data-stu-id="dfebb-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="dfebb-112">Esempi di utilizzo di gestione della qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-112">Examples of the use of quality management</span></span>
<span data-ttu-id="dfebb-113">La gestione della qualità è flessibile e può essere implementata in vari modi per soddisfare i requisiti di livelli specifici di operazioni della catena di fornitura.</span><span class="sxs-lookup"><span data-stu-id="dfebb-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="dfebb-114">Nei seguenti esempi viene illustrato i possibili usi di queste funzionalità:</span><span class="sxs-lookup"><span data-stu-id="dfebb-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="dfebb-115">Consente di avviare un processo di controllo qualità in base a criteri predefiniti (al momento della registrazione in magazzino di un ordine acquisto di un fornitore specifico).</span><span class="sxs-lookup"><span data-stu-id="dfebb-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="dfebb-116">Consente di bloccare l'inventario durante l'ispezione per impedire che venga utilizzato un magazzino non approvato (blocco completo di quantità degli ordini acquisto).</span><span class="sxs-lookup"><span data-stu-id="dfebb-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="dfebb-117">Utilizzare il campionamento articoli come parte di un'associazione di qualità per definire l'importo di inventario fisico corrente che deve essere controllato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="dfebb-118">Il campionamento può basarsi su quantità fisse o una percentuale.</span><span class="sxs-lookup"><span data-stu-id="dfebb-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="dfebb-119">Creare ordini di controllo qualità per le entrate parziali.</span><span class="sxs-lookup"><span data-stu-id="dfebb-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="dfebb-120">Per creare un ordine di controllo qualità basato sulla quantità che viene fisicamente ricevuta con un ordine, è necessario selezionare la casella di controllo **Per quantità aggiornata** nel modulo **Campionamento articoli**.</span><span class="sxs-lookup"><span data-stu-id="dfebb-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="dfebb-121">Consente di creare i tipi di test che includono i valori di test minimi, massimi e di destinazione e di eseguire il test qualitativo-contro-quantitativo con i risultati di convalida predefiniti.</span><span class="sxs-lookup"><span data-stu-id="dfebb-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="dfebb-122">Specificare un livello di qualità accettabile (AQL) per controllare le tolleranze di misura di qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="dfebb-123">Specificare le risorse che un'operazione di ispezione richiede, ad esempio area di test e strumenti di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="dfebb-124">Utilizzo delle associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-124">Working with quality associations</span></span>
<span data-ttu-id="dfebb-125">Il processo aziendale che utilizza un'associazione di controllo qualità può essere correlato a diversi documenti di origine come ordini acquisto, ordini cliente o ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="dfebb-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="dfebb-126">Ciascun record di associazione di controllo qualità definisce il set di test, l'AQL e il piano di campionamento da applicare agli ordini di controllo qualità generati.</span><span class="sxs-lookup"><span data-stu-id="dfebb-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="dfebb-127">Un record di un'associazione di controllo qualità deve essere definito per ogni variazione in un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="dfebb-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="dfebb-128">Ad esempio, è possibile impostare un'associazione di controllo qualità che generi un ordine di controllo qualità quando si aggiorna l'entrata prodotti di un ordine acquisto.</span><span class="sxs-lookup"><span data-stu-id="dfebb-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="dfebb-129">A seconda dell'impostazione del piano di esecuzione, il processo di attivazione stesso può essere bloccato quando è presente un ordine di controllo qualità aperto, o i processi seguenti, ad esempio la fatturazone di un ordine fornitore, possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="dfebb-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="dfebb-130">**Nota:** Mentre vi sono ordini di controllo qualità aperti, le quantità di inventario sono automaticamente bloccate.</span><span class="sxs-lookup"><span data-stu-id="dfebb-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="dfebb-131">A seconda dell'impostazione di **Blocco completo** nella pagina **Campionamenti articolo**, la quantità è la quantità dell'ordine di controllo qualità o la quantità della riga di documento di origine.</span><span class="sxs-lookup"><span data-stu-id="dfebb-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="dfebb-132">Per un processo aziendale specificato, il record di un'associazione di controllo qualità identifica l'evento e le condizioni per cui viene generato un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="dfebb-133">Le condizioni possono essere specifiche a un sito o a una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="dfebb-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="dfebb-134">Un ordine di controllo qualità che prevede test distruttivi può essere generato solo quando sono disponibili delle scorte per l'evento.</span><span class="sxs-lookup"><span data-stu-id="dfebb-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="dfebb-135">Negli esempi riportati di seguito viene illustrata la modalità di definizione di un record di associazione di controllo qualità per le variazioni in ciascun processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="dfebb-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="dfebb-136">Per ciascun esempio, sono riepilogati nella seguente tabella gli eventi e le condizioni definiti da un record di associazione di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="dfebb-137">Tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="dfebb-137">Reference type</span></span></th>
<th><span data-ttu-id="dfebb-138">Tipo di evento</span><span class="sxs-lookup"><span data-stu-id="dfebb-138">Event type</span></span></th>
<th><span data-ttu-id="dfebb-139">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="dfebb-139">Execution</span></span></th>
<th><span data-ttu-id="dfebb-140">Bloccaggio evento</span><span class="sxs-lookup"><span data-stu-id="dfebb-140">Event blocking</span></span></th>
<th><span data-ttu-id="dfebb-141">Riferimento documento</span><span class="sxs-lookup"><span data-stu-id="dfebb-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="dfebb-142">Inventario</span><span class="sxs-lookup"><span data-stu-id="dfebb-142">Inventory</span></span></td>
<td><span data-ttu-id="dfebb-143">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="dfebb-143">Not applicable</span></span></td>
<td><span data-ttu-id="dfebb-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="dfebb-144">Not applicable</span></span></td>
<td><span data-ttu-id="dfebb-145">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-145">None</span></span></td>
<td><span data-ttu-id="dfebb-146">Tutti</span><span class="sxs-lookup"><span data-stu-id="dfebb-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="dfebb-147">Vendite</span><span class="sxs-lookup"><span data-stu-id="dfebb-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="dfebb-148">Il processo di prelievo è programmato</span><span class="sxs-lookup"><span data-stu-id="dfebb-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="dfebb-149">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-149">Before</span></span></td>
<td><span data-ttu-id="dfebb-150">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="dfebb-151">Solo ID specifico, Gruppo o Tutto</span><span class="sxs-lookup"><span data-stu-id="dfebb-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-152">Processo di prelievo</span><span class="sxs-lookup"><span data-stu-id="dfebb-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-153">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="dfebb-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-154">Fattura</span><span class="sxs-lookup"><span data-stu-id="dfebb-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dfebb-155">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="dfebb-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-156">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-156">Before</span></span></td>
<td><span data-ttu-id="dfebb-157">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-158">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="dfebb-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-159">Fattura</span><span class="sxs-lookup"><span data-stu-id="dfebb-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="dfebb-160">Acquisto</span><span class="sxs-lookup"><span data-stu-id="dfebb-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="dfebb-161">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="dfebb-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="dfebb-162">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-162">Before</span></span></td>
<td><span data-ttu-id="dfebb-163">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-164">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="dfebb-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-165">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="dfebb-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-166">Fattura</span><span class="sxs-lookup"><span data-stu-id="dfebb-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dfebb-167">Dopo</span><span class="sxs-lookup"><span data-stu-id="dfebb-167">After</span></span></td>
<td><span data-ttu-id="dfebb-168">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-169">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="dfebb-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-170">Fattura</span><span class="sxs-lookup"><span data-stu-id="dfebb-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dfebb-171">Registrazione</span><span class="sxs-lookup"><span data-stu-id="dfebb-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-172">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="dfebb-172">Not applicable</span></span></td>
<td><span data-ttu-id="dfebb-173">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-174">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="dfebb-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-175">Fattura</span><span class="sxs-lookup"><span data-stu-id="dfebb-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="dfebb-176">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="dfebb-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-177">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-177">Before</span></span></td>
<td><span data-ttu-id="dfebb-178">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-179">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="dfebb-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-180">Fattura</span><span class="sxs-lookup"><span data-stu-id="dfebb-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="dfebb-181">Dopo</span><span class="sxs-lookup"><span data-stu-id="dfebb-181">After</span></span></td>
<td><span data-ttu-id="dfebb-182">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-183">Fattura</span><span class="sxs-lookup"><span data-stu-id="dfebb-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="dfebb-184">Produzione</span><span class="sxs-lookup"><span data-stu-id="dfebb-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-185">Registrazione</span><span class="sxs-lookup"><span data-stu-id="dfebb-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-186">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="dfebb-186">Not applicable</span></span></td>
<td><span data-ttu-id="dfebb-187">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="dfebb-188">Tutti</span><span class="sxs-lookup"><span data-stu-id="dfebb-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-189">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-190">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="dfebb-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="dfebb-191">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-192">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-192">Before</span></span></td>
<td><span data-ttu-id="dfebb-193">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-194">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-195">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="dfebb-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="dfebb-196">Dopo</span><span class="sxs-lookup"><span data-stu-id="dfebb-196">After</span></span></td>
<td><span data-ttu-id="dfebb-197">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-198">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="dfebb-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="dfebb-199">Quarantena</span><span class="sxs-lookup"><span data-stu-id="dfebb-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-200">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="dfebb-201">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-201">Before</span></span></td>
<td><span data-ttu-id="dfebb-202">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-203">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="dfebb-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-204">Dopo</span><span class="sxs-lookup"><span data-stu-id="dfebb-204">After</span></span></td>
<td><span data-ttu-id="dfebb-205">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="dfebb-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-206">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="dfebb-206">End</span></span></td>
<td><span data-ttu-id="dfebb-207">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-207">Before</span></span></td>
<td><span data-ttu-id="dfebb-208">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="dfebb-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dfebb-209">Operazione ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="dfebb-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-210">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="dfebb-211">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-211">Before</span></span></td>
<td><span data-ttu-id="dfebb-212">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-213">ID specifico, Gruppo o Tutti e Specifico risorsa, Gruppo o Tutti</span><span class="sxs-lookup"><span data-stu-id="dfebb-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-214">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-215">Dopo</span><span class="sxs-lookup"><span data-stu-id="dfebb-215">After</span></span></td>
<td><span data-ttu-id="dfebb-216">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dfebb-217">Produzione co-prodotti</span><span class="sxs-lookup"><span data-stu-id="dfebb-217">Co-product production</span></span></td>
<td><span data-ttu-id="dfebb-218">Registrazione</span><span class="sxs-lookup"><span data-stu-id="dfebb-218">Registration</span></span></td>
<td><span data-ttu-id="dfebb-219">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="dfebb-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-220">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="dfebb-221">Tutti</span><span class="sxs-lookup"><span data-stu-id="dfebb-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="dfebb-222">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="dfebb-222">Report as finished</span></span></td>
<td><span data-ttu-id="dfebb-223">Prima</span><span class="sxs-lookup"><span data-stu-id="dfebb-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-224">Dopo</span><span class="sxs-lookup"><span data-stu-id="dfebb-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dfebb-225">Nella tabella seguente vengono fornite ulteriori informazioni sulla modalità di generazione di ordini di controllo qualità per tipi specifici di processo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="dfebb-226">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="dfebb-226">Type of process</span></span></th>
<th><span data-ttu-id="dfebb-227">Quando gli ordini di controllo qualità possono essere generati automaticamente</span><span class="sxs-lookup"><span data-stu-id="dfebb-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="dfebb-228">Quando gli ordini di controllo qualità possono essere generati se il test distruttivo è obbligatorio</span><span class="sxs-lookup"><span data-stu-id="dfebb-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="dfebb-229">Informazioni sulle condizioni</span><span class="sxs-lookup"><span data-stu-id="dfebb-229">Condition information</span></span></th>
<th><span data-ttu-id="dfebb-230">Informazioni sulla generazione manuale</span><span class="sxs-lookup"><span data-stu-id="dfebb-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="dfebb-231">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="dfebb-231">Purchase order</span></span></td>
<td><span data-ttu-id="dfebb-232">Prima o dopo la registrazione di un elenco di entrate o un'entrata prodotti per il materiale ricevuta</span><span class="sxs-lookup"><span data-stu-id="dfebb-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="dfebb-233">Dopo che l'entrata prodotti per il materiale ricevuto viene registrata, poiché il materiale deve essere disponibile per il test distruttivo</span><span class="sxs-lookup"><span data-stu-id="dfebb-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="dfebb-234">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="dfebb-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dfebb-235">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine fornitore può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-236">Ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="dfebb-236">Quarantine order</span></span></td>
<td><span data-ttu-id="dfebb-237">Prima o dopo che l'ordine di quarantena viene dichiarato finito o completato</span><span class="sxs-lookup"><span data-stu-id="dfebb-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="dfebb-238">Gli ordini di controllo qualità che richiedono i test distruttivi non possono essere generati.</span><span class="sxs-lookup"><span data-stu-id="dfebb-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="dfebb-239">Si presume che la funzionalità di ordine di quarantena gestisca lo smaltimento del materiale distrutto.</span><span class="sxs-lookup"><span data-stu-id="dfebb-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="dfebb-240">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="dfebb-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dfebb-241">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di quarantena può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-242">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="dfebb-242">Sales order</span></span></td>
<td><span data-ttu-id="dfebb-243">Prima di un processo di prelievo o un aggiornamento del documento di trasporto per gli articoli in spedizione</span><span class="sxs-lookup"><span data-stu-id="dfebb-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="dfebb-244">In qualsiasi fase</span><span class="sxs-lookup"><span data-stu-id="dfebb-244">At any step</span></span></td>
<td><span data-ttu-id="dfebb-245">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un cliente specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="dfebb-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dfebb-246">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine cliente può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-247">Ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="dfebb-247">Production order</span></span></td>
<td><span data-ttu-id="dfebb-248">Prima o dopo la registrazione della quantità finita per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="dfebb-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="dfebb-249">Dopo la registrazione della quantità finita per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="dfebb-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="dfebb-250">La richiesta di un ordine di controllo qualità può riflettere un sito o un articolo specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="dfebb-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dfebb-251">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di produzione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-252">Ordine di produzione che ha un'operazione del ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="dfebb-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="dfebb-253">Prima o dopo che il report venga completato per un'operazione</span><span class="sxs-lookup"><span data-stu-id="dfebb-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="dfebb-254">Dopo la dichiarazione della fine dell'ultima operazione di produzione</span><span class="sxs-lookup"><span data-stu-id="dfebb-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="dfebb-255">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o una risorsa operativa specifica o una combinazione di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="dfebb-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dfebb-256">Un ordine di controllo qualità generato manualmente che si riferisce a un'operazione del ciclo di lavorazione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-257">Inventario</span><span class="sxs-lookup"><span data-stu-id="dfebb-257">Inventory</span></span></td>
<td><span data-ttu-id="dfebb-258">Un ordine di controllo qualità non può essere generato automaticamente per una transazione in un giornale di registrazione magazzino o per le transazioni degli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="dfebb-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="dfebb-259">Un ordine di controllo qualità deve essere creato manualmente per la quantità in magazzino di un articolo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="dfebb-260">Scorte fisiche disponibili è un campo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dfebb-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="dfebb-261">Esempi di generazione automatica dell'ordine di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-261">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="dfebb-262">Acquisti</span><span class="sxs-lookup"><span data-stu-id="dfebb-262">Purchasing</span></span>

<span data-ttu-id="dfebb-263">Se durante l'acquisto, si imposta il campo **Tipo di evento** su **Entrata prodotti** e il campo **Esecuzione** su **Dopo** nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="dfebb-263">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="dfebb-264">Se l'opzione **Per quantità aggiornata** è impostata su **Sì**, viene generato un ordine di controllo qualità per ogni entrata dell'ordine fornitore, in base alla quantità ricevuta e alle impostazioni nel campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="dfebb-264">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="dfebb-265">Ogni volta che una quantità viene ricevuta per l'ordine fornitore, nuovi ordini di controllo qualità vengono generati in base alla quantità ricevuta.</span><span class="sxs-lookup"><span data-stu-id="dfebb-265">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="dfebb-266">Se l'opzione **Per quantità aggiornata** è impostata su **No**, viene generato un ordine di controllo qualità per la prima entrata dell'ordine fornitore, in base alla quantità ricevuta.</span><span class="sxs-lookup"><span data-stu-id="dfebb-266">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="dfebb-267">Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-267">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="dfebb-268">Gli ordini di controllo qualità non vengono generati per le entrate successive dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="dfebb-268">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="dfebb-269">Specifica qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-269">Quality specification</span></span></th>
<th><span data-ttu-id="dfebb-270">Per quantità aggiornata</span><span class="sxs-lookup"><span data-stu-id="dfebb-270">Per updated quantity</span></span></th>
<th><span data-ttu-id="dfebb-271">Per dimensione di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="dfebb-271">Per tracking dimension</span></span></th>
<th><span data-ttu-id="dfebb-272">Risultato</span><span class="sxs-lookup"><span data-stu-id="dfebb-272">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="dfebb-273">Percentuale: 10%</span><span class="sxs-lookup"><span data-stu-id="dfebb-273">Percentage: 10%</span></span></td>
<td><span data-ttu-id="dfebb-274">Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-274">Yes</span></span></td>
<td>
<p><span data-ttu-id="dfebb-275">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-275">Batch number: No</span></span></p>
<p><span data-ttu-id="dfebb-276">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-276">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="dfebb-277">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="dfebb-277">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="dfebb-278">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="dfebb-278">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="dfebb-279">Ordine di controllo qualità #1 per 3 (10% di 30)</span><span class="sxs-lookup"><span data-stu-id="dfebb-279">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-280">Dichiarazione di finito per 70</span><span class="sxs-lookup"><span data-stu-id="dfebb-280">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="dfebb-281">Ordine di controllo qualità #2 per 7 (10% della quantità rimanente dell'ordine, che equivale a 70 in questo caso)</span><span class="sxs-lookup"><span data-stu-id="dfebb-281">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-282">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="dfebb-282">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="dfebb-283">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-283">No</span></span></td>
<td>
<p><span data-ttu-id="dfebb-284">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-284">Batch number: No</span></span></p>
<p><span data-ttu-id="dfebb-285">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-285">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="dfebb-286">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="dfebb-286">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="dfebb-287">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="dfebb-287">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="dfebb-288">L'ordine di controllo qualità #1 viene creato per 1 (per la prima quantità dichiarata finita, con un valore fisso di 1).</span><span class="sxs-lookup"><span data-stu-id="dfebb-288">Quality order #1 is created for 1 (for the first reported-as-finished quantity, which has a fixed value of 1).</span></span></li>
<li><span data-ttu-id="dfebb-289">Non vengono creati altri ordini di controllo qualità in base alla quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="dfebb-289">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-290">Dichiarazione di finito per 10</span><span class="sxs-lookup"><span data-stu-id="dfebb-290">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="dfebb-291">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-291">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-292">Dichiarazione di finito per 60</span><span class="sxs-lookup"><span data-stu-id="dfebb-292">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="dfebb-293">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-293">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-294">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="dfebb-294">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="dfebb-295">Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-295">Yes</span></span></td>
<td>
<p><span data-ttu-id="dfebb-296">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-296">Batch number: Yes</span></span></p>
<p><span data-ttu-id="dfebb-297">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-297">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="dfebb-298">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="dfebb-298">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="dfebb-299">Dichiarazione di finito per 3</span><span class="sxs-lookup"><span data-stu-id="dfebb-299">Report as finished for 3</span></span>
<ul>
<li><span data-ttu-id="dfebb-300">Ordine di controllo qualità #1 per 1 del batch #b1, numero di serie #s1</span><span class="sxs-lookup"><span data-stu-id="dfebb-300">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="dfebb-301">Ordine di controllo qualità #2 per 1 del batch #b2, numero di serie #s2</span><span class="sxs-lookup"><span data-stu-id="dfebb-301">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="dfebb-302">Ordine di controllo qualità #3 per 1 del batch #b3, numero di serie #s3</span><span class="sxs-lookup"><span data-stu-id="dfebb-302">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-303">Dichiarazione di finito per 2</span><span class="sxs-lookup"><span data-stu-id="dfebb-303">Report as finished for 2</span></span>
<ul>
<li><span data-ttu-id="dfebb-304">Ordine di controllo qualità #4 per 1 del batch #b4, numero di serie #s4</span><span class="sxs-lookup"><span data-stu-id="dfebb-304">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="dfebb-305">Ordine di controllo qualità #5 per 1 del batch #b5, numero di serie #s5</span><span class="sxs-lookup"><span data-stu-id="dfebb-305">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="dfebb-306"><strong>Nota:</strong> il batch può essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-306"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-307">Quantità fissa: 2</span><span class="sxs-lookup"><span data-stu-id="dfebb-307">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="dfebb-308">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-308">No</span></span></td>
<td>
<p><span data-ttu-id="dfebb-309">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-309">Batch number: Yes</span></span></p>
<p><span data-ttu-id="dfebb-310">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-310">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="dfebb-311">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="dfebb-311">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="dfebb-312">Dichiarazione di finito per 4</span><span class="sxs-lookup"><span data-stu-id="dfebb-312">Report as finished for 4</span></span>
<ul>
<li><span data-ttu-id="dfebb-313">Ordine di controllo qualità #1 per 1 del batch #b1, numero di serie #s1.</span><span class="sxs-lookup"><span data-stu-id="dfebb-313">Quality order #1 for 1 of batch #b1, serial #s1.</span></span></li>
<li><span data-ttu-id="dfebb-314">Ordine di controllo qualità #2 per 1 del batch #b2, numero di serie #s2.</span><span class="sxs-lookup"><span data-stu-id="dfebb-314">Quality order #2 for 1 of batch #b2, serial #s2.</span></span></li>
<li><span data-ttu-id="dfebb-315">Ordine di controllo qualità #3 per 1 del batch #b3, numero di serie #s3.</span><span class="sxs-lookup"><span data-stu-id="dfebb-315">Quality order #3 for 1 of batch #b3, serial #s3.</span></span></li>
<li><span data-ttu-id="dfebb-316">Ordine di controllo qualità #4 per 1 del batch #b4, numero di serie #s4.</span><span class="sxs-lookup"><span data-stu-id="dfebb-316">Quality order #4 for 1 of batch #b4, serial #s4.</span></span></li>
<li><span data-ttu-id="dfebb-317">Non vengono creati altri ordini di controllo qualità in base alla quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="dfebb-317">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-318">Dichiarazione di finito per 6</span><span class="sxs-lookup"><span data-stu-id="dfebb-318">Report as finished for 6</span></span>
<ul>
<li><span data-ttu-id="dfebb-319">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-319">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="production"></a><span data-ttu-id="dfebb-320">Produzione</span><span class="sxs-lookup"><span data-stu-id="dfebb-320">Production</span></span>

<span data-ttu-id="dfebb-321">Se durante la produzione, si imposta il campo **Tipo di evento** su **Dichiarato finito** e il campo **Esecuzione** su **Dopo** nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="dfebb-321">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="dfebb-322">Se l'opzione **Per quantità aggiornata** è impostata su **Sì**, viene generato un ordine di controllo qualità in base a ogni quantità finita e alle impostazioni nel campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="dfebb-322">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="dfebb-323">Ogni volta che una quantità viene dichiarata come finita per l'ordine di produzione, nuovi ordini di controllo qualità vengono generati in base alla quantità finita.</span><span class="sxs-lookup"><span data-stu-id="dfebb-323">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="dfebb-324">La logica di generazione è coerente con l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="dfebb-324">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="dfebb-325">Se l'opzione **Per quantità aggiornata** è impostata su **No**, viene generato un ordine di controllo qualità la prima volta che una quantità viene dichiarata come finita, in base alla quantità finita.</span><span class="sxs-lookup"><span data-stu-id="dfebb-325">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="dfebb-326">Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità del campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="dfebb-326">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="dfebb-327">Gli ordini di controllo qualità non vengono generati per le successive quantità finite.</span><span class="sxs-lookup"><span data-stu-id="dfebb-327">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="dfebb-328">Specifica qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-328">Quality specification</span></span></th>
<th><span data-ttu-id="dfebb-329">Per quantità aggiornata</span><span class="sxs-lookup"><span data-stu-id="dfebb-329">Per updated quantity</span></span></th>
<th><span data-ttu-id="dfebb-330">Per dimensione di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="dfebb-330">Per tracking dimension</span></span></th>
<th><span data-ttu-id="dfebb-331">Risultato</span><span class="sxs-lookup"><span data-stu-id="dfebb-331">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="dfebb-332">Percentuale: 10%</span><span class="sxs-lookup"><span data-stu-id="dfebb-332">Percentage: 10%</span></span></td>
<td><span data-ttu-id="dfebb-333">Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-333">Yes</span></span></td>
<td>
<p><span data-ttu-id="dfebb-334">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-334">Batch number: No</span></span></p>
<p><span data-ttu-id="dfebb-335">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-335">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="dfebb-336">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="dfebb-336">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="dfebb-337">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="dfebb-337">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="dfebb-338">Ordine di controllo qualità #1 per 3 (10% di 30)</span><span class="sxs-lookup"><span data-stu-id="dfebb-338">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-339">Dichiarazione di finito per 70</span><span class="sxs-lookup"><span data-stu-id="dfebb-339">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="dfebb-340">Ordine di controllo qualità #2 per 7 (10% della quantità rimanente dell'ordine, che equivale a 70 in questo caso)</span><span class="sxs-lookup"><span data-stu-id="dfebb-340">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-341">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="dfebb-341">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="dfebb-342">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-342">No</span></span></td>
<td>
<p><span data-ttu-id="dfebb-343">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-343">Batch number: No</span></span></p>
<p><span data-ttu-id="dfebb-344">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="dfebb-344">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="dfebb-345">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="dfebb-345">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="dfebb-346">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="dfebb-346">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="dfebb-347">L'ordine di controllo qualità #1 per 1 (per la prima quantità dichiarata finita, con un valore fisso di 1)</span><span class="sxs-lookup"><span data-stu-id="dfebb-347">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="dfebb-348">L'ordine di controllo qualità #2 per 1 (per la quantità rimanente con un valore fisso di 1)</span><span class="sxs-lookup"><span data-stu-id="dfebb-348">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-349">Dichiarazione di finito per 10</span><span class="sxs-lookup"><span data-stu-id="dfebb-349">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="dfebb-350">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-350">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-351">Dichiarazione di finito per 60</span><span class="sxs-lookup"><span data-stu-id="dfebb-351">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="dfebb-352">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-352">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-353">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="dfebb-353">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="dfebb-354">Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-354">Yes</span></span></td>
<td>
<p><span data-ttu-id="dfebb-355">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-355">Batch number: Yes</span></span></p>
<p><span data-ttu-id="dfebb-356">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-356">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="dfebb-357">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="dfebb-357">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="dfebb-358">Dichiarato finito per 3: 1 per #b1, #s1; 1 per #b2, #s2 e 1 per #b3, #s3</span><span class="sxs-lookup"><span data-stu-id="dfebb-358">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="dfebb-359">Ordine di controllo qualità #1 per 1 del batch #b1, numero di serie #s1</span><span class="sxs-lookup"><span data-stu-id="dfebb-359">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="dfebb-360">Ordine di controllo qualità #2 per 1 del batch #b2, numero di serie #s2</span><span class="sxs-lookup"><span data-stu-id="dfebb-360">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="dfebb-361">Ordine di controllo qualità #3 per 1 del batch #b3, numero di serie #s3</span><span class="sxs-lookup"><span data-stu-id="dfebb-361">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-362">Dichiarato finito per 2: 1 per #b4, #s4 e 1 per #b5, #s5</span><span class="sxs-lookup"><span data-stu-id="dfebb-362">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="dfebb-363">Ordine di controllo qualità #4 per 1 del batch #b4, numero di serie #s4</span><span class="sxs-lookup"><span data-stu-id="dfebb-363">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="dfebb-364">Ordine di controllo qualità #5 per 1 del batch #b5, numero di serie #s5</span><span class="sxs-lookup"><span data-stu-id="dfebb-364">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="dfebb-365"><strong>Nota:</strong> il batch può essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-365"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="dfebb-366">Quantità fissa: 2</span><span class="sxs-lookup"><span data-stu-id="dfebb-366">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="dfebb-367">Nessuno</span><span class="sxs-lookup"><span data-stu-id="dfebb-367">No</span></span></td>
<td>
<p><span data-ttu-id="dfebb-368">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-368">Batch number: Yes</span></span></p>
<p><span data-ttu-id="dfebb-369">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="dfebb-369">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="dfebb-370">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="dfebb-370">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="dfebb-371">Dichiarato finito per 4: 1 per #b1, #s1; 1 per #b2, #s2; 1 per #b3, #s3 e 1 per #b4, #s4</span><span class="sxs-lookup"><span data-stu-id="dfebb-371">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="dfebb-372">Ordine di controllo qualità #1 per 1 del batch #b1, numero di serie #s1</span><span class="sxs-lookup"><span data-stu-id="dfebb-372">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="dfebb-373">Ordine di controllo qualità #2 per 1 del batch #b2, numero di serie #s2</span><span class="sxs-lookup"><span data-stu-id="dfebb-373">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="dfebb-374">Ordine di controllo qualità #3 per 1 del batch #b3, numero di serie #s3</span><span class="sxs-lookup"><span data-stu-id="dfebb-374">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="dfebb-375">Ordine di controllo qualità #4 per 1 del batch #b4, numero di serie #s4</span><span class="sxs-lookup"><span data-stu-id="dfebb-375">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="dfebb-376">Ordine di controllo qualità #5 per 2, senza riferimento a un batch o un numero di serie</span><span class="sxs-lookup"><span data-stu-id="dfebb-376">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dfebb-377">Dichiarato finito per 6: 1 per #b5, #s5; 1 per #b6, #s6; 1 per #b7, #s7; 1 per #b8, #s8; 1 per #b9, #s9 e 1 per #b10, #s10</span><span class="sxs-lookup"><span data-stu-id="dfebb-377">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="dfebb-378">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-378">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="dfebb-379">Pagine sulla gestione qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-379">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfebb-380">Pagina</span><span class="sxs-lookup"><span data-stu-id="dfebb-380">Page</span></span></th>
<th><span data-ttu-id="dfebb-381">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfebb-381">Description</span></span></th>
<th><span data-ttu-id="dfebb-382">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfebb-382">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="dfebb-383">Associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-383">Quality associations</span></span></td>
<td><span data-ttu-id="dfebb-384">Vedere le sezioni precedenti dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-384">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="dfebb-385">Un'associazione di controllo qualità definisce le seguenti informazioni per un ordine di controllo qualità generato:</span><span class="sxs-lookup"><span data-stu-id="dfebb-385">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="dfebb-386">L'evento della transazione</span><span class="sxs-lookup"><span data-stu-id="dfebb-386">The transaction event</span></span></li>
<li><span data-ttu-id="dfebb-387">Il set di test che devono essere eseguiti sugli articoli</span><span class="sxs-lookup"><span data-stu-id="dfebb-387">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="dfebb-388">L'AQL</span><span class="sxs-lookup"><span data-stu-id="dfebb-388">The AQL</span></span></li>
<li><span data-ttu-id="dfebb-389">Il piano di campionamento</span><span class="sxs-lookup"><span data-stu-id="dfebb-389">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="dfebb-390">Occorre definire un'associazione di controllo qualità per ogni variazione in un processo aziendale che richieda la generazione automatica di un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-390">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="dfebb-391">Ad esempio, è possible generare un ordine di controllo qualità nei processi aziendali per ordini acquisto, ordini di quarantena, ordini cliente e ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="dfebb-391">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dfebb-392">Test</span><span class="sxs-lookup"><span data-stu-id="dfebb-392">Tests</span></span></td>
<td><span data-ttu-id="dfebb-393">Utilizzare questa pagina per definire e visualizzare i singoli test che determinano se i prodotti sono conformi alle specifiche di qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-393">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="dfebb-394">È possibile assegnare uno o più test singoli a un gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-394">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="dfebb-395">In questo caso, è inoltre necessario specificare le informazioni specifiche del test, ad esempio i valori di misurazione accettabili.</span><span class="sxs-lookup"><span data-stu-id="dfebb-395">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="dfebb-396">I valori di misurazione vengono utilizzati per i test quantitativi, mentre le variabili di test vengono utilizzate per i test qualitativi.</span><span class="sxs-lookup"><span data-stu-id="dfebb-396">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="dfebb-397">A un test quantitativo è associato un tipo di test <strong>Intero</strong> o <strong>Frazione</strong> e di un'unità di misura designata.</span><span class="sxs-lookup"><span data-stu-id="dfebb-397">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="dfebb-398">Le specifiche di qualità e i risultati del test vengono espressi sotto forma di numeri.</span><span class="sxs-lookup"><span data-stu-id="dfebb-398">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="dfebb-399">Un test qualitativo è un tipo di test <strong>Opzione</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfebb-399">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="dfebb-400">I test qualitativi richiedono informazioni aggiuntive sulla variabile di test misurata e sulle relative opzioni enumerate.</span><span class="sxs-lookup"><span data-stu-id="dfebb-400">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="dfebb-401">Le specifiche di qualità e i risultati del test vengono espressi in base a un esito.</span><span class="sxs-lookup"><span data-stu-id="dfebb-401">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="dfebb-402">Una società di produzione esegue due test sul materiale acquistato, ovvero un test quantitativo sulla qualità del materiale e un test qualitativo sul danno all'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="dfebb-402">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="dfebb-403">La società definisce informazioni aggiuntive sul test qualitativo per identificare la variabile di test, per l'imballaggio danneggiato, e i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="dfebb-403">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="dfebb-404">La società utilizza la pagina <strong>Gruppi di test</strong> per assegnare i due test a un gruppo di test e per specificare le informazioni specifiche del test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-404">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="dfebb-405">Il gruppo di test viene assegnato a un ordine di controllo qualità, in modo che la società possa creare un report per i risultati dei due test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-405">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dfebb-406">Gruppi di test</span><span class="sxs-lookup"><span data-stu-id="dfebb-406">Test groups</span></span></td>
<td><span data-ttu-id="dfebb-407">Utilizzare questa pagina per impostare, modificare e visualizzare gruppi di test e i singoli test assegnati a un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="dfebb-407">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="dfebb-408">Nel riquadro superiore sono visualizzati i gruppi di test, mentre nel riquadro inferiore sono visualizzati i test assegnati a un gruppo di test selezionato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-408">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="dfebb-409">A un gruppo di test è possibile assegnare più criteri, tra cui un piano di campionamento, un AQL e la richiesta di test distruttivo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-409">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="dfebb-410">Quando si assegna un singolo test a un gruppo di test, è necessario definire informazioni aggiuntive, come sequenza, documenti e date di validità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-410">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="dfebb-411">In un test quantitativo, le informazioni definite dall'utente includono anche i valori di misurazione accettabili</span><span class="sxs-lookup"><span data-stu-id="dfebb-411">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="dfebb-412">e in un test qualitativo includono la variabile di test e il risultato predefinito.</span><span class="sxs-lookup"><span data-stu-id="dfebb-412">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="dfebb-413">Il gruppo di test assegnato a un ordine di controllo qualità definisce il set predefinito di test che devono essere eseguiti sull'articolo specificato.</span><span class="sxs-lookup"><span data-stu-id="dfebb-413">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="dfebb-414">Tuttavia, è possibile aggiungere, eliminare o modificare i test in un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-414">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="dfebb-415">I risultati di ciascun test vengono riportati in un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-415">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="dfebb-416">In una società di produzione è definito un gruppo di test per ogni variazione apportata alle linee guida per il controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-416">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="dfebb-417">I vari gruppi di test riflettono le differenze nei piani di campionamento, nei set di test da eseguire congiuntamente, nel livello di qualità accettabile e in altri fattori.</span><span class="sxs-lookup"><span data-stu-id="dfebb-417">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="dfebb-418">Per i test quantitativi sono inoltre presenti differenze nei valori di misurazione accettabili.</span><span class="sxs-lookup"><span data-stu-id="dfebb-418">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="dfebb-419">Per applicare le linee guida per il controllo qualità, la società assegna un gruppo di test a ciascuna regola per la generazione automatica di ordini di controllo qualità (nella pagina <strong>Associazioni di controllo qualità</strong>) e assegna un gruppo di test agli ordini di controllo qualità creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="dfebb-419">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dfebb-420">Gruppi di controllo qualità articoli</span><span class="sxs-lookup"><span data-stu-id="dfebb-420">Item quality groups</span></span></td>
<td><span data-ttu-id="dfebb-421">Utilizzare questa pagina per impostare, modificare e visualizzare gli articoli assegnati a un gruppo di controllo qualità o i gruppi di controllo qualità assegnati a un articolo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-421">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="dfebb-422">Un gruppo di controllo qualità rappresenta i requisiti di test comuni per gli articoli.</span><span class="sxs-lookup"><span data-stu-id="dfebb-422">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="dfebb-423">Dopo la definizione dei requisiti di test nella pagine <strong>Gruppi di test</strong>, è possibile definire le regole per generare automaticamente gli ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="dfebb-423">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="dfebb-424">Per semplificare il processo, non si definiscono le regole per i singoli articoli.</span><span class="sxs-lookup"><span data-stu-id="dfebb-424">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="dfebb-425">Invece, definire le regole per un gruppo di controllo qualità, utilizzando la pagina <strong>Associazioni di controllo qualità</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfebb-425">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="dfebb-426">È inoltre possibile utilizzare la pagina <strong>Gruppi di controllo qualità articoli</strong> per un gruppo di controllo qualità selezionato per assegnare gli articoli rilevanti al gruppo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-426">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="dfebb-427">È inoltre possibile utilizzare la pagina <strong>Gruppi di controllo qualità articoli</strong> per un articolo selezionato per assegnarvi i gruppi di controllo qualità rilevanti.</span><span class="sxs-lookup"><span data-stu-id="dfebb-427">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="dfebb-428">Una società di produzione acquista varie materie prime con gli stessi requisiti di test per quanto riguarda l'ispezione in entrata.</span><span class="sxs-lookup"><span data-stu-id="dfebb-428">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="dfebb-429">La società definisce un gruppo di controllo qualità e vi assegna i numeri articolo associati alle materie prime.</span><span class="sxs-lookup"><span data-stu-id="dfebb-429">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="dfebb-430">In seguito, la società acquista un nuovo tipo di materie prima con gli stessi requisiti di test.</span><span class="sxs-lookup"><span data-stu-id="dfebb-430">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="dfebb-431">Invece di impostare nuovi requisiti di test per il nuovo materiale, la società aggiunge il relativo numero articolo al gruppo di controllo qualità esistente.</span><span class="sxs-lookup"><span data-stu-id="dfebb-431">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="dfebb-432">La stessa società produce inoltre articoli con gli stessi requisiti di test della produzione e spedisce articoli con gli stessi requisiti per quanto riguarda l'esecuzione di test prima della spedizione.</span><span class="sxs-lookup"><span data-stu-id="dfebb-432">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="dfebb-433">La società definisce due ulteriori gruppi di controllo qualità e assegna a ognuno i numeri di articolo rilevanti.</span><span class="sxs-lookup"><span data-stu-id="dfebb-433">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dfebb-434">Variabili di test</span><span class="sxs-lookup"><span data-stu-id="dfebb-434">Test variables</span></span></td>
<td><span data-ttu-id="dfebb-435">Utilizzare questa pagina per definire e visualizzare le variabili associate a un test qualitativo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-435">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="dfebb-436">Per ciascuna variabile, è possibile definire i risultati enumerati che rappresentano le possibili opzioni.</span><span class="sxs-lookup"><span data-stu-id="dfebb-436">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="dfebb-437">Definire i test nella pagina <strong>Test</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfebb-437">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="dfebb-438">Per i test qualitativi, è necessario impostare il tipo di test su <strong>Opzione</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfebb-438">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="dfebb-439">Utilizzare la pagina <strong>Gruppi di test</strong> per assegnare una variabile di test a un test specifico.</span><span class="sxs-lookup"><span data-stu-id="dfebb-439">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="dfebb-440">Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="dfebb-440">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="dfebb-441">Il test di ispezione ha diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="dfebb-441">This inspection test has several variables.</span></span> <span data-ttu-id="dfebb-442">Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-442">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="dfebb-443">Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto.</span><span class="sxs-lookup"><span data-stu-id="dfebb-443">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dfebb-444">Risultati variabile di test</span><span class="sxs-lookup"><span data-stu-id="dfebb-444">Test variable outcomes</span></span></td>
<td><span data-ttu-id="dfebb-445">Utilizzare questa pagina per impostare, modificare e visualizzare i possibili risultati di una variabile di test associata a un test qualitativo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-445">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="dfebb-446">Per ogni risultato è possibile assegnare lo stato <strong>superato</strong> o <strong>non superato</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfebb-446">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="dfebb-447">È necessario definire una variabile e i relativi risultati per un test qualitativo definito nella pagina <strong>Test</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfebb-447">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="dfebb-448">Per i test qualitativi, il tipo di test è impostato su <strong>Opzione</strong> nella pagina <strong>Test</strong>. Utilizzare la pagina <strong>Gruppi di test</strong> per assegnare una variabile di test e il risultato predefinito a un singolo test qualitativo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-448">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="dfebb-449">Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="dfebb-449">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="dfebb-450">Il test di ispezione ha diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="dfebb-450">This inspection test has of several variables.</span></span> <span data-ttu-id="dfebb-451">Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo.</span><span class="sxs-lookup"><span data-stu-id="dfebb-451">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="dfebb-452">Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto.</span><span class="sxs-lookup"><span data-stu-id="dfebb-452">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="dfebb-453">A ogni risultato viene assegnato lo stato <strong>superato</strong> o <strong>non superato</strong>.</span><span class="sxs-lookup"><span data-stu-id="dfebb-453">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="dfebb-454">Durante il test di ispezione per ogni variabile, l'ispettore indica il risultato del test selezionando uno dei risultati.</span><span class="sxs-lookup"><span data-stu-id="dfebb-454">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="dfebb-455">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dfebb-455">Additional resources</span></span>
--------

[<span data-ttu-id="dfebb-456">Processi di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="dfebb-456">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="dfebb-457">Gestione della non conformità</span><span class="sxs-lookup"><span data-stu-id="dfebb-457">Nonconformance management</span></span>](enable-nonconformance-management.md)
