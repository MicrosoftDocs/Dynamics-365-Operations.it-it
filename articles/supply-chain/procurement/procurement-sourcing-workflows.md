---
title: Flussi di lavoro di approvvigionamento
description: In alcune organizzazioni le richieste di acquisto e gli ordini fornitore devono essere approvati da un utente diverso dalla persona che ha immesso la transazione. Per impostare un processo di approvazione, è possibile creare un flusso di lavoro.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93ceab555bf278ced13d8360956f6db65ba275f8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813456"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="31fb3-104">Flussi di lavoro di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="31fb3-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31fb3-105">In alcune organizzazioni le richieste di acquisto e gli ordini fornitore devono essere approvati da un utente diverso dalla persona che ha immesso la transazione.</span><span class="sxs-lookup"><span data-stu-id="31fb3-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="31fb3-106">Per impostare un processo di approvazione, è possibile creare un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="31fb3-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="31fb3-107">Un flusso di lavoro rappresenta un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="31fb3-107">A workflow represents a business process.</span></span> <span data-ttu-id="31fb3-108">Definisce il modo in cui un documento attraversa il sistema e stabilisce chi deve completare un'attività o approvare un documento.</span><span class="sxs-lookup"><span data-stu-id="31fb3-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="31fb3-109">Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="31fb3-109">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="31fb3-110">**Processi coerenti**: è possibile definire il processo di approvazione per documenti specifici, ad esempio richieste di acquisto e note spese.</span><span class="sxs-lookup"><span data-stu-id="31fb3-110">**Consistent processes**— You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="31fb3-111">L'utilizzo del sistema flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.</span><span class="sxs-lookup"><span data-stu-id="31fb3-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="31fb3-112">**Visibilità dei processi**: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di una specifica istanza di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="31fb3-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="31fb3-113">In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="31fb3-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="31fb3-114">**Elenco di lavoro centralizzato**: gli utenti possono visualizzare l'elenco di lavoro centralizzato per verificare le attività e i processi di approvazione del flusso di lavoro cui sono stati allocati in tutti i flussi di lavoro cui partecipano.</span><span class="sxs-lookup"><span data-stu-id="31fb3-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="31fb3-115">Questo elenco di lavoro è disponibile nella pagina Elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="31fb3-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="31fb3-116"> Tipi di flussi di lavoro che è possibile creare</span><span class="sxs-lookup"><span data-stu-id="31fb3-116">The types of workflows that you can create</span></span>
<span data-ttu-id="31fb3-117">Per Approvvigionamento sono disponibili i tipi di flusso di lavoro indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="31fb3-117">The following workflow types are available for Procurement and sourcing.</span></span>

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| <span data-ttu-id="31fb3-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="31fb3-118">**Type**</span></span>                         | <span data-ttu-id="31fb3-119">**Utilizzare questo tipo per:**</span><span class="sxs-lookup"><span data-stu-id="31fb3-119">**Use this type to**</span></span>                                          |
| <span data-ttu-id="31fb3-120">Verifica richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="31fb3-120">Purchase requisition review</span></span>      | <span data-ttu-id="31fb3-121">Creare flussi di lavoro di revisione e approvazione per richieste di acquisto.</span><span class="sxs-lookup"><span data-stu-id="31fb3-121">Create review and approval workflows for purchase requisitions.</span></span>            |
| <span data-ttu-id="31fb3-122">Verifica righe di richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="31fb3-122">Purchase requisition line review</span></span> | <span data-ttu-id="31fb3-123">Creare flussi di lavoro di revisione e approvazione per righe di richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="31fb3-123">Create review and approval workflows for purchase requisition lines.</span></span>       |
| <span data-ttu-id="31fb3-124">Flusso di lavoro ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="31fb3-124">Purchase order workflow</span></span>          | <span data-ttu-id="31fb3-125">Creare flussi di lavoro di revisione e approvazione per ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="31fb3-125">Create review and approval workflows for purchase orders.</span></span>     |
| <span data-ttu-id="31fb3-126">Flusso di lavoro riga ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="31fb3-126">Purchase order line workflow</span></span>     | <span data-ttu-id="31fb3-127">Creare flussi di lavoro di revisione e approvazione per righe ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="31fb3-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="31fb3-128">Flusso di lavoro richieste aggiunta fornitore</span><span class="sxs-lookup"><span data-stu-id="31fb3-128">Vendor add application workflow</span></span>  | <span data-ttu-id="31fb3-129">Creare flussi di lavoro di revisione e approvazione per l'aggiunta di nuovi fornitori tramite le richieste fornitore.</span><span class="sxs-lookup"><span data-stu-id="31fb3-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

## <a name="creating-a-workflow"></a><span data-ttu-id="31fb3-130">Creazione di un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="31fb3-130">Creating a workflow</span></span>

<span data-ttu-id="31fb3-131">Per creare un flusso di lavoro, accedere ad Approvvigionamento &gt; Impostazioni &gt; Flussi di lavoro di approvvigionamento e creare un nuovo flusso di lavoro selezionando il tipo di flusso di lavoro che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="31fb3-131">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span>  

<span data-ttu-id="31fb3-132">Nella canvas del flusso di lavoro è possibile trascinare elementi del flusso di lavoro nel designer e collegare gli elementi a un flusso.</span><span class="sxs-lookup"><span data-stu-id="31fb3-132">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="31fb3-133">Gli elementi del flusso di lavoro devono essere configurati.</span><span class="sxs-lookup"><span data-stu-id="31fb3-133">The workflow elements should be configured.</span></span> <span data-ttu-id="31fb3-134">Per gli elementi del flusso di lavoro e l'approvazione è possibile configurare il partecipante che deve eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="31fb3-134">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="31fb3-135">Tipi di partecipanti</span><span class="sxs-lookup"><span data-stu-id="31fb3-135">Types of participants</span></span>

<span data-ttu-id="31fb3-136">È possibile assegnare un passaggio di approvazione ai gruppi di partecipanti indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="31fb3-136">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="31fb3-137">Gruppo utenti</span><span class="sxs-lookup"><span data-stu-id="31fb3-137">User group</span></span>    | <span data-ttu-id="31fb3-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31fb3-138">Description</span></span>                                                               |
|---------------|---------------------------------------------------------------------------|
| <span data-ttu-id="31fb3-139">Partecipante</span><span class="sxs-lookup"><span data-stu-id="31fb3-139">Participant</span></span>   | <span data-ttu-id="31fb3-140">Assegnare il passaggio di approvazione ai membri di un gruppo o ruolo.</span><span class="sxs-lookup"><span data-stu-id="31fb3-140">Assign the approval step to members of a group or role.</span></span>                   |
| <span data-ttu-id="31fb3-141">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="31fb3-141">Hierarchy</span></span>     | <span data-ttu-id="31fb3-142">Assegnare il passaggio di approvazione agli utenti di una gerarchia organizzativa specifica.</span><span class="sxs-lookup"><span data-stu-id="31fb3-142">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="31fb3-143">Utente del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="31fb3-143">Workflow user</span></span> | <span data-ttu-id="31fb3-144">Assegnare il passaggio di approvazione agli utenti del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="31fb3-144">Assign the approval step to users of this workflow.</span></span>                       |
| <span data-ttu-id="31fb3-145">Coda</span><span class="sxs-lookup"><span data-stu-id="31fb3-145">Queue</span></span>         | <span data-ttu-id="31fb3-146">Assegnare il passaggio di approvazione a una coda di elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="31fb3-146">Assign the approval step to a work item queue.</span></span>                            |
| <span data-ttu-id="31fb3-147">Utente</span><span class="sxs-lookup"><span data-stu-id="31fb3-147">User</span></span>          | <span data-ttu-id="31fb3-148">Assegnare il passaggio relativo all'approvazione a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="31fb3-148">Assign the approval step to specific users.</span></span>                               |



## <a name="additional-resources"></a><span data-ttu-id="31fb3-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="31fb3-149">Additional resources</span></span>

- [<span data-ttu-id="31fb3-150">Definizione di flussi di lavoro di processi aziendali per le richieste di acquisto</span><span class="sxs-lookup"><span data-stu-id="31fb3-150">Defining business process workflows for purchase requisitions</span></span>](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

- [<span data-ttu-id="31fb3-151">Flusso di lavoro delle richieste di acquisto</span><span class="sxs-lookup"><span data-stu-id="31fb3-151">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)

- [<span data-ttu-id="31fb3-152">Inserimento di fornitori</span><span class="sxs-lookup"><span data-stu-id="31fb3-152">Onboard vendors</span></span>](vendor-onboarding.md)

