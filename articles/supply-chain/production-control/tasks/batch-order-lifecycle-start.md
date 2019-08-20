---
title: Ciclo di vita di ordini batch dalla creazione all'avvio
description: In questa procedura vengono descritti i passaggi della prima parte del ciclo di vita di un ordine batch.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a1803822bebf58a3370afe8c5dc9f519c65917d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843819"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="41d0f-103">Ciclo di vita di ordini batch dalla creazione all'avvio</span><span class="sxs-lookup"><span data-stu-id="41d0f-103">Batch order lifecycle from create to start</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="41d0f-104">In questa procedura vengono descritti i passaggi della prima parte del ciclo di vita di un ordine batch.</span><span class="sxs-lookup"><span data-stu-id="41d0f-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="41d0f-105">Dalla creazione, stima dei costi e programmazione de processo di produzione all'inizio effettivo di un ordine batch.</span><span class="sxs-lookup"><span data-stu-id="41d0f-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="41d0f-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="41d0f-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="41d0f-107">I prerequisiti per eseguire la procedura con un altro set di dati sono un prodotto rilasciato con una versione attiva del ciclo di lavorazione e della formula.</span><span class="sxs-lookup"><span data-stu-id="41d0f-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="41d0f-108">Creazione di un ordine lotto</span><span class="sxs-lookup"><span data-stu-id="41d0f-108">Create a batch order</span></span>
1. <span data-ttu-id="41d0f-109">Passare a Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="41d0f-109">Go to All production orders.</span></span>
2. <span data-ttu-id="41d0f-110">Fare clic su Nuovo ordine batch.</span><span class="sxs-lookup"><span data-stu-id="41d0f-110">Click New batch order.</span></span>
3. <span data-ttu-id="41d0f-111">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="41d0f-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="41d0f-112">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="41d0f-112">Click Create.</span></span>
5. <span data-ttu-id="41d0f-113">Utilizzare il filtro rapido per filtrare il campo Produzione in base a un valore di 'b'.</span><span class="sxs-lookup"><span data-stu-id="41d0f-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="41d0f-114">Visualizzare la formula di produzione e i co-prodotti previsti</span><span class="sxs-lookup"><span data-stu-id="41d0f-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="41d0f-115">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="41d0f-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="41d0f-116">Fare clic su Formula.</span><span class="sxs-lookup"><span data-stu-id="41d0f-116">Click Formula.</span></span>
3. <span data-ttu-id="41d0f-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-117">Close the page.</span></span>
4. <span data-ttu-id="41d0f-118">Fare clic su Co-prodotti.</span><span class="sxs-lookup"><span data-stu-id="41d0f-118">Click Co-products.</span></span>
5. <span data-ttu-id="41d0f-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="41d0f-120">Stimare l'ordine batch</span><span class="sxs-lookup"><span data-stu-id="41d0f-120">Estimate the batch order</span></span>
1. <span data-ttu-id="41d0f-121">Fare clic su Stima.</span><span class="sxs-lookup"><span data-stu-id="41d0f-121">Click Estimate.</span></span>
2. <span data-ttu-id="41d0f-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="41d0f-122">Click OK.</span></span>
3. <span data-ttu-id="41d0f-123">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="41d0f-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="41d0f-124">Fare clic su Visualizza dettagli calcolo.</span><span class="sxs-lookup"><span data-stu-id="41d0f-124">Click View calculation details.</span></span>
5. <span data-ttu-id="41d0f-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="41d0f-126">Rilasciare l'ordine batch</span><span class="sxs-lookup"><span data-stu-id="41d0f-126">Release the batch order</span></span>
1. <span data-ttu-id="41d0f-127">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="41d0f-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="41d0f-128">Fare clic su Rilascia.</span><span class="sxs-lookup"><span data-stu-id="41d0f-128">Click Release.</span></span>
3. <span data-ttu-id="41d0f-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="41d0f-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="41d0f-130">Programmare i processi di produzione</span><span class="sxs-lookup"><span data-stu-id="41d0f-130">Schedule production jobs</span></span>
1. <span data-ttu-id="41d0f-131">Nel riquadro azioni fare clic su Programmazione.</span><span class="sxs-lookup"><span data-stu-id="41d0f-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="41d0f-132">Fare clic su Programma processi.</span><span class="sxs-lookup"><span data-stu-id="41d0f-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="41d0f-133">Selezionare No nel campo Capacità limitata.</span><span class="sxs-lookup"><span data-stu-id="41d0f-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="41d0f-134">Selezionare No nel campo Materiale limitato.</span><span class="sxs-lookup"><span data-stu-id="41d0f-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="41d0f-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="41d0f-135">Click OK.</span></span>
6. <span data-ttu-id="41d0f-136">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="41d0f-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="41d0f-137">Fare clic su Tutti i processi.</span><span class="sxs-lookup"><span data-stu-id="41d0f-137">Click All jobs.</span></span>
8. <span data-ttu-id="41d0f-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="41d0f-139">Iniziare l'ordine batch</span><span class="sxs-lookup"><span data-stu-id="41d0f-139">Start the batch order</span></span>
1. <span data-ttu-id="41d0f-140">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="41d0f-140">Click Start.</span></span>
2. <span data-ttu-id="41d0f-141">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="41d0f-141">Click the General tab.</span></span>
3. <span data-ttu-id="41d0f-142">Selezionare No nel campo Registra distinta di prelievo ora.</span><span class="sxs-lookup"><span data-stu-id="41d0f-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="41d0f-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="41d0f-143">Click OK.</span></span>
5. <span data-ttu-id="41d0f-144">Nel riquadro azioni fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="41d0f-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="41d0f-145">Fare clic su Distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="41d0f-145">Click Picking list.</span></span>
7. <span data-ttu-id="41d0f-146">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="41d0f-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="41d0f-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-147">Close the page.</span></span>
9. <span data-ttu-id="41d0f-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-148">Close the page.</span></span>
10. <span data-ttu-id="41d0f-149">Fare clic su Scheda ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="41d0f-149">Click Route card.</span></span>
11. <span data-ttu-id="41d0f-150">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="41d0f-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="41d0f-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-151">Close the page.</span></span>
13. <span data-ttu-id="41d0f-152">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41d0f-152">Close the page.</span></span>

