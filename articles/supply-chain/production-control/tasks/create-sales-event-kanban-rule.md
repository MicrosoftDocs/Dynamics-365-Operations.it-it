---
title: Creare una regola kanban eventi di vendita
description: Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban che è attivata durante la creazione di un ordine cliente.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1759adea6db8120078e2f32bff79178545c2328a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430861"
---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="10ec8-103">Creare una regola kanban eventi di vendita</span><span class="sxs-lookup"><span data-stu-id="10ec8-103">Create a sales event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="10ec8-104">Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban che è attivata durante la creazione di un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="10ec8-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="10ec8-105">La regola kanban eventi soddisfa i requisiti che derivano dalle righe di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="10ec8-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="10ec8-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="10ec8-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="10ec8-107">Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.</span><span class="sxs-lookup"><span data-stu-id="10ec8-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="10ec8-108">Crea una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="10ec8-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="10ec8-109">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="10ec8-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="10ec8-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="10ec8-110">Click New.</span></span>
3. <span data-ttu-id="10ec8-111">Nel campo Strategia di rifornimento, selezionare 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="10ec8-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="10ec8-112">Selezionare un evento indica che la regola kanban è attivata da un evento, ad esempio, la creazione di una riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="10ec8-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="10ec8-113">Applicabile alle aree in cui ogni kanban deve coprire una richiesta specifica.</span><span class="sxs-lookup"><span data-stu-id="10ec8-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="10ec8-114">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="10ec8-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="10ec8-115">Selezionare Assembly finale.</span><span class="sxs-lookup"><span data-stu-id="10ec8-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="10ec8-116">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="10ec8-116">Expand the Details section.</span></span>
6. <span data-ttu-id="10ec8-117">Nel campo Prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="10ec8-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="10ec8-118">Selezionare L0050.</span><span class="sxs-lookup"><span data-stu-id="10ec8-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="10ec8-119">Definire un evento</span><span class="sxs-lookup"><span data-stu-id="10ec8-119">Define an event</span></span>
1. <span data-ttu-id="10ec8-120">Espandere la sezione Eventi.</span><span class="sxs-lookup"><span data-stu-id="10ec8-120">Expand the Events section.</span></span>
2. <span data-ttu-id="10ec8-121">Nel campo Evento vendite selezionare 'Automatico'.</span><span class="sxs-lookup"><span data-stu-id="10ec8-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="10ec8-122">Selezionando l'evento vendite Automatico, la regola kanban verrà attivata automaticamente quando una riga di vendita corrisponde al prodotto e all'ubicazione di entrata.</span><span class="sxs-lookup"><span data-stu-id="10ec8-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="10ec8-123">In questa procedura, si tratta del prodotto L0050 nel magazzino 13.</span><span class="sxs-lookup"><span data-stu-id="10ec8-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="10ec8-124">Impostare Quantità minima evento su '50'.</span><span class="sxs-lookup"><span data-stu-id="10ec8-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="10ec8-125">Con una quantità di evento minima di 50, la regola kanban verrà attivata solo gli eventi con una quantità di 50 o più.</span><span class="sxs-lookup"><span data-stu-id="10ec8-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="10ec8-126">Espandere la sezione Flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="10ec8-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="10ec8-127">Si noti che l'ubicazione di entrata è il magazzino 13.</span><span class="sxs-lookup"><span data-stu-id="10ec8-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="10ec8-128">Ciò significa che la regola kanban verrà attivata per questa ubicazione.</span><span class="sxs-lookup"><span data-stu-id="10ec8-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="10ec8-129">In questo esempio, una riga di vendita per il prodotto L0050, con una quantità di 50 o più, nel magazzino 13, attiverà questa regola kanban.</span><span class="sxs-lookup"><span data-stu-id="10ec8-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="10ec8-130">Creare la riga di vendita per attivare la regola kanban eventi</span><span class="sxs-lookup"><span data-stu-id="10ec8-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="10ec8-131">Fare clic su Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="10ec8-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="10ec8-132">Un avviso viene visualizzato quando la regola kanban viene salvata, pertanto i kanban verranno creati in tempo reale durante la creazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="10ec8-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="10ec8-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="10ec8-133">Click New.</span></span>
3. <span data-ttu-id="10ec8-134">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="10ec8-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="10ec8-135">Selezionare, ad esempio, US-003.</span><span class="sxs-lookup"><span data-stu-id="10ec8-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="10ec8-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="10ec8-136">Click OK.</span></span>
5. <span data-ttu-id="10ec8-137">Nel campo Numero articolo digitare "L0050".</span><span class="sxs-lookup"><span data-stu-id="10ec8-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="10ec8-138">Nel campo Sito digitare '1'.</span><span class="sxs-lookup"><span data-stu-id="10ec8-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="10ec8-139">Selezionare Sito 1 poiché il magazzino 13 si trova nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="10ec8-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="10ec8-140">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="10ec8-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="10ec8-141">Impostare Magazzino su 13.</span><span class="sxs-lookup"><span data-stu-id="10ec8-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="10ec8-142">Impostare la quantità su "75".</span><span class="sxs-lookup"><span data-stu-id="10ec8-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="10ec8-143">Impostare una quantità pari a 50 o maggiore per attivare la regola kanban creata.</span><span class="sxs-lookup"><span data-stu-id="10ec8-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="10ec8-144">Verificare che il kanban venga creato</span><span class="sxs-lookup"><span data-stu-id="10ec8-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="10ec8-145">Fare clic su Prodotto e fornitura.</span><span class="sxs-lookup"><span data-stu-id="10ec8-145">Click Product and supply.</span></span>
2. <span data-ttu-id="10ec8-146">Fare clic su Visualizza struttura di pegging.</span><span class="sxs-lookup"><span data-stu-id="10ec8-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="10ec8-147">Si noti che viene creato un kanban con la stessa quantità della riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="10ec8-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="10ec8-148">È inoltre possibile visualizzare le uscite materiali necessarie per la produzione di L0050.</span><span class="sxs-lookup"><span data-stu-id="10ec8-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="10ec8-149">Si tratta dell'ultimo passaggio di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="10ec8-149">This is the last step in this procedure.</span></span>  

