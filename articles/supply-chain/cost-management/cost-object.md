---
title: Oggetti di costo
description: Questo articolo fornisce le informazioni sugli oggetti di costo e illustra come i costi e le quantità sono accumulati. Un oggetto di costo è un'entità per cui costi e quantità sono accumulati. Un'entità oggetto di costo può essere un prodotto o varianti prodotto, ad esempio varianti per stile e colore.
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
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85e590322c75cfb2ad21236af56656061037a4b7
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983527"
---
# <a name="cost-objects"></a><span data-ttu-id="936ae-105">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="936ae-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="936ae-106">Questo articolo fornisce le informazioni sugli oggetti di costo e illustra come i costi e le quantità sono accumulati.</span><span class="sxs-lookup"><span data-stu-id="936ae-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="936ae-107">Un oggetto di costo è un'entità per cui costi e quantità sono accumulati.</span><span class="sxs-lookup"><span data-stu-id="936ae-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="936ae-108">Un'entità oggetto di costo può essere un prodotto o varianti prodotto, ad esempio varianti per stile e colore.</span><span class="sxs-lookup"><span data-stu-id="936ae-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="936ae-109">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="936ae-109">Cost objects</span></span>

<span data-ttu-id="936ae-110">Nella pagina **Oggetti di costo** sono elencati tutti gli oggetti di costo registrati in un prodotto.</span><span class="sxs-lookup"><span data-stu-id="936ae-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="936ae-111">Gli oggetti di costo vengono definiti dai dati delle seguenti origini:</span><span class="sxs-lookup"><span data-stu-id="936ae-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="936ae-112">Prodotto</span><span class="sxs-lookup"><span data-stu-id="936ae-112">Product</span></span>
-   <span data-ttu-id="936ae-113">Gruppo di dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="936ae-113">Product dimension group</span></span>
-   <span data-ttu-id="936ae-114">Gruppo di dimensioni di immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="936ae-114">Storage dimension group</span></span>
-   <span data-ttu-id="936ae-115">Gruppo di dimensioni di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="936ae-115">Tracking dimension group</span></span>

<span data-ttu-id="936ae-116">**Nota:** un oggetto di costo rappresenta un elemento di costo solo di tipo **Materiale diretto**.</span><span class="sxs-lookup"><span data-stu-id="936ae-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="936ae-117">Un oggetto di costo e un oggetto di magazzino differiscono nel modo in cui un oggetto di costo è definito dalle dimensioni inventariali selezionate per il rendiconto finanziario.</span><span class="sxs-lookup"><span data-stu-id="936ae-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="936ae-118">Ad esempio, un articolo ha la configurazione indicata di seguito:</span><span class="sxs-lookup"><span data-stu-id="936ae-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="936ae-119">**Sito:** Inventario fisico = Sì, Inventario finanziario = Sì</span><span class="sxs-lookup"><span data-stu-id="936ae-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="936ae-120">**Magazzino:** Inventario fisico = Sì, Inventario finanziario = No</span><span class="sxs-lookup"><span data-stu-id="936ae-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="936ae-121">**Batch n.:** Inventario fisico = Sì, Inventario finanziario = No</span><span class="sxs-lookup"><span data-stu-id="936ae-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="936ae-122">Nella seguente tabella vengono illustrate le definizioni di oggetto di costo e di oggetto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="936ae-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="936ae-123">Tipo oggetto</span><span class="sxs-lookup"><span data-stu-id="936ae-123">Object type</span></span>      | <span data-ttu-id="936ae-124">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="936ae-124">Item number</span></span> | <span data-ttu-id="936ae-125">Sito</span><span class="sxs-lookup"><span data-stu-id="936ae-125">Site</span></span> | <span data-ttu-id="936ae-126">Magazzino</span><span class="sxs-lookup"><span data-stu-id="936ae-126">Warehouse</span></span> | <span data-ttu-id="936ae-127">Batch n.</span><span class="sxs-lookup"><span data-stu-id="936ae-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="936ae-128">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="936ae-128">Cost object</span></span>      | <span data-ttu-id="936ae-129"> interno </span><span class="sxs-lookup"><span data-stu-id="936ae-129">x</span></span>           | <span data-ttu-id="936ae-130"> interno </span><span class="sxs-lookup"><span data-stu-id="936ae-130">x</span></span>    |           |           |
| <span data-ttu-id="936ae-131">Oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="936ae-131">Inventory object</span></span> | <span data-ttu-id="936ae-132"> interno </span><span class="sxs-lookup"><span data-stu-id="936ae-132">x</span></span>           | <span data-ttu-id="936ae-133"> interno </span><span class="sxs-lookup"><span data-stu-id="936ae-133">x</span></span>    |  <span data-ttu-id="936ae-134"> interno </span><span class="sxs-lookup"><span data-stu-id="936ae-134">x</span></span>        | <span data-ttu-id="936ae-135"> interno </span><span class="sxs-lookup"><span data-stu-id="936ae-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="936ae-136">Accumulo di costi e quantità</span><span class="sxs-lookup"><span data-stu-id="936ae-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="936ae-137">Il valore nel campo **Valore** è una somma dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="936ae-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="936ae-138">Importo costi fisico</span><span class="sxs-lookup"><span data-stu-id="936ae-138">Physical cost amount</span></span>
    -   <span data-ttu-id="936ae-139">Importo costi finanziario</span><span class="sxs-lookup"><span data-stu-id="936ae-139">Financial cost amount</span></span>
    -   <span data-ttu-id="936ae-140">Rettifiche</span><span class="sxs-lookup"><span data-stu-id="936ae-140">Adjustments</span></span>
-   <span data-ttu-id="936ae-141">Il valore nel campo **Quantità** è una somma dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="936ae-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="936ae-142">Ricevuto</span><span class="sxs-lookup"><span data-stu-id="936ae-142">Received</span></span>
    -   <span data-ttu-id="936ae-143">Detratto</span><span class="sxs-lookup"><span data-stu-id="936ae-143">Deducted</span></span>
    -   <span data-ttu-id="936ae-144">Quantità registrata</span><span class="sxs-lookup"><span data-stu-id="936ae-144">Posted quantity</span></span>
-   <span data-ttu-id="936ae-145">Il campo **Costo unitario medio** è un campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="936ae-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="936ae-146">Il valore viene calcolato dividendo il valore di **Valore** per il valore di **Quantità**.</span><span class="sxs-lookup"><span data-stu-id="936ae-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="936ae-147">**Nota:** Il parametro **Includi valore fisico** non ha alcun effetto sui calcoli precedenti.</span><span class="sxs-lookup"><span data-stu-id="936ae-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="936ae-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="936ae-148">Additional resources</span></span>
--------

[<span data-ttu-id="936ae-149">Gruppo di dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="936ae-149">Product dimension group</span></span>](https://technet.microsoft.com/library/aa499382.aspx)

[<span data-ttu-id="936ae-150">Gruppo di dimensioni di immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="936ae-150">Storage dimension group</span></span>](https://technet.microsoft.com/library/hh209317.aspx)

[<span data-ttu-id="936ae-151">Gruppo di dimensioni di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="936ae-151">Tracking dimension group</span></span>](https://technet.microsoft.com/library/hh209465.aspx)

[<span data-ttu-id="936ae-152">Novità o modifiche</span><span class="sxs-lookup"><span data-stu-id="936ae-152">What's new or changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="936ae-153">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="936ae-153">Cost entries</span></span>](cost-entries.md)



