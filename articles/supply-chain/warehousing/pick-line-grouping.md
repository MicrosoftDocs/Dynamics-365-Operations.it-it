---
title: Raggruppamento righe prelievo
description: In questo argomento viene fornita una panoramica del raggruppamento delle righe prelievo.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1b1d0135d450bc9be7b1303240a9ca70f95ae38e
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906270"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="aefdb-103">Raggruppamento righe prelievo</span><span class="sxs-lookup"><span data-stu-id="aefdb-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aefdb-104">Nel raggruppamento delle righe di prelievo, è possibile combinare più righe di lavoro con lo stesso articolo e posizione in un unico prelievo che viene presentato all'utente su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="aefdb-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="aefdb-105">Pertanto, gli addetti al magazzino possono ricevere le istruzioni più efficienti possibili, ma viene mantenuta anche la necessaria separazione delle righe di lavoro nel sistema (ad esempio, per diversi contenitori e ordini).</span><span class="sxs-lookup"><span data-stu-id="aefdb-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="aefdb-106">Configurare il raggruppamento delle righe prelievo</span><span class="sxs-lookup"><span data-stu-id="aefdb-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="aefdb-107">Creare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="aefdb-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="aefdb-108">Andare a **Gestione magazzino \>Impostazione \>Dispositivo mobile \>Voci di menu del dispositivo mobile** e creare una nuova voce di menu denominata **Prelievo riga gruppo di vendita - Utente diretto**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**, and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="aefdb-109">In **Voci di menu del dispositivo mobile**, impostare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="aefdb-109">Under **Mobile device menu items**, set the following values:</span></span>

    - <span data-ttu-id="aefdb-110">Nel campo **Nome voce di menu**, immettere **Prelievo vendite - Riga gruppo**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="aefdb-111">Nel campo **Titolo**, immetti **Prelievo vendite - Riga gruppo**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="aefdb-112">Selezionare **Lavoro** nel campo **Modalità**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="aefdb-113">Impostare l'opzione **Utilizza lavoro esistente** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="aefdb-114">Nella scheda Dettagli **Generale**, è possibile impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="aefdb-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="aefdb-115">Nel campo **Diretto da**, selezionare **Diretto dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="aefdb-116">Impostare l'opzione **Genera targa** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="aefdb-117">Impostare l'opzione **Prelievo gruppo** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="aefdb-118">Nella Scheda dettagli **Classi di lavoro**, seguire questi passaggi per configurare le classi di lavoro valide per la voce di menu del dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="aefdb-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="aefdb-119">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-119">Select **New**.</span></span>
    2. <span data-ttu-id="aefdb-120">Nel campo **ID classe di lavoro**, selezionare **Vendite** o **Prelievo SO**, a seconda del magazzino che verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="aefdb-120">In the **Work class ID** field, select **Sales** or **SO Pick**, depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="aefdb-121">Nel campo **Tipo ordine di lavoro** selezionare **Ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="aefdb-122">Configurare un menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="aefdb-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="aefdb-123">Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="aefdb-124">Aggiungere la voce di menu appena creata al menu desiderato.</span><span class="sxs-lookup"><span data-stu-id="aefdb-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="aefdb-125">Configurare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="aefdb-125">Set up a work template</span></span>

1. <span data-ttu-id="aefdb-126">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="aefdb-127">Trovare il modello di lavoro da utilizzare con questa funzione.</span><span class="sxs-lookup"><span data-stu-id="aefdb-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="aefdb-128">Per questo esempio, selezionare il modello di lavoro Contoso **51 prelievi da approntare** standard.</span><span class="sxs-lookup"><span data-stu-id="aefdb-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="aefdb-129">Nel menu, selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="aefdb-130">Nella scheda **Ordinamento**, selezionare **Aggiungi** e quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="aefdb-130">On the **Sorting** tab, select **Add**, and then set the following values:</span></span>

    - <span data-ttu-id="aefdb-131">Nel campo **Tabella** selezionare **Transazioni lavoro temporanee**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="aefdb-132">Nel campo **Tabella derivata** selezionare **Transazioni lavoro temporanee**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="aefdb-133">Nel campo **Campo** selezionare **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="aefdb-134">Nel campo **Direzione di ricerca**, selezionare **Crescente**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="aefdb-135">Affinché la funzionalità di raggruppamento delle righe di prelievo funzioni, le righe di lavoro devono essere ordinate per ID articolo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="aefdb-136">Se le righe che hanno gli stessi articoli non sono in sequenza una dopo l'altra, non verranno raggruppate.</span><span class="sxs-lookup"><span data-stu-id="aefdb-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="aefdb-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="aefdb-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="aefdb-138">Creare il lavoro di prelievo</span><span class="sxs-lookup"><span data-stu-id="aefdb-138">Create picking work</span></span>

<span data-ttu-id="aefdb-139">Prima di poter impostare il raggruppamento delle righe di prelievo, è necessario creare del lavoro in uscita idoneo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="aefdb-140">Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="aefdb-141">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="aefdb-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="aefdb-142">Nel campo **Conto cliente** selezionare qualsiasi cliente.</span><span class="sxs-lookup"><span data-stu-id="aefdb-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="aefdb-143">Nel campo **Magazzino** della Scheda dettaglio **Generale**, selezionare **51**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="aefdb-144">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-144">Then select **OK**.</span></span>
5. <span data-ttu-id="aefdb-145">In **Righe ordine cliente**, aggiungere le sei righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="aefdb-145">Under **Sales order lines**, add the following six lines:</span></span>

    - <span data-ttu-id="aefdb-146">**Riga 1:** nel campo **Numero articolo** selezionare **M9200**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="aefdb-147">Nel campo **Quantità** immettere **3**</span><span class="sxs-lookup"><span data-stu-id="aefdb-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="aefdb-148">**Riga 2:** nel campo **Numero articolo** selezionare **M9201**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="aefdb-149">Nel campo **Quantità** immettere **3**</span><span class="sxs-lookup"><span data-stu-id="aefdb-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="aefdb-150">**Riga 3:** nel campo **Numero articolo** selezionare **M9202**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="aefdb-151">Nel campo **Quantità** immettere **2**</span><span class="sxs-lookup"><span data-stu-id="aefdb-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="aefdb-152">**Riga 4:** nel campo **Numero articolo** selezionare **M9200**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="aefdb-153">Nel campo **Quantità** immettere **1**</span><span class="sxs-lookup"><span data-stu-id="aefdb-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="aefdb-154">**Riga 5:** nel campo **Numero articolo** selezionare **M9200**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="aefdb-155">Nel campo **Quantità** immettere **3**</span><span class="sxs-lookup"><span data-stu-id="aefdb-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="aefdb-156">**Riga 6:** nel campo **Numero articolo** selezionare **M9202**.</span><span class="sxs-lookup"><span data-stu-id="aefdb-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="aefdb-157">Nel campo **Quantità** immettere **7**</span><span class="sxs-lookup"><span data-stu-id="aefdb-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="aefdb-158">Ecco un riepilogo delle quantità totali per ciascun articolo:</span><span class="sxs-lookup"><span data-stu-id="aefdb-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="aefdb-159">**Articolo M9200:** 7 ciascuno</span><span class="sxs-lookup"><span data-stu-id="aefdb-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="aefdb-160">**Articolo M9201:** 3 ciascuno</span><span class="sxs-lookup"><span data-stu-id="aefdb-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="aefdb-161">**Articolo M9202:** 9 ciascuno</span><span class="sxs-lookup"><span data-stu-id="aefdb-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="aefdb-162">Prima di rilasciare gli ordini al magazzino, è necessario assicurarsi che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli di tutti gli ordini.</span><span class="sxs-lookup"><span data-stu-id="aefdb-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="aefdb-163">Rivedere l'impostazione **Direttiva ubicazione** per determinare quali ubicazioni di prelievo vengono utilizzate per il prelievo dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="aefdb-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="aefdb-164">Prenotare le scorte e rilasciarle al magazzino.</span><span class="sxs-lookup"><span data-stu-id="aefdb-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="aefdb-165">Viene creato un ID lavoro con sei righe.</span><span class="sxs-lookup"><span data-stu-id="aefdb-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="aefdb-166">Le righe sono ordinate per numero articolo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="aefdb-167">Eseguire il flussi del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="aefdb-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="aefdb-168">Sul dispositivo mobile, selezionare il menu che include la nuova voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="aefdb-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="aefdb-169">Selezionare la voce di menu **Prelievo vendite - Riga gruppo** e avviare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="aefdb-170">Dopo aver selezionato il menu e inserito l'ID lavoro, viene visualizzato il passaggio di prelievo in cui sono raggruppate tutte le righe di prelievo per l'articolo M9200.</span><span class="sxs-lookup"><span data-stu-id="aefdb-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="aefdb-171">Si riceve quindi l'istruzione per prelevare scegliere 7 quantità dell'articolo M9200.</span><span class="sxs-lookup"><span data-stu-id="aefdb-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="aefdb-172">Confermare il passaggio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="aefdb-173">Passare alla schermata client del lavoro in corso e prendere nota che tutte e tre le righe di prelievo per l'articolo M9200 sono state chiuse contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="aefdb-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="aefdb-174">Viene presentata la riga di lavoro 4.</span><span class="sxs-lookup"><span data-stu-id="aefdb-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="aefdb-175">Confermare il passaggio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-175">Confirm the pick step.</span></span>

    <span data-ttu-id="aefdb-176">L'ultimo passaggio di prelievo sul dispositivo mobile aggrega le ultime due righe di prelievo dall'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="aefdb-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="aefdb-177">Completare il passaggio di prelievo per 9 ciascuno dell'articolo M9202.</span><span class="sxs-lookup"><span data-stu-id="aefdb-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="aefdb-178">Confermare il passaggio di inserimento e tutte le coppie di prelievo/inserimento aggiuntive per completare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="aefdb-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="aefdb-179">Le righe di lavoro possono essere raggruppate solo se sono in sequenza.</span><span class="sxs-lookup"><span data-stu-id="aefdb-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="aefdb-180">Sono supportate le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="aefdb-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="aefdb-181">Articoli a peso variabile.</span><span class="sxs-lookup"><span data-stu-id="aefdb-181">Catch-weight items.</span></span> <span data-ttu-id="aefdb-182">Se sul lavoro sono presenti articoli a peso variabile, riceverai un messaggio di errore prima di iniziare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="aefdb-183">Prelievo di pezzi.</span><span class="sxs-lookup"><span data-stu-id="aefdb-183">Piece picking.</span></span>
>    - <span data-ttu-id="aefdb-184">Righe di lavoro che includono lavori di rifornimento incompiuti.</span><span class="sxs-lookup"><span data-stu-id="aefdb-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="aefdb-185">Prelievo eccessivo.</span><span class="sxs-lookup"><span data-stu-id="aefdb-185">Over-picking.</span></span>
