---
title: Consolidare le spedizioni quando vengono rilasciate al magazzino utilizzando Rilascio automatico degli ordini cliente
description: Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino nella stessa procedura periodica di rilascio al magazzino automatizzata.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 82a95ecf196ef7c33831da7f4d03df629b17fa53
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807562"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="4cf52-103">Consolidare le spedizioni quando vengono rilasciate al magazzino utilizzando Rilascio automatico degli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="4cf52-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4cf52-104">Questo argomento presenta uno scenario in cui più ordini vengono rilasciati al magazzino nella stessa procedura periodica di rilascio al magazzino automatizzata.</span><span class="sxs-lookup"><span data-stu-id="4cf52-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="4cf52-105">Gli ordini verranno automaticamente consolidati in spedizioni, in base a regole definite come criteri di consolidamento delle spedizioni.</span><span class="sxs-lookup"><span data-stu-id="4cf52-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="4cf52-106">Durante lo scenario, creerai serie di ordini cliente e rilascerai ogni serie nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="4cf52-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="4cf52-107">Esaminerai quindi le spedizioni che vengono create o aggiornate durante il consolidamento della spedizione, in base ai criteri configurati.</span><span class="sxs-lookup"><span data-stu-id="4cf52-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="4cf52-108">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="4cf52-108">Make demo data available</span></span>

<span data-ttu-id="4cf52-109">Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4cf52-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="4cf52-110">Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="4cf52-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="4cf52-111">Impostare i criteri di consolidamento delle spedizioni e i filtri per i prodotti</span><span class="sxs-lookup"><span data-stu-id="4cf52-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="4cf52-112">Lo scenario qui descritto presuppone che tu abbia già attivato la funzione, eseguito gli esercizi [Configurare i criteri di consolidamento della spedizione](configure-shipment-consolidation-policies.md) e creato i criteri e altri record ivi descritti.</span><span class="sxs-lookup"><span data-stu-id="4cf52-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="4cf52-113">Assicurati di eseguire quegli esercizi prima di continuare con questo scenario.</span><span class="sxs-lookup"><span data-stu-id="4cf52-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="4cf52-114">Crea gli ordini cliente per questo scenario</span><span class="sxs-lookup"><span data-stu-id="4cf52-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="4cf52-115">Inizia creando una raccolta di ordini cliente con cui puoi lavorare.</span><span class="sxs-lookup"><span data-stu-id="4cf52-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="4cf52-116">Devi lavorare con un magazzino abilitato per i processi di magazzino avanzati (WMS).</span><span class="sxs-lookup"><span data-stu-id="4cf52-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="4cf52-117">A meno che non venga esplicitamente menzionato un magazzino diverso, tale magazzino deve essere utilizzato per ciascuna dei seguenti insiemi di ordini.</span><span class="sxs-lookup"><span data-stu-id="4cf52-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="4cf52-118">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente** e crea una raccolta di ordini cliente con le impostazioni descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4cf52-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="4cf52-119">Crea un insieme di ordini 1</span><span class="sxs-lookup"><span data-stu-id="4cf52-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="4cf52-120">Ordine cliente 1-1</span><span class="sxs-lookup"><span data-stu-id="4cf52-120">Sales order 1-1</span></span>

1. <span data-ttu-id="4cf52-121">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-122">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf52-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf52-123">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="4cf52-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="4cf52-124">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-125">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-126">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="4cf52-127">Ordine cliente 1-2</span><span class="sxs-lookup"><span data-stu-id="4cf52-127">Sales order 1-2</span></span>

1. <span data-ttu-id="4cf52-128">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-129">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf52-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf52-130">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="4cf52-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="4cf52-131">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-132">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-133">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="4cf52-134">Ordine cliente 1-3</span><span class="sxs-lookup"><span data-stu-id="4cf52-134">Sales order 1-3</span></span>

1. <span data-ttu-id="4cf52-135">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-136">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf52-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf52-137">**Modalità di consegna:** *10*</span><span class="sxs-lookup"><span data-stu-id="4cf52-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="4cf52-138">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-139">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-140">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4cf52-141">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-142">**Numero articolo:** *A0002* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-143">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4cf52-144">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="4cf52-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="4cf52-145">Crea un insieme di ordini 2</span><span class="sxs-lookup"><span data-stu-id="4cf52-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="4cf52-146">Ordini cliente 2-1 e 2-2</span><span class="sxs-lookup"><span data-stu-id="4cf52-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="4cf52-147">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf52-148">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="4cf52-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="4cf52-149">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-150">**Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)</span><span class="sxs-lookup"><span data-stu-id="4cf52-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="4cf52-151">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4cf52-152">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-153">**Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)</span><span class="sxs-lookup"><span data-stu-id="4cf52-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="4cf52-154">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4cf52-155">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="4cf52-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="4cf52-156">Crea un insieme di ordini 3</span><span class="sxs-lookup"><span data-stu-id="4cf52-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="4cf52-157">Ordine cliente 3-1</span><span class="sxs-lookup"><span data-stu-id="4cf52-157">Sales order 3-1</span></span>

1. <span data-ttu-id="4cf52-158">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-159">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="4cf52-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="4cf52-160">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-161">**Numero articolo:** *M9200* (un articolo il cui filtro **Codice 4** è impostato su *Infiammabile*)</span><span class="sxs-lookup"><span data-stu-id="4cf52-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="4cf52-162">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4cf52-163">Aggiungi una seconda riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-164">**Numero articolo:** *M9201* (un articolo il cui filtro **Codice 4** è impostato su *Esplosivo*)</span><span class="sxs-lookup"><span data-stu-id="4cf52-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="4cf52-165">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4cf52-166">**Modalità di consegna:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="4cf52-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="4cf52-167">Questo ordine è identico ai due ordini creati per l'insieme di ordini 2.</span><span class="sxs-lookup"><span data-stu-id="4cf52-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="4cf52-168">Tuttavia, è elencato come insieme di ordini perché lo rilascerai separatamente più avanti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="4cf52-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="4cf52-169">Crea un insieme di ordini 4</span><span class="sxs-lookup"><span data-stu-id="4cf52-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="4cf52-170">Ordine cliente 4-1</span><span class="sxs-lookup"><span data-stu-id="4cf52-170">Sales order 4-1</span></span>

1. <span data-ttu-id="4cf52-171">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-172">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf52-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf52-173">**Richiesta di approvvigionamento cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="4cf52-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4cf52-174">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-175">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-176">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="4cf52-177">Crea un insieme di ordini 5</span><span class="sxs-lookup"><span data-stu-id="4cf52-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="4cf52-178">Ordini cliente 5-1 e 5-2</span><span class="sxs-lookup"><span data-stu-id="4cf52-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="4cf52-179">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf52-180">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf52-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf52-181">**Richiesta di approvvigionamento cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="4cf52-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="4cf52-182">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-183">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-184">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="4cf52-185">Ordine cliente 5-3</span><span class="sxs-lookup"><span data-stu-id="4cf52-185">Sales order 5-3</span></span>

1. <span data-ttu-id="4cf52-186">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-187">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4cf52-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4cf52-188">**Richiesta di approvvigionamento cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="4cf52-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4cf52-189">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-190">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-191">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="4cf52-192">Crea un insieme di ordini 6</span><span class="sxs-lookup"><span data-stu-id="4cf52-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="4cf52-193">Ordini cliente 6-1 e 6-2</span><span class="sxs-lookup"><span data-stu-id="4cf52-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="4cf52-194">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf52-195">**Conto cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="4cf52-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="4cf52-196">**Richiesta di approvvigionamento cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="4cf52-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="4cf52-197">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-198">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-199">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="4cf52-200">Ordini cliente 6-3 e 6-4</span><span class="sxs-lookup"><span data-stu-id="4cf52-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="4cf52-201">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf52-202">**Conto cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="4cf52-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="4cf52-203">**Richiesta di approvvigionamento cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="4cf52-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4cf52-204">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-205">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-206">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="4cf52-207">Ordini cliente 6-5 e 6-6</span><span class="sxs-lookup"><span data-stu-id="4cf52-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="4cf52-208">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf52-209">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="4cf52-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="4cf52-210">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="4cf52-210">**Site:** *6*</span></span>
    - <span data-ttu-id="4cf52-211">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="4cf52-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="4cf52-212">**Pool:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="4cf52-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="4cf52-213">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-214">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-215">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="4cf52-216">Ordini cliente 6-7 e 6-8</span><span class="sxs-lookup"><span data-stu-id="4cf52-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="4cf52-217">Crea due ordini cliente identici con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4cf52-218">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="4cf52-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="4cf52-219">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="4cf52-219">**Site:** *6*</span></span>
    - <span data-ttu-id="4cf52-220">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="4cf52-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="4cf52-221">**Pool:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="4cf52-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="4cf52-222">Aggiungi una riga ordine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4cf52-223">**Numero articolo:** *A0001* (un articolo a cui non è stato assegnato il filtro **Codice 4**)</span><span class="sxs-lookup"><span data-stu-id="4cf52-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4cf52-224">**Quantità:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4cf52-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="4cf52-225">Rilascio automatico di ordini cliente nel magazzino</span><span class="sxs-lookup"><span data-stu-id="4cf52-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="4cf52-226">Per ciascuna serie di ordini cliente creati in precedenza, dovrai completare una procedura per il rilascio automatico nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="4cf52-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="4cf52-227">In ogni caso, proseguirai attraverso la [procedura base di rilascio al magazzino](#release-procedure) riportata qui.</span><span class="sxs-lookup"><span data-stu-id="4cf52-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="4cf52-228">Procedura di rilascio in magazzino di base</span><span class="sxs-lookup"><span data-stu-id="4cf52-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="4cf52-229">Per ciascuna serie di ordini cliente creata in precedenza, verranno completate le tre procedure descritte nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4cf52-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="4cf52-230">Aggiorna il modello ondata che verrà utilizzato durante il rilascio</span><span class="sxs-lookup"><span data-stu-id="4cf52-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="4cf52-231">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="4cf52-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="4cf52-232">Imposta il campo **Tipo di modello ondata** su *Spedizione*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="4cf52-233">Trova e seleziona il modello ondata associato al magazzino utilizzato nei insieme di ordini creati per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="4cf52-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="4cf52-234">Ad esempio, se hai utilizzato il magazzino *24*, seleziona il modello ondata **Spedizione predefinita 24**.</span><span class="sxs-lookup"><span data-stu-id="4cf52-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="4cf52-235">Se hai utilizzato il magazzino *61*, seleziona il modello ondata **Spedizione 61**.</span><span class="sxs-lookup"><span data-stu-id="4cf52-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="4cf52-236">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4cf52-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="4cf52-237">Impostare l'opzione **Elabora ondata al rilascio in magazzino** su *No*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="4cf52-238">Rilascia al magazzino</span><span class="sxs-lookup"><span data-stu-id="4cf52-238">Release to the warehouse</span></span>

1. <span data-ttu-id="4cf52-239">Vai a **Gestione del magazzino \> Rilascio in magazzino \> Rilascio automatico degli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="4cf52-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="4cf52-240">Imposta il campo **Quantità da rilasciare** su *Tutto*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="4cf52-241">Nella Scheda dettaglio **Record da includere**, seleziona **Filtro** per aprire la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="4cf52-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="4cf52-242">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga che ha le seguenti impostazioni alla griglia:</span><span class="sxs-lookup"><span data-stu-id="4cf52-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="4cf52-243">**Tabella:** *Ordine cliente*</span><span class="sxs-lookup"><span data-stu-id="4cf52-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="4cf52-244">**Tabella derivata:** *Ordine cliente*</span><span class="sxs-lookup"><span data-stu-id="4cf52-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="4cf52-245">**Campo:** *Ordine cliente*</span><span class="sxs-lookup"><span data-stu-id="4cf52-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="4cf52-246">**Criteri:** immetti un elenco separato da virgole dei numeri degli ordini cliente dall'insieme di ordini desiderato.</span><span class="sxs-lookup"><span data-stu-id="4cf52-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="4cf52-247">Seleziona **OK** per salvare la tua query.</span><span class="sxs-lookup"><span data-stu-id="4cf52-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="4cf52-248">Seleziona **OK** per iniziare la procedura *Rilascio automatico in magazzino*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="4cf52-249">Rivedi la spedizione creata o aggiornata</span><span class="sxs-lookup"><span data-stu-id="4cf52-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="4cf52-250">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="4cf52-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="4cf52-251">Trova e seleziona la spedizione richiesta.</span><span class="sxs-lookup"><span data-stu-id="4cf52-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="4cf52-252">Se è stato utilizzato un criterio di consolidamento al momento della creazione o dell'aggiornamento della spedizione, dovresti visualizzarlo nel campo **Criteri di consolidamento della spedizione**.</span><span class="sxs-lookup"><span data-stu-id="4cf52-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="4cf52-253">Rilascia gli ordini cliente dall'insieme di ordini 1</span><span class="sxs-lookup"><span data-stu-id="4cf52-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="4cf52-254">Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 1.</span><span class="sxs-lookup"><span data-stu-id="4cf52-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="4cf52-255">Al termine, dovresti vedere che sono state create due spedizioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="4cf52-256">La prima spedizione contiene tre righe ed è stata creata utilizzando il criterio di consolidamento della spedizione *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf52-257">La seconda spedizione, che non utilizza la modalità di trasporto della consegna *Airways*, è stata creata utilizzando i criteri di consolidamento della spedizione *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="4cf52-258">Rilascia gli ordini cliente dall'insieme di ordini 2</span><span class="sxs-lookup"><span data-stu-id="4cf52-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="4cf52-259">Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 2.</span><span class="sxs-lookup"><span data-stu-id="4cf52-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="4cf52-260">Al termine, dovresti vedere che sono state create tre spedizioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="4cf52-261">La prima spedizione contiene articoli *Infiammabili*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="4cf52-262">Ognuna delle altre due spedizioni contiene una riga che ha l'articolo *Esplosivo*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="4cf52-263">Rilascia gli ordini cliente dall'insieme di ordini 3</span><span class="sxs-lookup"><span data-stu-id="4cf52-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="4cf52-264">Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 3.</span><span class="sxs-lookup"><span data-stu-id="4cf52-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="4cf52-265">Al termine, dovresti vedere che si sono verificate le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="4cf52-266">Una spedizione esistente (la spedizione creata quando l'insieme di ordini 2 è stato rilasciato nel magazzino) è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="4cf52-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="4cf52-267">Una riga che ha l'articolo *Infiammabile* è stata aggiunta.</span><span class="sxs-lookup"><span data-stu-id="4cf52-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="4cf52-268">È stata creata una nuova spedizione che contiene l'articolo *Esplosivo*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="4cf52-269">Rilascia gli ordini cliente dall'insieme di ordini 4</span><span class="sxs-lookup"><span data-stu-id="4cf52-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="4cf52-270">Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 4.</span><span class="sxs-lookup"><span data-stu-id="4cf52-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="4cf52-271">Al termine, dovresti vedere quella spedizione esistente (dove il campo **Richiesta di approvvigionamento cliente** è impostato su *1*) è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="4cf52-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="4cf52-272">È stata aggiunta una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="4cf52-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="4cf52-273">Rilascia gli ordini cliente dall'insieme di ordini 5</span><span class="sxs-lookup"><span data-stu-id="4cf52-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="4cf52-274">Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 5.</span><span class="sxs-lookup"><span data-stu-id="4cf52-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="4cf52-275">Al termine, dovresti vedere che si sono verificate le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="4cf52-276">Una spedizione esistente (dove il campo **Richiesta di approvvigionamento cliente** è impostato su *1*) è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="4cf52-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="4cf52-277">Una riga dall'ordine cliente 5-3 (dove il campo **Richiesta di approvvigionamento cliente** è impostato su *1*) è stata aggiunta ad esso.</span><span class="sxs-lookup"><span data-stu-id="4cf52-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="4cf52-278">È stata creata una nuova spedizione, in cui le righe degli ordini cliente 5-1 e 5-2 sono raggruppate in un'unica spedizione.</span><span class="sxs-lookup"><span data-stu-id="4cf52-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="4cf52-279">Rilascia gli ordini cliente dall'insieme di ordini 6</span><span class="sxs-lookup"><span data-stu-id="4cf52-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="4cf52-280">Segui la [procedura base di rilascio al magazzino](#release-procedure) per rilasciare gli ordini cliente dall'insieme di ordini 6.</span><span class="sxs-lookup"><span data-stu-id="4cf52-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="4cf52-281">Al termine, dovresti vedere che sono state create quattro spedizioni:</span><span class="sxs-lookup"><span data-stu-id="4cf52-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="4cf52-282">Le righe dei due ordini per il cliente *US-003* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf52-283">Le righe dei due ordini per il cliente *US-004* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf52-284">Le righe dagli ordini cliente 6-5 e 6-6 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *Pool di ordini*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4cf52-285">Le righe dagli ordini cliente 6-7 e 6-8 per cliente *US-007* sono state raggruppate in una spedizione utilizzando il criterio di consolidamento della spedizione *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="4cf52-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4cf52-286">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4cf52-286">Additional resources</span></span>

- [<span data-ttu-id="4cf52-287">Criteri consolidamento spedizione</span><span class="sxs-lookup"><span data-stu-id="4cf52-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="4cf52-288">Configurazione dei criteri di consolidamento delle spedizioni</span><span class="sxs-lookup"><span data-stu-id="4cf52-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]