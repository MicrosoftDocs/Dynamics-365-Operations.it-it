---
title: Trasferire materiali con processi kanban
description: Questa procedura riguarda l'esecuzione del processo kanban di prelievo per trasferire i materiali.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e8808b168d2b3845b315e6bbcfb376e37f31fe4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981033"
---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="1ce01-103">Trasferire materiali con processi kanban</span><span class="sxs-lookup"><span data-stu-id="1ce01-103">Transfer materials with kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ce01-104">Questa procedura riguarda l'esecuzione del processo kanban di prelievo per trasferire i materiali.</span><span class="sxs-lookup"><span data-stu-id="1ce01-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="1ce01-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="1ce01-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1ce01-106">Questa procedura è destinata all'addetto al magazzino.</span><span class="sxs-lookup"><span data-stu-id="1ce01-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="1ce01-107">Visualizza processi di trasferimento</span><span class="sxs-lookup"><span data-stu-id="1ce01-107">Display transfer jobs</span></span>
1. <span data-ttu-id="1ce01-108">Andare a Controllo produzione > Kanban > Bacheca kanban per processi di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="1ce01-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="1ce01-109">Espandere o comprimere la sezione Filtri.</span><span class="sxs-lookup"><span data-stu-id="1ce01-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="1ce01-110">Nella sezione Filtri è possibile specificare i processi che si desidera visualizzare filtrando per flusso di produzione, nome dell'attività, il magazzino e ubicazione di origine e magazzino e ubicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1ce01-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="1ce01-111">Nel campo Magazzino origine digitare "11".</span><span class="sxs-lookup"><span data-stu-id="1ce01-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="1ce01-112">Nel campo Ubicazione destinazione digitare "12".</span><span class="sxs-lookup"><span data-stu-id="1ce01-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="1ce01-113">Avvia un processo di trasferimento</span><span class="sxs-lookup"><span data-stu-id="1ce01-113">Start a transfer job</span></span>
1. <span data-ttu-id="1ce01-114">Nell'elenco deselezionare la riga selezionata, se presente.</span><span class="sxs-lookup"><span data-stu-id="1ce01-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="1ce01-115">Nell'elenco selezionare la riga 4.</span><span class="sxs-lookup"><span data-stu-id="1ce01-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="1ce01-116">Selezionare il primo processo con lo stato Non pianificato.</span><span class="sxs-lookup"><span data-stu-id="1ce01-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="1ce01-117">Assicurarsi che questo sia l'unico processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ce01-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="1ce01-118">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="1ce01-118">Click Start.</span></span>
    * <span data-ttu-id="1ce01-119">Si noti che un'icona indica che il processo è avviato.</span><span class="sxs-lookup"><span data-stu-id="1ce01-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="1ce01-120">Selezionare un secondo processo di trasferimento e modificare la quantità</span><span class="sxs-lookup"><span data-stu-id="1ce01-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="1ce01-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1ce01-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1ce01-122">È possibile selezionare più processi, ma per adesso selezionare solo la riga 5.</span><span class="sxs-lookup"><span data-stu-id="1ce01-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="1ce01-123">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1ce01-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1ce01-124">Verificare che il processo nel passaggio precedente sia l'unico selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ce01-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="1ce01-125">Deselezionare tutti gli altri processi.</span><span class="sxs-lookup"><span data-stu-id="1ce01-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="1ce01-126">Annotare il valore nel campo Quantità processo per farvi riferimento in seguito</span><span class="sxs-lookup"><span data-stu-id="1ce01-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="1ce01-127">Impostare la quantità processo su "30".</span><span class="sxs-lookup"><span data-stu-id="1ce01-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="1ce01-128">Si noti l'avviso.</span><span class="sxs-lookup"><span data-stu-id="1ce01-128">Notice the warning!</span></span> <span data-ttu-id="1ce01-129">Non è possibile trasferire una quantità pari a 30.</span><span class="sxs-lookup"><span data-stu-id="1ce01-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="1ce01-130">In base all'impostazione della regola kanban, è possibile trasferire solo la quantità originale.</span><span class="sxs-lookup"><span data-stu-id="1ce01-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="1ce01-131">Utilizzare il valore annotato in precedenza nel campo Quantità processo</span><span class="sxs-lookup"><span data-stu-id="1ce01-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="1ce01-132">Impostare la quantità del processo sul valore precedente.</span><span class="sxs-lookup"><span data-stu-id="1ce01-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="1ce01-133">Avviare il secondo processo di trasferimento</span><span class="sxs-lookup"><span data-stu-id="1ce01-133">Start the second transfer job</span></span>
1. <span data-ttu-id="1ce01-134">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="1ce01-134">Click Start.</span></span>
    * <span data-ttu-id="1ce01-135">Verrà iniziato il trasferimento del processo nella riga. 5.</span><span class="sxs-lookup"><span data-stu-id="1ce01-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="1ce01-136">Completare entrambi i processi di trasferimento</span><span class="sxs-lookup"><span data-stu-id="1ce01-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="1ce01-137">Nell'elenco selezionare la riga 4.</span><span class="sxs-lookup"><span data-stu-id="1ce01-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="1ce01-138">Ora due processi di trasferimento sono selezionati nella riga 4 e nella riga. 5.</span><span class="sxs-lookup"><span data-stu-id="1ce01-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="1ce01-139">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="1ce01-139">Click Complete.</span></span>
    * <span data-ttu-id="1ce01-140">In questo modo verrà completato il trasferimento di entrambi i processi.</span><span class="sxs-lookup"><span data-stu-id="1ce01-140">This will complete the transfer of both jobs.</span></span>  

