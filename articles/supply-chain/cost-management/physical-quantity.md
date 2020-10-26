---
title: Valori di un oggetto di magazzino
description: Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: daa36dad4009cc25b89363dcff6b4496205522e3
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981489"
---
# <a name="inventory-object-values"></a><span data-ttu-id="eacc6-103">Valori di un oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="eacc6-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eacc6-104">Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="eacc6-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="eacc6-105">Una nuova funzione denominata **quantità fisica** consente di visualizzare i valori di un oggetto specifico di magazzino.</span><span class="sxs-lookup"><span data-stu-id="eacc6-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="eacc6-106">Un oggetto di costo rappresenta il livello di entità in cui la contabilità inventario viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="eacc6-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="eacc6-107">Per ulteriori informazioni sugli oggetti di costo, vedere [Oggetti di costo](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="eacc6-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="eacc6-108">Per visualizzare i valori di un oggetto di magazzino specifico, fare clic su **Quantità fisica** nella pagina **Oggetto di costo**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="eacc6-109">Ecco viene calcolato il valore di un oggetto di magazzino:</span><span class="sxs-lookup"><span data-stu-id="eacc6-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="eacc6-110">object.Value magazzino = Cost unitario object.Average × object.Quantity magazzino</span><span class="sxs-lookup"><span data-stu-id="eacc6-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="eacc6-111">Il seguente esempio mostra come vengono calcolati i valori di un oggetto di magazzino e di un oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="eacc6-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="eacc6-112">Due eventi di entrata prodotti vengono registrati nell'articolo A:</span><span class="sxs-lookup"><span data-stu-id="eacc6-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="eacc6-113">Entrata prodotti 1: Quantità = 100. pz, Importo = $ 1.000, 00, Sito = 1, Magazzino =11 Batch n.</span><span class="sxs-lookup"><span data-stu-id="eacc6-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="eacc6-114">= B1</span><span class="sxs-lookup"><span data-stu-id="eacc6-114">= B1</span></span>
-   <span data-ttu-id="eacc6-115">Entrata prodotti 2: Quantità = 50. pz, Importo = $800,00, Sito = 1, Magazzino =11 Batch n.</span><span class="sxs-lookup"><span data-stu-id="eacc6-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="eacc6-116">= B2</span><span class="sxs-lookup"><span data-stu-id="eacc6-116">= B2</span></span>

<span data-ttu-id="eacc6-117">Nella seguente tabella viene visualizzato il risultato del calcolo per un oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="eacc6-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="eacc6-118">È possibile visualizzare il risultato nella pagina **Oggetto di costo**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-118">You can view the result on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="eacc6-119">Tipo oggetto</span><span class="sxs-lookup"><span data-stu-id="eacc6-119">Object type</span></span></th>
<th><span data-ttu-id="eacc6-120">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="eacc6-120">Item number</span></span></th>
<th><span data-ttu-id="eacc6-121">Sito</span><span class="sxs-lookup"><span data-stu-id="eacc6-121">Site</span></span></th>
<th><span data-ttu-id="eacc6-122">Quantità</span><span class="sxs-lookup"><span data-stu-id="eacc6-122">Quantity</span></span></th>
<th><span data-ttu-id="eacc6-123">Unità di magazzino</span><span class="sxs-lookup"><span data-stu-id="eacc6-123">Inventory unit</span></span></th>
<th><span data-ttu-id="eacc6-124">Valore</span><span class="sxs-lookup"><span data-stu-id="eacc6-124">Value</span></span></th>
<th><span data-ttu-id="eacc6-125">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="eacc6-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="eacc6-126">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="eacc6-126">Cost object</span></span></td>
<td><span data-ttu-id="eacc6-127">A</span><span class="sxs-lookup"><span data-stu-id="eacc6-127">A</span></span></td>
<td><span data-ttu-id="eacc6-128">1</span><span class="sxs-lookup"><span data-stu-id="eacc6-128">1</span></span></td>
<td><span data-ttu-id="eacc6-129">150</span><span class="sxs-lookup"><span data-stu-id="eacc6-129">150</span></span></td>
<td><span data-ttu-id="eacc6-130">Pzi</span><span class="sxs-lookup"><span data-stu-id="eacc6-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="eacc6-131">$1800,00</span><span class="sxs-lookup"><span data-stu-id="eacc6-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="eacc6-132">$12,00</span><span class="sxs-lookup"><span data-stu-id="eacc6-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="eacc6-133">Nella seguente tabella viene visualizzato il risultato del calcolo per un oggetto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="eacc6-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="eacc6-134">È possibile visualizzare il risultato facendo clic su **Quantità fisica** nella pagina **Oggetto di costo**.</span><span class="sxs-lookup"><span data-stu-id="eacc6-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="eacc6-135">Tipo oggetto</span><span class="sxs-lookup"><span data-stu-id="eacc6-135">Object type</span></span></th>
<th><span data-ttu-id="eacc6-136">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="eacc6-136">Item number</span></span></th>
<th><span data-ttu-id="eacc6-137">Sito</span><span class="sxs-lookup"><span data-stu-id="eacc6-137">Site</span></span></th>
<th><span data-ttu-id="eacc6-138">Magazzino</span><span class="sxs-lookup"><span data-stu-id="eacc6-138">Warehouse</span></span></th>
<th><span data-ttu-id="eacc6-139">Batch n.</span><span class="sxs-lookup"><span data-stu-id="eacc6-139">Batch No.</span></span></th>
<th><span data-ttu-id="eacc6-140">Quantità</span><span class="sxs-lookup"><span data-stu-id="eacc6-140">Quantity</span></span></th>
<th><span data-ttu-id="eacc6-141">Unità di magazzino</span><span class="sxs-lookup"><span data-stu-id="eacc6-141">Inventory unit</span></span></th>
<th><span data-ttu-id="eacc6-142">Valore</span><span class="sxs-lookup"><span data-stu-id="eacc6-142">Value</span></span></th>
<th><span data-ttu-id="eacc6-143">Costo unitario medio</span><span class="sxs-lookup"><span data-stu-id="eacc6-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="eacc6-144">Oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="eacc6-144">Inventory object</span></span></td>
<td><span data-ttu-id="eacc6-145">A</span><span class="sxs-lookup"><span data-stu-id="eacc6-145">A</span></span></td>
<td><span data-ttu-id="eacc6-146">1</span><span class="sxs-lookup"><span data-stu-id="eacc6-146">1</span></span></td>
<td><span data-ttu-id="eacc6-147">11</span><span class="sxs-lookup"><span data-stu-id="eacc6-147">11</span></span></td>
<td><span data-ttu-id="eacc6-148">B1</span><span class="sxs-lookup"><span data-stu-id="eacc6-148">B1</span></span></td>
<td><span data-ttu-id="eacc6-149">100</span><span class="sxs-lookup"><span data-stu-id="eacc6-149">100</span></span></td>
<td><span data-ttu-id="eacc6-150">Pzi</span><span class="sxs-lookup"><span data-stu-id="eacc6-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="eacc6-151">$1200,00</span><span class="sxs-lookup"><span data-stu-id="eacc6-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="eacc6-152">$12,00</span><span class="sxs-lookup"><span data-stu-id="eacc6-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eacc6-153">Oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="eacc6-153">Inventory object</span></span></td>
<td><span data-ttu-id="eacc6-154">A</span><span class="sxs-lookup"><span data-stu-id="eacc6-154">A</span></span></td>
<td><span data-ttu-id="eacc6-155">1</span><span class="sxs-lookup"><span data-stu-id="eacc6-155">1</span></span></td>
<td><span data-ttu-id="eacc6-156">11</span><span class="sxs-lookup"><span data-stu-id="eacc6-156">11</span></span></td>
<td><span data-ttu-id="eacc6-157">B2</span><span class="sxs-lookup"><span data-stu-id="eacc6-157">B2</span></span></td>
<td><span data-ttu-id="eacc6-158">50</span><span class="sxs-lookup"><span data-stu-id="eacc6-158">50</span></span></td>
<td><span data-ttu-id="eacc6-159">Pzi</span><span class="sxs-lookup"><span data-stu-id="eacc6-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="eacc6-160">$600,00</span><span class="sxs-lookup"><span data-stu-id="eacc6-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="eacc6-161">$12,00</span><span class="sxs-lookup"><span data-stu-id="eacc6-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="eacc6-162">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="eacc6-162">Additional resources</span></span>
--------

[<span data-ttu-id="eacc6-163">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="eacc6-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="eacc6-164">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="eacc6-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="eacc6-165">Novità e modifiche</span><span class="sxs-lookup"><span data-stu-id="eacc6-165">What's new and changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)



