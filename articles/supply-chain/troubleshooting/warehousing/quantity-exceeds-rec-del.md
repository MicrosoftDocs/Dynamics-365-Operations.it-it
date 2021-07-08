---
title: La quantità che stai tentando di aggiornare supera la quantità ricevuta/consegnata.
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la quantità di lavoro prelevata e prenotata per l'ordine cliente.
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
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249127"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a><span data-ttu-id="78068-103">La quantità che stai tentando di aggiornare supera la quantità ricevuta/consegnata</span><span class="sxs-lookup"><span data-stu-id="78068-103">Quantity that you're trying to update exceeds the received/delivered quantity</span></span>

<span data-ttu-id="78068-104">Codice errore: SYS7676</span><span class="sxs-lookup"><span data-stu-id="78068-104">Error code: SYS7676</span></span>

## <a name="symptoms"></a><span data-ttu-id="78068-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="78068-105">Symptoms</span></span>

<span data-ttu-id="78068-106">Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la quantità di lavoro prelevata e prenotata per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="78068-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the work quantity that was picked and reserved for the sales order.</span></span>

<span data-ttu-id="78068-107">Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="78068-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="78068-108">La quantità che si sta tentando di aggiornare supera quella ricevuta/consegnata.</span><span class="sxs-lookup"><span data-stu-id="78068-108">The quantity that you are trying to update exceeds the quantity received/delivered.</span></span>

<span data-ttu-id="78068-109">Pertanto, non è possibile generare il documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="78068-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="78068-110">Causa</span><span class="sxs-lookup"><span data-stu-id="78068-110">Cause</span></span>

<span data-ttu-id="78068-111">La quantità di lavoro prelevata non corrisponde alla quantità di lavoro creata nella riga di carico.</span><span class="sxs-lookup"><span data-stu-id="78068-111">The picked work quantity doesn't match the created work quantity on the load line.</span></span> <span data-ttu-id="78068-112">Ad esempio, questo problema potrebbe verificarsi se la quantità della riga di carico, la quantità creata dal lavoro o la quantità prelevata non è accurata.</span><span class="sxs-lookup"><span data-stu-id="78068-112">For example, this issue might occur if the load line quantity, work created quantity, or picked quantity isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="78068-113">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="78068-113">Resolution</span></span>

<span data-ttu-id="78068-114">Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce.</span><span class="sxs-lookup"><span data-stu-id="78068-114">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="78068-115">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="78068-115">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="78068-116">Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="78068-116">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="78068-117">Rettifica la quantità della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="78068-117">Adjust the load line quantity.</span></span>
- <span data-ttu-id="78068-118">Storna tutte le registrazioni di prelievo e ripeti il prelievo.</span><span class="sxs-lookup"><span data-stu-id="78068-118">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="78068-119">Esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano</span><span class="sxs-lookup"><span data-stu-id="78068-119">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="78068-120">Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="78068-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="78068-121">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="78068-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="78068-122">Seleziona il carico per cui la spedizione non può essere generata.</span><span class="sxs-lookup"><span data-stu-id="78068-122">Select the load that the shipment can't be generated for.</span></span>
1. <span data-ttu-id="78068-123">Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.</span><span class="sxs-lookup"><span data-stu-id="78068-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="78068-124">Prendi nota del valore del campo **Quantità di lavoro creata**.</span><span class="sxs-lookup"><span data-stu-id="78068-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="78068-125">Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="78068-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="78068-126">Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="78068-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="78068-127">Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="78068-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="78068-128">Rettifica la quantità della riga di carico</span><span class="sxs-lookup"><span data-stu-id="78068-128">Adjust the load line quantity</span></span>

<span data-ttu-id="78068-129">Utilizza la seguente procedura per rettificare la quantità della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="78068-129">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="78068-130">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="78068-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="78068-131">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="78068-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="78068-132">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="78068-132">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="78068-133">Nella scheda  **Righe carico** seleziona la riga di carico per l'articolo che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="78068-133">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="78068-134">Seleziona **Riduci quantità prelevata** per rettificare la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="78068-134">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="78068-135">Imposta il campo **Riduci riga di carico** per riflettere le rettifiche sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="78068-135">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="78068-136">Storna tutte le registrazioni di prelievo e ripeti il prelievo</span><span class="sxs-lookup"><span data-stu-id="78068-136">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="78068-137">Se qualcuno ha utilizzato la registrazione del prelievo per chiudere una riga di carico senza lavoro, può verificarsi una discrepanza tra la quantità della riga di carico e la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="78068-137">If someone used pick registration to close a load line without work, a discrepancy can occur between the load line quantity and the picked quantity.</span></span> <span data-ttu-id="78068-138">In questo caso, è necessario stornare la registrazione del prelievo manuale e completare il prelievo utilizzando l'app per dispositivi mobili Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="78068-138">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="78068-139">Utilizza la seguente procedura per stornare la registrazione del prelievo.</span><span class="sxs-lookup"><span data-stu-id="78068-139">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="78068-140">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini**.</span><span class="sxs-lookup"><span data-stu-id="78068-140">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="78068-141">Selezionare l'ordine cliente per il quale non è possibile registrare un documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="78068-141">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="78068-142">Nella scheda  **Righe ordine cliente** seleziona la riga dell'ordine cliente per cui è stata eseguita la registrazione del prelievo.</span><span class="sxs-lookup"><span data-stu-id="78068-142">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="78068-143">Seleziona **Aggiorna riga \> Prelievo** per annullare il prelievo degli articoli.</span><span class="sxs-lookup"><span data-stu-id="78068-143">Select **Update line \> Pick** to unpick the items.</span></span>
