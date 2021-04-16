---
title: Raggruppamento righe prelievo
description: In questo argomento viene fornita una panoramica del raggruppamento delle righe prelievo.
author: Mirzaab
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: fe0e63ef742b7bfd09684a94d273a1841d24599c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828275"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="efa40-103">Raggruppamento righe prelievo</span><span class="sxs-lookup"><span data-stu-id="efa40-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efa40-104">Il raggruppamento delle righe di prelievo consente di combinare più righe di lavoro con lo stesso articolo e posizione in un unico prelievo che viene presentato all'utente sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="efa40-104">Pick line grouping enables multiple work lines that have the same item and location to be combined into a single pick that is presented to the user on the mobile device.</span></span> <span data-ttu-id="efa40-105">Pertanto, gli addetti al magazzino possono ricevere le istruzioni più efficienti possibili, ma viene mantenuta anche la necessaria separazione delle righe di lavoro nel sistema (ad esempio, per diversi contenitori, ordini e così via).</span><span class="sxs-lookup"><span data-stu-id="efa40-105">Therefore, warehouse workers can receive the most efficient instructions, but required work line separation (for different containers, orders, and so on) can still be maintained in the system.</span></span>

## <a name="turn-on-the-pick-line-grouping-feature"></a><span data-ttu-id="efa40-106">Attivare la funzionalità di raggruppamento delle righe di prelievo</span><span class="sxs-lookup"><span data-stu-id="efa40-106">Turn on the pick line grouping feature</span></span>

<span data-ttu-id="efa40-107">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="efa40-107">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="efa40-108">Gli amministratori possono utilizzare l'area di lavoro della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="efa40-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="efa40-109">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="efa40-109">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="efa40-110">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="efa40-110">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="efa40-111">**Nome funzionalità:** *Raggruppamento righe prelievo*</span><span class="sxs-lookup"><span data-stu-id="efa40-111">**Feature name:** *Pick line grouping*</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="efa40-112">Configurare il raggruppamento delle righe prelievo</span><span class="sxs-lookup"><span data-stu-id="efa40-112">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="efa40-113">Creare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="efa40-113">Create a mobile device menu item</span></span>

1. <span data-ttu-id="efa40-114">Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="efa40-114">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="efa40-115">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="efa40-115">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="efa40-116">Nel campo **Nome voce di menu**, immetti *Prelievo riga gruppo di vendita*.</span><span class="sxs-lookup"><span data-stu-id="efa40-116">In the **Menu item name** field, enter *Sales group line picking*.</span></span>
1. <span data-ttu-id="efa40-117">Nel campo **Titolo**, immetti *Prelievo riga gruppo di vendita*.</span><span class="sxs-lookup"><span data-stu-id="efa40-117">In the **Title** field, enter *Sales group line picking*.</span></span> <span data-ttu-id="efa40-118">Questo titolo verrà visualizzato nel menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="efa40-118">This title will be shown on the mobile device menu.</span></span>
1. <span data-ttu-id="efa40-119">Selezionare *Lavoro* nel campo **Modalità**.</span><span class="sxs-lookup"><span data-stu-id="efa40-119">In the **Mode** field, select *Work*.</span></span>
1. <span data-ttu-id="efa40-120">Impostare l'opzione **Utilizza lavoro esistente** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="efa40-120">Set the **Use existing work** option to *Yes*.</span></span>
1. <span data-ttu-id="efa40-121">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="efa40-121">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="efa40-122">Nel campo **Diretto da**, selezionare *Diretto dall'utente*.</span><span class="sxs-lookup"><span data-stu-id="efa40-122">In the **Directed by** field, select *User directed*.</span></span>
    - <span data-ttu-id="efa40-123">Impostare l'opzione **Genera targa** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="efa40-123">Set the **Generate license plate** option to *Yes*.</span></span>
    - <span data-ttu-id="efa40-124">Impostare l'opzione **Prelievo gruppo** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="efa40-124">Set the **Group pick** option to *Yes*.</span></span>
    - <span data-ttu-id="efa40-125">Accettare i valori predefiniti per le opzioni rimanenti.</span><span class="sxs-lookup"><span data-stu-id="efa40-125">Accept the default values for the remaining options.</span></span>

1. <span data-ttu-id="efa40-126">Seguire questi passaggi per configurare le classi di lavoro valide per la voce di menu del dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="efa40-126">Follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="efa40-127">Nella Scheda dettagli **Classi di lavoro**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="efa40-127">On the **Work classes** FastTab, elect **New**.</span></span>
    2. <span data-ttu-id="efa40-128">Nel campo **ID classe di lavoro**, è possibile selezionare *Vendite* o *Prelievo SO*, a seconda del magazzino che verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="efa40-128">In the **Work class ID** field, you can select either *Sales* or *SO Pick*, depending on the warehouse that you will use.</span></span> <span data-ttu-id="efa40-129">Per questo scenario, selezionare *Prelievo SO*.</span><span class="sxs-lookup"><span data-stu-id="efa40-129">For this scenario, select *SO Pick*.</span></span>

        <span data-ttu-id="efa40-130">Il campo **Tipo ordine di lavoro** viene automaticamente impostato su *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="efa40-130">The **Work order type** field is automatically set to *Sales orders*.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="efa40-131">Configurare un menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="efa40-131">Set up a mobile device menu</span></span>

<span data-ttu-id="efa40-132">Segui questi passaggi per aggiungere la voce di menu appena creata al file **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="efa40-132">Follow these steps to add the menu item that you just created to the **Outbound** menu.</span></span>

1. <span data-ttu-id="efa40-133">Accedi a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="efa40-133">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="efa40-134">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="efa40-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="efa40-135">Il riquadro dell'elenco mostra tutti i menu dei dispositivi mobili esistenti.</span><span class="sxs-lookup"><span data-stu-id="efa40-135">The list pane shows all existing mobile device menus.</span></span> <span data-ttu-id="efa40-136">Seleziona *In uscita* nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="efa40-136">Select *Outbound* in the list.</span></span>
1. <span data-ttu-id="efa40-137">Nell'elenco **Menu e voci di menu disponibili**, trovare e selezionare la voce di menu *Prelievo riga gruppo di vendita* appena creata.</span><span class="sxs-lookup"><span data-stu-id="efa40-137">In the **Available menus and menu items** list, find and select the *Sales group line picking* menu item that you created.</span></span>
1. <span data-ttu-id="efa40-138">Seleziona il pulsante freccia destra per spostare la voce di menu *Prelievo riga gruppo di vendita* sull'elenco **Struttura menu**.</span><span class="sxs-lookup"><span data-stu-id="efa40-138">Select the right arrow button to move the *Sales group line picking* menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="efa40-139">Utilizzare i pulsanti freccia su o freccia giù per spostare la voce di menu nella posizione desiderata nella struttura di menu.</span><span class="sxs-lookup"><span data-stu-id="efa40-139">Use the up arrow and down arrow buttons to move the menu item into the desired position in the menu structure.</span></span>
1. <span data-ttu-id="efa40-140">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="efa40-140">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="efa40-141">Configurare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="efa40-141">Set up a work template</span></span>

1. <span data-ttu-id="efa40-142">Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="efa40-142">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="efa40-143">Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="efa40-143">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="efa40-144">Nella griglia **Panoramica**, trovare e selezionare il modello di lavoro da utilizzare con questa funzione.</span><span class="sxs-lookup"><span data-stu-id="efa40-144">In the **Overview** grid, find and select the work template that should be used with this function.</span></span> <span data-ttu-id="efa40-145">Per questo scenario, selezionare il modello *51 prelievi da approntare*.</span><span class="sxs-lookup"><span data-stu-id="efa40-145">For this scenario, select the *51 Pick to stage* template.</span></span>
1. <span data-ttu-id="efa40-146">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="efa40-146">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="efa40-147">Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, selezionare **Aggiungi** e quindi impostare i seguenti valori per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="efa40-147">In the query editor dialog box, on the **Sorting** tab, select **Add**, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="efa40-148">Nella colonna **Tabella** selezionare *Transazioni lavoro temporanee*.</span><span class="sxs-lookup"><span data-stu-id="efa40-148">In the **Table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="efa40-149">Nella colonna **Tabella derivata** selezionare *Transazioni lavoro temporanee*.</span><span class="sxs-lookup"><span data-stu-id="efa40-149">In the **Derived table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="efa40-150">Nella colonna **Campo** selezionare *Numero articolo*.</span><span class="sxs-lookup"><span data-stu-id="efa40-150">In the **Field** column, select *Item number*.</span></span>
    - <span data-ttu-id="efa40-151">Nella colonna **Direzione di ricerca**, selezionare *Crescente*.</span><span class="sxs-lookup"><span data-stu-id="efa40-151">In the **Search direction** column, select *Ascending*.</span></span>

1. <span data-ttu-id="efa40-152">Selezionare **OK** per chiudere la finestra di dialogo e salvare la selezione.</span><span class="sxs-lookup"><span data-stu-id="efa40-152">Select **OK** to close the dialog box and save your selection.</span></span>
1. <span data-ttu-id="efa40-153">Viene visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?".</span><span class="sxs-lookup"><span data-stu-id="efa40-153">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="efa40-154">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="efa40-154">Select **Yes** to continue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efa40-155">Affinché la funzionalità di raggruppamento delle righe di prelievo funzioni, le righe di lavoro devono essere ordinate per ID articolo.</span><span class="sxs-lookup"><span data-stu-id="efa40-155">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="efa40-156">Se le righe che hanno gli stessi articoli non sono in sequenza una dopo l'altra, non verranno raggruppate.</span><span class="sxs-lookup"><span data-stu-id="efa40-156">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="efa40-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="efa40-157">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="efa40-158">Creare il lavoro di prelievo</span><span class="sxs-lookup"><span data-stu-id="efa40-158">Create picking work</span></span>

<span data-ttu-id="efa40-159">Prima di poter impostare il raggruppamento delle righe di prelievo, è necessario creare del lavoro in uscita idoneo.</span><span class="sxs-lookup"><span data-stu-id="efa40-159">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="efa40-160">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="efa40-160">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="efa40-161">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="efa40-161">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="efa40-162">Nel campo **Conto cliente** selezionare *US-004*.</span><span class="sxs-lookup"><span data-stu-id="efa40-162">In the **Customer account** field, select *US-004*.</span></span>
1. <span data-ttu-id="efa40-163">Nel campo **Magazzino** della Scheda dettaglio **Generale**, selezionare *51*.</span><span class="sxs-lookup"><span data-stu-id="efa40-163">On the **General** FastTab, in the **Warehouse** field, select *51*.</span></span>
1. <span data-ttu-id="efa40-164">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="efa40-164">Select **OK**.</span></span>
1. <span data-ttu-id="efa40-165">Nella Scheda dettagli **Righe ordine cliente**, aggiungere le sei righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="efa40-165">On the **Sales order lines** FastTab, add the following six lines:</span></span>

    - <span data-ttu-id="efa40-166">**Riga 1:** nel campo **Numero articolo** selezionare *M9200*.</span><span class="sxs-lookup"><span data-stu-id="efa40-166">**Line 1:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="efa40-167">Nel campo **Quantità** immettere *3*</span><span class="sxs-lookup"><span data-stu-id="efa40-167">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="efa40-168">**Riga 2:** nel campo **Numero articolo** selezionare *M9201*.</span><span class="sxs-lookup"><span data-stu-id="efa40-168">**Line 2:** In the **Item number** field, select *M9201*.</span></span> <span data-ttu-id="efa40-169">Nel campo **Quantità** immettere *3*</span><span class="sxs-lookup"><span data-stu-id="efa40-169">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="efa40-170">**Riga 3:** nel campo **Numero articolo** selezionare *M9202*.</span><span class="sxs-lookup"><span data-stu-id="efa40-170">**Line 3:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="efa40-171">Nel campo **Quantità** immettere *2*</span><span class="sxs-lookup"><span data-stu-id="efa40-171">In the **Quantity** field, enter *2*.</span></span>
    - <span data-ttu-id="efa40-172">**Riga 4:** nel campo **Numero articolo** selezionare *M9200*.</span><span class="sxs-lookup"><span data-stu-id="efa40-172">**Line 4:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="efa40-173">Nel campo **Quantità** immettere *1*</span><span class="sxs-lookup"><span data-stu-id="efa40-173">In the **Quantity** field, enter *1*.</span></span>
    - <span data-ttu-id="efa40-174">**Riga 5:** nel campo **Numero articolo** selezionare *M9200*.</span><span class="sxs-lookup"><span data-stu-id="efa40-174">**Line 5:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="efa40-175">Nel campo **Quantità** immettere *3*</span><span class="sxs-lookup"><span data-stu-id="efa40-175">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="efa40-176">**Riga 6:** nel campo **Numero articolo** selezionare *M9202*.</span><span class="sxs-lookup"><span data-stu-id="efa40-176">**Line 6:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="efa40-177">Nel campo **Quantità** immettere *7*</span><span class="sxs-lookup"><span data-stu-id="efa40-177">In the **Quantity** field, enter *7*.</span></span>

    <span data-ttu-id="efa40-178">Ecco un riepilogo delle quantità totali per ciascun articolo:</span><span class="sxs-lookup"><span data-stu-id="efa40-178">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="efa40-179">**Articolo M9200:** *7* ciascuno</span><span class="sxs-lookup"><span data-stu-id="efa40-179">**Item M9200:** *7* each</span></span>
    - <span data-ttu-id="efa40-180">**Articolo M9201:** *3* ciascuno</span><span class="sxs-lookup"><span data-stu-id="efa40-180">**Item M9201:** *3* each</span></span>
    - <span data-ttu-id="efa40-181">**Articolo M9202:** *9* ciascuno</span><span class="sxs-lookup"><span data-stu-id="efa40-181">**Item M9202:** *9* each</span></span>

1. <span data-ttu-id="efa40-182">Prima di rilasciare gli ordini al magazzino, è necessario assicurarsi che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli di tutti gli ordini.</span><span class="sxs-lookup"><span data-stu-id="efa40-182">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="efa40-183">Rivedere l'impostazione **Direttiva ubicazione** per determinare quali ubicazioni di prelievo vengono utilizzate per il prelievo dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="efa40-183">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span> <span data-ttu-id="efa40-184">Se stai usando l'ambiente di dati demo Contoso per il magazzino *51*, verifica che ci siano scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="efa40-184">If you're using the Contoso demo data environment for warehouse *51*, confirm that there is available inventory.</span></span>

    <span data-ttu-id="efa40-185">È ora necessario prenotare le scorte per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="efa40-185">You must now reserve the inventory for each line.</span></span>

1. <span data-ttu-id="efa40-186">Nella Scheda dettaglio **Righe ordine cliente**, seleziona una delle righe da prenotare.</span><span class="sxs-lookup"><span data-stu-id="efa40-186">On the **Sales order lines** FastTab, select one of the lines that must be reserved.</span></span>
1. <span data-ttu-id="efa40-187">Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="efa40-187">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="efa40-188">Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per applicare la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="efa40-188">On the **Reservation** page, on the Action Pane, select **Reserve lot** to apply the reservation.</span></span> <span data-ttu-id="efa40-189">Quindi, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="efa40-189">Then close the page.</span></span>
1. <span data-ttu-id="efa40-190">Ripetere i passaggi da 8 a 10 per le righe rimanenti che devono essere prenotate.</span><span class="sxs-lookup"><span data-stu-id="efa40-190">Repeat steps 8 through 10 for the remaining lines that must be reserved.</span></span>

    <span data-ttu-id="efa40-191">È necessario ora rilasciare l'ordine cliente al magazzino.</span><span class="sxs-lookup"><span data-stu-id="efa40-191">You must now release the sales order to the warehouse.</span></span>

1. <span data-ttu-id="efa40-192">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="efa40-192">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="efa40-193">Si riceve un messaggio che informa che una spedizione e un ciclo sono stati creati e che il ciclo è stato inviato per essere eseguito in batch.</span><span class="sxs-lookup"><span data-stu-id="efa40-193">You receive a message that states that a shipment and a wave have been created, and that the wave has been submitted to run in a batch.</span></span>

    <span data-ttu-id="efa40-194">Quando il ciclo e tutti i processi a valle sono stati completati, viene creato un ID lavoro per il lavoro che ha sei righe.</span><span class="sxs-lookup"><span data-stu-id="efa40-194">When the wave and all downstream jobs have been completed, a work ID is created for work that has six lines.</span></span> <span data-ttu-id="efa40-195">Le righe sono ordinate per numero articolo.</span><span class="sxs-lookup"><span data-stu-id="efa40-195">The lines are sorted by item number.</span></span>

1. <span data-ttu-id="efa40-196">Passare a **Gestione magazzino \> Lavoro \> Tutti i lavori** per visualizzare tutti i lavori creati.</span><span class="sxs-lookup"><span data-stu-id="efa40-196">Go to **Warehouse management \> Work \> All work** to view the work that was created.</span></span> <span data-ttu-id="efa40-197">Prendere nota del valore **ID lavoro**, in modo da poterlo utilizzare nella procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="efa40-197">Make a note of the **Work ID** value, because you will need it in the next procedure.</span></span>

### <a name="initiate-picking-from-the-mobile-device"></a><span data-ttu-id="efa40-198">Avviare il prelievo dal dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="efa40-198">Initiate picking from the mobile device</span></span>

1. <span data-ttu-id="efa40-199">Accedere al dispositivo mobile come utente configurato per il magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="efa40-199">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="efa40-200">Sul dispositivo mobile, selezionare il menu che include la nuova voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="efa40-200">On the mobile device, select the menu that includes the new mobile device menu item.</span></span> <span data-ttu-id="efa40-201">Per questo scenario, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="efa40-201">For this scenario, select **Outbound**.</span></span>
1. <span data-ttu-id="efa40-202">Selezionare la voce di menu **Prelievo riga gruppo di vendita** per avviare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="efa40-202">Select the **Sales group line picking** menu item to initiate the pick.</span></span>
1. <span data-ttu-id="efa40-203">Immetti il valore **ID lavoro** di cui hai preso nota nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="efa40-203">Enter the **Work ID** value that you made a note of in the previous procedure.</span></span>

    <span data-ttu-id="efa40-204">Dovresti vedere un passaggio di prelievo in cui tutte le righe di prelievo per l'articolo *M9200* sono raggruppate e dovresti ricevere un'istruzione per scegliere *7* per ognuno degli articoli *M9200*.</span><span class="sxs-lookup"><span data-stu-id="efa40-204">You should see a pick step where all pick lines for item *M9200* are grouped, and you should receive an instruction to pick *7* each of item *M9200*.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="efa40-205">Sul dispositivo mobile, il lavoro di prelievo per le tre righe di lavoro di prelievo è stato aggregato in un unico passaggio di prelievo per l'utente.</span><span class="sxs-lookup"><span data-stu-id="efa40-205">On the mobile device, the pick work for the three pick work lines has been aggregated into one picking step for the user.</span></span>

1. <span data-ttu-id="efa40-206">Confermare il passaggio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="efa40-206">Confirm the pick step.</span></span>
1. <span data-ttu-id="efa40-207">Passare alla pagina del lavoro per l'ID lavoro e prendere nota che tutte e tre le righe di prelievo per l'articolo *M9200* sono state chiuse contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="efa40-207">Go to the work page for the work ID, and notice that all three pick lines for item *M9200* were closed simultaneously.</span></span>
1. <span data-ttu-id="efa40-208">Tornare al dispositivo mobile e continuare con il prelievo.</span><span class="sxs-lookup"><span data-stu-id="efa40-208">Go back to the mobile device, and continue to pick.</span></span> <span data-ttu-id="efa40-209">Dovrebbe essere visualizzata la riga di lavoro 4 per l'articolo *M9201*.</span><span class="sxs-lookup"><span data-stu-id="efa40-209">Work line 4 for item *M9201* should be presented.</span></span> <span data-ttu-id="efa40-210">Poiché nell'ordine era presente una sola riga di lavoro, non c'è nulla da aggregare.</span><span class="sxs-lookup"><span data-stu-id="efa40-210">Because there was only one work line on the order, there is nothing to aggregate.</span></span>
1. <span data-ttu-id="efa40-211">Confermare il passaggio di prelievo.</span><span class="sxs-lookup"><span data-stu-id="efa40-211">Confirm the pick step.</span></span>
1. <span data-ttu-id="efa40-212">L'ultimo passaggio di prelievo sul dispositivo mobile aggrega le ultime due righe di prelievo dall'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="efa40-212">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>
1. <span data-ttu-id="efa40-213">Completare il passaggio di prelievo per *9* ciascuno dell'articolo *M9202*.</span><span class="sxs-lookup"><span data-stu-id="efa40-213">Complete the pick step for *9* each of item *M9202*.</span></span>
1. <span data-ttu-id="efa40-214">Confermare il passaggio di inserimento e tutte le coppie di prelievo/inserimento aggiuntive per completare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="efa40-214">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="efa40-215">Le righe di lavoro possono essere raggruppate solo se sono in sequenza.</span><span class="sxs-lookup"><span data-stu-id="efa40-215">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="efa40-216">Sono supportate le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="efa40-216">The following functionality isn't supported:</span></span>
>
>   - <span data-ttu-id="efa40-217">Articoli a peso variabile</span><span class="sxs-lookup"><span data-stu-id="efa40-217">Catch-weight items</span></span>
>
>    <span data-ttu-id="efa40-218">Se sul lavoro sono presenti articoli a peso variabile, riceverai un messaggio di errore prima di iniziare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="efa40-218">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>
>   - <span data-ttu-id="efa40-219">Prelievo di pezzi</span><span class="sxs-lookup"><span data-stu-id="efa40-219">Piece picking</span></span>
>   - <span data-ttu-id="efa40-220">Righe di lavoro che includono lavori di rifornimento incompiuti</span><span class="sxs-lookup"><span data-stu-id="efa40-220">Work lines that have unfinished replenishment work</span></span>
>   - <span data-ttu-id="efa40-221">Prelievo eccessivo</span><span class="sxs-lookup"><span data-stu-id="efa40-221">Over-picking</span></span>
>   - <span data-ttu-id="efa40-222">Prelievo breve con riallocazione articolo</span><span class="sxs-lookup"><span data-stu-id="efa40-222">Short picking with item reallocation</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]