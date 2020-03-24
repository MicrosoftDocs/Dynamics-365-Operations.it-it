---
title: Annullare un processo di pianificazione generale
description: In questo argomento viene descritto come annullare un processo di pianificazione attivo che utilizza la funzionalità di pianificazione incorporata.
author: ChristianRytt
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: c04e2b2c0e5d7f28ea688578b3e1d7a1e1d9f6d3
ms.sourcegitcommit: 66eae22cd99e53fe8e4c6c94945ad8061b69a442
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2020
ms.locfileid: "3117450"
---
# <a name="cancel-a-master-planning-job"></a><span data-ttu-id="b2cf5-103">Annullare un processo di pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="b2cf5-103">Cancel a master planning job</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2cf5-104">In Microsoft Dynamics 365 Supply Chain Management, ci sono più opzioni per annullare un processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-104">In Microsoft Dynamics 365 Supply Chain Management, there are multiple options for canceling a master planning job.</span></span> <span data-ttu-id="b2cf5-105">Ad esempio, è possibile che si desideri annullare un processo di pianificazione generale se è stato avviato per errore o è in esecuzione più a lungo del previsto e si desidera terminarlo.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-105">For example, you may want to cancel a master planning job if it was started by mistake or is running longer than expected and you want to end it.</span></span> <span data-ttu-id="b2cf5-106">Il modo migliore per annullare un processo di pianificazione è dalla pagina **Processi di pianificazione non completati**.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-106">The best way to cancel a planning job is from  the **Unfinished planning processes** page.</span></span> <span data-ttu-id="b2cf5-107">Le opzioni alternative dalle pagine **Processi batch**e **Processi batch avanzati** devono essere utilizzate solo se l'annullamento del processo di pianificazione generale dalla pagina **Processi di pianificazione non completati** non viene completato in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-107">Alternative options from the **Batch jobs** and **Batch jobs enhanced** pages should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

## <a name="preferred-cancel-option"></a><span data-ttu-id="b2cf5-108">Opzione di annullamento preferita</span><span class="sxs-lookup"><span data-stu-id="b2cf5-108">Preferred cancel option</span></span>
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a><span data-ttu-id="b2cf5-109">Annullare il processo di pianificazione generale dalla pagina **Processi di pianificazione non completati**</span><span class="sxs-lookup"><span data-stu-id="b2cf5-109">Cancel master planning job from **Unfinished planning processes** page</span></span>
1. <span data-ttu-id="b2cf5-110">Andare a **Pianificazione generale > Richieste di informazioni e report > Panificazione generale > Processi di pianificazione non completati**.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-110">Go to **Master planning > Inquiries and reports > Master planning > Unfinished planning processes**.</span></span>
2. <span data-ttu-id="b2cf5-111">Selezionare la riga del processo di pianificazione che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-111">Select the line with the planning process that you want to cancel.</span></span>
3. <span data-ttu-id="b2cf5-112">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-112">Click **Cancel**.</span></span>

## <a name="additional-cancel-options"></a><span data-ttu-id="b2cf5-113">Ulteriori opzioni di annullamento</span><span class="sxs-lookup"><span data-stu-id="b2cf5-113">Additional cancel options</span></span>
<span data-ttu-id="b2cf5-114">Queste devono essere utilizzate solo se l'annullamento del processo di pianificazione generale dalla pagina **Processi di pianificazione non completati** non viene completato in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-114">These should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a><span data-ttu-id="b2cf5-115">Eliminare il processo di pianificazione generale dalla pagina **Processi batch**</span><span class="sxs-lookup"><span data-stu-id="b2cf5-115">Delete master planning job from the **Batch jobs** page</span></span>
1. <span data-ttu-id="b2cf5-116">Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-116">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="b2cf5-117">Selezionare la riga del processo di pianificazione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-117">Select the line with the planning job that you want to delete.</span></span>
3. <span data-ttu-id="b2cf5-118">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-118">Click **Delete**.</span></span>

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a><span data-ttu-id="b2cf5-119">Interrompere l'attività del processo di pianificazione generale dalla pagina **Processi batch avanzati**</span><span class="sxs-lookup"><span data-stu-id="b2cf5-119">Abort master planning job task from the **Batch jobs enhanced** page</span></span>
1. <span data-ttu-id="b2cf5-120">Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-120">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="b2cf5-121">Se l'ID processo non è visualizzato nell'elenco, fare clic su **Passa al modulo avanzato**, altrimenti procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-121">If the job ID is not shown in the list, click **Switch to enhanced form**, otherwise proceed with the next step.</span></span>
3. <span data-ttu-id="b2cf5-122">Aprire il processo batch</span><span class="sxs-lookup"><span data-stu-id="b2cf5-122">Open the batch job.</span></span> <span data-ttu-id="b2cf5-123">Fare clic su **ID processo** del processo batch con le attività che si desidera terminare.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-123">Click the **Job ID** for the batch job with tasks that you want to end.</span></span>
4. <span data-ttu-id="b2cf5-124">In **Attività batch**, selezionare le attività da terminare.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-124">In **Batch tasks**, select the tasks to end.</span></span>
5. <span data-ttu-id="b2cf5-125">Nella scheda dettaglio **Attività batch**, fare clic su **Interrompi**.</span><span class="sxs-lookup"><span data-stu-id="b2cf5-125">On the **Batch tasks** FastTab, click **Abort**.</span></span>
