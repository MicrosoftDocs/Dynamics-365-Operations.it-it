---
title: 'Definire il conteggio ciclo '
description: Il conteggio ciclo è un processo di magazzino che è possibile utilizzare per controllare gli articoli di magazzino disponibili.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2832547f81b0153d42ac4664184f18bd66f1acdd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571685"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="3c123-103">Definire il conteggio ciclo </span><span class="sxs-lookup"><span data-stu-id="3c123-103">Define cycle counting</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c123-104">Il conteggio ciclo è un processo di magazzino che è possibile utilizzare per controllare gli articoli di magazzino disponibili.</span><span class="sxs-lookup"><span data-stu-id="3c123-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="3c123-105">Questa registrazione attività mostra come impostare la priorità predefinita di lavoro di conteggio, abilitare una voce di menu dispositivo mobile per elaborare sia le operazioni di prelievo che di conteggio, abilitare un attivatore di soglia di conteggio quando un'ubicazione diventa vuota e abilitare un piano di conteggio ciclo per un articolo specifico all'interno di un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="3c123-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="3c123-106">Queste attività vengono in genere svolte da un responsabile di magazzino.</span><span class="sxs-lookup"><span data-stu-id="3c123-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="3c123-107">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure con dati propri.</span><span class="sxs-lookup"><span data-stu-id="3c123-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="3c123-108">Definire la priorità del lavoro di conteggio</span><span class="sxs-lookup"><span data-stu-id="3c123-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="3c123-109">Andare a Gestione magazzino > Impostazioni > Parametri di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="3c123-109">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="3c123-110">Fare clic sulla scheda Conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="3c123-110">Click the Cycle counting tab.</span></span>
3. <span data-ttu-id="3c123-111">Nel campo Priorità lavoro conteggio ciclo predefinita immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3c123-111">In the Default cycle count work priority field, enter a number.</span></span>
    * <span data-ttu-id="3c123-112">Questo passaggio cambia la priorità di conteggio ciclo rispetto ad altri tipi di lavoro nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="3c123-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="3c123-113">Se si inserisce un numero inferiore a quello di altri tipi di lavoro, la priorità di lavoro di conteggio ciclo aumenta.</span><span class="sxs-lookup"><span data-stu-id="3c123-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="3c123-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3c123-114">Click Save.</span></span>
5. <span data-ttu-id="3c123-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3c123-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="3c123-116">Abilitare il dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="3c123-116">Enable the mobile device</span></span>
1. <span data-ttu-id="3c123-117">Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Voci di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="3c123-117">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="3c123-118">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3c123-118">Click New.</span></span>
3. <span data-ttu-id="3c123-119">Digitare un valore nel campo Nome voce di menu.</span><span class="sxs-lookup"><span data-stu-id="3c123-119">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="3c123-120">Digitare un valore nel campo Titolo.</span><span class="sxs-lookup"><span data-stu-id="3c123-120">In the Title field, type a value.</span></span>
5. <span data-ttu-id="3c123-121">Selezionare "Lavoro" nel campo Modalità.</span><span class="sxs-lookup"><span data-stu-id="3c123-121">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="3c123-122">Impostare l'opzione Utilizza lavoro esistente su Sì.</span><span class="sxs-lookup"><span data-stu-id="3c123-122">Set the Use existing work option to Yes.</span></span>
    * <span data-ttu-id="3c123-123">Quando questa opzione viene impostata su Sì, il sistema cercherà il lavoro esistente quando viene utilizzata la voce di menu dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="3c123-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="3c123-124">Nel campo Diretto da selezionare "Diretto dal sistema".</span><span class="sxs-lookup"><span data-stu-id="3c123-124">In the Directed by field, select 'System directed'.</span></span>
    * <span data-ttu-id="3c123-125">Quando è selezionata l'opzione "Diretto dal sistema", il lavoratore del magazzino verrà indirizzato al lavoro aperto nelle classi di lavoro definite.</span><span class="sxs-lookup"><span data-stu-id="3c123-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="3c123-126">Tali classi verranno create in seguito.</span><span class="sxs-lookup"><span data-stu-id="3c123-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="3c123-127">Espandere o comprimere la sezione Classi lavoro.</span><span class="sxs-lookup"><span data-stu-id="3c123-127">Expand or collapse the Work classes section.</span></span>
    * <span data-ttu-id="3c123-128">In seguito verranno create ora due classi di lavoro da utilizzare con la voce di menu dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="3c123-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="3c123-129">Quando la voce di menu viene utilizzata, verrà eseguita una ricerca in queste classi di lavoro e il lavoro con la priorità più alta verrà visualizzato all'utente.</span><span class="sxs-lookup"><span data-stu-id="3c123-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="3c123-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3c123-130">Click New.</span></span>
10. <span data-ttu-id="3c123-131">Nel campo ID classe lavoro selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-131">In the Work class ID field, select a value.</span></span>
11. <span data-ttu-id="3c123-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3c123-132">Click New.</span></span>
12. <span data-ttu-id="3c123-133">Nel campo ID classe lavoro selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-133">In the Work class ID field, select a value.</span></span>
13. <span data-ttu-id="3c123-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3c123-134">Click Save.</span></span>
14. <span data-ttu-id="3c123-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3c123-135">Close the page.</span></span>
15. <span data-ttu-id="3c123-136">Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="3c123-136">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
16. <span data-ttu-id="3c123-137">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="3c123-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="3c123-138">Nella struttura selezionare la voce di menu appena creata.</span><span class="sxs-lookup"><span data-stu-id="3c123-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="3c123-139">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="3c123-139">Click Edit.</span></span>
19. <span data-ttu-id="3c123-140">Fare clic sulla freccia per aggiungere la voce al menu.</span><span class="sxs-lookup"><span data-stu-id="3c123-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="3c123-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3c123-141">Click Save.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="3c123-142">Creare una soglia di conteggio</span><span class="sxs-lookup"><span data-stu-id="3c123-142">Create a counting threshold</span></span>
1. <span data-ttu-id="3c123-143">Andare a Gestione magazzino > Impostazioni > Conteggio ciclo > Soglie conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="3c123-143">Go to Warehouse management > Setup > Cycle counting > Cycle count thresholds.</span></span>
2. <span data-ttu-id="3c123-144">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3c123-144">Click New.</span></span>
3. <span data-ttu-id="3c123-145">Nel campo ID soglia conteggio ciclo immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-145">In the Cycle counting threshold ID field, type a value.</span></span>
4. <span data-ttu-id="3c123-146">Impostare l'opzione Elabora immediatamente conteggio ciclo su Sì.</span><span class="sxs-lookup"><span data-stu-id="3c123-146">Set the Process cycle counting immediately option to Yes.</span></span>
5. <span data-ttu-id="3c123-147">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-147">In the Description field, type a value.</span></span>
6. <span data-ttu-id="3c123-148">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3c123-148">Click Save.</span></span>
7. <span data-ttu-id="3c123-149">Fare clic su Seleziona ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="3c123-149">Click Select locations.</span></span>
8. <span data-ttu-id="3c123-150">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3c123-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="3c123-151">Nel campo Criteri selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-151">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="3c123-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3c123-152">Click OK.</span></span>
11. <span data-ttu-id="3c123-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3c123-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="3c123-154">Creare un piano di conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="3c123-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="3c123-155">Andare a Gestione magazzino > Impostazioni > Conteggio ciclo > Piani di conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="3c123-155">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="3c123-156">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3c123-156">Click New.</span></span>
3. <span data-ttu-id="3c123-157">Nel campo ID piano di conteggio ciclo immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-157">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="3c123-158">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="3c123-158">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3c123-159">Nel campo Numero massimo di conteggi ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3c123-159">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="3c123-160">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3c123-160">Click Save.</span></span>
7. <span data-ttu-id="3c123-161">Fare clic su Seleziona ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="3c123-161">Click Select locations.</span></span>
8. <span data-ttu-id="3c123-162">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3c123-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="3c123-163">Nel campo Criteri selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-163">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="3c123-164">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3c123-164">Click OK.</span></span>
11. <span data-ttu-id="3c123-165">Nel campo Giorni tra conteggio ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3c123-165">In the Days between cycle counting field, enter a number.</span></span>
    * <span data-ttu-id="3c123-166">Ad esempio, se il valore specificato nel campo Giorni tra conteggio ciclo è impostato su 5, il lavoro del conteggio ciclo verrà creato ogni cinque giorni.</span><span class="sxs-lookup"><span data-stu-id="3c123-166">For example, if the Days between cycle counting field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="3c123-167">Tuttavia, se il lavoro di conteggio ciclo viene elaborato il terzo giorno, il lavoro di conteggio ciclo successivo verrà creato cinque giorni dopo l'elaborazione dell'ultimo conteggio ciclo, ovvero l'ottavo giorno.</span><span class="sxs-lookup"><span data-stu-id="3c123-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="3c123-168">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3c123-168">Click Save.</span></span>
13. <span data-ttu-id="3c123-169">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3c123-169">Click New.</span></span>
14. <span data-ttu-id="3c123-170">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="3c123-170">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="3c123-171">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="3c123-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="3c123-172">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="3c123-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="3c123-173">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3c123-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="3c123-174">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-174">In the Description field, type a value.</span></span>
17. <span data-ttu-id="3c123-175">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3c123-175">Click Save.</span></span>
18. <span data-ttu-id="3c123-176">Fare clic su Definisci query prodotto.</span><span class="sxs-lookup"><span data-stu-id="3c123-176">Click Define product query.</span></span>
19. <span data-ttu-id="3c123-177">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3c123-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="3c123-178">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3c123-178">In the Criteria field, enter or select a value.</span></span>
21. <span data-ttu-id="3c123-179">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3c123-179">Click OK.</span></span>
22. <span data-ttu-id="3c123-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3c123-180">Close the page.</span></span>

