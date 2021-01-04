---
title: Ordinamento in uscita
description: Questo argomento fornisce informazioni sull'ordinamento in uscita. Questa funzionalità semplifica la gestione di piccoli contenitori e aiuta i lavoratori a pianificare e organizzare meglio la capacità dei pallet nel camion.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 84c4ec83ed16762e6c3c1a22425cf60e5b3ae8da
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431568"
---
# <a name="outbound-sorting"></a><span data-ttu-id="6449f-104">Ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="6449f-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6449f-105">Questa funzionalità semplifica la gestione di piccoli contenitori e aiuta i lavoratori a pianificare e organizzare meglio la capacità dei pallet nel camion.</span><span class="sxs-lookup"><span data-stu-id="6449f-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="6449f-106">Quando si utilizza l'ordinamento in uscita, è possibile ordinare i contenitori imballati nel pallet corretto dopo che sono stati in una stazione di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="6449f-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="6449f-107">È anche possibile creare una gerarchia di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="6449f-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="6449f-108">Questa funzionalità consente di creare pallet da contenitori imballati mediante la funzionalità di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="6449f-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="6449f-109">Il contenitore non viene inviato al luogo di spedizione finale in quanto si trova nel flusso di imballaggio originale.</span><span class="sxs-lookup"><span data-stu-id="6449f-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="6449f-110">Al contrario, i lavoratori possono chiudere il contenitore e spostarlo in un'ubicazione di tipo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="6449f-111">Possono quindi ordinare i contenitori in posizioni, ognuna delle quali ha una targa.</span><span class="sxs-lookup"><span data-stu-id="6449f-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="6449f-112">Dopo che i contenitori sono stati ordinati, è possibile creare lavoro per inviare l'intera targa alla banchina di spedizione finale o alle ubicazioni di gestione temporanea, in base alle direttive di ubicazione o alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="6449f-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="6449f-113">Inoltre, l'azione di chiusura della posizione di ordinamento può spostare immediatamente le scorte nell'ubicazione di spedizione finale e prelevarle per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="6449f-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="6449f-114">Attivare la funzionalità Ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="6449f-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="6449f-115">Prima di poter utilizzare questa funzionalità, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="6449f-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="6449f-116">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="6449f-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6449f-117">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6449f-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6449f-118">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="6449f-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6449f-119">**Nome funzionalità:** *Ordinamento in uscita*</span><span class="sxs-lookup"><span data-stu-id="6449f-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="6449f-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="6449f-120">Setup</span></span>

<span data-ttu-id="6449f-121">Per questo scenario, è necessario utilizzare i dati dimostrativi **USMF** standard e il magazzino *62*.</span><span class="sxs-lookup"><span data-stu-id="6449f-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="6449f-122">È inoltre necessario completare la configurazione descritta nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6449f-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="6449f-123">Impostare un modello di ondata</span><span class="sxs-lookup"><span data-stu-id="6449f-123">Set up a wave template</span></span>

<span data-ttu-id="6449f-124">Questa configurazione elabora automaticamente l'ondata e crea lavoro quando una riga viene rilasciata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="6449f-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="6449f-125">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="6449f-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="6449f-126">Nell'elenco di modelli, selezionare **Magazzino 62**.</span><span class="sxs-lookup"><span data-stu-id="6449f-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="6449f-127">Nella Scheda dettaglio **Generale**, assicurarsi che l'opzione **Elabora ondata al rilascio in magazzino** sia impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="6449f-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="6449f-128">Configurare un lavoratore</span><span class="sxs-lookup"><span data-stu-id="6449f-128">Set up a worker</span></span>

<span data-ttu-id="6449f-129">La stazione di imballaggio è considerata un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="6449f-129">The packing station is considered a location.</span></span> <span data-ttu-id="6449f-130">I lavoratori che accedono alla stazione di imballaggio vedono e lavorano solo su spedizioni e contenitori pianificati in quella specifica ubicazione di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="6449f-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="6449f-131">Un utente che accede a Microsoft Dynamics 365 deve essere configurato come lavoratore in Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="6449f-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="6449f-132">Se il nome dell'utente non appare nell'elenco di utenti di lavoro, utilizzare la seguente procedura per aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="6449f-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="6449f-133">Questi passaggi presuppongono che l'utente esista già nel sistema e che sia stato associato come dipendente o lavoratore nel modulo **Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="6449f-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="6449f-134">Andare a **Gestione magazzino \> Impostazioni \> Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="6449f-135">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-135">Select **New**.</span></span>
1. <span data-ttu-id="6449f-136">Nel campo **Lavoratore**, selezionare l'utente di destinazione nell'elenco di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="6449f-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="6449f-137">Selezionare **Select**.</span><span class="sxs-lookup"><span data-stu-id="6449f-137">Select **Select**.</span></span>
1. <span data-ttu-id="6449f-138">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6449f-139">Nella Scheda dettaglio **Utenti**, selezionare **Nuovo** per creare un account per dispositivo mobile e impostarne i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="6449f-140">**ID utente:** immettere un ID univoco.</span><span class="sxs-lookup"><span data-stu-id="6449f-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="6449f-141">**Nome utente:** immettere un nome per l'ID.</span><span class="sxs-lookup"><span data-stu-id="6449f-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="6449f-142">**Magazzino predefinito:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="6449f-143">**Nome menu:** *Principale*</span><span class="sxs-lookup"><span data-stu-id="6449f-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="6449f-144">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6449f-145">Viene visualizzata la finestra di dialogo **Imposta password** dove è possibile creare una semplice password che l'utente può utilizzare per accedere all'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="6449f-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="6449f-146">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="6449f-146">Set the following values:</span></span>

    - <span data-ttu-id="6449f-147">**Password:** immettere una password semplice.</span><span class="sxs-lookup"><span data-stu-id="6449f-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="6449f-148">**Conferma password:** immettere di nuovo la stessa password.</span><span class="sxs-lookup"><span data-stu-id="6449f-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="6449f-149">Selezionare **Imposta password**.</span><span class="sxs-lookup"><span data-stu-id="6449f-149">Select **Set password**.</span></span>

    <span data-ttu-id="6449f-150">Una notifica nel Centro azioni indica che la password è stata impostata per l'utente creato.</span><span class="sxs-lookup"><span data-stu-id="6449f-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="6449f-151">Creare un tipo di ubicazione</span><span class="sxs-lookup"><span data-stu-id="6449f-151">Create a location type</span></span>

1. <span data-ttu-id="6449f-152">Andare a **Gestione magazzino \> Impostazione \> Magazzino \> Tipi di ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="6449f-153">Nel riquadro azioni selezionare **Nuovo** per creare un tipo di ubicazione e impostarne i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="6449f-154">**Tipo di ubicazione:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="6449f-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="6449f-155">**Descrizione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="6449f-156">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="6449f-157">Impostare i parametri di Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="6449f-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="6449f-158">Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6449f-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="6449f-159">Nella scheda **Generale** della Scheda dettaglio **Tipi di ubicazione**, impostare il campo **Tipo di ubicazione di ordinamento** su *ORDINAMENTO*.</span><span class="sxs-lookup"><span data-stu-id="6449f-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="6449f-160">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="6449f-161">Impostare un profilo di ubicazione</span><span class="sxs-lookup"><span data-stu-id="6449f-161">Set up a location profile</span></span>

1. <span data-ttu-id="6449f-162">Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="6449f-163">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-164">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="6449f-165">**ID profilo ubicazione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="6449f-166">**Nome:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="6449f-167">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-168">**Formato ubicazione:** *ASRB* (Sezione-Scaffale-Ripiano-Contenitore)</span><span class="sxs-lookup"><span data-stu-id="6449f-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="6449f-169">**Tipo di ubicazione:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="6449f-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="6449f-170">**Usa rilevamento targa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6449f-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="6449f-171">**Consenti articoli combinati:** *Sì* (quando si imposta questa opzione su *Sì*, l'opzione **Consenti batch inventario combinati** è automaticamente impostata su *Sì* e non può essere modificata in modo indipendente).</span><span class="sxs-lookup"><span data-stu-id="6449f-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="6449f-172">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="6449f-173">Impostare un'ubicazione</span><span class="sxs-lookup"><span data-stu-id="6449f-173">Set up a location</span></span>

1. <span data-ttu-id="6449f-174">Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="6449f-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="6449f-175">Nell'intestazione, deselezionare la casella di controllo **Genera cifre di controllo per ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="6449f-176">Nel riquadro azioni selezionare **Nuovo** per creare un'ubicazione e impostarne i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="6449f-177">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6449f-178">**Ubicazione:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="6449f-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="6449f-179">**ID profilo ubicazione:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="6449f-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="6449f-180">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="6449f-181">Impostare un modello di ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="6449f-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="6449f-182">Il modello di ordinamento in uscita determina se il lavoro viene creato al di fuori dell'ubicazione di ordinamento e se l'ordinamento viene eseguito manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6449f-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="6449f-183">Per questo scenario, si creerà un modello di ordinamento in uscita per creare pallet dopo la stazione di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="6449f-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="6449f-184">Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Modello di ordinamento in uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="6449f-185">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-186">Nell'intestazione del nuovo modello, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="6449f-187">**ID modello di ordinamento in uscita:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="6449f-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="6449f-188">**Descrizione:** *Creazione automatica di lavoro*</span><span class="sxs-lookup"><span data-stu-id="6449f-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="6449f-189">**Tipo di modello di ordinamento in uscita:** *Contenitore*</span><span class="sxs-lookup"><span data-stu-id="6449f-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="6449f-190">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6449f-191">**Ubicazione:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="6449f-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="6449f-192">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-193">**Ordina tipo di verifica:** selezionare *Scansione posizione*</span><span class="sxs-lookup"><span data-stu-id="6449f-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="6449f-194">**Crea lavoro in posizione chiusa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6449f-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="6449f-195">Se questa opzione è impostata su *Sì*, quando la posizione è chiusa, verrà creato il lavoro per spostare le scorte nell'ubicazione di spedizione finale.</span><span class="sxs-lookup"><span data-stu-id="6449f-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="6449f-196">Se è impostata su *No*, le scorte verranno immediatamente prelevate nell'ordine quando la posizione viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="6449f-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="6449f-197">**Assegnazione di posizione:** *Automatica*</span><span class="sxs-lookup"><span data-stu-id="6449f-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="6449f-198">Se questo campo è impostato su *Manuale*, l'utente deve sempre indicare in quale posizione le scorte devono essere ordinate.</span><span class="sxs-lookup"><span data-stu-id="6449f-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="6449f-199">Se è impostato su *Automatica*, il sistema inserisce automaticamente le scorte in una posizione quando possibile, in base alle suddivisioni del modello di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="6449f-200">Nel riquadro azioni selezionare **Salva** per rendere l'opzione **Modifica query** disponibile.</span><span class="sxs-lookup"><span data-stu-id="6449f-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="6449f-201">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="6449f-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="6449f-202">Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="6449f-203">**Tabella:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="6449f-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="6449f-204">**Tabella derivata:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="6449f-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="6449f-205">**Campo:** *Servizio trasporto*</span><span class="sxs-lookup"><span data-stu-id="6449f-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="6449f-206">Dopo aver selezionato questo valore, è possibile che venga visualizzato il messaggio seguente: "Il servizio di trasporto non è un campo indice.</span><span class="sxs-lookup"><span data-stu-id="6449f-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="6449f-207">Vuoi aggiungere l'ordinamento su questo? "</span><span class="sxs-lookup"><span data-stu-id="6449f-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="6449f-208">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6449f-208">Select **Yes**.</span></span>

    - <span data-ttu-id="6449f-209">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="6449f-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="6449f-210">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-210">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-211">È possibile che venga visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?".</span><span class="sxs-lookup"><span data-stu-id="6449f-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="6449f-212">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6449f-212">Select **Yes**.</span></span>

    <span data-ttu-id="6449f-213">Il pulsante **Interruzioni del modello di ordinamento in uscita** nel riquadro azioni diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="6449f-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="6449f-214">Nel riquadro azioni selezionare **Interruzioni del modello di ordinamento in uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="6449f-215">Nella finestra di dialogo **Criteri di ordinamento in uscita**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6449f-216">**Nome tabella di riferimento:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="6449f-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="6449f-217">**Nome campo di riferimento:** *Servizio trasporto*</span><span class="sxs-lookup"><span data-stu-id="6449f-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="6449f-218">**Raggruppa per campo:** selezionare questa casella di controllo per raggruppare le spedizioni per servizio di trasporto.</span><span class="sxs-lookup"><span data-stu-id="6449f-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="6449f-219">Selezionare **OK** per salvare le impostazioni e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6449f-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="6449f-220">Impostare i criteri di imballaggio dei contenitori</span><span class="sxs-lookup"><span data-stu-id="6449f-220">Set up container packing policies</span></span>

1. <span data-ttu-id="6449f-221">Passare a **Gestione magazzino \> Impostazioni \> Contenitori \> Criteri imballaggio contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="6449f-222">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-223">Nell'intestazione dei nuovi criteri, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="6449f-224">**Criteri imballaggio contenitore:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="6449f-225">**Descrizione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="6449f-226">Nella Scheda dettaglio **Panoramica**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-227">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6449f-228">**Ubicazione predefinita per ordinamento:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="6449f-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="6449f-229">**Unità peso:** *kg*</span><span class="sxs-lookup"><span data-stu-id="6449f-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="6449f-230">**Criteri chiusura contenitore:** *Rilascio automatico*</span><span class="sxs-lookup"><span data-stu-id="6449f-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="6449f-231">**Criteri rilascio contenitore:** *assegnare il contenitore alla posizione di ordinamento in uscita*</span><span class="sxs-lookup"><span data-stu-id="6449f-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="6449f-232">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="6449f-233">Impostare i profili imballaggio</span><span class="sxs-lookup"><span data-stu-id="6449f-233">Set up packing profiles</span></span>

<span data-ttu-id="6449f-234">Creare un nuovo profilo di imballaggio che verrà utilizzato insieme alla funzionalità di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="6449f-235">Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Profili imballaggio**.</span><span class="sxs-lookup"><span data-stu-id="6449f-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="6449f-236">Nel riquadro azioni selezionare **Nuovo** per creare una riga e impostarne i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="6449f-237">**ID profilo imballaggio:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="6449f-238">**Descrizione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="6449f-239">**Criteri imballaggio contenitore:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="6449f-240">**Modalità ID contenitore:** *Auto*</span><span class="sxs-lookup"><span data-stu-id="6449f-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="6449f-241">**Tipo di contenitore:** *Scatola-grande*</span><span class="sxs-lookup"><span data-stu-id="6449f-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="6449f-242">**Creazione automatica contenitore alla chiusura del contenitore:** deselezionato (= *No*)</span><span class="sxs-lookup"><span data-stu-id="6449f-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="6449f-243">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="6449f-244">Impostare classi di lavoro</span><span class="sxs-lookup"><span data-stu-id="6449f-244">Set up work classes</span></span>

<span data-ttu-id="6449f-245">Impostare una classe di lavoro che verrà utilizzata insieme all'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="6449f-246">Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6449f-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="6449f-247">Nel riquadro azioni selezionare **Nuovo** per creare una classe di lavoro per l'ordinamento e impostarne i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="6449f-248">**ID classe lavoro:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="6449f-249">**Descrizione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="6449f-250">**Tipo ordine di lavoro:** *Prelievo scorte ordinate*</span><span class="sxs-lookup"><span data-stu-id="6449f-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="6449f-251">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="6449f-252">Configurare voci di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="6449f-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="6449f-253">Configurare una voce di menu per pallet</span><span class="sxs-lookup"><span data-stu-id="6449f-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="6449f-254">Creare una voce di menu per dispositivo mobile per creare pallet durante l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="6449f-255">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6449f-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6449f-256">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-257">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="6449f-258">**Nome voce di menu:** *Creazione pallet*</span><span class="sxs-lookup"><span data-stu-id="6449f-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="6449f-259">**Titolo:** *Creazione pallet*</span><span class="sxs-lookup"><span data-stu-id="6449f-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="6449f-260">**Modalità:** *Indiretta*</span><span class="sxs-lookup"><span data-stu-id="6449f-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="6449f-261">**Utilizza lavoro esistente:** *No*</span><span class="sxs-lookup"><span data-stu-id="6449f-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="6449f-262">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-263">**Codice attività:** *Ordinamento in uscita*</span><span class="sxs-lookup"><span data-stu-id="6449f-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="6449f-264">Quando questo campo è impostato su *Ordinamento in uscita*, il campo **ID modello di ordinamento in uscita** è visualizzato.</span><span class="sxs-lookup"><span data-stu-id="6449f-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="6449f-265">**Utilizza guida processo:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6449f-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="6449f-266">Quando il campo **Codice attività** è impostato su *Ordinamento in uscita*, questa opzione viene automaticamente impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="6449f-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="6449f-267">**ID modello di ordinamento in uscita:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="6449f-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="6449f-268">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="6449f-269">Configurare una voce di menu per il carico</span><span class="sxs-lookup"><span data-stu-id="6449f-269">Set up a new loading menu item</span></span>

<span data-ttu-id="6449f-270">Ora creeremo una voce di menu che consente agli utenti di spostare gli articoli di magazzino ordinati nell'ubicazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="6449f-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="6449f-271">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6449f-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6449f-272">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-273">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="6449f-274">**Nome voce di menu:** *Carica da ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="6449f-275">**Titolo:** *Carica da ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="6449f-276">**Modalità:** *Lavoro*</span><span class="sxs-lookup"><span data-stu-id="6449f-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="6449f-277">**Utilizza lavoro esistente:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6449f-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="6449f-278">Nella Scheda dettaglio **Generale**, impostare il campo **Diretto da** su *Diretto dall'utente*.</span><span class="sxs-lookup"><span data-stu-id="6449f-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="6449f-279">Nella Scheda dettaglio **Classi di lavoro**, selezionare **Nuovo**, quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="6449f-280">**ID classe lavoro:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="6449f-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="6449f-281">**Tipo ordine di lavoro:** *Prelievo scorte ordinate*</span><span class="sxs-lookup"><span data-stu-id="6449f-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="6449f-282">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="6449f-283">Configurare il menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="6449f-283">Set up the mobile device menu</span></span>

<span data-ttu-id="6449f-284">È ora necessario aggiungere le nuove voci di menu al menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="6449f-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="6449f-285">Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6449f-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="6449f-286">Selezionare il menu **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="6449f-287">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6449f-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6449f-288">Nella colonna **Menu e voci di menu disponibili**, trovare e selezionare **Creazione pallet**.</span><span class="sxs-lookup"><span data-stu-id="6449f-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="6449f-289">Selezionare il pulsante freccia DESTRA per spostare **Creazione pallet** nella colonna **Struttura menu**.</span><span class="sxs-lookup"><span data-stu-id="6449f-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="6449f-290">Utilizzare i pulsanti freccia SU e GIÙ per inserire la voce di menu **Creazione pallet** nella posizione desiderata nel menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="6449f-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="6449f-291">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-291">Select **Save**.</span></span>
1. <span data-ttu-id="6449f-292">Ripetere questa procedura per aggiungere la voce di menu **Carica da ordinamento** al menu **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="6449f-293">Imposta direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="6449f-293">Set up location directives</span></span>

<span data-ttu-id="6449f-294">Le *direttive ubicazione* sono regole che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte.</span><span class="sxs-lookup"><span data-stu-id="6449f-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="6449f-295">Ora è necessario creare una regola per gestire il lavoro di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="6449f-296">Configurare una direttiva per una singola SKU</span><span class="sxs-lookup"><span data-stu-id="6449f-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="6449f-297">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6449f-298">Nel riquadro sinistro, impostare il campo **Tipo ordine di lavoro** su *Prelievo scorte ordinate*.</span><span class="sxs-lookup"><span data-stu-id="6449f-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="6449f-299">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-300">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="6449f-301">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="6449f-302">**Nome:** *Portellone*</span><span class="sxs-lookup"><span data-stu-id="6449f-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="6449f-303">Nella Scheda dettaglio **Direttive ubicazione**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-304">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="6449f-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="6449f-305">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="6449f-305">**Site:** *6*</span></span>
    - <span data-ttu-id="6449f-306">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6449f-307">**Più SKU:** *No*</span><span class="sxs-lookup"><span data-stu-id="6449f-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="6449f-308">Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Righe**.</span><span class="sxs-lookup"><span data-stu-id="6449f-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="6449f-309">Nella Scheda dettaglio **Righe**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="6449f-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="6449f-310">Accettare i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="6449f-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="6449f-311">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="6449f-312">**Da:** *0*</span><span class="sxs-lookup"><span data-stu-id="6449f-312">**From:** *0*</span></span>
    - <span data-ttu-id="6449f-313">**A:** *1.000.000*</span><span class="sxs-lookup"><span data-stu-id="6449f-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="6449f-314">Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Azioni direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="6449f-315">Nella Scheda dettaglio **Azioni direttiva ubicazione**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="6449f-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="6449f-316">Accettare i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="6449f-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="6449f-317">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="6449f-318">**Nome:** *Portellone*</span><span class="sxs-lookup"><span data-stu-id="6449f-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="6449f-319">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-319">Select **Save**.</span></span>
1. <span data-ttu-id="6449f-320">Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="6449f-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="6449f-321">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trovare la riga in cui il campo **Campo** è impostato su *Ubicazione*.</span><span class="sxs-lookup"><span data-stu-id="6449f-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="6449f-322">Impostare il campo **Criteri** per questa riga su *Portellone*.</span><span class="sxs-lookup"><span data-stu-id="6449f-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="6449f-323">Selezionare **OK** per salvare le impostazioni e chiudere l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="6449f-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="6449f-324">Configurare una direttiva per più SKU</span><span class="sxs-lookup"><span data-stu-id="6449f-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="6449f-325">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6449f-326">Nel riquadro sinistro, impostare il campo **Tipo ordine di lavoro** su *Prelievo scorte ordinate*.</span><span class="sxs-lookup"><span data-stu-id="6449f-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="6449f-327">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-328">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="6449f-329">**Sequenza:** *2*</span><span class="sxs-lookup"><span data-stu-id="6449f-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="6449f-330">**Nome:** *Multi portellone*</span><span class="sxs-lookup"><span data-stu-id="6449f-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="6449f-331">Nella Scheda dettaglio **Direttive ubicazione**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-332">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="6449f-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="6449f-333">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="6449f-333">**Site:** *6*</span></span>
    - <span data-ttu-id="6449f-334">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6449f-335">**Più SKU:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6449f-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="6449f-336">Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Righe**.</span><span class="sxs-lookup"><span data-stu-id="6449f-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="6449f-337">Nella Scheda dettaglio **Righe**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="6449f-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="6449f-338">Accettare i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="6449f-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="6449f-339">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="6449f-340">**Da:** *0*</span><span class="sxs-lookup"><span data-stu-id="6449f-340">**From:** *0*</span></span>
    - <span data-ttu-id="6449f-341">**A:** *1.000.000*</span><span class="sxs-lookup"><span data-stu-id="6449f-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="6449f-342">Selezionare **Salva** per rendere disponibile la barra degli strumenti nella Scheda dettaglio **Azioni direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="6449f-343">Nella Scheda dettaglio **Azioni direttiva ubicazione**, selezionare **Nuovo**, quindi impostare i seguenti valori per la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="6449f-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="6449f-344">Accettare i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="6449f-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="6449f-345">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="6449f-346">**Nome:** *Multi portellone*</span><span class="sxs-lookup"><span data-stu-id="6449f-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="6449f-347">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-347">Select **Save**.</span></span>
1. <span data-ttu-id="6449f-348">Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="6449f-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="6449f-349">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trovare la riga in cui il campo **Campo** è impostato su *Ubicazione*.</span><span class="sxs-lookup"><span data-stu-id="6449f-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="6449f-350">Impostare il campo **Criteri** per questa riga su *Portellone*.</span><span class="sxs-lookup"><span data-stu-id="6449f-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="6449f-351">Selezionare **OK** per salvare le impostazioni e chiudere l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="6449f-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="6449f-352">Imposta modelli di lavoro</span><span class="sxs-lookup"><span data-stu-id="6449f-352">Set up work templates</span></span>

1. <span data-ttu-id="6449f-353">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6449f-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="6449f-354">Impostare il campo **Tipo ordine di lavoro** su *Prelievo scorte ordinate*.</span><span class="sxs-lookup"><span data-stu-id="6449f-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="6449f-355">Nel riquadro azioni selezionare **Nuovo** per creare un modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6449f-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="6449f-356">Nella scheda **Panoramica**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="6449f-357">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="6449f-358">**Modello di lavoro** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="6449f-359">**Descrizione modello di lavoro:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="6449f-360">Seleziona **Salva** per rendere la Scheda dettaglio **Dettagli modello di lavoro** disponibile.</span><span class="sxs-lookup"><span data-stu-id="6449f-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="6449f-361">Nella Scheda dettaglio **Dettagli modello di lavoro**, selezionare **Nuovo** per aggiungere una riga e quindi impostarne i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="6449f-362">**Tipo di lavoro:** *Prelevare*</span><span class="sxs-lookup"><span data-stu-id="6449f-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="6449f-363">**ID classe lavoro:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="6449f-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="6449f-364">Selezionare di nuovo **Nuovo** per aggiungere una seconda riga e quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="6449f-365">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="6449f-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="6449f-366">**ID classe lavoro:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="6449f-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="6449f-367">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6449f-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="6449f-368">Scenario</span><span class="sxs-lookup"><span data-stu-id="6449f-368">Scenario</span></span>

<span data-ttu-id="6449f-369">Questo scenario simula una situazione in cui i contenitori imballati devono essere ordinati automaticamente in posizioni diverse (pallet) dopo la stazione di imballaggio, a seconda del servizio di trasporto per la spedizione.</span><span class="sxs-lookup"><span data-stu-id="6449f-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="6449f-370">Dopo che tutti gli articoli del carico sono stati imballati e ordinati per indirizzo, i pallet verranno spostati verso il portellone.</span><span class="sxs-lookup"><span data-stu-id="6449f-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="6449f-371">Creare ordini cliente e lavoro di prelievo</span><span class="sxs-lookup"><span data-stu-id="6449f-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="6449f-372">Creare l'ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="6449f-372">Create sales order 1</span></span>

1. <span data-ttu-id="6449f-373">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="6449f-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6449f-374">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-375">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6449f-376">**Conto cliente:** *US-005*</span><span class="sxs-lookup"><span data-stu-id="6449f-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="6449f-377">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6449f-378">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6449f-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="6449f-379">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="6449f-380">Passa alla visualizzazione **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="6449f-381">Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="6449f-382">**Vettore spedizione:** *Air cargo*</span><span class="sxs-lookup"><span data-stu-id="6449f-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="6449f-383">**Servizio trasporto:** *Air*</span><span class="sxs-lookup"><span data-stu-id="6449f-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="6449f-384">Tornare alla visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="6449f-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="6449f-385">Se una nuova riga vuota non viene aggiunta automaticamente alla griglia nella Scheda dettaglio **Righe ordine cliente**, selezionare **Aggiungi riga** per aggiungerne una.</span><span class="sxs-lookup"><span data-stu-id="6449f-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="6449f-386">Nella nuova riga ordine, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="6449f-387">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6449f-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="6449f-388">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="6449f-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="6449f-389">Mentre la nuova riga ordine è ancora selezionata nella Scheda dettaglio **Righe ordine cliente**, nel menu **Inventario** sopra la griglia, selezionare **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="6449f-390">Nella pagina **Prenotazione**, selezionare **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="6449f-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="6449f-391">Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="6449f-392">Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6449f-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="6449f-393">Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine.</span><span class="sxs-lookup"><span data-stu-id="6449f-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="6449f-394">Prendere nota del numero ID ondata e del numero ID spedizione.</span><span class="sxs-lookup"><span data-stu-id="6449f-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="6449f-395">Ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="6449f-395">Sales order 2</span></span>

1. <span data-ttu-id="6449f-396">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="6449f-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6449f-397">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6449f-398">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6449f-399">**Conto cliente:** *US-006*</span><span class="sxs-lookup"><span data-stu-id="6449f-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="6449f-400">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="6449f-401">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6449f-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="6449f-402">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-402">The new sales order is opened.</span></span> <span data-ttu-id="6449f-403">Dovrebbe includere una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="6449f-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="6449f-404">Impostare i seguenti valori in questa riga ordine:</span><span class="sxs-lookup"><span data-stu-id="6449f-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="6449f-405">**Articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6449f-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="6449f-406">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="6449f-407">Nella scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, impostare il campo **Modalità di consegna** su *Flowe-STD*.</span><span class="sxs-lookup"><span data-stu-id="6449f-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="6449f-408">Nella Scheda dettaglio **Righe ordine cliente**, selezionare **Aggiungi riga**, quindi impostare i seguenti valori nella seconda riga ordine.</span><span class="sxs-lookup"><span data-stu-id="6449f-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="6449f-409">**Articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6449f-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="6449f-410">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="6449f-411">Nella scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, impostare il valore del campo **Modalità di consegna** su *Air C-Air*.</span><span class="sxs-lookup"><span data-stu-id="6449f-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="6449f-412">Nella Scheda dettaglio **Righe ordine cliente**, selezionare la prima riga ordine.</span><span class="sxs-lookup"><span data-stu-id="6449f-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="6449f-413">Quindi, nel menu **Scorte** sopra la griglia, selezionare **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="6449f-414">Nella pagina **Prenotazione**, selezionare **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="6449f-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="6449f-415">Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="6449f-416">Nella Scheda dettaglio **Righe ordine cliente**, selezionare la seconda riga ordine.</span><span class="sxs-lookup"><span data-stu-id="6449f-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="6449f-417">Quindi, nel menu **Scorte** sopra la griglia, selezionare **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="6449f-418">Nella pagina **Prenotazione**, selezionare **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="6449f-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="6449f-419">Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="6449f-420">Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6449f-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="6449f-421">Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine.</span><span class="sxs-lookup"><span data-stu-id="6449f-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="6449f-422">Si noti che sono stati creati due numeri ID ondata e due numeri ID spedizione, uno per ciascuna modalità di consegna per le righe ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="6449f-423">Ottenere gli ID lavoro dai dettagli del lavoro</span><span class="sxs-lookup"><span data-stu-id="6449f-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="6449f-424">Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6449f-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="6449f-425">La pagina mostra gli ID lavoro creati dagli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="6449f-426">Utilizzare gli ID ondata e gli ID spedizione dagli ordini cliente creati per trovare l'ID lavoro per ogni ondata e spedizione.</span><span class="sxs-lookup"><span data-stu-id="6449f-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="6449f-427">Prendere nota di questi ID lavoro, in quanto saranno necessari nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="6449f-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="6449f-428">Si noti che sono stati creati due ID lavoro per il secondo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="6449f-429">Se vengono prelevati articoli differenti in diverse ubicazioni, vengono generati ID lavoro distinti.</span><span class="sxs-lookup"><span data-stu-id="6449f-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="6449f-430">Prelevare articoli per gli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="6449f-430">Pick items for the sales orders</span></span>

<span data-ttu-id="6449f-431">Completare il lavoro creato utilizzando il dispositivo mobile per spostare gli articoli nella stazione di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="6449f-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="6449f-432">Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).</span><span class="sxs-lookup"><span data-stu-id="6449f-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="6449f-433">Nel menu principale, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="6449f-434">Nel menu **In uscita**, selezionare **Prelievo vendite**.</span><span class="sxs-lookup"><span data-stu-id="6449f-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="6449f-435">Nel campo **ID**, immettere l'ID lavoro creato per l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="6449f-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="6449f-436">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-436">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-437">Nella pagina **Ordini cliente - Prelievo**, immettere una targa di destinazione creata per l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="6449f-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="6449f-438">Si noti che sono visualizzati l'ubicazione di prelievo (*bulk-001*), l'articolo (*A0001*) e la quantità (*2 pezzi*).</span><span class="sxs-lookup"><span data-stu-id="6449f-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="6449f-439">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-439">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-440">Esaminare le informazioni nella pagina **Ordini cliente - Stoccaggio**.</span><span class="sxs-lookup"><span data-stu-id="6449f-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="6449f-441">Il campo **Ubicazione** deve indicare che gli articoli prelevati vengono spostati all'ubicazione *Imballaggio*.</span><span class="sxs-lookup"><span data-stu-id="6449f-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="6449f-442">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-442">Select **OK**.</span></span>

    <span data-ttu-id="6449f-443">Nella pagina **Esegui scansione ID lavoro/ID targa**, viene visualizzato il messaggio "Lavoro completato", che indica che l'ID lavoro dell'ordine cliente 1 è stato completato.</span><span class="sxs-lookup"><span data-stu-id="6449f-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="6449f-444">Ora si sceglierà l'ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="6449f-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="6449f-445">Nel campo **ID**, immettere l'ID lavoro creato per l'ordine cliente 2, dove la riga 1 include l'articolo *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6449f-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="6449f-446">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-446">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-447">Nella pagina **Ordini cliente - Prelievo**, immettere una targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6449f-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="6449f-448">Si noti che sono visualizzati l'ubicazione di prelievo (*bulk-001*), l'articolo (*A0001*) e la quantità (*1 pezzo*).</span><span class="sxs-lookup"><span data-stu-id="6449f-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="6449f-449">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-449">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-450">Esaminare le informazioni nella pagina **Ordini cliente - Stoccaggio**.</span><span class="sxs-lookup"><span data-stu-id="6449f-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="6449f-451">Il campo **Ubicazione** deve indicare che gli articoli prelevati vengono spostati all'ubicazione *Imballaggio*.</span><span class="sxs-lookup"><span data-stu-id="6449f-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="6449f-452">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-452">Select **OK**.</span></span>

    <span data-ttu-id="6449f-453">Nella pagina **Esegui scansione ID lavoro/ID targa**, viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="6449f-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="6449f-454">Questo messaggio indica che l'ID lavoro della riga 1 dell'ordine di vendita 2 è stato completato.</span><span class="sxs-lookup"><span data-stu-id="6449f-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="6449f-455">Nel campo **ID**, immettere l'ID lavoro creato per l'ordine cliente 2, dove la riga 2 include l'articolo *A0002*.</span><span class="sxs-lookup"><span data-stu-id="6449f-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="6449f-456">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-456">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-457">Nella pagina **Ordini cliente - Prelievo**, immettere una targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6449f-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="6449f-458">Si noti che sono visualizzati l'ubicazione di prelievo (*bulk-002*), l'articolo (*A0001*) e la quantità (*1 pezzo*).</span><span class="sxs-lookup"><span data-stu-id="6449f-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="6449f-459">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-459">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-460">Esaminare le informazioni nella pagina **Ordini cliente - Stoccaggio**.</span><span class="sxs-lookup"><span data-stu-id="6449f-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="6449f-461">Il campo **Ubicazione** deve indicare che gli articoli prelevati vengono spostati all'ubicazione *Imballaggio*.</span><span class="sxs-lookup"><span data-stu-id="6449f-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="6449f-462">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-462">Select **OK**.</span></span>

    <span data-ttu-id="6449f-463">Nella pagina **Esegui scansione ID lavoro/ID targa**, viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="6449f-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="6449f-464">Questo messaggio indica che l'ID lavoro della riga 2 dell'ordine di vendita 2 è stato completato.</span><span class="sxs-lookup"><span data-stu-id="6449f-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="6449f-465">Imballare ordini cliente in contenitori</span><span class="sxs-lookup"><span data-stu-id="6449f-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="6449f-466">Imballare l'ordine cliente 1 in contenitori</span><span class="sxs-lookup"><span data-stu-id="6449f-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="6449f-467">Andare a **Gestione magazzino \> Imballaggio e containerizzazione \> Imballaggio**.</span><span class="sxs-lookup"><span data-stu-id="6449f-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="6449f-468">Viene visualizzata la finestra di dialogo **Seleziona stazione di imballaggio**.</span><span class="sxs-lookup"><span data-stu-id="6449f-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="6449f-469">Per impostazione predefinita, il campo **Lavoratore** deve essere impostato sul nome del lavoratore impostato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6449f-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="6449f-470">Impostare i seguenti valori per visualizzare e lavorare su spedizioni e contenitori pianificati nell'ubicazione di imballaggio specifica:</span><span class="sxs-lookup"><span data-stu-id="6449f-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="6449f-471">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="6449f-471">**Site:** *6*</span></span>
    - <span data-ttu-id="6449f-472">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="6449f-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="6449f-473">**Ubicazione:** *Imballaggio*</span><span class="sxs-lookup"><span data-stu-id="6449f-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="6449f-474">**ID profilo imballaggio:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="6449f-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="6449f-475">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6449f-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="6449f-476">Nella pagina **Imballaggio**, nel campo **Targa o spedizione**, immettere la targa di destinazione per l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="6449f-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="6449f-477">Quindi premere il tasto **TAB** o **INVIO** della tastiera per uscire dal campo.</span><span class="sxs-lookup"><span data-stu-id="6449f-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="6449f-478">Nel riquadro azioni selezionare **Nuovo contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="6449f-479">Accettare tutte le impostazioni predefinite e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="6449f-480">Prendere nota dell'ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="6449f-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="6449f-481">Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-482">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="6449f-483">**Identificatore:** articolo *A0001*</span><span class="sxs-lookup"><span data-stu-id="6449f-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="6449f-484">Nel riquadro azioni selezionare **Chiudi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="6449f-485">Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="6449f-486">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-486">Select **OK**.</span></span> <span data-ttu-id="6449f-487">Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="6449f-488">Creare un secondo contenitore per aggiungere il secondo articolo della targa per l'ordine cliente 1 a un nuovo contenitore.</span><span class="sxs-lookup"><span data-stu-id="6449f-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="6449f-489">Nel riquadro azioni selezionare **Nuovo contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="6449f-490">Accettare tutte le impostazioni predefinite e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="6449f-491">Prendere nota dell'ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="6449f-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="6449f-492">Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-493">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="6449f-494">**Identificatore:** articolo *A0001*</span><span class="sxs-lookup"><span data-stu-id="6449f-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="6449f-495">Nel riquadro azioni selezionare **Chiudi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="6449f-496">Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="6449f-497">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-497">Select **OK**.</span></span> <span data-ttu-id="6449f-498">Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="6449f-499">Imballare l'ordine cliente 2 in contenitori</span><span class="sxs-lookup"><span data-stu-id="6449f-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="6449f-500">Nella pagina **Imballaggio**, nel campo **Targa o spedizione**, immettere la targa di destinazione per la riga 1 dell'ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="6449f-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="6449f-501">Quindi premere il tasto **TAB** o **INVIO** della tastiera per uscire dal campo.</span><span class="sxs-lookup"><span data-stu-id="6449f-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="6449f-502">Nel riquadro azioni selezionare **Nuovo contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="6449f-503">Accettare tutte le impostazioni predefinite e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="6449f-504">Prendere nota dell'ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="6449f-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="6449f-505">Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-506">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="6449f-507">**Identificatore:** articolo *A0001*</span><span class="sxs-lookup"><span data-stu-id="6449f-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="6449f-508">Nel riquadro azioni selezionare **Chiudi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="6449f-509">Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="6449f-510">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-510">Select **OK**.</span></span> <span data-ttu-id="6449f-511">Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="6449f-512">Nel campo **Targa o spedizione**, immettere la targa di destinazione per la riga 2 dell'ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="6449f-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="6449f-513">Quindi premere il tasto **TAB** o **INVIO** della tastiera per uscire dal campo.</span><span class="sxs-lookup"><span data-stu-id="6449f-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="6449f-514">Nel riquadro azioni selezionare **Nuovo contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="6449f-515">Accettare tutte le impostazioni predefinite e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="6449f-516">Prendere nota dell'ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="6449f-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="6449f-517">Nella Scheda dettaglio **Imballaggio articolo**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6449f-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6449f-518">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6449f-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="6449f-519">**Identificatore:** articolo *A0002*</span><span class="sxs-lookup"><span data-stu-id="6449f-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="6449f-520">Nel riquadro azioni selezionare **Chiudi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="6449f-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="6449f-521">Nella finestra di dialogo **Chiudi contenitore**, selezionare **Ottieni peso sistema** di modo che il sistema aggiorni il campo **Peso lordo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="6449f-522">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-522">Select **OK**.</span></span> <span data-ttu-id="6449f-523">Il contenitore viene spostato nell'ubicazione *ORDINAMENTO* ed è pronto per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="6449f-524">Per visualizzare i dettagli del contenitore, selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Contenitori** e cercare gli ID contenitore creati durante l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="6449f-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="6449f-525">Ordinare i contenitori</span><span class="sxs-lookup"><span data-stu-id="6449f-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6449f-526">Quando si accede alla voce di menu **Creazione pallet** nell'app per dispositivi mobili per eseguire l'ordinamento in uscita, viene visualizzato il pulsante **Completo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="6449f-527">*Non utilizzare il pulsante **Completo** per ordinare o chiudere la posizione.*</span><span class="sxs-lookup"><span data-stu-id="6449f-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="6449f-528">Il pulsante **Completo** è disponibile per impostazione predefinita e non può essere disabilitato o rimosso dalla pagina.</span><span class="sxs-lookup"><span data-stu-id="6449f-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="6449f-529">Non è utilizzato per la funzionalità *Ordinamento in uscita*.</span><span class="sxs-lookup"><span data-stu-id="6449f-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="6449f-530">Ordinare il primo contenitore</span><span class="sxs-lookup"><span data-stu-id="6449f-530">Sort the first container</span></span>

1. <span data-ttu-id="6449f-531">Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).</span><span class="sxs-lookup"><span data-stu-id="6449f-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="6449f-532">Nel menu principale, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="6449f-533">Nel menu **In uscita**, selezionare **Creazione pallet**.</span><span class="sxs-lookup"><span data-stu-id="6449f-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="6449f-534">Nel campo **Targa/Con**, immettere il primo ID contenitore associato all'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="6449f-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="6449f-535">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-535">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-536">Poiché al momento non esistono posizioni di ordinamento, è necessario specificarne una.</span><span class="sxs-lookup"><span data-stu-id="6449f-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="6449f-537">Nel campo **ID posizione ordinamento**, immettere *SP01*.</span><span class="sxs-lookup"><span data-stu-id="6449f-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="6449f-538">Poiché nessuna targa è attualmente associata alla posizione di ordinamento *SP01*, è necessario specificarne una.</span><span class="sxs-lookup"><span data-stu-id="6449f-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="6449f-539">Nel campo **TARGA**, immettere *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="6449f-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="6449f-540">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-540">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-541">Poiché la convalida della posizione di ordinamento è attivata, è necessario immettere nuovamente l'ID posizione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="6449f-542">Nel campo **ID posizione ordinamento**, immettere *SP01*.</span><span class="sxs-lookup"><span data-stu-id="6449f-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="6449f-543">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-543">Select **OK**.</span></span>

    <span data-ttu-id="6449f-544">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="6449f-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="6449f-545">Per visualizzare la posizione di ordinamento e la targa nella stessa, selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Assegnazioni di posizioni di ordinamento in uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="6449f-546">La pagina **Assegnazioni di posizioni di ordinamento in uscita** mostra tutte le posizioni di ordinamento attualmente attive.</span><span class="sxs-lookup"><span data-stu-id="6449f-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="6449f-547">Il campo **Transazioni posizioni di ordinamento** mostra la targa associata a ciascuna posizione di ordinamento e i contenitori che si trovano nella posizione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6449f-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="6449f-548">Si noti che esiste attualmente una posizione di ordinamento e che la Scheda dettaglio **Criteri di posizione di ordinamento** mostra un criterio di **Spedizione - Servizio trasporto - Aereo**.</span><span class="sxs-lookup"><span data-stu-id="6449f-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="6449f-549">Ordinare i contenitori rimanenti</span><span class="sxs-lookup"><span data-stu-id="6449f-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="6449f-550">Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).</span><span class="sxs-lookup"><span data-stu-id="6449f-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="6449f-551">Nel menu principale, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="6449f-552">Nel menu **In uscita**, selezionare **Creazione pallet**.</span><span class="sxs-lookup"><span data-stu-id="6449f-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="6449f-553">Nel campo **Targa/Con**, immettere il secondo ID contenitore associato all'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="6449f-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="6449f-554">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-554">Select **OK**.</span></span> <span data-ttu-id="6449f-555">Poiché il modello di ordinamento è configurato per l'ordinamento automatico ed esiste già una posizione di ordinamento con criteri corrispondenti, si viene automaticamente indirizzati alla posizione di ordinamento corretta.</span><span class="sxs-lookup"><span data-stu-id="6449f-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="6449f-556">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-556">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-557">Confermare l'ID posizione di ordinamento per indicare che le scorte sono nell'ubicazione corretta.</span><span class="sxs-lookup"><span data-stu-id="6449f-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="6449f-558">Nel campo **ID posizione ordinamento**, immettere *SP01*.</span><span class="sxs-lookup"><span data-stu-id="6449f-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="6449f-559">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-559">Select **OK**.</span></span>

    <span data-ttu-id="6449f-560">Il lavoro è completato per il secondo contenitore dell'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="6449f-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="6449f-561">Ora si ordineranno i contenitori rimanenti dell'ordine di vendita 2.</span><span class="sxs-lookup"><span data-stu-id="6449f-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="6449f-562">Nel campo **Targa/Con**, immettere l'ID contenitore del contenitore dell'ordine cliente 2 che contiene l'articolo *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6449f-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="6449f-563">Poiché il servizio di trasporto differisce, viene richiesto di immettere una nuova posizione di ordinamento e di assegnare una targa a quella posizione.</span><span class="sxs-lookup"><span data-stu-id="6449f-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="6449f-564">Utilizzare la posizione ordinamento *SP02* e la targa *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="6449f-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="6449f-565">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-565">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-566">Confermare la posizione di ordinamento immettendo *SP02* nel campo **ID posizione di ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="6449f-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="6449f-567">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-567">Select **OK**.</span></span>

    <span data-ttu-id="6449f-568">Il lavoro è completato per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="6449f-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="6449f-569">Nel campo **Targa/Con**, immettere l'ID contenitore per il contenitore rimanente dell'ordine cliente 2 che contiene l'articolo *A0002*.</span><span class="sxs-lookup"><span data-stu-id="6449f-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="6449f-570">Poiché il servizio di trasporto è uguale a quello dell'ordine cliente 1, il sistema mostra la posizione di ordinamento esistente che ha criteri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6449f-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="6449f-571">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-571">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-572">Confermare la posizione di ordinamento immettendo *SP01* nel campo **ID posizione di ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="6449f-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="6449f-573">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-573">Select **OK**.</span></span>

    <span data-ttu-id="6449f-574">Il lavoro è completato per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="6449f-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="6449f-575">Chiudere le posizioni di ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="6449f-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="6449f-576">Quando tutte le scorte sono state ordinate, la posizione deve essere chiusa prima di poter creare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="6449f-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="6449f-577">Verrà creato un lavoro di prelievo delle scorte ordinate per portare le scorte al portellone.</span><span class="sxs-lookup"><span data-stu-id="6449f-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="6449f-578">Chiudere una posizione dal dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="6449f-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="6449f-579">Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).</span><span class="sxs-lookup"><span data-stu-id="6449f-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="6449f-580">Nel menu principale, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="6449f-581">Nel menu **In uscita**, selezionare **Creazione pallet**.</span><span class="sxs-lookup"><span data-stu-id="6449f-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="6449f-582">Nel campo **Targa/Con**, immettere un ID contenitore che è stato ordinato per ordinare la posizione *SP01*.</span><span class="sxs-lookup"><span data-stu-id="6449f-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="6449f-583">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-583">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-584">Viene visualizzato il seguente messaggio: "Il contenitore è già ordinato nella posizione SP01.</span><span class="sxs-lookup"><span data-stu-id="6449f-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="6449f-585">Chiudere la posizione?".</span><span class="sxs-lookup"><span data-stu-id="6449f-585">Close the position?"</span></span> <span data-ttu-id="6449f-586">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6449f-586">Select **Close**.</span></span>

    <span data-ttu-id="6449f-587">Il lavoro è completato.</span><span class="sxs-lookup"><span data-stu-id="6449f-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="6449f-588">Chiudere una posizione dalle assegnazioni delle posizioni di ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="6449f-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="6449f-589">Selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Assegnazioni di posizioni di ordinamento in uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="6449f-590">Nella colonna sinistra selezionare **SP02**.</span><span class="sxs-lookup"><span data-stu-id="6449f-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="6449f-591">Questa riga della posizione di ordinamento in uscita è quella che verrà chiusa.</span><span class="sxs-lookup"><span data-stu-id="6449f-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="6449f-592">Nel riquadro azioni selezionare **Chiudi posizione**.</span><span class="sxs-lookup"><span data-stu-id="6449f-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="6449f-593">Il record della posizione di ordinamento viene chiuso e non è più visualizzato.</span><span class="sxs-lookup"><span data-stu-id="6449f-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="6449f-594">Per visualizzare tutti i record della posizione chiusa, selezionare la casella di controllo **Mostra chiuso**.</span><span class="sxs-lookup"><span data-stu-id="6449f-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="6449f-595">Prelievo scorte ordinate</span><span class="sxs-lookup"><span data-stu-id="6449f-595">Sorted inventory picking</span></span>

<span data-ttu-id="6449f-596">È necessario completare il lavoro di prelievo dell'inventario ordinato.</span><span class="sxs-lookup"><span data-stu-id="6449f-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="6449f-597">Al termine, le scorte saranno prelevate nell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6449f-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="6449f-598">A quel punto, si applicano tutti gli altri processi di magazzino.</span><span class="sxs-lookup"><span data-stu-id="6449f-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="6449f-599">Nel dispositivo mobile, accedere al magazzino *62* utilizzando l'ID utente creato per questo scenario (o l'ID utente di un utente di dati dimostrativi esistente).</span><span class="sxs-lookup"><span data-stu-id="6449f-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="6449f-600">Nel menu principale, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6449f-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="6449f-601">Nel menu **In uscita**, selezionare **Carica da ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="6449f-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="6449f-602">Immettere l'ID targa di destinazione dalla prima posizione di ordinamento, *SP01*.</span><span class="sxs-lookup"><span data-stu-id="6449f-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="6449f-603">Impostare il campo **ID** su *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="6449f-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="6449f-604">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-604">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-605">La pagina **Prelievo scorte ordinate: Prelievo** mostra il lavoro di prelievo che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="6449f-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="6449f-606">Prelevare dall'ubicazione *ORDINAMENTO* e dalla targa di destinazione *PLP01*, che ha più articoli e una quantità pari a *3*.</span><span class="sxs-lookup"><span data-stu-id="6449f-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="6449f-607">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-607">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-608">La pagina **Prelievo scorte ordinate: Stoccaggio** mostra il lavoro di stoccaggio che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="6449f-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="6449f-609">Stoccare nell'ubicazione *Portellone* e nella targa di destinazione *PLP01*, che ha più articoli e una quantità pari a *3*.</span><span class="sxs-lookup"><span data-stu-id="6449f-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="6449f-610">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-610">Select **OK**.</span></span>

    <span data-ttu-id="6449f-611">Il lavoro è completato.</span><span class="sxs-lookup"><span data-stu-id="6449f-611">Work is completed.</span></span>

1. <span data-ttu-id="6449f-612">Immettere l'ID targa di destinazione della seconda posizione di ordinamento, *SP02*.</span><span class="sxs-lookup"><span data-stu-id="6449f-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="6449f-613">Impostare il campo **ID** su *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="6449f-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="6449f-614">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-614">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-615">La pagina **Prelievo scorte ordinate: Prelievo** mostra il lavoro di prelievo che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="6449f-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="6449f-616">Prelevare dall'ubicazione *ORDINAMENTO* e dalla targa di destinazione *PLP02*, che ha più articoli e una quantità pari a *1*.</span><span class="sxs-lookup"><span data-stu-id="6449f-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="6449f-617">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-617">Select **OK**.</span></span>
1. <span data-ttu-id="6449f-618">La pagina **Prelievo scorte ordinate: Stoccaggio** mostra il lavoro di stoccaggio che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="6449f-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="6449f-619">Stoccare nell'ubicazione *Portellone* e nella targa di destinazione *PLP02*, che ha più articoli e una quantità pari a *1*.</span><span class="sxs-lookup"><span data-stu-id="6449f-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="6449f-620">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6449f-620">Select **OK**.</span></span>

    <span data-ttu-id="6449f-621">Il lavoro è completato.</span><span class="sxs-lookup"><span data-stu-id="6449f-621">Work is completed.</span></span>

<span data-ttu-id="6449f-622">Da questo momento, si applicano tutti gli altri processi di magazzino.</span><span class="sxs-lookup"><span data-stu-id="6449f-622">From this point forward, all other warehouse processes apply.</span></span>
