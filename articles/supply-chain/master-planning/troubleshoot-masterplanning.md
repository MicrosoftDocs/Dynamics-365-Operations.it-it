---
title: Risolvere i problemi della pianificazione principale
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si lavora con la pianificazione principale.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1492854b7d2da480942800e378be9d2bb60bb1f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645067"
---
# <a name="troubleshoot-master-planning"></a><span data-ttu-id="a2c8b-103">Risolvere i problemi della pianificazione principale</span><span class="sxs-lookup"><span data-stu-id="a2c8b-103">Troubleshoot master planning</span></span>

<span data-ttu-id="a2c8b-104">Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si lavora con la pianificazione principale.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-104">This topic describes how to fix issues that you might encounter while you work with master planning.</span></span>

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a><span data-ttu-id="a2c8b-105">L'esplosione della distinta base si comporta in modo diverso per gli ordini di produzione fissi e per gli ordini di produzione stimati per il lavoro creato manualmente.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-105">Bill of materials explosion behaves differently for firmed production orders and for estimated production orders for manually created work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2c8b-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="a2c8b-106">Issue description</span></span>

<span data-ttu-id="a2c8b-107">Quando un ordine di produzione viene stabilizzato, gli articoli non vengono esplosi quando si esplode la distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="a2c8b-107">When a production order is firmed, the items aren't exploded when you explode the bill of materials (BOM).</span></span> <span data-ttu-id="a2c8b-108">Tuttavia, quando si crea manualmente un ordine di lavoro e quindi si stima l'ordine di produzione, gli articoli vengono esplosi.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-108">However, when you manually create a work order and then estimate the production order, the items are exploded.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2c8b-109">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a2c8b-109">Issue resolution</span></span>

<span data-ttu-id="a2c8b-110">Il sistema funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-110">The system is working as expected.</span></span> <span data-ttu-id="a2c8b-111">L'esplosione che si verifica quando l'ordine di produzione viene stabilizzato punterà all'ordine pianificato, ma in questo caso non sembra che l'ordine pianificato sia attualmente confermato.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-111">The explosion that occurs when the production order is firmed will point to the planned order, but it doesn't appear that the planned order is currently firmed in this case.</span></span> <span data-ttu-id="a2c8b-112">Tuttavia, se l'ordine di produzione è stato stimato, l'esplosione viene attivata dall'ordine di produzione rilasciato in cui non esiste alcun ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-112">However, if the production order has been estimated, the explosion is triggered from the released production order where no planned order exists.</span></span>

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a><span data-ttu-id="a2c8b-113">Il valore Ritardo non viene aggiornato quando riprogramma un ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-113">The Delay value isn't updated when I reschedule a planned order.</span></span>

<span data-ttu-id="a2c8b-114">Per aggiornare il ritardo per gli ordini pianificati, aprire la finestra di dialoto **Riprogrammazione** per l'ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-114">To update the delay for planned orders, open the **Rescheduling** dialog box for the planned order.</span></span> <span data-ttu-id="a2c8b-115">Nella Scheda dettaglio **Esplosione**, assicurarsi che l'opzione **Esegui esplosione dopo la riprogrammazione** sia impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-115">On the **Explosion** FastTab, make sure that the **Perform explosion after rescheduling** option is set to *Yes*.</span></span>

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a><span data-ttu-id="a2c8b-116">La programmazione della produzione non considera i margini di sicurezza impostati sulla copertura dell'articolo per la fornitura con pegging.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-116">Production scheduling doesn't consider the safety margins that are set on the item coverage for pegged supply.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2c8b-117">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="a2c8b-117">Issue description</span></span>

<span data-ttu-id="a2c8b-118">La pianificazione generale considera i margini di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-118">Master planning considers the safety margins.</span></span> <span data-ttu-id="a2c8b-119">Tuttavia, i margini di sicurezza vengono ignorati quando vengono pianificati gli ordini di produzione pianificati.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-119">However, the safety margins are ignored when planned production orders are scheduled.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2c8b-120">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a2c8b-120">Issue resolution</span></span>

<span data-ttu-id="a2c8b-121">I margini vengono considerati solo durante la pianificazione generale, non durante la pianificazione manuale.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-121">Margins are considered only during master planning, not during manual scheduling.</span></span> <span data-ttu-id="a2c8b-122">I margini sono progettati per fungere da cuscinetto durante la fase di pianificazione, per dare un certo "margine" al processo vero e proprio.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-122">Margins are designed to act as a buffer during the planning phase, to give some "margin" for the actual process.</span></span>

<span data-ttu-id="a2c8b-123">Per ottenere il risultato desiderato, è possibile rimuovere il margine.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-123">To get the desired result, you can remove the margin.</span></span> <span data-ttu-id="a2c8b-124">Il ciclo di lavorazione deve quindi essere aggiornato in modo che includa il tempo desiderato (ad esempio, come tempo di coda).</span><span class="sxs-lookup"><span data-stu-id="a2c8b-124">The route must then be updated so that it includes the desired time (for example, as queue time).</span></span> <span data-ttu-id="a2c8b-125">Sia la pianificazione generale che la pianificazione manuale devono quindi produrre lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-125">Both master planning and manual scheduling should then produce the same result.</span></span>

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a><span data-ttu-id="a2c8b-126">Gli ordini pianificati vengono generati anche se sono presenti articoli in magazzino e per essi esistono già ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-126">Planned orders are generated even though we have items in stock and production orders already exist for them.</span></span>

<span data-ttu-id="a2c8b-127">È possibile risolvere questo problema aumentando il valore **Giorni positivi** per i gruppi rilevanti nella pagina **Gruppo di copertura**.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-127">You might be able to fix this issue by increasing the **Positive days** value for the relevant groups on the **Coverage group** page.</span></span> <span data-ttu-id="a2c8b-128">Questa modifica farà sì che il sistema determini se le scorte disponibili possono essere utilizzate per la domanda.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-128">This change will cause the system to determine whether on-hand inventory can be used for the demand.</span></span> <span data-ttu-id="a2c8b-129">Quindi non verrà generato un nuovo ordine pianificato per gli articoli disponibili.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-129">Then a new planned order won't be generated for the items that are in stock.</span></span>

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a><span data-ttu-id="a2c8b-130">La pianificazione generale non sembra rispettare i limiti di capacità e sta pianificando più della capacità disponibile.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-130">Master planning doesn't seem to respect capacity limitations and is scheduling more than the available capacity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2c8b-131">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="a2c8b-131">Issue description</span></span>

<span data-ttu-id="a2c8b-132">Quando si utilizza la pianificazione delle operazioni in cui è presente una capacità finita e dove il ciclo di lavorazione specifica una combinazione di requisiti sia per un gruppo di risorse che per le singole risorse, esiste una piccola possibilità di prenotazioni in eccesso a causa del modo in cui l'algoritmo convalida i conflitti di capacità.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-132">When you use operation scheduling where there is finite capacity, and where the route specifies a mix of requirements for both a resource group and individual resources, there is a small chance of overbooking because of the way that the algorithm validates for capacity conflicts.</span></span> <span data-ttu-id="a2c8b-133">Questo prenotazione in eccesso può verificarsi quando si utilizzano helper per eseguire la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-133">This overbooking can occur when you use helpers to run master planning.</span></span> <span data-ttu-id="a2c8b-134">È molto probabile che si verifichi se sono presenti molti processi che hanno un tempo di esecuzione relativamente breve.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-134">It's most likely to occur if there are many jobs that have a relatively short runtime.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2c8b-135">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a2c8b-135">Issue resolution</span></span>

<span data-ttu-id="a2c8b-136">Se è essenziale che non si verifichi la prenotazione in eccesso per la pianificazione delle operazioni, è possibile rendere la pianificazione parte della pianificazione generale a thread singolo attivando l'opzione **Capacità finita accurata per la pianificazione delle operazioni** nella pagina **Parametri di pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-136">If it's essential that no overbooking occur for operation scheduling, you can make the scheduling part of master planning single-threaded by turning on the **Accurate finite capacity for Operation Scheduling** option on the **Master planning parameters** page.</span></span> <span data-ttu-id="a2c8b-137">Questa opzione non è disponibile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-137">This option isn't available by default.</span></span> <span data-ttu-id="a2c8b-138">È necessario aggiungerla manualmente alla pagina utilizzando le funzionalità di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-138">You must manually add it to the page by using personalization features.</span></span> <span data-ttu-id="a2c8b-139">Quando si utilizza questa opzione, la pianificazione verrà eseguita più lentamente a causa della mancanza di elaborazione parallela.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-139">When you use this option, scheduling will run more slowly because of the lack of parallel processing.</span></span>

## <a name="planned-orders-take-a-long-time-to-update"></a><span data-ttu-id="a2c8b-140">Gli ordini pianificati richiedono molto tempo per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-140">Planned orders take a long time to update.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2c8b-141">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="a2c8b-141">Issue description</span></span>

<span data-ttu-id="a2c8b-142">Quando si aggiorna la quantità richiesta e/o la data di consegna di un ordine pianificato, in genere sono necessari almeno 30 secondi per ordine per salvare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-142">When updating the requirement quantity and/or delivery date on a planned order, it typically takes at least 30 seconds per order to save the update.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2c8b-143">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a2c8b-143">Issue resolution</span></span>

<span data-ttu-id="a2c8b-144">Si tratta di un problema noto con il motore di pianificazione generale integrato.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-144">This is a known issue with the built-in master planning engine.</span></span> <span data-ttu-id="a2c8b-145">È causato dall'auto esplosione sottostante attraverso la struttura della distinta base durante le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-145">It is caused by the underlying auto explosion through the BOM structure during edits.</span></span> <span data-ttu-id="a2c8b-146">Questo problema viene risolto in Ottimizzazione pianificazione, in cui un pianificatore può aggiornare e approvare gli ordini pertinenti e, se desiderato, attivare un'esecuzione della pianificazione per aggiornare gli ordini pianificati per la struttura della distinta base sottostante.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-146">This issue is addressed in Planning Optimization, where a planner can update and approve the relevant orders and, when desired, trigger a planning run to update planned orders for the underlying BOM structure.</span></span>

<span data-ttu-id="a2c8b-147">Un modo per migliorare le prestazioni con il motore di pianificazione generale integrato consiste nell'effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a2c8b-147">One way to improve performance with the built-in master planning engine is to do the following:</span></span>

1. <span data-ttu-id="a2c8b-148">Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-148">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="a2c8b-149">Selezionare un piano.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-149">Select a plan.</span></span>
1. <span data-ttu-id="a2c8b-150">Espandere la scheda dettaglio **Intervalli temporali in giorni**.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-150">Expand the **Time fence in days** FastTab.</span></span>
1. <span data-ttu-id="a2c8b-151">Impostare **Esplosione** su *Sì* e impostare il campo sotto questa impostazione su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a2c8b-151">Set **Explosion** to *Yes*, and set the field below this setting to 0 (zero).</span></span>

> [!NOTE]
> <span data-ttu-id="a2c8b-152">Ciò limiterà il periodo per le esplosioni eseguite per questo piano generale a un solo giorno.</span><span class="sxs-lookup"><span data-stu-id="a2c8b-152">This will limit the period for explosions performed for this master plan to a single day.</span></span>
