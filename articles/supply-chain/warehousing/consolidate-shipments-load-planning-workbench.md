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
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 396a038dbf2f4b6835ecbb5fd8cb39a3a3608af7
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383802"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="61bfe-103">Consolidare le spedizioni utilizzando Rilascia in magazzino dal workbench di pianificazione del carico</span><span class="sxs-lookup"><span data-stu-id="61bfe-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61bfe-104">Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino nello stesso carico e vengono quindi automaticamente consolidati in spedizioni.</span><span class="sxs-lookup"><span data-stu-id="61bfe-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="61bfe-105">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="61bfe-105">Make demo data available</span></span>

<span data-ttu-id="61bfe-106">Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="61bfe-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="61bfe-107">Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="61bfe-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="61bfe-108">Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti</span><span class="sxs-lookup"><span data-stu-id="61bfe-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="61bfe-109">Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti.</span><span class="sxs-lookup"><span data-stu-id="61bfe-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="61bfe-110">Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.</span><span class="sxs-lookup"><span data-stu-id="61bfe-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="61bfe-111">Crea gli ordini cliente per questo scenario</span><span class="sxs-lookup"><span data-stu-id="61bfe-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="61bfe-112">Inizia creando una raccolta di ordini cliente con cui puoi lavorare.</span><span class="sxs-lookup"><span data-stu-id="61bfe-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="61bfe-113">Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS).</span><span class="sxs-lookup"><span data-stu-id="61bfe-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="61bfe-114">A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.</span><span class="sxs-lookup"><span data-stu-id="61bfe-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="61bfe-115">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="61bfe-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="61bfe-116">Crea un insieme di ordini 1</span><span class="sxs-lookup"><span data-stu-id="61bfe-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="61bfe-117">Ordine cliente 1-1</span><span class="sxs-lookup"><span data-stu-id="61bfe-117">Sales order 1-1</span></span>

1. <span data-ttu-id="61bfe-118">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-119">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="61bfe-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="61bfe-120">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="61bfe-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="61bfe-121">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-122">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-123">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-124">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="61bfe-125">Ordine cliente 1-2</span><span class="sxs-lookup"><span data-stu-id="61bfe-125">Sales order 1-2</span></span>

1. <span data-ttu-id="61bfe-126">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-127">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="61bfe-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="61bfe-128">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="61bfe-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="61bfe-129">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-130">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-131">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-132">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="61bfe-133">Ordine cliente 1-3</span><span class="sxs-lookup"><span data-stu-id="61bfe-133">Sales order 1-3</span></span>

1. <span data-ttu-id="61bfe-134">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-135">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="61bfe-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="61bfe-136">**Modalità di consegna:** *10*</span><span class="sxs-lookup"><span data-stu-id="61bfe-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="61bfe-137">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-138">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-139">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-140">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="61bfe-141">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-142">**Numero articolo:** *A0002* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-143">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="61bfe-144">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="61bfe-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="61bfe-145">Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="61bfe-146">Crea un insieme di ordini 2</span><span class="sxs-lookup"><span data-stu-id="61bfe-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="61bfe-147">Ordini cliente 2-1 e 2-2</span><span class="sxs-lookup"><span data-stu-id="61bfe-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="61bfe-148">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="61bfe-149">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="61bfe-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="61bfe-150">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-151">**Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)</span><span class="sxs-lookup"><span data-stu-id="61bfe-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="61bfe-152">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-153">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="61bfe-154">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-155">**Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)</span><span class="sxs-lookup"><span data-stu-id="61bfe-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="61bfe-156">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="61bfe-157">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="61bfe-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="61bfe-158">Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="61bfe-159">Crea un insieme di ordini 3</span><span class="sxs-lookup"><span data-stu-id="61bfe-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="61bfe-160">Ordini cliente 3-1 e 3-2</span><span class="sxs-lookup"><span data-stu-id="61bfe-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="61bfe-161">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="61bfe-162">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="61bfe-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="61bfe-163">**Richiesta di approvvigionamento cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="61bfe-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="61bfe-164">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-165">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-166">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-167">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="61bfe-168">Ordini cliente 3-3 e 3-4</span><span class="sxs-lookup"><span data-stu-id="61bfe-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="61bfe-169">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="61bfe-170">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="61bfe-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="61bfe-171">**Richiesta di approvvigionamento cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="61bfe-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="61bfe-172">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-173">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-174">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-175">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="61bfe-176">Crea un insieme di ordini 4</span><span class="sxs-lookup"><span data-stu-id="61bfe-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="61bfe-177">Ordini cliente 4-1 e 4-2</span><span class="sxs-lookup"><span data-stu-id="61bfe-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="61bfe-178">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="61bfe-179">**Conto cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="61bfe-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="61bfe-180">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-181">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-182">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-183">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="61bfe-184">Ordini cliente 4-3 e 4-4</span><span class="sxs-lookup"><span data-stu-id="61bfe-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="61bfe-185">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="61bfe-186">**Conto cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="61bfe-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="61bfe-187">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-188">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-189">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-190">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="61bfe-191">Ordini cliente 4-5 e 4-6</span><span class="sxs-lookup"><span data-stu-id="61bfe-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="61bfe-192">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="61bfe-193">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="61bfe-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="61bfe-194">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="61bfe-194">**Site:** *6*</span></span>
    - <span data-ttu-id="61bfe-195">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="61bfe-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="61bfe-196">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="61bfe-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="61bfe-197">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-198">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-199">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-200">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="61bfe-201">Ordini cliente 4-7 e 4-8</span><span class="sxs-lookup"><span data-stu-id="61bfe-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="61bfe-202">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="61bfe-203">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="61bfe-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="61bfe-204">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="61bfe-204">**Site:** *6*</span></span>
    - <span data-ttu-id="61bfe-205">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="61bfe-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="61bfe-206">**Pool:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="61bfe-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="61bfe-207">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="61bfe-208">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="61bfe-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="61bfe-209">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="61bfe-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="61bfe-210">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61bfe-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="61bfe-211">Utilizza il workbench di pianificazione del carico per creare carichi e rilasciarli nel magazzino</span><span class="sxs-lookup"><span data-stu-id="61bfe-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="61bfe-212">Segui questi passaggi per creare un carico per ciascun insieme di ordini creato per questo scenario e quindi rilascialo nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="61bfe-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="61bfe-213">Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="61bfe-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="61bfe-214">Nella scheda **Righe di vendita**, trova e seleziona tutte le righe dell'ordine cliente da uno dei insieme di ordini creati per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="61bfe-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="61bfe-215">Nel riquadro azioni, nella scheda **Domanda e offerta**, seleziona **Aggiungi \> Al nuovo carico** per aggiungere le righe ordine selezionate a un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="61bfe-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="61bfe-216">Nella finestra di dialogo **Assegnazione modello di carico**, nel campo **ID modello carico**, seleziona un modello di caricamento, ad esempio *Modello di caricamento stnd*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="61bfe-217">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="61bfe-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="61bfe-218">Nella sezione **Carichi**, trova e seleziona il carico che hai appena creato.</span><span class="sxs-lookup"><span data-stu-id="61bfe-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="61bfe-219">Seleziona **Rilascia \> Rilascia in magazzino** per rilasciare il carico selezionato nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="61bfe-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="61bfe-220">Ripeti questa procedura per gli altri tre insieme di ordini creati per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="61bfe-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="61bfe-221">Verifica le spedizioni</span><span class="sxs-lookup"><span data-stu-id="61bfe-221">Verify the shipments</span></span>

<span data-ttu-id="61bfe-222">La seguente procedura consente di verificare le spedizioni che sono state create o aggiornate a seguito del consolidamento della spedizione.</span><span class="sxs-lookup"><span data-stu-id="61bfe-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="61bfe-223">Usala per rivedere ogni insieme di ordini che hai creato per questo scenario, quindi rivedi le sottosezioni che seguono per assicurarti di aver ottenuto i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="61bfe-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="61bfe-224">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="61bfe-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="61bfe-225">Trova e seleziona la spedizione richiesta.</span><span class="sxs-lookup"><span data-stu-id="61bfe-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="61bfe-226">Se è stato utilizzato un criterio di consolidamento al momento della creazione o dell'aggiornamento della spedizione, dovresti visualizzarlo nel campo **Criteri di consolidamento della spedizione**.</span><span class="sxs-lookup"><span data-stu-id="61bfe-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="61bfe-227">Rilascia insieme di ordini 1 in un carico</span><span class="sxs-lookup"><span data-stu-id="61bfe-227">Release order set 1 in one load</span></span>

<span data-ttu-id="61bfe-228">Dovrebbero essere state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="61bfe-229">La prima spedizione contiene tre righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="61bfe-230">La seconda spedizione, che non utilizza la modalità di trasporto della consegna *Airways*, è stata creata utilizzando i criteri di consolidamento della spedizione *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="61bfe-231">Rilascia insieme di ordini 2 in un carico</span><span class="sxs-lookup"><span data-stu-id="61bfe-231">Release order set 2 in one load</span></span>

<span data-ttu-id="61bfe-232">Dovrebbero essere state create tre spedizioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="61bfe-233">La prima spedizione contiene gli articoli *Infiammabili*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="61bfe-234">Ognuna delle altre due spedizioni contiene una riga che ha l'articolo *Esplosivo*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="61bfe-235">Rilascia insieme di ordini 3 in un carico</span><span class="sxs-lookup"><span data-stu-id="61bfe-235">Release order set 3 in one load</span></span>

<span data-ttu-id="61bfe-236">Dovrebbero essere state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="61bfe-237">La prima spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *1*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="61bfe-238">La seconda spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *2*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="61bfe-239">Rilascia insieme di ordini 4 in un carico</span><span class="sxs-lookup"><span data-stu-id="61bfe-239">Release order set 4 in one load</span></span>

<span data-ttu-id="61bfe-240">Dovrebbero essere state create quattro spedizioni:</span><span class="sxs-lookup"><span data-stu-id="61bfe-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="61bfe-241">Le righe dei due ordini per il conto cliente *US-003* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="61bfe-242">Le righe dei due ordini per il conto cliente *US-004* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="61bfe-243">Le righe dagli ordini cliente 4-5 e 4-6 per il conto cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="61bfe-244">Le righe dagli ordini cliente 4-7 e 4-8 per il conto cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="61bfe-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61bfe-245">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="61bfe-245">Additional resources</span></span>

- [<span data-ttu-id="61bfe-246">Criteri consolidamento spedizione</span><span class="sxs-lookup"><span data-stu-id="61bfe-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="61bfe-247">Configurazione dei criteri di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="61bfe-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)