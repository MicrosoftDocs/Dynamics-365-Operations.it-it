---
title: Valori di un oggetto di magazzino
description: Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 4aec6e70325c7e4d00e6070293a1ab0c719e420b
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="inventory-object-values"></a><span data-ttu-id="bc55c-103">Valori di un oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="bc55c-103">Inventory object values</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bc55c-104">Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="bc55c-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="bc55c-105">Una nuova funzione denominata **quantità fisica** consente di visualizzare i valori di un oggetto specifico di magazzino.</span><span class="sxs-lookup"><span data-stu-id="bc55c-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="bc55c-106">Un oggetto di costo rappresenta il livello di entità in cui la contabilità inventario viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="bc55c-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="bc55c-107">Per ulteriori informazioni sugli oggetti di costo, vedere [Oggetti di costo](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="bc55c-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="bc55c-108">Per visualizzare i valori di un oggetto di magazzino specifico, fare clic su **Quantità fisica** nella pagina **Oggetto di costo**.</span><span class="sxs-lookup"><span data-stu-id="bc55c-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="bc55c-109">Ecco viene calcolato il valore di un oggetto di magazzino:</span><span class="sxs-lookup"><span data-stu-id="bc55c-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="bc55c-110">object.Value magazzino = Cost unitario object.Average × object.Quantity magazzino</span><span class="sxs-lookup"><span data-stu-id="bc55c-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="bc55c-111">Il seguente esempio mostra come vengono calcolati i valori di un oggetto di magazzino e di un oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="bc55c-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="bc55c-112">Due eventi di entrata prodotti vengono registrati nell'articolo A:</span><span class="sxs-lookup"><span data-stu-id="bc55c-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="bc55c-113">Entrata prodotti 1: Quantità = 100. pz, Importo = $ 1.000, 00, Sito = 1, Magazzino =11 Batch n.</span><span class="sxs-lookup"><span data-stu-id="bc55c-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="bc55c-114">= B1</span><span class="sxs-lookup"><span data-stu-id="bc55c-114">= B1</span></span>
-   <span data-ttu-id="bc55c-115">Entrata prodotti 2: Quantità = 50. pz, Importo = $800,00, Sito = 1, Magazzino =11 Batch n.</span><span class="sxs-lookup"><span data-stu-id="bc55c-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="bc55c-116">= B2</span><span class="sxs-lookup"><span data-stu-id="bc55c-116">= B2</span></span>

<span data-ttu-id="bc55c-117">Nella seguente tabella viene visualizzato il risultato del calcolo per un oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="bc55c-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="bc55c-118">È possibile visualizzare il risultato nella pagina **Oggetto di costo**.</span><span class="sxs-lookup"><span data-stu-id="bc55c-118">You can view the result on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc55c-119">Tipo oggetto</span><span class="sxs-lookup"><span data-stu-id="bc55c-119">Object type</span></span></th>
<th><span data-ttu-id="bc55c-120">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="bc55c-120">Item number</span></span></th>
<th><span data-ttu-id="bc55c-121">Sito</span><span class="sxs-lookup"><span data-stu-id="bc55c-121">Site</span></span></th>
<th><span data-ttu-id="bc55c-122">Quantità</span><span class="sxs-lookup"><span data-stu-id="bc55c-122">Quantity</span></span></th>
<th><span data-ttu-id="bc55c-123">Unità di magazzino</span><span class="sxs-lookup"><span data-stu-id="bc55c-123">Inventory unit</span></span></th>
<th><span data-ttu-id="bc55c-124">Valore</span><span class="sxs-lookup"><span data-stu-id="bc55c-124">Value</span></span></th>
<th><span data-ttu-id="bc55c-125">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="bc55c-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bc55c-126">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="bc55c-126">Cost object</span></span></td>
<td><span data-ttu-id="bc55c-127">A</span><span class="sxs-lookup"><span data-stu-id="bc55c-127">A</span></span></td>
<td><span data-ttu-id="bc55c-128">1</span><span class="sxs-lookup"><span data-stu-id="bc55c-128">1</span></span></td>
<td><span data-ttu-id="bc55c-129">150</span><span class="sxs-lookup"><span data-stu-id="bc55c-129">150</span></span></td>
<td><span data-ttu-id="bc55c-130">Pzi</span><span class="sxs-lookup"><span data-stu-id="bc55c-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="bc55c-131">$1800,00</span><span class="sxs-lookup"><span data-stu-id="bc55c-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="bc55c-132">$12,00</span><span class="sxs-lookup"><span data-stu-id="bc55c-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bc55c-133">Nella seguente tabella viene visualizzato il risultato del calcolo per un oggetto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="bc55c-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="bc55c-134">È possibile visualizzare il risultato facendo clic su **Quantità fisica** nella pagina **Oggetto di costo**.</span><span class="sxs-lookup"><span data-stu-id="bc55c-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc55c-135">Tipo oggetto</span><span class="sxs-lookup"><span data-stu-id="bc55c-135">Object type</span></span></th>
<th><span data-ttu-id="bc55c-136">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="bc55c-136">Item number</span></span></th>
<th><span data-ttu-id="bc55c-137">Sito</span><span class="sxs-lookup"><span data-stu-id="bc55c-137">Site</span></span></th>
<th><span data-ttu-id="bc55c-138">Magazzino</span><span class="sxs-lookup"><span data-stu-id="bc55c-138">Warehouse</span></span></th>
<th><span data-ttu-id="bc55c-139">Batch n.</span><span class="sxs-lookup"><span data-stu-id="bc55c-139">Batch No.</span></span></th>
<th><span data-ttu-id="bc55c-140">Quantità</span><span class="sxs-lookup"><span data-stu-id="bc55c-140">Quantity</span></span></th>
<th><span data-ttu-id="bc55c-141">Unità di magazzino</span><span class="sxs-lookup"><span data-stu-id="bc55c-141">Inventory unit</span></span></th>
<th><span data-ttu-id="bc55c-142">Valore</span><span class="sxs-lookup"><span data-stu-id="bc55c-142">Value</span></span></th>
<th><span data-ttu-id="bc55c-143">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="bc55c-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bc55c-144">Oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="bc55c-144">Inventory object</span></span></td>
<td><span data-ttu-id="bc55c-145">A</span><span class="sxs-lookup"><span data-stu-id="bc55c-145">A</span></span></td>
<td><span data-ttu-id="bc55c-146">1</span><span class="sxs-lookup"><span data-stu-id="bc55c-146">1</span></span></td>
<td><span data-ttu-id="bc55c-147">11</span><span class="sxs-lookup"><span data-stu-id="bc55c-147">11</span></span></td>
<td><span data-ttu-id="bc55c-148">B1</span><span class="sxs-lookup"><span data-stu-id="bc55c-148">B1</span></span></td>
<td><span data-ttu-id="bc55c-149">100</span><span class="sxs-lookup"><span data-stu-id="bc55c-149">100</span></span></td>
<td><span data-ttu-id="bc55c-150">Pzi</span><span class="sxs-lookup"><span data-stu-id="bc55c-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="bc55c-151">$1200,00</span><span class="sxs-lookup"><span data-stu-id="bc55c-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="bc55c-152">$12,00</span><span class="sxs-lookup"><span data-stu-id="bc55c-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bc55c-153">Oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="bc55c-153">Inventory object</span></span></td>
<td><span data-ttu-id="bc55c-154">A</span><span class="sxs-lookup"><span data-stu-id="bc55c-154">A</span></span></td>
<td><span data-ttu-id="bc55c-155">1</span><span class="sxs-lookup"><span data-stu-id="bc55c-155">1</span></span></td>
<td><span data-ttu-id="bc55c-156">11</span><span class="sxs-lookup"><span data-stu-id="bc55c-156">11</span></span></td>
<td><span data-ttu-id="bc55c-157">B2</span><span class="sxs-lookup"><span data-stu-id="bc55c-157">B2</span></span></td>
<td><span data-ttu-id="bc55c-158">50</span><span class="sxs-lookup"><span data-stu-id="bc55c-158">50</span></span></td>
<td><span data-ttu-id="bc55c-159">Pzi</span><span class="sxs-lookup"><span data-stu-id="bc55c-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="bc55c-160">$600,00</span><span class="sxs-lookup"><span data-stu-id="bc55c-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="bc55c-161">$12,00</span><span class="sxs-lookup"><span data-stu-id="bc55c-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="bc55c-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc55c-162">See also</span></span>
--------

[<span data-ttu-id="bc55c-163">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="bc55c-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="bc55c-164">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="bc55c-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="bc55c-165">Novità e modifiche</span><span class="sxs-lookup"><span data-stu-id="bc55c-165">What's new and changed</span></span>](/dynamics365/unified-operations/dev-itpro/get-started/whats-new-changed)




