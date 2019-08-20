---
title: Eseguire processi di lavorazione kanban
description: Questa procedura illustra come eseguire i processi di lavorazione kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08fddd6404bf835283adaca14ad7ceb851f5a489
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837640"
---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="32c4a-103">Eseguire processi di lavorazione kanban</span><span class="sxs-lookup"><span data-stu-id="32c4a-103">Execute kanban process jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="32c4a-104">Questa procedura illustra come eseguire i processi di lavorazione kanban.</span><span class="sxs-lookup"><span data-stu-id="32c4a-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="32c4a-105">Il primo processo è stato completato con la quantità prevista e non presenta errori.</span><span class="sxs-lookup"><span data-stu-id="32c4a-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="32c4a-106">Il secondo lavoro è stato completato con errori.</span><span class="sxs-lookup"><span data-stu-id="32c4a-106">The second job is completed with errors.</span></span> <span data-ttu-id="32c4a-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="32c4a-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="32c4a-108">Questa procedura è destinata all'operatore.</span><span class="sxs-lookup"><span data-stu-id="32c4a-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="32c4a-109">Selezionare un processo kanban</span><span class="sxs-lookup"><span data-stu-id="32c4a-109">Select a kanban job</span></span>
1. <span data-ttu-id="32c4a-110">Andare a Controllo produzione > Kanban > Bacheca kanban per i processi di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="32c4a-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="32c4a-111">Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="32c4a-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="32c4a-112">Fare clic sulla riga con il gruppo di risorse 1250.</span><span class="sxs-lookup"><span data-stu-id="32c4a-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="32c4a-113">In questo modo verrà filtrato l'elenco dei processi per mostrare solo i processi per la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="32c4a-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="32c4a-114">Contrassegnare la riga con stato del processo pianificato.</span><span class="sxs-lookup"><span data-stu-id="32c4a-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="32c4a-115">Completare un processo con la quantità prevista</span><span class="sxs-lookup"><span data-stu-id="32c4a-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="32c4a-116">Espandere o comprimere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="32c4a-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="32c4a-117">In questa sezione vengono visualizzate le informazioni principali sul numero di carta, il numero di articolo, la quantità ordinata e il nome dell'attività.</span><span class="sxs-lookup"><span data-stu-id="32c4a-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="32c4a-118">Espandere o comprimere la sezione Istruzioni produzione.</span><span class="sxs-lookup"><span data-stu-id="32c4a-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="32c4a-119">In questa sezione vengono visualizzate le istruzioni di produzione per l'attività.</span><span class="sxs-lookup"><span data-stu-id="32c4a-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="32c4a-120">Le istruzioni possono essere testo, immagini, disegni e altri documenti.</span><span class="sxs-lookup"><span data-stu-id="32c4a-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="32c4a-121">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="32c4a-121">Click Start.</span></span>
    * <span data-ttu-id="32c4a-122">Selezionare un processo che non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="32c4a-122">Select a job that is not completed.</span></span> <span data-ttu-id="32c4a-123">Utilizzare le icone di stato nel campo Stato del processo per visualizzare lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="32c4a-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="32c4a-124">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="32c4a-124">Click Complete.</span></span>
    * <span data-ttu-id="32c4a-125">Il processo è stato completato con la qualità prevista.</span><span class="sxs-lookup"><span data-stu-id="32c4a-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="32c4a-126">Completare un processo con errori</span><span class="sxs-lookup"><span data-stu-id="32c4a-126">Complete a job with errors</span></span>
1. <span data-ttu-id="32c4a-127">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="32c4a-127">Click Start.</span></span>
    * <span data-ttu-id="32c4a-128">Quando un processo è completato, il processo successivo nell'elenco viene selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="32c4a-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="32c4a-129">Per questo motivo non è necessario selezionare un processo prima di fare clic su Start.</span><span class="sxs-lookup"><span data-stu-id="32c4a-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="32c4a-130">Nel riquadro azioni, fare clic su Produzione.</span><span class="sxs-lookup"><span data-stu-id="32c4a-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="32c4a-131">Fare clic su Completa (dettagli).</span><span class="sxs-lookup"><span data-stu-id="32c4a-131">Click Complete (details).</span></span>
4. <span data-ttu-id="32c4a-132">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32c4a-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="32c4a-133">Nel campo Quantità difettosa immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="32c4a-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="32c4a-134">Nel campo Quantità idonea immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="32c4a-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="32c4a-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="32c4a-135">Click OK.</span></span>

