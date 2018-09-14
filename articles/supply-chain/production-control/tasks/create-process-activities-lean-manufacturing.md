--- 
title: "Creare le attività di processo per la lean manufacturing"
description: "Creare un'attività di processo per lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: fa4d7fe2345d54faf405086a1e1bef599265470b
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="create-process-activities-for-lean-manufacturing"></a><span data-ttu-id="32276-103">Creare le attività di processo per la lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="32276-103">Create process activities for lean manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="32276-104">Creare un'attività di processo per lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="32276-104">Create a process activity for lean manufacturing.</span></span> 

<span data-ttu-id="32276-105">Prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="32276-105">Prerequisites:</span></span> 

1. <span data-ttu-id="32276-106">Un flusso di produzione e una versione non attiva devono essere creati.</span><span class="sxs-lookup"><span data-stu-id="32276-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="32276-107">Una cella di lavoro deve essere creata.</span><span class="sxs-lookup"><span data-stu-id="32276-107">A work cell must be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="32276-108">Trovare la versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="32276-108">Find the production flow version</span></span>
1. <span data-ttu-id="32276-109">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="32276-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="32276-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="32276-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="32276-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32276-111">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="32276-112">Creare una nuova attività</span><span class="sxs-lookup"><span data-stu-id="32276-112">Create a new activity</span></span>
1. <span data-ttu-id="32276-113">Fare clic su Attività.</span><span class="sxs-lookup"><span data-stu-id="32276-113">Click Activities.</span></span>
    * <span data-ttu-id="32276-114">Verificare che il flusso di produzione selezionato abbia una versione in bozza e selezionare tale versione.</span><span class="sxs-lookup"><span data-stu-id="32276-114">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="32276-115">Fare clic su Crea nuova attività piano.</span><span class="sxs-lookup"><span data-stu-id="32276-115">Click Create new plan activity.</span></span>
3. <span data-ttu-id="32276-116">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="32276-116">Click Next.</span></span>
4. <span data-ttu-id="32276-117">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="32276-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="32276-118">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="32276-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="32276-119">Si noti che il nome deve essere univoco per un flusso di produzione specificato per tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="32276-119">Note that the name must be unique for a given production flow for all versions.</span></span>  
6. <span data-ttu-id="32276-120">Nel campo Quantità di lavorazione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="32276-120">In the Process quantity field, enter a number.</span></span>
    * <span data-ttu-id="32276-121">Si noti che qualsiasi quantità di processo venga elaborata, questa è la quantità minima per processo per calcolare il costo della manodopera.</span><span class="sxs-lookup"><span data-stu-id="32276-121">Note that no matter what job quantity will be processed, this is the minimum quantity per job to calculate the labor cost.</span></span> <span data-ttu-id="32276-122">Se le quantità di processo deviano da questa quantità, uno scostamento costo della manodopera verrà creato.</span><span class="sxs-lookup"><span data-stu-id="32276-122">If job quantities deviate from this quantity, labor cost variance will be created.</span></span>  
7. <span data-ttu-id="32276-123">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="32276-123">Click Next.</span></span>

## <a name="select-the-work-cell"></a><span data-ttu-id="32276-124">Selezionare la cella di lavoro</span><span class="sxs-lookup"><span data-stu-id="32276-124">Select the work cell</span></span>
1. <span data-ttu-id="32276-125">Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="32276-125">In the Work cell field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="32276-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32276-126">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="32276-127">Definire gli aggiornamenti di inventario</span><span class="sxs-lookup"><span data-stu-id="32276-127">Define the inventory updates</span></span>
1. <span data-ttu-id="32276-128">Selezionare o deselezionare la casella di controllo Aggiorna entrata disponibile.</span><span class="sxs-lookup"><span data-stu-id="32276-128">Select or clear the Update on hand receipt check box.</span></span>
    * <span data-ttu-id="32276-129">Se Aggiorna disponibilità = No, è possibile definire l'attività in modo da ricevere un prodotto semilavorato (l'attività non raggiunge il livello DBA successivo).</span><span class="sxs-lookup"><span data-stu-id="32276-129">If Update On hand = No, you can define the activity to receive a semi-finished product (the activity does not reach the next BOM level).</span></span>    <span data-ttu-id="32276-130">È inoltre possibile scegliere di utilizzare prodotti semilavorati.</span><span class="sxs-lookup"><span data-stu-id="32276-130">You can also select to consume semi-finished products.</span></span>  

## <a name="define-the-picking-activities"></a><span data-ttu-id="32276-131">Definire le attività di prelievo</span><span class="sxs-lookup"><span data-stu-id="32276-131">Define the picking activities</span></span>
1. <span data-ttu-id="32276-132">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="32276-132">Click Next.</span></span>
2. <span data-ttu-id="32276-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32276-133">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="32276-134">Un'attività di prelievo predefinita viene creata per l'ubicazione di entrata della cella di lavoro selezionata.</span><span class="sxs-lookup"><span data-stu-id="32276-134">A default picking activity is created for the input location of the selected work cell.</span></span>  
3. <span data-ttu-id="32276-135">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="32276-135">Click Add.</span></span>
    * <span data-ttu-id="32276-136">È possibile creare attività di prelievo aggiuntive per prodotti specifici che non sono approntate nell'attività di entrata della cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="32276-136">You can create additional picking activities for specific products, that are not staged at the work cell input activity.</span></span>  
4. <span data-ttu-id="32276-137">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="32276-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="32276-138">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="32276-138">In the Item number field, type a value.</span></span>
6. <span data-ttu-id="32276-139">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="32276-139">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="32276-140">Con questa definizione, tutti i materiali utilizzati nell'attività vengono prelevati dal magazzino e dall'ubicazione di entrata predefiniti ad eccezione dell'articolo definito nella seconda attività di prelievo.</span><span class="sxs-lookup"><span data-stu-id="32276-140">With this definition, all materials consumed in the activity are picked from the default input warehouse and location except the item that is defined in the second picking activity.</span></span> <span data-ttu-id="32276-141">Questo articolo verrà prelevato da un magazzino e da un'ubicazione diversi.</span><span class="sxs-lookup"><span data-stu-id="32276-141">This item will be picked from a different warehouse and location.</span></span>  
7. <span data-ttu-id="32276-142">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="32276-142">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="32276-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32276-143">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="32276-144">Selezionare o deselezionare la casella di controllo Registra scarti.</span><span class="sxs-lookup"><span data-stu-id="32276-144">Select or clear the Register scrap check box.</span></span>
10. <span data-ttu-id="32276-145">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="32276-145">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="32276-146">Definire gli orari per le attività</span><span class="sxs-lookup"><span data-stu-id="32276-146">Define the activity times</span></span>
1. <span data-ttu-id="32276-147">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="32276-147">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="32276-148">La definizione di un runtime è richiesta.</span><span class="sxs-lookup"><span data-stu-id="32276-148">The definition of a Runtime is required.</span></span> <span data-ttu-id="32276-149">Il runtime viene utilizzato per calcolare i costi e i tempi di lavorazione dei processi kanban.</span><span class="sxs-lookup"><span data-stu-id="32276-149">The Runtime is used to calculate costs and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="32276-150">I runtime non vengono utilizzati per calcolare il carico di capacità e il consumo, questo viene calcolato in base alla durata ciclo, derivata dall'attività della versione del flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="32276-150">Runtimes are not used to calculate capacity load and consumption, this is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="32276-151">Immettere un numero nel campo Tempo.</span><span class="sxs-lookup"><span data-stu-id="32276-151">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="32276-152">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="32276-152">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="32276-153">Selezionare l'unità di tempo.</span><span class="sxs-lookup"><span data-stu-id="32276-153">Select the Time unit.</span></span>
5. <span data-ttu-id="32276-154">Nel campo Per quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="32276-154">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="32276-155">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="32276-155">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="32276-156">I tempi di attesa sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="32276-156">Queue times are optional.</span></span>  
7. <span data-ttu-id="32276-157">Immettere un numero nel campo Tempo.</span><span class="sxs-lookup"><span data-stu-id="32276-157">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="32276-158">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="32276-158">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="32276-159">Selezionare l'unità di tempo.</span><span class="sxs-lookup"><span data-stu-id="32276-159">Select the Time unit.</span></span>
10. <span data-ttu-id="32276-160">Nel campo Per quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="32276-160">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="32276-161">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="32276-161">Click Next.</span></span>
12. <span data-ttu-id="32276-162">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="32276-162">Click Finish.</span></span>
13. <span data-ttu-id="32276-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32276-163">Close the page.</span></span>


