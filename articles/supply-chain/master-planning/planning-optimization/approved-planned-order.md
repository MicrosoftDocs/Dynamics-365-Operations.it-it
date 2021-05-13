---
title: Visualizzare, gestire e approvare gli ordini pianificati
description: Questo argomento fornisce informazioni su come visualizzare, gestire e approvare gli ordini pianificati in Ottimizzazione pianificazione.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b9b5274481e693f9fa05eb084ec5505ce5bc2eb
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935659"
---
# <a name="view-manage-and-approve-planned-orders"></a><span data-ttu-id="0e123-103">Visualizzare, gestire e approvare gli ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-103">View, manage, and approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0e123-104">Questo argomento fornisce informazioni su come visualizzare, gestire e approvare gli ordini pianificati in Ottimizzazione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0e123-104">This topic provides information about how to view, manage, and approve planned orders in Planning Optimization.</span></span>

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a><span data-ttu-id="0e123-105">Visualizzare e gestire gli ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-105">View and manage planned orders</span></span>

<span data-ttu-id="0e123-106">È possibile visualizzare e gestire gli ordini pianificati in qualsiasi pagina elenco di ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="0e123-106">You can view and manage planned orders on any planned orders list page.</span></span> <span data-ttu-id="0e123-107">Vai in una delle seguenti posizioni, a seconda del tipo di ordini pianificati con cui desideri lavorare:</span><span class="sxs-lookup"><span data-stu-id="0e123-107">Go to one of the following places, depending on the type of planned orders that you want to work with:</span></span>

- <span data-ttu-id="0e123-108">Pianificazione generale \> Aree di lavoro \> Pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="0e123-108">Master planning \> Workspaces \> Master planning</span></span>
- <span data-ttu-id="0e123-109">Pianificazione generale \> Pianificazione generale \> Ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-109">Master planning \> Master planning \> Planned orders</span></span>
- <span data-ttu-id="0e123-110">Controllo produzione \> Ordini di produzione \> Tutti gli ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-110">Production control \> Production orders \> Planned production orders</span></span>
- <span data-ttu-id="0e123-111">Approvvigionamento \> Ordini fornitore \> Tutti gli ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="0e123-111">Procurement and sourcing \> Purchase orders \> Planned purchase orders</span></span>
- <span data-ttu-id="0e123-112">Gestione articoli \> Ordini in entrata \> Trasferimenti pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-112">Inventory management \> Inbound orders \> Planned transfers</span></span>
- <span data-ttu-id="0e123-113">Gestione articoli \> Ordini in uscita \> Trasferimenti pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-113">Inventory management \> Outbound orders \> Planned transfers</span></span>

## <a name="view-and-edit-the-status-of-planned-orders"></a><span data-ttu-id="0e123-114">Visualizzare e modificare lo stato degli ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-114">View and edit the status of planned orders</span></span>

<span data-ttu-id="0e123-115">Puoi usare il campo **Stato** di ogni ordine pianificato per monitorare i tuoi progressi o modificare il modo in cui verrà elaborato un ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="0e123-115">You can use the **Status** field of each planned order to help track your progress or change how a planned order will be processed.</span></span> <span data-ttu-id="0e123-116">Sono disponibili i seguenti valori di **Stato**:</span><span class="sxs-lookup"><span data-stu-id="0e123-116">The following **Status** values are available:</span></span>

- <span data-ttu-id="0e123-117">**Inevaso** - Agli ordini pianificati generati mediante la pianificazione generale viene assegnato questo stato.</span><span class="sxs-lookup"><span data-stu-id="0e123-117">**Unprocessed** – When master planning generates planned orders, they are given this status.</span></span> <span data-ttu-id="0e123-118">Gli ordini pianificati con questo stato verranno eliminati durante la successiva esecuzione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0e123-118">Planned orders that have this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="0e123-119">**Completato** - Questo stato indica che l'ordine pianificato è stato completato.</span><span class="sxs-lookup"><span data-stu-id="0e123-119">**Completed** – This status indicates that the planned order has been completed.</span></span> <span data-ttu-id="0e123-120">A un ordine pianificato che si sceglie di non stabilizzare è possibile cambiare manualmente lo stato in *Completato*.</span><span class="sxs-lookup"><span data-stu-id="0e123-120">If you decide not to firm a planned order, you can manually change its status to *Completed*.</span></span> <span data-ttu-id="0e123-121">Notare che gli stati *Inevaso* e *Completato* sono trattati allo stesso modo dal sistema.</span><span class="sxs-lookup"><span data-stu-id="0e123-121">Note that the system treats the *Unprocessed* and *Completed* statuses in the same way.</span></span>
- <span data-ttu-id="0e123-122">**Approvato** - Questo stato indica che l'ordine pianificato è approvato per la stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="0e123-122">**Approved** – This status indicates that the planned order is approved for firming.</span></span> <span data-ttu-id="0e123-123">Se si desidera stabilizzare un ordine pianificato, è possibile modificarne lo stato in *Approvato*.</span><span class="sxs-lookup"><span data-stu-id="0e123-123">If you want to firm a planned order, you can change its status to *Approved*.</span></span> <span data-ttu-id="0e123-124">Se si desidera mantenere le modifiche apportate a un ordine pianificato o se si prevede di stabilizzare un ordine pianificato, modificarne lo stato in *Approvato*.</span><span class="sxs-lookup"><span data-stu-id="0e123-124">If you want to keep the edits that have been made to a planned order, or if you're planning to firm a planned order, change its status to *Approved*.</span></span> <span data-ttu-id="0e123-125">Ordini pianificati con stato *Approvato* sono considerati come fornitura fissa e prevista dalla pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="0e123-125">Planned orders that have a status of *Approved* are considered fixed and expected supply by master planning.</span></span> <span data-ttu-id="0e123-126">Pertanto, non vengono modificati o eliminati durante le successive esecuzioni della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="0e123-126">Therefore, they aren't modified or deleted during later master planning runs.</span></span> <span data-ttu-id="0e123-127">Per ottenere questo comportamento, la logica di pianificazione copia gli ordini pianificati con stato *Approvato* dalla vecchia versione del piano alla nuova versione del piano durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="0e123-127">To achieve this behavior, the planning logic copies planned orders that have a status of *Approved* from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="0e123-128">Notare che gli ordini pianificati con stato *Approvato*\* sono considerati fornitura solo all'interno del piano generale specifico.</span><span class="sxs-lookup"><span data-stu-id="0e123-128">Note that planned orders that have a status of *Approved*\* are considered supply only within the specific master plan.</span></span>

<span data-ttu-id="0e123-129">Per modificare lo stato di un singolo ordine pianificato, [aprire qualsiasi pagina elenco degli ordini pianificati](#view-planned-orders), aprire l'ordine e quindi seguire uno di questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="0e123-129">To change the status of a single planned order, [open any planned orders list page](#view-planned-orders), open the order, and then follow one of these steps:</span></span>

- <span data-ttu-id="0e123-130">Nella Scheda dettaglio **Generale**, modificare il valore del campo **Stato**.</span><span class="sxs-lookup"><span data-stu-id="0e123-130">On the **General** FastTab, change the value of the **Status** field.</span></span>
- <span data-ttu-id="0e123-131">Nel riquadro Azioni, nella scheda **Ordine pianificato**, nel gruppo **Processo** selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="0e123-131">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="0e123-132">Per contrassegnare l'ordine come approvato, nel riquadro Azioni, selezionare **Approva**.</span><span class="sxs-lookup"><span data-stu-id="0e123-132">On the Action Pane, select **Approve** to mark the order as approved.</span></span>

<span data-ttu-id="0e123-133">Per modificare lo stato di più ordini pianificati contemporaneamente, [aprire qualsiasi pagina elenco degli ordini pianificati](#view-planned-orders), selezionare la casella di controllo per ogni ordine che desideri modificare, quindi seguire uno di questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="0e123-133">To change the status of several planned orders at the same time, [open any planned orders list page](#view-planned-orders), select the check box for each order that you want to change, and then follow one of these steps:</span></span>

- <span data-ttu-id="0e123-134">Nel riquadro Azioni, nella scheda **Ordine pianificato**, nel gruppo **Processo** selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="0e123-134">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="0e123-135">Per contrassegnare gli ordini come approvati, nel riquadro Azioni, selezionare **Approva**.</span><span class="sxs-lookup"><span data-stu-id="0e123-135">On the Action Pane, select **Approve** to mark the orders as approved.</span></span>

## <a name="approve-planned-orders"></a><span data-ttu-id="0e123-136">Approva ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-136">Approve planned orders</span></span>

<span data-ttu-id="0e123-137">L'approvazione degli ordini pianificati è un passaggio facoltativo nel processo per creare un ordine stabilizzato da un ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="0e123-137">Approval of planned orders is an optional step in the process of creating a firmed order from a planned order.</span></span>

<span data-ttu-id="0e123-138">La figura seguente mostra come utilizzare il valore **Stato** assegnato a ciascun ordine pianificato per implementare un flusso di lavoro di approvazione.</span><span class="sxs-lookup"><span data-stu-id="0e123-138">The following illustration shows how you can use the **Status** value that is assigned to each planned order to implement an approval workflow.</span></span> <span data-ttu-id="0e123-139">Per implementare un processo di approvazione, modificare manualmente il valore **Stato** per ogni ordine pianificato come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="0e123-139">To implement an approval process, manually adjust the **Status** value for each planned order as described in the previous section.</span></span>

![Flusso dell'ordine pianificato](media/approved-planned-orders-1.png)

> [!TIP]
> <span data-ttu-id="0e123-141">Si consiglia di approvare gli ordini pianificati modificati.</span><span class="sxs-lookup"><span data-stu-id="0e123-141">We recommend that you approve any modified planned orders.</span></span> <span data-ttu-id="0e123-142">In caso contrario, le modifiche verranno ignorate e sovrascritte dalla successiva esecuzione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0e123-142">Otherwise, the edits will be ignored and overwritten by the next planning run.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e123-143">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0e123-143">Additional resources</span></span>

- [<span data-ttu-id="0e123-144">Stabilizza ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="0e123-144">Firm planned orders</span></span>](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
