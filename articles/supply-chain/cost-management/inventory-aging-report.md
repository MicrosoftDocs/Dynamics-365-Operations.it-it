---
title: Esempi e logica dei report di aging delle scorte
description: Questo argomento presenta alcuni esempi che mostrano come interpretare i risultati di un report di aging delle scorte.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1d9c70a7931c009cd53fbd28a3f4c768d04964a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214420"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="a360a-103">Esempi e logica dei report di aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="a360a-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a360a-104">Questo argomento presenta alcuni esempi che mostrano come interpretare i risultati di un report di **aging delle scorte**.</span><span class="sxs-lookup"><span data-stu-id="a360a-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="a360a-105">Questo report classifica i valori delle quantità e delle scorte disponibili per un articolo o un gruppo di articoli selezionati in diversi gruppi di periodi.</span><span class="sxs-lookup"><span data-stu-id="a360a-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="a360a-106">Questo argomento mostra anche la logica interna del report.</span><span class="sxs-lookup"><span data-stu-id="a360a-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="a360a-107">Gli esempi in questo argomento mostrano i risultati presentati su un report **di aging delle scorte** standard.</span><span class="sxs-lookup"><span data-stu-id="a360a-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="a360a-108">Tuttavia, in generale, si consiglia di utilizzare la versione [Archiviazione report di aging delle scorte](inventory-aging-report-storage.md) di questo report, soprattutto quando si hanno molti articoli e magazzini da elaborare.</span><span class="sxs-lookup"><span data-stu-id="a360a-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="a360a-109">L'archiviazione report di aging delle scorte salva ogni report generato, mostra i risultati come una pagina interattiva e un grafico e consente di esportare qualsiasi rapporto salvato.</span><span class="sxs-lookup"><span data-stu-id="a360a-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="a360a-110">Dati di esempio utilizzati in questi esempi</span><span class="sxs-lookup"><span data-stu-id="a360a-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="a360a-111">Gli esempi in questo argomento si basano sui dati di transazione delle scorte di esempio descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a360a-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="a360a-112">Configurazione delle dimensioni di immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="a360a-112">Storage dimension setup</span></span>

<span data-ttu-id="a360a-113">Il sistema di esempio contiene la seguente configurazione delle dimensioni di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="a360a-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="a360a-114">Nome</span><span class="sxs-lookup"><span data-stu-id="a360a-114">Name</span></span>      | <span data-ttu-id="a360a-115">Attive</span><span class="sxs-lookup"><span data-stu-id="a360a-115">Active</span></span> | <span data-ttu-id="a360a-116">Inventario fisico</span><span class="sxs-lookup"><span data-stu-id="a360a-116">Physical inventory</span></span> | <span data-ttu-id="a360a-117">Inventario finanziario</span><span class="sxs-lookup"><span data-stu-id="a360a-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="a360a-118">Sito</span><span class="sxs-lookup"><span data-stu-id="a360a-118">Site</span></span>      | <span data-ttu-id="a360a-119">Sì</span><span class="sxs-lookup"><span data-stu-id="a360a-119">Yes</span></span>    | <span data-ttu-id="a360a-120">Sì</span><span class="sxs-lookup"><span data-stu-id="a360a-120">Yes</span></span>                | <span data-ttu-id="a360a-121">Sì</span><span class="sxs-lookup"><span data-stu-id="a360a-121">Yes</span></span>                 |
| <span data-ttu-id="a360a-122">Magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-122">Warehouse</span></span> | <span data-ttu-id="a360a-123">Sì</span><span class="sxs-lookup"><span data-stu-id="a360a-123">Yes</span></span>    | <span data-ttu-id="a360a-124">Sì</span><span class="sxs-lookup"><span data-stu-id="a360a-124">Yes</span></span>                | <span data-ttu-id="a360a-125">Nessuna</span><span class="sxs-lookup"><span data-stu-id="a360a-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="a360a-126">Modello inventariale</span><span class="sxs-lookup"><span data-stu-id="a360a-126">Inventory model</span></span>

<span data-ttu-id="a360a-127">Per il sistema di esempio, il modello inventariale per i prodotti rilasciati è *FIFO* e l'impostazione **Prezzo di costo** per il modello inventariale è *Includi valore fisico*.</span><span class="sxs-lookup"><span data-stu-id="a360a-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="a360a-128">Operazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-128">Inventory transactions</span></span>

<span data-ttu-id="a360a-129">Il sistema di esempio contiene le seguenti transazioni di inventario per un prodotto rilasciato con il numero di articolo *1.000*.</span><span class="sxs-lookup"><span data-stu-id="a360a-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="a360a-130">Riferimento</span><span class="sxs-lookup"><span data-stu-id="a360a-130">Reference</span></span>      | <span data-ttu-id="a360a-131">Sito</span><span class="sxs-lookup"><span data-stu-id="a360a-131">Site</span></span> | <span data-ttu-id="a360a-132">Magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-132">Warehouse</span></span> | <span data-ttu-id="a360a-133">Ricevimento</span><span class="sxs-lookup"><span data-stu-id="a360a-133">Receipt</span></span>   | <span data-ttu-id="a360a-134">Uscita</span><span class="sxs-lookup"><span data-stu-id="a360a-134">Issue</span></span> | <span data-ttu-id="a360a-135">Data effettiva</span><span class="sxs-lookup"><span data-stu-id="a360a-135">Physical date</span></span> | <span data-ttu-id="a360a-136">Data finanziaria</span><span class="sxs-lookup"><span data-stu-id="a360a-136">Financial date</span></span> | <span data-ttu-id="a360a-137">Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-137">Quantity</span></span> | <span data-ttu-id="a360a-138">Importo costo</span><span class="sxs-lookup"><span data-stu-id="a360a-138">Cost amount</span></span> | <span data-ttu-id="a360a-139">Importo costi fisico</span><span class="sxs-lookup"><span data-stu-id="a360a-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="a360a-140">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="a360a-140">Purchase order</span></span> | <span data-ttu-id="a360a-141">1</span><span class="sxs-lookup"><span data-stu-id="a360a-141">1</span></span>    | <span data-ttu-id="a360a-142">11</span><span class="sxs-lookup"><span data-stu-id="a360a-142">11</span></span>        | <span data-ttu-id="a360a-143">Acquistato</span><span class="sxs-lookup"><span data-stu-id="a360a-143">Purchased</span></span> |       | <span data-ttu-id="a360a-144">15 marzo</span><span class="sxs-lookup"><span data-stu-id="a360a-144">March 15</span></span>      | <span data-ttu-id="a360a-145">15 marzo</span><span class="sxs-lookup"><span data-stu-id="a360a-145">March 15</span></span>       | <span data-ttu-id="a360a-146">10</span><span class="sxs-lookup"><span data-stu-id="a360a-146">10</span></span>       | <span data-ttu-id="a360a-147">1.000</span><span class="sxs-lookup"><span data-stu-id="a360a-147">1,000</span></span>       | <span data-ttu-id="a360a-148">1.000</span><span class="sxs-lookup"><span data-stu-id="a360a-148">1,000</span></span>                |
| <span data-ttu-id="a360a-149">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="a360a-149">Purchase order</span></span> | <span data-ttu-id="a360a-150">2</span><span class="sxs-lookup"><span data-stu-id="a360a-150">2</span></span>    | <span data-ttu-id="a360a-151">21</span><span class="sxs-lookup"><span data-stu-id="a360a-151">21</span></span>        | <span data-ttu-id="a360a-152">Acquistato</span><span class="sxs-lookup"><span data-stu-id="a360a-152">Purchased</span></span> |       | <span data-ttu-id="a360a-153">15 marzo</span><span class="sxs-lookup"><span data-stu-id="a360a-153">March 15</span></span>      | <span data-ttu-id="a360a-154">15 marzo</span><span class="sxs-lookup"><span data-stu-id="a360a-154">March 15</span></span>       | <span data-ttu-id="a360a-155">10</span><span class="sxs-lookup"><span data-stu-id="a360a-155">10</span></span>       | <span data-ttu-id="a360a-156">2,000</span><span class="sxs-lookup"><span data-stu-id="a360a-156">2,000</span></span>       | <span data-ttu-id="a360a-157">2,000</span><span class="sxs-lookup"><span data-stu-id="a360a-157">2,000</span></span>                |
| <span data-ttu-id="a360a-158">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="a360a-158">Purchase order</span></span> | <span data-ttu-id="a360a-159">1</span><span class="sxs-lookup"><span data-stu-id="a360a-159">1</span></span>    | <span data-ttu-id="a360a-160">11</span><span class="sxs-lookup"><span data-stu-id="a360a-160">11</span></span>        | <span data-ttu-id="a360a-161">Ricevuti</span><span class="sxs-lookup"><span data-stu-id="a360a-161">Received</span></span>  |       | <span data-ttu-id="a360a-162">15 aprile</span><span class="sxs-lookup"><span data-stu-id="a360a-162">April 15</span></span>      |                | <span data-ttu-id="a360a-163">5</span><span class="sxs-lookup"><span data-stu-id="a360a-163">5</span></span>        |             | <span data-ttu-id="a360a-164">375</span><span class="sxs-lookup"><span data-stu-id="a360a-164">375</span></span>                  |
| <span data-ttu-id="a360a-165">Ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="a360a-165">Transfer order</span></span> | <span data-ttu-id="a360a-166">1</span><span class="sxs-lookup"><span data-stu-id="a360a-166">1</span></span>    | <span data-ttu-id="a360a-167">11</span><span class="sxs-lookup"><span data-stu-id="a360a-167">11</span></span>        |           | <span data-ttu-id="a360a-168">Venduto</span><span class="sxs-lookup"><span data-stu-id="a360a-168">Sold</span></span>  | <span data-ttu-id="a360a-169">2° maggio</span><span class="sxs-lookup"><span data-stu-id="a360a-169">May 2</span></span>         | <span data-ttu-id="a360a-170">2° maggio</span><span class="sxs-lookup"><span data-stu-id="a360a-170">May 2</span></span>          | <span data-ttu-id="a360a-171">-5</span><span class="sxs-lookup"><span data-stu-id="a360a-171">-5</span></span>       | <span data-ttu-id="a360a-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="a360a-172">-458.33</span></span>     | <span data-ttu-id="a360a-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="a360a-173">-458.33</span></span>              |
| <span data-ttu-id="a360a-174">Ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="a360a-174">Transfer order</span></span> | <span data-ttu-id="a360a-175">1</span><span class="sxs-lookup"><span data-stu-id="a360a-175">1</span></span>    | <span data-ttu-id="a360a-176">12</span><span class="sxs-lookup"><span data-stu-id="a360a-176">12</span></span>        | <span data-ttu-id="a360a-177">Acquistato</span><span class="sxs-lookup"><span data-stu-id="a360a-177">Purchased</span></span> |       | <span data-ttu-id="a360a-178">2° maggio</span><span class="sxs-lookup"><span data-stu-id="a360a-178">May 2</span></span>         | <span data-ttu-id="a360a-179">2° maggio</span><span class="sxs-lookup"><span data-stu-id="a360a-179">May 2</span></span>          | <span data-ttu-id="a360a-180">5</span><span class="sxs-lookup"><span data-stu-id="a360a-180">5</span></span>        | <span data-ttu-id="a360a-181">458.33</span><span class="sxs-lookup"><span data-stu-id="a360a-181">458.33</span></span>      | <span data-ttu-id="a360a-182">458.33</span><span class="sxs-lookup"><span data-stu-id="a360a-182">458.33</span></span>               |
| <span data-ttu-id="a360a-183">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="a360a-183">Sales order</span></span>    | <span data-ttu-id="a360a-184">1</span><span class="sxs-lookup"><span data-stu-id="a360a-184">1</span></span>    | <span data-ttu-id="a360a-185">12</span><span class="sxs-lookup"><span data-stu-id="a360a-185">12</span></span>        |           | <span data-ttu-id="a360a-186">Venduto</span><span class="sxs-lookup"><span data-stu-id="a360a-186">Sold</span></span>  | <span data-ttu-id="a360a-187">3° maggio</span><span class="sxs-lookup"><span data-stu-id="a360a-187">May 3</span></span>         | <span data-ttu-id="a360a-188">3° maggio</span><span class="sxs-lookup"><span data-stu-id="a360a-188">May 3</span></span>          | <span data-ttu-id="a360a-189">-1</span><span class="sxs-lookup"><span data-stu-id="a360a-189">-1</span></span>       | <span data-ttu-id="a360a-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="a360a-190">-91.67</span></span>      | <span data-ttu-id="a360a-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="a360a-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="a360a-192">Come vengono calcolate le quantità e gli importi in ciascun intervallo di periodi</span><span class="sxs-lookup"><span data-stu-id="a360a-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="a360a-193">Utilizzando i dati di esempio descritti nelle sezioni precedenti, puoi eseguire un report **di aging delle scorte** con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="a360a-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="a360a-194">**Alla data:** *9 maggio 2020*</span><span class="sxs-lookup"><span data-stu-id="a360a-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="a360a-195">**Sito:** *Visualizza*</span><span class="sxs-lookup"><span data-stu-id="a360a-195">**Site:** *View*</span></span>
- <span data-ttu-id="a360a-196">**Magazzino:** *No*</span><span class="sxs-lookup"><span data-stu-id="a360a-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="a360a-197">**Numero articolo:** *Totale*</span><span class="sxs-lookup"><span data-stu-id="a360a-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="a360a-198">**Periodo di aging:** imposta questo campo per generare bucket mensili.</span><span class="sxs-lookup"><span data-stu-id="a360a-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="a360a-199">In questo caso, il contenuto del report generato sarà simile al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="a360a-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="a360a-200">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="a360a-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-201">Sito</span><span class="sxs-lookup"><span data-stu-id="a360a-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-202">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="a360a-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-203">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="a360a-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-204">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-205">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-206">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="a360a-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-208">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="a360a-210">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-211">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="a360a-212">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-213">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="a360a-214">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-215">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="a360a-216">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-216">1000</span></span></td>
    <td><span data-ttu-id="a360a-217">1</span><span class="sxs-lookup"><span data-stu-id="a360a-217">1</span></span></td>
    <td><span data-ttu-id="a360a-218">14</span><span class="sxs-lookup"><span data-stu-id="a360a-218">14</span></span></td>
    <td><span data-ttu-id="a360a-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a360a-219">1,283.33</span></span></td>
    <td><span data-ttu-id="a360a-220">14</span><span class="sxs-lookup"><span data-stu-id="a360a-220">14</span></span></td>
    <td><span data-ttu-id="a360a-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a360a-221">1,283.33</span></span></td>
    <td><span data-ttu-id="a360a-222">91.67</span><span class="sxs-lookup"><span data-stu-id="a360a-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-223">5.00</span><span class="sxs-lookup"><span data-stu-id="a360a-223">5.00</span></span></td>
    <td><span data-ttu-id="a360a-224">458.33</span><span class="sxs-lookup"><span data-stu-id="a360a-224">458.33</span></span></td>
    <td><span data-ttu-id="a360a-225">9.00</span><span class="sxs-lookup"><span data-stu-id="a360a-225">9.00</span></span></td>
    <td><span data-ttu-id="a360a-226">825.00</span><span class="sxs-lookup"><span data-stu-id="a360a-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="a360a-227">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-227">1000</span></span></td>
    <td><span data-ttu-id="a360a-228">2</span><span class="sxs-lookup"><span data-stu-id="a360a-228">2</span></span></td>
    <td><span data-ttu-id="a360a-229">10</span><span class="sxs-lookup"><span data-stu-id="a360a-229">10</span></span></td>
    <td><span data-ttu-id="a360a-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-230">2,000.00</span></span></td>
    <td><span data-ttu-id="a360a-231">10</span><span class="sxs-lookup"><span data-stu-id="a360a-231">10</span></span></td>
    <td><span data-ttu-id="a360a-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-232">2,000.00</span></span></td>
    <td><span data-ttu-id="a360a-233">200.00</span><span class="sxs-lookup"><span data-stu-id="a360a-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-234">10.00</span><span class="sxs-lookup"><span data-stu-id="a360a-234">10.00</span></span></td>
    <td><span data-ttu-id="a360a-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="a360a-236"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="a360a-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="a360a-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="a360a-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="a360a-243">Nota i seguenti dettagli in questo report di esempio:</span><span class="sxs-lookup"><span data-stu-id="a360a-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="a360a-244">I valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** mostrati nel report sono valori per le dimensioni delle scorte finanziarie (**Sito**, in questo caso).</span><span class="sxs-lookup"><span data-stu-id="a360a-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="a360a-245">Ad esempio, per il sito 1, il report mostra le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="a360a-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="a360a-246">Il valore **Quantità valore di inventario** è *14* (= 10 + 5 - 5 + 5 - 1).</span><span class="sxs-lookup"><span data-stu-id="a360a-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="a360a-247">Il valore **Valore di inventario** è *1.283,33* (= 1.000 + 375 - 458,33 + 458,33 - 91,67).</span><span class="sxs-lookup"><span data-stu-id="a360a-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="a360a-248">Il valore **Costo unitario medio** è *91,67*.</span><span class="sxs-lookup"><span data-stu-id="a360a-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="a360a-249">Il valore **Valore disponibilità** e il valore **Quantità** in ciascun bucket del periodo viene calcolato utilizzando il valore **Costo unitario medio**.</span><span class="sxs-lookup"><span data-stu-id="a360a-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="a360a-250">Il report determina la quantità disponibile per ciascun bucket del periodo riassumendo la quantità di inventario totale ricevuta per ciascun bucket del periodo.</span><span class="sxs-lookup"><span data-stu-id="a360a-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="a360a-251">Quindi applica il principio FIFO (first in, first out) per detrarre la quantità totale emessa, indipendentemente dal modello di inventario utilizzato dagli articoli.</span><span class="sxs-lookup"><span data-stu-id="a360a-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="a360a-252">Se esegui di nuovo lo stesso rapporto, ma questa volta hai impostato entrambi i campi **Sito** e **Magazzino** su *Visualizza*, il nuovo report sarà simile al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="a360a-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="a360a-253">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="a360a-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-254">Sito</span><span class="sxs-lookup"><span data-stu-id="a360a-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-255">Magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-256">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="a360a-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-257">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="a360a-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-258">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-259">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-260">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="a360a-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-262">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="a360a-264">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-265">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="a360a-266">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-267">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="a360a-268">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-269">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="a360a-270">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-270">1000</span></span></td>
    <td><span data-ttu-id="a360a-271">1</span><span class="sxs-lookup"><span data-stu-id="a360a-271">1</span></span></td>
    <td><span data-ttu-id="a360a-272">11</span><span class="sxs-lookup"><span data-stu-id="a360a-272">11</span></span></td>
    <td><span data-ttu-id="a360a-273">10</span><span class="sxs-lookup"><span data-stu-id="a360a-273">10</span></span></td>
    <td><span data-ttu-id="a360a-274">916.67</span><span class="sxs-lookup"><span data-stu-id="a360a-274">916.67</span></span></td>
    <td><span data-ttu-id="a360a-275">14</span><span class="sxs-lookup"><span data-stu-id="a360a-275">14</span></span></td>
    <td><span data-ttu-id="a360a-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a360a-276">1,283.33</span></span></td>
    <td><span data-ttu-id="a360a-277">91.67</span><span class="sxs-lookup"><span data-stu-id="a360a-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-278">5.00</span><span class="sxs-lookup"><span data-stu-id="a360a-278">5.00</span></span></td>
    <td><span data-ttu-id="a360a-279">458.33</span><span class="sxs-lookup"><span data-stu-id="a360a-279">458.33</span></span></td>
    <td><span data-ttu-id="a360a-280">5.00</span><span class="sxs-lookup"><span data-stu-id="a360a-280">5.00</span></span></td>
    <td><span data-ttu-id="a360a-281">458.33</span><span class="sxs-lookup"><span data-stu-id="a360a-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="a360a-282">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-282">1000</span></span></td>
    <td><span data-ttu-id="a360a-283">1</span><span class="sxs-lookup"><span data-stu-id="a360a-283">1</span></span></td>
    <td><span data-ttu-id="a360a-284">12</span><span class="sxs-lookup"><span data-stu-id="a360a-284">12</span></span></td>
    <td><span data-ttu-id="a360a-285">4</span><span class="sxs-lookup"><span data-stu-id="a360a-285">4</span></span></td>
    <td><span data-ttu-id="a360a-286">366.67</span><span class="sxs-lookup"><span data-stu-id="a360a-286">366.67</span></span></td>
    <td><span data-ttu-id="a360a-287">14</span><span class="sxs-lookup"><span data-stu-id="a360a-287">14</span></span></td>
    <td><span data-ttu-id="a360a-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a360a-288">1,283.33</span></span></td>
    <td><span data-ttu-id="a360a-289">91.67</span><span class="sxs-lookup"><span data-stu-id="a360a-289">91.67</span></span></td>
    <td><span data-ttu-id="a360a-290">4.00</span><span class="sxs-lookup"><span data-stu-id="a360a-290">4.00</span></span></td>
    <td><span data-ttu-id="a360a-291">366.67</span><span class="sxs-lookup"><span data-stu-id="a360a-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="a360a-292">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-292">1000</span></span></td>
    <td><span data-ttu-id="a360a-293">2</span><span class="sxs-lookup"><span data-stu-id="a360a-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="a360a-294">10</span><span class="sxs-lookup"><span data-stu-id="a360a-294">10</span></span></td>
    <td><span data-ttu-id="a360a-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-295">2,000.00</span></span></td>
    <td><span data-ttu-id="a360a-296">10</span><span class="sxs-lookup"><span data-stu-id="a360a-296">10</span></span></td>
    <td><span data-ttu-id="a360a-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-297">2,000.00</span></span></td>
    <td><span data-ttu-id="a360a-298">200.00</span><span class="sxs-lookup"><span data-stu-id="a360a-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-299">10.00</span><span class="sxs-lookup"><span data-stu-id="a360a-299">10.00</span></span></td>
    <td><span data-ttu-id="a360a-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="a360a-301"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="a360a-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="a360a-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="a360a-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="a360a-310">Questa volta, il sito 1 è diviso in due righe, una per il magazzino 11 e una per il magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="a360a-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="a360a-311">Tuttavia, i valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** sono gli stessi poiché **Magazzino** non è una dimensione dell'inventario finanziario.</span><span class="sxs-lookup"><span data-stu-id="a360a-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="a360a-312">Notare inoltre che la distribuzione della quantità del sito 1 è diversa.</span><span class="sxs-lookup"><span data-stu-id="a360a-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="a360a-313">Nel primo report eseguito, il sistema ha ignorato l'ordine di trasferimento che si è verificato nello stesso sito e ha dedotto la quantità della fattura di vendita dal bucket del periodo **31/3/2020 - 1/3/2020** nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="a360a-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="a360a-314">Tuttavia, nel nuovo report, il sistema deduce la quantità della fattura di vendita dal bucket del periodo **8/5/2020 - 1/5/2020** nel magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="a360a-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="a360a-315">Effetti della chiusura dell'inventario</span><span class="sxs-lookup"><span data-stu-id="a360a-315">Effects of inventory closing</span></span>

<span data-ttu-id="a360a-316">Se esegui la chiusura dell'inventario per maggio e successivamente esegui nuovamente il report precedente, ma imposti il campo **Alla data** su *31 maggio 2020*, noterai i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="a360a-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="a360a-317">I valori **Valore di inventario** e **Costo unitario medio** vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="a360a-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="a360a-318">Il valore **Valore disponibilità** e tutti i valori **Importo** in ogni bucket del periodo vengono aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a360a-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="a360a-319">Il nuovo report sarà simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a360a-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="a360a-320">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="a360a-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-321">Sito</span><span class="sxs-lookup"><span data-stu-id="a360a-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-322">Magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-323">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="a360a-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-324">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="a360a-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-325">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-326">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="a360a-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a360a-327">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="a360a-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-329">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a360a-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="a360a-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="a360a-331">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-332">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="a360a-333">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-334">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="a360a-335">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="a360a-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="a360a-336">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="a360a-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="a360a-337">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-337">1000</span></span></td>
    <td><span data-ttu-id="a360a-338">1</span><span class="sxs-lookup"><span data-stu-id="a360a-338">1</span></span></td>
    <td><span data-ttu-id="a360a-339">11</span><span class="sxs-lookup"><span data-stu-id="a360a-339">11</span></span></td>
    <td><span data-ttu-id="a360a-340">10</span><span class="sxs-lookup"><span data-stu-id="a360a-340">10</span></span></td>
    <td><span data-ttu-id="a360a-341">910.70</span><span class="sxs-lookup"><span data-stu-id="a360a-341">910.70</span></span></td>
    <td><span data-ttu-id="a360a-342">14</span><span class="sxs-lookup"><span data-stu-id="a360a-342">14</span></span></td>
    <td><span data-ttu-id="a360a-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="a360a-343">1,275.00</span></span></td>
    <td><span data-ttu-id="a360a-344">91.07</span><span class="sxs-lookup"><span data-stu-id="a360a-344">91.07</span></span></td>
    <td><span data-ttu-id="a360a-345">0,00</span><span class="sxs-lookup"><span data-stu-id="a360a-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="a360a-346">5.00</span><span class="sxs-lookup"><span data-stu-id="a360a-346">5.00</span></span></td>
    <td><span data-ttu-id="a360a-347">455.36</span><span class="sxs-lookup"><span data-stu-id="a360a-347">455.36</span></span></td>
    <td><span data-ttu-id="a360a-348">5.00</span><span class="sxs-lookup"><span data-stu-id="a360a-348">5.00</span></span></td>
    <td><span data-ttu-id="a360a-349">455.36</span><span class="sxs-lookup"><span data-stu-id="a360a-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="a360a-350">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-350">1000</span></span></td>
    <td><span data-ttu-id="a360a-351">1</span><span class="sxs-lookup"><span data-stu-id="a360a-351">1</span></span></td>
    <td><span data-ttu-id="a360a-352">12</span><span class="sxs-lookup"><span data-stu-id="a360a-352">12</span></span></td>
    <td><span data-ttu-id="a360a-353">4</span><span class="sxs-lookup"><span data-stu-id="a360a-353">4</span></span></td>
    <td><span data-ttu-id="a360a-354">364.29</span><span class="sxs-lookup"><span data-stu-id="a360a-354">364.29</span></span></td>
    <td><span data-ttu-id="a360a-355">14</span><span class="sxs-lookup"><span data-stu-id="a360a-355">14</span></span></td>
    <td><span data-ttu-id="a360a-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="a360a-356">1,275.00</span></span></td>
    <td><span data-ttu-id="a360a-357">91.07</span><span class="sxs-lookup"><span data-stu-id="a360a-357">91.07</span></span></td>
    <td><span data-ttu-id="a360a-358">4.00</span><span class="sxs-lookup"><span data-stu-id="a360a-358">4.00</span></span></td>
    <td><span data-ttu-id="a360a-359">364.29</span><span class="sxs-lookup"><span data-stu-id="a360a-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="a360a-360">1000</span><span class="sxs-lookup"><span data-stu-id="a360a-360">1000</span></span></td>
    <td><span data-ttu-id="a360a-361">2</span><span class="sxs-lookup"><span data-stu-id="a360a-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="a360a-362">10</span><span class="sxs-lookup"><span data-stu-id="a360a-362">10</span></span></td>
    <td><span data-ttu-id="a360a-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-363">2,000.00</span></span></td>
    <td><span data-ttu-id="a360a-364">10</span><span class="sxs-lookup"><span data-stu-id="a360a-364">10</span></span></td>
    <td><span data-ttu-id="a360a-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-365">2,000.00</span></span></td>
    <td><span data-ttu-id="a360a-366">200.00</span><span class="sxs-lookup"><span data-stu-id="a360a-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-367">10.00</span><span class="sxs-lookup"><span data-stu-id="a360a-367">10.00</span></span></td>
    <td><span data-ttu-id="a360a-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a360a-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="a360a-369"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a360a-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="a360a-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="a360a-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="a360a-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="a360a-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="a360a-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]