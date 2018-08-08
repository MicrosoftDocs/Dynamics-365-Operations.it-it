---
title: Rilascio batch degli ordini di trasferimento parzialmente prenotati
description: In questo argomento viene descritto come impostare e applicare il rilascio batch degli ordini di trasferimento parzialmente prenotati da un dispositivo mobile.
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 578b9875deec077a077b54a9227815e2c4fd3b2d
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="batch-release-of-partially-reserved-transfer-orders"></a><span data-ttu-id="f2cfb-103">Rilascio batch degli ordini di trasferimento parzialmente prenotati</span><span class="sxs-lookup"><span data-stu-id="f2cfb-103">Batch release of partially reserved transfer orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2cfb-104">La funzionalità per il rilascio batch degli ordini di trasferimento parzialmente prenotati consente di rilasciare parzialmente gli ordini di trasferimento a un magazzino utilizzando un processo batch.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-104">The functionality for batch release of partially reserved transfer orders lets you partially release transfer orders to a warehouse by using a batch job.</span></span>
<span data-ttu-id="f2cfb-105">Poiché si ha la possibilità di rilasciare una quantità parziale, non è necessario attendere che l'intera quantità dell'ordine sia disponibile nel magazzino prima di rilasciare un ordine.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-105">Because you have the option to release a partial quantity, you don’t have to wait for the whole order quantity to be available in the warehouse before you release an order.</span></span>

<span data-ttu-id="f2cfb-106">Il rilascio di ordini a un magazzino è un processo di gestione magazzino avanzato.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-106">The release of orders to a warehouse is an advanced warehouse management process.</span></span> <span data-ttu-id="f2cfb-107">Questo processo include attività come prelievo, imballaggio e spedizione che un addetto al magazzino può eseguire mediante un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-107">This process involves activities, such as picking, packing, and shipping, that a warehouse worker can perform by using a mobile device.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="f2cfb-108">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="f2cfb-108">Where it applies</span></span>

<span data-ttu-id="f2cfb-109">Per questa funzionalità, gli ordini di trasferimento vengono rilasciati a un magazzino utilizzando un processo batch.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-109">For this functionality, transfer orders are released to a warehouse by using a batch job.</span></span> <span data-ttu-id="f2cfb-110">Questa funzionalità è utile quando non si hanno scorte sufficienti in magazzino, ma si desidera comunque trasferire articoli da un magazzino a un altro.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-110">This functionality is useful when you don’t have enough inventory in the warehouse, but you still want to transfer items from one warehouse to another.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="f2cfb-111">Come si imposta</span><span class="sxs-lookup"><span data-stu-id="f2cfb-111">How it is set up</span></span>

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="f2cfb-112">Specificare i parametri di evasione per gli ordini di trasferimento e gli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfb-112">Specify fulfillment criteria for transfer orders and sales orders</span></span>

<span data-ttu-id="f2cfb-113">Per poter rilasciare parzialmente un ordine a un magazzino in un batch, è necessario soddisfare i parametri di evasione.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-113">Before an order can be partially released to a warehouse in a batch, the fulfillment criteria must be met.</span></span> <span data-ttu-id="f2cfb-114">Questi parametri di evasione sono determinati dal criterio di evasione.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-114">These fulfillment criteria are determined by the fulfillment policy.</span></span>

<span data-ttu-id="f2cfb-115">I criteri di evasione per gli ordini di trasferimento e gli ordini cliente sono definiti a livello aziendale.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-115">Fulfillment policies for transfer orders and sales orders are specified at the company level.</span></span> <span data-ttu-id="f2cfb-116">A seconda dell'impostazione del criterio di evasione, il rilascio degli ordini in un batch verrà accettato o rifiutato.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-116">Depending on the setup of the fulfillment policy, the release of orders in a batch will be accepted or rejected.</span></span> <span data-ttu-id="f2cfb-117">Gli ordini verranno quindi elaborati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-117">The orders will then be processed accordingly.</span></span>

-   <span data-ttu-id="f2cfb-118">Per creare criteri di evasione per ordini di trasferimento e ordini cliente, fare clic su **Gestione magazzino** \> **Impostazione** \> **Rilascia in magazzino** \> **Criteri di evasione** e quindi creare un criterio di evasione immettendo un nome e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-118">To create fulfillment policies for transfer orders and sales orders, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then create a fulfillment policy by entering a name and a description.</span></span>

-   <span data-ttu-id="f2cfb-119">Per specificare una percentuale di evasione, un tipo di valore e il messaggio visualizzato se il criterio di evasione viene violato, fare clic su **Gestione magazzino** \> **Impostazione** \> **Rilascia in magazzino** \> **Regola di evasione** e quindi impostare i campi **Percentuale evasione**, **Tipo di valore** e **Messaggio di violazione adempimento**.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-119">To specify a fulfillment rate, a value type, and the message that is shown if the fulfillment policy is violated, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then set the **Fulfillment rate**, **Value type**, and **Fulfillment violation message** fields.</span></span>

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="f2cfb-120">Impostare i criteri di evasione per gli ordini di trasferimento e gli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="f2cfb-120">Set the fulfillment policies for transfer orders and sales orders</span></span>

-   <span data-ttu-id="f2cfb-121">Per impostare i criteri di evasione per gli ordini di trasferimento, fare clic su **Gestione articoli** \> **Impostazione** \> **Parametri di gestione articoli e magazzino** \> **Ordini di trasferimento** \> **Gestione magazzino** e selezionare un criterio di evasione per gli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-121">To set the fulfillment policies for transfer orders, click **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters** \> **Transfer orders** \> **Warehouse management**, and then select a transfer order fulfillment policy.</span></span>

-   <span data-ttu-id="f2cfb-122">Per impostare i criteri di evasione per gli ordini cliente, fare clic su **Contabilità clienti** \> **Impostazione** \> **Parametri contabilità clienti** \> **Gestione magazzino** e selezionare un criterio di evasione per gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-122">To set the fulfillment policies for sales orders, click **Accounts receivable** \> **Setup** \> **Accounts receivable parameters** \> **Warehouse management**, and then select a sales order fulfillment policy.</span></span>

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a><span data-ttu-id="f2cfb-123">Consentire il rilascio in un batch e specificare la quantità da rilasciare in un batch</span><span class="sxs-lookup"><span data-stu-id="f2cfb-123">Allow release in a batch and specify the quantity that should be release in a batch</span></span>

<span data-ttu-id="f2cfb-124">Un processo batch viene utilizzato per rilasciare ordini a un magazzino in un batch.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-124">A batch job is used to release orders to a warehouse in a batch.</span></span> <span data-ttu-id="f2cfb-125">I parametri che determinano gli ordini da eseguire in un processo batch vengono impostati nel processo batch stesso.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-125">The parameters that distinguish the orders that should be run in a batch job are set on the batch job itself.</span></span>

<span data-ttu-id="f2cfb-126">Il parametro **Quantità** specifica se l'intera quantità o la quantità prenotata fisicamente deve essere rilasciata nel batch.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-126">The **Quantity** parameter specifies whether the whole quantity or the physically reserved quantity should be released in the batch.</span></span> <span data-ttu-id="f2cfb-127">Il parametro **Consenti rilascio degli ordini parzialmente rilasciati** determina se gli ordini nel batch devono essere accettati o rifiutati nel caso siano stati parzialmente rilasciati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-127">The **Allow release of partially released orders** parameter determines whether orders in the batch should be accepted or rejected if they were partially released earlier.</span></span>

-   <span data-ttu-id="f2cfb-128">Per impostare i parametri **Consenti rilascio degli ordini parzialmente rilasciati** e **Quantità** per gli ordini di trasferimento, fare clic su **Gestione magazzino** \> **Rilascia in magazzino** \> **Rilascio automatico degli ordini di trasferimento**.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-128">To set the **Quantity** and **Allow release of partially released orders** parameters for transfer orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of transfer orders**.</span></span>

-   <span data-ttu-id="f2cfb-129">Per impostare i parametri **Consenti rilascio degli ordini parzialmente rilasciati** e **Quantità** per gli ordini cliente, fare clic su **Gestione magazzino** \> **Rilascia in magazzino** \> **Rilascio automatico degli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="f2cfb-129">To set the **Quantity** and **Allow release of partially released orders** parameters for sales orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of sales orders**.</span></span>

