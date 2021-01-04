---
title: Eventi dell'app di magazzino
description: In questo argomento viene descritta l'elaborazione degli eventi dell'app di magazzino utilizzata per elaborare messaggi di evento dell'app di magazzino come parte di un processo batch.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 210008c4a1366773f465c59b38eca30f11f0b38c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431009"
---
# <a name="warehouse-app-event-processing"></a><span data-ttu-id="a8574-103">Elaborazione degli eventi dell'app di magazzino</span><span class="sxs-lookup"><span data-stu-id="a8574-103">Warehouse app event processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8574-104">I processi batch in esecuzione in Supply Chain Management possono utilizzare i dati di una coda per elaborare eventi emessi dall'app di magazzino per reagire come necessario agli eventi segnalati.</span><span class="sxs-lookup"><span data-stu-id="a8574-104">Batch jobs running in Supply Chain Management can use data from a queue for processing events issued by the warehouse app to react as needed to the signaled events.</span></span> <span data-ttu-id="a8574-105">Questa funzionalità aggiunge eventi pertinenti alla coda in risposta a determinati tipi di azioni intraprese dai lavoratori che utilizzano l'app.</span><span class="sxs-lookup"><span data-stu-id="a8574-105">This feature add relevant events to the queue in response to certain types of actions taken by workers using the app.</span></span> <span data-ttu-id="a8574-106">Un esempio è quando si utilizza la funzionalità **Crea ed elabora ordini di trasferimento nell'app di magazzino**, l'intestazione e le righe dell'ordine di trasferimento vengono create e aggiornate nel back-end quando il sistema esegue il processo batch **Elabora eventi dell'app di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a8574-106">An example is when using the **Create and process transfer orders from the warehouse app** feature, the transfer order header and lines get created and updated in the back end when the system is running the **Process warehouse app events** batch job.</span></span>

## <a name="enable-the-process-warehouse-app-events-feature"></a><span data-ttu-id="a8574-107">Abilitare la funzionalità Elabora eventi dell'app di magazzino</span><span class="sxs-lookup"><span data-stu-id="a8574-107">Enable the Process warehouse app events feature</span></span>

<span data-ttu-id="a8574-108">Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="a8574-108">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="a8574-109">Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="a8574-109">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="a8574-110">La funzionalità Elabora eventi dell'app di magazzino viene elencata come:</span><span class="sxs-lookup"><span data-stu-id="a8574-110">The Process warehouse app events feature is listed as:</span></span>

- <span data-ttu-id="a8574-111">**Modulo**: Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="a8574-111">**Module** - Warehouse management</span></span>
- <span data-ttu-id="a8574-112">**Nome funzionalità**: Elabora eventi dell'app di magazzino</span><span class="sxs-lookup"><span data-stu-id="a8574-112">**Feature name** - Process warehouse app events</span></span>

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a><span data-ttu-id="a8574-113">Configurare un processo batch per elaborare eventi dell'app di magazzino</span><span class="sxs-lookup"><span data-stu-id="a8574-113">Set up a batch job to process warehouse app events</span></span>

### <a name="process-warehouse-app-events"></a><span data-ttu-id="a8574-114">Elaborare eventi dell'app di magazzino</span><span class="sxs-lookup"><span data-stu-id="a8574-114">Process warehouse app events</span></span>

<span data-ttu-id="a8574-115">Configura un processo batch pianificato per elaborare gli eventi dell'app di magazzino per la creazione dell'ordine di trasferimento e gli aggiornamenti delle righe.</span><span class="sxs-lookup"><span data-stu-id="a8574-115">Set up a scheduled batch job to process the warehouse app events for the transfer order creation and line updates.</span></span>

1. <span data-ttu-id="a8574-116">Vai a **Gestione magazzino \> Attività periodiche \> Elabora eventi dell'app di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a8574-116">Go to **Warehouse management \> Periodic tasks \> Process warehouse app events**.</span></span>
1. <span data-ttu-id="a8574-117">Viene visualizzata la finestra di dialogo Elabora eventi dell'app di magazzino.</span><span class="sxs-lookup"><span data-stu-id="a8574-117">The Process warehouse app events dialog box opens.</span></span> <span data-ttu-id="a8574-118">Espandi la Scheda dettaglio **Esegui in background** e imposta **Elaborazione batch** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a8574-118">Expand the **Run in background** FastTab and set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="a8574-119">Nella Scheda dettaglio **Esegui in background** selezionare **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="a8574-119">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="a8574-120">Si apre la finestra di dialogo **Definisci ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="a8574-120">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="a8574-121">Imposta il programma di esecuzione secondo necessità per la tua azienda.</span><span class="sxs-lookup"><span data-stu-id="a8574-121">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="a8574-122">Seleziona **OK** per tornare alla finestra di dialogo **Elabora eventi dell'app di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a8574-122">Select **OK** to return to the **Process warehouse app events** dialog box.</span></span>
1. <span data-ttu-id="a8574-123">Seleziona **OK** nella finestra di dialogo **Elabora eventi dell'app di magazzino** per aggiungere il processo batch alla coda batch.</span><span class="sxs-lookup"><span data-stu-id="a8574-123">Select **OK** in the **Process warehouse app events** dialog box to add the batch job to the batch queue.</span></span>

## <a name="query-warehouse-app-events"></a><span data-ttu-id="a8574-124">Eseguire query sugli eventi dell'app di magazzino</span><span class="sxs-lookup"><span data-stu-id="a8574-124">Query warehouse app events</span></span>

<span data-ttu-id="a8574-125">Puoi visualizzare la coda degli eventi e i messaggi di eventi generati dall'app di magazzino selezionando **Gestione magazzino \> Richieste di informazioni e report \> Log dispositivo mobile \> Eventi dell'app di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a8574-125">You can view the event queue and events messages generated by the warehouse app by going to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>

## <a name="the-standard-event-queue-process"></a><span data-ttu-id="a8574-126">Elaborazione della coda di eventi standard</span><span class="sxs-lookup"><span data-stu-id="a8574-126">The standard event queue process</span></span>

<span data-ttu-id="a8574-127">La coda degli eventi delle app di magazzino verrà in genere utilizzata con il flusso descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="a8574-127">The warehouse apps events queue will typically be used with the following described flow:</span></span>

1. <span data-ttu-id="a8574-128">Un evento viene aggiunto alla coda con un messaggio di evento.</span><span class="sxs-lookup"><span data-stu-id="a8574-128">An event gets added to the queue  with an event message.</span></span> <span data-ttu-id="a8574-129">Il nuovo messaggio ha inizialmente lo stato di evento **In attesa**, il che significa che il processo batch **Elabora eventi dell'app di magazzino** non preleverà ed elaborerà questo messaggio.</span><span class="sxs-lookup"><span data-stu-id="a8574-129">The new message initially has an Event state of **Waiting**, which means that the **Process warehouse app events** batch job will not pick up and process this message.</span></span>
1. <span data-ttu-id="a8574-130">Non appena lo stato del messaggio viene aggiornato a **In coda**, il processo batch degli eventi **Elabora l'app di magazzino** verrà prelevato ed elaborerà l'evento.</span><span class="sxs-lookup"><span data-stu-id="a8574-130">As soon as the message state is updated to **Queued**, the **Process warehouse app** events batch job will pick up and process the event.</span></span>
1. <span data-ttu-id="a8574-131">Il processo batch aggiorna lo stato dell'evento a **Completato** o **Non riuscito**, a seconda dell'esito dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="a8574-131">The batch job updates the event states to either **Completed** or **Failed**, depending on whether the requested process was possible.</span></span>
1. <span data-ttu-id="a8574-132">Quando lo stato di tutti i messaggi di evento correlati è **Completato**, l'evento viene eliminato dalla coda.</span><span class="sxs-lookup"><span data-stu-id="a8574-132">When all the related event messages are **Completed**, the event is deleted from the queue.</span></span>

 <span data-ttu-id="a8574-133">Per un esempio dettagliato, vedi [Creare un ordine di trasferimento dall'elaborazione dell'app di magazzino](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="a8574-133">For a detailed example, see [Create transfer order from warehouse app process](create-transfer-order-from-warehouse-app.md).</span></span>

## <a name="handle-event-errors"></a><span data-ttu-id="a8574-134">Gestire gli errori degli eventi</span><span class="sxs-lookup"><span data-stu-id="a8574-134">Handle event errors</span></span>

<span data-ttu-id="a8574-135">Come parte dell'elaborazione degli eventi di magazzino, l'attività di messaggio richiesta potrebbe non ricevere processi dal processo batch.</span><span class="sxs-lookup"><span data-stu-id="a8574-135">As part of the warehouse event processing, the requested message activity may not receive processes from the batch job.</span></span> <span data-ttu-id="a8574-136">In questo caso, lo stato del messaggio di evento diventerà **Non riuscito**.</span><span class="sxs-lookup"><span data-stu-id="a8574-136">In this case, the event message will change to **Failed**.</span></span> <span data-ttu-id="a8574-137">Puoi usare le informazioni in **Log batch** per sapere perché e intraprendere l'azione necessaria per correggere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="a8574-137">You can use the **Batch log** information to learn why and take needed action to correct any problems.</span></span>

<span data-ttu-id="a8574-138">Per un esempio dettagliato, vedi [Creare un ordine di trasferimento dall'app di magazzino](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="a8574-138">For a detailed example, see [Create transfer order from warehouse app](create-transfer-order-from-warehouse-app.md).</span></span>

<span data-ttu-id="a8574-139">Per ripristinare un messaggio di evento di un'app di magazzino non riuscita:</span><span class="sxs-lookup"><span data-stu-id="a8574-139">To reset a failed warehouse app event message:</span></span>

1. <span data-ttu-id="a8574-140">Vai a **Gestione magazzino \> Richieste di informazioni e report \> Log dispositivo mobile \> Eventi dell'app di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a8574-140">Go to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>
1. <span data-ttu-id="a8574-141">Nella Scheda dettaglio **Messaggi di evento dell'app di magazzino**, trova e seleziona un evento pertinente nella cui colonna **Stato evento** è visualizzato **Non riuscito**.</span><span class="sxs-lookup"><span data-stu-id="a8574-141">On the **Warehouse app event messages** FastTab, find and select a relevant event that is showing **Failed** in the **Event state** column.</span></span>
1. <span data-ttu-id="a8574-142">Seleziona **Ripristina** nella barra degli strumenti **Messaggi di evento dell'app di magazzino** .</span><span class="sxs-lookup"><span data-stu-id="a8574-142">Select **Reset** from the **Warehouse app event messages** toolbar.</span></span>
1. <span data-ttu-id="a8574-143">Continua a lavorare fino a quando tutti i messaggi pertinenti non vengono ripristinati.</span><span class="sxs-lookup"><span data-stu-id="a8574-143">Continue working until all relevant messages are reset.</span></span>

<span data-ttu-id="a8574-144">Puoi anche rimuovere un messaggio di evento **Non riuscito** utilizzando l'opzione **Elimina** nella barra degli strumenti **Messaggi di evento dell'app di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a8574-144">You can also remove a **Failed** event message by using the **Delete** option on the **Warehouse app event messages** toolbar.</span></span>
