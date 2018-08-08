--- 
title: "Calcolare suggerimenti su quantità kanban"
description: "Questa procedura riguarda l'ottimizzazione della dimensione e delle quantità kanban per una regola kanban specifica tramite il calcolo della quantità kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 540dd32c5da5859ef5e69f55d6806eada90bc840
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="calculate-kanban-quantity-suggestions"></a><span data-ttu-id="0d944-103">Calcolare suggerimenti su quantità kanban</span><span class="sxs-lookup"><span data-stu-id="0d944-103">Calculate kanban quantity suggestions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d944-104">Questa procedura riguarda l'ottimizzazione della dimensione e delle quantità kanban per una regola kanban specifica tramite il calcolo della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-104">This procedure focuses on optimizing the kanban size and quantities for a specific kanban rule by using the kanban quantity calculation.</span></span> <span data-ttu-id="0d944-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="0d944-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0d944-106">Questa procedura è destinata al responsabile del flusso del valore.</span><span class="sxs-lookup"><span data-stu-id="0d944-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="0d944-107">Per seguire questa procedura, è necessario aver completato la procedura Aggiungere criteri di calcolo quantità kanban a una regola kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-107">It is a prerequisite that you have completed the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span>


## <a name="create-a-kanban-quantity-calculation"></a><span data-ttu-id="0d944-108">Creare un calcolo di quantità kanban</span><span class="sxs-lookup"><span data-stu-id="0d944-108">Create a kanban quantity calculation</span></span>
1. <span data-ttu-id="0d944-109">Andare a Controllo produzione > Attività periodiche > Calcolo quantità kanban > Calcola quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Calculate kanban quantity.</span></span>
2. <span data-ttu-id="0d944-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0d944-110">Click New.</span></span>
3. <span data-ttu-id="0d944-111">Nel campo Nome digitare "Speaker2016".</span><span class="sxs-lookup"><span data-stu-id="0d944-111">In the Name field, type 'Speaker2016'.</span></span>
4. <span data-ttu-id="0d944-112">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0d944-112">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0d944-113">Selezionare i criteri creati nella procedura Aggiungere criteri di calcolo quantità kanban a una regola kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-113">Select the policy that you have created in the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span> <span data-ttu-id="0d944-114">Ad esempio, Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="0d944-114">For example, Speaker2016.</span></span>  
5. <span data-ttu-id="0d944-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d944-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="0d944-116">Nel campo Regola attiva dalla data impostare la data e l'ora su "17-12-2012T08.00.00".</span><span class="sxs-lookup"><span data-stu-id="0d944-116">In the Rule active as of date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="0d944-117">Questa data viene utilizzata come base per determinare quali regole kanban fisse vengono incluse nel calcolo della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-117">This date serves as the basis for determining which fixed kanban rules are included in the kanban quantity calculation.</span></span>  
7. <span data-ttu-id="0d944-118">Nel campo Data di inizio periodo evasione domanda impostare la data e l'ora su "17-11-2012T09.00.00".</span><span class="sxs-lookup"><span data-stu-id="0d944-118">In the Fulfilled demand period start date field, set the date and time to '2012-11-17T09:00:00'.</span></span>
    * <span data-ttu-id="0d944-119">Data dalla quale vengono incluse le transazioni della domanda passata per calcolare la quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-119">The date from when past demand transactions are included to calculate the kanban quantity.</span></span>  
8. <span data-ttu-id="0d944-120">Nel campo Data di fine periodo evasione domanda impostare la data e l'ora su "17-12-2012T07.59.59".</span><span class="sxs-lookup"><span data-stu-id="0d944-120">In the Fulfilled demand period end date field, set the date and time to '2012-12-17T07:59:59'.</span></span>
    * <span data-ttu-id="0d944-121">Data fino alla quale vengono incluse le transazioni della domanda passata per calcolare la quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-121">The date until when past demand transactions are included to calculate the kanban quantity.</span></span>  
9. <span data-ttu-id="0d944-122">Nel campo Data di inizio periodo domanda impostare la data e l'ora su "17-12-2012T08.00.00".</span><span class="sxs-lookup"><span data-stu-id="0d944-122">In the Demand period start date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="0d944-123">Data dalla quale vengono incluse le transazioni della domanda corrente per calcolare la quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-123">The date from when current demand transactions are included to calculate the kanban quantity.</span></span>  
10. <span data-ttu-id="0d944-124">Nel campo Data di fine periodo domanda impostare la data e l'ora su "16-01-2013T07.59.59".</span><span class="sxs-lookup"><span data-stu-id="0d944-124">In the Demand period end date field, set the date and time to '2013-01-16T07:59:59'.</span></span>
    * <span data-ttu-id="0d944-125">Data fino alla quale vengono incluse le transazioni della domanda corrente per calcolare la quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-125">The date until when current demand transactions are included to calculate the kanban quantity.</span></span>  

## <a name="generate-kanban-quantity-proposal"></a><span data-ttu-id="0d944-126">Generare una proposta di quantità kanban</span><span class="sxs-lookup"><span data-stu-id="0d944-126">Generate kanban quantity proposal</span></span>
1. <span data-ttu-id="0d944-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="0d944-127">Click Save.</span></span>
2. <span data-ttu-id="0d944-128">Fare clic su Genera.</span><span class="sxs-lookup"><span data-stu-id="0d944-128">Click Generate.</span></span>
    * <span data-ttu-id="0d944-129">Viene generata una riga di proposta di quantità kanban per la regola kanban 000020.</span><span class="sxs-lookup"><span data-stu-id="0d944-129">This generates a kanban quantity proposal line for the kanban rule 000020.</span></span>  

## <a name="run-kanban-quantity-calculation"></a><span data-ttu-id="0d944-130">Eseguire il calcolo della quantità kanban</span><span class="sxs-lookup"><span data-stu-id="0d944-130">Run kanban quantity calculation</span></span>
1. <span data-ttu-id="0d944-131">Fare clic su Calcola.</span><span class="sxs-lookup"><span data-stu-id="0d944-131">Click Calculate.</span></span>
    * <span data-ttu-id="0d944-132">Viene calcolata la proposta di quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-132">This calculates the kanban quantity proposal.</span></span>  
2. <span data-ttu-id="0d944-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0d944-133">Click OK.</span></span>
3. <span data-ttu-id="0d944-134">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d944-134">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0d944-135">Si noti che la quantità kanban consentita è 2.</span><span class="sxs-lookup"><span data-stu-id="0d944-135">Notice the suggested kanban quantity is 2.</span></span>  

## <a name="change-product-quantity-and-calculate-again"></a><span data-ttu-id="0d944-136">Modificare la quantità di prodotto e calcolarla nuovamente</span><span class="sxs-lookup"><span data-stu-id="0d944-136">Change product quantity and calculate again</span></span>
1. <span data-ttu-id="0d944-137">Impostare la quantità prodotto su "5".</span><span class="sxs-lookup"><span data-stu-id="0d944-137">Set Product quantity to '5'.</span></span>
2. <span data-ttu-id="0d944-138">Fare clic su Calcola.</span><span class="sxs-lookup"><span data-stu-id="0d944-138">Click Calculate.</span></span>
3. <span data-ttu-id="0d944-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0d944-139">Click OK.</span></span>
    * <span data-ttu-id="0d944-140">Si noti che con una quantità kanban pari a 5, il suggerimento viene modificato in una quantità kanban pari a 4.</span><span class="sxs-lookup"><span data-stu-id="0d944-140">Notice that with a kanban quantity of 5, the suggestion is changed to a kanban quantity of 4.</span></span>  
    * <span data-ttu-id="0d944-141">Questa situazione è causata dal fatto che con una quantità di prodotto inferiore sono necessarie quantità kanban maggiori per soddisfare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="0d944-141">This is caused by the fact that with a lower product quantity, we need more kanbans to fulfill the demand.</span></span>  

## <a name="update-kanban-rule"></a><span data-ttu-id="0d944-142">Aggiornare la quantità kanban</span><span class="sxs-lookup"><span data-stu-id="0d944-142">Update kanban rule</span></span>
1. <span data-ttu-id="0d944-143">Nel campo Data di validità regola immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="0d944-143">In the Rule effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="0d944-144">Impostare "Regola attiva dalla data" su una data successiva a quella corrente.</span><span class="sxs-lookup"><span data-stu-id="0d944-144">Set the 'Rule active as of date' to a date in the future.</span></span> <span data-ttu-id="0d944-145">Ad esempio, oggi + un anno.</span><span class="sxs-lookup"><span data-stu-id="0d944-145">For example, today + one year.</span></span>  
2. <span data-ttu-id="0d944-146">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="0d944-146">Click Update.</span></span>
3. <span data-ttu-id="0d944-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0d944-147">Click OK.</span></span>
4. <span data-ttu-id="0d944-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0d944-148">Close the page.</span></span>

## <a name="validate-change-on-kanban-rule"></a><span data-ttu-id="0d944-149">Convalidare la modifica della regola kanban</span><span class="sxs-lookup"><span data-stu-id="0d944-149">Validate change on kanban rule</span></span>
1. <span data-ttu-id="0d944-150">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-150">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="0d944-151">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0d944-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0d944-152">Selezionare la regola kanban creata nella sottoattività precedente.</span><span class="sxs-lookup"><span data-stu-id="0d944-152">Select the kanban rule that was created in the previous sub-task.</span></span> <span data-ttu-id="0d944-153">Questa deve essere la prima regola kanban nell'elenco ordinato per numero.</span><span class="sxs-lookup"><span data-stu-id="0d944-153">This should be the first kanban rule in the list sorted by number.</span></span>  
3. <span data-ttu-id="0d944-154">Attivare/disattivare l'espansione della sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="0d944-154">Toggle the expansion of the Details section.</span></span>
    * <span data-ttu-id="0d944-155">Si noti la data di validità, che indica che questa regola non è attivata fino a tale data.</span><span class="sxs-lookup"><span data-stu-id="0d944-155">Notice the effective date, which means that this rule is not activated until this date.</span></span>  
4. <span data-ttu-id="0d944-156">Attivare/disattivare l'espansione della sezione Quantità.</span><span class="sxs-lookup"><span data-stu-id="0d944-156">Toggle the expansion of the Quantities section.</span></span>
    * <span data-ttu-id="0d944-157">Si noti che si tratta della quantità predefinita immessa nel calcolo della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-157">Notice this is the default quantity that you entered on the kanban quantity calculation.</span></span>  
    * <span data-ttu-id="0d944-158">Si noti che si tratta della quantità kanban fissa pari a 4 derivata dal calcolo della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="0d944-158">Notice this is the fixed kanban quantity of 4 from the kanban quantity calculation.</span></span>  
5. <span data-ttu-id="0d944-159">Fare clic sulla scheda ListPanel.</span><span class="sxs-lookup"><span data-stu-id="0d944-159">Click the ListPanel tab.</span></span>


