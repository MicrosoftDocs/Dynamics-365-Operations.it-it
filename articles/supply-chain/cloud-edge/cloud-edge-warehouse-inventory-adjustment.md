---
title: Rettifica scorte magazzino
description: In questo argomento vengono fornite informazioni sul giornale di registrazione e sull'elaborazione della rettifica scorte magazzino quando si utilizzano unità di scala.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a451816078ca2e77f30379828777209dc48bd849
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026135"
---
# <a name="warehouse-inventory-adjustment"></a><span data-ttu-id="f6a1f-103">Rettifica scorte magazzino</span><span class="sxs-lookup"><span data-stu-id="f6a1f-103">Warehouse inventory adjustment</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f6a1f-104">La funzionalità di rettifica scorte magazzino viene utilizzata durante l'esecuzione di unità di scala per cloud e rete perimetrale per [carichi di lavoro di produzione](cloud-edge-workload-manufacturing.md) e [carichi di lavoro di gestione del magazzino](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="f6a1f-104">The Warehouse inventory adjustment feature is used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="f6a1f-105">Quando un lavoratore esegue una rettifica magazzino utilizzando l'app di magazzino rispetto a un carico di lavoro di gestione del magazzino per unità di scala, l'aggiornamento delle scorte fisiche disponibili deve essere elaborato dal processo batch **Giornale di registrazione rettifica scorte di magazzino** , che esegui e pianifichi andando a **Gestione magazzino> Attività periodiche> Giornale di registrazione rettifica scorte magazzino**.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-105">When a worker does an inventory adjustment using the warehouse app against a scale unit warehouse management workload, the physical on-hand update must be processed by the **Warehouse inventory adjustment journal** batch job, which you run and schedule by going to **Warehouse management > Periodic tasks > Warehouse inventory adjustment journal**.</span></span>

<span data-ttu-id="f6a1f-106">I seguenti processi di lavoro dell'app di magazzino utilizzano attualmente il **Giornale di registrazione rettifica scorte di magazzino** su carichi di lavoro per unità di scala:</span><span class="sxs-lookup"><span data-stu-id="f6a1f-106">The following warehouse app work processes currently use the **Warehouse inventory adjustment journal** on scale unit workloads:</span></span>

- <span data-ttu-id="f6a1f-107">Rettifica (in ingresso/uscita)</span><span class="sxs-lookup"><span data-stu-id="f6a1f-107">Adjustment in/out</span></span>
- <span data-ttu-id="f6a1f-108">Conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="f6a1f-108">Cycle counting</span></span>
- <span data-ttu-id="f6a1f-109">Caricamento targa</span><span class="sxs-lookup"><span data-stu-id="f6a1f-109">License plate loading</span></span>

<span data-ttu-id="f6a1f-110">Diverse transazioni di magazzino vengono create come parte di ogni processo di rettifica magazzino su cloud e rete perimetrale perché le distribuzioni hub e unità di scala condividono i record di inventario.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-110">Several inventory transactions are created as part of each inventory adjustment process because the hub and scale unit deployments share the inventory records.</span></span>

## <a name="inventory-adjustment-example"></a><span data-ttu-id="f6a1f-111">Esempio di rettifica magazzino</span><span class="sxs-lookup"><span data-stu-id="f6a1f-111">Inventory adjustment example</span></span>

<span data-ttu-id="f6a1f-112">In questo esempio, un addetto al magazzino ha utilizzato l'app del magazzino per registrare l'aggiunta di scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-112">In this example, a warehouse worker has used the warehouse app to register the adding of on-hand inventory.</span></span>

<span data-ttu-id="f6a1f-113">Innanzitutto, il carico di lavoro per unità di scala crea una transazione di rettifica scorte di magazzino per la rettifica fisica positiva, che viene quindi sincronizzata con l'hub e si traduce in un aumento delle scorte disponibili sull'hub.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-113">First, the scale unit workload creates a warehouse inventory adjustment transaction for the positive physical adjustment, which is then synchronized to the hub and results in an increase of the on-hand inventory on the hub.</span></span>

| <span data-ttu-id="f6a1f-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="f6a1f-114">Type</span></span>                                    | <span data-ttu-id="f6a1f-115">Unità di scala</span><span class="sxs-lookup"><span data-stu-id="f6a1f-115">Scale unit</span></span> | <span data-ttu-id="f6a1f-116">Direzione</span><span class="sxs-lookup"><span data-stu-id="f6a1f-116">Direction</span></span> | <span data-ttu-id="f6a1f-117">Hub</span><span class="sxs-lookup"><span data-stu-id="f6a1f-117">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="f6a1f-118">Rettifica scorte magazzino</span><span class="sxs-lookup"><span data-stu-id="f6a1f-118">Warehouse inventory adjustment</span></span>          | <span data-ttu-id="f6a1f-119">+1</span><span class="sxs-lookup"><span data-stu-id="f6a1f-119">+1</span></span>         | ->        | <span data-ttu-id="f6a1f-120">+1</span><span class="sxs-lookup"><span data-stu-id="f6a1f-120">+1</span></span>  |

<span data-ttu-id="f6a1f-121">L'hub elabora quindi una registrazione a giornale di conteggio, che viene ricevuta tramite i [messaggi dell'elaboratore di messaggi](cloud-edge-message-processor-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f6a1f-121">The hub then processes a counting journal posting, which is received through [message processor messages](cloud-edge-message-processor-messages.md).</span></span> <span data-ttu-id="f6a1f-122">Questo aggiorna le scorte aggiuntive disponibili.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-122">This updates the additional inventory on hand.</span></span> <span data-ttu-id="f6a1f-123">Per evitare il doppio delle scorte disponibili, l'hub crea una transazione di contropartita come parte di questo processo e rimuove le scorte disponibili registrate in precedenza correlate alla rettifica scorte magazzino.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-123">To prevent double inventory on hand, the hub creates an offset transaction as part of this process and removes the previously recorded on-hand inventory that is related to the warehouse inventory adjustment.</span></span>

| <span data-ttu-id="f6a1f-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="f6a1f-124">Type</span></span>                                    | <span data-ttu-id="f6a1f-125">Unità di scala</span><span class="sxs-lookup"><span data-stu-id="f6a1f-125">Scale unit</span></span> | <span data-ttu-id="f6a1f-126">Direzione</span><span class="sxs-lookup"><span data-stu-id="f6a1f-126">Direction</span></span> | <span data-ttu-id="f6a1f-127">Hub</span><span class="sxs-lookup"><span data-stu-id="f6a1f-127">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="f6a1f-128">Conteggio</span><span class="sxs-lookup"><span data-stu-id="f6a1f-128">Counting</span></span>                                | <span data-ttu-id="f6a1f-129">+1</span><span class="sxs-lookup"><span data-stu-id="f6a1f-129">+1</span></span>         | <-        | <span data-ttu-id="f6a1f-130">+1</span><span class="sxs-lookup"><span data-stu-id="f6a1f-130">+1</span></span>  |
| <span data-ttu-id="f6a1f-131">Rettifica scorte magazzino (contropartita)</span><span class="sxs-lookup"><span data-stu-id="f6a1f-131">Warehouse inventory adjustment (Offset)</span></span> | <span data-ttu-id="f6a1f-132">-1</span><span class="sxs-lookup"><span data-stu-id="f6a1f-132">-1</span></span>         | <-        | <span data-ttu-id="f6a1f-133">-1</span><span class="sxs-lookup"><span data-stu-id="f6a1f-133">-1</span></span>  |

<span data-ttu-id="f6a1f-134">Dopo che un'unità di scala ha creato un **Giornale di registrazione rettifica scorte magazzino** sull'hub, puoi rivedere sia il **Giornale di registrazione di conteggio** che il **Giornale di registrazione di contropartita** che vengono creati dall'hub come parte del processo di rettifica.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-134">After a scale unit has created a **Warehouse inventory adjustment journal** on the hub, you can review both the **Counting journal** and the **Offset journal**, which are created by the hub as part of the adjustment process.</span></span>

<span data-ttu-id="f6a1f-135">È possibile rivedere ciascuna di queste registrazioni e transazioni in Supply Chain Management effettuando le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="f6a1f-135">You can review each of these journal entries and transaction in Supply Chain Management by doing the following steps:</span></span>

1. <span data-ttu-id="f6a1f-136">Accedi all'unità di scala.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-136">Sign in on the scale unit.</span></span>
1. <span data-ttu-id="f6a1f-137">Vai a **Gestione magazzino \> Attività periodiche \> Giornale di registrazione rettifica scorte magazzino**.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-137">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="f6a1f-138">Nella pagina **Giornale di registrazione rettifica scorte magazzino**, trova e apri il giornale che ha registrato la modifica delle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-138">On the **Warehouse inventory adjustment journal** page, find and open the journal that recorded the on-hand inventory change.</span></span> <span data-ttu-id="f6a1f-139">La sezione **Righe giornale di registrazione** mostra ogni rettifica registrata da questo giornale.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-139">The **Journal lines** section shows each adjustment recorded by this journal.</span></span>
1. <span data-ttu-id="f6a1f-140">Accedi all'hub.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-140">Sign in on the hub.</span></span>
1. <span data-ttu-id="f6a1f-141">Vai a **Gestione magazzino \> Attività periodiche \> Giornale di registrazione rettifica scorte magazzino**.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-141">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="f6a1f-142">Nella pagina **Giornale di registrazione rettifica scorte magazzino**, dovresti vedere lo stesso giornale di registrazione elencato se l'hub e l'unità di scala sono stati sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-142">On the **Warehouse inventory adjustment journal** page, you should see the same journal listed if the hub and scale unit have synced.</span></span>
1. <span data-ttu-id="f6a1f-143">Apri il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-143">Open the journal.</span></span> <span data-ttu-id="f6a1f-144">Se i [messaggi dell'elaboratore di messaggi](cloud-edge-message-processor-messages.md) sono stati elaborati, vedrai i collegamenti al **Giornale di registrazione di conteggio** e al **Giornale di registrazione di contropartita** nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-144">If the [message processor messages](cloud-edge-message-processor-messages.md) have been processed, you will see links to the **Counting journal** and the **Offset journal** in the header.</span></span>
    - <span data-ttu-id="f6a1f-145">Il **Giornale di registrazione di conteggio** dovrebbe mostrare gli stessi valori di dimensione delle righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-145">The **Counting journal** should show the same dimension values as the journal lines.</span></span>
    - <span data-ttu-id="f6a1f-146">Il **Giornale di registrazione di contropartita** dovrebbe mostrare la contropartita, che rimuove la doppia rettifica magazzino.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-146">The **Offset journal** should show the offset, which removes the double inventory adjustment.</span></span>
    > [!NOTE]
    > <span data-ttu-id="f6a1f-147">Quando tutta la sincronizzazione e l'elaborazione sono state completate, il **Giornale doi registrazione di conteggio** e il **Giornale di registrazione di contropartita** vengono sincronizzati di nuovo con l'unità di scala.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-147">When all syncing and processing is complete, the **Counting journal** and the **Offset journal** are synced back to the scale unit.</span></span> <span data-ttu-id="f6a1f-148">Possono anche essere visualizzati dalla pagina **Giornale di registrazione rettifica scorte magazzino** pertinente.</span><span class="sxs-lookup"><span data-stu-id="f6a1f-148">These can also be viewed from the relevant **Warehouse inventory adjustment journal** page.</span></span>
