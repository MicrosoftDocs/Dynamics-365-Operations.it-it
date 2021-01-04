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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431129"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="70ae4-103">Esempi e logica dei report di aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="70ae4-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70ae4-104">Questo argomento presenta alcuni esempi che mostrano come interpretare i risultati di un report di **aging delle scorte**.</span><span class="sxs-lookup"><span data-stu-id="70ae4-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="70ae4-105">Questo report classifica i valori delle quantità e delle scorte disponibili per un articolo o un gruppo di articoli selezionati in diversi gruppi di periodi.</span><span class="sxs-lookup"><span data-stu-id="70ae4-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="70ae4-106">Questo argomento mostra anche la logica interna del report.</span><span class="sxs-lookup"><span data-stu-id="70ae4-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="70ae4-107">Gli esempi in questo argomento mostrano i risultati presentati su un report **di aging delle scorte** standard.</span><span class="sxs-lookup"><span data-stu-id="70ae4-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="70ae4-108">Tuttavia, in generale, si consiglia di utilizzare la versione [Archiviazione report di aging delle scorte](inventory-aging-report-storage.md) di questo report, soprattutto quando si hanno molti articoli e magazzini da elaborare.</span><span class="sxs-lookup"><span data-stu-id="70ae4-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="70ae4-109">L'archiviazione report di aging delle scorte salva ogni report generato, mostra i risultati come una pagina interattiva e un grafico e consente di esportare qualsiasi rapporto salvato.</span><span class="sxs-lookup"><span data-stu-id="70ae4-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="70ae4-110">Dati di esempio utilizzati in questi esempi</span><span class="sxs-lookup"><span data-stu-id="70ae4-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="70ae4-111">Gli esempi in questo argomento si basano sui dati di transazione delle scorte di esempio descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="70ae4-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="70ae4-112">Configurazione delle dimensioni di immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="70ae4-112">Storage dimension setup</span></span>

<span data-ttu-id="70ae4-113">Il sistema di esempio contiene la seguente configurazione delle dimensioni di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="70ae4-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="70ae4-114">Nome</span><span class="sxs-lookup"><span data-stu-id="70ae4-114">Name</span></span>      | <span data-ttu-id="70ae4-115">Attive</span><span class="sxs-lookup"><span data-stu-id="70ae4-115">Active</span></span> | <span data-ttu-id="70ae4-116">Inventario fisico</span><span class="sxs-lookup"><span data-stu-id="70ae4-116">Physical inventory</span></span> | <span data-ttu-id="70ae4-117">Inventario finanziario</span><span class="sxs-lookup"><span data-stu-id="70ae4-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="70ae4-118">Sito</span><span class="sxs-lookup"><span data-stu-id="70ae4-118">Site</span></span>      | <span data-ttu-id="70ae4-119">Sì</span><span class="sxs-lookup"><span data-stu-id="70ae4-119">Yes</span></span>    | <span data-ttu-id="70ae4-120">Sì</span><span class="sxs-lookup"><span data-stu-id="70ae4-120">Yes</span></span>                | <span data-ttu-id="70ae4-121">Sì</span><span class="sxs-lookup"><span data-stu-id="70ae4-121">Yes</span></span>                 |
| <span data-ttu-id="70ae4-122">Magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-122">Warehouse</span></span> | <span data-ttu-id="70ae4-123">Sì</span><span class="sxs-lookup"><span data-stu-id="70ae4-123">Yes</span></span>    | <span data-ttu-id="70ae4-124">Sì</span><span class="sxs-lookup"><span data-stu-id="70ae4-124">Yes</span></span>                | <span data-ttu-id="70ae4-125">Nessuna</span><span class="sxs-lookup"><span data-stu-id="70ae4-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="70ae4-126">Modello inventariale</span><span class="sxs-lookup"><span data-stu-id="70ae4-126">Inventory model</span></span>

<span data-ttu-id="70ae4-127">Per il sistema di esempio, il modello inventariale per i prodotti rilasciati è *FIFO* e l'impostazione **Prezzo di costo** per il modello inventariale è *Includi valore fisico*.</span><span class="sxs-lookup"><span data-stu-id="70ae4-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="70ae4-128">Operazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-128">Inventory transactions</span></span>

<span data-ttu-id="70ae4-129">Il sistema di esempio contiene le seguenti transazioni di inventario per un prodotto rilasciato con il numero di articolo *1.000*.</span><span class="sxs-lookup"><span data-stu-id="70ae4-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="70ae4-130">Riferimento</span><span class="sxs-lookup"><span data-stu-id="70ae4-130">Reference</span></span>      | <span data-ttu-id="70ae4-131">Sito</span><span class="sxs-lookup"><span data-stu-id="70ae4-131">Site</span></span> | <span data-ttu-id="70ae4-132">Magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-132">Warehouse</span></span> | <span data-ttu-id="70ae4-133">Ricevimento</span><span class="sxs-lookup"><span data-stu-id="70ae4-133">Receipt</span></span>   | <span data-ttu-id="70ae4-134">Uscita</span><span class="sxs-lookup"><span data-stu-id="70ae4-134">Issue</span></span> | <span data-ttu-id="70ae4-135">Data effettiva</span><span class="sxs-lookup"><span data-stu-id="70ae4-135">Physical date</span></span> | <span data-ttu-id="70ae4-136">Data finanziaria</span><span class="sxs-lookup"><span data-stu-id="70ae4-136">Financial date</span></span> | <span data-ttu-id="70ae4-137">Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-137">Quantity</span></span> | <span data-ttu-id="70ae4-138">Importo costo</span><span class="sxs-lookup"><span data-stu-id="70ae4-138">Cost amount</span></span> | <span data-ttu-id="70ae4-139">Importo costi fisico</span><span class="sxs-lookup"><span data-stu-id="70ae4-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="70ae4-140">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="70ae4-140">Purchase order</span></span> | <span data-ttu-id="70ae4-141">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-141">1</span></span>    | <span data-ttu-id="70ae4-142">11</span><span class="sxs-lookup"><span data-stu-id="70ae4-142">11</span></span>        | <span data-ttu-id="70ae4-143">Acquistato</span><span class="sxs-lookup"><span data-stu-id="70ae4-143">Purchased</span></span> |       | <span data-ttu-id="70ae4-144">15 marzo</span><span class="sxs-lookup"><span data-stu-id="70ae4-144">March 15</span></span>      | <span data-ttu-id="70ae4-145">15 marzo</span><span class="sxs-lookup"><span data-stu-id="70ae4-145">March 15</span></span>       | <span data-ttu-id="70ae4-146">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-146">10</span></span>       | <span data-ttu-id="70ae4-147">1.000</span><span class="sxs-lookup"><span data-stu-id="70ae4-147">1,000</span></span>       | <span data-ttu-id="70ae4-148">1.000</span><span class="sxs-lookup"><span data-stu-id="70ae4-148">1,000</span></span>                |
| <span data-ttu-id="70ae4-149">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="70ae4-149">Purchase order</span></span> | <span data-ttu-id="70ae4-150">2</span><span class="sxs-lookup"><span data-stu-id="70ae4-150">2</span></span>    | <span data-ttu-id="70ae4-151">21</span><span class="sxs-lookup"><span data-stu-id="70ae4-151">21</span></span>        | <span data-ttu-id="70ae4-152">Acquistato</span><span class="sxs-lookup"><span data-stu-id="70ae4-152">Purchased</span></span> |       | <span data-ttu-id="70ae4-153">15 marzo</span><span class="sxs-lookup"><span data-stu-id="70ae4-153">March 15</span></span>      | <span data-ttu-id="70ae4-154">15 marzo</span><span class="sxs-lookup"><span data-stu-id="70ae4-154">March 15</span></span>       | <span data-ttu-id="70ae4-155">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-155">10</span></span>       | <span data-ttu-id="70ae4-156">2,000</span><span class="sxs-lookup"><span data-stu-id="70ae4-156">2,000</span></span>       | <span data-ttu-id="70ae4-157">2,000</span><span class="sxs-lookup"><span data-stu-id="70ae4-157">2,000</span></span>                |
| <span data-ttu-id="70ae4-158">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="70ae4-158">Purchase order</span></span> | <span data-ttu-id="70ae4-159">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-159">1</span></span>    | <span data-ttu-id="70ae4-160">11</span><span class="sxs-lookup"><span data-stu-id="70ae4-160">11</span></span>        | <span data-ttu-id="70ae4-161">Ricevuti</span><span class="sxs-lookup"><span data-stu-id="70ae4-161">Received</span></span>  |       | <span data-ttu-id="70ae4-162">15 aprile</span><span class="sxs-lookup"><span data-stu-id="70ae4-162">April 15</span></span>      |                | <span data-ttu-id="70ae4-163">5</span><span class="sxs-lookup"><span data-stu-id="70ae4-163">5</span></span>        |             | <span data-ttu-id="70ae4-164">375</span><span class="sxs-lookup"><span data-stu-id="70ae4-164">375</span></span>                  |
| <span data-ttu-id="70ae4-165">Ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="70ae4-165">Transfer order</span></span> | <span data-ttu-id="70ae4-166">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-166">1</span></span>    | <span data-ttu-id="70ae4-167">11</span><span class="sxs-lookup"><span data-stu-id="70ae4-167">11</span></span>        |           | <span data-ttu-id="70ae4-168">Venduto</span><span class="sxs-lookup"><span data-stu-id="70ae4-168">Sold</span></span>  | <span data-ttu-id="70ae4-169">2° maggio</span><span class="sxs-lookup"><span data-stu-id="70ae4-169">May 2</span></span>         | <span data-ttu-id="70ae4-170">2° maggio</span><span class="sxs-lookup"><span data-stu-id="70ae4-170">May 2</span></span>          | <span data-ttu-id="70ae4-171">-5</span><span class="sxs-lookup"><span data-stu-id="70ae4-171">-5</span></span>       | <span data-ttu-id="70ae4-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="70ae4-172">-458.33</span></span>     | <span data-ttu-id="70ae4-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="70ae4-173">-458.33</span></span>              |
| <span data-ttu-id="70ae4-174">Ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="70ae4-174">Transfer order</span></span> | <span data-ttu-id="70ae4-175">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-175">1</span></span>    | <span data-ttu-id="70ae4-176">12</span><span class="sxs-lookup"><span data-stu-id="70ae4-176">12</span></span>        | <span data-ttu-id="70ae4-177">Acquistato</span><span class="sxs-lookup"><span data-stu-id="70ae4-177">Purchased</span></span> |       | <span data-ttu-id="70ae4-178">2° maggio</span><span class="sxs-lookup"><span data-stu-id="70ae4-178">May 2</span></span>         | <span data-ttu-id="70ae4-179">2° maggio</span><span class="sxs-lookup"><span data-stu-id="70ae4-179">May 2</span></span>          | <span data-ttu-id="70ae4-180">5</span><span class="sxs-lookup"><span data-stu-id="70ae4-180">5</span></span>        | <span data-ttu-id="70ae4-181">458.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-181">458.33</span></span>      | <span data-ttu-id="70ae4-182">458.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-182">458.33</span></span>               |
| <span data-ttu-id="70ae4-183">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="70ae4-183">Sales order</span></span>    | <span data-ttu-id="70ae4-184">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-184">1</span></span>    | <span data-ttu-id="70ae4-185">12</span><span class="sxs-lookup"><span data-stu-id="70ae4-185">12</span></span>        |           | <span data-ttu-id="70ae4-186">Venduto</span><span class="sxs-lookup"><span data-stu-id="70ae4-186">Sold</span></span>  | <span data-ttu-id="70ae4-187">3° maggio</span><span class="sxs-lookup"><span data-stu-id="70ae4-187">May 3</span></span>         | <span data-ttu-id="70ae4-188">3° maggio</span><span class="sxs-lookup"><span data-stu-id="70ae4-188">May 3</span></span>          | <span data-ttu-id="70ae4-189">-1</span><span class="sxs-lookup"><span data-stu-id="70ae4-189">-1</span></span>       | <span data-ttu-id="70ae4-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="70ae4-190">-91.67</span></span>      | <span data-ttu-id="70ae4-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="70ae4-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="70ae4-192">Come vengono calcolate le quantità e gli importi in ciascun intervallo di periodi</span><span class="sxs-lookup"><span data-stu-id="70ae4-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="70ae4-193">Utilizzando i dati di esempio descritti nelle sezioni precedenti, puoi eseguire un report **di aging delle scorte** con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="70ae4-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="70ae4-194">**Alla data:** *9 maggio 2020*</span><span class="sxs-lookup"><span data-stu-id="70ae4-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="70ae4-195">**Sito:** *Visualizza*</span><span class="sxs-lookup"><span data-stu-id="70ae4-195">**Site:** *View*</span></span>
- <span data-ttu-id="70ae4-196">**Magazzino:** *No*</span><span class="sxs-lookup"><span data-stu-id="70ae4-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="70ae4-197">**Numero articolo:** *Totale*</span><span class="sxs-lookup"><span data-stu-id="70ae4-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="70ae4-198">**Periodo di aging:** imposta questo campo per generare bucket mensili.</span><span class="sxs-lookup"><span data-stu-id="70ae4-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="70ae4-199">In questo caso, il contenuto del report generato sarà simile al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="70ae4-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="70ae4-200">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="70ae4-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-201">Sito</span><span class="sxs-lookup"><span data-stu-id="70ae4-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-202">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="70ae4-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-203">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="70ae4-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-204">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-205">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-206">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="70ae4-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-208">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="70ae4-210">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-211">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="70ae4-212">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-213">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="70ae4-214">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-215">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="70ae4-216">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-216">1000</span></span></td>
    <td><span data-ttu-id="70ae4-217">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-217">1</span></span></td>
    <td><span data-ttu-id="70ae4-218">14</span><span class="sxs-lookup"><span data-stu-id="70ae4-218">14</span></span></td>
    <td><span data-ttu-id="70ae4-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-219">1,283.33</span></span></td>
    <td><span data-ttu-id="70ae4-220">14</span><span class="sxs-lookup"><span data-stu-id="70ae4-220">14</span></span></td>
    <td><span data-ttu-id="70ae4-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-221">1,283.33</span></span></td>
    <td><span data-ttu-id="70ae4-222">91.67</span><span class="sxs-lookup"><span data-stu-id="70ae4-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-223">5.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-223">5.00</span></span></td>
    <td><span data-ttu-id="70ae4-224">458.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-224">458.33</span></span></td>
    <td><span data-ttu-id="70ae4-225">9.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-225">9.00</span></span></td>
    <td><span data-ttu-id="70ae4-226">825.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="70ae4-227">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-227">1000</span></span></td>
    <td><span data-ttu-id="70ae4-228">2</span><span class="sxs-lookup"><span data-stu-id="70ae4-228">2</span></span></td>
    <td><span data-ttu-id="70ae4-229">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-229">10</span></span></td>
    <td><span data-ttu-id="70ae4-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-230">2,000.00</span></span></td>
    <td><span data-ttu-id="70ae4-231">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-231">10</span></span></td>
    <td><span data-ttu-id="70ae4-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-232">2,000.00</span></span></td>
    <td><span data-ttu-id="70ae4-233">200.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-234">10.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-234">10.00</span></span></td>
    <td><span data-ttu-id="70ae4-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="70ae4-236"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="70ae4-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="70ae4-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="70ae4-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="70ae4-243">Nota i seguenti dettagli in questo report di esempio:</span><span class="sxs-lookup"><span data-stu-id="70ae4-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="70ae4-244">I valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** mostrati nel report sono valori per le dimensioni delle scorte finanziarie (**Sito**, in questo caso).</span><span class="sxs-lookup"><span data-stu-id="70ae4-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="70ae4-245">Ad esempio, per il sito 1, il report mostra le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="70ae4-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="70ae4-246">Il valore **Quantità valore di inventario** è *14* (= 10 + 5 - 5 + 5 - 1).</span><span class="sxs-lookup"><span data-stu-id="70ae4-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="70ae4-247">Il valore **Valore di inventario** è *1.283,33* (= 1.000 + 375 - 458,33 + 458,33 - 91,67).</span><span class="sxs-lookup"><span data-stu-id="70ae4-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="70ae4-248">Il valore **Costo unitario medio** è *91,67*.</span><span class="sxs-lookup"><span data-stu-id="70ae4-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="70ae4-249">Il valore **Valore disponibilità** e il valore **Quantità** in ciascun bucket del periodo viene calcolato utilizzando il valore **Costo unitario medio**.</span><span class="sxs-lookup"><span data-stu-id="70ae4-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="70ae4-250">Il report determina la quantità disponibile per ciascun bucket del periodo riassumendo la quantità di inventario totale ricevuta per ciascun bucket del periodo.</span><span class="sxs-lookup"><span data-stu-id="70ae4-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="70ae4-251">Quindi applica il principio FIFO (first in, first out) per detrarre la quantità totale emessa, indipendentemente dal modello di inventario utilizzato dagli articoli.</span><span class="sxs-lookup"><span data-stu-id="70ae4-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="70ae4-252">Se esegui di nuovo lo stesso rapporto, ma questa volta hai impostato entrambi i campi **Sito** e **Magazzino** su *Visualizza*, il nuovo report sarà simile al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="70ae4-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="70ae4-253">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="70ae4-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-254">Sito</span><span class="sxs-lookup"><span data-stu-id="70ae4-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-255">Magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-256">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="70ae4-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-257">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="70ae4-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-258">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-259">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-260">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="70ae4-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-262">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="70ae4-264">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-265">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="70ae4-266">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-267">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="70ae4-268">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-269">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="70ae4-270">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-270">1000</span></span></td>
    <td><span data-ttu-id="70ae4-271">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-271">1</span></span></td>
    <td><span data-ttu-id="70ae4-272">11</span><span class="sxs-lookup"><span data-stu-id="70ae4-272">11</span></span></td>
    <td><span data-ttu-id="70ae4-273">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-273">10</span></span></td>
    <td><span data-ttu-id="70ae4-274">916.67</span><span class="sxs-lookup"><span data-stu-id="70ae4-274">916.67</span></span></td>
    <td><span data-ttu-id="70ae4-275">14</span><span class="sxs-lookup"><span data-stu-id="70ae4-275">14</span></span></td>
    <td><span data-ttu-id="70ae4-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-276">1,283.33</span></span></td>
    <td><span data-ttu-id="70ae4-277">91.67</span><span class="sxs-lookup"><span data-stu-id="70ae4-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-278">5.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-278">5.00</span></span></td>
    <td><span data-ttu-id="70ae4-279">458.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-279">458.33</span></span></td>
    <td><span data-ttu-id="70ae4-280">5.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-280">5.00</span></span></td>
    <td><span data-ttu-id="70ae4-281">458.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="70ae4-282">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-282">1000</span></span></td>
    <td><span data-ttu-id="70ae4-283">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-283">1</span></span></td>
    <td><span data-ttu-id="70ae4-284">12</span><span class="sxs-lookup"><span data-stu-id="70ae4-284">12</span></span></td>
    <td><span data-ttu-id="70ae4-285">4</span><span class="sxs-lookup"><span data-stu-id="70ae4-285">4</span></span></td>
    <td><span data-ttu-id="70ae4-286">366.67</span><span class="sxs-lookup"><span data-stu-id="70ae4-286">366.67</span></span></td>
    <td><span data-ttu-id="70ae4-287">14</span><span class="sxs-lookup"><span data-stu-id="70ae4-287">14</span></span></td>
    <td><span data-ttu-id="70ae4-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="70ae4-288">1,283.33</span></span></td>
    <td><span data-ttu-id="70ae4-289">91.67</span><span class="sxs-lookup"><span data-stu-id="70ae4-289">91.67</span></span></td>
    <td><span data-ttu-id="70ae4-290">4.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-290">4.00</span></span></td>
    <td><span data-ttu-id="70ae4-291">366.67</span><span class="sxs-lookup"><span data-stu-id="70ae4-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="70ae4-292">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-292">1000</span></span></td>
    <td><span data-ttu-id="70ae4-293">2</span><span class="sxs-lookup"><span data-stu-id="70ae4-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="70ae4-294">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-294">10</span></span></td>
    <td><span data-ttu-id="70ae4-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-295">2,000.00</span></span></td>
    <td><span data-ttu-id="70ae4-296">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-296">10</span></span></td>
    <td><span data-ttu-id="70ae4-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-297">2,000.00</span></span></td>
    <td><span data-ttu-id="70ae4-298">200.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-299">10.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-299">10.00</span></span></td>
    <td><span data-ttu-id="70ae4-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="70ae4-301"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="70ae4-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="70ae4-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="70ae4-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="70ae4-310">Questa volta, il sito 1 è diviso in due righe, una per il magazzino 11 e una per il magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="70ae4-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="70ae4-311">Tuttavia, i valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** sono gli stessi poiché **Magazzino** non è una dimensione dell'inventario finanziario.</span><span class="sxs-lookup"><span data-stu-id="70ae4-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="70ae4-312">Notare inoltre che la distribuzione della quantità del sito 1 è diversa.</span><span class="sxs-lookup"><span data-stu-id="70ae4-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="70ae4-313">Nel primo report eseguito, il sistema ha ignorato l'ordine di trasferimento che si è verificato nello stesso sito e ha dedotto la quantità della fattura di vendita dal bucket del periodo **31/3/2020 - 1/3/2020** nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="70ae4-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="70ae4-314">Tuttavia, nel nuovo report, il sistema deduce la quantità della fattura di vendita dal bucket del periodo **8/5/2020 - 1/5/2020** nel magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="70ae4-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="70ae4-315">Effetti della chiusura dell'inventario</span><span class="sxs-lookup"><span data-stu-id="70ae4-315">Effects of inventory closing</span></span>

<span data-ttu-id="70ae4-316">Se esegui la chiusura dell'inventario per maggio e successivamente esegui nuovamente il report precedente, ma imposti il campo **Alla data** su *31 maggio 2020*, noterai i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="70ae4-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="70ae4-317">I valori **Valore di inventario** e **Costo unitario medio** vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="70ae4-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="70ae4-318">Il valore **Valore disponibilità** e tutti i valori **Importo** in ogni bucket del periodo vengono aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="70ae4-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="70ae4-319">Il nuovo report sarà simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="70ae4-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="70ae4-320">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="70ae4-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-321">Sito</span><span class="sxs-lookup"><span data-stu-id="70ae4-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-322">Magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-323">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="70ae4-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-324">Valore disponibilità</span><span class="sxs-lookup"><span data-stu-id="70ae4-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-325">Quantità valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-326">Valore di magazzino</span><span class="sxs-lookup"><span data-stu-id="70ae4-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="70ae4-327">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="70ae4-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-329">30/4/2020 -1/4/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="70ae4-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="70ae4-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="70ae4-331">P1: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-332">P1: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="70ae4-333">P2: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-334">P2: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="70ae4-335">P3: Quantità</span><span class="sxs-lookup"><span data-stu-id="70ae4-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="70ae4-336">P3: Importo</span><span class="sxs-lookup"><span data-stu-id="70ae4-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="70ae4-337">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-337">1000</span></span></td>
    <td><span data-ttu-id="70ae4-338">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-338">1</span></span></td>
    <td><span data-ttu-id="70ae4-339">11</span><span class="sxs-lookup"><span data-stu-id="70ae4-339">11</span></span></td>
    <td><span data-ttu-id="70ae4-340">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-340">10</span></span></td>
    <td><span data-ttu-id="70ae4-341">910.70</span><span class="sxs-lookup"><span data-stu-id="70ae4-341">910.70</span></span></td>
    <td><span data-ttu-id="70ae4-342">14</span><span class="sxs-lookup"><span data-stu-id="70ae4-342">14</span></span></td>
    <td><span data-ttu-id="70ae4-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-343">1,275.00</span></span></td>
    <td><span data-ttu-id="70ae4-344">91.07</span><span class="sxs-lookup"><span data-stu-id="70ae4-344">91.07</span></span></td>
    <td><span data-ttu-id="70ae4-345">0,00</span><span class="sxs-lookup"><span data-stu-id="70ae4-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="70ae4-346">5.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-346">5.00</span></span></td>
    <td><span data-ttu-id="70ae4-347">455.36</span><span class="sxs-lookup"><span data-stu-id="70ae4-347">455.36</span></span></td>
    <td><span data-ttu-id="70ae4-348">5.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-348">5.00</span></span></td>
    <td><span data-ttu-id="70ae4-349">455.36</span><span class="sxs-lookup"><span data-stu-id="70ae4-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="70ae4-350">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-350">1000</span></span></td>
    <td><span data-ttu-id="70ae4-351">1</span><span class="sxs-lookup"><span data-stu-id="70ae4-351">1</span></span></td>
    <td><span data-ttu-id="70ae4-352">12</span><span class="sxs-lookup"><span data-stu-id="70ae4-352">12</span></span></td>
    <td><span data-ttu-id="70ae4-353">4</span><span class="sxs-lookup"><span data-stu-id="70ae4-353">4</span></span></td>
    <td><span data-ttu-id="70ae4-354">364.29</span><span class="sxs-lookup"><span data-stu-id="70ae4-354">364.29</span></span></td>
    <td><span data-ttu-id="70ae4-355">14</span><span class="sxs-lookup"><span data-stu-id="70ae4-355">14</span></span></td>
    <td><span data-ttu-id="70ae4-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-356">1,275.00</span></span></td>
    <td><span data-ttu-id="70ae4-357">91.07</span><span class="sxs-lookup"><span data-stu-id="70ae4-357">91.07</span></span></td>
    <td><span data-ttu-id="70ae4-358">4.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-358">4.00</span></span></td>
    <td><span data-ttu-id="70ae4-359">364.29</span><span class="sxs-lookup"><span data-stu-id="70ae4-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="70ae4-360">1000</span><span class="sxs-lookup"><span data-stu-id="70ae4-360">1000</span></span></td>
    <td><span data-ttu-id="70ae4-361">2</span><span class="sxs-lookup"><span data-stu-id="70ae4-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="70ae4-362">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-362">10</span></span></td>
    <td><span data-ttu-id="70ae4-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-363">2,000.00</span></span></td>
    <td><span data-ttu-id="70ae4-364">10</span><span class="sxs-lookup"><span data-stu-id="70ae4-364">10</span></span></td>
    <td><span data-ttu-id="70ae4-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-365">2,000.00</span></span></td>
    <td><span data-ttu-id="70ae4-366">200.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-367">10.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-367">10.00</span></span></td>
    <td><span data-ttu-id="70ae4-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="70ae4-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="70ae4-369"><strong>1.000 totali</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="70ae4-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="70ae4-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="70ae4-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="70ae4-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="70ae4-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="70ae4-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
