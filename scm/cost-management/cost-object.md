---
title: Oggetti di costo
description: "Questo articolo fornisce le informazioni sugli oggetti di costo e illustra come i costi e le quantità sono accumulati. Un oggetto di costo è un'entità per cui costi e quantità sono accumulati. Un'entità oggetto di costo può essere un prodotto o varianti prodotto, ad esempio varianti per stile e colore."
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
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: d43ea6c0d80a1602f298bbbedb88dd8f7decca4e
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="cost-objects"></a><span data-ttu-id="0c9f0-105">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="0c9f0-105">Cost objects</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0c9f0-106">Questo articolo fornisce le informazioni sugli oggetti di costo e illustra come i costi e le quantità sono accumulati.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="0c9f0-107">Un oggetto di costo è un'entità per cui costi e quantità sono accumulati.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="0c9f0-108">Un'entità oggetto di costo può essere un prodotto o varianti prodotto, ad esempio varianti per stile e colore.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

<a name="cost-objects"></a><span data-ttu-id="0c9f0-109">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="0c9f0-109">Cost objects</span></span>
------------

<span data-ttu-id="0c9f0-110">Nella pagina **Oggetti di costo** sono elencati tutti gli oggetti di costo registrati in un prodotto.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="0c9f0-111">Gli oggetti di costo vengono definiti dai dati delle seguenti origini:</span><span class="sxs-lookup"><span data-stu-id="0c9f0-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="0c9f0-112">Prodotto</span><span class="sxs-lookup"><span data-stu-id="0c9f0-112">Product</span></span>
-   <span data-ttu-id="0c9f0-113">Gruppo di dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="0c9f0-113">Product dimension group</span></span>
-   <span data-ttu-id="0c9f0-114">Gruppo di dimensioni di immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="0c9f0-114">Storage dimension group</span></span>
-   <span data-ttu-id="0c9f0-115">Gruppo di dimensioni di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="0c9f0-115">Tracking dimension group</span></span>

<span data-ttu-id="0c9f0-116">**Nota:** un oggetto di costo rappresenta un elemento di costo solo di tipo **Materiale diretto**.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="0c9f0-117">Un oggetto di costo e un oggetto di magazzino differiscono nel modo in cui un oggetto di costo è definito dalle dimensioni inventariali selezionate per il rendiconto finanziario.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="0c9f0-118">Ad esempio, un articolo ha la configurazione indicata di seguito:</span><span class="sxs-lookup"><span data-stu-id="0c9f0-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="0c9f0-119">**Sito:** Inventario fisico = Sì, Inventario finanziario = Sì</span><span class="sxs-lookup"><span data-stu-id="0c9f0-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="0c9f0-120">**Magazzino:** Inventario fisico = Sì, Inventario finanziario = No</span><span class="sxs-lookup"><span data-stu-id="0c9f0-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="0c9f0-121">**Batch n.:** Inventario fisico = Sì, Inventario finanziario = No</span><span class="sxs-lookup"><span data-stu-id="0c9f0-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="0c9f0-122">Nella seguente tabella vengono illustrate le definizioni di oggetto di costo e di oggetto di magazzino.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="0c9f0-123">Tipo oggetto</span><span class="sxs-lookup"><span data-stu-id="0c9f0-123">Object type</span></span>      | <span data-ttu-id="0c9f0-124">Numero articolo</span><span class="sxs-lookup"><span data-stu-id="0c9f0-124">Item number</span></span> | <span data-ttu-id="0c9f0-125">Sito</span><span class="sxs-lookup"><span data-stu-id="0c9f0-125">Site</span></span> | <span data-ttu-id="0c9f0-126">Magazzino</span><span class="sxs-lookup"><span data-stu-id="0c9f0-126">Warehouse</span></span> | <span data-ttu-id="0c9f0-127">Batch n.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="0c9f0-128">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="0c9f0-128">Cost object</span></span>      | <span data-ttu-id="0c9f0-129"> interno </span><span class="sxs-lookup"><span data-stu-id="0c9f0-129">x</span></span>           | <span data-ttu-id="0c9f0-130"> interno </span><span class="sxs-lookup"><span data-stu-id="0c9f0-130">x</span></span>    |           |           |
| <span data-ttu-id="0c9f0-131">Oggetto di magazzino</span><span class="sxs-lookup"><span data-stu-id="0c9f0-131">Inventory object</span></span> | <span data-ttu-id="0c9f0-132"> interno </span><span class="sxs-lookup"><span data-stu-id="0c9f0-132">x</span></span>           | <span data-ttu-id="0c9f0-133"> interno </span><span class="sxs-lookup"><span data-stu-id="0c9f0-133">x</span></span>    |  <span data-ttu-id="0c9f0-134"> interno </span><span class="sxs-lookup"><span data-stu-id="0c9f0-134">x</span></span>        | <span data-ttu-id="0c9f0-135"> interno </span><span class="sxs-lookup"><span data-stu-id="0c9f0-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="0c9f0-136">Accumulo di costi e quantità</span><span class="sxs-lookup"><span data-stu-id="0c9f0-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="0c9f0-137">Il valore nel campo **Valore** è una somma dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c9f0-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="0c9f0-138">Importo costi fisico</span><span class="sxs-lookup"><span data-stu-id="0c9f0-138">Physical cost amount</span></span>
    -   <span data-ttu-id="0c9f0-139">Importo costi finanziario</span><span class="sxs-lookup"><span data-stu-id="0c9f0-139">Financial cost amount</span></span>
    -   <span data-ttu-id="0c9f0-140">Rettifiche</span><span class="sxs-lookup"><span data-stu-id="0c9f0-140">Adjustments</span></span>
-   <span data-ttu-id="0c9f0-141">Il valore nel campo **Quantità** è una somma dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c9f0-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="0c9f0-142">Ricevuto</span><span class="sxs-lookup"><span data-stu-id="0c9f0-142">Received</span></span>
    -   <span data-ttu-id="0c9f0-143">Detratto</span><span class="sxs-lookup"><span data-stu-id="0c9f0-143">Deducted</span></span>
    -   <span data-ttu-id="0c9f0-144">Quantità registrata</span><span class="sxs-lookup"><span data-stu-id="0c9f0-144">Posted quantity</span></span>
-   <span data-ttu-id="0c9f0-145">Il campo **Costo unitario medio** è un campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="0c9f0-146">Il valore viene calcolato dividendo il valore di **Valore** per il valore di **Quantità**.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="0c9f0-147">**Nota:** Il parametro **Includi valore fisico** non ha alcun effetto sui calcoli precedenti.</span><span class="sxs-lookup"><span data-stu-id="0c9f0-147">**Note:** The **Include physical value **parameter has no effect on the preceding calculations.</span></span>

<a name="see-also"></a><span data-ttu-id="0c9f0-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c9f0-148">See also</span></span>
--------

[<span data-ttu-id="0c9f0-149">Gruppo di dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="0c9f0-149">Product dimension group</span></span>](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[<span data-ttu-id="0c9f0-150">Gruppo di dimensioni di immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="0c9f0-150">Storage dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[<span data-ttu-id="0c9f0-151">Gruppo di dimensioni di tracciabilità</span><span class="sxs-lookup"><span data-stu-id="0c9f0-151">Tracking dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[<span data-ttu-id="0c9f0-152">Novità o modifiche</span><span class="sxs-lookup"><span data-stu-id="0c9f0-152">What's new or changed</span></span>](/dynamics365/unified-operations/dev-itpro/get-started/whats-new-changed)

[<span data-ttu-id="0c9f0-153">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="0c9f0-153">Cost entries</span></span>](cost-entries.md)




