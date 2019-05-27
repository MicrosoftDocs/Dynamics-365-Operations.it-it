---
title: Impostare un modello di lavoro per gli ordini fornitore
description: La procedura si basa sull'impostazione di un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d737f9dfd1888602266a87853e54407618ae2781
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558321"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="43ffe-103">Impostare un modello di lavoro per gli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="43ffe-103">Set up a work template for purchase orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="43ffe-104">La procedura si basa sull'impostazione di un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti.</span><span class="sxs-lookup"><span data-stu-id="43ffe-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="43ffe-105">I modelli di lavoro determinano il set di istruzioni presentate all'addetto del magazzino in un dispositivo mobile quando si spostano gli articoli dall'area di ricevimento.</span><span class="sxs-lookup"><span data-stu-id="43ffe-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="43ffe-106">È possibile utilizzare questa procedura con i dati indicati nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="43ffe-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="43ffe-107">Prima di iniziare questa guida, creare un ID pool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43ffe-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="43ffe-108">In questo esempio, viene utilizzato un ID pool di lavoro denominato Inbound.</span><span class="sxs-lookup"><span data-stu-id="43ffe-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="43ffe-109">Questa procedura è destinata al responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="43ffe-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="43ffe-110">Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43ffe-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="43ffe-111">Nel campo Tipo ordine di lavoro selezionare "Ordini fornitori".</span><span class="sxs-lookup"><span data-stu-id="43ffe-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="43ffe-112">Creare un'intestazione del modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="43ffe-112">Create a work template header</span></span>
1. <span data-ttu-id="43ffe-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="43ffe-113">Click New.</span></span>
2. <span data-ttu-id="43ffe-114">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="43ffe-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="43ffe-115">È la sequenza secondo cui vengono valutati i modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43ffe-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="43ffe-116">Se necessario, è possibile modificare la sequenza.</span><span class="sxs-lookup"><span data-stu-id="43ffe-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="43ffe-117">Digitare un valore nel campo Modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43ffe-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="43ffe-118">Identificatore univoco per il modello.</span><span class="sxs-lookup"><span data-stu-id="43ffe-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="43ffe-119">Nel campo Descrizione modello di lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="43ffe-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="43ffe-120">L'opzione Valido non viene selezionata finché non saranno state completate tutte le informazioni necessarie per il modello e non si sarà fatto clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43ffe-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="43ffe-121">Un ordine di tipo ordine acquisto non può essere elaborato automaticamente, quindi lasciare l'opzione Elabora automaticamente impostata su no.</span><span class="sxs-lookup"><span data-stu-id="43ffe-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="43ffe-122">Nel campo ID pool lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="43ffe-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="43ffe-123">Gli ID pool di lavoro consentono di organizzare il lavoro in gruppi.</span><span class="sxs-lookup"><span data-stu-id="43ffe-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="43ffe-124">Il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.</span><span class="sxs-lookup"><span data-stu-id="43ffe-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="43ffe-125">Nel campo Priorità lavoro, immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="43ffe-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="43ffe-126">Indica il livello di importanza del lavoro e il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.</span><span class="sxs-lookup"><span data-stu-id="43ffe-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="43ffe-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43ffe-127">Click Save.</span></span>
    * <span data-ttu-id="43ffe-128">È necessario salvare l'intestazione del modello di lavoro per rendere disponibile il pulsante Modifica query.</span><span class="sxs-lookup"><span data-stu-id="43ffe-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="43ffe-129">Configurare la query per il modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="43ffe-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="43ffe-130">Fare clic su Modifica query.</span><span class="sxs-lookup"><span data-stu-id="43ffe-130">Click Edit query.</span></span>
    * <span data-ttu-id="43ffe-131">Verrà impostato un limite in modo che il modello possa essere utilizzato solo all'interno di un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="43ffe-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="43ffe-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="43ffe-132">Click Add.</span></span>
3. <span data-ttu-id="43ffe-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="43ffe-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="43ffe-134">Nel campo Campo, digitare 'warehouse'.</span><span class="sxs-lookup"><span data-stu-id="43ffe-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="43ffe-135">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="43ffe-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="43ffe-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="43ffe-136">Click OK.</span></span>
7. <span data-ttu-id="43ffe-137">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="43ffe-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="43ffe-138">Impostare i dettagli del modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="43ffe-138">Set work template details</span></span>
1. <span data-ttu-id="43ffe-139">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="43ffe-139">Click New.</span></span>
2. <span data-ttu-id="43ffe-140">Nel campo Tipo di lavoro, selezionare 'Preleva'.</span><span class="sxs-lookup"><span data-stu-id="43ffe-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="43ffe-141">Nel campo ID classe lavoro, digitare 'acquisto'.</span><span class="sxs-lookup"><span data-stu-id="43ffe-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="43ffe-142">La classe di lavoro impostata in questo campo sarà l'impostazione predefinita in tutte le righe di lavoro di tipo prelievo create tramite questo modello.</span><span class="sxs-lookup"><span data-stu-id="43ffe-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="43ffe-143">La classe di lavoro non può essere sostituita dalle righe ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43ffe-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="43ffe-144">Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che un addetto al magazzino può elaborare in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="43ffe-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="43ffe-145">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="43ffe-145">Click New.</span></span>
5. <span data-ttu-id="43ffe-146">Nel campo Tipo di lavoro selezionare "Inserisci".</span><span class="sxs-lookup"><span data-stu-id="43ffe-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="43ffe-147">Nel campo ID classe, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="43ffe-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="43ffe-148">Le istruzioni di prelievo e stoccaggio costituiscono un set.</span><span class="sxs-lookup"><span data-stu-id="43ffe-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="43ffe-149">Ogni set di prelievo/stoccaggio deve avere la stessa classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43ffe-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="43ffe-150">Utilizzare la stessa classe di lavoro fornita per l'istruzione di prelievo.</span><span class="sxs-lookup"><span data-stu-id="43ffe-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="43ffe-151">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43ffe-151">Click Save.</span></span>
    * <span data-ttu-id="43ffe-152">Si noti che la casella di controllo Valido ora è selezionata.</span><span class="sxs-lookup"><span data-stu-id="43ffe-152">Note that the Valid checkbox is now checked.</span></span>  

