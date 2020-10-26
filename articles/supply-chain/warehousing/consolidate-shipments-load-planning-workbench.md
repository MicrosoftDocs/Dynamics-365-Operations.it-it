---
title: Consolidare le spedizioni utilizzando Rilascia in magazzino dal workbench di pianificazione del carico
description: Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino nello stesso carico e vengono quindi automaticamente consolidati in spedizioni.
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
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 2f1dd5c743664e638c043b600ae7b0f6bce5ddcd
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986842"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="c24ac-103">Consolidare le spedizioni utilizzando Rilascia in magazzino dal workbench di pianificazione del carico</span><span class="sxs-lookup"><span data-stu-id="c24ac-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c24ac-104">Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino nello stesso carico e vengono quindi automaticamente consolidati in spedizioni.</span><span class="sxs-lookup"><span data-stu-id="c24ac-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="c24ac-105">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="c24ac-105">Make demo data available</span></span>

<span data-ttu-id="c24ac-106">Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c24ac-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c24ac-107">Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="c24ac-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="c24ac-108">Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti</span><span class="sxs-lookup"><span data-stu-id="c24ac-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="c24ac-109">Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti.</span><span class="sxs-lookup"><span data-stu-id="c24ac-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="c24ac-110">Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.</span><span class="sxs-lookup"><span data-stu-id="c24ac-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="c24ac-111">Crea gli ordini cliente per questo scenario</span><span class="sxs-lookup"><span data-stu-id="c24ac-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="c24ac-112">Inizia creando una raccolta di ordini cliente con cui puoi lavorare.</span><span class="sxs-lookup"><span data-stu-id="c24ac-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="c24ac-113">Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS).</span><span class="sxs-lookup"><span data-stu-id="c24ac-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="c24ac-114">A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.</span><span class="sxs-lookup"><span data-stu-id="c24ac-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="c24ac-115">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c24ac-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="c24ac-116">Crea un insieme di ordini 1</span><span class="sxs-lookup"><span data-stu-id="c24ac-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="c24ac-117">Ordine cliente 1-1</span><span class="sxs-lookup"><span data-stu-id="c24ac-117">Sales order 1-1</span></span>

1. <span data-ttu-id="c24ac-118">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-119">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c24ac-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c24ac-120">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="c24ac-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c24ac-121">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-122">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-123">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-124">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="c24ac-125">Ordine cliente 1-2</span><span class="sxs-lookup"><span data-stu-id="c24ac-125">Sales order 1-2</span></span>

1. <span data-ttu-id="c24ac-126">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-127">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c24ac-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c24ac-128">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="c24ac-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c24ac-129">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-130">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-131">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-132">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="c24ac-133">Ordine cliente 1-3</span><span class="sxs-lookup"><span data-stu-id="c24ac-133">Sales order 1-3</span></span>

1. <span data-ttu-id="c24ac-134">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-135">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c24ac-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c24ac-136">**Modalità di consegna:** *10*</span><span class="sxs-lookup"><span data-stu-id="c24ac-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="c24ac-137">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-138">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-139">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-140">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="c24ac-141">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-142">**Numero articolo:** *A0002* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-143">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="c24ac-144">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="c24ac-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c24ac-145">Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="c24ac-146">Crea un insieme di ordini 2</span><span class="sxs-lookup"><span data-stu-id="c24ac-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="c24ac-147">Ordini cliente 2-1 e 2-2</span><span class="sxs-lookup"><span data-stu-id="c24ac-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="c24ac-148">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c24ac-149">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="c24ac-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="c24ac-150">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-151">**Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)</span><span class="sxs-lookup"><span data-stu-id="c24ac-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="c24ac-152">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-153">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="c24ac-154">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-155">**Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)</span><span class="sxs-lookup"><span data-stu-id="c24ac-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="c24ac-156">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="c24ac-157">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="c24ac-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c24ac-158">Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="c24ac-159">Crea un insieme di ordini 3</span><span class="sxs-lookup"><span data-stu-id="c24ac-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="c24ac-160">Ordini cliente 3-1 e 3-2</span><span class="sxs-lookup"><span data-stu-id="c24ac-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="c24ac-161">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c24ac-162">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c24ac-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c24ac-163">**Richiesta di approvvigionamento cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="c24ac-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="c24ac-164">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-165">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-166">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-167">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="c24ac-168">Ordini cliente 3-3 e 3-4</span><span class="sxs-lookup"><span data-stu-id="c24ac-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="c24ac-169">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c24ac-170">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c24ac-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c24ac-171">**Richiesta di approvvigionamento cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="c24ac-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="c24ac-172">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-173">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-174">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-175">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="c24ac-176">Crea un insieme di ordini 4</span><span class="sxs-lookup"><span data-stu-id="c24ac-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="c24ac-177">Ordini cliente 4-1 e 4-2</span><span class="sxs-lookup"><span data-stu-id="c24ac-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="c24ac-178">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c24ac-179">**Conto cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="c24ac-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="c24ac-180">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-181">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-182">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-183">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="c24ac-184">Ordini cliente 4-3 e 4-4</span><span class="sxs-lookup"><span data-stu-id="c24ac-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="c24ac-185">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c24ac-186">**Conto cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="c24ac-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="c24ac-187">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-188">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-189">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-190">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="c24ac-191">Ordini cliente 4-5 e 4-6</span><span class="sxs-lookup"><span data-stu-id="c24ac-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="c24ac-192">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c24ac-193">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c24ac-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c24ac-194">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="c24ac-194">**Site:** *6*</span></span>
    - <span data-ttu-id="c24ac-195">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="c24ac-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="c24ac-196">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="c24ac-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="c24ac-197">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-198">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-199">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-200">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="c24ac-201">Ordini cliente 4-7 e 4-8</span><span class="sxs-lookup"><span data-stu-id="c24ac-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="c24ac-202">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c24ac-203">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c24ac-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c24ac-204">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="c24ac-204">**Site:** *6*</span></span>
    - <span data-ttu-id="c24ac-205">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="c24ac-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="c24ac-206">**Pool:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="c24ac-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="c24ac-207">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c24ac-208">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="c24ac-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c24ac-209">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c24ac-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c24ac-210">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c24ac-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="c24ac-211">Utilizza il workbench di pianificazione del carico per creare carichi e rilasciarli nel magazzino</span><span class="sxs-lookup"><span data-stu-id="c24ac-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="c24ac-212">Segui questi passaggi per creare un carico per ciascun insieme di ordini creato per questo scenario e quindi rilascialo nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="c24ac-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="c24ac-213">Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="c24ac-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="c24ac-214">Nella scheda **Righe di vendita**, trova e seleziona tutte le righe dell'ordine cliente da uno dei insieme di ordini creati per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="c24ac-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="c24ac-215">Nel riquadro azioni, nella scheda **Domanda e offerta**, seleziona **Aggiungi \> Al nuovo carico** per aggiungere le righe ordine selezionate a un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="c24ac-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="c24ac-216">Nella finestra di dialogo **Assegnazione modello di carico**, nel campo **ID modello carico**, seleziona un modello di caricamento, ad esempio *Modello di caricamento stnd*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="c24ac-217">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c24ac-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="c24ac-218">Nella sezione **Carichi**, trova e seleziona il carico che hai appena creato.</span><span class="sxs-lookup"><span data-stu-id="c24ac-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="c24ac-219">Seleziona **Rilascia \> Rilascia in magazzino** per rilasciare il carico selezionato nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="c24ac-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="c24ac-220">Ripeti questa procedura per gli altri tre insieme di ordini creati per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="c24ac-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="c24ac-221">Verifica le spedizioni</span><span class="sxs-lookup"><span data-stu-id="c24ac-221">Verify the shipments</span></span>

<span data-ttu-id="c24ac-222">La seguente procedura consente di verificare le spedizioni che sono state create o aggiornate a seguito del consolidamento della spedizione.</span><span class="sxs-lookup"><span data-stu-id="c24ac-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="c24ac-223">Usala per rivedere ogni insieme di ordini che hai creato per questo scenario, quindi rivedi le sottosezioni che seguono per assicurarti di aver ottenuto i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="c24ac-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="c24ac-224">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="c24ac-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="c24ac-225">Trova e seleziona la spedizione richiesta.</span><span class="sxs-lookup"><span data-stu-id="c24ac-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="c24ac-226">Se è stato utilizzato un criterio di consolidamento al momento della creazione o dell'aggiornamento della spedizione, dovresti visualizzarlo nel campo **Criteri di consolidamento della spedizione**.</span><span class="sxs-lookup"><span data-stu-id="c24ac-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="c24ac-227">Rilascia insieme di ordini 1 in un carico</span><span class="sxs-lookup"><span data-stu-id="c24ac-227">Release order set 1 in one load</span></span>

<span data-ttu-id="c24ac-228">Dovrebbero essere state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="c24ac-229">La prima spedizione contiene tre righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="c24ac-230">La seconda spedizione, che non utilizza la modalità di trasporto della consegna *Airways*, è stata creata utilizzando i criteri di consolidamento della spedizione *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="c24ac-231">Rilascia insieme di ordini 2 in un carico</span><span class="sxs-lookup"><span data-stu-id="c24ac-231">Release order set 2 in one load</span></span>

<span data-ttu-id="c24ac-232">Dovrebbero essere state create tre spedizioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="c24ac-233">La prima spedizione contiene gli articoli *Infiammabili*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="c24ac-234">Ognuna delle altre due spedizioni contiene una riga che ha l'articolo *Esplosivo*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="c24ac-235">Rilascia insieme di ordini 3 in un carico</span><span class="sxs-lookup"><span data-stu-id="c24ac-235">Release order set 3 in one load</span></span>

<span data-ttu-id="c24ac-236">Dovrebbero essere state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="c24ac-237">La prima spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *1*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="c24ac-238">La seconda spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *2*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="c24ac-239">Rilascia insieme di ordini 4 in un carico</span><span class="sxs-lookup"><span data-stu-id="c24ac-239">Release order set 4 in one load</span></span>

<span data-ttu-id="c24ac-240">Dovrebbero essere state create quattro spedizioni:</span><span class="sxs-lookup"><span data-stu-id="c24ac-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="c24ac-241">Le righe dei due ordini per il conto cliente *US-003* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="c24ac-242">Le righe dei due ordini per il conto cliente *US-004* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="c24ac-243">Le righe dagli ordini cliente 4-5 e 4-6 per il conto cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="c24ac-244">Le righe dagli ordini cliente 4-7 e 4-8 per il conto cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="c24ac-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c24ac-245">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c24ac-245">Additional resources</span></span>

- [<span data-ttu-id="c24ac-246">Criteri consolidamento spedizione</span><span class="sxs-lookup"><span data-stu-id="c24ac-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="c24ac-247">Configurazione dei criteri di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="c24ac-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
