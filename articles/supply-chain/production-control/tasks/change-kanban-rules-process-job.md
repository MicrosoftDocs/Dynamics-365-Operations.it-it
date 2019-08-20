---
title: Modificare regole kanban di un processo di lavorazione
description: La procedura consente di modificare la regola kanban utilizzata per un kanban specifico.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c036f6aad79e33df6009913d1e21ff6176f22593
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843795"
---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="0478e-103">Modificare regole kanban di un processo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="0478e-103">Change kanban rules for a process job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0478e-104">La procedura consente di modificare la regola kanban utilizzata per un kanban specifico.</span><span class="sxs-lookup"><span data-stu-id="0478e-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="0478e-105">Ciò è utile per livellare le risorse di carico o in caso di scomposizione.</span><span class="sxs-lookup"><span data-stu-id="0478e-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="0478e-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="0478e-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0478e-107">Questa procedura è destinata al responsabile pianificazione che lavora presso una società di produzione snella, responsabile del flusso del valore.</span><span class="sxs-lookup"><span data-stu-id="0478e-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="0478e-108">Copiare la regola kanban</span><span class="sxs-lookup"><span data-stu-id="0478e-108">Copy kanban rule</span></span>
1. <span data-ttu-id="0478e-109">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="0478e-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="0478e-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="0478e-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0478e-111">Selezionare la regola kanban di evento 000022 per L0001.</span><span class="sxs-lookup"><span data-stu-id="0478e-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="0478e-112">Fare clic su Duplica regola kanban.</span><span class="sxs-lookup"><span data-stu-id="0478e-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="0478e-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0478e-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="0478e-114">Modificare la regola kanban</span><span class="sxs-lookup"><span data-stu-id="0478e-114">Change kanban rule</span></span>
1. <span data-ttu-id="0478e-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0478e-115">Close the page.</span></span>
2. <span data-ttu-id="0478e-116">Passare a Programmazione processo kanban.</span><span class="sxs-lookup"><span data-stu-id="0478e-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="0478e-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0478e-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0478e-118">Selezionare la riga con il kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="0478e-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="0478e-119">Fare clic su Utilizza regola kanban alternativa.</span><span class="sxs-lookup"><span data-stu-id="0478e-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="0478e-120">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="0478e-120">Click Next.</span></span>
6. <span data-ttu-id="0478e-121">Nel campo Regola kanban immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0478e-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="0478e-122">Selezionare la regola kanban creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0478e-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="0478e-123">Si tratta della regola kanban con il numero più elevato.</span><span class="sxs-lookup"><span data-stu-id="0478e-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="0478e-124">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="0478e-124">Click Finish.</span></span>
    * <span data-ttu-id="0478e-125">A questo punto il processo kanban utilizza un'altra regola kanban.</span><span class="sxs-lookup"><span data-stu-id="0478e-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="0478e-126">Può essere utile per livellare il carico delle celle di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0478e-126">This can be useful to level load work cells.</span></span>  

