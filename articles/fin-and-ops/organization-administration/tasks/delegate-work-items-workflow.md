---
title: Delegare elementi di lavoro in un flusso di lavoro
description: Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44dc747543e32b54729d12c89a401b0187e25a61
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916417"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="e8f8c-103">Delegare elementi di lavoro in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e8f8c-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="e8f8c-104">Delegare manualmente un elemento di lavoro</span><span class="sxs-lookup"><span data-stu-id="e8f8c-104">Manually delegate a work item</span></span>

<span data-ttu-id="e8f8c-105">Per delegare un singolo elemento di lavoro, selezionare l'opzione **Delega** nel menu **Flusso di lavoro** e immettere il nome dell'utente da delegare con un commento.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="e8f8c-106">In questo modo si riassegnerà l'elemento di lavoro a tale utente di modo che possa completarlo.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="e8f8c-107">Delegare automaticamente elementi di lavoro</span><span class="sxs-lookup"><span data-stu-id="e8f8c-107">Automatically delegate work items</span></span>

<span data-ttu-id="e8f8c-108">Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire sugli elementi di lavoro per un periodo di tempo, è possibile delegare automaticamente i nuovi elementi di lavoro ad altri utenti utilizzando la pagina **Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="e8f8c-109">Impostare la delega automatica</span><span class="sxs-lookup"><span data-stu-id="e8f8c-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="e8f8c-110">Passare a **Comune > Impostazioni > Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-110">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="e8f8c-111">Fare clic sulla scheda **Flusso di lavoro**. Assicurarsi che la sezione Delega sia espansa.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-111">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="e8f8c-112">Per configurare il sistema in modo da delegare automaticamente gli elementi di lavoro ad altri utenti, è necessario creare regole di delega, che specificano il momento in cui determinati tipi di elementi di lavoro vengono delegati.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-112">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="e8f8c-113">Per creare una regola di delega, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8f8c-113">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="e8f8c-114">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-114">Click **Add**.</span></span>
4. <span data-ttu-id="e8f8c-115">Nel campo **Ambito** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-115">In the **Scope** field, select an option.</span></span>
    - <span data-ttu-id="e8f8c-116">Tutto: consente di delegare tutti gli elementi di lavoro assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-116">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="e8f8c-117">Modulo: consente di delegare solo gli elementi di lavoro correlati a un tipo specifico di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-117">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="e8f8c-118">Se si seleziona questa opzione, è necessario selezionare il tipo di flusso di lavoro nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-118">If you select this option, you must select the type of workflow in the Name field.</span></span>
    - <span data-ttu-id="e8f8c-119">Flusso di lavoro: consente di delegare solo gli elementi di lavoro correlati a un flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-119">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="e8f8c-120">Se si seleziona questa opzione, è necessario selezionare il flusso di lavoro nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-120">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="e8f8c-121">Nel campo **Delega** selezionare l'utente a cui si desidera delegare gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-121">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="e8f8c-122">Specificare il momento in cui gli elementi di lavoro devono essere delegati automaticamente nei campi Data/ora di inizio e Data/ora di fine.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-122">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="e8f8c-123">Nel campo **Data/ora di inizio** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-123">In the **Start date/time** field, enter a date and time.</span></span>
7. <span data-ttu-id="e8f8c-124">Nel campo **Data/ora di fine** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-124">In the **End date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="e8f8c-125">Selezionare la casella di controllo **Attivato** per attivare la regola di delega.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-125">Select the **Enabled** check box to activate the delegation rule.</span></span> <span data-ttu-id="e8f8c-126">Se è stato selezionato **Modulo** come ambito, è necessario selezionare il modulo nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-126">If you selected **Module** as the Scope, then you must select the module in the Name field.</span></span> <span data-ttu-id="e8f8c-127">Se è stato selezionato **Flusso di lavoro** come ambito, è necessario selezionare lo specifico flusso di lavoro da delegare nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-127">If you selected **Workflow** as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="e8f8c-128">Nel campo **Commento** immettere un commento che spiega il motivo della delega degli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-128">In the **Comment** field, enter a comment that explains why you are delegating the work items.</span></span>

