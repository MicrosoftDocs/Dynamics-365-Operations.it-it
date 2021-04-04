---
title: Creare una regola kanban tramite un evento riga kanban
description: Questa procedura crea una regola kanban usando l'impostazione di evento riga kanban che attiva il pull da un'attività di processo.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc838a64e74b561dd17fd2b568fa8c190a1dfcfe
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255207"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a><span data-ttu-id="69dc2-103">Creare una regola kanban tramite un evento riga kanban</span><span class="sxs-lookup"><span data-stu-id="69dc2-103">Create a kanban rule using a kanban line event</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69dc2-104">Questa procedura crea una regola kanban usando l'impostazione di evento riga kanban che attiva il pull da un'attività di processo.</span><span class="sxs-lookup"><span data-stu-id="69dc2-104">This procedure creates a kanban rule by using the kanban line event setting to trigger pull from a process activity.</span></span> <span data-ttu-id="69dc2-105">La regola kanban è attivata da un'attività di processo kanban, con una quantità uguale o maggiore di 25 ciascuna.</span><span class="sxs-lookup"><span data-stu-id="69dc2-105">The kanban rule is triggered by a kanban process activity, with a quantity equal to or greater than 25 each.</span></span> <span data-ttu-id="69dc2-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="69dc2-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="69dc2-107">Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato in un ambiente lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="69dc2-107">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-kanban-rule"></a><span data-ttu-id="69dc2-108">Creare una regola kanban</span><span class="sxs-lookup"><span data-stu-id="69dc2-108">Create a kanban rule</span></span>
1. <span data-ttu-id="69dc2-109">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="69dc2-109">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="69dc2-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="69dc2-110">Click New.</span></span>
3. <span data-ttu-id="69dc2-111">Nel campo Strategia di rifornimento, selezionare 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="69dc2-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="69dc2-112">Con questa azione i kanban vengono generati direttamente a partire dalla domanda.</span><span class="sxs-lookup"><span data-stu-id="69dc2-112">This generates kanbans directly from demand.</span></span> <span data-ttu-id="69dc2-113">Viene utilizzata per impostare le regole che definiscono uno scenario di produzione su ordine.</span><span class="sxs-lookup"><span data-stu-id="69dc2-113">It is used to set up rules that define a make-to-order scenario.</span></span>  
4. <span data-ttu-id="69dc2-114">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="69dc2-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="69dc2-115">Immettere o selezionare SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="69dc2-115">Enter or select SpeakerAssemblyAndPolish.</span></span> <span data-ttu-id="69dc2-116">La prima attività di una regola kanban di produzione è essere un'attività di processo nel flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="69dc2-116">The first activity of a manufacturing kanban rule is a process activity in the production flow.</span></span> <span data-ttu-id="69dc2-117">Quando si seleziona l'attività, le date di validità di quest'ultima vengono copiate nelle date di validità della regola kanban.</span><span class="sxs-lookup"><span data-stu-id="69dc2-117">When you select the activity, the validity dates of the activity are copied to the validity dates of the kanban rule.</span></span>  
5. <span data-ttu-id="69dc2-118">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="69dc2-118">Expand the Details section.</span></span>
6. <span data-ttu-id="69dc2-119">Nel campo Prodotto digitare 'L0001'.</span><span class="sxs-lookup"><span data-stu-id="69dc2-119">In the Product field, type 'L0001'.</span></span>
7. <span data-ttu-id="69dc2-120">Espandere la sezione Eventi.</span><span class="sxs-lookup"><span data-stu-id="69dc2-120">Expand the Events section.</span></span>
8. <span data-ttu-id="69dc2-121">Nel campo Evento riga Kanban selezionare 'Automatico'.</span><span class="sxs-lookup"><span data-stu-id="69dc2-121">In the Kanban line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="69dc2-122">Ciò genera i kanban di evento su richiesta.</span><span class="sxs-lookup"><span data-stu-id="69dc2-122">This generates event kanbans on demand.</span></span>  <span data-ttu-id="69dc2-123">Il campo viene usato per configurare le regole kanban per il rifornimento di materiale richiesto per un'attività di processo downstream.</span><span class="sxs-lookup"><span data-stu-id="69dc2-123">The field is used to configure kanban rules that replenish material that is required for a downstream process activity.</span></span> <span data-ttu-id="69dc2-124">Quando si seleziona Automatico, i kanban di evento vengono creati con la domanda.</span><span class="sxs-lookup"><span data-stu-id="69dc2-124">When you select Automatic, the event kanbans are created with the demand.</span></span> <span data-ttu-id="69dc2-125">Questa impostazione è consigliata se si prevede di eseguire la produzione lo stesso giorno.</span><span class="sxs-lookup"><span data-stu-id="69dc2-125">This setting is recommended if you expect to execute production on the same day.</span></span>  
9. <span data-ttu-id="69dc2-126">Impostare Quantità minima evento su '25'.</span><span class="sxs-lookup"><span data-stu-id="69dc2-126">Set Minimum event quantity to '25'.</span></span>
    * <span data-ttu-id="69dc2-127">Vengono generati kanban evento quando la quantità di domanda è uguale o superiore al valore di questo campo.</span><span class="sxs-lookup"><span data-stu-id="69dc2-127">Event kanbans are generated when the demand quantity is equal to or more than this field.</span></span> <span data-ttu-id="69dc2-128">Ciò è utile se volete produrre una quantità di ordine minore di questo campo su una macchina e maggiore di questo campo su un'altra macchina.</span><span class="sxs-lookup"><span data-stu-id="69dc2-128">This is useful if you want to produce an order quantity less than this field on one machine and more than this field on another machine.</span></span>  
10. <span data-ttu-id="69dc2-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="69dc2-129">Click Save.</span></span>

## <a name="create-sales-order-and-trigger-kanban-chain"></a><span data-ttu-id="69dc2-130">Creare l'ordine cliente e attivare la catena kanban</span><span class="sxs-lookup"><span data-stu-id="69dc2-130">Create sales order and trigger kanban chain</span></span>
1. <span data-ttu-id="69dc2-131">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="69dc2-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="69dc2-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="69dc2-132">Click New.</span></span>
3. <span data-ttu-id="69dc2-133">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="69dc2-133">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="69dc2-134">Selezionare il conto cliente US-003, Forest Wholesales.</span><span class="sxs-lookup"><span data-stu-id="69dc2-134">Select Customer account US-003, Forest Wholesales.</span></span>  
4. <span data-ttu-id="69dc2-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="69dc2-135">Click OK.</span></span>
5. <span data-ttu-id="69dc2-136">Nel campo Numero articolo digitare "L0001".</span><span class="sxs-lookup"><span data-stu-id="69dc2-136">In the Item number field, type 'L0001'.</span></span>
    * <span data-ttu-id="69dc2-137">L0001 è l'articolo per cui viene creata la regola kanban.</span><span class="sxs-lookup"><span data-stu-id="69dc2-137">L0001 is the item for which you created the kanban rule.</span></span>  
6. <span data-ttu-id="69dc2-138">Impostare la quantità su "27".</span><span class="sxs-lookup"><span data-stu-id="69dc2-138">Set Quantity to '27'.</span></span>
    * <span data-ttu-id="69dc2-139">Poiché 27 è maggiore della quantità minima di 25 nella regola kanban, ciò attiverà kanban evento.</span><span class="sxs-lookup"><span data-stu-id="69dc2-139">Because 27 is higher than the minimum quantity of 25 on the kanban rule, this will trigger an event kanban.</span></span>  
7. <span data-ttu-id="69dc2-140">Nel campo Sito digitare '1'.</span><span class="sxs-lookup"><span data-stu-id="69dc2-140">In the Site field, type '1'.</span></span>
8. <span data-ttu-id="69dc2-141">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="69dc2-141">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="69dc2-142">Selezionare magazzino 13.</span><span class="sxs-lookup"><span data-stu-id="69dc2-142">Select warehouse 13.</span></span>  
9. <span data-ttu-id="69dc2-143">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="69dc2-143">Click Save.</span></span>

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a><span data-ttu-id="69dc2-144">Visualizzare il kanban generato dalla regola kanban</span><span class="sxs-lookup"><span data-stu-id="69dc2-144">View the kanban generated by the kanban rule</span></span>
1. <span data-ttu-id="69dc2-145">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="69dc2-145">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="69dc2-146">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="69dc2-146">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="69dc2-147">Espandere la sezione Kanban.</span><span class="sxs-lookup"><span data-stu-id="69dc2-147">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="69dc2-148">Notare che un kanban per 27 è stato creato per elaborare l'attività basata sulla regola kanban creata.</span><span class="sxs-lookup"><span data-stu-id="69dc2-148">Notice that a kanban for 27 was created to process the  activity based on the created kanban rule.</span></span>  
    * <span data-ttu-id="69dc2-149">Questo è l'ultimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="69dc2-149">This is the last step.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]