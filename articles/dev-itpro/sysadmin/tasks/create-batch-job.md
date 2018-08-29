--- 
title: Crea processi batch
description: "Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b32c16a0c0045e22128746f81c6e9fd03370ac1f
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="create-batch-jobs"></a><span data-ttu-id="cd2e2-103">Crea processi batch</span><span class="sxs-lookup"><span data-stu-id="cd2e2-103">Create batch jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd2e2-104">Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="cd2e2-105">I processi batch vengono eseguiti con le credenziali di sicurezza dell'utente da cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="cd2e2-106">Per creare un processo batch, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="cd2e2-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="cd2e2-108">Creare il processo batch</span><span class="sxs-lookup"><span data-stu-id="cd2e2-108">Create the batch job</span></span>
1. <span data-ttu-id="cd2e2-109">Andare a Amministrazione sistema > Richieste di informazioni > Processi batch.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="cd2e2-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-110">Click New.</span></span>
3. <span data-ttu-id="cd2e2-111">Digitare un valore nel campo Descrizione processo.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="cd2e2-112">Nel campo Data/ora di inizio programmate immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="cd2e2-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="cd2e2-114">Creare una ricorrenza</span><span class="sxs-lookup"><span data-stu-id="cd2e2-114">Create a recurrence</span></span>
1. <span data-ttu-id="cd2e2-115">Nel riquadro azioni fare clic su Processo batch.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="cd2e2-116">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-116">Click Recurrence.</span></span>
    * <span data-ttu-id="cd2e2-117">Usare queste opzioni per immettere un intervallo e un criterio per la ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="cd2e2-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="cd2e2-119">Aggiungere avvisi</span><span class="sxs-lookup"><span data-stu-id="cd2e2-119">Add alerts</span></span>
1. <span data-ttu-id="cd2e2-120">Nel riquadro azioni fare clic su Processo batch.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="cd2e2-121">Fare clic su Avvisi.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-121">Click Alerts.</span></span>
    * <span data-ttu-id="cd2e2-122">Indicare se si desidera che i messaggi di avviso vengano inviati quando il processo batch termina, presenta una condizione di errore o viene annullato.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="cd2e2-123">Poi specificare se volete che gli allarmi vengano visualizzati come messaggi popup.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="cd2e2-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cd2e2-124">Click OK.</span></span>


