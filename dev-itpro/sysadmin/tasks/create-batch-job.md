--- 
title: Creare un processo batch
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-batch-job"></a><span data-ttu-id="e8c0c-103">Creare un processo batch</span><span class="sxs-lookup"><span data-stu-id="e8c0c-103">Create a batch job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e8c0c-104">Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="e8c0c-105">I processi batch vengono eseguiti con le credenziali di sicurezza dell'utente da cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="e8c0c-106">Per creare un processo batch, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="e8c0c-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="e8c0c-108">Creare il processo batch</span><span class="sxs-lookup"><span data-stu-id="e8c0c-108">Create the batch job</span></span>
1. <span data-ttu-id="e8c0c-109">Andare a Amministrazione sistema > Richieste di informazioni > Processi batch.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="e8c0c-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-110">Click New.</span></span>
3. <span data-ttu-id="e8c0c-111">Digitare un valore nel campo Descrizione processo.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="e8c0c-112">Nel campo Data/ora di inizio programmate immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="e8c0c-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="e8c0c-114">Creare una ricorrenza</span><span class="sxs-lookup"><span data-stu-id="e8c0c-114">Create a recurrence</span></span>
1. <span data-ttu-id="e8c0c-115">Nel riquadro azioni fare clic su Processo batch.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="e8c0c-116">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-116">Click Recurrence.</span></span>
    * <span data-ttu-id="e8c0c-117">Usare queste opzioni per immettere un intervallo e un criterio per la ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="e8c0c-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="e8c0c-119">Aggiungere avvisi</span><span class="sxs-lookup"><span data-stu-id="e8c0c-119">Add alerts</span></span>
1. <span data-ttu-id="e8c0c-120">Nel riquadro azioni fare clic su Processo batch.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="e8c0c-121">Fare clic su Avvisi.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-121">Click Alerts.</span></span>
    * <span data-ttu-id="e8c0c-122">Indicare se si desidera che i messaggi di avviso vengano inviati quando il processo batch termina, presenta una condizione di errore o viene annullato.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="e8c0c-123">Poi specificare se volete che gli allarmi vengano visualizzati come messaggi popup.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="e8c0c-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e8c0c-124">Click OK.</span></span>

