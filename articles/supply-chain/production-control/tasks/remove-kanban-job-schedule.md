---
title: Rimuovere un processo kanban dalla programmazione
description: Questa procedura riguarda la rimozione di un processo kanban di lavorazione pianificato dalla programmazione ripristinando lo stato del processo su Non pianificato.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4d994be5c6bb1edc6f0fc64494a19a5babf72ae
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "352070"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="4919c-103">Rimuovere un processo kanban dalla programmazione</span><span class="sxs-lookup"><span data-stu-id="4919c-103">Remove a kanban job from the schedule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4919c-104">Questa procedura riguarda la rimozione di un processo kanban di lavorazione pianificato dalla programmazione ripristinando lo stato del processo su Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="4919c-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="4919c-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="4919c-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="4919c-106">La procedura è destinata al supervisore dello shop floor o al responsabile di pianificazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="4919c-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="4919c-107">Trovare un processo kanban pianificato</span><span class="sxs-lookup"><span data-stu-id="4919c-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="4919c-108">Andare a Controllo produzione > Kanban > Programmazione processo kanban.</span><span class="sxs-lookup"><span data-stu-id="4919c-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="4919c-109">Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4919c-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4919c-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4919c-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4919c-111">Selezionare la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="4919c-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="4919c-112">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="4919c-112">Click Select.</span></span>
5. <span data-ttu-id="4919c-113">Nel campo Visualizza stato processo selezionare "Programmato".</span><span class="sxs-lookup"><span data-stu-id="4919c-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="4919c-114">Rimuovere il processo kanban pianificato dalla programmazione</span><span class="sxs-lookup"><span data-stu-id="4919c-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="4919c-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4919c-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4919c-116">Selezionare un processo con stato Pianificato, ad esempio un processo del 19 dicembre 2012.</span><span class="sxs-lookup"><span data-stu-id="4919c-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="4919c-117">Nel riquadro azioni fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="4919c-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="4919c-118">Fare clic su Ripristina stato del processo.</span><span class="sxs-lookup"><span data-stu-id="4919c-118">Click Revert job status.</span></span>
4. <span data-ttu-id="4919c-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4919c-119">Click OK.</span></span>
    * <span data-ttu-id="4919c-120">In questo modo lo stato del processo corrente verrà ripristinato da Pianificato a Non pianificato e il processo verrà rimosso dalla bacheca dei processi.</span><span class="sxs-lookup"><span data-stu-id="4919c-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

