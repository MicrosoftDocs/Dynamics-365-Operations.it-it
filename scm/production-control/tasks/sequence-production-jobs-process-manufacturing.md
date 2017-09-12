--- 
title: Processi di produzione in sequenza per la produzione di processo
description: "Questa procedura utilizza i prodotti di vernice come esempio per mostrare come ordinare gli ordini pianificati in sequenza in base alla priorità di colore e dimensione del collo."
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a25a4575ca1600b07b2dac5949c8775bcd162650
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="2d6b5-103">Processi di produzione in sequenza per la produzione di processo</span><span class="sxs-lookup"><span data-stu-id="2d6b5-103">Sequence production jobs for process manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2d6b5-104">Questa procedura utilizza i prodotti di vernice come esempio per mostrare come ordinare gli ordini pianificati in sequenza in base alla priorità di colore e dimensione del collo.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="2d6b5-105">La società di dati dimostrativi utilizzata per creare questa procedura è USPI.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="2d6b5-106">Questa procedura è destinata al responsabile pianificazione produzione.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="2d6b5-107">Eseguire la pianificazione generale per USPI</span><span class="sxs-lookup"><span data-stu-id="2d6b5-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="2d6b5-108">Andare a Pianificazione generale > Pianificazione generale > Esegui > Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="2d6b5-109">Nel campo Piano generale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2d6b5-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2d6b5-111">Selezionare Piano generale.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="2d6b5-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-112">Click OK.</span></span>
    * <span data-ttu-id="2d6b5-113">Si avvia la pianificazione generale, incluso il processo di sequenza.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="2d6b5-114">Il processo può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="2d6b5-115">Visualizzare gli ordini pianificati per i prodotti di vernice</span><span class="sxs-lookup"><span data-stu-id="2d6b5-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="2d6b5-116">Andare a Pianificazione generale > Pianificazione generale > Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="2d6b5-117">Espandere il riquadro Dettaglio informazioni dei dettagli articolo.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="2d6b5-118">Espandere il riquadro Dettaglio informazioni della programmazione.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="2d6b5-119">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2d6b5-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2d6b5-121">Selezionare Piano generale.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="2d6b5-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="2d6b5-123">Utilizzare il filtro rapido per filtrare il campo Numero articolo in base al valore "P300".</span><span class="sxs-lookup"><span data-stu-id="2d6b5-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="2d6b5-124">Sbloccare per scorrere a destra e visualizzare la data dell'ordine e la data di consegna.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="2d6b5-125">Questi articoli con data dell'ordine odierna e le date di consegna degli ordini pianificati non vengono ordinati in sequenza dopo la priorità di colore e di dimensione del collo, come illustrato nel nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="2d6b5-126">È possibile passare il mouse su un numero di articolo per visualizzare il nome del prodotto e la priorità.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="2d6b5-127">Mettere in sequenza gli ordini pianificati di vernice</span><span class="sxs-lookup"><span data-stu-id="2d6b5-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="2d6b5-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-128">Close the page.</span></span>
2. <span data-ttu-id="2d6b5-129">Andare a Pianificazione generale > Pianificazione generale > Ordini pianificati in sequenza.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="2d6b5-130">Espandere il riquadro Dettaglio informazioni dei dettagli articolo.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="2d6b5-131">Espandere il riquadro Dettaglio informazioni della programmazione.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="2d6b5-132">Nota: in questo campo la data e l'ora di inizio degli ordini pianificati sono ordinate in sequenza in base al colore e alla dimensione del collo in un periodo dell'intervallo di tempo di 28 giorni.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="2d6b5-133">Questi periodi sono definiti da un numero nel campo Campagna.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="2d6b5-134">Il modulo dell'ordine pianificato in sequenza agisce come il normale modulo ordine pianificato e il pianificatore di produzione può stabilizzare gli ordini pianificati in questo campo.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="2d6b5-135">Contrassegnare tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-135">Mark all rows.</span></span>
6. <span data-ttu-id="2d6b5-136">Fare clic su Accetta.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-136">Click Accept.</span></span>
    * <span data-ttu-id="2d6b5-137">Questa operazione aggiornerà gli ordini pianificati con l'azione di sequenza selezionata Posticipa o Anticipa.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="2d6b5-138">Verificare la sequenza degli ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="2d6b5-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="2d6b5-139">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-139">Close the page.</span></span>
2. <span data-ttu-id="2d6b5-140">Andare a Pianificazione generale > Pianificazione generale > Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="2d6b5-141">Espandere il riquadro Dettaglio informazioni dei dettagli articolo.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="2d6b5-142">Espandere il riquadro Dettaglio informazioni della programmazione.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="2d6b5-143">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2d6b5-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2d6b5-145">Selezionare Piano generale.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="2d6b5-146">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2d6b5-147">Utilizzare il filtro rapido per filtrare il campo Numero articolo in base al valore "P300".</span><span class="sxs-lookup"><span data-stu-id="2d6b5-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="2d6b5-148">Gli ordini vengono ora ordinati in sequenza in base alla priorità di colore e dimensioni e gli ordini pianificati cominciano alla prima data dell'ordine e alla prima data di consegna.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="2d6b5-149">Convalidare la colonna relativa alla data dell'ordine o alla data di inizio in Dettagli programmazione nel riquadro Dettaglio informazioni.</span><span class="sxs-lookup"><span data-stu-id="2d6b5-149">Validate the Order date column or the Start date in the Schedule details FactBbox.</span></span>  

