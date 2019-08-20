---
title: Creare una regola kanban tramite un evento scorte minime
description: Questa procedura si concentra sulla configurazione necessaria per creare una regola kanban facendo uso di un evento di scorte minime per assicurarsi che un prodotto specifico sia sempre disponibile in una ubicazione specifica.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b578a664e9e3b6496e5665b2eefd9d75f86ecc3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837832"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a><span data-ttu-id="621f2-103">Creare una regola kanban tramite un evento scorte minime</span><span class="sxs-lookup"><span data-stu-id="621f2-103">Create a kanban rule using a minimum stock event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="621f2-104">Questa procedura si concentra sulla configurazione necessaria per creare una regola kanban facendo uso di un evento di scorte minime per assicurarsi che un prodotto specifico sia sempre disponibile in una ubicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="621f2-104">This procedure focuses on the setup needed to create a kanban rule using a minimum stock event to ensure that a specific product is always available at a specific location.</span></span> <span data-ttu-id="621f2-105">Una regola kanban è creata per trasferire il materiale all'ubicazione quando il livello delle scorte scende sotto 200 pezzi.</span><span class="sxs-lookup"><span data-stu-id="621f2-105">A kanban rule is created to transfer material to the location when the inventory level drops below 200 pieces.</span></span> <span data-ttu-id="621f2-106">Eseguendo l'elaborazione dell'evento di pegging, i kanbans necessari vengono creati.</span><span class="sxs-lookup"><span data-stu-id="621f2-106">By running the Pegging event processing, the needed kanbans are created.</span></span> <span data-ttu-id="621f2-107">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="621f2-107">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="621f2-108">Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato in un ambiente lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="621f2-108">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="621f2-109">Crea una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="621f2-109">Create a new kanban rule</span></span>
1. <span data-ttu-id="621f2-110">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="621f2-110">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="621f2-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="621f2-111">Click New.</span></span>
3. <span data-ttu-id="621f2-112">Selezionare "Prelievo" nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="621f2-112">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="621f2-113">Questo tipo viene utilizzato per creare kanban di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="621f2-113">This type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="621f2-114">Nel campo Strategia di rifornimento, selezionare 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="621f2-114">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="621f2-115">La strategia di evento è utilizzata per creare i kanban di trasferimento basati su un evento.</span><span class="sxs-lookup"><span data-stu-id="621f2-115">The Event strategy is used to create the transfer kanbans based on an event.</span></span> <span data-ttu-id="621f2-116">Successivamente nella procedura, si attiveranno i kanban di trasferimento usando il rifornimento scorte.</span><span class="sxs-lookup"><span data-stu-id="621f2-116">Later in the procedure, you will trigger transfer kanbans by using stock replenishment.</span></span>  
5. <span data-ttu-id="621f2-117">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="621f2-117">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="621f2-118">Immettere o selezionare ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="621f2-118">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="621f2-119">Questa attività di trasferimento ha magazzino e ubicazione di entrata (output) 12, pertanto il materiale verrà spostato in ubicazione 12 in magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="621f2-119">This transfer activity has receipt (output) warehouse and location 12, which means that materials will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="621f2-120">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="621f2-120">Expand the Details section.</span></span>
7. <span data-ttu-id="621f2-121">Nel campo Prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="621f2-121">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="621f2-122">Selezionare M0007.</span><span class="sxs-lookup"><span data-stu-id="621f2-122">Select M0007.</span></span>  
8. <span data-ttu-id="621f2-123">Espandere la sezione Eventi.</span><span class="sxs-lookup"><span data-stu-id="621f2-123">Expand the Events section.</span></span>
9. <span data-ttu-id="621f2-124">Nel campo Evento rifornimento scorte, selezionare 'Batch'.</span><span class="sxs-lookup"><span data-stu-id="621f2-124">In the Stock replenishment event field, select 'Batch'.</span></span>
    * <span data-ttu-id="621f2-125">Ciò crea i kanban per soddisfare il fabbisogno di materiali all'ubicazione correlata durante l'elaborazione dell'evento di pegging.</span><span class="sxs-lookup"><span data-stu-id="621f2-125">This creates kanbans to fulfill material needs at the related location during Pegging event processing.</span></span>  

## <a name="set-the-minimum-quantity-for-the-item"></a><span data-ttu-id="621f2-126">Impostare la quantità minima per l'articolo</span><span class="sxs-lookup"><span data-stu-id="621f2-126">Set the minimum quantity for the item</span></span>
1. <span data-ttu-id="621f2-127">Fare clic per seguire il collegamento nel campo Prodotto.</span><span class="sxs-lookup"><span data-stu-id="621f2-127">Click to follow the link in the Product field.</span></span>
2. <span data-ttu-id="621f2-128">Fare clic per seguire il collegamento nel campo Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="621f2-128">Click to follow the link in the Item number field.</span></span>
3. <span data-ttu-id="621f2-129">Espandere il Dettaglio informazioni Immagine prodotto.</span><span class="sxs-lookup"><span data-stu-id="621f2-129">Expand the Product image FactBox.</span></span>
4. <span data-ttu-id="621f2-130">Nel riquadro azioni fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="621f2-130">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="621f2-131">Fare clic su Copertura articoli.</span><span class="sxs-lookup"><span data-stu-id="621f2-131">Click Item coverage.</span></span>
6. <span data-ttu-id="621f2-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="621f2-132">Click New.</span></span>
7. <span data-ttu-id="621f2-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="621f2-133">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="621f2-134">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="621f2-134">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="621f2-135">Impostare Magazzino su 12.</span><span class="sxs-lookup"><span data-stu-id="621f2-135">Set Warehouse to 12.</span></span>  
9. <span data-ttu-id="621f2-136">Impostare il minimo su '200'.</span><span class="sxs-lookup"><span data-stu-id="621f2-136">Set Minimum to '200'.</span></span>

## <a name="run-the-batch-event-creation-job"></a><span data-ttu-id="621f2-137">Eseguire il processo di creazione evento batch</span><span class="sxs-lookup"><span data-stu-id="621f2-137">Run the batch event creation job</span></span>
1. <span data-ttu-id="621f2-138">Andare a Controllo produzione > Attività periodiche > Elaborazione batch processo kanban > Elaborazione evento di pegging.</span><span class="sxs-lookup"><span data-stu-id="621f2-138">Go to Production control > Periodic tasks > Kanban job batch processing > Pegging event processing.</span></span>
2. <span data-ttu-id="621f2-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="621f2-139">Click OK.</span></span>
3. <span data-ttu-id="621f2-140">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="621f2-140">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
4. <span data-ttu-id="621f2-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="621f2-141">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="621f2-142">Selezionare la regola kanban creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="621f2-142">Select the kanban rule that you created earlier.</span></span>  
5. <span data-ttu-id="621f2-143">Espandere la sezione Kanban.</span><span class="sxs-lookup"><span data-stu-id="621f2-143">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="621f2-144">Notare che un kanban è stato creato per trasferire il materiale necessario per il magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="621f2-144">Notice that a kanban was created to transfer the needed material to warehouse 12.</span></span>  

