---
title: Consolidare le spedizioni manualmente utilizzando la pagina Consolida spedizioni
description: Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente utilizzando la pagina Consolida spedizioni.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: acc6e1d09894b57d2bb063bacbcddef239c1a8bd
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383798"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a><span data-ttu-id="dc31f-103">Consolidare le spedizioni manualmente utilizzando la pagina Consolida spedizioni</span><span class="sxs-lookup"><span data-stu-id="dc31f-103">Consolidate shipments manually by using the Consolidate shipments page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc31f-104">Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente utilizzando la pagina **Consolida spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated later by using the **Consolidate shipments** page.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="dc31f-105">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="dc31f-105">Make demo data available</span></span>

<span data-ttu-id="dc31f-106">Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dc31f-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="dc31f-107">Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="dc31f-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="dc31f-108">Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti</span><span class="sxs-lookup"><span data-stu-id="dc31f-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="dc31f-109">Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti.</span><span class="sxs-lookup"><span data-stu-id="dc31f-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="dc31f-110">Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.</span><span class="sxs-lookup"><span data-stu-id="dc31f-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="dc31f-111">Crea gli ordini cliente per questo scenario</span><span class="sxs-lookup"><span data-stu-id="dc31f-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="dc31f-112">Inizia creando una raccolta di ordini cliente con cui puoi lavorare.</span><span class="sxs-lookup"><span data-stu-id="dc31f-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="dc31f-113">Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS).</span><span class="sxs-lookup"><span data-stu-id="dc31f-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="dc31f-114">A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.</span><span class="sxs-lookup"><span data-stu-id="dc31f-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="dc31f-115">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dc31f-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-sales-orders-1-and-2"></a><span data-ttu-id="dc31f-116">Crea ordini cliente 1 e 2</span><span class="sxs-lookup"><span data-stu-id="dc31f-116">Create sales orders 1 and 2</span></span>

1. <span data-ttu-id="dc31f-117">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dc31f-117">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="dc31f-118">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="dc31f-118">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="dc31f-119">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="dc31f-119">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="dc31f-120">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dc31f-120">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="dc31f-121">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="dc31f-121">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="dc31f-122">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="dc31f-122">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="dc31f-123">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="dc31f-123">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-sales-orders-3-and-4"></a><span data-ttu-id="dc31f-124">Crea ordini cliente 3 e 4</span><span class="sxs-lookup"><span data-stu-id="dc31f-124">Create sales orders 3 and 4</span></span>

1. <span data-ttu-id="dc31f-125">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dc31f-125">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="dc31f-126">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="dc31f-126">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="dc31f-127">**Pool:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="dc31f-127">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="dc31f-128">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dc31f-128">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="dc31f-129">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="dc31f-129">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="dc31f-130">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="dc31f-130">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="dc31f-131">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="dc31f-131">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="dc31f-132">Rilascia gli ordini al magazzino</span><span class="sxs-lookup"><span data-stu-id="dc31f-132">Release the orders to the warehouse</span></span>

<span data-ttu-id="dc31f-133">Segui questi passaggi per rilasciare ciascun ordine cliente creato per questo scenario nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="dc31f-133">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="dc31f-134">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-134">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="dc31f-135">Trova e seleziona l'ordine cliente da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="dc31f-135">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="dc31f-136">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Azioni \> Rilascia in magazzino** per rilasciare l'ordine cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="dc31f-136">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="dc31f-137">Ripeti questa procedura per ogni altro ordine cliente creato per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="dc31f-137">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-shipments"></a><span data-ttu-id="dc31f-138">Consolida spedizioni</span><span class="sxs-lookup"><span data-stu-id="dc31f-138">Consolidate shipments</span></span>

1. <span data-ttu-id="dc31f-139">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-139">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="dc31f-140">Trova e seleziona una spedizione creata quando l'ordine cliente 1 è stato rilasciato al magazzino.</span><span class="sxs-lookup"><span data-stu-id="dc31f-140">Find and select a shipment that was created when sales order 1 was released to the warehouse.</span></span> <span data-ttu-id="dc31f-141">Il campo **Criteri di consolidamento spedizioni** deve essere impostato su *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="dc31f-141">(Its **Shipment consolidation policy** field should be set to *Order pool*.)</span></span>
1. <span data-ttu-id="dc31f-142">Nel riquadro azioni, nella scheda **Spedizioni**, seleziona **Spedizioni \> Consolida spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-142">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="dc31f-143">Verifica le spedizioni consigliate per il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="dc31f-143">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="dc31f-144">Solo una spedizione con gli stessi criteri deve essere suggerita per il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="dc31f-144">Only one shipment that has the same policy should be suggested for consolidation.</span></span>
1. <span data-ttu-id="dc31f-145">Chiudi la pagina **Consolidamento spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-145">Close the **Shipment consolidation** page.</span></span>
1. <span data-ttu-id="dc31f-146">Trova e seleziona una spedizione creata quando l'ordine cliente 3 è stato rilasciato al magazzino.</span><span class="sxs-lookup"><span data-stu-id="dc31f-146">Find and select a shipment that was created when sales order 3 was released to the warehouse.</span></span> <span data-ttu-id="dc31f-147">Il campo **Criteri di consolidamento spedizioni** deve essere impostato su *Predefinito*.</span><span class="sxs-lookup"><span data-stu-id="dc31f-147">(Its **Shipment consolidation policy** field should be set to *Default*.)</span></span>
1. <span data-ttu-id="dc31f-148">Nel riquadro azioni, nella scheda **Spedizioni**, seleziona **Spedizioni \> Consolida spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-148">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="dc31f-149">Verifica che le spedizioni siano consigliate per il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="dc31f-149">Verify that no shipments are suggested for consolidation.</span></span>
1. <span data-ttu-id="dc31f-150">Seleziona **Mostra filtri**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-150">Select **Show filters**.</span></span>
1. <span data-ttu-id="dc31f-151">Nel riquadro **Filtri**, rimuovere il filtro **Numero ordine** e seleziona **Applica**.</span><span class="sxs-lookup"><span data-stu-id="dc31f-151">In the **Filters** pane, remove the **Order number** filter, and then select **Apply**.</span></span>
1. <span data-ttu-id="dc31f-152">Verifica le spedizioni consigliate per il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="dc31f-152">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="dc31f-153">Solo una spedizione con gli stessi criteri deve essere suggerita per il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="dc31f-153">Only one shipment that has the same policy should be suggested for consolidation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dc31f-154">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dc31f-154">Additional resources</span></span>

- [<span data-ttu-id="dc31f-155">Criteri consolidamento spedizione</span><span class="sxs-lookup"><span data-stu-id="dc31f-155">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="dc31f-156">Configurazione dei criteri di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="dc31f-156">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)