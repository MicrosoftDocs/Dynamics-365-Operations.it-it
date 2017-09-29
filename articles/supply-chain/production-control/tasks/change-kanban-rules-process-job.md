--- 
title: Modificare regole kanban di un processo di lavorazione
description: La procedura consente di modificare la regola kanban utilizzata per un kanban specifico.
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7f8b2a67e03a64deae9d4bc9c7e3e714d134443c
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="c937a-103">Modificare regole kanban di un processo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="c937a-103">Change kanban rules for a process job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c937a-104">La procedura consente di modificare la regola kanban utilizzata per un kanban specifico.</span><span class="sxs-lookup"><span data-stu-id="c937a-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="c937a-105">Ciò è utile per livellare le risorse di carico o in caso di scomposizione.</span><span class="sxs-lookup"><span data-stu-id="c937a-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="c937a-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c937a-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c937a-107">Questa procedura è destinata al responsabile pianificazione che lavora presso una società di produzione snella, responsabile del flusso del valore.</span><span class="sxs-lookup"><span data-stu-id="c937a-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="c937a-108">Copiare la regola kanban</span><span class="sxs-lookup"><span data-stu-id="c937a-108">Copy kanban rule</span></span>
1. <span data-ttu-id="c937a-109">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="c937a-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="c937a-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c937a-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c937a-111">Selezionare la regola kanban di evento 000022 per L0001.</span><span class="sxs-lookup"><span data-stu-id="c937a-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="c937a-112">Fare clic su Duplica regola kanban.</span><span class="sxs-lookup"><span data-stu-id="c937a-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="c937a-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c937a-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="c937a-114">Modificare la regola kanban</span><span class="sxs-lookup"><span data-stu-id="c937a-114">Change kanban rule</span></span>
1. <span data-ttu-id="c937a-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c937a-115">Close the page.</span></span>
2. <span data-ttu-id="c937a-116">Passare a Programmazione processo kanban.</span><span class="sxs-lookup"><span data-stu-id="c937a-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="c937a-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c937a-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c937a-118">Selezionare la riga con il kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="c937a-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="c937a-119">Fare clic su Utilizza regola kanban alternativa.</span><span class="sxs-lookup"><span data-stu-id="c937a-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="c937a-120">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="c937a-120">Click Next.</span></span>
6. <span data-ttu-id="c937a-121">Nel campo Regola kanban immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c937a-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="c937a-122">Selezionare la regola kanban creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c937a-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="c937a-123">Si tratta della regola kanban con il numero più elevato.</span><span class="sxs-lookup"><span data-stu-id="c937a-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="c937a-124">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="c937a-124">Click Finish.</span></span>
    * <span data-ttu-id="c937a-125">A questo punto il processo kanban utilizza un'altra regola kanban.</span><span class="sxs-lookup"><span data-stu-id="c937a-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="c937a-126">Può essere utile per livellare il carico delle celle di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c937a-126">This can be useful to level load work cells.</span></span>  


