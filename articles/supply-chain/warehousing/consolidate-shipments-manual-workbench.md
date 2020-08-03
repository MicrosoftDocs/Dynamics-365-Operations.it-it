---
title: Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni
description: Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente in spedizioni utilizzando il workbench di consolidamento delle spedizioni.
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
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b1a2c9506b4444fc98a9e4f0389cbd69db4ce052
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383801"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="b6ecd-103">Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="b6ecd-103">Consolidate shipments by using the shipment consolidation workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6ecd-104">Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino e consolidati successivamente in spedizioni utilizzando il workbench di consolidamento delle spedizioni.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated into shipments later by using the shipment consolidation workbench.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="b6ecd-105">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="b6ecd-105">Make demo data available</span></span>

<span data-ttu-id="b6ecd-106">Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b6ecd-107">Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="b6ecd-108">Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti</span><span class="sxs-lookup"><span data-stu-id="b6ecd-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="b6ecd-109">Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="b6ecd-110">Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a><span data-ttu-id="b6ecd-111">Attiva la funzionalità dei criteri di consolidamento delle spedizioni manuali</span><span class="sxs-lookup"><span data-stu-id="b6ecd-111">Turn on the manual shipment consolidation feature</span></span>

<span data-ttu-id="b6ecd-112">Prima di poter usare la funzionalità *Consolidamento spedizione manuale*, devi attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-112">Before you can use the *Manual shipment consolidation* feature, you must turn it on in your system.</span></span> <span data-ttu-id="b6ecd-113">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="b6ecd-114">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b6ecd-115">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b6ecd-116">**Nome funzionalità:** *Consolidamento spedizione manuale*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-116">**Feature name:** *Manual shipment consolidation*</span></span>

<span data-ttu-id="b6ecd-117">Come menzionato in [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md), devi attivare anche la funzionalità *Consolida spedizione* prima di poter creare criteri.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-117">As was mentioned in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), you must also turn on the *Consolidate shipment* feature before you can create policies.</span></span> <span data-ttu-id="b6ecd-118">Tuttavia, dovresti già aver completato questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-118">However, you should already have completed that step.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="b6ecd-119">Crea gli ordini cliente per questo scenario</span><span class="sxs-lookup"><span data-stu-id="b6ecd-119">Create the sales orders for this scenario</span></span>

<span data-ttu-id="b6ecd-120">Inizia creando una raccolta di ordini cliente con cui puoi lavorare.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-120">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="b6ecd-121">Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS).</span><span class="sxs-lookup"><span data-stu-id="b6ecd-121">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="b6ecd-122">A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-122">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="b6ecd-123">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-123">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="b6ecd-124">Crea un insieme di ordini 1</span><span class="sxs-lookup"><span data-stu-id="b6ecd-124">Create order set 1</span></span>

#### <a name="sales-orders-1-1-and-1-2"></a><span data-ttu-id="b6ecd-125">Ordini cliente 1-1 e 1-2</span><span class="sxs-lookup"><span data-stu-id="b6ecd-125">Sales orders 1-1 and 1-2</span></span>

1. <span data-ttu-id="b6ecd-126">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-126">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-127">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b6ecd-128">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b6ecd-129">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-130">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-131">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-132">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="b6ecd-133">Ordine cliente 1-3</span><span class="sxs-lookup"><span data-stu-id="b6ecd-133">Sales order 1-3</span></span>

1. <span data-ttu-id="b6ecd-134">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-135">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b6ecd-136">**Modalità di consegna:** *10*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="b6ecd-137">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-138">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-139">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-140">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="b6ecd-141">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-142">**Numero articolo:** *A0002* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-143">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="b6ecd-144">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b6ecd-145">Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="b6ecd-146">Crea un insieme di ordini 2</span><span class="sxs-lookup"><span data-stu-id="b6ecd-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="b6ecd-147">Ordini cliente 2-1 e 2-2</span><span class="sxs-lookup"><span data-stu-id="b6ecd-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="b6ecd-148">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-149">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-149">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="b6ecd-150">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-150">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b6ecd-151">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-151">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-152">**Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-152">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="b6ecd-153">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-153">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-154">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-154">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="b6ecd-155">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-155">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-156">**Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-156">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="b6ecd-157">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-157">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="b6ecd-158">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-158">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b6ecd-159">Seleziona **Magazzino \> Prenotazione**, quindi, nel riquadro azioni, seleziona **Prenota lotto** per prenotare la seconda riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-159">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="b6ecd-160">Crea un insieme di ordini 3</span><span class="sxs-lookup"><span data-stu-id="b6ecd-160">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="b6ecd-161">Ordini cliente 3-1 e 3-2</span><span class="sxs-lookup"><span data-stu-id="b6ecd-161">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="b6ecd-162">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-162">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-163">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-163">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b6ecd-164">**Richiesta di approvvigionamento cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-164">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="b6ecd-165">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-165">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-166">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-166">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-167">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-167">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-168">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-168">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="b6ecd-169">Ordini cliente 3-3 e 3-4</span><span class="sxs-lookup"><span data-stu-id="b6ecd-169">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="b6ecd-170">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-170">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-171">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-171">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b6ecd-172">**Richiesta di approvvigionamento cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-172">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="b6ecd-173">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-173">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-174">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-174">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-175">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-175">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-176">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-176">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="b6ecd-177">Crea un insieme di ordini 4</span><span class="sxs-lookup"><span data-stu-id="b6ecd-177">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="b6ecd-178">Ordini cliente 4-1 e 4-2</span><span class="sxs-lookup"><span data-stu-id="b6ecd-178">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="b6ecd-179">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-180">**Conto cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-180">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="b6ecd-181">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-181">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-182">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-182">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-183">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-183">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-184">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-184">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="b6ecd-185">Ordini cliente 4-3 e 4-4</span><span class="sxs-lookup"><span data-stu-id="b6ecd-185">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="b6ecd-186">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-186">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-187">**Conto cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-187">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="b6ecd-188">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-188">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-189">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-189">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-190">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-190">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-191">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-191">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="b6ecd-192">Ordini cliente 4-5 e 4-6</span><span class="sxs-lookup"><span data-stu-id="b6ecd-192">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="b6ecd-193">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-193">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-194">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="b6ecd-195">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-195">**Site:** *6*</span></span>
    - <span data-ttu-id="b6ecd-196">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-196">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="b6ecd-197">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-197">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="b6ecd-198">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-198">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-199">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-199">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-200">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-200">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-201">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-201">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="b6ecd-202">Ordini cliente 4-7 e 4-8</span><span class="sxs-lookup"><span data-stu-id="b6ecd-202">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="b6ecd-203">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-203">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b6ecd-204">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-204">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="b6ecd-205">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-205">**Site:** *6*</span></span>
    - <span data-ttu-id="b6ecd-206">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-206">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="b6ecd-207">**Pool:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-207">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="b6ecd-208">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-208">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b6ecd-209">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="b6ecd-209">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b6ecd-210">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-210">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b6ecd-211">Seleziona **Magazzino \> Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-211">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="b6ecd-212">Rilascia gli ordini al magazzino</span><span class="sxs-lookup"><span data-stu-id="b6ecd-212">Release the orders to the warehouse</span></span>

<span data-ttu-id="b6ecd-213">Segui questi passaggi per rilasciare ciascun ordine cliente creato per questo scenario nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-213">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="b6ecd-214">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-214">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b6ecd-215">Trova e seleziona l'ordine cliente da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-215">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="b6ecd-216">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Azioni \> Rilascia in magazzino** per rilasciare l'ordine cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-216">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="b6ecd-217">Ripeti questa procedura per ogni altro ordine cliente creato per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-217">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="b6ecd-218">Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="b6ecd-218">Consolidate the shipments by using the shipment consolidation workbench</span></span>

1. <span data-ttu-id="b6ecd-219">Vai a **Gestione magazzino \> Rilascia in magazzino \> Workbench consolidamento spedizione**.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-219">Go to **Warehouse management \> Release to warehouse \> Shipment consolidation workbench**.</span></span>
1. <span data-ttu-id="b6ecd-220">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-220">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="b6ecd-221">Nella finestra di dialogo dell'editor delle query, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga che ha le seguenti impostazioni alla griglia:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-221">In the query editor dialog box, on the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="b6ecd-222">**Tabella:** *Ordini cliente*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-222">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="b6ecd-223">**Campo:** *Ordine cliente*</span><span class="sxs-lookup"><span data-stu-id="b6ecd-223">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="b6ecd-224">**Criteri:** immetti un elenco separato da virgole dei numeri di ordini cliente per ciascun insieme di ordini creato per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-224">**Criteria:** Enter a comma-separated list of the sales order numbers for each order set that you created for this scenario.</span></span>

1. <span data-ttu-id="b6ecd-225">Seleziona **OK** per salvare la query e chiudere la finestra dialogo.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-225">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="b6ecd-226">Nel riquadro azioni, seleziona **Consolida spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-226">On the Action Pane, select **Consolidate shipments**.</span></span>
1. <span data-ttu-id="b6ecd-227">Seleziona tutte le spedizioni, quindi nel riquadro azioni, seleziona **Consolida**.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-227">Select all the shipments, and then, on the Action Pane, select **Consolidate**.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="b6ecd-228">Verifica le spedizioni</span><span class="sxs-lookup"><span data-stu-id="b6ecd-228">Verify the shipments</span></span>

<span data-ttu-id="b6ecd-229">La seguente procedura consente di verificare le spedizioni che sono state create o aggiornate a seguito del consolidamento della spedizione.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-229">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="b6ecd-230">Usala per rivedere ogni insieme di ordini che hai creato per questo scenario, quindi rivedi le sottosezioni che seguono per assicurarti di aver ottenuto i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-230">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="b6ecd-231">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-231">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="b6ecd-232">Trova e seleziona la spedizione richiesta.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-232">Find and select the required shipment.</span></span>
1. <span data-ttu-id="b6ecd-233">Se è stato utilizzato un criterio di consolidamento al momento della creazione o dell'aggiornamento della spedizione, dovresti visualizzarlo nel campo **Criteri di consolidamento della spedizione**.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-233">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="related-shipments-for-order-set-1"></a><span data-ttu-id="b6ecd-234">Spedizioni correlate per insiemi di ordini 1</span><span class="sxs-lookup"><span data-stu-id="b6ecd-234">Related shipments for order set 1</span></span>

<span data-ttu-id="b6ecd-235">Dovrebbero essere state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-235">Two shipments should have been created:</span></span>

- <span data-ttu-id="b6ecd-236">La prima spedizione contiene tre righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-236">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="b6ecd-237">La seconda spedizione, che non utilizza la modalità di trasporto della consegna *Airways*, è stata creata utilizzando i criteri di consolidamento della spedizione *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-237">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="related-shipments-for-order-set-2"></a><span data-ttu-id="b6ecd-238">Spedizioni correlate per insiemi di ordini 2</span><span class="sxs-lookup"><span data-stu-id="b6ecd-238">Related shipments for order set 2</span></span>

<span data-ttu-id="b6ecd-239">Dovrebbero essere state create tre spedizioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-239">Three shipments should have been created:</span></span>

- <span data-ttu-id="b6ecd-240">La prima spedizione contiene articoli *Infiammabili*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-240">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="b6ecd-241">Ognuna delle altre due spedizioni contiene una riga che ha l'articolo *Esplosivo*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-241">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="related-shipments-for-order-set-3"></a><span data-ttu-id="b6ecd-242">Spedizioni correlate per insiemi di ordini 3</span><span class="sxs-lookup"><span data-stu-id="b6ecd-242">Related shipments for order set 3</span></span>

<span data-ttu-id="b6ecd-243">Dovrebbero essere state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-243">Two shipments should have been created:</span></span>

- <span data-ttu-id="b6ecd-244">La prima spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *1*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-244">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="b6ecd-245">La seconda spedizione contiene righe di ordini dall'ordine cliente il cui campo **Richiesta di approvvigionamento cliente** è impostato su *2*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-245">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="related-shipments-for-order-set-4"></a><span data-ttu-id="b6ecd-246">Spedizioni correlate per insiemi di ordini 4</span><span class="sxs-lookup"><span data-stu-id="b6ecd-246">Related shipments for order set 4</span></span>

<span data-ttu-id="b6ecd-247">Dovrebbero essere state create quattro spedizioni:</span><span class="sxs-lookup"><span data-stu-id="b6ecd-247">Four shipments should have been created:</span></span>

- <span data-ttu-id="b6ecd-248">Le righe dei due ordini per il cliente *US-003* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-248">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="b6ecd-249">Le righe dei due ordini per il cliente *US-004* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-249">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="b6ecd-250">Le righe dagli ordini cliente 4-5 e 4-6 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-250">Lines from sales orders 4-5 and 4-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="b6ecd-251">Le righe dagli ordini cliente 4-7 e 4-8 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="b6ecd-251">Lines from sales orders 4-7 and 4-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6ecd-252">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b6ecd-252">Additional resources</span></span>

- [<span data-ttu-id="b6ecd-253">Criteri consolidamento spedizione</span><span class="sxs-lookup"><span data-stu-id="b6ecd-253">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="b6ecd-254">Configurazione dei criteri di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="b6ecd-254">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)