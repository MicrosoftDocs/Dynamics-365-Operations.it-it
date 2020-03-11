---
title: Ordini cliente in Modern POS (MPOS)
description: In questo argomento vengono fornite informazioni sugli ordini cliente in Modern POS (MPOS). Gli ordini cliente sono anche noti come ordini speciali. Questo argomento include una discussione sui parametri e i flussi di transazioni correlati.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b8ea8339c2ad25ceed2415eb5ccf5e2048c612fa
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022999"
---
# <a name="customer-orders-in-modern-pos-mpos"></a><span data-ttu-id="295a7-105">Ordini cliente in Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="295a7-105">Customer orders in Modern POS (MPOS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="295a7-106">In questo argomento vengono fornite informazioni sugli ordini cliente in Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="295a7-106">This topic provides information about customer orders in Modern POS (MPOS).</span></span> <span data-ttu-id="295a7-107">Gli ordini cliente sono anche noti come ordini speciali.</span><span class="sxs-lookup"><span data-stu-id="295a7-107">Customer orders are also known as special orders.</span></span> <span data-ttu-id="295a7-108">Questo argomento include una discussione sui parametri e i flussi di transazioni correlati.</span><span class="sxs-lookup"><span data-stu-id="295a7-108">The topic includes a discussion of related parameters and transaction flows.</span></span>

<span data-ttu-id="295a7-109">In un mondo commerciale omni-canale, molti rivenditori offrono l'opzione degli ordini cliente, o ordini speciali, per soddisfare vari requisiti di prodotti ed evasione.</span><span class="sxs-lookup"><span data-stu-id="295a7-109">In an omni-channel commerce world, many retailers provide the option of customer orders, or special orders, to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="295a7-110">Di seguito sono riportati alcuni scenari comuni:</span><span class="sxs-lookup"><span data-stu-id="295a7-110">Here are some typical scenarios:</span></span>

- <span data-ttu-id="295a7-111">Un cliente desidera che i prodotti siano consegnati a un indirizzo specifico in una data specifica.</span><span class="sxs-lookup"><span data-stu-id="295a7-111">A customer wants products to be delivered to a specific address on a specific date.</span></span>
- <span data-ttu-id="295a7-112">Un cliente desidera prelevare i prodotti da un punto vendita o da una posizione diversa dal punto vendita o posizione in cui il cliente ha acquisito i prodotti.</span><span class="sxs-lookup"><span data-stu-id="295a7-112">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span>
- <span data-ttu-id="295a7-113">Un cliente desidera che qualcun altro prelevi i prodotti che il cliente ha acquistato.</span><span class="sxs-lookup"><span data-stu-id="295a7-113">A customer wants someone else to pick up products that the customer purchased.</span></span>

<span data-ttu-id="295a7-114">I rivenditori utilizzano gli ordini cliente anche per ridurre al minimo le vendite perse che l'esaurimento delle scorte potrebbero causare altrimenti, poiché la merce può essere consegnata o prelevata in una data o in una località diversa.</span><span class="sxs-lookup"><span data-stu-id="295a7-114">Retailers also use customer orders to minimize lost sales that stock outages might otherwise cause, because the merchandise can be delivered or picked up at a different time or place.</span></span>

## <a name="set-up-customer-orders"></a><span data-ttu-id="295a7-115">Impostare gli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="295a7-115">Set up customer orders</span></span>

<span data-ttu-id="295a7-116">Di seguito sono riportati alcuni dei parametri che è possibile impostare nella pagina **Parametri di commercio** per definire la modalità di evasione degli ordini cliente:</span><span class="sxs-lookup"><span data-stu-id="295a7-116">Here are some of the parameters that can be set on the **Commerce parameters** page to define how customer orders are fulfilled:</span></span>

- <span data-ttu-id="295a7-117">**Percentuale di deposito predefinita** - consente di specificare l'importo che il cliente deve pagare come deposito prima che un ordine possa essere confermato.</span><span class="sxs-lookup"><span data-stu-id="295a7-117">**Default deposit percentage** – Specify the amount that the customer must pay as a deposit before an order can be confirmed.</span></span> <span data-ttu-id="295a7-118">L'importo del deposito predefinito viene calcolato come percentuale del valore dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="295a7-118">The default deposit amount is calculated as a percentage of the order value.</span></span> <span data-ttu-id="295a7-119">A seconda dei privilegi, un associato del punto vendita può ignorare l'importo utilizzando **Sostituzione deposito**.</span><span class="sxs-lookup"><span data-stu-id="295a7-119">Depending on privileges, a store associate might be able to override the amount by using **Deposit override**.</span></span>
- <span data-ttu-id="295a7-120">**Percentuale spese di annullamento** - se un addebito verrà applicato quando un ordine cliente viene annullato, specificare l'importo dell'addebito.</span><span class="sxs-lookup"><span data-stu-id="295a7-120">**Cancellation charge percentage** – If a charge will be applied when a customer order is canceled, specify the amount of that charge.</span></span>
- <span data-ttu-id="295a7-121">**Codice spese di annullamento** - se un addebito verrà applicato quando un ordine cliente viene annullato, l'addebito verrà visualizzato con un codice spese nell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="295a7-121">**Cancellation charge code** – If a charge will be applied when a customer order is canceled, that charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="295a7-122">Utilizzare questo parametro per definire il codice spese di annullamento.</span><span class="sxs-lookup"><span data-stu-id="295a7-122">Use this parameter to define the cancellation charge code.</span></span>
- <span data-ttu-id="295a7-123">**Codice spese di spedizione** - rivenditori possono addebitare una commissione supplementare per la spedizione della merce a un cliente.</span><span class="sxs-lookup"><span data-stu-id="295a7-123">**Shipping charge code** – Retailers can charge an extra fee for shipping merchandise to a customer.</span></span> <span data-ttu-id="295a7-124">L'importo delle spese di spedizione verrà visualizzato con un codice spese nell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="295a7-124">The amount of that shipping charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="295a7-125">Utilizzare questo parametro per mappare il codice spese di spedizione alle spese di spedizione nell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="295a7-125">Use this parameter to map the shipping charge code to shipping charges on the customer order.</span></span>
- <span data-ttu-id="295a7-126">**Rimborso spese di spedizione** - consente di specificare se le spese di spedizione associate a un ordine cliente sono rimborsabili.</span><span class="sxs-lookup"><span data-stu-id="295a7-126">**Refund shipping charges** – Specify whether shipping charges that are associated with a customer order are refundable.</span></span>
- <span data-ttu-id="295a7-127">**Importo massimo senza approvazione** - se le spese di spedizione sono rimborsabili, specificare l'importo massimo di rimborsi di spese di spedizione negli ordini di reso.</span><span class="sxs-lookup"><span data-stu-id="295a7-127">**Maximum amount without approval** – If shipping charges are refundable, specify the maximum amount of shipping charge refunds across return orders.</span></span> <span data-ttu-id="295a7-128">Se questo importo viene superato, la sostituzione del responsabile è necessaria per proseguire con il rimborso.</span><span class="sxs-lookup"><span data-stu-id="295a7-128">If this amount is exceeded, manager override is required in order to continue with the refund.</span></span> <span data-ttu-id="295a7-129">Per soddisfare i seguenti scenari, un rimborso delle spese di spedizione può superare l'importo originariamente pagato:</span><span class="sxs-lookup"><span data-stu-id="295a7-129">To accommodate the following scenarios, a refund of shipping charges can exceed the amount that was originally paid:</span></span>

    - <span data-ttu-id="295a7-130">Le spese vengono applicate a livello di intestazione ordine cliente e quando una certa quantità di una riga prodotto viene restituita, il rimborso massimo delle spese di spedizione consentito per i prodotti e la quantità non può essere determinato in un modo che funziona per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="295a7-130">Charges are applied at the level of the sales order header, and when some quantity of a product line is returned, the maximum refund of shipping charges that is allowed for the products and the quantity can't be determined in way that works for all customers.</span></span>
    - <span data-ttu-id="295a7-131">Le spese di spedizione vengono sostenute per ciascuna istanza di spedizione.</span><span class="sxs-lookup"><span data-stu-id="295a7-131">Shipping charges are incurred for every instance of shipping.</span></span> <span data-ttu-id="295a7-132">Se un cliente restituisce più volte dei prodotti e i criteri del rivenditore indicano che il rivenditore sopporterà il costo delle spese di spedizione reso, le spese di spedizione reso saranno superiori alle spese di spedizione effettive.</span><span class="sxs-lookup"><span data-stu-id="295a7-132">If a customer returns products multiple times, and the retailer's policy specifies that the retailer will bear the cost of return shipping charges, the return shipping charges will be more than the actual shipping charges.</span></span>

## <a name="transaction-flow-for-customer-orders"></a><span data-ttu-id="295a7-133">Flusso della transazione per gli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="295a7-133">Transaction flow for customer orders</span></span>

### <a name="create-a-customer-order-in-modern-pos"></a><span data-ttu-id="295a7-134">Creare un ordine cliente in Modern POS</span><span class="sxs-lookup"><span data-stu-id="295a7-134">Create a customer order in Modern POS</span></span>

1. <span data-ttu-id="295a7-135">Aggiungere un cliente alla transazione.</span><span class="sxs-lookup"><span data-stu-id="295a7-135">Add a customer to the transaction.</span></span>
2. <span data-ttu-id="295a7-136">Aggiungere prodotti al carrello.</span><span class="sxs-lookup"><span data-stu-id="295a7-136">Add products to the cart.</span></span>
3. <span data-ttu-id="295a7-137">Fare clic su **Crea ordine cliente** quindi selezionare il tipo di ordine.</span><span class="sxs-lookup"><span data-stu-id="295a7-137">Click **Create customer order**, and then select the order type.</span></span> <span data-ttu-id="295a7-138">Tipo di ordine può essere **Ordine cliente** o **Offerta**.</span><span class="sxs-lookup"><span data-stu-id="295a7-138">The order type can be either **Customer order** or **Quote**.</span></span>
4. <span data-ttu-id="295a7-139">Fare clic su **Spedizione selezionata** o **Spedisci tutto** per spedire i prodotti a un indirizzo nel conto cliente, specificare la data di spedizione richiesta e specificare le spese di spedizione.</span><span class="sxs-lookup"><span data-stu-id="295a7-139">Click **Ship selected** or **Ship all** to ship the products to an address on the customer account, specify the requested shipping date, and specify shipping charges.</span></span>
5. <span data-ttu-id="295a7-140">Fare clic su **Prelievo selezionato** o **Preleva tutto** per selezionare i prodotti che saranno prelevati dal punto vendita corrente o da un punto vendita diverso in una data specifica.</span><span class="sxs-lookup"><span data-stu-id="295a7-140">Click **Pick up selected** or **Pick-up all** to select products that will be picked up from the current store or a different store on a specific date.</span></span>
6. <span data-ttu-id="295a7-141">Incassare l'importo del deposito, se un deposito è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="295a7-141">Collect the deposit amount, if a deposit is required.</span></span>

### <a name="edit-an-existing-customer-order"></a><span data-ttu-id="295a7-142">Modificare un ordine cliente esistente</span><span class="sxs-lookup"><span data-stu-id="295a7-142">Edit an existing customer order</span></span>

1. <span data-ttu-id="295a7-143">Nella home page, fare clic su **Trova ordine**.</span><span class="sxs-lookup"><span data-stu-id="295a7-143">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="295a7-144">Trovare e selezionare l'ordine da modificare.</span><span class="sxs-lookup"><span data-stu-id="295a7-144">Find and select the order to edit.</span></span> <span data-ttu-id="295a7-145">In fondo alla pagina fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="295a7-145">At the bottom of the page, click the **Edit**.</span></span>

### <a name="pick-up-an-order"></a><span data-ttu-id="295a7-146">Prelevare un ordine</span><span class="sxs-lookup"><span data-stu-id="295a7-146">Pick up an order</span></span>

1. <span data-ttu-id="295a7-147">Nella home page, fare clic su **Trova ordine**.</span><span class="sxs-lookup"><span data-stu-id="295a7-147">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="295a7-148">Selezionare l'ordine da prelevare.</span><span class="sxs-lookup"><span data-stu-id="295a7-148">Select the order to pick up.</span></span> <span data-ttu-id="295a7-149">In fondo alla pagina fare clic su **Prelievo e imballaggio**.</span><span class="sxs-lookup"><span data-stu-id="295a7-149">At the bottom of the page, click **Picking and packing**.</span></span>
3. <span data-ttu-id="295a7-150">Fare clic su **Preleva**.</span><span class="sxs-lookup"><span data-stu-id="295a7-150">Click **Pick up**.</span></span>

### <a name="cancel-an-order"></a><span data-ttu-id="295a7-151">Annullare un ordine</span><span class="sxs-lookup"><span data-stu-id="295a7-151">Cancel an order</span></span>

1. <span data-ttu-id="295a7-152">Nella home page, fare clic su **Trova ordine**.</span><span class="sxs-lookup"><span data-stu-id="295a7-152">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="295a7-153">Selezionare l'ordine cliente da annullare.</span><span class="sxs-lookup"><span data-stu-id="295a7-153">Select the order to cancel.</span></span> <span data-ttu-id="295a7-154">In fondo alla pagina fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="295a7-154">At the bottom of the page, click **Cancel**.</span></span>

### <a name="create-a-return-order"></a><span data-ttu-id="295a7-155">Creare un ordine di reso</span><span class="sxs-lookup"><span data-stu-id="295a7-155">Create a return order</span></span>

1. <span data-ttu-id="295a7-156">Nella home page, fare clic su **Trova ordine**.</span><span class="sxs-lookup"><span data-stu-id="295a7-156">On the home page, click **Find an order**.</span></span>
2. <span data-ttu-id="295a7-157">Selezionare l'ordine da restituire, selezionare la fattura per l'ordine quindi selezionare la riga prodotto della merce da restituire.</span><span class="sxs-lookup"><span data-stu-id="295a7-157">Select the order to return, select the invoice for the order, and then select the product line for the merchandise to return.</span></span>
3. <span data-ttu-id="295a7-158">In fondo alla pagina fare clic su **Ordine di reso**.</span><span class="sxs-lookup"><span data-stu-id="295a7-158">At the bottom of the page, click the **Return order**.</span></span>

## <a name="asynchronous-transaction-flow-for-customer-orders"></a><span data-ttu-id="295a7-159">Flusso asincrono della transazione per gli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="295a7-159">Asynchronous transaction flow for customer orders</span></span>

<span data-ttu-id="295a7-160">Gli ordini cliente possono essere creati dal client POS in modalità sincrona o in modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="295a7-160">Customer orders can be created from the point of sale (POS) client in either synchronous mode or asynchronous mode.</span></span>

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a><span data-ttu-id="295a7-161">Abilitare la creazione degli ordini cliente in modalità asincrona</span><span class="sxs-lookup"><span data-stu-id="295a7-161">Enable customer orders to be created in asynchronous mode</span></span>

1. <span data-ttu-id="295a7-162">Fare clic su **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazione POS** &gt; **Profili POS** &gt; **Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="295a7-162">Click **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profile** &gt; **Functionality profiles**.</span></span>
2. <span data-ttu-id="295a7-163">Nella Scheda dettaglio **Generale** , impostare l'opzione **Crea ordine cliente in modalità asincrona** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="295a7-163">On the **General** FastTab, set the **Create customer order in async mode** option to **Yes**.</span></span>

<span data-ttu-id="295a7-164">Quando l'opzione **Crea ordine cliente in modalità asincrona** è impostata su **Sì**, ordini cliente vengono creati sempre in modalità asincrona, anche se Retail Transaction Service (RTS) è disponibile.</span><span class="sxs-lookup"><span data-stu-id="295a7-164">When the **Create customer order in async mode** option is set to **Yes**, customer orders are always created in asynchronous mode, even if Retail Transaction Service (RTS) is available.</span></span> <span data-ttu-id="295a7-165">Se si imposta questa opzione su **No**, ordini cliente vengono creati sempre in modalità sincrona utilizzando RTS.</span><span class="sxs-lookup"><span data-stu-id="295a7-165">If you set this option to **No**, customer orders are always created in synchronous mode by using RTS.</span></span> <span data-ttu-id="295a7-166">Quando gli ordini cliente vengono creati in modalità asincrona, vengono estratti e immessi in Commerce tramite i processi Pull (P).</span><span class="sxs-lookup"><span data-stu-id="295a7-166">When customer orders are created in asynchronous mode, they are pulled and inserted into Commerce by Pull (P) jobs.</span></span> <span data-ttu-id="295a7-167">Gli ordini cliente corrispondenti vengono creati in Commerce quando **Sincronizza ordini** viene eseguito manualmente o tramite un processo batch.</span><span class="sxs-lookup"><span data-stu-id="295a7-167">The corresponding sales orders are created when **Synchronize orders** is run either manually or through a batch process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="295a7-168">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="295a7-168">Additional resources</span></span>

[<span data-ttu-id="295a7-169">Ordini cliente ibridi</span><span class="sxs-lookup"><span data-stu-id="295a7-169">Hybrid customer orders</span></span>](hybrid-customer-orders.md)