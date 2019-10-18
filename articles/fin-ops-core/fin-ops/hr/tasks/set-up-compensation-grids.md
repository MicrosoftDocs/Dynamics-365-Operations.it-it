---
title: Impostare le griglie retributive
description: Le griglie retributive vengono utilizzate per definire e gestire le strutture di pagamento per i piani di retribuzione fissa.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0caebb2dfbff12545610aa6438dccbec84db3f9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190352"
---
# <a name="set-up-compensation-grids"></a><span data-ttu-id="e1c13-103">Impostare le griglie retributive</span><span class="sxs-lookup"><span data-stu-id="e1c13-103">Set up compensation grids</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1c13-104">Le griglie retributive vengono utilizzate per definire e gestire le strutture di pagamento per i piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="e1c13-104">Compensation grids are used to define and maintain the pay structures for fixed compensation plans.</span></span> <span data-ttu-id="e1c13-105">Le griglie retributive possono essere condivise tra più piani o essere copiate quando si crea un nuovo piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="e1c13-105">Compensation grids can be shared between multiple plans or copied when creating a new compensation plan.</span></span>  <span data-ttu-id="e1c13-106">Prima della creazione della griglia retributiva, i livelli e i punti di riferimento devono essere impostati.</span><span class="sxs-lookup"><span data-stu-id="e1c13-106">Before creating a compensation grid, Levels and Reference points must be set up.</span></span> <span data-ttu-id="e1c13-107">In questo esempio si crea un nuovo tipo di grado di griglia retributiva utilizzando i dati dimostrativi per i livelli e i punti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e1c13-107">This example will create a new Grade type of compensation grid using demo data for the Levels and Reference points.</span></span> <span data-ttu-id="e1c13-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="e1c13-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-information-about-the-compensation-grid"></a><span data-ttu-id="e1c13-109">Impostare le informazioni sulla griglia retributiva</span><span class="sxs-lookup"><span data-stu-id="e1c13-109">Set up information about the compensation grid</span></span>
1. <span data-ttu-id="e1c13-110">Andare a Risorse umane > Compensation > Retribuzione fissa > Griglie retributive.</span><span class="sxs-lookup"><span data-stu-id="e1c13-110">Go to Human resources > Compensation > Fixed compensation > Compensation grids.</span></span>
2. <span data-ttu-id="e1c13-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e1c13-111">Click New.</span></span>
3. <span data-ttu-id="e1c13-112">Digitare un valore nel campo Griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-112">In the Grid field, type a value.</span></span>
4. <span data-ttu-id="e1c13-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e1c13-114">Selezionare un'opzione nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="e1c13-114">In the Type field, select an option.</span></span>
6. <span data-ttu-id="e1c13-115">Nel campo Impostazione riferimenti immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-115">In the Reference setup field, enter or select a value.</span></span>
7. <span data-ttu-id="e1c13-116">Nel campo Valuta immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-116">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="e1c13-117">Digitare un valore nel campo Valuta.</span><span class="sxs-lookup"><span data-stu-id="e1c13-117">In the Currency field, type a value.</span></span>
9. <span data-ttu-id="e1c13-118">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="e1c13-118">In the Effective date field, enter a date.</span></span>

## <a name="add-levels-to-the-compensation-structure"></a><span data-ttu-id="e1c13-119">Aggiungere livelli alla struttura retributiva</span><span class="sxs-lookup"><span data-stu-id="e1c13-119">Add levels to the compensation structure</span></span>
1. <span data-ttu-id="e1c13-120">Fare clic su Struttura retributiva.</span><span class="sxs-lookup"><span data-stu-id="e1c13-120">Click Compensation structure.</span></span>
2. <span data-ttu-id="e1c13-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e1c13-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="e1c13-122">Nel campo Livello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-122">In the Level field, enter or select a value.</span></span>
4. <span data-ttu-id="e1c13-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e1c13-123">Click New.</span></span>
5. <span data-ttu-id="e1c13-124">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e1c13-124">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="e1c13-125">Nel campo Livello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-125">In the Level field, enter or select a value.</span></span>
7. <span data-ttu-id="e1c13-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e1c13-126">Click New.</span></span>
8. <span data-ttu-id="e1c13-127">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e1c13-127">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="e1c13-128">Nel campo Livello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-128">In the Level field, enter or select a value.</span></span>
10. <span data-ttu-id="e1c13-129">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e1c13-129">Click New.</span></span>
11. <span data-ttu-id="e1c13-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e1c13-130">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="e1c13-131">Nel campo Livello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-131">In the Level field, enter or select a value.</span></span>
13. <span data-ttu-id="e1c13-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e1c13-132">Click New.</span></span>
14. <span data-ttu-id="e1c13-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e1c13-133">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="e1c13-134">Nel campo Livello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-134">In the Level field, enter or select a value.</span></span>

## <a name="fill-in-the-compensation-structure-with-values"></a><span data-ttu-id="e1c13-135">Compilare la struttura retributiva con valori</span><span class="sxs-lookup"><span data-stu-id="e1c13-135">Fill in the compensation structure with values</span></span>
1. <span data-ttu-id="e1c13-136">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e1c13-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e1c13-137">In questa fase, i valori di retribuzione possono essere immessi manualmente in ogni campo della tabella o la funzionalità di modifica di massa può essere utilizzata per completare facilmente più campi ed eseguire calcoli di base.</span><span class="sxs-lookup"><span data-stu-id="e1c13-137">At this point, compensation values can manually be entered into each field in the table, or the Mass change functionality can be used to easily fill in multiple fields and perform basic calculations.</span></span>  
2. <span data-ttu-id="e1c13-138">Fare clic su Modifica in massa.</span><span class="sxs-lookup"><span data-stu-id="e1c13-138">Click Mass change.</span></span>
    * <span data-ttu-id="e1c13-139">Per la griglia, è necessario applicare prima il valore del punto intermedio di primo livello a tutti i campi della tabella.</span><span class="sxs-lookup"><span data-stu-id="e1c13-139">For this grid, we'll first apply the value for the midpoint of the first level's to all the fields in the table.</span></span> <span data-ttu-id="e1c13-140">Si tratta della base della matrice di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="e1c13-140">This will be the basis for the compensation matrix.</span></span>  
3. <span data-ttu-id="e1c13-141">Nel campo Tipo di rettifica selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="e1c13-141">In the Adjustment type field, select an option.</span></span>
4. <span data-ttu-id="e1c13-142">Nel campo Importo di rettifica immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e1c13-142">In the Adjustment amount field, enter a number.</span></span>
5. <span data-ttu-id="e1c13-143">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="e1c13-143">In the list, mark or unmark all rows.</span></span>
6. <span data-ttu-id="e1c13-144">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-144">Click Apply to grid.</span></span>
    * <span data-ttu-id="e1c13-145">Ora verrà utilizzata la funzione di modifica di massa per incrementare gli importi in ogni livello successivo di una percentuale o un importo determinato.</span><span class="sxs-lookup"><span data-stu-id="e1c13-145">Now we'll use the mass change function to increment the amounts in each subsequent level by a certain percentage or amount.</span></span> <span data-ttu-id="e1c13-146">In questo esempio, ogni grado avrà una distribuzione del 12,5% tra i punti intermedi.</span><span class="sxs-lookup"><span data-stu-id="e1c13-146">In this example, each grade will have a 12.5% spread between their midpoints.</span></span>  
7. <span data-ttu-id="e1c13-147">Nel campo Tipo di rettifica selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="e1c13-147">In the Adjustment type field, select an option.</span></span>
8. <span data-ttu-id="e1c13-148">Nel campo Importo di rettifica immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e1c13-148">In the Adjustment amount field, enter a number.</span></span>
9. <span data-ttu-id="e1c13-149">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-149">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="e1c13-150">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-150">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="e1c13-151">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-151">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="e1c13-152">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-152">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="e1c13-153">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-153">Click Apply to grid.</span></span>
14. <span data-ttu-id="e1c13-154">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-154">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="e1c13-155">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-155">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="e1c13-156">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-156">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="e1c13-157">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-157">Click Apply to grid.</span></span>
18. <span data-ttu-id="e1c13-158">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-158">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="e1c13-159">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1c13-159">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="e1c13-160">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-160">Click Apply to grid.</span></span>
21. <span data-ttu-id="e1c13-161">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e1c13-161">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="e1c13-162">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-162">Click Apply to grid.</span></span>
    * <span data-ttu-id="e1c13-163">Ora verrà utilizzata la funzione di modifica di massa per rettificare i punti di riferimento minimo e massimo di ciascun livello.</span><span class="sxs-lookup"><span data-stu-id="e1c13-163">Now we'll use the mass change function to adjust the Minimum and Maximum reference points for each level.</span></span> <span data-ttu-id="e1c13-164">In questo esempio si utilizza una distribuzione del 50% in modo che il punto di riferimento minimo verrà rettificato a -20% e il massimo verrà rettificato a +20%.</span><span class="sxs-lookup"><span data-stu-id="e1c13-164">This example will use a 50% spread so the Minimum reference point will be adjusted -20% and the Maximum will be adjusted +20%.</span></span>  
23. <span data-ttu-id="e1c13-165">Nel campo Importo di rettifica immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e1c13-165">In the Adjustment amount field, enter a number.</span></span>
24. <span data-ttu-id="e1c13-166">Nel campo Punto di riferimento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-166">In the Reference point field, enter or select a value.</span></span>
25. <span data-ttu-id="e1c13-167">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="e1c13-167">In the list, mark or unmark all rows.</span></span>
26. <span data-ttu-id="e1c13-168">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-168">Click Apply to grid.</span></span>
27. <span data-ttu-id="e1c13-169">Nel campo Importo di rettifica immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e1c13-169">In the Adjustment amount field, enter a number.</span></span>
28. <span data-ttu-id="e1c13-170">Nel campo Punto di riferimento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e1c13-170">In the Reference point field, enter or select a value.</span></span>
29. <span data-ttu-id="e1c13-171">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="e1c13-171">In the list, mark or unmark all rows.</span></span>
30. <span data-ttu-id="e1c13-172">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e1c13-172">Click Apply to grid.</span></span>

