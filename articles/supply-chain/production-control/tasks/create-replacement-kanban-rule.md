--- 
title: Creare una regola kanban di sostituzione
description: Questa procedura mostra come sostituire la regola kanban esistente con una nuova regola kanban in una data specifica.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 12df41f14973628063b11f20f7368f47b2ad3488
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="14be8-103">Creare una regola kanban di sostituzione</span><span class="sxs-lookup"><span data-stu-id="14be8-103">Create a replacement kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="14be8-104">Questa procedura mostra come sostituire la regola kanban esistente con una nuova regola kanban in una data specifica.</span><span class="sxs-lookup"><span data-stu-id="14be8-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="14be8-105">Questa opzione è utile quando le modifiche al flusso di produzione o alle regole di rifornimento devono essere coordinate e programmate.</span><span class="sxs-lookup"><span data-stu-id="14be8-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="14be8-106">La società di dati dimostrativi utilizzata per creare la procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="14be8-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="14be8-107">Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore quando prepara la produzione di un flusso di produzione modificato o una nuova regola di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="14be8-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="14be8-108">Questa attività sostituisce la regola kanban 000022 con una nuova regola e aumenta la quantità massima da 48 a 100 per la nuova regola.</span><span class="sxs-lookup"><span data-stu-id="14be8-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="14be8-109">Selezionare una regola kanban da sostituire.</span><span class="sxs-lookup"><span data-stu-id="14be8-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="14be8-110">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="14be8-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="14be8-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="14be8-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="14be8-112">Selezionare una regola kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="14be8-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="14be8-113">Creare una regola kanban di sostituzione</span><span class="sxs-lookup"><span data-stu-id="14be8-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="14be8-114">Fare clic su Sostituisci regola kanban.</span><span class="sxs-lookup"><span data-stu-id="14be8-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="14be8-115">Nel campo Data di validità immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="14be8-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="14be8-116">Selezionare una data futura, ad esempio una settimana da oggi.</span><span class="sxs-lookup"><span data-stu-id="14be8-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="14be8-117">È la data e l'ora in cui la nuova regola kanban diventa attiva e sostituisce la regola kanban vecchia.</span><span class="sxs-lookup"><span data-stu-id="14be8-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="14be8-118">Se la regola kanban modifica il percorso del flusso di produzione, un'altra attività può essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="14be8-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="14be8-119">In questa procedura l'attività non verrà toccata.</span><span class="sxs-lookup"><span data-stu-id="14be8-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="14be8-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="14be8-120">Click OK.</span></span>
    * <span data-ttu-id="14be8-121">Viene creata una nuova regola kanban per sostituire la regola kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="14be8-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="14be8-122">La data di validità viene impostata in base alla data scelta quando si sostituisce la regola kanban.</span><span class="sxs-lookup"><span data-stu-id="14be8-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="14be8-123">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="14be8-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="14be8-124">Selezionare la regola kanban 000022 sostituita.</span><span class="sxs-lookup"><span data-stu-id="14be8-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="14be8-125">La regola kanban sostituita ha la stessa data della data di scadenza poiché questa è la data in cui scadrà.</span><span class="sxs-lookup"><span data-stu-id="14be8-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="14be8-126">Nell'elenco selezionare la riga 1.</span><span class="sxs-lookup"><span data-stu-id="14be8-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="14be8-127">Selezionare la nuova regola kanban in cima all'elenco.</span><span class="sxs-lookup"><span data-stu-id="14be8-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="14be8-128">Si tratta della regola kanban con il numero più elevato.</span><span class="sxs-lookup"><span data-stu-id="14be8-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="14be8-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="14be8-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="14be8-130">Fare clic sul numero della regola kanban per aprire la regola.</span><span class="sxs-lookup"><span data-stu-id="14be8-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="14be8-131">Modificare la quantità massima per la regola kanban sostitutiva</span><span class="sxs-lookup"><span data-stu-id="14be8-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="14be8-132">Impostare Quantità massima su "100".</span><span class="sxs-lookup"><span data-stu-id="14be8-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="14be8-133">Espandere la scheda dettaglio Quantità per visualizzare il campo Quantità massima.</span><span class="sxs-lookup"><span data-stu-id="14be8-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="14be8-134">Modificare la quantità massima in 100 permetterà l'elaborazione di un massimo di 100 kanban.</span><span class="sxs-lookup"><span data-stu-id="14be8-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="14be8-135">Questo è l'ultimo passaggio di questa attività.</span><span class="sxs-lookup"><span data-stu-id="14be8-135">This is the last step in this task.</span></span>  


