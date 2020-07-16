---
title: Delegare elementi di lavoro in un flusso di lavoro
description: Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti.
author: ChrisGarty
manager: AnnBe
ms.date: 06/23/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d98d84b89f1f3322a9c896b74b63a3b6425b13b
ms.sourcegitcommit: 267864eb0dccd6e26d49d280bd4ad1b770a73a77
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "3515766"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="b5b2b-103">Delegare elementi di lavoro in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b5b2b-103">Delegate work items in a workflow</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="b5b2b-104">Delegare manualmente un elemento di lavoro</span><span class="sxs-lookup"><span data-stu-id="b5b2b-104">Manually delegate a work item</span></span>

<span data-ttu-id="b5b2b-105">Per delegare un singolo elemento di lavoro, selezionare l'opzione **Delega** nel menu **Flusso di lavoro** e immettere il nome dell'utente da delegare con un commento.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="b5b2b-106">In questo modo si riassegnerà l'elemento di lavoro a tale utente di modo che possa completarlo.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="manually-delegate-multiple-work-items"></a><span data-ttu-id="b5b2b-107">Delega manuale di più elementi di lavoro</span><span class="sxs-lookup"><span data-stu-id="b5b2b-107">Manually delegate multiple work items</span></span>

<span data-ttu-id="b5b2b-108">Più elementi di lavoro possono essere delegati insieme dalla pagina **Elementi di lavoro assegnati a me**.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-108">Multiple work items can be delegated together from the **Work items assigned to me** page.</span></span> <span data-ttu-id="b5b2b-109">I seguenti tipi di flusso di lavoro sono idonei per la delega di massa: flusso di lavoro di approvazione del contratto di acquisto, flusso di lavoro dell'ordine di acquisto, revisione della richiesta di acquisto e flusso di lavoro della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-109">The following workflow types are eligible for mass delegation: Purchase agreement approval workflow, Purchase order workflow, Purchase requisition review, and Vendor invoice workflow.</span></span> <span data-ttu-id="b5b2b-110">La funzionalità **Delega più elementi di lavoro** è disabilitata per impostazione predefinita e può essere abilitata in **Aree di lavoro > Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-110">The **Delegate multiple work items** feature is disabled by default and can be enabled in **Workspaces > Feature management**.</span></span> <span data-ttu-id="b5b2b-111">Contatta l'amministratore di sistema per assistenza nell'abilitazione di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-111">Contact your system administrator for help with enabling this feature.</span></span>
1.  <span data-ttu-id="b5b2b-112">Vai a **Comune> Comune> Elementi di lavoro> Elementi di lavoro assegnati a me**.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-112">Go to **Common > Common > Work items > Work items assigned to me**.</span></span>
2.  <span data-ttu-id="b5b2b-113">Seleziona gli elementi di lavoro che verranno delegati.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-113">Select the work items that will be delegated.</span></span>
3.  <span data-ttu-id="b5b2b-114">Fai clic sul menu **Delegare elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-114">Click the **Delegate work items** menu.</span></span>
4.  <span data-ttu-id="b5b2b-115">Nel campo **Utente** seleziona l'utente a cui vuoi delegare gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-115">In the **User** field, select the user to delegate the work items to.</span></span>
5.  <span data-ttu-id="b5b2b-116">Nel campo **Commento** immettere un commento che spiega il motivo della delega degli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-116">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
6.  <span data-ttu-id="b5b2b-117">Fai clic sul pulsante **Delega elementi di lavoro** per completare la delega degli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-117">Click the **Delegate work items** button to complete the work item delegation.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="b5b2b-118">Delegare automaticamente elementi di lavoro</span><span class="sxs-lookup"><span data-stu-id="b5b2b-118">Automatically delegate work items</span></span>

<span data-ttu-id="b5b2b-119">Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire sugli elementi di lavoro per un periodo di tempo, è possibile delegare automaticamente i nuovi elementi di lavoro ad altri utenti utilizzando la pagina **Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-119">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="b5b2b-120">Impostare la delega automatica</span><span class="sxs-lookup"><span data-stu-id="b5b2b-120">Set up automatic delegation</span></span>
1. <span data-ttu-id="b5b2b-121">Passare a **Comune > Impostazioni > Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-121">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="b5b2b-122">Fare clic sulla scheda **Flusso di lavoro**. Assicurarsi che la sezione Delega sia espansa.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-122">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="b5b2b-123">Per configurare il sistema in modo da delegare automaticamente gli elementi di lavoro ad altri utenti, è necessario creare regole di delega, che specificano il momento in cui determinati tipi di elementi di lavoro vengono delegati.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-123">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="b5b2b-124">Per creare una regola di delega, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5b2b-124">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="b5b2b-125">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-125">Click **Add**.</span></span>
4. <span data-ttu-id="b5b2b-126">Nel campo **Ambito** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-126">In the **Scope** field, select an option.</span></span>
    - <span data-ttu-id="b5b2b-127">Tutto: consente di delegare tutti gli elementi di lavoro assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-127">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="b5b2b-128">Modulo: consente di delegare solo gli elementi di lavoro correlati a un tipo specifico di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-128">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="b5b2b-129">Se si seleziona questa opzione, è necessario selezionare il tipo di flusso di lavoro nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-129">If you select this option, you must select the type of workflow in the Name field.</span></span>
    - <span data-ttu-id="b5b2b-130">Flusso di lavoro: consente di delegare solo gli elementi di lavoro correlati a un flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-130">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="b5b2b-131">Se si seleziona questa opzione, è necessario selezionare il flusso di lavoro nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-131">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="b5b2b-132">Nel campo **Delega** selezionare l'utente a cui si desidera delegare gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-132">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="b5b2b-133">Specificare il momento in cui gli elementi di lavoro devono essere delegati automaticamente nei campi Data/ora di inizio e Data/ora di fine.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-133">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="b5b2b-134">Nel campo **Data/ora di inizio** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-134">In the **Start date/time** field, enter a date and time.</span></span>
7. <span data-ttu-id="b5b2b-135">Nel campo **Data/ora di fine** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-135">In the **End date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="b5b2b-136">Selezionare la casella di controllo **Attivato** per attivare la regola di delega.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-136">Select the **Enabled** check box to activate the delegation rule.</span></span> <span data-ttu-id="b5b2b-137">Se è stato selezionato **Modulo** come ambito, è necessario selezionare il modulo nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-137">If you selected **Module** as the Scope, then you must select the module in the Name field.</span></span> <span data-ttu-id="b5b2b-138">Se è stato selezionato **Flusso di lavoro** come ambito, è necessario selezionare lo specifico flusso di lavoro da delegare nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-138">If you selected **Workflow** as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="b5b2b-139">Nel campo **Commento** immettere un commento che spiega il motivo della delega degli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-139">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>

