---
title: Creare un processo batch
description: Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4360cd7068658a170f5b44c2ce7c71c39c44fa8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679890"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="32f61-103">Creare un processo batch</span><span class="sxs-lookup"><span data-stu-id="32f61-103">Create a batch job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="32f61-104">Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="32f61-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="32f61-105">I processi batch vengono eseguiti con le credenziali di sicurezza dell'utente da cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="32f61-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="32f61-106">Per creare un processo batch, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="32f61-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="32f61-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="32f61-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="32f61-108">Creare il processo batch</span><span class="sxs-lookup"><span data-stu-id="32f61-108">Create the batch job</span></span>
1. <span data-ttu-id="32f61-109">Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Richieste di informazioni > Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="32f61-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="32f61-110">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="32f61-110">Click **New**.</span></span>
3. <span data-ttu-id="32f61-111">Digitare un valore nel campo **Descrizione processo**.</span><span class="sxs-lookup"><span data-stu-id="32f61-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="32f61-112">Nel campo **Data/ora di inizio programmate** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="32f61-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="32f61-113">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="32f61-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="32f61-114">Creare una ricorrenza</span><span class="sxs-lookup"><span data-stu-id="32f61-114">Create a recurrence</span></span>
1. <span data-ttu-id="32f61-115">Nel riquadro azioni fare clic su **Processo batch**.</span><span class="sxs-lookup"><span data-stu-id="32f61-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="32f61-116">Fare clic su **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="32f61-116">Click **Recurrence**.</span></span> <span data-ttu-id="32f61-117">Usare queste opzioni per immettere un intervallo e un criterio per la ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="32f61-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="32f61-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="32f61-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="32f61-119">Aggiungere avvisi</span><span class="sxs-lookup"><span data-stu-id="32f61-119">Add alerts</span></span>
1. <span data-ttu-id="32f61-120">Nel riquadro azioni fare clic su **Processo batch**.</span><span class="sxs-lookup"><span data-stu-id="32f61-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="32f61-121">Fare clic su **Avvisi**.</span><span class="sxs-lookup"><span data-stu-id="32f61-121">Click **Alerts**.</span></span> <span data-ttu-id="32f61-122">Indicare se si desidera che i messaggi di avviso vengano inviati quando il processo batch termina, presenta una condizione di errore o viene annullato.</span><span class="sxs-lookup"><span data-stu-id="32f61-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="32f61-123">Poi specificare se volete che gli allarmi vengano visualizzati come messaggi popup.</span><span class="sxs-lookup"><span data-stu-id="32f61-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="32f61-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="32f61-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="32f61-125">Modificare lo stato del processo batch</span><span class="sxs-lookup"><span data-stu-id="32f61-125">Adjust batch job status</span></span>
1. <span data-ttu-id="32f61-126">Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.</span><span class="sxs-lookup"><span data-stu-id="32f61-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="32f61-127">Selezionare il processo batch appropriato.</span><span class="sxs-lookup"><span data-stu-id="32f61-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="32f61-128">Nel riquadro azioni fare clic su **Processo batch > Funzioni > Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="32f61-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="32f61-129">Selezionare lo stato appropriato:</span><span class="sxs-lookup"><span data-stu-id="32f61-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="32f61-130">**Trattenuto**: impostare il processo batch su **trattenuto** di modo che sia trattenuto dallo scheduler dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="32f61-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="32f61-131">È equivalente a *fermo*.</span><span class="sxs-lookup"><span data-stu-id="32f61-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="32f61-132">**In attesa**: impostare il processo batch su **in attesa** di modo che sia in attesa di essere selezionato dallo scheduler di processi batch.</span><span class="sxs-lookup"><span data-stu-id="32f61-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="32f61-133">E equivalente a *avvia*.</span><span class="sxs-lookup"><span data-stu-id="32f61-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="32f61-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="32f61-134">Click **OK**.</span></span>
