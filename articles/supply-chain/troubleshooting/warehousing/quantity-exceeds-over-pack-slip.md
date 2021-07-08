---
title: La quantità supera la percentuale di limite massimo di fornitura durante la generazione del documento di trasporto
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la percentuale di limite massimo di fornitura.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249124"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="c97c8-103">La quantità supera la percentuale di limite massimo di fornitura durante la generazione del documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="c97c8-103">Quantity exceeds over-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="c97c8-104">Codice errore: SYS24920</span><span class="sxs-lookup"><span data-stu-id="c97c8-104">Error code: SYS24920</span></span>

## <a name="symptoms"></a><span data-ttu-id="c97c8-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="c97c8-105">Symptoms</span></span>

<span data-ttu-id="c97c8-106">Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="c97c8-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the over-delivery percentage.</span></span>

<span data-ttu-id="c97c8-107">Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="c97c8-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="c97c8-108">Il limite massimo di fornitura della riga è pari al %1 percento, mentre quello consentito è solo del %2 percento.</span><span class="sxs-lookup"><span data-stu-id="c97c8-108">Overdelivery of line is %1 percent, but the allowed overdelivery is only %2 percent.</span></span>

<span data-ttu-id="c97c8-109">Pertanto, non è possibile generare il documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="c97c8-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="c97c8-110">Causa</span><span class="sxs-lookup"><span data-stu-id="c97c8-110">Cause</span></span>

<span data-ttu-id="c97c8-111">La quantità prelevata per il carico o la spedizione è maggiore della quantità ordinata e non rientra nell'intervallo della percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="c97c8-111">The picked quantity for the load or shipment is more than the ordered quantity and isn't within the range of the over-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="c97c8-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="c97c8-112">Resolution</span></span>

<span data-ttu-id="c97c8-113">Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce.</span><span class="sxs-lookup"><span data-stu-id="c97c8-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="c97c8-114">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c97c8-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="c97c8-115">Rettifica la quantità della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="c97c8-115">Adjust the load line quantity.</span></span>
- <span data-ttu-id="c97c8-116">Rettifica la percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="c97c8-116">Adjust the over-delivery percentage.</span></span>
- <span data-ttu-id="c97c8-117">Storna e apporta rettifiche.</span><span class="sxs-lookup"><span data-stu-id="c97c8-117">Reverse and make adjustments.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="c97c8-118">Rettifica la quantità della riga di carico</span><span class="sxs-lookup"><span data-stu-id="c97c8-118">Adjust the load line quantity</span></span>

<span data-ttu-id="c97c8-119">Utilizza la seguente procedura per rettificare la quantità della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="c97c8-119">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="c97c8-120">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-120">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c97c8-121">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c97c8-121">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="c97c8-122">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-122">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="c97c8-123">Nella scheda  **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="c97c8-123">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="c97c8-124">Seleziona **Riduci quantità prelevata** per rettificare la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="c97c8-124">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="c97c8-125">Nella scheda  **Dettagli riga** seleziona **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-125">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="c97c8-126">Imposta il campo **Quantità** sulla quantità prelevata (ovvero, il valore del campo **Quantità di lavoro creata**), in modo che possa procedere la generazione del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c97c8-126">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="adjust-the-over-delivery-percentage"></a><span data-ttu-id="c97c8-127">Rettifica la percentuale di limite massimo di fornitura</span><span class="sxs-lookup"><span data-stu-id="c97c8-127">Adjust the over-delivery percentage</span></span>

<span data-ttu-id="c97c8-128">Utilizza la seguente procedura per rettificare la percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="c97c8-128">Use the following procedure to adjust the over-delivery percentage.</span></span>

1. <span data-ttu-id="c97c8-129">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-129">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="c97c8-130">Selezionare l'ordine cliente per il quale non è possibile registrare un documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="c97c8-130">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="c97c8-131">Nella scheda  **Righe ordine cliente**, seleziona la riga ordine cliente dell'articolo che supera la percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="c97c8-131">On the **Sales order lines** tab, select the sales order line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="c97c8-132">Nella scheda  **Dettagli riga** seleziona **Consegna**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-132">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="c97c8-133">Imposta il campo **Limite massimo di fornitura** su una percentuale maggiore che tiene conto della quantità prelevata rispetto alla quantità di carico, in modo che possa procedere la generazione del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c97c8-133">Set the **Overdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="c97c8-134">Storna e apporta rettifiche</span><span class="sxs-lookup"><span data-stu-id="c97c8-134">Reverse and make adjustments</span></span>

<span data-ttu-id="c97c8-135">Storna tutto ciò che è stato registrato per il carico (ad esempio, documento di trasporto, conferma di spedizione e lavoro), apporta le rettifiche all'ordine di vendita, rilascia nuovamente l'ordine al magazzino e completa la procedura di spedizione.</span><span class="sxs-lookup"><span data-stu-id="c97c8-135">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="c97c8-136">Utilizza la seguente procedura per annullare un documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="c97c8-136">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="c97c8-137">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-137">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c97c8-138">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Annulla documenti di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-138">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="c97c8-139">Utilizza la seguente procedura per stornare una conferma di spedizione.</span><span class="sxs-lookup"><span data-stu-id="c97c8-139">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="c97c8-140">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-140">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c97c8-141">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-141">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="c97c8-142">Utilizza la seguente procedura per stornare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="c97c8-142">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="c97c8-143">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-143">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c97c8-144">Nella scheda  **Lavoro** del riquadro azioni, nel gruppo  **Carichi**, seleziona  **Storna lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c97c8-144">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
