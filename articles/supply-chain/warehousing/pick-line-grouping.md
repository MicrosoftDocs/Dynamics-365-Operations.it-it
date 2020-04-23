---
title: Raggruppamento righe prelievo
description: In questo argomento viene fornita una panoramica del raggruppamento delle righe prelievo.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 4b9cd7dac680c1691fb4c6dd4078f109254be784
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215599"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="b9f47-103">Raggruppamento righe prelievo</span><span class="sxs-lookup"><span data-stu-id="b9f47-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9f47-104">Nel raggruppamento delle righe di prelievo, è possibile combinare più righe di lavoro con lo stesso articolo e posizione in un unico prelievo che viene presentato all'utente su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b9f47-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="b9f47-105">Pertanto, gli addetti al magazzino possono ricevere le istruzioni più efficienti possibili, ma viene mantenuta anche la necessaria separazione delle righe di lavoro nel sistema (ad esempio, per diversi contenitori e ordini).</span><span class="sxs-lookup"><span data-stu-id="b9f47-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="b9f47-106">Configurare il raggruppamento delle righe prelievo</span><span class="sxs-lookup"><span data-stu-id="b9f47-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="b9f47-107">Creare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="b9f47-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="b9f47-108">Andare a **Gestione magazzino \>Impostazione \>Dispositivo mobile \>Voci di menu del dispositivo mobile** e creare una nuova voce di menu denominata **Prelievo riga gruppo di vendita - Utente diretto**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**, and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="b9f47-109">In **Voci di menu del dispositivo mobile**, impostare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f47-109">Under **Mobile device menu items**, set the following values:</span></span>

    - <span data-ttu-id="b9f47-110">Nel campo **Nome voce di menu**, immettere **Prelievo vendite - Riga gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="b9f47-111">Nel campo **Titolo**, immetti **Prelievo vendite - Riga gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="b9f47-112">Selezionare **Lavoro** nel campo **Modalità**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="b9f47-113">Impostare l'opzione **Utilizza lavoro esistente** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="b9f47-114">Nella scheda Dettagli **Generale**, è possibile impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b9f47-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="b9f47-115">Nel campo **Diretto da**, selezionare **Diretto dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="b9f47-116">Impostare l'opzione **Genera targa** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="b9f47-117">Impostare l'opzione **Prelievo gruppo** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="b9f47-118">Nella Scheda dettagli **Classi di lavoro**, seguire questi passaggi per configurare le classi di lavoro valide per la voce di menu del dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="b9f47-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="b9f47-119">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-119">Select **New**.</span></span>
    2. <span data-ttu-id="b9f47-120">Nel campo **ID classe di lavoro**, selezionare **Vendite** o **Prelievo SO**, a seconda del magazzino che verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b9f47-120">In the **Work class ID** field, select **Sales** or **SO Pick**, depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="b9f47-121">Nel campo **Tipo ordine di lavoro** selezionare **Ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="b9f47-122">Configurare un menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="b9f47-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="b9f47-123">Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="b9f47-124">Aggiungere la voce di menu appena creata al menu desiderato.</span><span class="sxs-lookup"><span data-stu-id="b9f47-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="b9f47-125">Configurare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="b9f47-125">Set up a work template</span></span>

1. <span data-ttu-id="b9f47-126">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b9f47-127">Trovare il modello di lavoro da utilizzare con questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b9f47-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="b9f47-128">Per questo esempio, selezionare il modello di lavoro Contoso **51 prelievi da approntare** standard.</span><span class="sxs-lookup"><span data-stu-id="b9f47-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="b9f47-129">Nel menu, selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="b9f47-130">Nella scheda **Ordinamento**, selezionare **Aggiungi** e quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b9f47-130">On the **Sorting** tab, select **Add**, and then set the following values:</span></span>

    - <span data-ttu-id="b9f47-131">Nel campo **Tabella** selezionare **Transazioni lavoro temporanee**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="b9f47-132">Nel campo **Tabella derivata** selezionare **Transazioni lavoro temporanee**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="b9f47-133">Nel campo **Campo** selezionare **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="b9f47-134">Nel campo **Direzione di ricerca**, selezionare **Crescente**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="b9f47-135">Affinché la funzionalità di raggruppamento delle righe di prelievo funzioni, le righe di lavoro devono essere ordinate per ID articolo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="b9f47-136">Se le righe che hanno gli stessi articoli non sono in sequenza una dopo l'altra, non verranno raggruppate.</span><span class="sxs-lookup"><span data-stu-id="b9f47-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="b9f47-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9f47-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="b9f47-138">Creare il lavoro di prelievo</span><span class="sxs-lookup"><span data-stu-id="b9f47-138">Create picking work</span></span>

<span data-ttu-id="b9f47-139">Prima di poter impostare il raggruppamento delle righe di prelievo, è necessario creare del lavoro in uscita idoneo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="b9f47-140">Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="b9f47-141">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b9f47-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="b9f47-142">Nel campo **Conto cliente** selezionare qualsiasi cliente.</span><span class="sxs-lookup"><span data-stu-id="b9f47-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="b9f47-143">Nel campo **Magazzino** della Scheda dettaglio **Generale**, selezionare **51**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="b9f47-144">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-144">Then select **OK**.</span></span>
5. <span data-ttu-id="b9f47-145">In **Righe ordine cliente**, aggiungere le sei righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f47-145">Under **Sales order lines**, add the following six lines:</span></span>

    - <span data-ttu-id="b9f47-146">**Riga 1:** nel campo **Numero articolo** selezionare **M9200**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="b9f47-147">Nel campo **Quantità** immettere **3**</span><span class="sxs-lookup"><span data-stu-id="b9f47-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="b9f47-148">**Riga 2:** nel campo **Numero articolo** selezionare **M9201**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="b9f47-149">Nel campo **Quantità** immettere **3**</span><span class="sxs-lookup"><span data-stu-id="b9f47-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="b9f47-150">**Riga 3:** nel campo **Numero articolo** selezionare **M9202**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="b9f47-151">Nel campo **Quantità** immettere **2**</span><span class="sxs-lookup"><span data-stu-id="b9f47-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="b9f47-152">**Riga 4:** nel campo **Numero articolo** selezionare **M9200**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="b9f47-153">Nel campo **Quantità** immettere **1**</span><span class="sxs-lookup"><span data-stu-id="b9f47-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="b9f47-154">**Riga 5:** nel campo **Numero articolo** selezionare **M9200**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="b9f47-155">Nel campo **Quantità** immettere **3**</span><span class="sxs-lookup"><span data-stu-id="b9f47-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="b9f47-156">**Riga 6:** nel campo **Numero articolo** selezionare **M9202**.</span><span class="sxs-lookup"><span data-stu-id="b9f47-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="b9f47-157">Nel campo **Quantità** immettere **7**</span><span class="sxs-lookup"><span data-stu-id="b9f47-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="b9f47-158">Ecco un riepilogo delle quantità totali per ciascun articolo:</span><span class="sxs-lookup"><span data-stu-id="b9f47-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="b9f47-159">**Articolo M9200:** 7 ciascuno</span><span class="sxs-lookup"><span data-stu-id="b9f47-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="b9f47-160">**Articolo M9201:** 3 ciascuno</span><span class="sxs-lookup"><span data-stu-id="b9f47-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="b9f47-161">**Articolo M9202:** 9 ciascuno</span><span class="sxs-lookup"><span data-stu-id="b9f47-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="b9f47-162">Prima di rilasciare gli ordini al magazzino, è necessario assicurarsi che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli di tutti gli ordini.</span><span class="sxs-lookup"><span data-stu-id="b9f47-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="b9f47-163">Rivedere l'impostazione **Direttiva ubicazione** per determinare quali ubicazioni di prelievo vengono utilizzate per il prelievo dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b9f47-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="b9f47-164">Prenotare le scorte e rilasciarle al magazzino.</span><span class="sxs-lookup"><span data-stu-id="b9f47-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="b9f47-165">Viene creato un ID lavoro con sei righe.</span><span class="sxs-lookup"><span data-stu-id="b9f47-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="b9f47-166">Le righe sono ordinate per numero articolo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="b9f47-167">Eseguire il flussi del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="b9f47-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="b9f47-168">Sul dispositivo mobile, selezionare il menu che include la nuova voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b9f47-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="b9f47-169">Selezionare la voce di menu **Prelievo vendite - Riga gruppo** e avviare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="b9f47-170">Dopo aver selezionato il menu e inserito l'ID lavoro, viene visualizzato il passaggio di prelievo in cui sono raggruppate tutte le righe di prelievo per l'articolo M9200.</span><span class="sxs-lookup"><span data-stu-id="b9f47-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="b9f47-171">Si riceve quindi l'istruzione per prelevare scegliere 7 quantità dell'articolo M9200.</span><span class="sxs-lookup"><span data-stu-id="b9f47-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="b9f47-172">Confermare il passaggio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="b9f47-173">Passare alla schermata client del lavoro in corso e prendere nota che tutte e tre le righe di prelievo per l'articolo M9200 sono state chiuse contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b9f47-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="b9f47-174">Viene presentata la riga di lavoro 4.</span><span class="sxs-lookup"><span data-stu-id="b9f47-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="b9f47-175">Confermare il passaggio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-175">Confirm the pick step.</span></span>

    <span data-ttu-id="b9f47-176">L'ultimo passaggio di prelievo sul dispositivo mobile aggrega le ultime due righe di prelievo dall'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9f47-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="b9f47-177">Completare il passaggio di prelievo per 9 ciascuno dell'articolo M9202.</span><span class="sxs-lookup"><span data-stu-id="b9f47-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="b9f47-178">Confermare il passaggio di inserimento e tutte le coppie di prelievo/inserimento aggiuntive per completare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9f47-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="b9f47-179">Le righe di lavoro possono essere raggruppate solo se sono in sequenza.</span><span class="sxs-lookup"><span data-stu-id="b9f47-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="b9f47-180">Sono supportate le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="b9f47-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="b9f47-181">Articoli a peso variabile.</span><span class="sxs-lookup"><span data-stu-id="b9f47-181">Catch-weight items.</span></span> <span data-ttu-id="b9f47-182">Se sul lavoro sono presenti articoli a peso variabile, riceverai un messaggio di errore prima di iniziare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="b9f47-183">Prelievo di pezzi.</span><span class="sxs-lookup"><span data-stu-id="b9f47-183">Piece picking.</span></span>
>    - <span data-ttu-id="b9f47-184">Righe di lavoro che includono lavori di rifornimento incompiuti.</span><span class="sxs-lookup"><span data-stu-id="b9f47-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="b9f47-185">Prelievo eccessivo.</span><span class="sxs-lookup"><span data-stu-id="b9f47-185">Over-picking.</span></span>
