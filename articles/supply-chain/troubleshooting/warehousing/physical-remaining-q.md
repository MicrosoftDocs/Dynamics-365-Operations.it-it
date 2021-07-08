---
title: La quantità fisica residua nell'unità non deve essere zero
description: Quando si genera un documento di trasporto, i dati forniti hanno una quantità di inventario diversa da zero e una quantità di vendita pari a zero.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248788"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a><span data-ttu-id="db8bf-103">La quantità fisica residua nell'unità non deve essere zero</span><span class="sxs-lookup"><span data-stu-id="db8bf-103">Physical remaining quantity in the unit must not be zero</span></span>

<span data-ttu-id="db8bf-104">Codice errore: SYS19591</span><span class="sxs-lookup"><span data-stu-id="db8bf-104">Error code: SYS19591</span></span>

## <a name="symptoms"></a><span data-ttu-id="db8bf-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="db8bf-105">Symptoms</span></span>

<span data-ttu-id="db8bf-106">Quando si genera un documento di trasporto, i dati forniti hanno una quantità di inventario diversa da zero e una quantità di vendita pari a zero.</span><span class="sxs-lookup"><span data-stu-id="db8bf-106">When you generate a packing slip, the data that is supplied to it has a non-zero inventory quantity but a zero sales quantity.</span></span>

<span data-ttu-id="db8bf-107">Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="db8bf-107">When you try to generate the packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="db8bf-108">La quantità fisica rimanente nell'unità %1 deve essere diversa da zero.</span><span class="sxs-lookup"><span data-stu-id="db8bf-108">Physical remaining quantity in the unit %1 must be other than zero.</span></span>

<span data-ttu-id="db8bf-109">Pertanto, non è possibile generare il documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="db8bf-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="db8bf-110">Causa</span><span class="sxs-lookup"><span data-stu-id="db8bf-110">Cause</span></span>

<span data-ttu-id="db8bf-111">Il sistema valuta la quantità fisica rimanente nell'unità di magazzino e la quantità fisica rimanente nell'unità di spedizione.</span><span class="sxs-lookup"><span data-stu-id="db8bf-111">The system evaluates the physical remaining quantity in the inventory unit and the physical remaining quantity in the shipping unit.</span></span> <span data-ttu-id="db8bf-112">Se il sistema rileva che la quantità fisica rimanente nell'unità di spedizione è 0 (zero), ma la quantità fisica rimanente nell'unità di magazzino non è 0, non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="db8bf-112">If the system finds that the physical remaining quantity in the shipping unit is 0 (zero), but the physical remaining quantity in the inventory unit isn't 0, you can't generate the packing slip.</span></span> <span data-ttu-id="db8bf-113">Ad esempio, questo problema potrebbe verificarsi se l'unità di vendita e l'unità di magazzino per l'articolo differiscono e la conversione tra le unità non è accurata.</span><span class="sxs-lookup"><span data-stu-id="db8bf-113">For example, this issue might occur if the sales unit and inventory unit for the item differ, and the conversion between units isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="db8bf-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="db8bf-114">Resolution</span></span>

<span data-ttu-id="db8bf-115">Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce.</span><span class="sxs-lookup"><span data-stu-id="db8bf-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="db8bf-116">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="db8bf-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="db8bf-117">Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="db8bf-117">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="db8bf-118">Rivedi le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza problemi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="db8bf-118">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>
- <span data-ttu-id="db8bf-119">Rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità.</span><span class="sxs-lookup"><span data-stu-id="db8bf-119">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>
- <span data-ttu-id="db8bf-120">Assicurati che l'unità di misura del magazzino sia inferiore all'unità di misura di vendita.</span><span class="sxs-lookup"><span data-stu-id="db8bf-120">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="db8bf-121">Esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano</span><span class="sxs-lookup"><span data-stu-id="db8bf-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="db8bf-122">Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="db8bf-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="db8bf-123">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="db8bf-124">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="db8bf-124">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="db8bf-125">Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.</span><span class="sxs-lookup"><span data-stu-id="db8bf-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="db8bf-126">Prendi nota del valore del campo **Quantità di lavoro creata**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="db8bf-127">Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="db8bf-128">Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="db8bf-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="db8bf-129">Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="db8bf-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a><span data-ttu-id="db8bf-130">Rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza problemi di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="db8bf-130">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues</span></span>

<span data-ttu-id="db8bf-131">Usa la seguente procedura per rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza problemi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="db8bf-131">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>

1. <span data-ttu-id="db8bf-132">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="db8bf-133">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="db8bf-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="db8bf-134">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="db8bf-135">Nella scheda  **Righe di carico**, seleziona la riga di carico dell'articolo che supera il limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="db8bf-135">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery.</span></span>
1. <span data-ttu-id="db8bf-136">Seleziona **Riduci quantità prelevata** per rettificare la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="db8bf-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="db8bf-137">Nella scheda  **Dettagli riga** seleziona **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-137">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="db8bf-138">Imposta il campo **Quantità** sulla quantità prelevata (ovvero, il valore del campo **Quantità di lavoro creata**), in modo che possa procedere la generazione del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="db8bf-138">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="db8bf-139">Rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità</span><span class="sxs-lookup"><span data-stu-id="db8bf-139">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="db8bf-140">Usa la seguente procedura per rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità.</span><span class="sxs-lookup"><span data-stu-id="db8bf-140">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="db8bf-141">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-141">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="db8bf-142">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="db8bf-142">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="db8bf-143">Nella scheda dettaglio **Righe carico** seleziona la riga di carico per l'articolo che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="db8bf-143">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="db8bf-144">Prendi nota del valore dei campi **Quantità** e **Unità**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-144">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="db8bf-145">Vai a **Amministrazione organizzazione \> Unità \> Unità**.</span><span class="sxs-lookup"><span data-stu-id="db8bf-145">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="db8bf-146">Seleziona l'unità per la quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="db8bf-146">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="db8bf-147">Rettifica il valore del campo **Precisione decimale** come richiesto.</span><span class="sxs-lookup"><span data-stu-id="db8bf-147">Adjust the value of the **Decimal precision** field as required.</span></span>

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a><span data-ttu-id="db8bf-148">Assicurarsi che l'unità di misura del magazzino sia inferiore all'unità di misura di vendita</span><span class="sxs-lookup"><span data-stu-id="db8bf-148">Make sure that the inventory unit of measure is smaller than the sales unit of measure</span></span>

<span data-ttu-id="db8bf-149">Assicurati che l'unità di misura del magazzino sia inferiore all'unità di misura di vendita.</span><span class="sxs-lookup"><span data-stu-id="db8bf-149">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span> <span data-ttu-id="db8bf-150">Considera la riconfigurazione dell'unità di misura dell'articolo come richiesto.</span><span class="sxs-lookup"><span data-stu-id="db8bf-150">Consider reconfiguring the unit of measure for the item as required.</span></span>
