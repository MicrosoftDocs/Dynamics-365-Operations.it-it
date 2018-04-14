--- 
title: Creare una regola kanban eventi riga DBA
description: "Questa attività mostra la configurazione necessaria per creare una regola kanban evento per garantire il rifornimento per le righe DBA di produzione in un ambiente di produzione misto lean e classico."
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a84927f0abdbe822f71db9088217c8ac4143fba6
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="2bc87-103">Creare una regola kanban eventi riga DBA</span><span class="sxs-lookup"><span data-stu-id="2bc87-103">Create a BOM line event kanban rule</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2bc87-104">Questa attività mostra la configurazione necessaria per creare una regola kanban evento per garantire il rifornimento per le righe DBA di produzione in un ambiente di produzione misto lean e classico.</span><span class="sxs-lookup"><span data-stu-id="2bc87-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="2bc87-105">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="2bc87-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="2bc87-106">Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.</span><span class="sxs-lookup"><span data-stu-id="2bc87-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="2bc87-107">Crea una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="2bc87-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="2bc87-108">Andare a Controllo produzione > Attività periodiche > Calcolo quantità kanban > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="2bc87-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="2bc87-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bc87-109">Click New.</span></span>
3. <span data-ttu-id="2bc87-110">Selezionare "Prelievo" nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="2bc87-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="2bc87-111">Il tipo Prelievo viene utilizzato per creare kanban di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="2bc87-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="2bc87-112">Nel campo Strategia di rifornimento, selezionare 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="2bc87-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="2bc87-113">La strategia di evento è selezionata per creare il trasferimento dei kanban in base a un evento.</span><span class="sxs-lookup"><span data-stu-id="2bc87-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="2bc87-114">Più avanti nella guida di attività verrà attivata con la stima di un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2bc87-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="2bc87-115">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bc87-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="2bc87-116">Immettere o selezionare ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="2bc87-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="2bc87-117">Questa attività di trasferimento ha magazzino e ubicazione di entrata (output) 12, pertanto il materiale verrà spostato in ubicazione 12 in magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="2bc87-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="2bc87-118">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="2bc87-118">Expand the Details section.</span></span>
7. <span data-ttu-id="2bc87-119">Nel campo Prodotto immettere o selezionare M0001.</span><span class="sxs-lookup"><span data-stu-id="2bc87-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="2bc87-120">Espandere la sezione Eventi.</span><span class="sxs-lookup"><span data-stu-id="2bc87-120">Expand the Events section.</span></span>
9. <span data-ttu-id="2bc87-121">Nel campo Evento riga DBA selezionare "Automatico".</span><span class="sxs-lookup"><span data-stu-id="2bc87-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="2bc87-122">Con il campo Evento riga DBA impostato su Automatico, il kanban verrà creato per soddisfare le esigenze di materiale delle righe DBA dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2bc87-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="2bc87-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bc87-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="2bc87-124">Creare e modificare un nuovo ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="2bc87-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="2bc87-125">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="2bc87-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="2bc87-126">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="2bc87-126">Click New production order.</span></span>
3. <span data-ttu-id="2bc87-127">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bc87-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="2bc87-128">Immettere o selezionare "L0001".</span><span class="sxs-lookup"><span data-stu-id="2bc87-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="2bc87-129">Viene utilizzato l'articolo L0001 poiché l'articolo M0001 è incluso nella DBA per l'articolo L0001.</span><span class="sxs-lookup"><span data-stu-id="2bc87-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="2bc87-130">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="2bc87-130">Click Create.</span></span>
5. <span data-ttu-id="2bc87-131">Nell'elenco fare clic sul collegamento nella riga per L0001</span><span class="sxs-lookup"><span data-stu-id="2bc87-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="2bc87-132">Fare clic su DBA.</span><span class="sxs-lookup"><span data-stu-id="2bc87-132">Click BOM.</span></span>
7. <span data-ttu-id="2bc87-133">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2bc87-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2bc87-134">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="2bc87-134">Click Edit.</span></span>
9. <span data-ttu-id="2bc87-135">Nel campo Tipo di riga selezionare "Fornitura sottoposta a pegging".</span><span class="sxs-lookup"><span data-stu-id="2bc87-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="2bc87-136">La fornitura sottoposta a pegging è selezionata per avviare la creazione della fornitura di un kanban.</span><span class="sxs-lookup"><span data-stu-id="2bc87-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="2bc87-137">Selezionare No nel campo Consumo risorsa.</span><span class="sxs-lookup"><span data-stu-id="2bc87-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="2bc87-138">Deselezionando la casella di controllo Consumo risorsa è possibile modificare il magazzino.</span><span class="sxs-lookup"><span data-stu-id="2bc87-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="2bc87-139">Espandere la sezione Dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="2bc87-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="2bc87-140">Nel campo Magazzino digitare "12".</span><span class="sxs-lookup"><span data-stu-id="2bc87-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="2bc87-141">Il magazzino viene impostato su 12 poiché questo è il magazzino di output per l'attività di prelievo.</span><span class="sxs-lookup"><span data-stu-id="2bc87-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="2bc87-142">Nel campo Ubicazione digitare "12".</span><span class="sxs-lookup"><span data-stu-id="2bc87-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="2bc87-143">L'ubicazione viene impostata su 12 poiché questa è l'ubicazione di output per l'attività di prelievo.</span><span class="sxs-lookup"><span data-stu-id="2bc87-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="2bc87-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bc87-144">Close the page.</span></span>
15. <span data-ttu-id="2bc87-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bc87-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="2bc87-146">Stimare l'ordine di produzione e visualizzare il kanban creato</span><span class="sxs-lookup"><span data-stu-id="2bc87-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="2bc87-147">Fare clic su Stima.</span><span class="sxs-lookup"><span data-stu-id="2bc87-147">Click Estimate.</span></span>
    * <span data-ttu-id="2bc87-148">La stima dell'ordine di produzione avvierà la creazione del kanban collegato per fornire l'articolo M0001.</span><span class="sxs-lookup"><span data-stu-id="2bc87-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="2bc87-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2bc87-149">Click OK.</span></span>
3. <span data-ttu-id="2bc87-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bc87-150">Close the page.</span></span>
4. <span data-ttu-id="2bc87-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bc87-151">Close the page.</span></span>
5. <span data-ttu-id="2bc87-152">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="2bc87-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="2bc87-153">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2bc87-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2bc87-154">Selezionare la regola kanban evento creata per l'articolo M0001.</span><span class="sxs-lookup"><span data-stu-id="2bc87-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="2bc87-155">Espandere la sezione Kanban.</span><span class="sxs-lookup"><span data-stu-id="2bc87-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="2bc87-156">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2bc87-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2bc87-157">Si noti il kanban creato per fornire M0001 per l'ordine di produzione stimato.</span><span class="sxs-lookup"><span data-stu-id="2bc87-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="2bc87-158">Questo è l'ultimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="2bc87-158">This is the last step!</span></span>  


