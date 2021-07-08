---
title: La quantità prelevata non è sufficiente durante la generazione del documento di trasporto
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità prelevata che non corrisponde alla quantità di lavoro creata nella riga di carico.
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
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249126"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a><span data-ttu-id="4336f-103">La quantità prelevata non è sufficiente durante la generazione del documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="4336f-103">Picked quantity isn't sufficient during packing slip generation</span></span>

<span data-ttu-id="4336f-104">Codice errore: SYS54073</span><span class="sxs-lookup"><span data-stu-id="4336f-104">Error code: SYS54073</span></span>

## <a name="symptoms"></a><span data-ttu-id="4336f-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="4336f-105">Symptoms</span></span>

<span data-ttu-id="4336f-106">Quando si genera un documento di trasporto, il carico in uscita contiene una quantità prelevata che non corrisponde alla quantità di lavoro creata nella riga di carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-106">When you generate a packing slip, the outbound load contains a picked quantity that doesn't match the created work quantity on the load line.</span></span>

<span data-ttu-id="4336f-107">Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="4336f-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="4336f-108">Poiché è stata prelevata una quantità di %1, non è sufficiente aggiornare %2 quando, conseguentemente, la quantità rimanente deve essere %3.</span><span class="sxs-lookup"><span data-stu-id="4336f-108">As %1 have been picked, it is not sufficient to update %2, when, subsequently, the remainder must be %3.</span></span>

<span data-ttu-id="4336f-109">Pertanto, non è possibile generare il documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="4336f-110">Causa</span><span class="sxs-lookup"><span data-stu-id="4336f-110">Cause</span></span>

<span data-ttu-id="4336f-111">Il documento di trasporto non può essere generato nello stato attuale perché potrebbe sussistere una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="4336f-111">The packing slip can't be generated in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="4336f-112">Il lavoro correlato non è stato ancora prelevato e spostato nell'ubicazione di spedizione finale.</span><span class="sxs-lookup"><span data-stu-id="4336f-112">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="4336f-113">La quantità di lavoro prelevata non corrisponde alla quantità di lavoro creata nella riga di carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-113">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="4336f-114">La quantità della riga di carico, la quantità di lavoro creata e la quantità prelevata non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="4336f-114">The load line quantity, work created quantity, and picked quantity don't match.</span></span>

## <a name="resolution"></a><span data-ttu-id="4336f-115">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="4336f-115">Resolution</span></span>

<span data-ttu-id="4336f-116">Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce.</span><span class="sxs-lookup"><span data-stu-id="4336f-116">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="4336f-117">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4336f-117">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="4336f-118">Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="4336f-118">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="4336f-119">Rettifica la quantità della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-119">Adjust the load line quantity.</span></span>
- <span data-ttu-id="4336f-120">Storna tutte le registrazioni di prelievo e ripeti il prelievo.</span><span class="sxs-lookup"><span data-stu-id="4336f-120">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="4336f-121">Esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano</span><span class="sxs-lookup"><span data-stu-id="4336f-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="4336f-122">Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="4336f-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="4336f-123">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="4336f-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="4336f-124">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4336f-124">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="4336f-125">Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="4336f-126">Prendi nota del valore del campo **Quantità di lavoro creata**.</span><span class="sxs-lookup"><span data-stu-id="4336f-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="4336f-127">Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="4336f-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="4336f-128">Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="4336f-129">Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="4336f-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="4336f-130">Rettifica la quantità della riga di carico</span><span class="sxs-lookup"><span data-stu-id="4336f-130">Adjust the load line quantity</span></span>

<span data-ttu-id="4336f-131">Utilizza la seguente procedura per rettificare la quantità della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-131">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="4336f-132">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="4336f-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="4336f-133">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="4336f-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="4336f-134">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="4336f-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="4336f-135">Nella scheda  **Righe carico** seleziona la riga di carico per l'articolo che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="4336f-135">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="4336f-136">Seleziona **Riduci quantità prelevata** per rettificare la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="4336f-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="4336f-137">Imposta il campo **Riduci riga di carico** per riflettere le rettifiche sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-137">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="4336f-138">Storna tutte le registrazioni di prelievo e ripeti il prelievo</span><span class="sxs-lookup"><span data-stu-id="4336f-138">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="4336f-139">Il problema potrebbe verificarsi perché qualcuno ha utilizzato la registrazione del prelievo per chiudere una riga di carico senza lavoro.</span><span class="sxs-lookup"><span data-stu-id="4336f-139">The issue might occur because someone used pick registration to close a load line without work.</span></span> <span data-ttu-id="4336f-140">In questo caso, è necessario stornare la registrazione del prelievo manuale e completare il prelievo utilizzando l'app per dispositivi mobili Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="4336f-140">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="4336f-141">Utilizza la seguente procedura per stornare la registrazione del prelievo.</span><span class="sxs-lookup"><span data-stu-id="4336f-141">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="4336f-142">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini**.</span><span class="sxs-lookup"><span data-stu-id="4336f-142">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="4336f-143">Selezionare l'ordine cliente per il quale non è possibile registrare un documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="4336f-143">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="4336f-144">Nella scheda  **Righe ordine cliente** seleziona la riga dell'ordine cliente per cui è stata eseguita la registrazione del prelievo.</span><span class="sxs-lookup"><span data-stu-id="4336f-144">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="4336f-145">Seleziona **Aggiorna riga \> Prelievo** per annullare il prelievo degli articoli.</span><span class="sxs-lookup"><span data-stu-id="4336f-145">Select **Update line \> Pick** to unpick the items.</span></span>
