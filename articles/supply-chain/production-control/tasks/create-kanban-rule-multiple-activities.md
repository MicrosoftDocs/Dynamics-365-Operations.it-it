---
title: Creare una regola kanban per più attività
description: Questa procedura mostra come creare una regola kanban che comprende più attività da un flusso di produzione.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c25d47a78d1cc91ee2625ef628d7b9ba345b097
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977915"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="bd0f6-103">Creare una regola kanban per più attività</span><span class="sxs-lookup"><span data-stu-id="bd0f6-103">Create a kanban rule for multiple activities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd0f6-104">Questa procedura mostra come creare una regola kanban che comprende più attività da un flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="bd0f6-105">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="bd0f6-106">Questa attività è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato in un ambiente lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="bd0f6-107">Crea una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="bd0f6-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="bd0f6-108">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="bd0f6-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-109">Click New.</span></span>
3. <span data-ttu-id="bd0f6-110">Nel campo Strategia di rifornimento, selezionare 'Programmato'.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="bd0f6-111">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="bd0f6-112">Selezionare SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="bd0f6-113">Selezioni la casella di controllo Attività multiple.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="bd0f6-114">Lo scopo è includere più di una attività nella regola kanban.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="bd0f6-115">Scegliete un percorso nel flusso di produzione quando selezionate l'ultima attività di piano.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="bd0f6-116">Nel campo Ultima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="bd0f6-117">Selezionare SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="bd0f6-118">Dopo che selezionate il valore, una pagina si apre automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="bd0f6-119">Selezionare il flusso kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="bd0f6-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-120">Click OK.</span></span>  
7. <span data-ttu-id="bd0f6-121">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-121">Expand the Details section.</span></span>
8. <span data-ttu-id="bd0f6-122">Nel campo Prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="bd0f6-123">Selezionare l'articolo L0006.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="bd0f6-124">Creare e visualizzare processi kanban</span><span class="sxs-lookup"><span data-stu-id="bd0f6-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="bd0f6-125">Espandere la sezione Kanban.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="bd0f6-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-126">Click Add.</span></span>
3. <span data-ttu-id="bd0f6-127">Immettere '1' nel campo Numero di nuovi kanban.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="bd0f6-128">Ciò creerà un kanban.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="bd0f6-129">Impostare la quantità prodotto su "3".</span><span class="sxs-lookup"><span data-stu-id="bd0f6-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="bd0f6-130">Kanban elaborerà 3 prodotti.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="bd0f6-131">Nel campo Data/ora scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="bd0f6-132">È possibile immettere Oggi.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-132">You can enter Today.</span></span>  
6. <span data-ttu-id="bd0f6-133">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-133">Click Create.</span></span>
7. <span data-ttu-id="bd0f6-134">Fare clic su Dettagli.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-134">Click Details.</span></span>
    * <span data-ttu-id="bd0f6-135">Notare che il kanban ha due processi dal flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="bd0f6-136">Il primo è SpeakerAssemblyAndPolish e il secondo è SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="bd0f6-137">Questo è l'ultimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="bd0f6-137">This is the last step!</span></span>  

