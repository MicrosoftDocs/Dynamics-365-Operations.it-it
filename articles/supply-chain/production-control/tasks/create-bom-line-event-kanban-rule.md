---
title: Creare una regola kanban eventi riga DBA
description: Questa attività mostra la configurazione necessaria per creare una regola kanban evento per garantire il rifornimento per le righe DBA di produzione in un ambiente di produzione misto lean e classico.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27d415e146f33224bcbbfb73498040d584e07f10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829212"
---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="5535b-103">Creare una regola kanban eventi riga DBA</span><span class="sxs-lookup"><span data-stu-id="5535b-103">Create a BOM line event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5535b-104">Questa attività mostra la configurazione necessaria per creare una regola kanban evento per garantire il rifornimento per le righe DBA di produzione in un ambiente di produzione misto lean e classico.</span><span class="sxs-lookup"><span data-stu-id="5535b-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="5535b-105">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="5535b-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="5535b-106">Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.</span><span class="sxs-lookup"><span data-stu-id="5535b-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="5535b-107">Crea una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="5535b-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="5535b-108">Andare a Controllo produzione > Attività periodiche > Calcolo quantità kanban > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="5535b-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="5535b-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5535b-109">Click New.</span></span>
3. <span data-ttu-id="5535b-110">Selezionare "Prelievo" nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="5535b-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="5535b-111">Il tipo Prelievo viene utilizzato per creare kanban di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="5535b-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="5535b-112">Nel campo Strategia di rifornimento, selezionare 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="5535b-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="5535b-113">La strategia di evento è selezionata per creare il trasferimento dei kanban in base a un evento.</span><span class="sxs-lookup"><span data-stu-id="5535b-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="5535b-114">Più avanti nella guida di attività verrà attivata con la stima di un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="5535b-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="5535b-115">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5535b-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="5535b-116">Immettere o selezionare ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="5535b-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="5535b-117">Questa attività di trasferimento ha magazzino e ubicazione di entrata (output) 12, pertanto il materiale verrà spostato in ubicazione 12 in magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="5535b-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="5535b-118">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="5535b-118">Expand the Details section.</span></span>
7. <span data-ttu-id="5535b-119">Nel campo Prodotto immettere o selezionare M0001.</span><span class="sxs-lookup"><span data-stu-id="5535b-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="5535b-120">Espandere la sezione Eventi.</span><span class="sxs-lookup"><span data-stu-id="5535b-120">Expand the Events section.</span></span>
9. <span data-ttu-id="5535b-121">Nel campo Evento riga DBA selezionare "Automatico".</span><span class="sxs-lookup"><span data-stu-id="5535b-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="5535b-122">Con il campo Evento riga DBA impostato su Automatico, il kanban verrà creato per soddisfare le esigenze di materiale delle righe DBA dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="5535b-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="5535b-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5535b-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="5535b-124">Creare e modificare un nuovo ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="5535b-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="5535b-125">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="5535b-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="5535b-126">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="5535b-126">Click New production order.</span></span>
3. <span data-ttu-id="5535b-127">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5535b-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="5535b-128">Immettere o selezionare "L0001".</span><span class="sxs-lookup"><span data-stu-id="5535b-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="5535b-129">Viene utilizzato l'articolo L0001 poiché l'articolo M0001 è incluso nella DBA per l'articolo L0001.</span><span class="sxs-lookup"><span data-stu-id="5535b-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="5535b-130">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="5535b-130">Click Create.</span></span>
5. <span data-ttu-id="5535b-131">Nell'elenco fare clic sul collegamento nella riga per L0001</span><span class="sxs-lookup"><span data-stu-id="5535b-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="5535b-132">Fare clic su DBA.</span><span class="sxs-lookup"><span data-stu-id="5535b-132">Click BOM.</span></span>
7. <span data-ttu-id="5535b-133">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5535b-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5535b-134">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="5535b-134">Click Edit.</span></span>
9. <span data-ttu-id="5535b-135">Nel campo Tipo di riga selezionare "Fornitura sottoposta a pegging".</span><span class="sxs-lookup"><span data-stu-id="5535b-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="5535b-136">La fornitura sottoposta a pegging è selezionata per avviare la creazione della fornitura di un kanban.</span><span class="sxs-lookup"><span data-stu-id="5535b-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="5535b-137">Selezionare No nel campo Consumo risorsa.</span><span class="sxs-lookup"><span data-stu-id="5535b-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="5535b-138">Deselezionando la casella di controllo Consumo risorsa è possibile modificare il magazzino.</span><span class="sxs-lookup"><span data-stu-id="5535b-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="5535b-139">Espandere la sezione Dimensioni inventariali.</span><span class="sxs-lookup"><span data-stu-id="5535b-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="5535b-140">Nel campo Magazzino digitare "12".</span><span class="sxs-lookup"><span data-stu-id="5535b-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="5535b-141">Il magazzino viene impostato su 12 poiché questo è il magazzino di output per l'attività di prelievo.</span><span class="sxs-lookup"><span data-stu-id="5535b-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="5535b-142">Nel campo Ubicazione digitare "12".</span><span class="sxs-lookup"><span data-stu-id="5535b-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="5535b-143">L'ubicazione viene impostata su 12 poiché questa è l'ubicazione di output per l'attività di prelievo.</span><span class="sxs-lookup"><span data-stu-id="5535b-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="5535b-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5535b-144">Close the page.</span></span>
15. <span data-ttu-id="5535b-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5535b-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="5535b-146">Stimare l'ordine di produzione e visualizzare il kanban creato</span><span class="sxs-lookup"><span data-stu-id="5535b-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="5535b-147">Fare clic su Stima.</span><span class="sxs-lookup"><span data-stu-id="5535b-147">Click Estimate.</span></span>
    * <span data-ttu-id="5535b-148">La stima dell'ordine di produzione avvierà la creazione del kanban collegato per fornire l'articolo M0001.</span><span class="sxs-lookup"><span data-stu-id="5535b-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="5535b-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5535b-149">Click OK.</span></span>
3. <span data-ttu-id="5535b-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5535b-150">Close the page.</span></span>
4. <span data-ttu-id="5535b-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5535b-151">Close the page.</span></span>
5. <span data-ttu-id="5535b-152">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="5535b-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="5535b-153">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5535b-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5535b-154">Selezionare la regola kanban evento creata per l'articolo M0001.</span><span class="sxs-lookup"><span data-stu-id="5535b-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="5535b-155">Espandere la sezione Kanban.</span><span class="sxs-lookup"><span data-stu-id="5535b-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="5535b-156">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5535b-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5535b-157">Si noti il kanban creato per fornire M0001 per l'ordine di produzione stimato.</span><span class="sxs-lookup"><span data-stu-id="5535b-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="5535b-158">Questo è l'ultimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="5535b-158">This is the last step!</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]