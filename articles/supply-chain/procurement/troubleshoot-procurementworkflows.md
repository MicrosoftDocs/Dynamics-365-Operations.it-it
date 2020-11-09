---
title: Risolvere i problemi dei flussi di lavoro di approvvigionamento
description: Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con i flussi di lavoro di approvvigionamento.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cdedc45b8f057310801f134104156a732fb58d86
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018539"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a><span data-ttu-id="4a8a2-103">Risolvere i problemi dei flussi di lavoro di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="4a8a2-103">Troubleshoot procurement and sourcing workflows</span></span>

<span data-ttu-id="4a8a2-104">Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con i flussi di lavoro di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-104">This topic describes how to fix issues that you might encounter while you work with procurement and sourcing workflows.</span></span>

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a><span data-ttu-id="4a8a2-105">Errore durante il reinvio di un ordine fornitore al flusso di lavoro dopo una modifica: "Le modifiche all'ordine fornitore X sono consentite solo in stato Bozza quando è attivata la gestione delle modifiche"</span><span class="sxs-lookup"><span data-stu-id="4a8a2-105">Error when re-submitting a purchase order to the workflow after a change: "Changes to purchase order X are allowed only in a Draft state when change management is activated"</span></span>

<span data-ttu-id="4a8a2-106">Questo problema si verifica solo se l'ordine fornitore era in uno stato *Confermato* prima di richiedere le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-106">This issue occurs only if the purchase order was in a *Confirmed* state before you requested changes.</span></span> <span data-ttu-id="4a8a2-107">Se richiedi modifiche mentre l'ordine fornitore è in uno stato *Approvato* , il flusso di lavoro può essere elaborato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-107">If you request changes while the purchase order is in an *Approved* state, the workflow can be processed successfully.</span></span>

### <a name="error-description"></a><span data-ttu-id="4a8a2-108">Descrizione errore</span><span class="sxs-lookup"><span data-stu-id="4a8a2-108">Error description</span></span>

<span data-ttu-id="4a8a2-109">Il seguente errore si verifica nel flusso di lavoro quando un ordine fornitore viene nuovamente inviato dopo una modifica:</span><span class="sxs-lookup"><span data-stu-id="4a8a2-109">The following error occurs in the workflow when a purchase order is resubmitted after a change:</span></span>

> <span data-ttu-id="4a8a2-110">Interrotto (errore): Eccezione X++: le modifiche all'ordine fornitore PO0000569 sono consentite solo nello stato Bozza quando la gestione delle modifiche è attivata su</span><span class="sxs-lookup"><span data-stu-id="4a8a2-110">Stopped (error): X++ Exception: Changes to purchase order PO0000569 are only allowed in state Draft when change management is activated at</span></span><br>
<span data-ttu-id="4a8a2-111">SysWorkflowParticipantProvider-resolve</span><span class="sxs-lookup"><span data-stu-id="4a8a2-111">SysWorkflowParticipantProvider-resolve</span></span><br>
<span data-ttu-id="4a8a2-112">SysWorkflowParticipantProvider-resolveParticipants</span><span class="sxs-lookup"><span data-stu-id="4a8a2-112">SysWorkflowParticipantProvider-resolveParticipants</span></span><br>
<span data-ttu-id="4a8a2-113">SysWorkflowServiceProvider-resolveParticipant</span><span class="sxs-lookup"><span data-stu-id="4a8a2-113">SysWorkflowServiceProvider-resolveParticipant</span></span><br>
<span data-ttu-id="4a8a2-114">SysWorkflowQueue-resume</span><span class="sxs-lookup"><span data-stu-id="4a8a2-114">SysWorkflowQueue-resume</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4a8a2-115">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4a8a2-115">Issue resolution</span></span>

<span data-ttu-id="4a8a2-116">Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-116">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="4a8a2-117">Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza* , vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-117">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="4a8a2-118">Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="4a8a2-118">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

<span data-ttu-id="4a8a2-119">Il problema verrà risolto tramite [questo articolo della Knowledge Base (KB) di Microsoft](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span><span class="sxs-lookup"><span data-stu-id="4a8a2-119">The issue will be fixed through [this Microsoft Knowledge Base (KB) article](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="4a8a2-120">Una o più distribuzioni contabili è distribuita eccessivamente o sottodistribuita.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-120">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

<span data-ttu-id="4a8a2-121">Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-121">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="4a8a2-122">Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza* , vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-122">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="4a8a2-123">Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="4a8a2-123">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a><span data-ttu-id="4a8a2-124">Se una rimanenza di consegna viene annullata su un ordine fornitore in cui è attivata la gestione delle modifiche, l'ordine fornitore passa allo stato Confermato.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-124">If a delivery remainder is canceled on a purchase order where change management is turned on, the purchase order goes to a Confirmed state.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4a8a2-125">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="4a8a2-125">Issue description</span></span>

<span data-ttu-id="4a8a2-126">Per un ordine fornitore soggetto a gestione delle modifiche, se l'unica modifica richiesta è l'annullamento di una rimanenza di consegna su una o più righe, l'ordine fornitore passerà direttamente sullo stato *Confermato* quando è approvato e non verrà creato alcun giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-126">For a purchase order that is subject to change management, if the only change that is requested is the cancellation of a delivery remainder on one or more of the lines, the purchase order will go directly to a *Confirmed* state when it's approved, and no journal will be created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4a8a2-127">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4a8a2-127">Issue resolution</span></span>

<span data-ttu-id="4a8a2-128">L'annullamento di una rimanenza di consegna non influisce sul contenuto del giornale di registrazione delle conferme.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-128">Cancellation of a delivery remainder doesn't affect the contents of the confirmation journal.</span></span> <span data-ttu-id="4a8a2-129">Questa funzionalità deve essere utilizzata quando la riga è stata ricevuta parzialmente e la qualità rimanente deve essere annullata nel passaggio di processo dopo che l'ordine fornitore è stato confermato con il fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-129">This functionality should be used when the line has been partially received, and the remainder quality should be canceled in the process step after the purchase order has been confirmed with the vendor.</span></span>

<span data-ttu-id="4a8a2-130">Se ciò si riflette sulla conferma dell'ordine fornitore, la quantità deve essere rettificata nella riga dell'ordine fornitore in modo che venga richiesta la conferma.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-130">If this should be reflected on the purchase order confirmation, the quantity should be adjusted on the purchase order line so that the confirmation will be required.</span></span> <span data-ttu-id="4a8a2-131">In alternativa, se non è stato ricevuto nulla sulla riga, la quantità può essere rimossa.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-131">Alternatively, if nothing has been received on the line, the quantity can be removed.</span></span> <span data-ttu-id="4a8a2-132">In questo caso, sarà richiesta la riconferma.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-132">In this case, reconfirmation will be required.</span></span>

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a><span data-ttu-id="4a8a2-133">Gli ordini fornitore annullati vengono visualizzati nell'elenco delle bozze nell'area di lavoro Preparazione ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-133">Canceled purchase orders appear in the draft list in the Purchase order preparation workspace.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4a8a2-134">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="4a8a2-134">Issue description</span></span>

<span data-ttu-id="4a8a2-135">Dopo aver annullato gli ordini fornitore che erano nello stato *Confermato* , gli ordini fornitore annullati vengono ancora visualizzati nell'elenco delle bozze di ordini fornitore nell'area di lavoro **Preparazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-135">After you cancel purchase orders that were in a *Confirmed* state, the canceled purchase orders still appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4a8a2-136">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4a8a2-136">Issue resolution</span></span>

<span data-ttu-id="4a8a2-137">Questo problema si verifica solo per gli ordini fornitore soggetti a gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-137">This issue occurs only for purchase orders that are subject to change management.</span></span> <span data-ttu-id="4a8a2-138">Si verifica perché l'annullamento è considerato una modifica che deve essere approvata.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-138">It occurs because the cancellation is considered a change that must be approved.</span></span> <span data-ttu-id="4a8a2-139">L'approvazione può essere eseguita automaticamente dal sistema.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-139">The approval can be done automatically by the system.</span></span> <span data-ttu-id="4a8a2-140">Pertanto, il processo consiste nell'inviare l'ordine fornitore annullato al flusso di lavoro di approvazione in modo che possa passare allo stato *Approvato*.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-140">Therefore, the process is to submit the canceled purchase order to the approval workflow so that it can go to an *Approved* state.</span></span> <span data-ttu-id="4a8a2-141">A quel punto, l'ordine fornitore non verrà più visualizzato nell'elenco delle bozze di ordini fornitore nell'area di lavoro **Preparazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="4a8a2-141">At that point, the purchase order will no longer appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

