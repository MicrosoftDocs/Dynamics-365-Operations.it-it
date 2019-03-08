---
title: Creare una regola kanban eventi di vendita
description: Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban che è attivata durante la creazione di un ordine cliente.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2bee6e81acd029406c95237f0b4ba4ab2565ea1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "342019"
---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="3571c-103">Creare una regola kanban eventi di vendita</span><span class="sxs-lookup"><span data-stu-id="3571c-103">Create a sales event kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3571c-104">Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban che è attivata durante la creazione di un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3571c-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="3571c-105">La regola kanban eventi soddisfa i requisiti che derivano dalle righe di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3571c-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="3571c-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="3571c-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3571c-107">Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.</span><span class="sxs-lookup"><span data-stu-id="3571c-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="3571c-108">Crea una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="3571c-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="3571c-109">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="3571c-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="3571c-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3571c-110">Click New.</span></span>
3. <span data-ttu-id="3571c-111">Nel campo Strategia di rifornimento, selezionare 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="3571c-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="3571c-112">Selezionare un evento indica che la regola kanban è attivata da un evento, ad esempio, la creazione di una riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3571c-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="3571c-113">Applicabile alle aree in cui ogni kanban deve coprire una richiesta specifica.</span><span class="sxs-lookup"><span data-stu-id="3571c-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="3571c-114">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3571c-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="3571c-115">Selezionare Assembly finale.</span><span class="sxs-lookup"><span data-stu-id="3571c-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="3571c-116">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="3571c-116">Expand the Details section.</span></span>
6. <span data-ttu-id="3571c-117">Nel campo Prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3571c-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="3571c-118">Selezionare L0050.</span><span class="sxs-lookup"><span data-stu-id="3571c-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="3571c-119">Definire un evento</span><span class="sxs-lookup"><span data-stu-id="3571c-119">Define an event</span></span>
1. <span data-ttu-id="3571c-120">Espandere la sezione Eventi.</span><span class="sxs-lookup"><span data-stu-id="3571c-120">Expand the Events section.</span></span>
2. <span data-ttu-id="3571c-121">Nel campo Evento vendite selezionare 'Automatico'.</span><span class="sxs-lookup"><span data-stu-id="3571c-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="3571c-122">Selezionando l'evento vendite Automatico, la regola kanban verrà attivata automaticamente quando una riga di vendita corrisponde al prodotto e all'ubicazione di entrata.</span><span class="sxs-lookup"><span data-stu-id="3571c-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="3571c-123">In questa procedura, si tratta del prodotto L0050 nel magazzino 13.</span><span class="sxs-lookup"><span data-stu-id="3571c-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="3571c-124">Impostare Quantità minima evento su '50'.</span><span class="sxs-lookup"><span data-stu-id="3571c-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="3571c-125">Con una quantità di evento minima di 50, la regola kanban verrà attivata solo gli eventi con una quantità di 50 o più.</span><span class="sxs-lookup"><span data-stu-id="3571c-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="3571c-126">Espandere la sezione Flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="3571c-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="3571c-127">Si noti che l'ubicazione di entrata è il magazzino 13.</span><span class="sxs-lookup"><span data-stu-id="3571c-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="3571c-128">Ciò significa che la regola kanban verrà attivata per questa ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3571c-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="3571c-129">In questo esempio, una riga di vendita per il prodotto L0050, con una quantità di 50 o più, nel magazzino 13, attiverà questa regola kanban.</span><span class="sxs-lookup"><span data-stu-id="3571c-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="3571c-130">Creare la riga di vendita per attivare la regola kanban eventi</span><span class="sxs-lookup"><span data-stu-id="3571c-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="3571c-131">Fare clic su Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="3571c-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="3571c-132">Un avviso viene visualizzato quando la regola kanban viene salvata, pertanto i kanban verranno creati in tempo reale durante la creazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3571c-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="3571c-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3571c-133">Click New.</span></span>
3. <span data-ttu-id="3571c-134">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3571c-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="3571c-135">Selezionare, ad esempio, US-003.</span><span class="sxs-lookup"><span data-stu-id="3571c-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="3571c-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3571c-136">Click OK.</span></span>
5. <span data-ttu-id="3571c-137">Nel campo Numero articolo digitare "L0050".</span><span class="sxs-lookup"><span data-stu-id="3571c-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="3571c-138">Nel campo Sito digitare '1'.</span><span class="sxs-lookup"><span data-stu-id="3571c-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="3571c-139">Selezionare Sito 1 poiché il magazzino 13 si trova nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="3571c-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="3571c-140">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3571c-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="3571c-141">Impostare Magazzino su 13.</span><span class="sxs-lookup"><span data-stu-id="3571c-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="3571c-142">Impostare la quantità su "75".</span><span class="sxs-lookup"><span data-stu-id="3571c-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="3571c-143">Impostare una quantità pari a 50 o maggiore per attivare la regola kanban creata.</span><span class="sxs-lookup"><span data-stu-id="3571c-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="3571c-144">Verificare che il kanban venga creato</span><span class="sxs-lookup"><span data-stu-id="3571c-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="3571c-145">Fare clic su Prodotto e fornitura.</span><span class="sxs-lookup"><span data-stu-id="3571c-145">Click Product and supply.</span></span>
2. <span data-ttu-id="3571c-146">Fare clic su Visualizza struttura di pegging.</span><span class="sxs-lookup"><span data-stu-id="3571c-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="3571c-147">Si noti che viene creato un kanban con la stessa quantità della riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="3571c-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="3571c-148">È inoltre possibile visualizzare le uscite materiali necessarie per la produzione di L0050.</span><span class="sxs-lookup"><span data-stu-id="3571c-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="3571c-149">Si tratta dell'ultimo passaggio di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="3571c-149">This is the last step in this procedure.</span></span>  

