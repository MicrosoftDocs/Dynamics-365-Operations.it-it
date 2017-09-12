--- 
title: Analizzare i risultati del questionario
description: Le statistiche del questionario possono essere utilizzate per calcolare medie, totali e percentuali in base a un set di dati demografici.
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c243a84b63215ab44e2929c64dbc4aced7061474
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="analyze-questionnaire-results"></a><span data-ttu-id="e0f8a-103">Analizzare i risultati del questionario</span><span class="sxs-lookup"><span data-stu-id="e0f8a-103">Analyze questionnaire results</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e0f8a-104">Le statistiche del questionario possono essere utilizzate per calcolare medie, totali e percentuali in base a un set di dati demografici.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-104">Questionnaire statistics can be used to calculate averages, totals, and percentages based on a set of demographic data.</span></span> <span data-ttu-id="e0f8a-105">Per iniziare questa procedura, andare a Questionario > Visualizza e analizza risultati > Statistiche questionario.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-105">To begin this procedure, go to Questionnaire > View and analyze results > Questionnaire statistics.</span></span> <span data-ttu-id="e0f8a-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-statistics-record"></a><span data-ttu-id="e0f8a-107">Creare un record di statistiche questionario</span><span class="sxs-lookup"><span data-stu-id="e0f8a-107">Create a Questionnaire statistics record</span></span>
1. <span data-ttu-id="e0f8a-108">Andare a Statistiche questionario.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-108">Go to Questionnaire statistics.</span></span>
2. <span data-ttu-id="e0f8a-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-109">Click New.</span></span>
3. <span data-ttu-id="e0f8a-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e0f8a-111">Digitare un valore nel campo Statistiche.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-111">In the Statistics field, type a value.</span></span>
5. <span data-ttu-id="e0f8a-112">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="e0f8a-113">Nel campo Questionario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-113">In the Questionnaire field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e0f8a-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e0f8a-115">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-115">Click the General tab.</span></span>
    * <span data-ttu-id="e0f8a-116">Selezionare se si desidera includere risultati anonimi o risultati di lavoratori, contatti e candidati.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-116">Select if you want to include anonymous results or results from workers, contacts, and applicants.</span></span>  
9. <span data-ttu-id="e0f8a-117">Selezionare o deselezionare la casella di controllo Lavoratore.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-117">Select or clear the Worker check box.</span></span>
    * <span data-ttu-id="e0f8a-118">Se vengono visualizzati i risultati in base ad anzianità o età, specificare gli intervalli da utilizzare per raggruppare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-118">If you will be viewing the results by seniority or age, specify the intervals that you would like to use for grouping the results.</span></span>  
    * <span data-ttu-id="e0f8a-119">Se si immette 5 per l'intervallo di età, i risultati verranno raggruppati in base a intervalli di cinque anni.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-119">Entering a 5 for the age interval will group the results based on five-year age intervals.</span></span>  
10. <span data-ttu-id="e0f8a-120">Nel campo Età immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-120">In the Age field, enter a number.</span></span>
    * <span data-ttu-id="e0f8a-121">Selezionare se si desidera eseguire il calcolo per l'intero questionario, per ciascun gruppo di risultati, per ciascuna domanda o per ogni riga della domanda.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-121">Select if you want to run the calculation against the entire questionnaire, for each result group, for each question, or for each question row.</span></span>  
    * <span data-ttu-id="e0f8a-122">Selezionare il modo in cui si desidera raggruppare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-122">Select how you would like to group the results.</span></span>  
    * <span data-ttu-id="e0f8a-123">Ad esempio, se si calcolano i punti medi per domanda, è consigliabile visualizzare le domande raggruppate per gruppo di risultati.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-123">For example, if you calculate the average points per question, you may want to see the questions grouped by Result group.</span></span>  
    * <span data-ttu-id="e0f8a-124">Selezionare i dati su cui basare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-124">Select the data to base the calculation on.</span></span>  
    * <span data-ttu-id="e0f8a-125">Ad esempio, può essere opportuno visualizzare le percentuali medie ricevute nel questionario tra i lavoratori rispetto al numero medio di punti raggiunti tra i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-125">For example, if you want to see the average percent received on the questionnaire across your workers versus the average number of points achieved across your workers.</span></span>  
11. <span data-ttu-id="e0f8a-126">Fare clic sulla scheda Intervallo.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-126">Click the Range tab.</span></span>
    * <span data-ttu-id="e0f8a-127">Utilizzare gli intervalli per limitare il set di risultati solo a quelli che soddisfano i criteri dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-127">Use ranges to limit your result set to only those meeting the Range criteria.</span></span>  
12. <span data-ttu-id="e0f8a-128">Fare clic sulla scheda Raggruppamento per.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-128">Click the Grouping by tab.</span></span>
    * <span data-ttu-id="e0f8a-129">Utilizzare i raggruppamenti per determinare il modo in cui i risultati devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-129">Use Groupings to determine how the results should be displayed.</span></span>  
    * <span data-ttu-id="e0f8a-130">Ad esempio, raggruppare i risultati prima per sesso, quindi per età.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-130">For example, group the results first by gender, then by age.</span></span>  
13. <span data-ttu-id="e0f8a-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e0f8a-132">Spostare i raggruppamenti nel lato selezionato e posizionarli nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-132">Move the groupings into the Selected side and place them in the desired order.</span></span>  

## <a name="execute-the-statistics-calculation"></a><span data-ttu-id="e0f8a-133">Eseguire il calcolo delle statistiche</span><span class="sxs-lookup"><span data-stu-id="e0f8a-133">Execute the statistics calculation</span></span>
1. <span data-ttu-id="e0f8a-134">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-134">Click Execute.</span></span>
    * <span data-ttu-id="e0f8a-135">Selezionare la funzione di calcolo da eseguire sui risultati.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-135">Select which calculation function you would like to perform on the results.</span></span>  
    * <span data-ttu-id="e0f8a-136">Ad esempio, calcolare le percentuali medie nel questionario per i raggruppamenti selezionati o sommare i punti tra i gruppi di risultati per i raggruppamenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-136">For example, calculate the average percentages across the questionnaire for the selected groupings or total the points across the result groups for the selected groupings.</span></span>  
2. <span data-ttu-id="e0f8a-137">Selezionare o deselezionare la casella di controllo Elimina le ricerche precedenti.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-137">Select or clear the Delete previous searches check box.</span></span>
3. <span data-ttu-id="e0f8a-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-138">Click OK.</span></span>

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a><span data-ttu-id="e0f8a-139">Visualizzare i risultati dell'esecuzione delle statistiche del questionario.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-139">View the results of the questionnaire statistics run.</span></span>
1. <span data-ttu-id="e0f8a-140">Fare clic su Risultato.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-140">Click Result.</span></span>
2. <span data-ttu-id="e0f8a-141">Fare clic su Risultato.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-141">Click Result.</span></span>
3. <span data-ttu-id="e0f8a-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e0f8a-142">Close the page.</span></span>

