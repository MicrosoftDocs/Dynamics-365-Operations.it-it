---
title: Strategie di imballaggio dei contenitori
description: Questo argomento descrive le differenze tra le strategie di imballaggio dei contenitori e fornisce esempi.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292763"
---
# <a name="container-packing-strategies"></a><span data-ttu-id="a8bd0-103">Strategie di imballaggio dei contenitori</span><span class="sxs-lookup"><span data-stu-id="a8bd0-103">Container packing strategies</span></span>

<span data-ttu-id="a8bd0-104">Una *strategia di imballaggio del contenitore* è una strategia che è possibile utilizzare per definire le allocazioni di articoli tra i contenitori.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-104">A *container packing strategy* is a strategy that you can use to define item allocations across containers.</span></span> <span data-ttu-id="a8bd0-105">Questo argomento spiega le differenze tra le strategie *Imballa in tutti i contenitori aperti* e *Imballa solo nel contenitore corrente*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-105">This topic explains the differences between the *Pack into all open containers* and *Pack into current container only* strategies.</span></span>

- <span data-ttu-id="a8bd0-106">**Imballa in tutti i contenitori aperti** – Il sistema deve controllare tutti i contenitori aperti che sono già stati creati durante il ciclo di containerizzazione, per assicurarsi che l'articolo rientri in uno di essi.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-106">**Pack into all open containers** – The system must check all open containers that have already been created during the containerization cycle, to make sure that the item will fit into one of them.</span></span> <span data-ttu-id="a8bd0-107">Durante l'imballaggio, il sistema controlla ogni articolo per determinare se entrerà in uno dei contenitori creati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-107">During packing, the system checks each item to determine whether it will fit into any of the previously created containers.</span></span> <span data-ttu-id="a8bd0-108">Se l'articolo non entra in un contenitore esistente, il sistema crea un nuovo contenitore e continua fino a quando non ha finito di imballare l'intero ordine.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-108">If the item won't fit into an existing container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="a8bd0-109">Per esempio, *n* articoli ordinati richiedono la containerizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-109">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="a8bd0-110">Nel peggiore dei casi, ogni volta che il sistema elabora un articolo che non rientra in nessun contenitore esistente, esegue il totale di (\[(*n* – 1) × (*n* + 1)\] ÷ 2) per verificare se l'articolo rientra nei contenitori esistenti.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-110">In the worst case, every time that the system processes an item that doesn't fit into any existing container, it will do a total of (\[(*n* – 1) × (*n* + 1)\] ÷ 2) checks to evaluate whether the item fits into the existing containers.</span></span>

- <span data-ttu-id="a8bd0-111">**Imballa solo nel contenitore corrente** – Il sistema deve controllare solo il contenitore creato più di recente per assicurarsi che l'articolo possa rientrarvi.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-111">**Pack into current container only** – The system must check only the most recently created container to make sure that the item will fit into it.</span></span> <span data-ttu-id="a8bd0-112">Durante l'imballaggio, il sistema controlla ogni articolo per determinare se entrerà nel contenitore creato più di recente.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-112">During packing, the system checks each item to determine whether it will fit into the most recently created container.</span></span> <span data-ttu-id="a8bd0-113">Se l'articolo non entra nel contenitore, il sistema crea un nuovo contenitore e continua fino a quando non ha finito di imballare l'intero ordine.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-113">If the item won't fit into that container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="a8bd0-114">Per esempio, *n* articoli ordinati richiedono la containerizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-114">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="a8bd0-115">Nel peggiore dei casi, il sistema eseguirà il totale di (*n* – 1) per valutare se l'articolo rientra nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-115">In the worst case, the system will do a total of (*n* – 1) checks to evaluate whether the item fits into the containers.</span></span>

## <a name="example-of-the-flow-for-container-packing-strategies"></a><span data-ttu-id="a8bd0-116">Esempio del flusso per le strategie di imballaggio dei contenitori</span><span class="sxs-lookup"><span data-stu-id="a8bd0-116">Example of the flow for container packing strategies</span></span>

<span data-ttu-id="a8bd0-117">Imposta i seguenti articoli per la containerizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-117">You set up the following items for containerization.</span></span>

| <span data-ttu-id="a8bd0-118">Articolo</span><span class="sxs-lookup"><span data-stu-id="a8bd0-118">Item</span></span> | <span data-ttu-id="a8bd0-119">Dimensioni fisiche (larghezza × profondità × altezza)</span><span class="sxs-lookup"><span data-stu-id="a8bd0-119">Physical dimensions (width × depth × height)</span></span> | <span data-ttu-id="a8bd0-120">Peso</span><span class="sxs-lookup"><span data-stu-id="a8bd0-120">Weight</span></span> |
|---|---|---|
| <span data-ttu-id="a8bd0-121">Cavo HDMI 6'</span><span class="sxs-lookup"><span data-stu-id="a8bd0-121">HDMI Cable 6'</span></span> | <span data-ttu-id="a8bd0-122">1 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="a8bd0-122">1 × 1 × 1</span></span> | <span data-ttu-id="a8bd0-123">1</span><span class="sxs-lookup"><span data-stu-id="a8bd0-123">1</span></span> |
| <span data-ttu-id="a8bd0-124">Cavo HDMI 12'</span><span class="sxs-lookup"><span data-stu-id="a8bd0-124">HDMI Cable 12'</span></span> | <span data-ttu-id="a8bd0-125">2 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="a8bd0-125">2 × 1 × 1</span></span> | <span data-ttu-id="a8bd0-126">1</span><span class="sxs-lookup"><span data-stu-id="a8bd0-126">1</span></span> |
| <span data-ttu-id="a8bd0-127">Cavo HDMI 18'</span><span class="sxs-lookup"><span data-stu-id="a8bd0-127">HDMI Cable 18'</span></span> | <span data-ttu-id="a8bd0-128">3 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="a8bd0-128">3 × 1 × 1</span></span> | <span data-ttu-id="a8bd0-129">2</span><span class="sxs-lookup"><span data-stu-id="a8bd0-129">2</span></span> |

<span data-ttu-id="a8bd0-130">Imposti anche la seguente scatola che verrà utilizzata per l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-130">You also set up the following box that will be used for packaging.</span></span>

| <span data-ttu-id="a8bd0-131">Contenitore</span><span class="sxs-lookup"><span data-stu-id="a8bd0-131">Container</span></span> | <span data-ttu-id="a8bd0-132">Dimensioni fisiche (lunghezza × larghezza × altezza)</span><span class="sxs-lookup"><span data-stu-id="a8bd0-132">Physical dimensions (length × width × height)</span></span> | <span data-ttu-id="a8bd0-133">Peso</span><span class="sxs-lookup"><span data-stu-id="a8bd0-133">Weight</span></span> | <span data-ttu-id="a8bd0-134">Volume</span><span class="sxs-lookup"><span data-stu-id="a8bd0-134">Volume</span></span> |
|---|---|---|---|
| <span data-ttu-id="a8bd0-135">Scatola media</span><span class="sxs-lookup"><span data-stu-id="a8bd0-135">Medium Box</span></span> | <span data-ttu-id="a8bd0-136">6 × 3 × 2</span><span class="sxs-lookup"><span data-stu-id="a8bd0-136">6 × 3 × 2</span></span> | <span data-ttu-id="a8bd0-137">10</span><span class="sxs-lookup"><span data-stu-id="a8bd0-137">10</span></span> | <span data-ttu-id="a8bd0-138">100</span><span class="sxs-lookup"><span data-stu-id="a8bd0-138">100</span></span> |

<span data-ttu-id="a8bd0-139">Infine, imposti un ordine con i seguenti prodotti e quantità.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-139">Finally, you set up an order that has the following products and quantities.</span></span>

| <span data-ttu-id="a8bd0-140">Riga ordine cliente</span><span class="sxs-lookup"><span data-stu-id="a8bd0-140">Sales order line</span></span> | <span data-ttu-id="a8bd0-141">Quantità</span><span class="sxs-lookup"><span data-stu-id="a8bd0-141">Quantity</span></span> |
|---|---|
| <span data-ttu-id="a8bd0-142">Cavo HDMI 12'</span><span class="sxs-lookup"><span data-stu-id="a8bd0-142">HDMI Cable 12'</span></span> | <span data-ttu-id="a8bd0-143">9</span><span class="sxs-lookup"><span data-stu-id="a8bd0-143">9</span></span> |
| <span data-ttu-id="a8bd0-144">Cavo HDMI 18'</span><span class="sxs-lookup"><span data-stu-id="a8bd0-144">HDMI Cable 18'</span></span> | <span data-ttu-id="a8bd0-145">8</span><span class="sxs-lookup"><span data-stu-id="a8bd0-145">8</span></span> |
| <span data-ttu-id="a8bd0-146">Cavo HDMI 6'</span><span class="sxs-lookup"><span data-stu-id="a8bd0-146">HDMI Cable 6'</span></span> | <span data-ttu-id="a8bd0-147">13</span><span class="sxs-lookup"><span data-stu-id="a8bd0-147">13</span></span> |

<span data-ttu-id="a8bd0-148">La tabella seguente riepiloga il funzionamento della containerizzazione quando usi la strategia *Imballa in tutti i contenitori aperti* e quando usi la strategia *Imballa solo nel contenitore corrente*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-148">The following table summarizes how containerization works when you use the *Pack into all open containers* strategy and when you use the *Pack into current container only* strategy.</span></span>

| <span data-ttu-id="a8bd0-149">Imballa in tutti i contenitori aperti</span><span class="sxs-lookup"><span data-stu-id="a8bd0-149">Pack into all open containers</span></span> | <span data-ttu-id="a8bd0-150">Imballa nel contenitore corrente</span><span class="sxs-lookup"><span data-stu-id="a8bd0-150">Pack into current container</span></span> |
|---|---|
| <p><span data-ttu-id="a8bd0-151">Cavo HDMI 12':</span><span class="sxs-lookup"><span data-stu-id="a8bd0-151">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="a8bd0-152">Crea un nuovo contenitore, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-152">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="a8bd0-153">Metti 9 ea nel contenitore CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-153">Put 9 ea into container CONT0001.</span></span></li></ol> | <p><span data-ttu-id="a8bd0-154">Cavo HDMI 12':</span><span class="sxs-lookup"><span data-stu-id="a8bd0-154">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="a8bd0-155">Crea un nuovo contenitore, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-155">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="a8bd0-156">Metti 9 ea nel contenitore CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-156">Put 9 ea into container CONT0001.</span></span></li></ol> |
| <p><span data-ttu-id="a8bd0-157">Cavo HDMI 18':</span><span class="sxs-lookup"><span data-stu-id="a8bd0-157">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="a8bd0-158">Verifica se l'articolo può essere inserito nel contenitore CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-158">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="a8bd0-159">Crea un nuovo contenitore, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-159">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="a8bd0-160">Metti 5 ea nel contenitore CONT0002.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-160">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="a8bd0-161">Crea un nuovo contenitore, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-161">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="a8bd0-162">Metti 3 ea nel contenitore CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-162">Put 3 ea into container CONT0003.</span></span></li></ol> | <p><span data-ttu-id="a8bd0-163">Cavo HDMI 18':</span><span class="sxs-lookup"><span data-stu-id="a8bd0-163">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="a8bd0-164">Verifica se l'articolo può essere inserito nel contenitore CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-164">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="a8bd0-165">Crea un nuovo contenitore, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-165">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="a8bd0-166">Metti 5 ea nel contenitore CONT0002.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-166">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="a8bd0-167">Crea un nuovo contenitore, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-167">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="a8bd0-168">Metti 3 ea nel contenitore CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-168">Put 3 ea into container CONT0003.</span></span></li></ol> |
| <p><span data-ttu-id="a8bd0-169">Cavo HDMI 6':</span><span class="sxs-lookup"><span data-stu-id="a8bd0-169">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="a8bd0-170">Verifica se l'articolo può essere inserito nel contenitore CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-170">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="a8bd0-171">Metti 1 ea nel contenitore CONT0001.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-171">Put 1 ea into container CONT0001.</span></span></li><li><span data-ttu-id="a8bd0-172">Verifica se l'articolo può essere inserito nel contenitore CONT0002.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-172">Check whether the item can fit into container CONT0002.</span></span></li><li><span data-ttu-id="a8bd0-173">Verifica se l'articolo può essere inserito nel contenitore CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-173">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="a8bd0-174">Metti 4 ea nel contenitore CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-174">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="a8bd0-175">Crea un nuovo contenitore, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-175">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="a8bd0-176">Metti 8 ea nel contenitore CONT0004.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-176">Put 8 ea into container CONT0004.</span></span></li></ol> | <p><span data-ttu-id="a8bd0-177">Cavo HDMI 6':</span><span class="sxs-lookup"><span data-stu-id="a8bd0-177">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="a8bd0-178">Verifica se l'articolo può essere inserito nel contenitore CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-178">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="a8bd0-179">Metti 4 ea nel contenitore CONT0003.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-179">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="a8bd0-180">Crea un nuovo contenitore, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-180">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="a8bd0-181">Metti 9 ea nel contenitore CONT0004.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-181">Put 9 ea into container CONT0004.</span></span></li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a><span data-ttu-id="a8bd0-182">Scenario di esempio: imballa ordini singoli per contenitore</span><span class="sxs-lookup"><span data-stu-id="a8bd0-182">Example scenario: Pack single orders per container</span></span>

<span data-ttu-id="a8bd0-183">Questa sezione presenta uno scenario in cui il sistema viene impostato per consolidare più ordini in un'unica spedizione.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-183">This section presents a scenario where the system is set up to consolidate multiple orders into one shipment.</span></span> <span data-ttu-id="a8bd0-184">Pertanto, la containerizzazione verrà eseguita dall'ordine cliente per garantire che ogni ordine che contiene più prodotti sia imballato nel proprio contenitore.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-184">Therefore, containerization will be done from the sales order to ensure that every order that contains multiple products is packed into its own container.</span></span>

<span data-ttu-id="a8bd0-185">Questa funzionalità consente di gestire scenari in cui è necessario imballare un solo ordine cliente in ciascun contenitore, in modo che il centro di distribuzione possa effettuare il cross-docking dei contenitori pieni tra i negozi al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-185">This functionality lets you handle scenarios where you must pack only one sales order into each container, so that the distribution center can cross-dock full containers between retail stores.</span></span> <span data-ttu-id="a8bd0-186">Oltre agli scenari di vendita al dettaglio (ordine per negozio al dettaglio e spedizione a un centro di distribuzione per il cross-docking), questa tecnica è comunemente utilizzata anche nelle catene di approvvigionamento snelle (ordine cliente per linea di produzione just-in-time).</span><span class="sxs-lookup"><span data-stu-id="a8bd0-186">In addition to the retail scenarios (order per retail store and shipping to a distribution center for cross-docking) this technique is also commonly used in lean supply chains (sales order per just-in-time production line).</span></span>

<span data-ttu-id="a8bd0-187">Questo scenario mostra come è possibile ridurre il numero di contenitori valutati durante l'imballaggio utilizzando la strategia *Imballa solo nel contenitore corrente* per la containerizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-187">This scenario shows how you can decrease the number of containers that are evaluated during packing by using the *Pack into current container only* strategy for containerization.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a8bd0-188">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a8bd0-188">Prerequisites</span></span>

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a><span data-ttu-id="a8bd0-189">Attiva la funzione Consolida spedizioni nel tuo sistema</span><span class="sxs-lookup"><span data-stu-id="a8bd0-189">Turn on the Consolidate shipments feature in your system</span></span>

<span data-ttu-id="a8bd0-190">Questo scenario utilizza la funzionalità *Consolida spedizioni*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-190">This scenario uses the *Consolidate shipments* feature.</span></span> <span data-ttu-id="a8bd0-191">Se quella funzione non è già disponibile nel tuo sistema, devi attivarla usando [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8bd0-191">If that feature isn't already available in your system, you must turn it on by using [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

#### <a name="make-demo-data-available"></a><span data-ttu-id="a8bd0-192">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="a8bd0-192">Make demo data available</span></span>

<span data-ttu-id="a8bd0-193">Questo scenario fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-193">This scenario references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="a8bd0-194">Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-194">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

### <a name="inspect-or-create-container-types"></a><span data-ttu-id="a8bd0-195">Ispezionare o creare tipi di contenitori</span><span class="sxs-lookup"><span data-stu-id="a8bd0-195">Inspect or create container types</span></span>

<span data-ttu-id="a8bd0-196">Per ispezionare i tipi di contenitore o per creare nuovi tipi di contenitore, se necessari, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-196">To inspect your container types, or to create new container types if they are required, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-197">Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Tipi di contenitore**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-197">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>
1. <span data-ttu-id="a8bd0-198">Assicurati che ciascuno dei seguenti tipi di contenitore sia disponibile nei dati demo.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-198">Make sure that each of the following container types is available in your demo data.</span></span> <span data-ttu-id="a8bd0-199">Modifica o crea tipi di contenitori come richiesto.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-199">Edit or create container types as required.</span></span>

    - <span data-ttu-id="a8bd0-200">Tipo di contenitore 1:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-200">Container type 1:</span></span>

        - <span data-ttu-id="a8bd0-201">**Codice tipo di contenitore:** *Scatola-grande*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-201">**Container type code:** *Box-Large*</span></span>
        - <span data-ttu-id="a8bd0-202">**Descrizione:** *Scatola grande*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-202">**Description:** *Large Box*</span></span>
        - <span data-ttu-id="a8bd0-203">**Peso netto massimo:** *100*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-203">**Maximum net weight:** *100*</span></span>
        - <span data-ttu-id="a8bd0-204">**Volume:** *400*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-204">**Volume:** *400*</span></span>
        - <span data-ttu-id="a8bd0-205">**Lunghezza:** *4*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-205">**Length:** *4*</span></span>
        - <span data-ttu-id="a8bd0-206">**Larghezza:** *10*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-206">**Width:** *10*</span></span>
        - <span data-ttu-id="a8bd0-207">**Altezza:** *10*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-207">**Height:** *10*</span></span>

    - <span data-ttu-id="a8bd0-208">Tipo di contenitore 2:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-208">Container type 2:</span></span>

        - <span data-ttu-id="a8bd0-209">**Codice tipo di contenitore:** *Scatola-media*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-209">**Container type code:** *Box-Medium*</span></span>
        - <span data-ttu-id="a8bd0-210">**Descrizione:** *Scatola media*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-210">**Description:** *Medium Box*</span></span>
        - <span data-ttu-id="a8bd0-211">**Peso netto massimo:** *50*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-211">**Maximum net weight:** *50*</span></span>
        - <span data-ttu-id="a8bd0-212">**Volume:** *200*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-212">**Volume:** *200*</span></span>
        - <span data-ttu-id="a8bd0-213">**Lunghezza:** *2*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-213">**Length:** *2*</span></span>
        - <span data-ttu-id="a8bd0-214">**Larghezza:** *10*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-214">**Width:** *10*</span></span>
        - <span data-ttu-id="a8bd0-215">**Altezza:** *10*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-215">**Height:** *10*</span></span>

    - <span data-ttu-id="a8bd0-216">Tipo di contenitore 3:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-216">Container type 3:</span></span>

        - <span data-ttu-id="a8bd0-217">**Codice tipo di contenitore:** *Scatola-piccola*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-217">**Container type code:** *Box-Small*</span></span>
        - <span data-ttu-id="a8bd0-218">**Descrizione:** *Scatola piccola*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-218">**Description:** *Small Box*</span></span>
        - <span data-ttu-id="a8bd0-219">**Peso netto massimo:** *20*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-219">**Maximum net weight:** *20*</span></span>
        - <span data-ttu-id="a8bd0-220">**Volume:** *100*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-220">**Volume:** *100*</span></span>
        - <span data-ttu-id="a8bd0-221">**Lunghezza:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-221">**Length:** *1*</span></span>
        - <span data-ttu-id="a8bd0-222">**Larghezza:** *10*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-222">**Width:** *10*</span></span>
        - <span data-ttu-id="a8bd0-223">**Altezza:** *10*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-223">**Height:** *10*</span></span>

### <a name="inspect-or-create-container-groups"></a><span data-ttu-id="a8bd0-224">Ispezionare o creare gruppi di contenitori</span><span class="sxs-lookup"><span data-stu-id="a8bd0-224">Inspect or create container groups</span></span>

<span data-ttu-id="a8bd0-225">Per ispezionare i gruppi di contenitore o per creare nuovi gruppi di contenitore, se necessari, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-225">To inspect your container groups, or to create new container groups if they are required, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-226">Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Gruppi di contenitori**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-226">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**.</span></span>
1. <span data-ttu-id="a8bd0-227">Assicurati che il seguente gruppo di contenitori sia disponibile nei dati demo.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-227">Make sure that the following container group is available in your demo data.</span></span> <span data-ttu-id="a8bd0-228">Se non è disponibile, seleziona **Nuovo** per crearlo.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-228">If it isn't available, select **New** to create it.</span></span>

    - <span data-ttu-id="a8bd0-229">**ID gruppo di contenitori:** *Scatole*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-229">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="a8bd0-230">**Descrizione:** *Dimensioni della scatola*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-230">**Description:** *Box sizes*</span></span>

1. <span data-ttu-id="a8bd0-231">Nella scheda dettaglio **Dettagli** per il gruppo di contenitori *Scatole* assicurati che esistano le seguenti righe.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-231">On the **Details** FastTab for the *Boxes* container group, make sure that the following lines exist.</span></span> <span data-ttu-id="a8bd0-232">Se non esistono, seleziona **Nuovo** per aggiungerle.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-232">If they don't, select **New** to add them.</span></span>

    - <span data-ttu-id="a8bd0-233">Riga 1:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-233">Line 1:</span></span>

        - <span data-ttu-id="a8bd0-234">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-234">**Sequence number:** *1*</span></span>
        - <span data-ttu-id="a8bd0-235">**Tipo di contenitore:** *Scatola-grande*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-235">**Container type:** *Box-Large*</span></span>
        - <span data-ttu-id="a8bd0-236">**Percentuale di utilizzo contenitore:** *100*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-236">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="a8bd0-237">Riga 2:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-237">Line 2:</span></span>

        - <span data-ttu-id="a8bd0-238">**Numero progressivo:** *2*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-238">**Sequence number:** *2*</span></span>
        - <span data-ttu-id="a8bd0-239">**Tipo di contenitore:** *Scatola-media*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-239">**Container type:** *Box-Medium*</span></span>
        - <span data-ttu-id="a8bd0-240">**Percentuale di utilizzo contenitore:** *100*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-240">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="a8bd0-241">Riga 3:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-241">Line 3:</span></span>

        - <span data-ttu-id="a8bd0-242">**Numero progressivo:** *3*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-242">**Sequence number:** *3*</span></span>
        - <span data-ttu-id="a8bd0-243">**Tipo di contenitore:** *Scatola-piccola*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-243">**Container type:** *Box-Small*</span></span>
        - <span data-ttu-id="a8bd0-244">**Percentuale di utilizzo contenitore:** *100*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-244">**Container utilization percentage:** *100*</span></span>

### <a name="create-a-new-container-build-template"></a><span data-ttu-id="a8bd0-245">Creare un nuovo modello di versione del contenitore</span><span class="sxs-lookup"><span data-stu-id="a8bd0-245">Create a new container build template</span></span>

<span data-ttu-id="a8bd0-246">Per creare un nuovo modello di versione del contenitore, effettua le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-246">To create a new container build template, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-247">Vai a **Gestione magazzino** \> **Impostazioni** \> **Contenitori** \> **Modello di versione contenitore**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-247">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container build template**.</span></span>
1. <span data-ttu-id="a8bd0-248">Seleziona **Nuovo** per creare un modello di versione del contenitore con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-248">Select **New** to create a container build template that has the following settings:</span></span>

    - <span data-ttu-id="a8bd0-249">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-249">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="a8bd0-250">**ID modello contenitore:** *Scatola*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-250">**Container template ID:** *Box*</span></span>
    - <span data-ttu-id="a8bd0-251">**ID gruppo di contenitori:** *Scatole*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-251">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="a8bd0-252">**Tipi di query di base:** *Riga allocazione vendite*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-252">**Base query types:** *Sales allocation line*</span></span>
    - <span data-ttu-id="a8bd0-253">**Codice del passaggio ciclo:** *234*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-253">**Wave step code:** *234*</span></span>
    - <span data-ttu-id="a8bd0-254">**Consenti prelievi suddivisi:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-254">**Allow split picks:** *Yes*</span></span>
    - <span data-ttu-id="a8bd0-255">**Strategia di imballaggio del contenitore:** *Imballa solo nel contenitore corrente*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-255">**Container packing strategy:** *Pack into current container only*</span></span>
    - <span data-ttu-id="a8bd0-256">**Imballa per unità direttiva:** *No*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-256">**Pack by directive unit:** *No*</span></span>

1. <span data-ttu-id="a8bd0-257">Mentre la riga per il nuovo modello è ancora selezionata, seleziona **Modifica query** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-257">While the row for the new template is still selected, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="a8bd0-258">Viene visualizzata la finestra di dialogo dell'editor di query standard.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-258">A standard query editor dialog box appears.</span></span> <span data-ttu-id="a8bd0-259">Nella scheda **Ordinamento** seleziona **Aggiungi** per aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-259">On the **Sorting** tab, select **Add** to add a row that has the following settings:</span></span>

    - <span data-ttu-id="a8bd0-260">**Tabella:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-260">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="a8bd0-261">**Tabella derivata:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-261">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="a8bd0-262">**Campo:** *Numero d'ordine*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-262">**Field:** *Order number*</span></span>
    - <span data-ttu-id="a8bd0-263">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-263">**Search direction:** *Ascending*</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a8bd0-264">Per evitare di scorrere su tutti gli altri contenitori aperti e per accelerare il processo controllando un contenitore alla volta, utilizza la strategia *Imballa solo nel contenitore corrente* oltre all'ordinamento per numero d'ordine.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-264">To avoid cycling over all the other open containers, and to speed up the process by checking one container at a time, use the *Pack into current container only* strategy in addition to sorting by order number.</span></span> <span data-ttu-id="a8bd0-265">Questa combinazione funzionerà come una pausa di lavoro su un modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-265">This combination will work like a work break on a work template.</span></span>

1. <span data-ttu-id="a8bd0-266">Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-266">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="a8bd0-267">Mentre la riga per il nuovo modello è ancora selezionata, seleziona **Vincoli combinazione contenitore** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-267">While the row for the new template is still selected, select **Container mixing constraints** on the Action Pane.</span></span>

    <span data-ttu-id="a8bd0-268">Ora aggiungerai un vincolo che inserisce gli articoli di un singolo ordine in un unico contenitore.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-268">You will now add a constraint that puts items from a single order into a single container.</span></span> <span data-ttu-id="a8bd0-269">Gli articoli di qualsiasi altro ordine verranno inseriti in un contenitore separato.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-269">Items from any other order will be put into a separate container.</span></span>

1. <span data-ttu-id="a8bd0-270">Seleziona **Nuovo** per creare un vincolo di combinazione del contenitore con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-270">Select **New** to create a mixing constraint that has the following settings:</span></span>

    - <span data-ttu-id="a8bd0-271">**Tabella:** *Ordini cliente*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-271">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="a8bd0-272">**Seleziona campo:** *SalesId* (Il campo apparirà come *Ordine cliente* nella griglia.)</span><span class="sxs-lookup"><span data-stu-id="a8bd0-272">**Field select:** *SalesId* (The field will appear as *Sales order* in the grid.)</span></span>

1. <span data-ttu-id="a8bd0-273">Seleziona **OK** per aggiungere il vincolo.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-273">Select **OK** to add the constraint.</span></span>
1. <span data-ttu-id="a8bd0-274">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-274">Close the page.</span></span>

### <a name="set-up-a-wave-template-for-containerization"></a><span data-ttu-id="a8bd0-275">Impostare un modello di ondata per la containerizzazione</span><span class="sxs-lookup"><span data-stu-id="a8bd0-275">Set up a wave template for containerization</span></span>

<span data-ttu-id="a8bd0-276">Per impostare un modello ciclo, effettua le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-276">To set up a wave template, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-277">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-277">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="a8bd0-278">Nel riquadro dell'elenco, imposta il campo **Tipo di modello ondata** su *Spedizione*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-278">In the list pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="a8bd0-279">Seleziona il modello **63 Containerizzazione** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-279">Select the **63 Containerization** template in the list.</span></span>
1. <span data-ttu-id="a8bd0-280">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-280">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a8bd0-281">Nella Scheda dettaglio **Metodi**, nella colonna **Metodi selezionati**, trova la seguente riga:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-281">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="a8bd0-282">**Nome del metodo:** *containerizzazione*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-282">**Method name:** *containerization*</span></span>
    - <span data-ttu-id="a8bd0-283">**Nome:** *Containerizzazione*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-283">**Name:** *Containerization*</span></span>

1. <span data-ttu-id="a8bd0-284">Impostare il campo **Codice passaggio ondata** per la riga su *234*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-284">Set the **Wave step code** field for the line to *234*.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="a8bd0-285">Configurare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="a8bd0-285">Set up a work template</span></span>

<span data-ttu-id="a8bd0-286">Per impostare un modello lavoro, effettua le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-286">To set up a work template, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-287">Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-287">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="a8bd0-288">Imposta il campo **Tipo ordine di lavoro** su *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-288">Set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="a8bd0-289">Nella griglia **Panoramica**, trovare e selezionare il modello di lavoro da utilizzare per imballare singoli ordini per contenitore.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-289">In the **Overview** grid, find and select the work template that should be used for packing single orders per container.</span></span> <span data-ttu-id="a8bd0-290">Per questo scenario, selezionare il modello **63 Prelievo per contenitore**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-290">For this scenario, select the **63 Pick to container** template.</span></span>
1. <span data-ttu-id="a8bd0-291">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-291">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="a8bd0-292">Viene visualizzata la finestra di dialogo dell'editor di query standard.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-292">A standard query editor dialog box appears.</span></span> <span data-ttu-id="a8bd0-293">Nella scheda **Ordinamento** aggiungi le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-293">On the **Sorting** tab, add the following lines:</span></span>

    - <span data-ttu-id="a8bd0-294">Riga 1:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-294">Line 1:</span></span>

        - <span data-ttu-id="a8bd0-295">**Tabella:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-295">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="a8bd0-296">**Tabella derivata:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-296">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="a8bd0-297">**Campo:** *ID spedizione*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-297">**Field:** *Shipment ID*</span></span>
        - <span data-ttu-id="a8bd0-298">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-298">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="a8bd0-299">Riga 2:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-299">Line 2:</span></span>

        - <span data-ttu-id="a8bd0-300">**Tabella:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-300">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="a8bd0-301">**Tabella derivata:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-301">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="a8bd0-302">**Campo:** *Numero d'ordine*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-302">**Field:** *Order number*</span></span>
        - <span data-ttu-id="a8bd0-303">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-303">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="a8bd0-304">Riga 3:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-304">Line 3:</span></span>

        - <span data-ttu-id="a8bd0-305">**Tabella:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-305">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="a8bd0-306">**Tabella derivata:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-306">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="a8bd0-307">**Campo:** *ID contenitore*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-307">**Field:** *Container ID*</span></span>
        - <span data-ttu-id="a8bd0-308">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-308">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="a8bd0-309">Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-309">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="a8bd0-310">Viene visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?".</span><span class="sxs-lookup"><span data-stu-id="a8bd0-310">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="a8bd0-311">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-311">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="a8bd0-312">Mentre il modello **63 Prelievo per contenitore** è ancora selezionato, seleziona **Suddivisioni intestazione lavoro** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-312">While the **63 Pick to container** template is still selected, select **Work header breaks** on the Action Pane.</span></span>

    <span data-ttu-id="a8bd0-313">Ora applicherai le impostazioni per suddividere il lavoro in modo che ogni contenitore nell'ordine sia collegato a un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-313">You will now apply settings to break the work so that each container in the order is linked to one work order.</span></span>

1. <span data-ttu-id="a8bd0-314">Seleziona la casella di controllo **Raggruppa per questo campo** per ogni riga della pagina **Suddivisioni intestazione lavoro** (**ID spedizione**, **Numero d'ordine**, e **ID contenitore**).</span><span class="sxs-lookup"><span data-stu-id="a8bd0-314">Select the **Group by this field** checkbox for each row on the **Work header breaks** page (**Shipment ID**, **Order number**, and **Container ID**).</span></span>
1. <span data-ttu-id="a8bd0-315">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-315">Close the page.</span></span>

### <a name="set-up-shipment-consolidation-policies"></a><span data-ttu-id="a8bd0-316">Impostare i criteri consolidamento spedizione</span><span class="sxs-lookup"><span data-stu-id="a8bd0-316">Set up shipment consolidation policies</span></span>

<span data-ttu-id="a8bd0-317">Per configurare un criterio di consolidamento spedizione, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-317">To set up a shipment consolidation policy, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-318">Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-318">Go to **Warehouse management \> Setup \> Release to warehouse \> Shipment consolidation policies**.</span></span>
1. <span data-ttu-id="a8bd0-319">Nel riquadro dell'elenco, imposta il campo **Tipo di criterio** su *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-319">In the list pane, set the **Policy type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="a8bd0-320">Seleziona il criterio **predefinito** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-320">Select the **Default** policy in the list.</span></span>
1. <span data-ttu-id="a8bd0-321">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-321">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a8bd0-322">Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi selezionati**, seleziona la riga in cui il campo **Nome campo** è impostato su *Numero ordine*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-322">On the **Consolidation fields** FastTab, in the **Selected fields** list, select the row where the **Field name** field is set to *Order number*.</span></span>
1. <span data-ttu-id="a8bd0-323">Seleziona il pulsante **Rimuovi** ![Freccia sinistra](media/backward-button.png) per spostare il campo sull'elenco **Campi rimanenti**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-323">Select the **Remove** button ![Left arrow](media/backward-button.png) to move the field to the **Remaining fields** list.</span></span>
1. <span data-ttu-id="a8bd0-324">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-324">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-physical-dimensions-for-the-product"></a><span data-ttu-id="a8bd0-325">Impostare le dimensioni fisiche del prodotto</span><span class="sxs-lookup"><span data-stu-id="a8bd0-325">Set up physical dimensions for the product</span></span>

<span data-ttu-id="a8bd0-326">Per impostare le dimensioni fisiche per i prodotti che verranno utilizzati in questo scenario, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-326">To set up physical dimensions for the products that will be used in this scenario, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-327">Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-327">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="a8bd0-328">Seleziona il prodotto in cui il campo **Numero articolo** è impostato su *A0001*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-328">Select the product where the **Item number** field is set to *A0001*.</span></span>
1. <span data-ttu-id="a8bd0-329">Nel riquadro azioni della scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **Dimensioni fisiche**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-329">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="a8bd0-330">Nella pagina **Dimensioni fisiche** vedi la seguente riga nella griglia:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-330">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="a8bd0-331">**Unità:** *pezzi*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-331">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="a8bd0-332">**Peso lordo:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-332">**Gross weight:** *3.00*</span></span>
    - <span data-ttu-id="a8bd0-333">**Larghezza:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-333">**Width:** *2.00*</span></span>
    - <span data-ttu-id="a8bd0-334">**Profondità:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-334">**Depth:** *2.00*</span></span>
    - <span data-ttu-id="a8bd0-335">**Altezza:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-335">**Height:** *4.00*</span></span>
    - <span data-ttu-id="a8bd0-336">**Volume:** *16,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-336">**Volume:** *16.00*</span></span>

1. <span data-ttu-id="a8bd0-337">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-337">Close the page.</span></span>
1. <span data-ttu-id="a8bd0-338">Seleziona il prodotto in cui il campo **Numero articolo** è impostato su *A0002*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-338">Select the product where the **Item number** field is set to *A0002*.</span></span>
1. <span data-ttu-id="a8bd0-339">Nel riquadro azioni della scheda **Gestione articoli**, nel gruppo **Magazzino**, selezionare **Dimensioni fisiche**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-339">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="a8bd0-340">Nella pagina **Dimensioni fisiche** vedi la seguente riga nella griglia:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-340">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="a8bd0-341">**Unità:** *pezzi*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-341">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="a8bd0-342">**Peso lordo:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-342">**Gross weight:** *4.00*</span></span>
    - <span data-ttu-id="a8bd0-343">**Larghezza:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-343">**Width:** *3.00*</span></span>
    - <span data-ttu-id="a8bd0-344">**Profondità:** *1,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-344">**Depth:** *1.00*</span></span>
    - <span data-ttu-id="a8bd0-345">**Altezza:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-345">**Height:** *3.00*</span></span>
    - <span data-ttu-id="a8bd0-346">**Volume:** *9,00*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-346">**Volume:** *9.00*</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="a8bd0-347">Creare l'ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="a8bd0-347">Create sales order 1</span></span>

<span data-ttu-id="a8bd0-348">Per creare un ordine cliente, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-348">To create a sales order, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-349">Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-349">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a8bd0-350">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-350">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8bd0-351">Viene visualizzata una finestra di dialogo per la creazione di un nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-351">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="a8bd0-352">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-352">Set the following values:</span></span>

    - <span data-ttu-id="a8bd0-353">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-353">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="a8bd0-354">**Magazzino:** *63*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-354">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="a8bd0-355">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-355">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="a8bd0-356">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-356">The new sales order is opened.</span></span> <span data-ttu-id="a8bd0-357">Nella Scheda dettagli **Righe ordine cliente**, aggiungi le seguenti righe di vendita:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-357">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="a8bd0-358">Riga 1:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-358">Line 1:</span></span>

        - <span data-ttu-id="a8bd0-359">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-359">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="a8bd0-360">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-360">**Quantity:** *2*</span></span>

    - <span data-ttu-id="a8bd0-361">Riga 2:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-361">Line 2:</span></span>

        - <span data-ttu-id="a8bd0-362">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-362">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="a8bd0-363">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-363">**Quantity:** *2*</span></span>

1. <span data-ttu-id="a8bd0-364">Seleziona la prima riga, quindi seleziona **Inventario \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-364">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="a8bd0-365">Nella pagina **Prenotazione**, selezionare **Prenota lotto**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-365">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="a8bd0-366">Quindi, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-366">Then close the page.</span></span>
1. <span data-ttu-id="a8bd0-367">Ripeti i due passaggi precedenti per la seconda riga.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-367">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="a8bd0-368">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-368">Close the page.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="a8bd0-369">Creare l'ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="a8bd0-369">Create sales order 2</span></span>

<span data-ttu-id="a8bd0-370">Per creare un secondo ordine cliente, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-370">To create a second sales order, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-371">Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-371">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a8bd0-372">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-372">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8bd0-373">Viene visualizzata una finestra di dialogo per la creazione di un nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-373">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="a8bd0-374">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-374">Set the following values:</span></span>

    - <span data-ttu-id="a8bd0-375">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="a8bd0-376">**Magazzino:** *63*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-376">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="a8bd0-377">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-377">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="a8bd0-378">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-378">The new sales order is opened.</span></span> <span data-ttu-id="a8bd0-379">Nella Scheda dettagli **Righe ordine cliente**, aggiungi le seguenti righe di vendita:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-379">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="a8bd0-380">Riga 1:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-380">Line 1:</span></span>

        - <span data-ttu-id="a8bd0-381">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-381">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="a8bd0-382">**Quantità:** *4*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-382">**Quantity:** *4*</span></span>

    - <span data-ttu-id="a8bd0-383">Riga 2:</span><span class="sxs-lookup"><span data-stu-id="a8bd0-383">Line 2:</span></span>

        - <span data-ttu-id="a8bd0-384">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-384">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="a8bd0-385">**Quantità:** *4*</span><span class="sxs-lookup"><span data-stu-id="a8bd0-385">**Quantity:** *4*</span></span>

1. <span data-ttu-id="a8bd0-386">Seleziona la prima riga, quindi seleziona **Inventario \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-386">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="a8bd0-387">Nella pagina **Prenotazione**, selezionare **Prenota lotto**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-387">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="a8bd0-388">Quindi, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-388">Then close the page.</span></span>
1. <span data-ttu-id="a8bd0-389">Ripeti i due passaggi precedenti per la seconda riga.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-389">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="a8bd0-390">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-390">Close the page.</span></span>

### <a name="create-the-load"></a><span data-ttu-id="a8bd0-391">Creare il carico</span><span class="sxs-lookup"><span data-stu-id="a8bd0-391">Create the load</span></span>

<span data-ttu-id="a8bd0-392">Segui questi passaggi per creare un carico per ciascun ordine creato per questo scenario e quindi rilascialo nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-392">To create a load for each order that you created for this scenario and then release it to the warehouse, follow these steps.</span></span>

1. <span data-ttu-id="a8bd0-393">Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-393">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="a8bd0-394">Nella scheda **Righe di vendita**, trova e seleziona tutte le righe degli ordini cliente creati per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-394">On the **Sales lines** tab, find and select all the sales order lines from the sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="a8bd0-395">Nel riquadro azioni, nella scheda **Domanda e offerta**, nel gruppo **Aggiungi** seleziona **Al nuovo carico**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-395">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span> <span data-ttu-id="a8bd0-396">Le righe dell'ordine selezionate vengono aggiunte a un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-396">The selected order lines are added to a new load.</span></span>
1. <span data-ttu-id="a8bd0-397">Nella finestra di dialogo **Assegnazione modello di carico**, nel campo **ID modello carico**, seleziona un modello di caricamento, ad esempio *40' Contenitore*.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-397">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *40' Container*.</span></span>
1. <span data-ttu-id="a8bd0-398">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-398">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="a8bd0-399">Nella sezione **Carichi**, trova e seleziona il carico che hai appena creato.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-399">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="a8bd0-400">Seleziona **Rilascia \> Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-400">Select **Release \> Release to warehouse**.</span></span>
1. <span data-ttu-id="a8bd0-401">Nella finestra di dialogo **Rilascia in magazzino** seleziona **OK** per rilasciare il carico selezionato nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-401">In the **Release to warehouse** dialog box, select **OK** to release the selected load to the warehouse.</span></span>

### <a name="verify-the-shipments-and-containers"></a><span data-ttu-id="a8bd0-402">Verificare le spedizioni e i contenitori</span><span class="sxs-lookup"><span data-stu-id="a8bd0-402">Verify the shipments and containers</span></span>

<span data-ttu-id="a8bd0-403">La seguente procedura consente di verificare le spedizioni che sono state create.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-403">The following procedure lets you verify the shipments that have been created.</span></span> <span data-ttu-id="a8bd0-404">Usala per rivedere l'ordine che hai creato per questo scenario e per assicurarti di aver ottenuto i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-404">Use it to review the order that you created for this scenario, to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="a8bd0-405">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-405">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="a8bd0-406">Trova e seleziona la spedizione che è stata creata per il carico che hai appena rilasciato.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-406">Find and select the shipment that was created for the load that you just released.</span></span>
1. <span data-ttu-id="a8bd0-407">Nel riquadro azioni, nella scheda **Trasporto** seleziona **Visualizza contenitori**.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-407">On the Action Pane, on the **Transportation** tab, select **View containers**.</span></span>
1. <span data-ttu-id="a8bd0-408">Verifica che gli articoli degli ordini cliente sono stati containerizzati in due contenitori diversi.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-408">Confirm that the items from the sales orders were containerized into two different containers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8bd0-409">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a8bd0-409">Additional resources</span></span>

- [<span data-ttu-id="a8bd0-410">Containerizzazione</span><span class="sxs-lookup"><span data-stu-id="a8bd0-410">Containerization</span></span>](wave-containerization.md)
