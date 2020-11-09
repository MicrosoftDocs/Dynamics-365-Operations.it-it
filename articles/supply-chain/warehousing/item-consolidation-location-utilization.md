---
title: Consolidamento degli articoli e utilizzo delle ubicazioni
description: Questo argomento fornisce informazioni sulle funzionalità che semplificano la visualizzazione e il filtraggio dell'utilizzo volumetrico delle ubicazioni nel magazzino per i responsabili del magazzino. I responsabili possono selezionare le ubicazioni e creare attività di movimentazione delle scorte direttamente dalla pagina Consolidamento articoli per consolidare gli articoli e quindi sfruttare meglio lo spazio del magazzino.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a328b20c1cfb2fc376ab4656c64cf585a5aa015
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017186"
---
# <a name="item-consolidation---location-utilization"></a><span data-ttu-id="ccbcb-104">Consolidamento degli articoli e utilizzo delle ubicazioni</span><span class="sxs-lookup"><span data-stu-id="ccbcb-104">Item consolidation - location utilization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccbcb-105">Questo argomento fornisce informazioni sulle funzionalità che semplificano la visualizzazione e il filtraggio dell'utilizzo volumetrico delle ubicazioni nel magazzino per i responsabili del magazzino.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-105">This topic provides information about functionality that makes it easy for warehouse managers to view and filter the volumetric utilization of locations across the warehouse.</span></span> <span data-ttu-id="ccbcb-106">I responsabili possono selezionare le ubicazioni e creare attività di movimentazione delle scorte direttamente dalla pagina **Consolidamento articoli** per consolidare gli articoli e quindi sfruttare meglio lo spazio del magazzino.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-106">Managers can select locations and create inventory movement work directly from the **Item Consolidation** page to consolidate items and therefore make better use of warehouse space.</span></span>

## <a name="turn-on-the-features"></a><span data-ttu-id="ccbcb-107">Attivare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="ccbcb-107">Turn on the features</span></span>

<span data-ttu-id="ccbcb-108">Prima di poter utilizzare le funzionalità descritte in questo argomento, è necessario attivarle nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-108">Before you can use the features that are described in this topic, you must turn them on in your system.</span></span> <span data-ttu-id="ccbcb-109">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle funzionalità e attivarle se sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="ccbcb-110">Attivare entrambe le funzionalità seguenti, nell'ordine indicato</span><span class="sxs-lookup"><span data-stu-id="ccbcb-110">Turn on both the following features, in the order that they are listed in.</span></span> <span data-ttu-id="ccbcb-111">(entrambe le funzionalità sono per il modulo **Gestione magazzino** ).</span><span class="sxs-lookup"><span data-stu-id="ccbcb-111">(Both features are for the **Warehouse management** module.)</span></span>

1. <span data-ttu-id="ccbcb-112">Stato ubicazione magazzino</span><span class="sxs-lookup"><span data-stu-id="ccbcb-112">Warehouse location status</span></span>
2. <span data-ttu-id="ccbcb-113">Utilizzo ubicazione consolidamento articolo</span><span class="sxs-lookup"><span data-stu-id="ccbcb-113">Item consolidation location utilization</span></span>

## <a name="warehouse-location-status"></a><span data-ttu-id="ccbcb-114">Stato ubicazione magazzino</span><span class="sxs-lookup"><span data-stu-id="ccbcb-114">Warehouse location status</span></span>

<span data-ttu-id="ccbcb-115">La funzionalità *SStato ubicazione magazzino* aggiunge quattro nuovi campi alla pagina **Ubicazioni** per tenere traccia di ulteriori informazioni sullo stato corrente dell'ubicazione:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-115">The *Warehouse location status* feature adds four new fields to the **Locations** page to track additional information about the current state of the location:</span></span>

- <span data-ttu-id="ccbcb-116">**Numero articolo** : l'articolo che si trova attualmente nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-116">**Item number** – The item that is currently in the location.</span></span> <span data-ttu-id="ccbcb-117">Se l'ubicazione contiene più articoli, questo campo sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-117">If the location contains multiple items, this field will be blank.</span></span>
- <span data-ttu-id="ccbcb-118">**Data e ora dell'ultima attività** : il timestamp dell'ultima transazione di magazzino eseguita a fronte dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-118">**Last activity date and time** – The timestamp of the last warehouse transaction that was performed against the location.</span></span>
- <span data-ttu-id="ccbcb-119">**Data di aging** : la data in cui le scorte nell'ubicazione sono state portate nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-119">**Aging date** – The date when the inventory in the location was brought into the warehouse.</span></span> <span data-ttu-id="ccbcb-120">Questa data viene calcolata in base alla data di aging della targa.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-120">This date is calculated based on the license plate aging date.</span></span> <span data-ttu-id="ccbcb-121">Sebbene questa data sia precisa per le ubicazioni tracciate in base alla targa, potrebbe non essere precisa per le ubicazioni che non sono tracciate in base alla targa.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-121">Although this date is accurate for license plate–tracked locations, it might not be accurate for locations that aren't license plate–tracked.</span></span>
- <span data-ttu-id="ccbcb-122">**Stato ubicazione** : lo stato dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-122">**Location status** – The status of the location.</span></span> <span data-ttu-id="ccbcb-123">I valori disponibili sono quattro:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-123">Four values are available:</span></span>

    - <span data-ttu-id="ccbcb-124">**Indeterminato** : il profilo dell'ubicazione non tiene traccia dello stato.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-124">**Undetermined** – The location profile doesn't track status.</span></span> <span data-ttu-id="ccbcb-125">Pertanto, lo stato corrente è sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-125">Therefore, the current status is unknown.</span></span>
    - <span data-ttu-id="ccbcb-126">**Vuoto** : al momento non ci sono scorte nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-126">**Empty** – No inventory is currently in the location.</span></span>
    - <span data-ttu-id="ccbcb-127">**Prelievo** : sono state eseguite transazioni in uscita a fronte dell'ubicazione dall'ultima volta in cui era vuota.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-127">**Picking** – Outbound transactions have been performed against the location after it was last empty.</span></span>
    - <span data-ttu-id="ccbcb-128">**Immagazzinamento** : sono state eseguite transazioni in entrata dall'ultima volta in cui l'ubicazione era vuota.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-128">**Storage** – Only inbound transactions have been performed since the location was last empty.</span></span>

<span data-ttu-id="ccbcb-129">Questi campi consentono ai responsabili del magazzino di ottenere una migliore panoramica dello stato delle ubicazioni nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-129">These fields let warehouse managers get a better overview of the status of the locations in the warehouse.</span></span> <span data-ttu-id="ccbcb-130">Consentono inoltre l'uso di report e filtri più avanzati.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-130">They also allow for more advanced reporting and filtering.</span></span>

## <a name="set-up-item-consolidation-and-location-utilization"></a><span data-ttu-id="ccbcb-131">Configurare il consolidamento degli articoli e l'utilizzo delle ubicazioni</span><span class="sxs-lookup"><span data-stu-id="ccbcb-131">Set up item consolidation and location utilization</span></span>

<span data-ttu-id="ccbcb-132">Questa sezione descrive come preparare il sistema all'uso del consolidamento degli articoli e dell'utilizzo delle ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-132">This section describes how to prepare your system to use item consolidation and location utilization.</span></span> <span data-ttu-id="ccbcb-133">Le procedure utilizzano valori campione dei dati demo standard.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-133">The procedures use sample values from the standard demo data.</span></span> <span data-ttu-id="ccbcb-134">Se si prevede di utilizzare lo scenario di esempio fornito più avanti in questo argomento, selezionare la persona giuridica **USMF** (che contiene i dati demo standard) e creare ogni record descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-134">If you plan to work through the example scenario that is provided later in this topic, select the **USMF** legal entity (which contains the standard demo data), and create each record that is described in this section.</span></span> <span data-ttu-id="ccbcb-135">Se non si prevede di utilizzare lo scenario di esempio, i valori forniti qui possono essere considerati esempi dei tipi di configurazione che è necessario completare per utilizzare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-135">If you don't plan to work through the example scenario, the values that are provided here can be considered examples of the types of setup that you must complete to use the features.</span></span>

### <a name="released-product"></a><span data-ttu-id="ccbcb-136">Prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="ccbcb-136">Released product</span></span>

1. <span data-ttu-id="ccbcb-137">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-137">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="ccbcb-138">Nel campo **Numero articolo** , selezionare *M9201* e aprire la pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-138">In the **Item number** field, select *M9201* , and open the details page.</span></span>
1. <span data-ttu-id="ccbcb-139">Nel riquadro azioni della scheda **Gestione articoli** , nel gruppo **Magazzino** , selezionare **Dimensioni fisiche**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-139">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="ccbcb-140">Nella pagina **Dimensioni fisiche** , nel riquadro azioni, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-140">On the **Physical dimension** page, on the Action Pane, select **New**.</span></span>

    <span data-ttu-id="ccbcb-141">Una nuova riga viene aggiunta alla griglia.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-141">A new line is added to the grid.</span></span> <span data-ttu-id="ccbcb-142">Il campo **Numero articolo** è preimpostato.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-142">The **Item number** field is preset.</span></span>

1. <span data-ttu-id="ccbcb-143">Nel campo **Unità** selezionare *unità*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-143">In the **Unit** field, select *ea*.</span></span> <span data-ttu-id="ccbcb-144">I campi rimanenti sulla riga vengono impostati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-144">The remaining fields on the line are automatically set.</span></span>
1. <span data-ttu-id="ccbcb-145">Selezionare **Salva** , quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-145">Select **Save** , and close the page.</span></span>

### <a name="location-profile"></a><span data-ttu-id="ccbcb-146">Profilo ubicazione</span><span class="sxs-lookup"><span data-stu-id="ccbcb-146">Location profile</span></span>

1. <span data-ttu-id="ccbcb-147">Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-147">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="ccbcb-148">Nell'elenco dei profili di ubicazione, seleziona **FLOOR-05**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-148">In the list of location profiles, select **FLOOR-05**.</span></span>
1. <span data-ttu-id="ccbcb-149">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-149">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ccbcb-150">Nella Scheda dettaglio **Generale** , assicurarsi che entrambe le seguenti opzioni siano impostate su *Sì* :</span><span class="sxs-lookup"><span data-stu-id="ccbcb-150">On the **General** FastTab, make sure that both the following options are set to *Yes* :</span></span>

    - <span data-ttu-id="ccbcb-151">Abilita articolo nell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="ccbcb-151">Enable item in location</span></span>
    - <span data-ttu-id="ccbcb-152">Abilita stato ubicazione</span><span class="sxs-lookup"><span data-stu-id="ccbcb-152">Enable location status</span></span>

1. <span data-ttu-id="ccbcb-153">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-153">Select **Save**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ccbcb-154">Se le opzioni **Abilita articolo nell'ubicazione** e **Abilita stato ubicazione** sono già impostate su *Sì* , passare alle istruzioni per la configurazione della Scheda Dettaglio **Dimensioni** nel passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-154">If the **Enable item in location** and **Enable location status** options were already set to *Yes* , skip ahead to the instructions for setting up the **Dimensions** FastTab in step 10.</span></span> <span data-ttu-id="ccbcb-155">Se le opzioni non sono già impostate su *Sì* , è necessario eseguire una verifica di coerenza per il modulo **Gestione magazzino** dopo averle impostate manualmente.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-155">If the options weren't already set to *Yes* , you must run a consistency check for the **Warehouse management** module after you manually set them.</span></span> <span data-ttu-id="ccbcb-156">In questo caso, andare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-156">In this case, continue to the next step.</span></span>

1. <span data-ttu-id="ccbcb-157">Per eseguire la verifica di coerenza, andare a **Amministrazione sistema \> Attività periodiche \> Database \> Verifica coerenza**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-157">To run the consistency check, go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="ccbcb-158">Nella finestra di dialogo **Verifica coerenza** , impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-158">In the **Consistency check** dialog box, set the following values:</span></span>

    - <span data-ttu-id="ccbcb-159">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-159">**Module:** *Warehouse management*</span></span>
    - <span data-ttu-id="ccbcb-160">**Verifica/Correggi:** *Verifica*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-160">**Check/Fix:** *Check*</span></span>
    - <span data-ttu-id="ccbcb-161">**Dal** : lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-161">**From date:** Leave this field blank.</span></span>
    - <span data-ttu-id="ccbcb-162">**Verifica di coerenza stato ubicazione magazzino:** selezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-162">**Warehouse location status consistency check:** Select this check box.</span></span>

1. <span data-ttu-id="ccbcb-163">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-163">Select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="ccbcb-164">Al termine della verifica di coerenza, viene visualizzata una notifica..</span><span class="sxs-lookup"><span data-stu-id="ccbcb-164">When the consistency check is completed, you receive a notification.</span></span> <span data-ttu-id="ccbcb-165">Aprire il [Centro azioni](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) per visualizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-165">Open the [Action Center](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) to view the message.</span></span> <span data-ttu-id="ccbcb-166">Selezionare **Dettagli messaggio** per visualizzare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-166">Select **Message details** to view the details.</span></span>
    >
    > <span data-ttu-id="ccbcb-167">Se il messaggio per la verifica di coerenza indica "Informazioni sullo stato dell'ubicazione errate trovate per l'ubicazione XXXX nel magazzino XX", è necessario eseguire nuovamente la verifica di coerenza.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-167">If the message for the consistency check states, "Incorrect location status information found for location XXXX in warehouse XX," you must run the consistency check again.</span></span> <span data-ttu-id="ccbcb-168">Questa volta, impostare il campo **Verifica/Correggi** su *Correggi errore*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-168">This time, set the **Check/Fix** field to *Fix error*.</span></span> <span data-ttu-id="ccbcb-169">Visualizzare i messaggi per assicurarsi che non siano stati rilevati errori.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-169">View the messages to make sure that no errors were found.</span></span>

1. <span data-ttu-id="ccbcb-170">Ora è necessario completare la configurazione del profilo dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-170">You must now finish setting up the location profile.</span></span> <span data-ttu-id="ccbcb-171">Tornare a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione** , selezionare il profilo di ubicazione **PIANO-05** , quindi, nel riquadro azioni, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-171">Go back to **Warehouse management \> Setup \> Warehouse \> Location profiles** , select location profile **FLOOR-05** , and then, on the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ccbcb-172">Nella Scheda dettaglio **Dimensioni** , impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-172">On the **Dimensions** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ccbcb-173">**Percentuale di utilizzo volume:** *100*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-173">**Volume utilization percentage:** *100*</span></span>
    - <span data-ttu-id="ccbcb-174">**Metodo volumetrico usato per ubicazione di magazzino:** *Usa volume ubicazione*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-174">**Volumetric method used for inventory location:** *Use location volume*</span></span>
    - <span data-ttu-id="ccbcb-175">**Altezza effettiva ubicazione:** *10*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-175">**Actual location height:** *10*</span></span>
    - <span data-ttu-id="ccbcb-176">**Larghezza effettiva ubicazione:** *10*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-176">**Actual location width:** *10*</span></span>
    - <span data-ttu-id="ccbcb-177">**Profondità effettiva ubicazione:** *10*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-177">**Actual location depth:** *10*</span></span>
    - <span data-ttu-id="ccbcb-178">**Peso massimo:** *100*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-178">**Maximum weight:** *100*</span></span>

1. <span data-ttu-id="ccbcb-179">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-179">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="ccbcb-180">Voci di menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="ccbcb-180">Mobile device menu items</span></span>

1. <span data-ttu-id="ccbcb-181">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-181">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="ccbcb-182">Nel riquadro azioni selezionare **Nuovo** per creare una voce di menu per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-182">On the Action Pane, select **New** to create a menu item for sorting.</span></span>
1. <span data-ttu-id="ccbcb-183">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-183">In the header, set the following values:</span></span>

    - <span data-ttu-id="ccbcb-184">**Nome voce di menu:** *Rettifica in entrata*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-184">**Menu item name:** *Adjust In*</span></span>
    - <span data-ttu-id="ccbcb-185">**Titolo:** *Rettifica in entrata*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-185">**Title:** *Adjust In*</span></span>
    - <span data-ttu-id="ccbcb-186">**Modalità:** *Lavoro*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-186">**Mode:** *Work*</span></span>
    - <span data-ttu-id="ccbcb-187">**Utilizza lavoro esistente:** *No*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-187">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="ccbcb-188">Nella Scheda dettaglio **Generale** , imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-188">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ccbcb-189">**Processo di creazione lavoro:** *Rettifica in entrata*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-189">**Work creation process:** *Adjustment in*</span></span>
    - <span data-ttu-id="ccbcb-190">**Tipi di rettifica magazzino:** *Rettifica in entrata*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-190">**Inventory adjustment types:** *Adjust in*</span></span>

1. <span data-ttu-id="ccbcb-191">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-191">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="ccbcb-192">Menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="ccbcb-192">Mobile device menu</span></span>

1. <span data-ttu-id="ccbcb-193">Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-193">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="ccbcb-194">Nell'elenco dei menu, selezionare **Scorte**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-194">In the list of menus, select **Inventory**.</span></span>
1. <span data-ttu-id="ccbcb-195">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-195">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ccbcb-196">Nell'elenco **Menu e voci di menu disponibili** , trova e seleziona la voce di menu **Rettifica in entrata**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-196">In the **Available Menus And Menu Items** list, find and select the **Adjust In** menu item.</span></span>
1. <span data-ttu-id="ccbcb-197">Selezionare il pulsante freccia destra per spostare **Rettifica in entrata** nell'elenco **Struttura menu**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-197">Select the right arrow button to move **Adjust In** to the **Menu Structure** list.</span></span> <span data-ttu-id="ccbcb-198">In questo modo, si aggiunge la nuova voce di menu al menu selezionato.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-198">In this way, you add the new menu item to the selected menu.</span></span>
1. <span data-ttu-id="ccbcb-199">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-199">Select **Save**.</span></span>

### <a name="movement-types"></a><span data-ttu-id="ccbcb-200">Tipi di movimento</span><span class="sxs-lookup"><span data-stu-id="ccbcb-200">Movement types</span></span>

1. <span data-ttu-id="ccbcb-201">Selezionare **Gestione magazzino \> Impostazione \> Scorte \> Tipi di movimento**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-201">Go to **Warehouse management \> Setup \> Inventory \> Movement types**.</span></span>
1. <span data-ttu-id="ccbcb-202">Nel riquadro azioni, selezionare **Nuovo** , quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-202">On the Action Pane, select **New** , and then set the following values:</span></span>

    - <span data-ttu-id="ccbcb-203">**Codice tipo di movimento:** *CONSOLIDARE*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-203">**Movement type code:** *CONSOLIDATE*</span></span>
    - <span data-ttu-id="ccbcb-204">**Descrizione:** *Consolidare ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-204">**Description:** *Consolidate locations*</span></span>
    - <span data-ttu-id="ccbcb-205">**ID classe lavoro:** *InvMov*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-205">**Work class ID:** *InvMov*</span></span>

1. <span data-ttu-id="ccbcb-206">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-206">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="ccbcb-207">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="ccbcb-207">Example scenario</span></span>

<span data-ttu-id="ccbcb-208">Il seguente scenario utilizza l'app di magazzino su un dispositivo mobile per creare una *rettifica in entrata* delle scorte in due ubicazioni nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-208">The following scenario uses the warehouse app on a mobile device to make an inventory *adjustment in* to two locations in the warehouse.</span></span>

### <a name="add-inventory-to-locations"></a><span data-ttu-id="ccbcb-209">Aggiungere scorte alle ubicazioni</span><span class="sxs-lookup"><span data-stu-id="ccbcb-209">Add inventory to locations</span></span>

1. <span data-ttu-id="ccbcb-210">Accedere al dispositivo mobile come utente configurato per il magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-210">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="ccbcb-211">Andare a **Scorte \> Rettifica in entrata**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-211">Go to **Inventory \> Adjust In**.</span></span>

    <span data-ttu-id="ccbcb-212">Ora si inserirà la prima rettifica dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-212">You will now enter the first location adjustment.</span></span>

1. <span data-ttu-id="ccbcb-213">Nell'attività **Rettifica in entrata** selezionare l'ubicazione per cui effettuare la rettifica delle scorte.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-213">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="ccbcb-214">Nel campo **UBICAZIONE** selezionare *LP-001*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-214">In the **LOC** field, select *LP-001*.</span></span>
1. <span data-ttu-id="ccbcb-215">Confermare l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-215">Confirm the location.</span></span>
1. <span data-ttu-id="ccbcb-216">Creare un ID targa per l'articolo che verrà aggiunto all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-216">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="ccbcb-217">Nel campo **TARGA** , immettere *LP00101*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-217">In the **LP** field, enter *LP00101*.</span></span>
1. <span data-ttu-id="ccbcb-218">Confermare la targa.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-218">Confirm the license plate.</span></span>
1. <span data-ttu-id="ccbcb-219">Immettere l'articolo che verrà aggiunto alla targa.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-219">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="ccbcb-220">Nel campo **ITEM** , immettere *M9201*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-220">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="ccbcb-221">Confermare l'articolo.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-221">Confirm the item.</span></span>
1. <span data-ttu-id="ccbcb-222">Immettere la quantità dell'elemento che verrà aggiunta.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-222">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="ccbcb-223">Nel campo **QUANTITÀ** immettere *10* '.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-223">In the **QTY** field, enter *10*.</span></span>
1. <span data-ttu-id="ccbcb-224">Confermare la quantità.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-224">Confirm the quantity.</span></span>

    <span data-ttu-id="ccbcb-225">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="ccbcb-225">You receive a "Work Completed" message.</span></span> <span data-ttu-id="ccbcb-226">Ora si inserirà la seconda rettifica dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-226">You will now enter the second location adjustment.</span></span>

1. <span data-ttu-id="ccbcb-227">Nell'attività **Rettifica in entrata** selezionare l'ubicazione per cui effettuare la rettifica delle scorte.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-227">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="ccbcb-228">Nel campo **UBICAZIONE** selezionare *LP-002*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-228">In the **LOC** field, select *LP-002*.</span></span>
1. <span data-ttu-id="ccbcb-229">Confermare l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-229">Confirm the location.</span></span>
1. <span data-ttu-id="ccbcb-230">Creare un ID targa per l'articolo che verrà aggiunto all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-230">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="ccbcb-231">Nel campo **TARGA** , immettere *LP00201*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-231">In the **LP** field, enter *LP00201*.</span></span>
1. <span data-ttu-id="ccbcb-232">Confermare la targa.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-232">Confirm the license plate.</span></span>
1. <span data-ttu-id="ccbcb-233">Immettere l'articolo che verrà aggiunto alla targa.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-233">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="ccbcb-234">Nel campo **ITEM** , immettere *M9201*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-234">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="ccbcb-235">Confermare l'articolo.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-235">Confirm the item.</span></span>
1. <span data-ttu-id="ccbcb-236">Immettere la quantità dell'elemento che verrà aggiunta.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-236">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="ccbcb-237">Nel campo **QUANTITÀ** immettere *15* '.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-237">In the **QTY** field, enter *15*.</span></span>
1. <span data-ttu-id="ccbcb-238">Confermare la quantità.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-238">Confirm the quantity.</span></span>

    <span data-ttu-id="ccbcb-239">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="ccbcb-239">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="ccbcb-240">Selezionare il pulsante Menu (a volte indicato come hamburger o pulsante hamburger), quindi selezionare **Annulla** per uscire dall'attività **Rettifica in entrata**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-240">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit the **Adjustment in** task.</span></span>

### <a name="consolidate-locations"></a><span data-ttu-id="ccbcb-241">Consolidare le ubicazioni</span><span class="sxs-lookup"><span data-stu-id="ccbcb-241">Consolidate locations</span></span>

1. <span data-ttu-id="ccbcb-242">Andare a **Gestione magazzino \> Attività periodiche \> Consolidamento articoli**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-242">Go to **Warehouse management \> Periodic tasks \> Item consolidation**.</span></span>
1. <span data-ttu-id="ccbcb-243">Nell'intestazione, selezionare un magazzino per cui eseguire il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-243">In the header, select a warehouse to do the consolidation for.</span></span> <span data-ttu-id="ccbcb-244">Nel campo **Magazzino** immettere *51*.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-244">In the **Warehouse** field, enter *51*.</span></span>

    <span data-ttu-id="ccbcb-245">Viene visualizzato un record per ogni ubicazione in cui larticolo *M9201* è stato rettificato.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-245">A record is shown for each location where item *M9201* was adjusted.</span></span> <span data-ttu-id="ccbcb-246">La colonna **Percentuale di utilizzo** mostra l'utilizzo volumetrico di ogni ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-246">The **Utilization percentage** column shows the volumetric utilization of each location.</span></span>

1. <span data-ttu-id="ccbcb-247">Per consolidare le scorte, selezionare tutte le ubicazioni che devono essere consolidate, quindi, nel riquadro azioni, selezionare **Consolida scorte**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-247">To consolidate inventory, select all the locations that must be consolidated, and then, on the Action Pane, select **Consolidate Inventory**.</span></span>
1. <span data-ttu-id="ccbcb-248">Nella finestra di dialogo **Consolida scorte** , specificare l'ubicazione e il tipo di movimento da utilizzare per creare il lavoro per il movimento delle scorte.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-248">In the **Consolidate inventory** dialog box, specify the location and movement type that should be used to create the work for inventory movement.</span></span> <span data-ttu-id="ccbcb-249">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ccbcb-249">Set the following values:</span></span>

    - <span data-ttu-id="ccbcb-250">**Ubicazione:** *LP-001*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-250">**Location:** *LP-001*</span></span>
    - <span data-ttu-id="ccbcb-251">**Codice tipo di movimento:** *CONSOLIDARE*</span><span class="sxs-lookup"><span data-stu-id="ccbcb-251">**Movement type code:** *CONSOLIDATE*</span></span>

1. <span data-ttu-id="ccbcb-252">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-252">Select **OK**.</span></span>
1. <span data-ttu-id="ccbcb-253">Viene visualizzato un messaggio informativo che mostra il lavoro di movimento creato.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-253">You receive an informational message that shows the movement work that was created.</span></span> <span data-ttu-id="ccbcb-254">Prendere nota dell'ID lavoro di movimento.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-254">Make a note of the movement work ID.</span></span>

### <a name="view-movement-work"></a><span data-ttu-id="ccbcb-255">Visualizzare il lavoro di movimento</span><span class="sxs-lookup"><span data-stu-id="ccbcb-255">View movement work</span></span>

1. <span data-ttu-id="ccbcb-256">Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-256">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="ccbcb-257">Visualizzare il lavoro creato.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-257">View the work that was created.</span></span> <span data-ttu-id="ccbcb-258">Utilizzare l'ID lavoro di movimento del consolidamento delle scorte per filtrare o cercare nella griglia di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-258">Use the movement work ID from the inventory consolidation to filter or search the work grid.</span></span>

    <span data-ttu-id="ccbcb-259">In questo scenario, un'ubicazione esistente con scorte è stata utilizzata come ubicazione di consolidamento delle scorte.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-259">In this scenario, an existing location that had inventory was used as the inventory consolidation location.</span></span> <span data-ttu-id="ccbcb-260">Pertanto, è stato creato un solo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-260">Therefore, only one work ID was created.</span></span>

    > [!NOTE]
   > <span data-ttu-id="ccbcb-261">Il sistema crea un ID lavoro per ogni movimento che deve essere completato.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-261">The system creates one work ID for each move that must be completed.</span></span> <span data-ttu-id="ccbcb-262">Se si specifica un'ubicazione che contiene già delle scorte, viene creato un solo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-262">If you specify a location that already contains inventory, only one work ID is created.</span></span> <span data-ttu-id="ccbcb-263">Se si specifica una nuova ubicazione, vengono creati due ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="ccbcb-263">If you specify a new location, two work IDs are created.</span></span>
