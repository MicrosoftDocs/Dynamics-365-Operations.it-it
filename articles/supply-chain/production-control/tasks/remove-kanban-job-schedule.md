---
title: Rimuovere un processo kanban dalla programmazione
description: Questa procedura riguarda la rimozione di un processo kanban di lavorazione pianificato dalla programmazione ripristinando lo stato del processo su Non pianificato.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0236faa9b534678ed232ac3572c8172c62e5241f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430843"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="64aef-103">Rimuovere un processo kanban dalla programmazione</span><span class="sxs-lookup"><span data-stu-id="64aef-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="64aef-104">Questa procedura riguarda la rimozione di un processo kanban di lavorazione pianificato dalla programmazione ripristinando lo stato del processo su Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="64aef-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="64aef-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="64aef-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="64aef-106">La procedura è destinata al supervisore dello shop floor o al responsabile di pianificazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="64aef-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="64aef-107">Trovare un processo kanban pianificato</span><span class="sxs-lookup"><span data-stu-id="64aef-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="64aef-108">Andare a Controllo produzione > Kanban > Programmazione processo kanban.</span><span class="sxs-lookup"><span data-stu-id="64aef-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="64aef-109">Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="64aef-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="64aef-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="64aef-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="64aef-111">Selezionare la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="64aef-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="64aef-112">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="64aef-112">Click Select.</span></span>
5. <span data-ttu-id="64aef-113">Nel campo Visualizza stato processo selezionare "Programmato".</span><span class="sxs-lookup"><span data-stu-id="64aef-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="64aef-114">Rimuovere il processo kanban pianificato dalla programmazione</span><span class="sxs-lookup"><span data-stu-id="64aef-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="64aef-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="64aef-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="64aef-116">Selezionare un processo con stato Pianificato, ad esempio un processo del 19 dicembre 2012.</span><span class="sxs-lookup"><span data-stu-id="64aef-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="64aef-117">Nel riquadro azioni fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="64aef-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="64aef-118">Fare clic su Ripristina stato del processo.</span><span class="sxs-lookup"><span data-stu-id="64aef-118">Click Revert job status.</span></span>
4. <span data-ttu-id="64aef-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="64aef-119">Click OK.</span></span>
    * <span data-ttu-id="64aef-120">In questo modo lo stato del processo corrente verrà ripristinato da Pianificato a Non pianificato e il processo verrà rimosso dalla bacheca dei processi.</span><span class="sxs-lookup"><span data-stu-id="64aef-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

