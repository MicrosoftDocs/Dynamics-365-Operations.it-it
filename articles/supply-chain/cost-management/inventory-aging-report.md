---
title: Esempi e logica dei report di aging delle scorte
description: Questo argomento presenta alcuni esempi che mostrano come interpretare i risultati di un report di aging delle scorte.
author: RichardLuan
manager: AnnBe
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6c165599c11b84e4064a9303d8b1f59558fc6b9d
ms.sourcegitcommit: 6bf8602333191e5161ba3a9ceecf160c85ff7e79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "3484532"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="12dd9-103">Esempi e logica dei report di aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="12dd9-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12dd9-104">Questo argomento presenta alcuni esempi che mostrano come interpretare i risultati di un report di **aging delle scorte**.</span><span class="sxs-lookup"><span data-stu-id="12dd9-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="12dd9-105">Questo report classifica i valori delle quantità e delle scorte disponibili per un articolo o un gruppo di articoli selezionati in diversi gruppi di periodi.</span><span class="sxs-lookup"><span data-stu-id="12dd9-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="12dd9-106">Questo argomento mostra anche la logica interna del report.</span><span class="sxs-lookup"><span data-stu-id="12dd9-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="12dd9-107">Gli esempi in questo argomento mostrano i risultati presentati su un report **di aging delle scorte** standard.</span><span class="sxs-lookup"><span data-stu-id="12dd9-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="12dd9-108">Tuttavia, in generale, si consiglia di utilizzare la versione [Archiviazione report di aging delle scorte](inventory-aging-report-storage.md) di questo report, soprattutto quando si hanno molti articoli e magazzini da elaborare.</span><span class="sxs-lookup"><span data-stu-id="12dd9-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="12dd9-109">L'archiviazione report di aging delle scorte salva ogni report generato, mostra i risultati come una pagina interattiva e un grafico e consente di esportare qualsiasi rapporto salvato.</span><span class="sxs-lookup"><span data-stu-id="12dd9-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="12dd9-110">Dati di esempio utilizzati in questi esempi</span><span class="sxs-lookup"><span data-stu-id="12dd9-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="12dd9-111">Gli esempi in questo argomento si basano sui dati di transazione delle scorte di esempio descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="12dd9-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="12dd9-112">Configurazione delle dimensioni di immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="12dd9-112">Storage dimension setup</span></span>

<span data-ttu-id="12dd9-113">Il sistema di esempio contiene la seguente configurazione delle dimensioni di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="12dd9-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="12dd9-114">Nome</span><span class="sxs-lookup"><span data-stu-id="12dd9-114">Name</span></span>      | <span data-ttu-id="12dd9-115">Attive</span><span class="sxs-lookup"><span data-stu-id="12dd9-115">Active</span></span> | <span data-ttu-id="12dd9-116">Inventario fisico</span><span class="sxs-lookup"><span data-stu-id="12dd9-116">Physical inventory</span></span> | <span data-ttu-id="12dd9-117">Inventario finanziario</span><span class="sxs-lookup"><span data-stu-id="12dd9-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="12dd9-118">Sito</span><span class="sxs-lookup"><span data-stu-id="12dd9-118">Site</span></span>      | <span data-ttu-id="12dd9-119">Sì</span><span class="sxs-lookup"><span data-stu-id="12dd9-119">Yes</span></span>    | <span data-ttu-id="12dd9-120">Sì</span><span class="sxs-lookup"><span data-stu-id="12dd9-120">Yes</span></span>                | <span data-ttu-id="12dd9-121">Sì</span><span class="sxs-lookup"><span data-stu-id="12dd9-121">Yes</span></span>                 |
| <span data-ttu-id="12dd9-122">Magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-122">Warehouse</span></span> | <span data-ttu-id="12dd9-123">Sì</span><span class="sxs-lookup"><span data-stu-id="12dd9-123">Yes</span></span>    | <span data-ttu-id="12dd9-124">Sì</span><span class="sxs-lookup"><span data-stu-id="12dd9-124">Yes</span></span>                | <span data-ttu-id="12dd9-125">Nessuna</span><span class="sxs-lookup"><span data-stu-id="12dd9-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="12dd9-126">Modello inventariale</span><span class="sxs-lookup"><span data-stu-id="12dd9-126">Inventory model</span></span>

<span data-ttu-id="12dd9-127">Per il sistema di esempio, il modello inventariale per i prodotti rilasciati è *FIFO* e l'impostazione **Prezzo di costo** per il modello inventariale è *Includi valore fisico*.</span><span class="sxs-lookup"><span data-stu-id="12dd9-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="12dd9-128">Operazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-128">Inventory transactions</span></span>

<span data-ttu-id="12dd9-129">Il sistema di esempio contiene le seguenti transazioni di inventario per un prodotto rilasciato con il numero di articolo *1.000*.</span><span class="sxs-lookup"><span data-stu-id="12dd9-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="12dd9-130">Riferimento</span><span class="sxs-lookup"><span data-stu-id="12dd9-130">Reference</span></span>      | <span data-ttu-id="12dd9-131">Sito</span><span class="sxs-lookup"><span data-stu-id="12dd9-131">Site</span></span> | <span data-ttu-id="12dd9-132">Magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-132">Warehouse</span></span> | <span data-ttu-id="12dd9-133">Ricevimento</span><span class="sxs-lookup"><span data-stu-id="12dd9-133">Receipt</span></span>   | <span data-ttu-id="12dd9-134">Uscita</span><span class="sxs-lookup"><span data-stu-id="12dd9-134">Issue</span></span> | <span data-ttu-id="12dd9-135">Data effettiva</span><span class="sxs-lookup"><span data-stu-id="12dd9-135">Physical date</span></span> | <span data-ttu-id="12dd9-136">Data finanziaria</span><span class="sxs-lookup"><span data-stu-id="12dd9-136">Financial date</span></span> | <span data-ttu-id="12dd9-137">Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-137">Quantity</span></span> | <span data-ttu-id="12dd9-138">Importo costo</span><span class="sxs-lookup"><span data-stu-id="12dd9-138">Cost amount</span></span> | <span data-ttu-id="12dd9-139">Importo costi fisico</span><span class="sxs-lookup"><span data-stu-id="12dd9-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="12dd9-140">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="12dd9-140">Purchase order</span></span> | <span data-ttu-id="12dd9-141">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-141">1</span></span>    | <span data-ttu-id="12dd9-142">11</span><span class="sxs-lookup"><span data-stu-id="12dd9-142">11</span></span>        | <span data-ttu-id="12dd9-143">Acquistato</span><span class="sxs-lookup"><span data-stu-id="12dd9-143">Purchased</span></span> |       | <span data-ttu-id="12dd9-144">15 marzo</span><span class="sxs-lookup"><span data-stu-id="12dd9-144">March 15</span></span>      | <span data-ttu-id="12dd9-145">15 marzo</span><span class="sxs-lookup"><span data-stu-id="12dd9-145">March 15</span></span>       | <span data-ttu-id="12dd9-146">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-146">10</span></span>       | <span data-ttu-id="12dd9-147">1.000</span><span class="sxs-lookup"><span data-stu-id="12dd9-147">1,000</span></span>       | <span data-ttu-id="12dd9-148">1.000</span><span class="sxs-lookup"><span data-stu-id="12dd9-148">1,000</span></span>                |
| <span data-ttu-id="12dd9-149">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="12dd9-149">Purchase order</span></span> | <span data-ttu-id="12dd9-150">2</span><span class="sxs-lookup"><span data-stu-id="12dd9-150">2</span></span>    | <span data-ttu-id="12dd9-151">21</span><span class="sxs-lookup"><span data-stu-id="12dd9-151">21</span></span>        | <span data-ttu-id="12dd9-152">Acquistato</span><span class="sxs-lookup"><span data-stu-id="12dd9-152">Purchased</span></span> |       | <span data-ttu-id="12dd9-153">15 marzo</span><span class="sxs-lookup"><span data-stu-id="12dd9-153">March 15</span></span>      | <span data-ttu-id="12dd9-154">15 marzo</span><span class="sxs-lookup"><span data-stu-id="12dd9-154">March 15</span></span>       | <span data-ttu-id="12dd9-155">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-155">10</span></span>       | <span data-ttu-id="12dd9-156">2,000</span><span class="sxs-lookup"><span data-stu-id="12dd9-156">2,000</span></span>       | <span data-ttu-id="12dd9-157">2,000</span><span class="sxs-lookup"><span data-stu-id="12dd9-157">2,000</span></span>                |
| <span data-ttu-id="12dd9-158">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="12dd9-158">Purchase order</span></span> | <span data-ttu-id="12dd9-159">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-159">1</span></span>    | <span data-ttu-id="12dd9-160">11</span><span class="sxs-lookup"><span data-stu-id="12dd9-160">11</span></span>        | <span data-ttu-id="12dd9-161">Ricevuti</span><span class="sxs-lookup"><span data-stu-id="12dd9-161">Received</span></span>  |       | <span data-ttu-id="12dd9-162">15 aprile</span><span class="sxs-lookup"><span data-stu-id="12dd9-162">April 15</span></span>      |                | <span data-ttu-id="12dd9-163">5</span><span class="sxs-lookup"><span data-stu-id="12dd9-163">5</span></span>        |             | <span data-ttu-id="12dd9-164">375</span><span class="sxs-lookup"><span data-stu-id="12dd9-164">375</span></span>                  |
| <span data-ttu-id="12dd9-165">Ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="12dd9-165">Transfer order</span></span> | <span data-ttu-id="12dd9-166">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-166">1</span></span>    | <span data-ttu-id="12dd9-167">11</span><span class="sxs-lookup"><span data-stu-id="12dd9-167">11</span></span>        |           | <span data-ttu-id="12dd9-168">Venduto</span><span class="sxs-lookup"><span data-stu-id="12dd9-168">Sold</span></span>  | <span data-ttu-id="12dd9-169">2° maggio</span><span class="sxs-lookup"><span data-stu-id="12dd9-169">May 2</span></span>         | <span data-ttu-id="12dd9-170">2° maggio</span><span class="sxs-lookup"><span data-stu-id="12dd9-170">May 2</span></span>          | <span data-ttu-id="12dd9-171">-5</span><span class="sxs-lookup"><span data-stu-id="12dd9-171">-5</span></span>       | <span data-ttu-id="12dd9-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="12dd9-172">-458.33</span></span>     | <span data-ttu-id="12dd9-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="12dd9-173">-458.33</span></span>              |
| <span data-ttu-id="12dd9-174">Ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="12dd9-174">Transfer order</span></span> | <span data-ttu-id="12dd9-175">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-175">1</span></span>    | <span data-ttu-id="12dd9-176">12</span><span class="sxs-lookup"><span data-stu-id="12dd9-176">12</span></span>        | <span data-ttu-id="12dd9-177">Acquistato</span><span class="sxs-lookup"><span data-stu-id="12dd9-177">Purchased</span></span> |       | <span data-ttu-id="12dd9-178">2° maggio</span><span class="sxs-lookup"><span data-stu-id="12dd9-178">May 2</span></span>         | <span data-ttu-id="12dd9-179">2° maggio</span><span class="sxs-lookup"><span data-stu-id="12dd9-179">May 2</span></span>          | <span data-ttu-id="12dd9-180">5</span><span class="sxs-lookup"><span data-stu-id="12dd9-180">5</span></span>        | <span data-ttu-id="12dd9-181">458.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-181">458.33</span></span>      | <span data-ttu-id="12dd9-182">458.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-182">458.33</span></span>               |
| <span data-ttu-id="12dd9-183">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="12dd9-183">Sales order</span></span>    | <span data-ttu-id="12dd9-184">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-184">1</span></span>    | <span data-ttu-id="12dd9-185">12</span><span class="sxs-lookup"><span data-stu-id="12dd9-185">12</span></span>        |           | <span data-ttu-id="12dd9-186">Venduto</span><span class="sxs-lookup"><span data-stu-id="12dd9-186">Sold</span></span>  | <span data-ttu-id="12dd9-187">3° maggio</span><span class="sxs-lookup"><span data-stu-id="12dd9-187">May 3</span></span>         | <span data-ttu-id="12dd9-188">3° maggio</span><span class="sxs-lookup"><span data-stu-id="12dd9-188">May 3</span></span>          | <span data-ttu-id="12dd9-189">-1</span><span class="sxs-lookup"><span data-stu-id="12dd9-189">-1</span></span>       | <span data-ttu-id="12dd9-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="12dd9-190">-91.67</span></span>      | <span data-ttu-id="12dd9-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="12dd9-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="12dd9-192">Come vengono calcolate le quantità e gli importi in ciascun intervallo di periodi</span><span class="sxs-lookup"><span data-stu-id="12dd9-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="12dd9-193">Utilizzando i dati di esempio descritti nelle sezioni precedenti, puoi eseguire un report **di aging delle scorte** con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="12dd9-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="12dd9-194">**Alla data:** *9 maggio 2020*</span><span class="sxs-lookup"><span data-stu-id="12dd9-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="12dd9-195">**Sito:** *Visualizza*</span><span class="sxs-lookup"><span data-stu-id="12dd9-195">**Site:** *View*</span></span>
- <span data-ttu-id="12dd9-196">**Magazzino:** *No*</span><span class="sxs-lookup"><span data-stu-id="12dd9-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="12dd9-197">**Numero articolo:** *Totale*</span><span class="sxs-lookup"><span data-stu-id="12dd9-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="12dd9-198">**Periodo di aging:** imposta questo campo per generare bucket mensili.</span><span class="sxs-lookup"><span data-stu-id="12dd9-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="12dd9-199">In questo caso, il contenuto del report generato sarà simile al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="12dd9-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="12dd9-200">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="12dd9-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-201">Sito</span><span class="sxs-lookup"><span data-stu-id="12dd9-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-202">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="12dd9-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-203">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="12dd9-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-204">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-205">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-206">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="12dd9-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-208">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="12dd9-210">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-211">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="12dd9-212">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-213">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="12dd9-214">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-215">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="12dd9-216">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-216">1000</span></span></td>
    <td><span data-ttu-id="12dd9-217">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-217">1</span></span></td>
    <td><span data-ttu-id="12dd9-218">14</span><span class="sxs-lookup"><span data-stu-id="12dd9-218">14</span></span></td>
    <td><span data-ttu-id="12dd9-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-219">1,283.33</span></span></td>
    <td><span data-ttu-id="12dd9-220">14</span><span class="sxs-lookup"><span data-stu-id="12dd9-220">14</span></span></td>
    <td><span data-ttu-id="12dd9-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-221">1,283.33</span></span></td>
    <td><span data-ttu-id="12dd9-222">91.67</span><span class="sxs-lookup"><span data-stu-id="12dd9-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-223">5.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-223">5.00</span></span></td>
    <td><span data-ttu-id="12dd9-224">458.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-224">458.33</span></span></td>
    <td><span data-ttu-id="12dd9-225">9.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-225">9.00</span></span></td>
    <td><span data-ttu-id="12dd9-226">825.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="12dd9-227">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-227">1000</span></span></td>
    <td><span data-ttu-id="12dd9-228">2</span><span class="sxs-lookup"><span data-stu-id="12dd9-228">2</span></span></td>
    <td><span data-ttu-id="12dd9-229">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-229">10</span></span></td>
    <td><span data-ttu-id="12dd9-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-230">2,000.00</span></span></td>
    <td><span data-ttu-id="12dd9-231">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-231">10</span></span></td>
    <td><span data-ttu-id="12dd9-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-232">2,000.00</span></span></td>
    <td><span data-ttu-id="12dd9-233">200.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-234">10.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-234">10.00</span></span></td>
    <td><span data-ttu-id="12dd9-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="12dd9-236"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="12dd9-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="12dd9-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="12dd9-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="12dd9-243">Nota i seguenti dettagli in questo report di esempio:</span><span class="sxs-lookup"><span data-stu-id="12dd9-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="12dd9-244">I valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** mostrati nel report sono valori per le dimensioni delle scorte finanziarie (**Sito**, in questo caso).</span><span class="sxs-lookup"><span data-stu-id="12dd9-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="12dd9-245">Ad esempio, per il sito 1, il report mostra le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="12dd9-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="12dd9-246">Il valore **Quantità valore di inventario** è *14* (= 10 + 5 - 5 + 5 - 1).</span><span class="sxs-lookup"><span data-stu-id="12dd9-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="12dd9-247">Il valore **Valore di inventario** è *1.283,33* (= 1.000 + 375 - 458,33 + 458,33 - 91,67).</span><span class="sxs-lookup"><span data-stu-id="12dd9-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="12dd9-248">Il valore **Costo unitario medio** è *91,67*.</span><span class="sxs-lookup"><span data-stu-id="12dd9-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="12dd9-249">Il valore **Valore disponibilità** e il valore **Quantità** in ciascun bucket del periodo viene calcolato utilizzando il valore **Costo unitario medio**.</span><span class="sxs-lookup"><span data-stu-id="12dd9-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="12dd9-250">Il report determina la quantità disponibile per ciascun bucket del periodo riassumendo la quantità di inventario totale ricevuta per ciascun bucket del periodo.</span><span class="sxs-lookup"><span data-stu-id="12dd9-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="12dd9-251">Quindi applica il principio FIFO (first in, first out) per detrarre la quantità totale emessa, indipendentemente dal modello di inventario utilizzato dagli articoli.</span><span class="sxs-lookup"><span data-stu-id="12dd9-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="12dd9-252">Se esegui di nuovo lo stesso rapporto, ma questa volta hai impostato entrambi i campi **Sito** e **Magazzino** su *Visualizza*, il nuovo report sarà simile al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="12dd9-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="12dd9-253">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="12dd9-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-254">Sito</span><span class="sxs-lookup"><span data-stu-id="12dd9-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-255">Magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-256">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="12dd9-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-257">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="12dd9-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-258">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-259">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-260">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="12dd9-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-262">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="12dd9-264">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-265">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="12dd9-266">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-267">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="12dd9-268">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-269">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="12dd9-270">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-270">1000</span></span></td>
    <td><span data-ttu-id="12dd9-271">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-271">1</span></span></td>
    <td><span data-ttu-id="12dd9-272">11</span><span class="sxs-lookup"><span data-stu-id="12dd9-272">11</span></span></td>
    <td><span data-ttu-id="12dd9-273">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-273">10</span></span></td>
    <td><span data-ttu-id="12dd9-274">916.67</span><span class="sxs-lookup"><span data-stu-id="12dd9-274">916.67</span></span></td>
    <td><span data-ttu-id="12dd9-275">14</span><span class="sxs-lookup"><span data-stu-id="12dd9-275">14</span></span></td>
    <td><span data-ttu-id="12dd9-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-276">1,283.33</span></span></td>
    <td><span data-ttu-id="12dd9-277">91.67</span><span class="sxs-lookup"><span data-stu-id="12dd9-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-278">5.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-278">5.00</span></span></td>
    <td><span data-ttu-id="12dd9-279">458.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-279">458.33</span></span></td>
    <td><span data-ttu-id="12dd9-280">5.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-280">5.00</span></span></td>
    <td><span data-ttu-id="12dd9-281">458.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="12dd9-282">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-282">1000</span></span></td>
    <td><span data-ttu-id="12dd9-283">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-283">1</span></span></td>
    <td><span data-ttu-id="12dd9-284">12</span><span class="sxs-lookup"><span data-stu-id="12dd9-284">12</span></span></td>
    <td><span data-ttu-id="12dd9-285">4</span><span class="sxs-lookup"><span data-stu-id="12dd9-285">4</span></span></td>
    <td><span data-ttu-id="12dd9-286">366.67</span><span class="sxs-lookup"><span data-stu-id="12dd9-286">366.67</span></span></td>
    <td><span data-ttu-id="12dd9-287">14</span><span class="sxs-lookup"><span data-stu-id="12dd9-287">14</span></span></td>
    <td><span data-ttu-id="12dd9-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="12dd9-288">1,283.33</span></span></td>
    <td><span data-ttu-id="12dd9-289">91.67</span><span class="sxs-lookup"><span data-stu-id="12dd9-289">91.67</span></span></td>
    <td><span data-ttu-id="12dd9-290">4.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-290">4.00</span></span></td>
    <td><span data-ttu-id="12dd9-291">366.67</span><span class="sxs-lookup"><span data-stu-id="12dd9-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="12dd9-292">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-292">1000</span></span></td>
    <td><span data-ttu-id="12dd9-293">2</span><span class="sxs-lookup"><span data-stu-id="12dd9-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="12dd9-294">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-294">10</span></span></td>
    <td><span data-ttu-id="12dd9-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-295">2,000.00</span></span></td>
    <td><span data-ttu-id="12dd9-296">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-296">10</span></span></td>
    <td><span data-ttu-id="12dd9-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-297">2,000.00</span></span></td>
    <td><span data-ttu-id="12dd9-298">200.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-299">10.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-299">10.00</span></span></td>
    <td><span data-ttu-id="12dd9-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="12dd9-301"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="12dd9-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="12dd9-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="12dd9-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="12dd9-310">Questa volta, il sito 1 è diviso in due righe, una per il magazzino 11 e una per il magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="12dd9-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="12dd9-311">Tuttavia, i valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** sono gli stessi poiché **Magazzino** non è una dimensione dell'inventario finanziario.</span><span class="sxs-lookup"><span data-stu-id="12dd9-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="12dd9-312">Notare inoltre che la distribuzione della quantità del sito 1 è diversa.</span><span class="sxs-lookup"><span data-stu-id="12dd9-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="12dd9-313">Nel primo report eseguito, il sistema ha ignorato l'ordine di trasferimento che si è verificato nello stesso sito e ha dedotto la quantità della fattura di vendita dal bucket del periodo **31/3/2020 - 1/3/2020** nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="12dd9-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="12dd9-314">Tuttavia, nel nuovo report, il sistema deduce la quantità della fattura di vendita dal bucket del periodo **8/5/2020 - 1/5/2020** nel magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="12dd9-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="12dd9-315">Effetti della chiusura dell'inventario</span><span class="sxs-lookup"><span data-stu-id="12dd9-315">Effects of inventory closing</span></span>

<span data-ttu-id="12dd9-316">Se esegui la chiusura dell'inventario per maggio e successivamente esegui nuovamente il report precedente, ma imposti il campo **Alla data** su *31 maggio 2020*, noterai i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="12dd9-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="12dd9-317">I valori **Valore di inventario** e **Costo unitario medio** vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="12dd9-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="12dd9-318">Il valore **Valore disponibilità** e tutti i valori **Importo** in ogni bucket del periodo vengono aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="12dd9-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="12dd9-319">Il nuovo report sarà simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="12dd9-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="12dd9-320">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="12dd9-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-321">Sito</span><span class="sxs-lookup"><span data-stu-id="12dd9-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-322">Magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-323">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="12dd9-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-324">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="12dd9-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-325">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-326">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="12dd9-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="12dd9-327">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="12dd9-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-329">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="12dd9-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="12dd9-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="12dd9-331">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-332">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="12dd9-333">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-334">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="12dd9-335">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="12dd9-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="12dd9-336">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="12dd9-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="12dd9-337">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-337">1000</span></span></td>
    <td><span data-ttu-id="12dd9-338">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-338">1</span></span></td>
    <td><span data-ttu-id="12dd9-339">11</span><span class="sxs-lookup"><span data-stu-id="12dd9-339">11</span></span></td>
    <td><span data-ttu-id="12dd9-340">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-340">10</span></span></td>
    <td><span data-ttu-id="12dd9-341">910.70</span><span class="sxs-lookup"><span data-stu-id="12dd9-341">910.70</span></span></td>
    <td><span data-ttu-id="12dd9-342">14</span><span class="sxs-lookup"><span data-stu-id="12dd9-342">14</span></span></td>
    <td><span data-ttu-id="12dd9-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-343">1,275.00</span></span></td>
    <td><span data-ttu-id="12dd9-344">91.07</span><span class="sxs-lookup"><span data-stu-id="12dd9-344">91.07</span></span></td>
    <td><span data-ttu-id="12dd9-345">0,00</span><span class="sxs-lookup"><span data-stu-id="12dd9-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="12dd9-346">5.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-346">5.00</span></span></td>
    <td><span data-ttu-id="12dd9-347">455.36</span><span class="sxs-lookup"><span data-stu-id="12dd9-347">455.36</span></span></td>
    <td><span data-ttu-id="12dd9-348">5.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-348">5.00</span></span></td>
    <td><span data-ttu-id="12dd9-349">455.36</span><span class="sxs-lookup"><span data-stu-id="12dd9-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="12dd9-350">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-350">1000</span></span></td>
    <td><span data-ttu-id="12dd9-351">1</span><span class="sxs-lookup"><span data-stu-id="12dd9-351">1</span></span></td>
    <td><span data-ttu-id="12dd9-352">12</span><span class="sxs-lookup"><span data-stu-id="12dd9-352">12</span></span></td>
    <td><span data-ttu-id="12dd9-353">4</span><span class="sxs-lookup"><span data-stu-id="12dd9-353">4</span></span></td>
    <td><span data-ttu-id="12dd9-354">364.29</span><span class="sxs-lookup"><span data-stu-id="12dd9-354">364.29</span></span></td>
    <td><span data-ttu-id="12dd9-355">14</span><span class="sxs-lookup"><span data-stu-id="12dd9-355">14</span></span></td>
    <td><span data-ttu-id="12dd9-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-356">1,275.00</span></span></td>
    <td><span data-ttu-id="12dd9-357">91.07</span><span class="sxs-lookup"><span data-stu-id="12dd9-357">91.07</span></span></td>
    <td><span data-ttu-id="12dd9-358">4.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-358">4.00</span></span></td>
    <td><span data-ttu-id="12dd9-359">364.29</span><span class="sxs-lookup"><span data-stu-id="12dd9-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="12dd9-360">1000</span><span class="sxs-lookup"><span data-stu-id="12dd9-360">1000</span></span></td>
    <td><span data-ttu-id="12dd9-361">2</span><span class="sxs-lookup"><span data-stu-id="12dd9-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="12dd9-362">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-362">10</span></span></td>
    <td><span data-ttu-id="12dd9-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-363">2,000.00</span></span></td>
    <td><span data-ttu-id="12dd9-364">10</span><span class="sxs-lookup"><span data-stu-id="12dd9-364">10</span></span></td>
    <td><span data-ttu-id="12dd9-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-365">2,000.00</span></span></td>
    <td><span data-ttu-id="12dd9-366">200.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-367">10.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-367">10.00</span></span></td>
    <td><span data-ttu-id="12dd9-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="12dd9-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="12dd9-369"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="12dd9-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="12dd9-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="12dd9-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="12dd9-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="12dd9-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="12dd9-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
