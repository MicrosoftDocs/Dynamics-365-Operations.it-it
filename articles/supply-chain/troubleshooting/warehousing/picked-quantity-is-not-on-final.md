---
title: Non puoi confermare una spedizione perché gli articoli non sono stati prelevati
description: Non puoi confermare una spedizione perché gli articoli non sono stati prelevati
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301307"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="5ef72-103">Non puoi confermare una spedizione perché gli articoli non sono stati prelevati</span><span class="sxs-lookup"><span data-stu-id="5ef72-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="5ef72-104">Codice di errore: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="5ef72-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="5ef72-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="5ef72-105">Symptoms</span></span>

<span data-ttu-id="5ef72-106">Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="5ef72-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="5ef72-107">Alcuni articoli necessari per il carico %1 non sono stati ancora prelevati e spostati nell'ubicazione di spedizione finale.</span><span class="sxs-lookup"><span data-stu-id="5ef72-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="5ef72-108">Pertanto, non è possibile confermare la spedizione per il carico.</span><span class="sxs-lookup"><span data-stu-id="5ef72-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="5ef72-109">Causa</span><span class="sxs-lookup"><span data-stu-id="5ef72-109">Cause</span></span>

<span data-ttu-id="5ef72-110">Il carico o la spedizione non possono essere confermati nello stato attuale perché potrebbe sussistere una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="5ef72-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="5ef72-111">Il lavoro correlato non è stato ancora prelevato e spostato nell'ubicazione di spedizione finale.</span><span class="sxs-lookup"><span data-stu-id="5ef72-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="5ef72-112">La quantità di lavoro prelevata non corrisponde alla quantità di lavoro creata nella riga di carico.</span><span class="sxs-lookup"><span data-stu-id="5ef72-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="5ef72-113">La direttiva ubicazione è stata configurata con l'ubicazione di imballaggio come ubicazione di spedizione finale durante l'utilizzo della containerizzazione del modello ciclo.</span><span class="sxs-lookup"><span data-stu-id="5ef72-113">The location directive has been configured with packing location as the final shipping location while using Wave template containerization.</span></span>

## <a name="resolution"></a><span data-ttu-id="5ef72-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="5ef72-114">Resolution</span></span>

<span data-ttu-id="5ef72-115">Il carico o la spedizione si trova attualmente in uno stato in cui la conferma della spedizione non riesce.</span><span class="sxs-lookup"><span data-stu-id="5ef72-115">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="5ef72-116">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ef72-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="5ef72-117">Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="5ef72-117">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="5ef72-118">Annulla gli ID lavoro che sono stati creati con l'ubicazione di imballaggio come ubicazione di spedizione finale, riconfigura la direttiva ubicazione e rilascia nuovamente il carico.</span><span class="sxs-lookup"><span data-stu-id="5ef72-118">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="5ef72-119">Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano</span><span class="sxs-lookup"><span data-stu-id="5ef72-119">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="5ef72-120">Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="5ef72-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="5ef72-121">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="5ef72-122">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="5ef72-122">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="5ef72-123">Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.</span><span class="sxs-lookup"><span data-stu-id="5ef72-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="5ef72-124">Prendi nota del valore del campo **Quantità di lavoro creata**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="5ef72-125">Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="5ef72-126">Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="5ef72-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="5ef72-127">Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="5ef72-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a><span data-ttu-id="5ef72-128">Annulla gli ID lavoro che sono stati creati con l'ubicazione di imballaggio come ubicazione di spedizione finale, riconfigura la direttiva ubicazione e rilascia nuovamente il carico</span><span class="sxs-lookup"><span data-stu-id="5ef72-128">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load</span></span>

<span data-ttu-id="5ef72-129">Utilizza la seguente procedura per annullare gli ID lavoro che hanno l'ubicazione di imballaggio come ubicazione di stoccaggio finale con la containerizzazione automatizzata in atto.</span><span class="sxs-lookup"><span data-stu-id="5ef72-129">Use the following procedure to cancel the work IDs that have the packing location as the final put location with automated containerization in place.</span></span>

1. <span data-ttu-id="5ef72-130">Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-130">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="5ef72-131">Viene visualizzata la finestra di dialogo **Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-131">The **Cancel work** dialog opens.</span></span> <span data-ttu-id="5ef72-132">Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="5ef72-132">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span> <span data-ttu-id="5ef72-133">L'ID lavoro selezionato deve avere un valore **Stato lavoro** di *Aperto*, *In corso*, *Annullato*, *Combinato*, o *Chiuso*.</span><span class="sxs-lookup"><span data-stu-id="5ef72-133">The selected work ID must have a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="5ef72-134">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-134">Select **OK**.</span></span>
1. <span data-ttu-id="5ef72-135">Seleziona **Sì** per confermare che desideri annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="5ef72-135">Select **Yes** to confirm that you want to cancel the work.</span></span>
1. <span data-ttu-id="5ef72-136">Ripeti questa procedura per gli altri ID lavoro, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5ef72-136">Repeat this procedure for the other work IDs as needed.</span></span>

<span data-ttu-id="5ef72-137">Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="5ef72-137">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>

<span data-ttu-id="5ef72-138">Utilizza la procedura seguente per riconfigurare la direttiva ubicazione in modo che non utilizzi l'ubicazione di imballaggio come ubicazione di spedizione finale quando viene impostata la containerizzazione automatica per il modello ciclo.</span><span class="sxs-lookup"><span data-stu-id="5ef72-138">Use the following procedure to reconfigure the location directive so it won't use the packing location as the final shipping location when automated containerization is set up for the wave template.</span></span>

1. <span data-ttu-id="5ef72-139">Vai a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-139">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="5ef72-140">Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="5ef72-140">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="5ef72-141">Seleziona la direttiva ubicazione che stai utilizzando per la containerizzazione automatizzata.</span><span class="sxs-lookup"><span data-stu-id="5ef72-141">Select the location directive you are using for automated containerization.</span></span>
1. <span data-ttu-id="5ef72-142">Nella barra degli strumenti della Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-142">On the **Location Directive Actions** FastTab toolbar, select **Edit query**.</span></span>
1. <span data-ttu-id="5ef72-143">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trova la riga in cui **Campo** è impostato su *Profilo ubicazione*, e verifica che il campo **Criteri** per quella riga non sia impostato su un profilo ubicazione che ha un **Tipo di ubicazione** di *Imballaggio*.</span><span class="sxs-lookup"><span data-stu-id="5ef72-143">In the query editor dialog, on the **Range** tab, find the row where **Field** is set to *Location profile*, and verify that the **Criteria** field for that row is not set to a location profile that has a **Location type** of *Packing*.</span></span> <span data-ttu-id="5ef72-144">Rettifica il campo **Criteri** per correggere l'ubicazione di stoccaggio finale.</span><span class="sxs-lookup"><span data-stu-id="5ef72-144">Adjust the **Criteria** field to correct the final put location.</span></span>

<span data-ttu-id="5ef72-145">Utilizza la seguente procedura per rilasciare nuovamente il carico e creare gli ID lavoro con l'ubicazione di spedizione finale corretta.</span><span class="sxs-lookup"><span data-stu-id="5ef72-145">Use the following procedure to rerelease the load and create work IDs with the correct final shipping location.</span></span>

1. <span data-ttu-id="5ef72-146">Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="5ef72-146">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="5ef72-147">Nella sezione **Carichi** trova il carico che deve essere rilasciato.</span><span class="sxs-lookup"><span data-stu-id="5ef72-147">In the **Loads** section, find the load that needs to be released.</span></span>
1. <span data-ttu-id="5ef72-148">Nella barra degli strumenti della sezione **Carichi** seleziona **Rilascia \> Rilascia in magazzino** per rilasciare il carico selezionato nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="5ef72-148">On the **Loads** section toolbar, select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="5ef72-149">Ripeti questa procedura per gli altri carichi, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5ef72-149">Repeat this procedure for the other loads as needed.</span></span>
