---
title: 'Definire il conteggio ciclo '
description: Il conteggio ciclo è un processo di magazzino che è possibile utilizzare per controllare gli articoli di magazzino disponibili.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8b7f39fc9a91d9fe219445e409d000266e24775
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431507"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="6fc81-103">Definire il conteggio ciclo </span><span class="sxs-lookup"><span data-stu-id="6fc81-103">Define cycle counting</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6fc81-104">Il conteggio ciclo è un processo di magazzino che è possibile utilizzare per controllare gli articoli di magazzino disponibili.</span><span class="sxs-lookup"><span data-stu-id="6fc81-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="6fc81-105">Questa registrazione attività mostra come impostare la priorità predefinita di lavoro di conteggio, abilitare una voce di menu dispositivo mobile per elaborare sia le operazioni di prelievo che di conteggio, abilitare un attivatore di soglia di conteggio quando un'ubicazione diventa vuota e abilitare un piano di conteggio ciclo per un articolo specifico all'interno di un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="6fc81-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="6fc81-106">Queste attività vengono in genere svolte da un responsabile di magazzino.</span><span class="sxs-lookup"><span data-stu-id="6fc81-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="6fc81-107">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure con dati propri.</span><span class="sxs-lookup"><span data-stu-id="6fc81-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="6fc81-108">Definire la priorità del lavoro di conteggio</span><span class="sxs-lookup"><span data-stu-id="6fc81-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="6fc81-109">Nel **pannello di navigazione** andare a **Moduli > Gestione magazzino > Impostazioni > Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-109">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="6fc81-110">Fare clic sulla scheda **Conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-110">Click the **Cycle counting** tab.</span></span>
3. <span data-ttu-id="6fc81-111">Nel campo **Priorità lavoro conteggio ciclo predefinita** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="6fc81-111">In the **Default cycle count work priority** field, enter a number.</span></span> <span data-ttu-id="6fc81-112">Questo passaggio cambia la priorità di conteggio ciclo rispetto ad altri tipi di lavoro nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="6fc81-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="6fc81-113">Se si inserisce un numero inferiore a quello di altri tipi di lavoro, la priorità di lavoro di conteggio ciclo aumenta.</span><span class="sxs-lookup"><span data-stu-id="6fc81-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="6fc81-114">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-114">Click **Save**.</span></span>
5. <span data-ttu-id="6fc81-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6fc81-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="6fc81-116">Abilitare il dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="6fc81-116">Enable the mobile device</span></span>
1. <span data-ttu-id="6fc81-117">Nel **pannello di navigazione**, andare a **Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-117">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="6fc81-118">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-118">Click **New**.</span></span>
3. <span data-ttu-id="6fc81-119">Digitare un valore nel campo **Nome voce di menu**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-119">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="6fc81-120">Digitare un valore nel campo **Titolo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-120">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="6fc81-121">Selezionare "Lavoro" nel campo **Modalità**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-121">In the **Mode** field, select 'Work'.</span></span>
6. <span data-ttu-id="6fc81-122">Impostare l'opzione **Utilizza lavoro esistente** su Sì.</span><span class="sxs-lookup"><span data-stu-id="6fc81-122">Set the **Use existing work** option to Yes.</span></span> <span data-ttu-id="6fc81-123">Quando questa opzione viene impostata su Sì, il sistema cercherà il lavoro esistente quando viene utilizzata la voce di menu dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="6fc81-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="6fc81-124">Nel campo **Diretto da** selezionare "Diretto dal sistema".</span><span class="sxs-lookup"><span data-stu-id="6fc81-124">In the **Directed by** field, select 'System directed'.</span></span> <span data-ttu-id="6fc81-125">Quando è selezionata l'opzione "Diretto dal sistema", il lavoratore del magazzino verrà indirizzato al lavoro aperto nelle classi di lavoro definite.</span><span class="sxs-lookup"><span data-stu-id="6fc81-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="6fc81-126">Tali classi verranno create in seguito.</span><span class="sxs-lookup"><span data-stu-id="6fc81-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="6fc81-127">Espandere la sezione **Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-127">Expand the **Work classes** fastTab.</span></span> <span data-ttu-id="6fc81-128">In seguito verranno create ora due classi di lavoro da utilizzare con la voce di menu dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="6fc81-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="6fc81-129">Quando la voce di menu viene utilizzata, verrà eseguita una ricerca in queste classi di lavoro e il lavoro con la priorità più alta verrà visualizzato all'utente.</span><span class="sxs-lookup"><span data-stu-id="6fc81-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="6fc81-130">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-130">Click **New**.</span></span>
10. <span data-ttu-id="6fc81-131">Nel campo **ID classe lavoro** selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6fc81-131">In the **Work class ID** field, select a value.</span></span>
11. <span data-ttu-id="6fc81-132">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-132">Click **New**.</span></span>
12. <span data-ttu-id="6fc81-133">Nel campo **ID classe lavoro** selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6fc81-133">In the **Work class ID** field, select a value.</span></span>
13. <span data-ttu-id="6fc81-134">Nel **Riquadro azioni** fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-134">In the **Action Pane**, click **Save**.</span></span>
14. <span data-ttu-id="6fc81-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6fc81-135">Close the page.</span></span>
15. <span data-ttu-id="6fc81-136">Nel **pannello di navigazione**, andare a **Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-136">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
16. <span data-ttu-id="6fc81-137">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6fc81-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="6fc81-138">Nella struttura selezionare la voce di menu appena creata.</span><span class="sxs-lookup"><span data-stu-id="6fc81-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="6fc81-139">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-139">Click **Edit**.</span></span>
19. <span data-ttu-id="6fc81-140">Fare clic sulla freccia per aggiungere la voce al menu.</span><span class="sxs-lookup"><span data-stu-id="6fc81-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="6fc81-141">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-141">Click **Save**.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="6fc81-142">Creare una soglia di conteggio</span><span class="sxs-lookup"><span data-stu-id="6fc81-142">Create a counting threshold</span></span>
1. <span data-ttu-id="6fc81-143">Nel **pannello di navigazione** andare a **Moduli > Gestione magazzino > Impostazioni > Conteggio ciclo > Soglie conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-143">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count thresholds**.</span></span>
2. <span data-ttu-id="6fc81-144">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-144">Click **New**.</span></span>
3. <span data-ttu-id="6fc81-145">Nel campo **ID soglia conteggio ciclo** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="6fc81-145">In the **Cycle counting threshold ID** field, type a value.</span></span>
4. <span data-ttu-id="6fc81-146">Impostare l'opzione **Elabora immediatamente conteggio ciclo** su Sì.</span><span class="sxs-lookup"><span data-stu-id="6fc81-146">Set the **Process cycle counting immediately** option to Yes.</span></span>
5. <span data-ttu-id="6fc81-147">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6fc81-147">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="6fc81-148">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-148">Click **Save**.</span></span>
7. <span data-ttu-id="6fc81-149">Fare clic su **Seleziona ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-149">Click **Select locations**.</span></span>
8. <span data-ttu-id="6fc81-150">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fc81-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="6fc81-151">Nel campo **Criteri** selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6fc81-151">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="6fc81-152">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-152">Click **OK**.</span></span>
11. <span data-ttu-id="6fc81-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6fc81-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="6fc81-154">Creare un piano di conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="6fc81-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="6fc81-155">Nel **pannello di navigazione** andare a **Moduli > Gestione magazzino > Impostazioni > Conteggio ciclo > Piani di conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-155">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count plans**.</span></span>
2. <span data-ttu-id="6fc81-156">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-156">Click **New**.</span></span>
3. <span data-ttu-id="6fc81-157">Nel campo **ID piano di conteggio ciclo** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="6fc81-157">In the **Cycle counting plan ID** field, type a value.</span></span>
4. <span data-ttu-id="6fc81-158">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6fc81-158">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="6fc81-159">Nel campo **Numero massimo di conteggi ciclo** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="6fc81-159">In the **Maximum number of cycle counts** field, enter a number.</span></span>
6. <span data-ttu-id="6fc81-160">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-160">Click **Save**.</span></span>
7. <span data-ttu-id="6fc81-161">Fare clic su **Seleziona ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-161">Click **Select locations**.</span></span>
8. <span data-ttu-id="6fc81-162">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fc81-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="6fc81-163">Nel campo **Criteri** selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6fc81-163">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="6fc81-164">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-164">Click **OK**.</span></span>
11. <span data-ttu-id="6fc81-165">Nel campo **Giorni tra conteggio ciclo** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="6fc81-165">In the **Days between cycle counting** field, enter a number.</span></span> <span data-ttu-id="6fc81-166">Ad esempio, se il valore specificato nel campo **Giorni tra conteggio ciclo** è impostato su 5, il lavoro del conteggio ciclo verrà creato ogni cinque giorni.</span><span class="sxs-lookup"><span data-stu-id="6fc81-166">For example, if the **Days between cycle counting** field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="6fc81-167">Tuttavia, se il lavoro di conteggio ciclo viene elaborato il terzo giorno, il lavoro di conteggio ciclo successivo verrà creato cinque giorni dopo l'elaborazione dell'ultimo conteggio ciclo, ovvero l'ottavo giorno.</span><span class="sxs-lookup"><span data-stu-id="6fc81-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="6fc81-168">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-168">Click **Save**.</span></span>
13. <span data-ttu-id="6fc81-169">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-169">Click **New**.</span></span>
14. <span data-ttu-id="6fc81-170">Immettere un numero nel campo **Numero progressivo**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-170">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="6fc81-171">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="6fc81-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="6fc81-172">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="6fc81-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="6fc81-173">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fc81-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="6fc81-174">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6fc81-174">In the **Description** field, type a value.</span></span>
17. <span data-ttu-id="6fc81-175">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-175">Click **Save**.</span></span>
18. <span data-ttu-id="6fc81-176">Fare clic su **Definisci query prodotto**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-176">Click **Define product** query.</span></span>
19. <span data-ttu-id="6fc81-177">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fc81-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="6fc81-178">Nel campo **Criteri** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6fc81-178">In the **Criteria** field, enter or select a value.</span></span>
21. <span data-ttu-id="6fc81-179">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fc81-179">Click **OK**.</span></span>
22. <span data-ttu-id="6fc81-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6fc81-180">Close the page.</span></span>

