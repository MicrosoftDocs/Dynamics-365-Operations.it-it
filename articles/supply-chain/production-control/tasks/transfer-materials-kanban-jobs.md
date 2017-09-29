--- 
title: Trasferire materiali tramite processi kanban (solo febbraio 2016)
description: Questa procedura riguarda l'esecuzione del processo kanban di prelievo per trasferire i materiali.
author: ChristianRytt
manager: AnnBe
ms.date: 02/07/2017
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
ms.openlocfilehash: c79480d844627a7eed8129515924f1f70ad04f95
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="transfer-materials-with-kanban-jobs-february-2016-only"></a><span data-ttu-id="f89fe-103">Trasferire materiali tramite processi kanban (solo febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="f89fe-103">Transfer materials with kanban jobs (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f89fe-104">Questa procedura riguarda l'esecuzione del processo kanban di prelievo per trasferire i materiali.</span><span class="sxs-lookup"><span data-stu-id="f89fe-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="f89fe-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="f89fe-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f89fe-106">Questa procedura è destinata all'addetto al magazzino.</span><span class="sxs-lookup"><span data-stu-id="f89fe-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="f89fe-107">Visualizza processi di trasferimento</span><span class="sxs-lookup"><span data-stu-id="f89fe-107">Display transfer jobs</span></span>
1. <span data-ttu-id="f89fe-108">Andare a Controllo produzione > Kanban > Bacheca kanban per processi di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="f89fe-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="f89fe-109">Espandere o comprimere la sezione Filtri.</span><span class="sxs-lookup"><span data-stu-id="f89fe-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="f89fe-110">Nella sezione Filtri è possibile specificare i processi che si desidera visualizzare filtrando per flusso di produzione, nome dell'attività, il magazzino e ubicazione di origine e magazzino e ubicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f89fe-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="f89fe-111">Nel campo Magazzino origine digitare "11".</span><span class="sxs-lookup"><span data-stu-id="f89fe-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="f89fe-112">Nel campo Ubicazione destinazione digitare "12".</span><span class="sxs-lookup"><span data-stu-id="f89fe-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="f89fe-113">Avvia un processo di trasferimento</span><span class="sxs-lookup"><span data-stu-id="f89fe-113">Start a transfer job</span></span>
1. <span data-ttu-id="f89fe-114">Nell'elenco deselezionare la riga selezionata, se presente.</span><span class="sxs-lookup"><span data-stu-id="f89fe-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="f89fe-115">Nell'elenco selezionare la riga 4.</span><span class="sxs-lookup"><span data-stu-id="f89fe-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="f89fe-116">Selezionare il primo processo con lo stato Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="f89fe-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="f89fe-117">Assicurarsi che questo sia l'unico processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f89fe-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="f89fe-118">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="f89fe-118">Click Start.</span></span>
    * <span data-ttu-id="f89fe-119">Si noti che un'icona indica che il processo è avviato.</span><span class="sxs-lookup"><span data-stu-id="f89fe-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="f89fe-120">Selezionare un secondo processo di trasferimento e modificare la quantità</span><span class="sxs-lookup"><span data-stu-id="f89fe-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="f89fe-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f89fe-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f89fe-122">È possibile selezionare più processi, ma per adesso selezionare solo la riga 5.</span><span class="sxs-lookup"><span data-stu-id="f89fe-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="f89fe-123">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f89fe-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f89fe-124">Verificare che il processo nel passaggio precedente sia l'unico selezionato.</span><span class="sxs-lookup"><span data-stu-id="f89fe-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="f89fe-125">Deselezionare tutti gli altri processi.</span><span class="sxs-lookup"><span data-stu-id="f89fe-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="f89fe-126">Annotare il valore nel campo Quantità processo per farvi riferimento in seguito</span><span class="sxs-lookup"><span data-stu-id="f89fe-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="f89fe-127">Impostare la quantità processo su "30".</span><span class="sxs-lookup"><span data-stu-id="f89fe-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="f89fe-128">Si noti l'avviso.</span><span class="sxs-lookup"><span data-stu-id="f89fe-128">Notice the warning!</span></span> <span data-ttu-id="f89fe-129">Non è possibile trasferire una quantità pari a 30.</span><span class="sxs-lookup"><span data-stu-id="f89fe-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="f89fe-130">In base all'impostazione della regola kanban, è possibile trasferire solo la quantità originale.</span><span class="sxs-lookup"><span data-stu-id="f89fe-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="f89fe-131">Utilizzare il valore annotato in precedenza nel campo Quantità processo</span><span class="sxs-lookup"><span data-stu-id="f89fe-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="f89fe-132">Impostare la quantità del processo sul valore precedente.</span><span class="sxs-lookup"><span data-stu-id="f89fe-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="f89fe-133">Avviare il secondo processo di trasferimento</span><span class="sxs-lookup"><span data-stu-id="f89fe-133">Start the second transfer job</span></span>
1. <span data-ttu-id="f89fe-134">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="f89fe-134">Click Start.</span></span>
    * <span data-ttu-id="f89fe-135">Verrà iniziato il trasferimento del processo nella riga. 5.</span><span class="sxs-lookup"><span data-stu-id="f89fe-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="f89fe-136">Completare entrambi i processi di trasferimento</span><span class="sxs-lookup"><span data-stu-id="f89fe-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="f89fe-137">Nell'elenco selezionare la riga 4.</span><span class="sxs-lookup"><span data-stu-id="f89fe-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="f89fe-138">Ora due processi di trasferimento sono selezionati nella riga 4 e nella riga. 5.</span><span class="sxs-lookup"><span data-stu-id="f89fe-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="f89fe-139">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="f89fe-139">Click Complete.</span></span>
    * <span data-ttu-id="f89fe-140">In questo modo verrà completato il trasferimento di entrambi i processi.</span><span class="sxs-lookup"><span data-stu-id="f89fe-140">This will complete the transfer of both jobs.</span></span>  


