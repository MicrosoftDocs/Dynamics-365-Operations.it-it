---
title: Associazioni di controllo qualità
description: In questo argomento viene descritto come utilizzare le associazioni di controllo qualità in Microsoft Dynamics 365 Supply Chain Management per generare automaticamente ordini di controllo qualità relativi ai processi di vendita, acquisto e produzione.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f46f09dc9b67cfb04d0320a071c2c739266af58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956711"
---
# <a name="quality-associations"></a><span data-ttu-id="c915d-103">Associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c915d-103">Quality associations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c915d-104">In questo argomento viene descritto come utilizzare le associazioni di controllo qualità in Microsoft Dynamics 365 Supply Chain Management per generare automaticamente ordini di controllo qualità relativi ai processi di vendita, acquisto e produzione.</span><span class="sxs-lookup"><span data-stu-id="c915d-104">This topic describes how you can use quality associations in Microsoft Dynamics 365 Supply Chain Management to automatically generate quality orders that are related to your sales, purchase, and production processes.</span></span>

<span data-ttu-id="c915d-105">Un'associazione di controllo qualità definisce le seguenti informazioni per un ordine di controllo qualità generato:</span><span class="sxs-lookup"><span data-stu-id="c915d-105">A quality association defines all the following information for a quality order that is generated:</span></span>

- <span data-ttu-id="c915d-106">L'evento della transazione</span><span class="sxs-lookup"><span data-stu-id="c915d-106">The transaction event</span></span>
- <span data-ttu-id="c915d-107">Il set di test che devono essere eseguiti sugli articoli</span><span class="sxs-lookup"><span data-stu-id="c915d-107">The set of tests that must be performed on the items</span></span>
- <span data-ttu-id="c915d-108">Livello di qualità accettabile (AQL)</span><span class="sxs-lookup"><span data-stu-id="c915d-108">The acceptable quality level (AQL)</span></span>
- <span data-ttu-id="c915d-109">Il piano di campionamento</span><span class="sxs-lookup"><span data-stu-id="c915d-109">The sampling plan</span></span>

<span data-ttu-id="c915d-110">Occorre definire un'associazione di controllo qualità per ogni variazione in un processo aziendale che richieda la generazione automatica di un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c915d-110">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="c915d-111">Ad esempio, è possible generare un ordine di controllo qualità nei processi aziendali per ordini acquisto, ordini di quarantena, ordini cliente e ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="c915d-111">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="c915d-112">Utilizzo delle associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c915d-112">Working with quality associations</span></span>

<span data-ttu-id="c915d-113">Il processo aziendale che utilizza un'associazione di controllo qualità può essere correlato a diversi documenti di origine come ordini acquisto, ordini cliente o ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="c915d-113">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="c915d-114">Ciascun record di associazione di controllo qualità definisce il set di test, l'AQL e il piano di campionamento da applicare agli ordini di controllo qualità generati.</span><span class="sxs-lookup"><span data-stu-id="c915d-114">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="c915d-115">Un record di un'associazione di controllo qualità deve essere definito per ogni variazione in un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="c915d-115">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="c915d-116">Ad esempio, è possibile impostare un'associazione di controllo qualità che generi un ordine di controllo qualità quando si aggiorna l'entrata prodotti di un ordine acquisto.</span><span class="sxs-lookup"><span data-stu-id="c915d-116">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="c915d-117">A seconda della configurazione del piano di esecuzione, il processo di attivazione stesso può essere bloccato mentre c'è un ordine di controllo qualità aperto.</span><span class="sxs-lookup"><span data-stu-id="c915d-117">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order.</span></span> <span data-ttu-id="c915d-118">In alternativa, è possibile bloccare i processi successivi, come la fatturazione degli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="c915d-118">Alternatively, subsequent processes, such as purchase order invoicing, can be blocked.</span></span>

> [!NOTE]
> <span data-ttu-id="c915d-119">Mentre vi sono ordini di controllo qualità aperti, le quantità di inventario sono automaticamente bloccate.</span><span class="sxs-lookup"><span data-stu-id="c915d-119">While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="c915d-120">A seconda dell'impostazione di **Blocco completo** nella pagina **Campionamenti articoli**, la quantità è la quantità dell'ordine di controllo qualità o la quantità della riga di documento di origine.</span><span class="sxs-lookup"><span data-stu-id="c915d-120">Depending on the setting of the **Full blocking** field on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span> <span data-ttu-id="c915d-121">Per ulteriori informazioni, vedere [Campionamento degli articoli per la gestione della qualità](quality-item-sampling.md).</span><span class="sxs-lookup"><span data-stu-id="c915d-121">For more information, see [Quality management item sampling](quality-item-sampling.md).</span></span>

<span data-ttu-id="c915d-122">Per un processo aziendale specificato, il record di un'associazione di controllo qualità identifica l'evento e le condizioni per cui viene generato un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c915d-122">For a given business process, the quality association record identifies the event and conditions that a quality order is generated for.</span></span> <span data-ttu-id="c915d-123">Le condizioni possono essere specifiche a un sito o a una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="c915d-123">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="c915d-124">Un ordine di controllo qualità che prevede test distruttivi può essere generato solo quando sono disponibili delle scorte per l'evento.</span><span class="sxs-lookup"><span data-stu-id="c915d-124">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="c915d-125">Per lavorare con associazioni di controllo qualità, vai a **Gestione articoli \> Impostazioni \> Controllo qualità \> Associazioni di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="c915d-125">To work with quality associations, go to **Inventory management \> Setup \> Quality control \> Quality associations**.</span></span> <span data-ttu-id="c915d-126">Negli esempi riportati di seguito viene illustrata la modalità di definizione di un record di associazione di controllo qualità per le variazioni in ciascun processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="c915d-126">The following examples show how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="c915d-127">Per ciascun esempio, sono riepilogati nella seguente tabella gli eventi e le condizioni definiti da un record di associazione di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c915d-127">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c915d-128">Tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="c915d-128">Reference type</span></span></th>
<th><span data-ttu-id="c915d-129">Tipo di evento</span><span class="sxs-lookup"><span data-stu-id="c915d-129">Event type</span></span></th>
<th><span data-ttu-id="c915d-130">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="c915d-130">Execution</span></span></th>
<th><span data-ttu-id="c915d-131">Bloccaggio evento</span><span class="sxs-lookup"><span data-stu-id="c915d-131">Event blocking</span></span></th>
<th><span data-ttu-id="c915d-132">Riferimento documento</span><span class="sxs-lookup"><span data-stu-id="c915d-132">Document reference</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c915d-133">Inventario</span><span class="sxs-lookup"><span data-stu-id="c915d-133">Inventory</span></span></td>
<td><span data-ttu-id="c915d-134">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c915d-134">Not applicable</span></span></td>
<td><span data-ttu-id="c915d-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c915d-135">Not applicable</span></span></td>
<td><span data-ttu-id="c915d-136">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-136">None</span></span></td>
<td><span data-ttu-id="c915d-137">Tutti</span><span class="sxs-lookup"><span data-stu-id="c915d-137">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="c915d-138">Vendite</span><span class="sxs-lookup"><span data-stu-id="c915d-138">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="c915d-139">Il processo di prelievo è programmato</span><span class="sxs-lookup"><span data-stu-id="c915d-139">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="c915d-140">Prima</span><span class="sxs-lookup"><span data-stu-id="c915d-140">Before</span></span></td>
<td><span data-ttu-id="c915d-141">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-141">None</span></span></td>
<td rowspan="22"><span data-ttu-id="c915d-142">Solo ID specifico, Gruppo o Tutto</span><span class="sxs-lookup"><span data-stu-id="c915d-142">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-143">Processo di prelievo</span><span class="sxs-lookup"><span data-stu-id="c915d-143">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-144">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="c915d-144">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-145">Fattura</span><span class="sxs-lookup"><span data-stu-id="c915d-145">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="c915d-146">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="c915d-146">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-147">Prima</span><span class="sxs-lookup"><span data-stu-id="c915d-147">Before</span></span></td>
<td><span data-ttu-id="c915d-148">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-148">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-149">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="c915d-149">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-150">Fattura</span><span class="sxs-lookup"><span data-stu-id="c915d-150">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="c915d-151">Acquisto</span><span class="sxs-lookup"><span data-stu-id="c915d-151">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="c915d-152">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="c915d-152">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="c915d-153">Prima</span><span class="sxs-lookup"><span data-stu-id="c915d-153">Before</span></span></td>
<td><span data-ttu-id="c915d-154">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-154">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-155">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="c915d-155">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-156">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="c915d-156">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-157">Fattura</span><span class="sxs-lookup"><span data-stu-id="c915d-157">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="c915d-158">Dopo</span><span class="sxs-lookup"><span data-stu-id="c915d-158">After</span></span></td>
<td><span data-ttu-id="c915d-159">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-160">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="c915d-160">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-161">Fattura</span><span class="sxs-lookup"><span data-stu-id="c915d-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="c915d-162">Registrazione</span><span class="sxs-lookup"><span data-stu-id="c915d-162">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-163">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c915d-163">Not applicable</span></span></td>
<td><span data-ttu-id="c915d-164">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-164">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-165">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="c915d-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-166">Fattura</span><span class="sxs-lookup"><span data-stu-id="c915d-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="c915d-167">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="c915d-167">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-168">Prima</span><span class="sxs-lookup"><span data-stu-id="c915d-168">Before</span></span></td>
<td><span data-ttu-id="c915d-169">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-169">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-170">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="c915d-170">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-171">Fattura</span><span class="sxs-lookup"><span data-stu-id="c915d-171">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="c915d-172">Dopo</span><span class="sxs-lookup"><span data-stu-id="c915d-172">After</span></span></td>
<td><span data-ttu-id="c915d-173">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-174">Fattura</span><span class="sxs-lookup"><span data-stu-id="c915d-174">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="c915d-175">Produzione</span><span class="sxs-lookup"><span data-stu-id="c915d-175">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-176">Registrazione</span><span class="sxs-lookup"><span data-stu-id="c915d-176">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-177">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c915d-177">Not applicable</span></span></td>
<td><span data-ttu-id="c915d-178">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-178">None</span></span></td>
<td rowspan="12"><span data-ttu-id="c915d-179">Tutti</span><span class="sxs-lookup"><span data-stu-id="c915d-179">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-180">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="c915d-180">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-181">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="c915d-181">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="c915d-182">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="c915d-182">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-183">Prima</span><span class="sxs-lookup"><span data-stu-id="c915d-183">Before</span></span></td>
<td><span data-ttu-id="c915d-184">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-185">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="c915d-185">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-186">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="c915d-186">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="c915d-187">Dopo</span><span class="sxs-lookup"><span data-stu-id="c915d-187">After</span></span></td>
<td><span data-ttu-id="c915d-188">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-188">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-189">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="c915d-189">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="c915d-190">Quarantena</span><span class="sxs-lookup"><span data-stu-id="c915d-190">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-191">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="c915d-191">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="c915d-192">Prima</span><span class="sxs-lookup"><span data-stu-id="c915d-192">Before</span></span></td>
<td><span data-ttu-id="c915d-193">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="c915d-193">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-194">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="c915d-194">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-195">Dopo</span><span class="sxs-lookup"><span data-stu-id="c915d-195">After</span></span></td>
<td><span data-ttu-id="c915d-196">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="c915d-196">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-197">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="c915d-197">End</span></span></td>
<td><span data-ttu-id="c915d-198">Prima</span><span class="sxs-lookup"><span data-stu-id="c915d-198">Before</span></span></td>
<td><span data-ttu-id="c915d-199">Fine periodo</span><span class="sxs-lookup"><span data-stu-id="c915d-199">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="c915d-200">Operazione ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="c915d-200">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-201">Dichiarazione di finito</span><span class="sxs-lookup"><span data-stu-id="c915d-201">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="c915d-202">Prima di</span><span class="sxs-lookup"><span data-stu-id="c915d-202">Before</span></span></td>
<td><span data-ttu-id="c915d-203">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="c915d-203">None</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-204">ID specifico, Gruppo o Tutti e Specifico risorsa, Gruppo o Tutti</span><span class="sxs-lookup"><span data-stu-id="c915d-204">Specific ID, Group, or All, and specific Resource, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-205">Dichiarazione di finito</span><span class="sxs-lookup"><span data-stu-id="c915d-205">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-206">Dopo</span><span class="sxs-lookup"><span data-stu-id="c915d-206">After</span></span></td>
<td><span data-ttu-id="c915d-207">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="c915d-207">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="c915d-208">Produzione co-prodotti</span><span class="sxs-lookup"><span data-stu-id="c915d-208">Co-product production</span></span></td>
<td><span data-ttu-id="c915d-209">Registrazione</span><span class="sxs-lookup"><span data-stu-id="c915d-209">Registration</span></span></td>
<td><span data-ttu-id="c915d-210">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c915d-210">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-211">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="c915d-211">None</span></span></td>
<td rowspan="3"><span data-ttu-id="c915d-212">Tutti</span><span class="sxs-lookup"><span data-stu-id="c915d-212">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="c915d-213">Dichiarazione di finito</span><span class="sxs-lookup"><span data-stu-id="c915d-213">Report as finished</span></span></td>
<td><span data-ttu-id="c915d-214">Prima di</span><span class="sxs-lookup"><span data-stu-id="c915d-214">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-215">Dopo</span><span class="sxs-lookup"><span data-stu-id="c915d-215">After</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c915d-216">La funzionalità *Gestione qualità per i processi di magazzino* aggiunge funzionalità per l'elaborazione degli ordini di controllo qualità per la produzione con **Tipo di evento** impostato su *Dichiarato finito* e **Esecuzione** impostato su *Dopo* e per acquisti con **Tipo di evento** impostato su *Registrazione*.</span><span class="sxs-lookup"><span data-stu-id="c915d-216">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production where the **Event type** field is set to *Report as finished* and the **Execution** field is set to *After*, and for purchases where the **Event type** field is set to *Registration*.</span></span> <span data-ttu-id="c915d-217">Per ulteriori informazioni, vedere [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="c915d-217">For more information, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

<span data-ttu-id="c915d-218">Nella tabella seguente vengono fornite ulteriori informazioni sulla modalità di generazione di ordini di controllo qualità per tipi specifici di processo.</span><span class="sxs-lookup"><span data-stu-id="c915d-218">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>

<div class="tableSection">
<table>
<thead>
<tr>
<th><span data-ttu-id="c915d-219">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="c915d-219">Type of process</span></span></th>
<th><span data-ttu-id="c915d-220">Quando gli ordini di controllo qualità possono essere generati automaticamente</span><span class="sxs-lookup"><span data-stu-id="c915d-220">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="c915d-221">Quando gli ordini di controllo qualità possono essere generati se il test distruttivo è obbligatorio</span><span class="sxs-lookup"><span data-stu-id="c915d-221">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="c915d-222">Informazioni sulle condizioni</span><span class="sxs-lookup"><span data-stu-id="c915d-222">Condition information</span></span></th>
<th><span data-ttu-id="c915d-223">Informazioni sulla generazione manuale</span><span class="sxs-lookup"><span data-stu-id="c915d-223">Manual generation information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c915d-224">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="c915d-224">Purchase order</span></span></td>
<td><span data-ttu-id="c915d-225">Prima o dopo la registrazione di un elenco di entrate o un'entrata prodotti per il materiale ricevuta</span><span class="sxs-lookup"><span data-stu-id="c915d-225">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="c915d-226">Dopo che l'entrata prodotti per il materiale ricevuto viene registrata, poiché il materiale deve essere disponibile per il test distruttivo</span><span class="sxs-lookup"><span data-stu-id="c915d-226">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="c915d-227">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="c915d-227">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="c915d-228">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine fornitore può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="c915d-228">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-229">Ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="c915d-229">Quarantine order</span></span></td>
<td><span data-ttu-id="c915d-230">Prima o dopo che l'ordine di quarantena viene dichiarato finito o completato</span><span class="sxs-lookup"><span data-stu-id="c915d-230">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="c915d-231">Gli ordini di controllo qualità che richiedono i test distruttivi non possono essere generati.</span><span class="sxs-lookup"><span data-stu-id="c915d-231">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="c915d-232">Si presume che la funzionalità di ordine di quarantena gestisca lo smaltimento del materiale distrutto.</span><span class="sxs-lookup"><span data-stu-id="c915d-232">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="c915d-233">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="c915d-233">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="c915d-234">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di quarantena può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="c915d-234">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-235">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="c915d-235">Sales order</span></span></td>
<td><span data-ttu-id="c915d-236">Prima di un processo di prelievo o un aggiornamento del documento di trasporto per gli articoli in spedizione</span><span class="sxs-lookup"><span data-stu-id="c915d-236">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="c915d-237">In qualsiasi fase</span><span class="sxs-lookup"><span data-stu-id="c915d-237">At any step</span></span></td>
<td><span data-ttu-id="c915d-238">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un cliente specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="c915d-238">The requirement for a quality order can reflect a specific site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="c915d-239">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine cliente può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="c915d-239">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-240">Ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c915d-240">Production order</span></span></td>
<td><span data-ttu-id="c915d-241">Prima o dopo la registrazione della quantità finita per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c915d-241">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="c915d-242">Dopo la registrazione della quantità finita per l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c915d-242">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="c915d-243">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo specifico o una combinazione di questi.</span><span class="sxs-lookup"><span data-stu-id="c915d-243">The requirement for a quality order can reflect a specific site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="c915d-244">Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di produzione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="c915d-244">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-245">Ordine di produzione che ha un'operazione del ciclo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="c915d-245">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="c915d-246">Prima o dopo che il report venga completato per un'operazione</span><span class="sxs-lookup"><span data-stu-id="c915d-246">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="c915d-247">Dopo la dichiarazione della fine dell'ultima operazione di produzione</span><span class="sxs-lookup"><span data-stu-id="c915d-247">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="c915d-248">La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o una risorsa operativa specifica o una combinazione di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="c915d-248">The requirement for a quality order can reflect a specific site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="c915d-249">Un ordine di controllo qualità generato manualmente che si riferisce a un'operazione del ciclo di lavorazione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</span><span class="sxs-lookup"><span data-stu-id="c915d-249">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c915d-250">Scorte</span><span class="sxs-lookup"><span data-stu-id="c915d-250">Inventory</span></span></td>
<td><span data-ttu-id="c915d-251">Un ordine di controllo qualità non può essere generato automaticamente per una transazione in un giornale di registrazione magazzino o per le transazioni degli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="c915d-251">A quality order can't be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="c915d-252">Un ordine di controllo qualità deve essere creato manualmente per la quantità in magazzino di un articolo.</span><span class="sxs-lookup"><span data-stu-id="c915d-252">A quality order must be manually created for an item's inventory quantity.</span></span> <span data-ttu-id="c915d-253">Scorte fisiche disponibili è un campo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c915d-253">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a><span data-ttu-id="c915d-254">Esempi di generazione automatica di ordini di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="c915d-254">Examples of automatic generation of quality orders</span></span>

### <a name="purchasing"></a><span data-ttu-id="c915d-255">Acquisto</span><span class="sxs-lookup"><span data-stu-id="c915d-255">Purchasing</span></span>

<span data-ttu-id="c915d-256">Se durante l'acquisto, si imposta il campo **Tipo di evento** su *Entrata prodotti* e il campo **Esecuzione** su *Dopo* nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="c915d-256">In purchasing, if you set the **Event type** field to *Product receipt* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="c915d-257">Se l'opzione **Per quantità aggiornata** è impostata su *Sì*, viene generato un ordine di controllo qualità per ogni entrata dell'ordine fornitore, in base alla quantità ricevuta e alle impostazioni nel campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="c915d-257">If the **Per updated quantity** option is set to *Yes*, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="c915d-258">Ogni volta che una quantità viene ricevuta per l'ordine fornitore, nuovi ordini di controllo qualità vengono generati in base alla quantità ricevuta.</span><span class="sxs-lookup"><span data-stu-id="c915d-258">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="c915d-259">Se l'opzione **Per quantità aggiornata** è impostata su *No*, viene generato un ordine di controllo qualità per la prima entrata dell'ordine fornitore, in base alla quantità ricevuta.</span><span class="sxs-lookup"><span data-stu-id="c915d-259">If the **Per updated quantity** option is set to *No*, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="c915d-260">Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="c915d-260">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="c915d-261">Gli ordini di controllo qualità non vengono generati per le entrate successive dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="c915d-261">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="c915d-262">Produzione</span><span class="sxs-lookup"><span data-stu-id="c915d-262">Production</span></span>

<span data-ttu-id="c915d-263">Se durante la produzione, si imposta il campo **Tipo di evento** su *Dichiarato finito* e il campo **Esecuzione** su *Dopo* nella pagina **Associazioni di controllo qualità**, saranno disponibili i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="c915d-263">In production, if you set the **Event type** field to *Report as finished* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="c915d-264">Se l'opzione **Per quantità aggiornata** è impostata su *Sì*, viene generato un ordine di controllo qualità in base a ogni quantità finita e alle impostazioni nel campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="c915d-264">If the **Per updated quantity** option is set to *Yes*, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="c915d-265">Ogni volta che una quantità viene dichiarata come finita per l'ordine di produzione, nuovi ordini di controllo qualità vengono generati in base alla quantità finita.</span><span class="sxs-lookup"><span data-stu-id="c915d-265">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on the newly finished quantity.</span></span> <span data-ttu-id="c915d-266">La logica di generazione è coerente con l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="c915d-266">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="c915d-267">Se l'opzione **Per quantità aggiornata** è impostata su *No*, viene generato un ordine di controllo qualità la prima volta che una quantità viene dichiarata come finita, in base alla quantità finita.</span><span class="sxs-lookup"><span data-stu-id="c915d-267">If the **Per updated quantity** option is set to *No*, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="c915d-268">Inoltre, uno o più ordini di controllo qualità vengono creati in base alla quantità rimanente e alle dimensioni di tracciabilità del campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="c915d-268">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="c915d-269">Gli ordini di controllo qualità non vengono generati per le successive quantità finite.</span><span class="sxs-lookup"><span data-stu-id="c915d-269">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c915d-270">Specifica qualità</span><span class="sxs-lookup"><span data-stu-id="c915d-270">Quality specification</span></span></th>
<th><span data-ttu-id="c915d-271">Per quantità aggiornata</span><span class="sxs-lookup"><span data-stu-id="c915d-271">Per updated quantity</span></span></th>
<th><span data-ttu-id="c915d-272">Per dimensione di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="c915d-272">Per tracking dimension</span></span></th>
<th><span data-ttu-id="c915d-273">Risultato</span><span class="sxs-lookup"><span data-stu-id="c915d-273">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c915d-274">Percentuale: 10%</span><span class="sxs-lookup"><span data-stu-id="c915d-274">Percentage: 10%</span></span></td>
<td><span data-ttu-id="c915d-275">Sì</span><span class="sxs-lookup"><span data-stu-id="c915d-275">Yes</span></span></td>
<td>
<p><span data-ttu-id="c915d-276">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="c915d-276">Batch number: No</span></span></p>
<p><span data-ttu-id="c915d-277">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="c915d-277">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="c915d-278">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="c915d-278">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="c915d-279">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="c915d-279">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="c915d-280">Ordine di controllo qualità 1 per 3 (10% di 30)</span><span class="sxs-lookup"><span data-stu-id="c915d-280">Quality order 1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c915d-281">Dichiarazione di finito per 70</span><span class="sxs-lookup"><span data-stu-id="c915d-281">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="c915d-282">Ordine di controllo qualità 2 per 7 (10% della quantità rimanente dell'ordine, che equivale a 70 in questo caso)</span><span class="sxs-lookup"><span data-stu-id="c915d-282">Quality order 2 for 7 (10% of the remaining order quantity, which is 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="c915d-283">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="c915d-283">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="c915d-284">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-284">No</span></span></td>
<td>
<p><span data-ttu-id="c915d-285">Numero batch: No</span><span class="sxs-lookup"><span data-stu-id="c915d-285">Batch number: No</span></span></p>
<p><span data-ttu-id="c915d-286">Numero di serie: No</span><span class="sxs-lookup"><span data-stu-id="c915d-286">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="c915d-287">Quantità ordine: 100</span><span class="sxs-lookup"><span data-stu-id="c915d-287">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="c915d-288">Dichiarazione di finito per 30</span><span class="sxs-lookup"><span data-stu-id="c915d-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="c915d-289">L'ordine di controllo qualità 1 per 1 (per la prima quantità dichiarata finita, con un valore fisso di 1)</span><span class="sxs-lookup"><span data-stu-id="c915d-289">Quality order 1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="c915d-290">L'ordine di controllo qualità 2 per 1 (per la quantità rimanente che ha ancora un valore fisso di 1)</span><span class="sxs-lookup"><span data-stu-id="c915d-290">Quality order 2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c915d-291">Dichiarazione di finito per 10</span><span class="sxs-lookup"><span data-stu-id="c915d-291">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="c915d-292">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="c915d-292">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c915d-293">Dichiarazione di finito per 60</span><span class="sxs-lookup"><span data-stu-id="c915d-293">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="c915d-294">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="c915d-294">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="c915d-295">Quantità fissa: 1</span><span class="sxs-lookup"><span data-stu-id="c915d-295">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="c915d-296">Sì</span><span class="sxs-lookup"><span data-stu-id="c915d-296">Yes</span></span></td>
<td>
<p><span data-ttu-id="c915d-297">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="c915d-297">Batch number: Yes</span></span></p>
<p><span data-ttu-id="c915d-298">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="c915d-298">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="c915d-299">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="c915d-299">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="c915d-300">Dichiara come finito per 3: 1 per il numero di lotto b1, numero di serie s1; 1 per numero di lotto b2, numero di serie s2; e 1 per il numero di lotto b3, numero di serie s3</span><span class="sxs-lookup"><span data-stu-id="c915d-300">Report as finished for 3: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; and 1 for batch number b3, serial number s3</span></span>
<ul>
<li><span data-ttu-id="c915d-301">Ordine di controllo qualità 1 per 1 del numero di lotto b1, numero di serie s1</span><span class="sxs-lookup"><span data-stu-id="c915d-301">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="c915d-302">Ordine di controllo qualità 2 per 1 del numero di lotto b2, numero di serie s2</span><span class="sxs-lookup"><span data-stu-id="c915d-302">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="c915d-303">Ordine di controllo qualità 3 per 1 del numero di lotto b3, numero di serie s3</span><span class="sxs-lookup"><span data-stu-id="c915d-303">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c915d-304">Dichiara come finito per 2: 1 per il numero di lotto b4, numero di serie s4; e 1 per il numero di lotto b5, numero di serie s5</span><span class="sxs-lookup"><span data-stu-id="c915d-304">Report as finished for 2: 1 for batch number b4, serial number s4; and 1 for batch number b5, serial number s5</span></span>
<ul>
<li><span data-ttu-id="c915d-305">Ordine di controllo qualità 4 per 1 del numero di lotto b4, numero di serie s4</span><span class="sxs-lookup"><span data-stu-id="c915d-305">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
<li><span data-ttu-id="c915d-306">Ordine di controllo qualità 5 per 1 del numero di lotto b5, numero di serie s5</span><span class="sxs-lookup"><span data-stu-id="c915d-306">Quality order 5 for 1 of batch number b5, serial number s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="c915d-307"><strong>Nota:</strong> il batch può essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c915d-307"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="c915d-308">Quantità fissa: 2</span><span class="sxs-lookup"><span data-stu-id="c915d-308">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="c915d-309">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c915d-309">No</span></span></td>
<td>
<p><span data-ttu-id="c915d-310">Numero batch: Sì</span><span class="sxs-lookup"><span data-stu-id="c915d-310">Batch number: Yes</span></span></p>
<p><span data-ttu-id="c915d-311">Numero di serie: Sì</span><span class="sxs-lookup"><span data-stu-id="c915d-311">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="c915d-312">Quantità ordine: 10</span><span class="sxs-lookup"><span data-stu-id="c915d-312">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="c915d-313">Dichiara come finito per 4: 1 per il numero di lotto b1, numero di serie s1; 1 per numero di lotto b2, numero di serie s2; 1 per il numero di lotto b3, numero di serie s3: e 1 per il numero di lotto b4, numero di serie s4</span><span class="sxs-lookup"><span data-stu-id="c915d-313">Report as finished for 4: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; 1 for batch number b3, serial number s3; and 1 for batch number b4, serial number s4</span></span>
<ul>
<li><span data-ttu-id="c915d-314">Ordine di controllo qualità 1 per 1 del numero di lotto b1, numero di serie s1</span><span class="sxs-lookup"><span data-stu-id="c915d-314">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="c915d-315">Ordine di controllo qualità 2 per 1 del numero di lotto b2, numero di serie s2</span><span class="sxs-lookup"><span data-stu-id="c915d-315">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="c915d-316">Ordine di controllo qualità 3 per 1 del numero di lotto b3, numero di serie s3</span><span class="sxs-lookup"><span data-stu-id="c915d-316">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
<li><span data-ttu-id="c915d-317">Ordine di controllo qualità 4 per 1 del numero di lotto b4, numero di serie s4</span><span class="sxs-lookup"><span data-stu-id="c915d-317">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="c915d-318">Ordine di controllo qualità 5 per 2, senza riferimento a un numero di lotto o un numero di serie</span><span class="sxs-lookup"><span data-stu-id="c915d-318">Quality order 5 for 2, without a reference to a batch number and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="c915d-319">Dichiara come finito per 6: 1 per il numero di lotto b5, numero di serie s5; 1 per numero di lotto b6, numero di serie s6; 1 per il numero di lotto b7, numero di serie s7; 1 per il numero di lotto b8, numero di serie s8; 1 per il numero di lotto b9, numero di serie s9: e 1 per il numero di lotto b10, numero di serie s10</span><span class="sxs-lookup"><span data-stu-id="c915d-319">Report as finished for 6: 1 for batch number b5, serial number s5; 1 for batch number b6, serial number s6; 1 for batch number b7, serial number s7; 1 for batch number b8, serial number s8; 1 for batch number b9, serial number s9; and 1 for batch number b10, serial number s10</span></span>
<ul>
<li><span data-ttu-id="c915d-320">Nessun ordine di controllo qualità viene creato.</span><span class="sxs-lookup"><span data-stu-id="c915d-320">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="c915d-321">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c915d-321">Additional resources</span></span>

- [<span data-ttu-id="c915d-322">Processi di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="c915d-322">Quality management processes</span></span>](quality-management-processes.md)
- [<span data-ttu-id="c915d-323">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="c915d-323">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="c915d-324">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="c915d-324">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
