---
title: Panoramica sulla gestione della qualità
description: In questo argomento viene descritto come utilizzare la gestione della qualità in Dynamics 365 Supply Chain Management per migliorare la qualità del prodotto all'interno della supply chain.
author: perlynne
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1d7828e6bb9a3684c1d76e2cfac96174a8dfbf4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431220"
---
# <a name="quality-management-overview"></a><span data-ttu-id="ea457-103">Panoramica sulla gestione della qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea457-104">In questo argomento viene descritto come utilizzare la gestione della qualità in Dynamics 365 Supply Chain Management per migliorare la qualità del prodotto all'interno della supply chain.</span><span class="sxs-lookup"><span data-stu-id="ea457-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="ea457-105">La gestione della qualità può favorire la gestione dei tempi di completamento quando ci si occupa di prodotti non conformi, indipendentemente dal punto di origine dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="ea457-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="ea457-106">Poiché i tipi di diagnostica sono collegati alla dichiarazione di correzione, Supply Chain Management consente di programmare le attività per correggere i problemi e impedire che si ripetano.</span><span class="sxs-lookup"><span data-stu-id="ea457-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="ea457-107">Oltre alla funzionalità per gestire la non conformità, la gestione della qualità include la funzionalità per tenere traccia dei problemi in base al tipo (anche i problemi interni) e per l'identificazione di soluzioni a breve termine o a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="ea457-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="ea457-108">Le statistiche relative agli indicatori di prestazioni chiave (KPI) forniscono un'analisi dei problemi di non conformità che si sono precedentemente verificati e le soluzioni applicate per correggerli.</span><span class="sxs-lookup"><span data-stu-id="ea457-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="ea457-109">È possibile utilizzare i dati storici per analizzare l'efficienza delle misure di qualità che sono state adottate in precedenza e determinare le misure appropriate in futuro.</span><span class="sxs-lookup"><span data-stu-id="ea457-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="ea457-110">Quando si imposta un'associazione di controllo qualità, Supply Chain Management può generare ordini di controllo qualità per diversi processi aziendali, eventi e condizioni.</span><span class="sxs-lookup"><span data-stu-id="ea457-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="ea457-111">L'associazione di controllo qualità può coprire un articolo specifico, un determinato gruppo di articoli oppure tutti gli articoli.</span><span class="sxs-lookup"><span data-stu-id="ea457-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="ea457-112">Esempi di utilizzo di gestione della qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-112">Examples of the use of quality management</span></span>
<span data-ttu-id="ea457-113">La gestione della qualità è flessibile e può essere implementata in vari modi per soddisfare i requisiti di livelli specifici di operazioni della catena di fornitura.</span><span class="sxs-lookup"><span data-stu-id="ea457-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="ea457-114">Nei seguenti esempi viene illustrato i possibili usi di queste funzionalità:</span><span class="sxs-lookup"><span data-stu-id="ea457-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="ea457-115">Consente di avviare un processo di controllo qualità in base a criteri predefiniti (al momento della registrazione in magazzino di un ordine acquisto di un fornitore specifico).</span><span class="sxs-lookup"><span data-stu-id="ea457-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="ea457-116">Consente di bloccare l'inventario durante l'ispezione per impedire che venga utilizzato un magazzino non approvato (blocco completo di quantità degli ordini acquisto).</span><span class="sxs-lookup"><span data-stu-id="ea457-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="ea457-117">Utilizzare il campionamento articoli come parte di un'associazione di qualità per definire l'importo di inventario fisico corrente che deve essere controllato.</span><span class="sxs-lookup"><span data-stu-id="ea457-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="ea457-118">Il campionamento può essere basato su quantità fisse, una percentuale o una targa completa.</span><span class="sxs-lookup"><span data-stu-id="ea457-118">Sampling can be based on fixed quantities, a percentage, or full license plate.</span></span>

> [!NOTE]
> <span data-ttu-id="ea457-119">La funzionalità _Gestione della qualità per i processi di magazzino_ estende le capacità di gestione della qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-119">The _Quality management for warehouse processes_ feature extends the capabilities of quality management.</span></span> <span data-ttu-id="ea457-120">Se si utilizza questa funzione, vedere [Gestione della qualità per i processi di magazzino](quality-management-for-warehouses-processes.md) per esempi su come funziona la gestione della qualità quando è abilitata.</span><span class="sxs-lookup"><span data-stu-id="ea457-120">If you are using this feature, then see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md) for examples of how quality management works when it's enabled.</span></span>

-   <span data-ttu-id="ea457-121">Creare ordini di controllo qualità per le entrate parziali.</span><span class="sxs-lookup"><span data-stu-id="ea457-121">Create quality orders for partial receipts.</span></span> <span data-ttu-id="ea457-122">Per creare un ordine di controllo qualità basato sulla quantità che viene fisicamente ricevuta con un ordine, è necessario selezionare la casella di controllo **Per quantità aggiornata** nel modulo **Campionamento articoli**.</span><span class="sxs-lookup"><span data-stu-id="ea457-122">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="ea457-123">Consente di creare i tipi di test che includono i valori di test minimi, massimi e di destinazione e di eseguire il test qualitativo-contro-quantitativo con i risultati di convalida predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ea457-123">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="ea457-124">Specificare un livello di qualità accettabile (AQL) per controllare le tolleranze di misura di qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-124">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="ea457-125">Specificare le risorse che un'operazione di ispezione richiede, ad esempio area di test e strumenti di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-125">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="ea457-126">Utilizzo delle associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-126">Working with quality associations</span></span>
<span data-ttu-id="ea457-127">Il processo aziendale che utilizza un'associazione di controllo qualità può essere correlato a diversi documenti di origine come ordini acquisto, ordini cliente o ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="ea457-127">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="ea457-128">Ciascun record di associazione di controllo qualità definisce il set di test, l'AQL e il piano di campionamento da applicare agli ordini di controllo qualità generati.</span><span class="sxs-lookup"><span data-stu-id="ea457-128">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="ea457-129">Un record di un'associazione di controllo qualità deve essere definito per ogni variazione in un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="ea457-129">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="ea457-130">Ad esempio, è possibile impostare un'associazione di controllo qualità che generi un ordine di controllo qualità quando si aggiorna l'entrata prodotti di un ordine acquisto.</span><span class="sxs-lookup"><span data-stu-id="ea457-130">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="ea457-131">A seconda dell'impostazione del piano di esecuzione, il processo di attivazione stesso può essere bloccato quando è presente un ordine di controllo qualità aperto, o i processi seguenti, ad esempio la fatturazone di un ordine fornitore, possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="ea457-131">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="ea457-132">**Nota:** Mentre vi sono ordini di controllo qualità aperti, le quantità di inventario sono automaticamente bloccate.</span><span class="sxs-lookup"><span data-stu-id="ea457-132">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="ea457-133">A seconda dell'impostazione di **Blocco completo** nella pagina **Campionamenti articolo**, la quantità è la quantità dell'ordine di controllo qualità o la quantità della riga di documento di origine.</span><span class="sxs-lookup"><span data-stu-id="ea457-133">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="ea457-134">Per un processo aziendale specificato, il record di un'associazione di controllo qualità identifica l'evento e le condizioni per cui viene generato un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-134">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="ea457-135">Le condizioni possono essere specifiche a un sito o a una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="ea457-135">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="ea457-136">Un ordine di controllo qualità che prevede test distruttivi può essere generato solo quando sono disponibili delle scorte per l'evento.</span><span class="sxs-lookup"><span data-stu-id="ea457-136">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="ea457-137">Negli esempi riportati di seguito viene illustrata la modalità di definizione di un record di associazione di controllo qualità per le variazioni in ciascun processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="ea457-137">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="ea457-138">Per ciascun esempio, sono riepilogati nella seguente tabella gli eventi e le condizioni definiti da un record di associazione di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-138">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="ea457-139">Tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="ea457-139">Reference type</span></span></th>
<th><span data-ttu-id="ea457-140">Tipo di evento</span><span class="sxs-lookup"><span data-stu-id="ea457-140">Event type</span></span></th>
<th><span data-ttu-id="ea457-141">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="ea457-141">Execution</span></span></th>
<th><span data-ttu-id="ea457-142">Bloccaggio evento</span><span class="sxs-lookup"><span data-stu-id="ea457-142">Event blocking</span></span></th>
<th><span data-ttu-id="ea457-143">Riferimento documento</span><span class="sxs-lookup"><span data-stu-id="ea457-143">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="ea457-144">Inventario</span><span class="sxs-lookup"><span data-stu-id="ea457-144">Inventory</span></span></td>
<td><span data-ttu-id="ea457-145">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ea457-145">Not applicable</span></span></td>
<td><span data-ttu-id="ea457-146">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ea457-146">Not applicable</span></span></td>
<td><span data-ttu-id="ea457-147">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-147">None</span></span></td>
<td><span data-ttu-id="ea457-148">Tutti</span><span class="sxs-lookup"><span data-stu-id="ea457-148">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="ea457-149">Vendite</span><span class="sxs-lookup"><span data-stu-id="ea457-149">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="ea457-150">Il processo di prelievo è programmato</span><span class="sxs-lookup"><span data-stu-id="ea457-150">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="ea457-151">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-151">Before</span></span></td>
<td><span data-ttu-id="ea457-152">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-152">None</span></span></td>
<td rowspan="22"><span data-ttu-id="ea457-153">Solo ID specifico, Gruppo o Tutto</span><span class="sxs-lookup"><span data-stu-id="ea457-153">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-154">Processo di prelievo</span><span class="sxs-lookup"><span data-stu-id="ea457-154">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-155">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="ea457-155">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-156">Fattura</span><span class="sxs-lookup"><span data-stu-id="ea457-156">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="ea457-157">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="ea457-157">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-158">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-158">Before</span></span></td>
<td><span data-ttu-id="ea457-159">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-160">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="ea457-160">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-161">Fattura</span><span class="sxs-lookup"><span data-stu-id="ea457-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="ea457-162">Acquisto</span><span class="sxs-lookup"><span data-stu-id="ea457-162">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="ea457-163">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="ea457-163">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="ea457-164">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-164">Before</span></span></td>
<td><span data-ttu-id="ea457-165">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-165">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-166">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="ea457-166">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-167">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="ea457-167">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-168">Fattura</span><span class="sxs-lookup"><span data-stu-id="ea457-168">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="ea457-169">Dopo</span><span class="sxs-lookup"><span data-stu-id="ea457-169">After</span></span></td>
<td><span data-ttu-id="ea457-170">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-170">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-171">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="ea457-171">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-172">Fattura</span><span class="sxs-lookup"><span data-stu-id="ea457-172">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="ea457-173">Registrazione</span><span class="sxs-lookup"><span data-stu-id="ea457-173">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-174">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ea457-174">Not applicable</span></span></td>
<td><span data-ttu-id="ea457-175">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-175">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-176">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="ea457-176">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-177">Fattura</span><span class="sxs-lookup"><span data-stu-id="ea457-177">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="ea457-178">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="ea457-178">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-179">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-179">Before</span></span></td>
<td><span data-ttu-id="ea457-180">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-180">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-181">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="ea457-181">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-182">Fattura</span><span class="sxs-lookup"><span data-stu-id="ea457-182">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="ea457-183">Dopo</span><span class="sxs-lookup"><span data-stu-id="ea457-183">After</span></span></td>
<td><span data-ttu-id="ea457-184">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-185">Fattura</span><span class="sxs-lookup"><span data-stu-id="ea457-185">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="ea457-186">Produzione</span><span class="sxs-lookup"><span data-stu-id="ea457-186">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-187">Registrazione</span><span class="sxs-lookup"><span data-stu-id="ea457-187">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-188">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ea457-188">Not applicable</span></span></td>
<td><span data-ttu-id="ea457-189">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-189">None</span></span></td>
<td rowspan="12"><span data-ttu-id="ea457-190">Tutti</span><span class="sxs-lookup"><span data-stu-id="ea457-190">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-191">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-191">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-192">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="ea457-192">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="ea457-193">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-193">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-194">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-194">Before</span></span></td>
<td><span data-ttu-id="ea457-195">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-195">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-196">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-196">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-197">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="ea457-197">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="ea457-198">Dopo</span><span class="sxs-lookup"><span data-stu-id="ea457-198">After</span></span></td>
<td><span data-ttu-id="ea457-199">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-199">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-200">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="ea457-200">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="ea457-201">Quarantena</span><span class="sxs-lookup"><span data-stu-id="ea457-201">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-202">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-202">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="ea457-203">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-203">Before</span></span></td>
<td><span data-ttu-id="ea457-204">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-204">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-205">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="ea457-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-206">Dopo</span><span class="sxs-lookup"><span data-stu-id="ea457-206">After</span></span></td>
<td><span data-ttu-id="ea457-207">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="ea457-207">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-208">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="ea457-208">End</span></span></td>
<td><span data-ttu-id="ea457-209">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-209">Before</span></span></td>
<td><span data-ttu-id="ea457-210">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="ea457-210">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="ea457-211">Operazione ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="ea457-211">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-212">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-212">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="ea457-213">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-213">Before</span></span></td>
<td><span data-ttu-id="ea457-214">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-214">None</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-215">ID specifico, Gruppo o Tutti e Specifico risorsa, Gruppo o Tutti</span><span class="sxs-lookup"><span data-stu-id="ea457-215">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-216">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-216">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-217">Dopo</span><span class="sxs-lookup"><span data-stu-id="ea457-217">After</span></span></td>
<td><span data-ttu-id="ea457-218">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-218">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="ea457-219">Produzione co-prodotti</span><span class="sxs-lookup"><span data-stu-id="ea457-219">Co-product production</span></span></td>
<td><span data-ttu-id="ea457-220">Registrazione</span><span class="sxs-lookup"><span data-stu-id="ea457-220">Registration</span></span></td>
<td><span data-ttu-id="ea457-221">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ea457-221">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-222">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-222">None</span></span></td>
<td rowspan="3"><span data-ttu-id="ea457-223">Tutti</span><span class="sxs-lookup"><span data-stu-id="ea457-223">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="ea457-224">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="ea457-224">Report as finished</span></span></td>
<td><span data-ttu-id="ea457-225">Prima</span><span class="sxs-lookup"><span data-stu-id="ea457-225">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-226">Dopo</span><span class="sxs-lookup"><span data-stu-id="ea457-226">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ea457-227">Nella tabella seguente vengono fornite ulteriori informazioni sulla modalità di generazione di ordini di controllo qualità per tipi specifici di processo.</span><span class="sxs-lookup"><span data-stu-id="ea457-227">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="ea457-228">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="ea457-228">Type of process</span></span></th>
<th><span data-ttu-id="ea457-229">Quando gli ordini di controllo qualità possono essere generati automaticamente</span><span class="sxs-lookup"><span data-stu-id="ea457-229">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="ea457-230">Quando gli ordini di controllo qualità possono essere generati se il test distruttivo è obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ea457-230">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="ea457-231">Informazioni sulle condizioni</span><span class="sxs-lookup"><span data-stu-id="ea457-231">Condition information</span></span></th>
<th><span data-ttu-id="ea457-232">Informazioni sulla generazione manuale</span><span class="sxs-lookup"><span data-stu-id="ea457-232">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="ea457-233">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="ea457-233">Purchase order</span></span></td>
<td><span data-ttu-id="ea457-234">Prima o dopo la registrazione di un elenco di entrate o un'entrata prodotti per il materiale ricevuta</span><span class="sxs-lookup"><span data-stu-id="ea457-234">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="ea457-235">Dopo che l'entrata prodotti per il materiale ricevuto viene registrata, poiché il materiale deve essere disponibile per il test distruttivo</span><span class="sxs-lookup"><span data-stu-id="ea457-235">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="ea457-236">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="ea457-236">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="ea457-237">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine fornitore può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-237">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-238">Ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="ea457-238">Quarantine order</span></span></td>
<td><span data-ttu-id="ea457-239">Prima o dopo che l'ordine di quarantena viene dichiarato finito o completato</span><span class="sxs-lookup"><span data-stu-id="ea457-239">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="ea457-240">Gli ordini di controllo qualità che richiedono i test distruttivi non possono essere generati.</span><span class="sxs-lookup"><span data-stu-id="ea457-240">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="ea457-241">Si presume che la funzionalità di ordine di quarantena gestisca lo smaltimento del materiale distrutto.</span><span class="sxs-lookup"><span data-stu-id="ea457-241">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="ea457-242">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="ea457-242">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="ea457-243">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di quarantena può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-243">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-244">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="ea457-244">Sales order</span></span></td>
<td><span data-ttu-id="ea457-245">Prima di un processo di prelievo o un aggiornamento del documento di trasporto per gli articoli in spedizione</span><span class="sxs-lookup"><span data-stu-id="ea457-245">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="ea457-246">In qualsiasi fase</span><span class="sxs-lookup"><span data-stu-id="ea457-246">At any step</span></span></td>
<td><span data-ttu-id="ea457-247">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un cliente specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="ea457-247">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="ea457-248">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine cliente può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-248">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-249">Ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="ea457-249">Production order</span></span></td>
<td><span data-ttu-id="ea457-250">Prima o dopo la registrazione della quantità finita per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="ea457-250">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="ea457-251">Dopo la registrazione della quantità finita per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="ea457-251">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="ea457-252">La richiesta di un ordine di controllo qualità può riflettere un sito o un articolo specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="ea457-252">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="ea457-253">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di produzione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-253">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-254">Ordine di produzione che ha un'operazione del ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="ea457-254">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="ea457-255">Prima o dopo che il report venga completato per un'operazione</span><span class="sxs-lookup"><span data-stu-id="ea457-255">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="ea457-256">Dopo la dichiarazione della fine dell'ultima operazione di produzione</span><span class="sxs-lookup"><span data-stu-id="ea457-256">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="ea457-257">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o una risorsa operativa specifica o una combinazione di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="ea457-257">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="ea457-258">Un ordine di controllo qualità generato manualmente che si riferisce a un'operazione del ciclo di lavorazione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-258">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ea457-259">Inventario</span><span class="sxs-lookup"><span data-stu-id="ea457-259">Inventory</span></span></td>
<td><span data-ttu-id="ea457-260">Un ordine di controllo qualità non può essere generato automaticamente per una transazione in un giornale di registrazione magazzino o per le transazioni degli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="ea457-260">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ea457-261">Un ordine di controllo qualità deve essere creato manualmente per la quantità in magazzino di un articolo.</span><span class="sxs-lookup"><span data-stu-id="ea457-261">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="ea457-262">Scorte fisiche disponibili è un campo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea457-262">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="ea457-263">Esempi di generazione automatica dell'ordine di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-263">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="ea457-264">Acquisti</span><span class="sxs-lookup"><span data-stu-id="ea457-264">Purchasing</span></span>

<span data-ttu-id="ea457-265">Se durante l'acquisto, si imposta il campo **Tipo di evento** su **Entrata prodotti** e il campo **Esecuzione** su **Dopo** nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="ea457-265">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="ea457-266">Se l'opzione **Per quantità aggiornata** è impostata su **Sì**, viene generato un ordine di controllo qualità per ogni entrata dell'ordine fornitore, in base alla quantità ricevuta e alle impostazioni nel campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="ea457-266">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="ea457-267">Ogni volta che una quantità viene ricevuta per l'ordine fornitore, nuovi ordini di controllo qualità vengono generati in base alla quantità ricevuta.</span><span class="sxs-lookup"><span data-stu-id="ea457-267">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="ea457-268">Se l'opzione **Per quantità aggiornata** è impostata su **No**, viene generato un ordine di controllo qualità per la prima entrata dell'ordine fornitore, in base alla quantità ricevuta.</span><span class="sxs-lookup"><span data-stu-id="ea457-268">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="ea457-269">Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="ea457-269">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="ea457-270">Gli ordini di controllo qualità non vengono generati per le entrate successive dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="ea457-270">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="ea457-271">Produzione</span><span class="sxs-lookup"><span data-stu-id="ea457-271">Production</span></span>

<span data-ttu-id="ea457-272">Se durante la produzione, si imposta il campo **Tipo di evento** su **Dichiarato finito** e il campo **Esecuzione** su **Dopo** nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="ea457-272">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="ea457-273">Se l'opzione **Per quantità aggiornata** è impostata su **Sì**, viene generato un ordine di controllo qualità in base a ogni quantità finita e alle impostazioni nel campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="ea457-273">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="ea457-274">Ogni volta che una quantità viene dichiarata come finita per l'ordine di produzione, nuovi ordini di controllo qualità vengono generati in base alla quantità finita.</span><span class="sxs-lookup"><span data-stu-id="ea457-274">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="ea457-275">La logica di generazione è coerente con l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="ea457-275">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="ea457-276">Se l'opzione **Per quantità aggiornata** è impostata su **No**, viene generato un ordine di controllo qualità la prima volta che una quantità viene dichiarata come finita, in base alla quantità finita.</span><span class="sxs-lookup"><span data-stu-id="ea457-276">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="ea457-277">Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità del campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="ea457-277">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="ea457-278">Gli ordini di controllo qualità non vengono generati per le successive quantità finite.</span><span class="sxs-lookup"><span data-stu-id="ea457-278">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="ea457-279">Specifica qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-279">Quality specification</span></span></th>
<th><span data-ttu-id="ea457-280">Per quantità aggiornata</span><span class="sxs-lookup"><span data-stu-id="ea457-280">Per updated quantity</span></span></th>
<th><span data-ttu-id="ea457-281">Per dimensione di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="ea457-281">Per tracking dimension</span></span></th>
<th><span data-ttu-id="ea457-282">Risultato</span><span class="sxs-lookup"><span data-stu-id="ea457-282">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="ea457-283">Percentuale: 10%</span><span class="sxs-lookup"><span data-stu-id="ea457-283">Percentage: 10%</span></span></td>
<td><span data-ttu-id="ea457-284">Sì</span><span class="sxs-lookup"><span data-stu-id="ea457-284">Yes</span></span></td>
<td>
<p><span data-ttu-id="ea457-285">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="ea457-285">Batch number: No</span></span></p>
<p><span data-ttu-id="ea457-286">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="ea457-286">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="ea457-287">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="ea457-287">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="ea457-288">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="ea457-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="ea457-289">Ordine di controllo qualità #1 per 3 (10% di 30)</span><span class="sxs-lookup"><span data-stu-id="ea457-289">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="ea457-290">Dichiarazione di finito per 70</span><span class="sxs-lookup"><span data-stu-id="ea457-290">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="ea457-291">Ordine di controllo qualità #2 per 7 (10% della quantità rimanente dell'ordine, che equivale a 70 in questo caso)</span><span class="sxs-lookup"><span data-stu-id="ea457-291">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="ea457-292">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="ea457-292">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="ea457-293">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-293">No</span></span></td>
<td>
<p><span data-ttu-id="ea457-294">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="ea457-294">Batch number: No</span></span></p>
<p><span data-ttu-id="ea457-295">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="ea457-295">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="ea457-296">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="ea457-296">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="ea457-297">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="ea457-297">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="ea457-298">L'ordine di controllo qualità #1 per 1 (per la prima quantità dichiarata finita, con un valore fisso di 1)</span><span class="sxs-lookup"><span data-stu-id="ea457-298">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="ea457-299">L'ordine di controllo qualità #2 per 1 (per la quantità rimanente con un valore fisso di 1)</span><span class="sxs-lookup"><span data-stu-id="ea457-299">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="ea457-300">Dichiarazione di finito per 10</span><span class="sxs-lookup"><span data-stu-id="ea457-300">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="ea457-301">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="ea457-301">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="ea457-302">Dichiarazione di finito per 60</span><span class="sxs-lookup"><span data-stu-id="ea457-302">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="ea457-303">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="ea457-303">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="ea457-304">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="ea457-304">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="ea457-305">Sì</span><span class="sxs-lookup"><span data-stu-id="ea457-305">Yes</span></span></td>
<td>
<p><span data-ttu-id="ea457-306">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="ea457-306">Batch number: Yes</span></span></p>
<p><span data-ttu-id="ea457-307">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="ea457-307">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="ea457-308">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="ea457-308">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="ea457-309">Dichiarato finito per 3: 1 per #b1, #s1; 1 per #b2, #s2 e 1 per #b3, #s3</span><span class="sxs-lookup"><span data-stu-id="ea457-309">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="ea457-310">Ordine di controllo qualità #1 per 1 del batch #b1, numero di serie #s1</span><span class="sxs-lookup"><span data-stu-id="ea457-310">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="ea457-311">Ordine di controllo qualità #2 per 1 del batch #b2, numero di serie #s2</span><span class="sxs-lookup"><span data-stu-id="ea457-311">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="ea457-312">Ordine di controllo qualità #3 per 1 del batch #b3, numero di serie #s3</span><span class="sxs-lookup"><span data-stu-id="ea457-312">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="ea457-313">Dichiarato finito per 2: 1 per #b4, #s4 e 1 per #b5, #s5</span><span class="sxs-lookup"><span data-stu-id="ea457-313">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="ea457-314">Ordine di controllo qualità #4 per 1 del batch #b4, numero di serie #s4</span><span class="sxs-lookup"><span data-stu-id="ea457-314">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="ea457-315">Ordine di controllo qualità #5 per 1 del batch #b5, numero di serie #s5</span><span class="sxs-lookup"><span data-stu-id="ea457-315">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="ea457-316"><strong>Nota:</strong> il batch può essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ea457-316"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="ea457-317">Quantità fissa: 2</span><span class="sxs-lookup"><span data-stu-id="ea457-317">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="ea457-318">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ea457-318">No</span></span></td>
<td>
<p><span data-ttu-id="ea457-319">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="ea457-319">Batch number: Yes</span></span></p>
<p><span data-ttu-id="ea457-320">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="ea457-320">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="ea457-321">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="ea457-321">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="ea457-322">Dichiarato finito per 4: 1 per #b1, #s1; 1 per #b2, #s2; 1 per #b3, #s3 e 1 per #b4, #s4</span><span class="sxs-lookup"><span data-stu-id="ea457-322">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="ea457-323">Ordine di controllo qualità #1 per 1 del batch #b1, numero di serie #s1</span><span class="sxs-lookup"><span data-stu-id="ea457-323">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="ea457-324">Ordine di controllo qualità #2 per 1 del batch #b2, numero di serie #s2</span><span class="sxs-lookup"><span data-stu-id="ea457-324">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="ea457-325">Ordine di controllo qualità #3 per 1 del batch #b3, numero di serie #s3</span><span class="sxs-lookup"><span data-stu-id="ea457-325">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="ea457-326">Ordine di controllo qualità #4 per 1 del batch #b4, numero di serie #s4</span><span class="sxs-lookup"><span data-stu-id="ea457-326">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="ea457-327">Ordine di controllo qualità #5 per 2, senza riferimento a un batch o un numero di serie</span><span class="sxs-lookup"><span data-stu-id="ea457-327">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="ea457-328">Dichiarato finito per 6: 1 per #b5, #s5; 1 per #b6, #s6; 1 per #b7, #s7; 1 per #b8, #s8; 1 per #b9, #s9 e 1 per #b10, #s10</span><span class="sxs-lookup"><span data-stu-id="ea457-328">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="ea457-329">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="ea457-329">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ea457-330">La funzionalità *Gestione della qualità per i processi di magazzino* aggiunge funzionalità per l'elaborazione degli ordini di qualità per la produzione con **Tipo di evento** impostato su *Dichiarato finito* e **Esecuzione** impostato su *Dopo* e per acquisti con **Tipo di evento** impostato su *Registrazione*.</span><span class="sxs-lookup"><span data-stu-id="ea457-330">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production with **Event type** set to *Report as finished* and **Execution** set to *After*, and for purchases with **Event type** set to *Registration*.</span></span> <span data-ttu-id="ea457-331">Per informazioni dettagliate, vedere [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="ea457-331">For details, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

## <a name="quality-management-pages"></a><span data-ttu-id="ea457-332">Pagine sulla gestione qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-332">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea457-333">Pagina</span><span class="sxs-lookup"><span data-stu-id="ea457-333">Page</span></span></th>
<th><span data-ttu-id="ea457-334">descrizione</span><span class="sxs-lookup"><span data-stu-id="ea457-334">Description</span></span></th>
<th><span data-ttu-id="ea457-335">Esempio</span><span class="sxs-lookup"><span data-stu-id="ea457-335">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ea457-336">Associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-336">Quality associations</span></span></td>
<td><span data-ttu-id="ea457-337">Vedere le sezioni precedenti dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="ea457-337">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="ea457-338">Un'associazione di controllo qualità definisce le seguenti informazioni per un ordine di controllo qualità generato:</span><span class="sxs-lookup"><span data-stu-id="ea457-338">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="ea457-339">L'evento della transazione</span><span class="sxs-lookup"><span data-stu-id="ea457-339">The transaction event</span></span></li>
<li><span data-ttu-id="ea457-340">Il set di test che devono essere eseguiti sugli articoli</span><span class="sxs-lookup"><span data-stu-id="ea457-340">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="ea457-341">L'AQL</span><span class="sxs-lookup"><span data-stu-id="ea457-341">The AQL</span></span></li>
<li><span data-ttu-id="ea457-342">Il piano di campionamento</span><span class="sxs-lookup"><span data-stu-id="ea457-342">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="ea457-343">Occorre definire un'associazione di controllo qualità per ogni variazione in un processo aziendale che richieda la generazione automatica di un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-343">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="ea457-344">Ad esempio, è possible generare un ordine di controllo qualità nei processi aziendali per ordini acquisto, ordini di quarantena, ordini cliente e ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="ea457-344">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea457-345">Test</span><span class="sxs-lookup"><span data-stu-id="ea457-345">Tests</span></span></td>
<td><span data-ttu-id="ea457-346">Utilizzare questa pagina per definire e visualizzare i singoli test che determinano se i prodotti sono conformi alle specifiche di qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-346">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="ea457-347">È possibile assegnare uno o più test singoli a un gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-347">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="ea457-348">In questo caso, è inoltre necessario specificare le informazioni specifiche del test, ad esempio i valori di misurazione accettabili.</span><span class="sxs-lookup"><span data-stu-id="ea457-348">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="ea457-349">I valori di misurazione vengono utilizzati per i test quantitativi, mentre le variabili di test vengono utilizzate per i test qualitativi.</span><span class="sxs-lookup"><span data-stu-id="ea457-349">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="ea457-350">A un test quantitativo è associato un tipo di test <strong>Intero</strong> o <strong>Frazione</strong> e di un'unità di misura designata.</span><span class="sxs-lookup"><span data-stu-id="ea457-350">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="ea457-351">Le specifiche di qualità e i risultati del test vengono espressi sotto forma di numeri.</span><span class="sxs-lookup"><span data-stu-id="ea457-351">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="ea457-352">Un test qualitativo è un tipo di test <strong>Opzione</strong>.</span><span class="sxs-lookup"><span data-stu-id="ea457-352">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="ea457-353">I test qualitativi richiedono informazioni aggiuntive sulla variabile di test misurata e sulle relative opzioni enumerate.</span><span class="sxs-lookup"><span data-stu-id="ea457-353">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="ea457-354">Le specifiche di qualità e i risultati del test vengono espressi in base a un esito.</span><span class="sxs-lookup"><span data-stu-id="ea457-354">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="ea457-355">Una società di produzione esegue due test sul materiale acquistato, ovvero un test quantitativo sulla qualità del materiale e un test qualitativo sul danno all'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="ea457-355">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="ea457-356">La società definisce informazioni aggiuntive sul test qualitativo per identificare la variabile di test, per l'imballaggio danneggiato, e i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="ea457-356">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="ea457-357">La società utilizza la pagina <strong>Gruppi di test</strong> per assegnare i due test a un gruppo di test e per specificare le informazioni specifiche del test.</span><span class="sxs-lookup"><span data-stu-id="ea457-357">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="ea457-358">Il gruppo di test viene assegnato a un ordine di controllo qualità, in modo che la società possa creare un report per i risultati dei due test.</span><span class="sxs-lookup"><span data-stu-id="ea457-358">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea457-359">Gruppi di test</span><span class="sxs-lookup"><span data-stu-id="ea457-359">Test groups</span></span></td>
<td><span data-ttu-id="ea457-360">Utilizzare questa pagina per impostare, modificare e visualizzare gruppi di test e i singoli test assegnati a un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="ea457-360">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="ea457-361">Nel riquadro superiore sono visualizzati i gruppi di test, mentre nel riquadro inferiore sono visualizzati i test assegnati a un gruppo di test selezionato.</span><span class="sxs-lookup"><span data-stu-id="ea457-361">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="ea457-362">A un gruppo di test è possibile assegnare più criteri, tra cui un piano di campionamento, un AQL e la richiesta di test distruttivo.</span><span class="sxs-lookup"><span data-stu-id="ea457-362">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="ea457-363">Quando si assegna un singolo test a un gruppo di test, è necessario definire informazioni aggiuntive, come sequenza, documenti e date di validità.</span><span class="sxs-lookup"><span data-stu-id="ea457-363">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="ea457-364">In un test quantitativo, le informazioni definite dall'utente includono anche i valori di misurazione accettabili</span><span class="sxs-lookup"><span data-stu-id="ea457-364">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="ea457-365">e in un test qualitativo includono la variabile di test e il risultato predefinito.</span><span class="sxs-lookup"><span data-stu-id="ea457-365">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="ea457-366">Il gruppo di test assegnato a un ordine di controllo qualità definisce il set predefinito di test che devono essere eseguiti sull'articolo specificato.</span><span class="sxs-lookup"><span data-stu-id="ea457-366">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="ea457-367">Tuttavia, è possibile aggiungere, eliminare o modificare i test in un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-367">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="ea457-368">I risultati di ciascun test vengono riportati in un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-368">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="ea457-369">In una società di produzione è definito un gruppo di test per ogni variazione apportata alle linee guida per il controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-369">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="ea457-370">I vari gruppi di test riflettono le differenze nei piani di campionamento, nei set di test da eseguire congiuntamente, nel livello di qualità accettabile e in altri fattori.</span><span class="sxs-lookup"><span data-stu-id="ea457-370">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="ea457-371">Per i test quantitativi sono inoltre presenti differenze nei valori di misurazione accettabili.</span><span class="sxs-lookup"><span data-stu-id="ea457-371">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="ea457-372">Per applicare le linee guida per il controllo qualità, la società assegna un gruppo di test a ciascuna regola per la generazione automatica di ordini di controllo qualità (nella pagina <strong>Associazioni di controllo qualità</strong>) e assegna un gruppo di test agli ordini di controllo qualità creati manualmente.</span><span class="sxs-lookup"><span data-stu-id="ea457-372">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea457-373">Gruppi di controllo qualità articoli</span><span class="sxs-lookup"><span data-stu-id="ea457-373">Item quality groups</span></span></td>
<td><span data-ttu-id="ea457-374">Utilizzare questa pagina per impostare, modificare e visualizzare gli articoli assegnati a un gruppo di controllo qualità o i gruppi di controllo qualità assegnati a un articolo.</span><span class="sxs-lookup"><span data-stu-id="ea457-374">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="ea457-375">Un gruppo di controllo qualità rappresenta i requisiti di test comuni per gli articoli.</span><span class="sxs-lookup"><span data-stu-id="ea457-375">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="ea457-376">Dopo la definizione dei requisiti di test nella pagine <strong>Gruppi di test</strong>, è possibile definire le regole per generare automaticamente gli ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="ea457-376">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="ea457-377">Per semplificare il processo, non si definiscono le regole per i singoli articoli.</span><span class="sxs-lookup"><span data-stu-id="ea457-377">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="ea457-378">Invece, definire le regole per un gruppo di controllo qualità, utilizzando la pagina <strong>Associazioni di controllo qualità</strong>.</span><span class="sxs-lookup"><span data-stu-id="ea457-378">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="ea457-379">È inoltre possibile utilizzare la pagina <strong>Gruppi di controllo qualità articoli</strong> per un gruppo di controllo qualità selezionato per assegnare gli articoli rilevanti al gruppo.</span><span class="sxs-lookup"><span data-stu-id="ea457-379">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="ea457-380">È inoltre possibile utilizzare la pagina <strong>Gruppi di controllo qualità articoli</strong> per un articolo selezionato per assegnarvi i gruppi di controllo qualità rilevanti.</span><span class="sxs-lookup"><span data-stu-id="ea457-380">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="ea457-381">Una società di produzione acquista varie materie prime con gli stessi requisiti di test per quanto riguarda l'ispezione in entrata.</span><span class="sxs-lookup"><span data-stu-id="ea457-381">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="ea457-382">La società definisce un gruppo di controllo qualità e vi assegna i numeri articolo associati alle materie prime.</span><span class="sxs-lookup"><span data-stu-id="ea457-382">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="ea457-383">In seguito, la società acquista un nuovo tipo di materie prima con gli stessi requisiti di test.</span><span class="sxs-lookup"><span data-stu-id="ea457-383">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="ea457-384">Invece di impostare nuovi requisiti di test per il nuovo materiale, la società aggiunge il relativo numero articolo al gruppo di controllo qualità esistente.</span><span class="sxs-lookup"><span data-stu-id="ea457-384">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="ea457-385">La stessa società produce inoltre articoli con gli stessi requisiti di test della produzione e spedisce articoli con gli stessi requisiti per quanto riguarda l'esecuzione di test prima della spedizione.</span><span class="sxs-lookup"><span data-stu-id="ea457-385">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="ea457-386">La società definisce due ulteriori gruppi di controllo qualità e assegna a ognuno i numeri di articolo rilevanti.</span><span class="sxs-lookup"><span data-stu-id="ea457-386">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea457-387">Variabili di test</span><span class="sxs-lookup"><span data-stu-id="ea457-387">Test variables</span></span></td>
<td><span data-ttu-id="ea457-388">Utilizzare questa pagina per definire e visualizzare le variabili associate a un test qualitativo.</span><span class="sxs-lookup"><span data-stu-id="ea457-388">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="ea457-389">Per ciascuna variabile, è possibile definire i risultati enumerati che rappresentano le possibili opzioni.</span><span class="sxs-lookup"><span data-stu-id="ea457-389">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="ea457-390">Definire i test nella pagina <strong>Test</strong>.</span><span class="sxs-lookup"><span data-stu-id="ea457-390">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="ea457-391">Per i test qualitativi, è necessario impostare il tipo di test su <strong>Opzione</strong>.</span><span class="sxs-lookup"><span data-stu-id="ea457-391">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="ea457-392">Utilizzare la pagina <strong>Gruppi di test</strong> per assegnare una variabile di test a un test specifico.</span><span class="sxs-lookup"><span data-stu-id="ea457-392">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="ea457-393">Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="ea457-393">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="ea457-394">Il test di ispezione ha diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="ea457-394">This inspection test has several variables.</span></span> <span data-ttu-id="ea457-395">Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo.</span><span class="sxs-lookup"><span data-stu-id="ea457-395">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="ea457-396">Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto.</span><span class="sxs-lookup"><span data-stu-id="ea457-396">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea457-397">Risultati variabile di test</span><span class="sxs-lookup"><span data-stu-id="ea457-397">Test variable outcomes</span></span></td>
<td><span data-ttu-id="ea457-398">Utilizzare questa pagina per impostare, modificare e visualizzare i possibili risultati di una variabile di test associata a un test qualitativo.</span><span class="sxs-lookup"><span data-stu-id="ea457-398">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="ea457-399">Per ogni risultato è possibile assegnare lo stato <strong>superato</strong> o <strong>non superato</strong>.</span><span class="sxs-lookup"><span data-stu-id="ea457-399">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="ea457-400">È necessario definire una variabile e i relativi risultati per un test qualitativo definito nella pagina <strong>Test</strong>.</span><span class="sxs-lookup"><span data-stu-id="ea457-400">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="ea457-401">Per i test qualitativi, il tipo di test è impostato su <strong>Opzione</strong> nella pagina <strong>Test</strong>. Utilizzare la pagina <strong>Gruppi di test</strong> per assegnare una variabile di test e il risultato predefinito a un singolo test qualitativo.</span><span class="sxs-lookup"><span data-stu-id="ea457-401">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="ea457-402">Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="ea457-402">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="ea457-403">Il test di ispezione ha diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="ea457-403">This inspection test has of several variables.</span></span> <span data-ttu-id="ea457-404">Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo.</span><span class="sxs-lookup"><span data-stu-id="ea457-404">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="ea457-405">Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto.</span><span class="sxs-lookup"><span data-stu-id="ea457-405">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="ea457-406">A ogni risultato viene assegnato lo stato <strong>superato</strong> o <strong>non superato</strong>.</span><span class="sxs-lookup"><span data-stu-id="ea457-406">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="ea457-407">Durante il test di ispezione per ogni variabile, l'ispettore indica il risultato del test selezionando uno dei risultati.</span><span class="sxs-lookup"><span data-stu-id="ea457-407">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="ea457-408">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ea457-408">Additional resources</span></span>
--------

[<span data-ttu-id="ea457-409">Processi di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="ea457-409">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="ea457-410">Gestione della non conformità</span><span class="sxs-lookup"><span data-stu-id="ea457-410">Nonconformance management</span></span>](enable-nonconformance-management.md)

[<span data-ttu-id="ea457-411">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="ea457-411">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)
