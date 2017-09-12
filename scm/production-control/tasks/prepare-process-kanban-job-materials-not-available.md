--- 
title: Preparare un processo kanban quando non sono disponibili materiali per la cella di lavoro
description: "Questa procedura riguarda la preparazione del processo kanban di lavorazione quando alcuni materiali non sono disponibili per la cella di lavoro ed è pertanto necessario prelevarvi dal magazzino."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 5a47af6910a9686e74ab6d1069dd02079e60cb8a
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="6730f-103">Preparare un processo kanban quando non sono disponibili materiali per la cella di lavoro</span><span class="sxs-lookup"><span data-stu-id="6730f-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6730f-104">Questa procedura riguarda la preparazione del processo kanban di lavorazione quando alcuni materiali non sono disponibili per la cella di lavoro ed è pertanto necessario prelevarvi dal magazzino.</span><span class="sxs-lookup"><span data-stu-id="6730f-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="6730f-105">La procedura Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro" è un prerequisito per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="6730f-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="6730f-106">Questa procedura è destinata all'operatore.</span><span class="sxs-lookup"><span data-stu-id="6730f-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="6730f-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="6730f-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="6730f-108">Andare a Controllo produzione > Kanban > Bacheca kanban per i processi di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="6730f-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="6730f-109">Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6730f-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="6730f-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6730f-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6730f-111">Selezionare la cella di lavoro 1250.</span><span class="sxs-lookup"><span data-stu-id="6730f-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="6730f-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6730f-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6730f-113">Selezionare Kanban 000356</span><span class="sxs-lookup"><span data-stu-id="6730f-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="6730f-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6730f-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6730f-115">Nell'elenco deselezionare la riga 4.</span><span class="sxs-lookup"><span data-stu-id="6730f-115">In the list, deselect row 4.</span></span> <span data-ttu-id="6730f-116">Selezionarla se non è stata completata l'attività "Preparare un processo kanban quando sono disponibili materiali".</span><span class="sxs-lookup"><span data-stu-id="6730f-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="6730f-117">Attivare/disattivare l'espansione della sezione Distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="6730f-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="6730f-118">L'icona che indica nessuna voce nello stato fornitura mostra che 48 unità dell'articolo P0002 sono mancanti per la cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6730f-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="6730f-119">Trasferire materiali nella cella di lavoro</span><span class="sxs-lookup"><span data-stu-id="6730f-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="6730f-120">Attivare/disattivare l'espansione della sezione Processi di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6730f-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="6730f-121">Utilizzare il filtro rapido per filtrare il campo Numero articolo in base al valore "P0002".</span><span class="sxs-lookup"><span data-stu-id="6730f-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="6730f-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6730f-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="6730f-123">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="6730f-123">Click Start.</span></span>
    * <span data-ttu-id="6730f-124">Trasferimento in corso.</span><span class="sxs-lookup"><span data-stu-id="6730f-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="6730f-125">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="6730f-125">Click Complete.</span></span>
    * <span data-ttu-id="6730f-126">L'articolo P0002 ora è disponibile nella distinta di prelievo per il processo kanban.</span><span class="sxs-lookup"><span data-stu-id="6730f-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="6730f-127">Ciò significa che è possibile preparare il processo kanban con tutti i materiali necessari.</span><span class="sxs-lookup"><span data-stu-id="6730f-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="6730f-128">Fare clic su Prepara.</span><span class="sxs-lookup"><span data-stu-id="6730f-128">Click Prepare.</span></span>
    * <span data-ttu-id="6730f-129">Si noti che un'icona nello stato del processo indica che il processo ora è pronto.</span><span class="sxs-lookup"><span data-stu-id="6730f-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  


