--- 
title: Impostare un modello di lavoro per gli ordini fornitore
description: La procedura si basa sull'impostazione di un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti.
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fbbe019bdca2d5182466a20370418a14032fe63d
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="c20ac-103">Impostare un modello di lavoro per gli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="c20ac-103">Set up a work template for purchase orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c20ac-104">La procedura si basa sull'impostazione di un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti.</span><span class="sxs-lookup"><span data-stu-id="c20ac-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="c20ac-105">I modelli di lavoro determinano il set di istruzioni presentate all'addetto del magazzino in un dispositivo mobile quando si spostano gli articoli dall'area di ricevimento.</span><span class="sxs-lookup"><span data-stu-id="c20ac-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="c20ac-106">È possibile utilizzare questa procedura con i dati indicati nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="c20ac-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="c20ac-107">Prima di iniziare questa guida, creare un ID pool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c20ac-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="c20ac-108">In questo esempio, viene utilizzato un ID pool di lavoro denominato Inbound.</span><span class="sxs-lookup"><span data-stu-id="c20ac-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="c20ac-109">Questa procedura è destinata al responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="c20ac-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="c20ac-110">Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c20ac-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="c20ac-111">Nel campo Tipo ordine di lavoro selezionare "Ordini fornitori".</span><span class="sxs-lookup"><span data-stu-id="c20ac-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="c20ac-112">Creare un'intestazione del modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="c20ac-112">Create a work template header</span></span>
1. <span data-ttu-id="c20ac-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c20ac-113">Click New.</span></span>
2. <span data-ttu-id="c20ac-114">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="c20ac-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="c20ac-115">È la sequenza secondo cui vengono valutati i modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c20ac-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="c20ac-116">Se necessario, è possibile modificare la sequenza.</span><span class="sxs-lookup"><span data-stu-id="c20ac-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="c20ac-117">Digitare un valore nel campo Modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c20ac-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="c20ac-118">Identificatore univoco per il modello.</span><span class="sxs-lookup"><span data-stu-id="c20ac-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="c20ac-119">Nel campo Descrizione modello di lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="c20ac-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="c20ac-120">L'opzione Valido non viene selezionata finché non saranno state completate tutte le informazioni necessarie per il modello e non si sarà fatto clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c20ac-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="c20ac-121">Un ordine di tipo ordine acquisto non può essere elaborato automaticamente, quindi lasciare l'opzione Elabora automaticamente impostata su no.</span><span class="sxs-lookup"><span data-stu-id="c20ac-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="c20ac-122">Nel campo ID pool lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="c20ac-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="c20ac-123">Gli ID pool di lavoro consentono di organizzare il lavoro in gruppi.</span><span class="sxs-lookup"><span data-stu-id="c20ac-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="c20ac-124">Il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.</span><span class="sxs-lookup"><span data-stu-id="c20ac-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="c20ac-125">Nel campo Priorità lavoro, immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="c20ac-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="c20ac-126">Indica il livello di importanza del lavoro e il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.</span><span class="sxs-lookup"><span data-stu-id="c20ac-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="c20ac-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c20ac-127">Click Save.</span></span>
    * <span data-ttu-id="c20ac-128">È necessario salvare l'intestazione del modello di lavoro per rendere disponibile il pulsante Modifica query.</span><span class="sxs-lookup"><span data-stu-id="c20ac-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="c20ac-129">Configurare la query per il modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="c20ac-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="c20ac-130">Fare clic su Modifica query.</span><span class="sxs-lookup"><span data-stu-id="c20ac-130">Click Edit query.</span></span>
    * <span data-ttu-id="c20ac-131">Verrà impostato un limite in modo che il modello possa essere utilizzato solo all'interno di un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="c20ac-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="c20ac-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c20ac-132">Click Add.</span></span>
3. <span data-ttu-id="c20ac-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c20ac-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c20ac-134">Nel campo Campo, digitare 'warehouse'.</span><span class="sxs-lookup"><span data-stu-id="c20ac-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="c20ac-135">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="c20ac-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="c20ac-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c20ac-136">Click OK.</span></span>
7. <span data-ttu-id="c20ac-137">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="c20ac-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="c20ac-138">Impostare i dettagli del modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="c20ac-138">Set work template details</span></span>
1. <span data-ttu-id="c20ac-139">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c20ac-139">Click New.</span></span>
2. <span data-ttu-id="c20ac-140">Nel campo Tipo di lavoro, selezionare 'Preleva'.</span><span class="sxs-lookup"><span data-stu-id="c20ac-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="c20ac-141">Nel campo ID classe lavoro, digitare 'acquisto'.</span><span class="sxs-lookup"><span data-stu-id="c20ac-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="c20ac-142">La classe di lavoro impostata in questo campo sarà l'impostazione predefinita in tutte le righe di lavoro di tipo prelievo create tramite questo modello.</span><span class="sxs-lookup"><span data-stu-id="c20ac-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="c20ac-143">La classe di lavoro non può essere sostituita dalle righe ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c20ac-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="c20ac-144">Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che un addetto al magazzino può elaborare in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c20ac-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="c20ac-145">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c20ac-145">Click New.</span></span>
5. <span data-ttu-id="c20ac-146">Nel campo Tipo di lavoro selezionare "Inserisci".</span><span class="sxs-lookup"><span data-stu-id="c20ac-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="c20ac-147">Nel campo ID classe, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c20ac-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="c20ac-148">Le istruzioni di prelievo e stoccaggio costituiscono un set.</span><span class="sxs-lookup"><span data-stu-id="c20ac-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="c20ac-149">Ogni set di prelievo/stoccaggio deve avere la stessa classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c20ac-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="c20ac-150">Utilizzare la stessa classe di lavoro fornita per l'istruzione di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c20ac-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="c20ac-151">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c20ac-151">Click Save.</span></span>
    * <span data-ttu-id="c20ac-152">Si noti che la casella di controllo Valido ora è selezionata.</span><span class="sxs-lookup"><span data-stu-id="c20ac-152">Note that the Valid checkbox is now checked.</span></span>  


