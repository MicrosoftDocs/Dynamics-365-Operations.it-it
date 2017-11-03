---
title: Voci di costo
description: "Questo articolo fornisce informazioni sulle voci di costo e sul momento in cui vengono create. Una voce di costo è un record che registra la quantità e il costo di un evento specifico."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4d8a443d03f8eb2d6ff44d869964b47b6569ce4c
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="cost-entries"></a><span data-ttu-id="3abd2-104">Voci di costo</span><span class="sxs-lookup"><span data-stu-id="3abd2-104">Cost entries</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3abd2-105">Questo articolo fornisce informazioni sulle voci di costo e sul momento in cui vengono create.</span><span class="sxs-lookup"><span data-stu-id="3abd2-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="3abd2-106">Una voce di costo è un record che registra la quantità e il costo di un evento specifico.</span><span class="sxs-lookup"><span data-stu-id="3abd2-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="3abd2-107">Le voci di costo sono aggregazioni delle operazioni di magazzino registrate su dimensioni inventariali finanziarie attive.</span><span class="sxs-lookup"><span data-stu-id="3abd2-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="3abd2-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="3abd2-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="3abd2-109">Esempio 1: nessuna voce di costo viene creata</span><span class="sxs-lookup"><span data-stu-id="3abd2-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="3abd2-110">Un evento del giornale di registrazione trasferimenti viene registrato.</span><span class="sxs-lookup"><span data-stu-id="3abd2-110">A transfer journal event is registered.</span></span> <span data-ttu-id="3abd2-111">L'evento trasferisce un pezzo di articolo A dall'ubicazione A all'ubicazione B. La dimensione inventariale dell'ubicazione non viene considerata parte dell'oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="3abd2-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="3abd2-112">Di conseguenza, l'evento crea due operazioni di magazzino e nessuna voce di costo.</span><span class="sxs-lookup"><span data-stu-id="3abd2-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="3abd2-113">Esempio 2: vengono create voci di costo</span><span class="sxs-lookup"><span data-stu-id="3abd2-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="3abd2-114">Un evento del giornale di registrazione trasferimenti viene registrato.</span><span class="sxs-lookup"><span data-stu-id="3abd2-114">A transfer journal event is registered.</span></span> <span data-ttu-id="3abd2-115">L'evento trasferisce un singolo pezzo dell'articolo A dal sito 1 al sito 2.</span><span class="sxs-lookup"><span data-stu-id="3abd2-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="3abd2-116">La dimensione inventariale Sito viene considerata parte dell'oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="3abd2-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="3abd2-117">Di conseguenza, l'evento crea due operazioni di magazzino e due voci di costo.</span><span class="sxs-lookup"><span data-stu-id="3abd2-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="3abd2-118">Esempio 3: viene creata una voce di costo</span><span class="sxs-lookup"><span data-stu-id="3abd2-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="3abd2-119">Un evento dell'entrata prodotti viene registrato per un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="3abd2-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="3abd2-120">L'evento immette 100 pezzi di un articolo A a un costo unitario di 10,00 euro (EUR).</span><span class="sxs-lookup"><span data-stu-id="3abd2-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="3abd2-121">Poiché l'articolo A utilizza un numero di serie per tenere traccia dello scopo di gestione articoli, un numero di serie univoco viene creato per ciascun articolo ricevuto.</span><span class="sxs-lookup"><span data-stu-id="3abd2-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="3abd2-122">Di conseguenza, l'evento crea 100 operazioni di magazzino e una voce di costo.</span><span class="sxs-lookup"><span data-stu-id="3abd2-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="3abd2-123">Pagina Voci di costo</span><span class="sxs-lookup"><span data-stu-id="3abd2-123">Cost entries page</span></span>
<span data-ttu-id="3abd2-124">La nuova pagina **Voci di costo** consente di visualizzare e controllare le registrazioni delle quantità e dei costi.</span><span class="sxs-lookup"><span data-stu-id="3abd2-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="3abd2-125">Questa pagina fa da complemento alle pagine **Operazione di magazzino** e **Liquidazione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="3abd2-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="3abd2-126">I record vengono registrati in ordine storico di un evento.</span><span class="sxs-lookup"><span data-stu-id="3abd2-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="3abd2-127">Di conseguenza, è possibile cercare e verificare rapidamente i costi accumulati di un evento specifico o di tutti gli eventi correlati a un documento.</span><span class="sxs-lookup"><span data-stu-id="3abd2-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="3abd2-128">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="3abd2-128">Here is an example:</span></span>

-   <span data-ttu-id="3abd2-129">Un evento dell'entrata prodotti viene registrato per l'articolo A. Cento pezzi vengono ricevuti al costo unitario di 10,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="3abd2-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="3abd2-130">Alcuni giorni dopo che l'evento di fatturazione è stato registrato, il costo aumenta a 11,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="3abd2-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="3abd2-131">Di conseguenza, l'importo totale è 1.100 EUR.</span><span class="sxs-lookup"><span data-stu-id="3abd2-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="3abd2-132">Un secondo giustificativo viene creato per rappresentare la differenza di 100 EUR.</span><span class="sxs-lookup"><span data-stu-id="3abd2-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="3abd2-133">Alcuni giorni dopo spese varie di 15,00 EUR per coprire il costo di trasporto vengono registrate nell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="3abd2-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="3abd2-134">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="3abd2-134">Voucher</span></span> | <span data-ttu-id="3abd2-135">Data</span><span class="sxs-lookup"><span data-stu-id="3abd2-135">Date</span></span>       | <span data-ttu-id="3abd2-136">Riferimento</span><span class="sxs-lookup"><span data-stu-id="3abd2-136">Reference</span></span>      | <span data-ttu-id="3abd2-137">Numero</span><span class="sxs-lookup"><span data-stu-id="3abd2-137">Number</span></span> | <span data-ttu-id="3abd2-138">ID lotto</span><span class="sxs-lookup"><span data-stu-id="3abd2-138">Lot ID</span></span>  | <span data-ttu-id="3abd2-139">Quantità</span><span class="sxs-lookup"><span data-stu-id="3abd2-139">Quantity</span></span> | <span data-ttu-id="3abd2-140">Importo</span><span class="sxs-lookup"><span data-stu-id="3abd2-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="3abd2-141">00001</span><span class="sxs-lookup"><span data-stu-id="3abd2-141">00001</span></span>   | <span data-ttu-id="3abd2-142">01/01/2015</span><span class="sxs-lookup"><span data-stu-id="3abd2-142">01-01-2015</span></span> | <span data-ttu-id="3abd2-143">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="3abd2-143">Purchase order</span></span> | <span data-ttu-id="3abd2-144">100001</span><span class="sxs-lookup"><span data-stu-id="3abd2-144">100001</span></span> | <span data-ttu-id="3abd2-145">0000101</span><span class="sxs-lookup"><span data-stu-id="3abd2-145">0000101</span></span> | <span data-ttu-id="3abd2-146">100,00</span><span class="sxs-lookup"><span data-stu-id="3abd2-146">100.00</span></span>   | <span data-ttu-id="3abd2-147">1000,00</span><span class="sxs-lookup"><span data-stu-id="3abd2-147">1000.00</span></span> |
| <span data-ttu-id="3abd2-148">00002</span><span class="sxs-lookup"><span data-stu-id="3abd2-148">00002</span></span>   | <span data-ttu-id="3abd2-149">20/01/2015</span><span class="sxs-lookup"><span data-stu-id="3abd2-149">20-01-2015</span></span> | <span data-ttu-id="3abd2-150">Ordine acquisto</span><span class="sxs-lookup"><span data-stu-id="3abd2-150">Purchase order</span></span> | <span data-ttu-id="3abd2-151">100001</span><span class="sxs-lookup"><span data-stu-id="3abd2-151">100001</span></span> | <span data-ttu-id="3abd2-152">0000101</span><span class="sxs-lookup"><span data-stu-id="3abd2-152">0000101</span></span> |          | <span data-ttu-id="3abd2-153">100,00</span><span class="sxs-lookup"><span data-stu-id="3abd2-153">100.00</span></span>  |
| <span data-ttu-id="3abd2-154">00003</span><span class="sxs-lookup"><span data-stu-id="3abd2-154">00003</span></span>   | <span data-ttu-id="3abd2-155">31/01/2015</span><span class="sxs-lookup"><span data-stu-id="3abd2-155">31-01-2015</span></span> | <span data-ttu-id="3abd2-156">Correzione</span><span class="sxs-lookup"><span data-stu-id="3abd2-156">Adjustment</span></span>     | <span data-ttu-id="3abd2-157">100001</span><span class="sxs-lookup"><span data-stu-id="3abd2-157">100001</span></span> | <span data-ttu-id="3abd2-158">0000101</span><span class="sxs-lookup"><span data-stu-id="3abd2-158">0000101</span></span> |          | <span data-ttu-id="3abd2-159">15,00</span><span class="sxs-lookup"><span data-stu-id="3abd2-159">15.00</span></span>   |

<span data-ttu-id="3abd2-160">La pagina **Voci di costo** abilita il filtro in base all'ID e alla data del documento.</span><span class="sxs-lookup"><span data-stu-id="3abd2-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="3abd2-161">Le voci di costo sono disponibili solo per gli [oggetti di costo](cost-object.md) o i prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="3abd2-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="see-also"></a><span data-ttu-id="3abd2-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3abd2-162">See also</span></span>
--------

[<span data-ttu-id="3abd2-163">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="3abd2-163">Cost objects</span></span>](cost-object.md)




