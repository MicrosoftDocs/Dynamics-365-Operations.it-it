---
title: Modificare regole kanban di un processo di lavorazione
description: La procedura consente di modificare la regola kanban utilizzata per un kanban specifico.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba77197f51b871f452c2aa94320aa2a68cf314df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255375"
---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="7d47f-103">Modificare regole kanban di un processo di lavorazione</span><span class="sxs-lookup"><span data-stu-id="7d47f-103">Change kanban rules for a process job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7d47f-104">La procedura consente di modificare la regola kanban utilizzata per un kanban specifico.</span><span class="sxs-lookup"><span data-stu-id="7d47f-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="7d47f-105">Ciò è utile per livellare le risorse di carico o in caso di scomposizione.</span><span class="sxs-lookup"><span data-stu-id="7d47f-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="7d47f-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="7d47f-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7d47f-107">Questa procedura è destinata al responsabile pianificazione che lavora presso una società di produzione snella, responsabile del flusso del valore.</span><span class="sxs-lookup"><span data-stu-id="7d47f-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="7d47f-108">Copiare la regola kanban</span><span class="sxs-lookup"><span data-stu-id="7d47f-108">Copy kanban rule</span></span>
1. <span data-ttu-id="7d47f-109">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="7d47f-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="7d47f-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7d47f-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7d47f-111">Selezionare la regola kanban di evento 000022 per L0001.</span><span class="sxs-lookup"><span data-stu-id="7d47f-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="7d47f-112">Fare clic su Duplica regola kanban.</span><span class="sxs-lookup"><span data-stu-id="7d47f-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="7d47f-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7d47f-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="7d47f-114">Modificare la regola kanban</span><span class="sxs-lookup"><span data-stu-id="7d47f-114">Change kanban rule</span></span>
1. <span data-ttu-id="7d47f-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7d47f-115">Close the page.</span></span>
2. <span data-ttu-id="7d47f-116">Passare a Programmazione processo kanban.</span><span class="sxs-lookup"><span data-stu-id="7d47f-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="7d47f-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7d47f-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7d47f-118">Selezionare la riga con il kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="7d47f-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="7d47f-119">Fare clic su Utilizza regola kanban alternativa.</span><span class="sxs-lookup"><span data-stu-id="7d47f-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="7d47f-120">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="7d47f-120">Click Next.</span></span>
6. <span data-ttu-id="7d47f-121">Nel campo Regola kanban immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7d47f-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="7d47f-122">Selezionare la regola kanban creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7d47f-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="7d47f-123">Si tratta della regola kanban con il numero più elevato.</span><span class="sxs-lookup"><span data-stu-id="7d47f-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="7d47f-124">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="7d47f-124">Click Finish.</span></span>
    * <span data-ttu-id="7d47f-125">A questo punto il processo kanban utilizza un'altra regola kanban.</span><span class="sxs-lookup"><span data-stu-id="7d47f-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="7d47f-126">Può essere utile per livellare il carico delle celle di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7d47f-126">This can be useful to level load work cells.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]