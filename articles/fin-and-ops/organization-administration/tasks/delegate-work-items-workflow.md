---
title: Delegare elementi di lavoro in un flusso di lavoro
description: Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: f85a1318822ceaf829134bf2eb3581e350d5bea4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "346251"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="3f017-103">Delegare elementi di lavoro in un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3f017-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3f017-104">Se si prevede di restare assenti dall'ufficio o di non essere disponibili per intervenire su alcuni elementi di lavoro, è possibile delegare o riassegnare i propri elementi di lavoro ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3f017-104">If you plan to be out of the office or otherwise unavailable to act on work items, you can delegate, or reassign, your work items to other users.</span></span> <span data-ttu-id="3f017-105">La procedura consente di configurare il sistema in modo da delegare automaticamente gli elementi di lavoro a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="3f017-105">This procedure helps you configure the system to automatically delegate your work items to another user.</span></span>



<span data-ttu-id="3f017-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="3f017-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-automatic-delegation"></a><span data-ttu-id="3f017-107">Impostare la delega automatica</span><span class="sxs-lookup"><span data-stu-id="3f017-107">Set up automatic delegation</span></span>
1. <span data-ttu-id="3f017-108">Passare a Comune > Impostazioni > Opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="3f017-108">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="3f017-109">Fare clic sulla scheda Flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3f017-109">Click the Workflow tab.</span></span>
    * <span data-ttu-id="3f017-110">Assicurarsi che la sezione Delega sia espansa.</span><span class="sxs-lookup"><span data-stu-id="3f017-110">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="3f017-111">Per configurare il sistema in modo da delegare automaticamente gli elementi di lavoro ad altri utenti, è necessario creare regole di delega, che specificano il momento in cui determinati tipi di elementi di lavoro vengono delegati.</span><span class="sxs-lookup"><span data-stu-id="3f017-111">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="3f017-112">Per creare una regola di delega, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f017-112">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="3f017-113">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="3f017-113">Click Add.</span></span>
4. <span data-ttu-id="3f017-114">Nel campo Ambito selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="3f017-114">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="3f017-115">Tutto: consente di delegare tutti gli elementi di lavoro assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="3f017-115">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="3f017-116">Modulo: consente di delegare solo gli elementi di lavoro correlati a un tipo specifico di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3f017-116">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="3f017-117">Se si seleziona questa opzione, è necessario selezionare il tipo di flusso di lavoro nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3f017-117">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="3f017-118">Flusso di lavoro: consente di delegare solo gli elementi di lavoro correlati a un flusso di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="3f017-118">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="3f017-119">Se si seleziona questa opzione, è necessario selezionare il flusso di lavoro nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3f017-119">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="3f017-120">Nel campo Delega selezionare l'utente a cui si desidera delegare gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3f017-120">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="3f017-121">Specificare il momento in cui gli elementi di lavoro devono essere delegati automaticamente nei campi Data/ora di inizio e Data/ora di fine.</span><span class="sxs-lookup"><span data-stu-id="3f017-121">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="3f017-122">Nel campo Data/ora di inizio immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="3f017-122">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="3f017-123">Nel campo Data/ora di fine immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="3f017-123">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="3f017-124">Selezionare la casella di controllo Attivato per attivare la regola di delega.</span><span class="sxs-lookup"><span data-stu-id="3f017-124">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="3f017-125">Se è stato selezionato Modulo come ambito, è necessario selezionare il modulo nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3f017-125">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="3f017-126">Se è stato selezionato Flusso di lavoro come ambito, è necessario selezionare lo specifico flusso di lavoro da delegare nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3f017-126">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="3f017-127">Nel campo Commento immettere un commento che spiega il motivo della delega degli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3f017-127">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

