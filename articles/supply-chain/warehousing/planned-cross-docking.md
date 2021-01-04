---
title: Cross-docking pianificato
description: Questo argomento descrive il cross-docking pianificato avanzato, in cui la quantità di scorte richiesta per un ordine viene indirizzata direttamente dalla ricevuta o dalla creazione alla banchina di uscita o alla zona di transito corretta. Tutte le scorte rimanenti dall'origine in entrata vengono indirizzate all'ubicazione di magazzino corretta attraverso il normale processo di stoccaggio.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: cc217f21a5fa70feb9ef9161f3ef2e2b6a333f35
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431548"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="5e230-104">Cross-docking pianificato</span><span class="sxs-lookup"><span data-stu-id="5e230-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e230-105">Questo argomento descrive il cross docking pianificato avanzato.</span><span class="sxs-lookup"><span data-stu-id="5e230-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="5e230-106">Il cross-docking è un processo di magazzino in cui la quantità di scorte richiesta per un ordine viene indirizzata direttamente dalla ricevuta o dalla creazione alla banchina di uscita o alla zona di transito corretta.</span><span class="sxs-lookup"><span data-stu-id="5e230-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="5e230-107">Tutte le scorte rimanenti dall'origine in entrata vengono indirizzate all'ubicazione di magazzino corretta attraverso il normale processo di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="5e230-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="5e230-108">Il cross-docking consente ai lavoratori di saltare lo stoccaggio in entrata e il prelievo in uscita delle scorte già contrassegnate per un ordine in uscita.</span><span class="sxs-lookup"><span data-stu-id="5e230-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="5e230-109">Pertanto, il numero di volte in cui l'inventario viene toccato viene ridotto al minimo, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="5e230-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="5e230-110">Inoltre, poiché vi è una minore interazione con il sistema, i risparmi di tempo e spazio nello shop floor del magazzino aumentano.</span><span class="sxs-lookup"><span data-stu-id="5e230-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="5e230-111">Prima di poter eseguire il cross-docking, l'utente deve configurare un nuovo modello di cross-docking, in cui sono specificati l'origine di approvvigionamento e altri set di requisiti per il cross-docking.</span><span class="sxs-lookup"><span data-stu-id="5e230-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="5e230-112">Quando viene creato l'ordine di uscita, la riga deve essere contrassegnata a fronte di un ordine di entrata che contiene lo stesso articolo.</span><span class="sxs-lookup"><span data-stu-id="5e230-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="5e230-113">Al momento della ricezione dell'ordine in entrata, la configurazione del cross-docking identifica automaticamente la necessità di cross-docking e crea il lavoro di movimentazione per la quantità richiesta, in base all'impostazione della direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5e230-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="5e230-114">Le transazioni di magazzino **non** sono esenti da registrazione quando viene annullato il lavoro di cross-docking, anche se l'impostazione per questa funzionalità è attivata nei parametri di gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="5e230-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-feature"></a><span data-ttu-id="5e230-115">Attivare la funzionalità di cross docking pianificata</span><span class="sxs-lookup"><span data-stu-id="5e230-115">Turn on the Planned cross docking feature</span></span>

<span data-ttu-id="5e230-116">Prima di poter utilizzare il cross-docking pianificato avanzato, è necessario attivare due funzionalità nel sistema.</span><span class="sxs-lookup"><span data-stu-id="5e230-116">Before you can use advanced planned cross-docking, the feature must be turned on in your system.</span></span> <span data-ttu-id="5e230-117">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="5e230-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="5e230-118">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="5e230-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="5e230-119">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="5e230-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="5e230-120">**Nome funzionalità:** *Cross docking pianificato*</span><span class="sxs-lookup"><span data-stu-id="5e230-120">**Feature name:** *Planned cross docking*</span></span>

## <a name="setup"></a><span data-ttu-id="5e230-121">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="5e230-121">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="5e230-122">Rigenerare i metodi di registrazione del carico</span><span class="sxs-lookup"><span data-stu-id="5e230-122">Regenerate load posting methods</span></span>

<span data-ttu-id="5e230-123">Il cross-docking pianificato è implementato come metodo di registrazione del carico.</span><span class="sxs-lookup"><span data-stu-id="5e230-123">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="5e230-124">Dopo aver attivato la funzionalità, è necessario rigenerare i metodi.</span><span class="sxs-lookup"><span data-stu-id="5e230-124">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="5e230-125">Accedi a **Gestione magazzino** \> Impostazione \> Metodi di registrazione carico.</span><span class="sxs-lookup"><span data-stu-id="5e230-125">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="5e230-126">Nel riquadro azioni, seleziona **Rigenera metodi**.</span><span class="sxs-lookup"><span data-stu-id="5e230-126">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="5e230-127">Quando la rigenerazione è completa, dovresti vedere un metodo che ha un valore **Nome del metodo** di *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="5e230-127">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="5e230-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5e230-128">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="5e230-129">Creare un modello di cross-docking</span><span class="sxs-lookup"><span data-stu-id="5e230-129">Create a cross-docking template</span></span>

1. <span data-ttu-id="5e230-130">Vai a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di cross-docking**.</span><span class="sxs-lookup"><span data-stu-id="5e230-130">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="5e230-131">Nel riquadro azioni seleziona **Nuovo** per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="5e230-131">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="5e230-132">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-132">In the header, set the following values:</span></span>

    - <span data-ttu-id="5e230-133">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e230-133">**Sequence:** *1*</span></span>

        <span data-ttu-id="5e230-134">Questo campo definisce l'ordine in cui vengono valutati i modelli.</span><span class="sxs-lookup"><span data-stu-id="5e230-134">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="5e230-135">**ID modello di cross-docking:** *51*</span><span class="sxs-lookup"><span data-stu-id="5e230-135">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="5e230-136">**Descrizione:** *Magazzino 51*</span><span class="sxs-lookup"><span data-stu-id="5e230-136">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="5e230-137">**Criteri di rilascio della domanda:** *Prima del ricevimento della fornitura*</span><span class="sxs-lookup"><span data-stu-id="5e230-137">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="5e230-138">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="5e230-138">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="5e230-139">L'impostazione sulla Scheda dettaglio **Pianificazione** controlla il funzionamento del modello.</span><span class="sxs-lookup"><span data-stu-id="5e230-139">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="5e230-140">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e230-140">Set the following values:</span></span>

    - <span data-ttu-id="5e230-141">**Fabbisogno della domanda:** *Nessuno*</span><span class="sxs-lookup"><span data-stu-id="5e230-141">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="5e230-142">Questo campo definisce il fabbisogno di scorte della domanda.</span><span class="sxs-lookup"><span data-stu-id="5e230-142">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="5e230-143">Se la domanda deve essere collegata all'offerta prima del rilascio, seleziona *Contrassegno*.</span><span class="sxs-lookup"><span data-stu-id="5e230-143">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="5e230-144">Se la domanda deve essere prenotata dall'ordine a fronte dell'offerta prima del rilascio, seleziona *Prenotazione ordine*.</span><span class="sxs-lookup"><span data-stu-id="5e230-144">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="5e230-145">**Tipo di individuazione:** *Ubicazioni di spedizione*</span><span class="sxs-lookup"><span data-stu-id="5e230-145">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="5e230-146">Questo campo definisce se il lavoro di cross-docking deve utilizzare le ubicazioni di transito/carico dalla spedizione o se deve utilizzare le direttive di ubicazione per trovare le proprie ubicazioni di transizione/carico.</span><span class="sxs-lookup"><span data-stu-id="5e230-146">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="5e230-147">**Modello di lavoro**: lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="5e230-147">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="5e230-148">Questo campo definisce il modello di lavoro che deve essere utilizzato quando viene creato il lavoro di cross-docking.</span><span class="sxs-lookup"><span data-stu-id="5e230-148">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="5e230-149">**Riconvalida al ricevimento della fornitura:** *No*</span><span class="sxs-lookup"><span data-stu-id="5e230-149">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="5e230-150">Questa opzione definisce se la fornitura deve essere riconvalidata al momento del ricevimento.</span><span class="sxs-lookup"><span data-stu-id="5e230-150">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="5e230-151">Se questa opzione è impostata su *Sì*, vengono controllati sia l'intervallo di tempo massimo sia l'intervallo di giorni di scadenza.</span><span class="sxs-lookup"><span data-stu-id="5e230-151">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="5e230-152">**Convalida finestra temporale:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="5e230-152">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="5e230-153">Questa opzione definisce se la finestra temporale massima deve essere valutata quando viene selezionata una fonte di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="5e230-153">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="5e230-154">Se questa opzione è impostata su *Sì*, diventano disponibili i campi correlati alle finestre di tempo massimo e minimo.</span><span class="sxs-lookup"><span data-stu-id="5e230-154">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="5e230-155">**Intervallo di tempo massimo:** *5*</span><span class="sxs-lookup"><span data-stu-id="5e230-155">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="5e230-156">Il campo definisce il periodo massimo consentito tra l'arrivo della fornitura e la partenza della domanda.</span><span class="sxs-lookup"><span data-stu-id="5e230-156">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="5e230-157">**Unità intervallo di tempo massimo:** *Giorni*</span><span class="sxs-lookup"><span data-stu-id="5e230-157">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="5e230-158">**Intervallo di tempo minimo:** *0*</span><span class="sxs-lookup"><span data-stu-id="5e230-158">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="5e230-159">Il campo definisce il periodo minimo consentito tra l'arrivo della fornitura e la partenza della domanda.</span><span class="sxs-lookup"><span data-stu-id="5e230-159">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="5e230-160">**Unità intervallo di tempo minimo:** *Giorni*</span><span class="sxs-lookup"><span data-stu-id="5e230-160">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="5e230-161">**Intervallo giorni di scadenza:** *0*</span><span class="sxs-lookup"><span data-stu-id="5e230-161">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="5e230-162">*Criteri FEFO (first out first first out):* questo campo definisce il numero massimo di giorni tra la data di scadenza del lotto in scadenza al momento che è attualmente nel magazzino e il lotto in ricezione.</span><span class="sxs-lookup"><span data-stu-id="5e230-162">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="5e230-163">Nella Scheda dettaglio **Fonti di approvvigionamento**, si specificano i tipi di fornitura validi per questo modello.</span><span class="sxs-lookup"><span data-stu-id="5e230-163">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="5e230-164">Seleziona **Nuovo**, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-164">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="5e230-165">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e230-165">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="5e230-166">**Fonte di approvvigionamento:** *Ordine fornitore*</span><span class="sxs-lookup"><span data-stu-id="5e230-166">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="5e230-167">Creare una classe di lavoro</span><span class="sxs-lookup"><span data-stu-id="5e230-167">Create a work class</span></span>

1. <span data-ttu-id="5e230-168">Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5e230-168">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="5e230-169">Nel riquadro azioni seleziona **Nuova** per creare una nuova classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e230-169">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="5e230-170">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e230-170">Set the following values:</span></span>

    - <span data-ttu-id="5e230-171">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="5e230-171">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="5e230-172">**Descrizione:** *Cross-docking*</span><span class="sxs-lookup"><span data-stu-id="5e230-172">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="5e230-173">**Tipo di ordine di lavoro:** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="5e230-173">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="5e230-174">Creare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="5e230-174">Create a work template</span></span>

1. <span data-ttu-id="5e230-175">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5e230-175">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="5e230-176">Imposta il campo **Tipo ordine di lavoro** su *Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="5e230-176">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="5e230-177">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla scheda **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="5e230-177">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="5e230-178">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-178">On the new line, set the following values:</span></span>

    - <span data-ttu-id="5e230-179">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e230-179">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="5e230-180">**Modello di lavoro:** *Cross-docking 51*</span><span class="sxs-lookup"><span data-stu-id="5e230-180">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="5e230-181">**Descrizione modello di lavoro:** *Cross-docking 51*</span><span class="sxs-lookup"><span data-stu-id="5e230-181">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="5e230-182">Seleziona **Salva** per rendere la Scheda dettaglio **Dettagli modello di lavoro** disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e230-182">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="5e230-183">Nella Scheda dettaglio **Dettagli modello di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="5e230-183">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="5e230-184">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-184">On the new line, set the following values:</span></span>

    - <span data-ttu-id="5e230-185">**Tipo di lavoro:** *Prelevare*</span><span class="sxs-lookup"><span data-stu-id="5e230-185">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="5e230-186">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="5e230-186">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="5e230-187">Seleziona **Nuova** per aggiungere un'altra riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-187">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="5e230-188">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="5e230-188">**Work type:** *Put*</span></span>
    - <span data-ttu-id="5e230-189">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="5e230-189">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="5e230-190">Seleziona **Salva** e verifica che la casella di controllo **Valido** sia selezionata per il modello *51 Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="5e230-190">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="5e230-191">Gli ID della classe di lavoro per i tipi di lavoro *Preleva* e *Inserisci* devono essere gli stessi.</span><span class="sxs-lookup"><span data-stu-id="5e230-191">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="5e230-192">Creare direttive di ubicazione</span><span class="sxs-lookup"><span data-stu-id="5e230-192">Create location directives</span></span>

1. <span data-ttu-id="5e230-193">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="5e230-193">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="5e230-194">Nel riquadro sinistro, imposta il campo **Tipo di ordine di lavoro** su *Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="5e230-194">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="5e230-195">Nel riquadro azioni, seleziona **Nuovo**, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-195">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="5e230-196">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e230-196">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="5e230-197">**Nome:** *51 inserisci cross-docking*</span><span class="sxs-lookup"><span data-stu-id="5e230-197">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="5e230-198">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="5e230-198">**Work type:** *Put*</span></span>
    - <span data-ttu-id="5e230-199">**Sito:** *5*</span><span class="sxs-lookup"><span data-stu-id="5e230-199">**Site:** *5*</span></span>
    - <span data-ttu-id="5e230-200">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="5e230-200">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="5e230-201">Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e230-201">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="5e230-202">Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="5e230-202">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="5e230-203">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-203">On the new line, set the following values:</span></span>

    - <span data-ttu-id="5e230-204">**Da quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e230-204">**From quantity:** *1*</span></span>
    - <span data-ttu-id="5e230-205">**A quantità:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="5e230-205">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="5e230-206">Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e230-206">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="5e230-207">Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="5e230-207">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="5e230-208">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="5e230-209">**Nome:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="5e230-209">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="5e230-210">**Utilizzo ubicazioni fisse:** *Ubicazioni fisse e non fisse*</span><span class="sxs-lookup"><span data-stu-id="5e230-210">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="5e230-211">Seleziona **Salva** per rendere il pulsante **Modifica query** nella barra degli strumenti **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e230-211">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="5e230-212">Seleziona **Modifica query** per aprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="5e230-212">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="5e230-213">Nella scheda **Intervallo**, verifica che siano configurate le seguenti due righe:</span><span class="sxs-lookup"><span data-stu-id="5e230-213">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="5e230-214">Riga 1:</span><span class="sxs-lookup"><span data-stu-id="5e230-214">Line 1:</span></span>

        - <span data-ttu-id="5e230-215">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="5e230-215">**Table:** *Locations*</span></span>
        - <span data-ttu-id="5e230-216">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="5e230-216">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="5e230-217">**Campo:** *Magazzino*</span><span class="sxs-lookup"><span data-stu-id="5e230-217">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="5e230-218">**Criteri:** *51*</span><span class="sxs-lookup"><span data-stu-id="5e230-218">**Criteria:** *51*</span></span>

    - <span data-ttu-id="5e230-219">Riga 2:</span><span class="sxs-lookup"><span data-stu-id="5e230-219">Line 2:</span></span>

        - <span data-ttu-id="5e230-220">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="5e230-220">**Table:** *Locations*</span></span>
        - <span data-ttu-id="5e230-221">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="5e230-221">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="5e230-222">**Campo:** *Ubicazione*</span><span class="sxs-lookup"><span data-stu-id="5e230-222">**Field:** *Location*</span></span>
        - <span data-ttu-id="5e230-223">**Criteri:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="5e230-223">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="5e230-224">Seleziona **OK** per chiudere l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="5e230-224">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="5e230-225">Creare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="5e230-225">Create a mobile device menu item</span></span>

1. <span data-ttu-id="5e230-226">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="5e230-226">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="5e230-227">Nell'elenco delle voci di menu nel riquadro sinistro, seleziona **Stoccaggio dell'ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="5e230-227">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="5e230-228">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5e230-228">Select **Edit**.</span></span>
1. <span data-ttu-id="5e230-229">Nella Scheda dettaglio **Classi di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="5e230-229">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="5e230-230">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-230">On the new line, set the following values:</span></span>

    - <span data-ttu-id="5e230-231">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="5e230-231">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="5e230-232">**Tipo di ordine di lavoro:** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="5e230-232">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="5e230-233">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5e230-233">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="5e230-234">Scenario</span><span class="sxs-lookup"><span data-stu-id="5e230-234">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="5e230-235">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="5e230-235">Create a purchase order</span></span>

<span data-ttu-id="5e230-236">Segui questi passaggi per creare un ordine fornitore come fonte di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="5e230-236">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="5e230-237">Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="5e230-237">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="5e230-238">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5e230-238">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e230-239">Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-239">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5e230-240">**Conto fornitore:** *104*</span><span class="sxs-lookup"><span data-stu-id="5e230-240">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="5e230-241">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="5e230-241">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="5e230-242">Seleziona **OK** e prendi nota del numero dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="5e230-242">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="5e230-243">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="5e230-243">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="5e230-244">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-244">On this line, set the following values:</span></span>

    - <span data-ttu-id="5e230-245">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="5e230-245">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="5e230-246">**Quantità:** *5*</span><span class="sxs-lookup"><span data-stu-id="5e230-246">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="5e230-247">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="5e230-247">Create a sales order</span></span>

<span data-ttu-id="5e230-248">Segui questi passaggi per creare un ordine cliente come origine della domanda.</span><span class="sxs-lookup"><span data-stu-id="5e230-248">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="5e230-249">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="5e230-249">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="5e230-250">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5e230-250">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e230-251">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-251">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5e230-252">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="5e230-252">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="5e230-253">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="5e230-253">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="5e230-254">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-254">Select **OK**.</span></span>
1. <span data-ttu-id="5e230-255">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="5e230-255">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="5e230-256">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e230-256">On this line, set the following values:</span></span>

    - <span data-ttu-id="5e230-257">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="5e230-257">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="5e230-258">**Quantità:** *3*</span><span class="sxs-lookup"><span data-stu-id="5e230-258">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="5e230-259">Creare cross-docking pianificato</span><span class="sxs-lookup"><span data-stu-id="5e230-259">Create planned cross-docking</span></span>

<span data-ttu-id="5e230-260">Segui questi passaggi per creare il cross-docking pianificato dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="5e230-260">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="5e230-261">Nella pagina **Dettagli ordine cliente** per l'ordine cliente appena creato, nel riquadro azioni, nella scheda **Magazzino** del gruppo **Azioni**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="5e230-261">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="5e230-262">L'operazione di rilascio in magazzino crea una riga di spedizione e di carico per la riga ordine client e tenta di allocare le scorte.</span><span class="sxs-lookup"><span data-stu-id="5e230-262">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="5e230-263">Viene visualizzato un messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="5e230-263">You receive an informational message.</span></span> <span data-ttu-id="5e230-264">Viene inoltre visualizzato il seguente messaggio di avviso: "Nessun lavoro creato per l'ondata XXXX.</span><span class="sxs-lookup"><span data-stu-id="5e230-264">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="5e230-265">Vedi il registro della cronologia di creazione del lavoro per i dettagli. "</span><span class="sxs-lookup"><span data-stu-id="5e230-265">See the work creation history log for details."</span></span> <span data-ttu-id="5e230-266">Questo comportamento è previsto perché non sono presenti scorte nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="5e230-266">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="5e230-267">Nella scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino**, seleziona **Dettagli spedizione**.</span><span class="sxs-lookup"><span data-stu-id="5e230-267">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="5e230-268">La pagina **Dettagli spedizione** viene visualizzata e mostra la spedizione creata per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="5e230-268">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="5e230-269">Nella Scheda dettaglio **Righe di carico**, il campo **Quantità cross-dockin pianificata** è impostato su *3*.</span><span class="sxs-lookup"><span data-stu-id="5e230-269">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="5e230-270">Poiché non erano disponibili scorte nel magazzino, ma una fonte di approvvigionamento valida arriverà entro l'intervallo di tempo definito nel modello di cross-docking, la quantità cross-docking è stata creata.</span><span class="sxs-lookup"><span data-stu-id="5e230-270">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="5e230-271">Nella Scheda dettaglio **Righe di carico**, seleziona **Cross-docking pianificato** per visualizzare i dettagli del cross-docking creato.</span><span class="sxs-lookup"><span data-stu-id="5e230-271">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="5e230-272">Elaborare il cross-docking</span><span class="sxs-lookup"><span data-stu-id="5e230-272">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="5e230-273">Ricezione dell'ordine fornitore nell'app per dispositivi mobili di magazzino</span><span class="sxs-lookup"><span data-stu-id="5e230-273">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="5e230-274">Il sistema riceverà la quantità di 5 dall'ordine di acquisto nell'ubicazione di ricevimento e creerà due parti del lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e230-274">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="5e230-275">Il primo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Cross docking* ed è collegato all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="5e230-275">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="5e230-276">Ha una quantità di 3 ed è diretto al luogo di spedizione finale in modo che possa essere spedito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="5e230-276">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="5e230-277">Il secondo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Ordini fornitore* ed è collegato all'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="5e230-277">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="5e230-278">Ha la quantità rimanente di 2 che non era cross-docking ed è indirizzata allo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="5e230-278">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="5e230-279">Accedi al dispositivo mobile come un utente in magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="5e230-279">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="5e230-280">Vai a **In entrata \> Entrata acquisto**.</span><span class="sxs-lookup"><span data-stu-id="5e230-280">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="5e230-281">Nel campo **Numero ordine fornitore**, inserisci il numero dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="5e230-281">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="5e230-282">Nel campo **Qtà** immetti *5*.</span><span class="sxs-lookup"><span data-stu-id="5e230-282">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="5e230-283">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-283">Select **OK**.</span></span>
1. <span data-ttu-id="5e230-284">Nella pagina successiva, imposta il campo **Articolo** su *A0001*.</span><span class="sxs-lookup"><span data-stu-id="5e230-284">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="5e230-285">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-285">Select **OK**.</span></span>
1. <span data-ttu-id="5e230-286">Nella pagina successiva, conferma i valori **Numero ordine fornitore**, **Articolo** e **Quantità** selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-286">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="5e230-287">Ricevi un messaggio di tipo Lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="5e230-287">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="5e230-288">Seleziona **Annulla** per uscire.</span><span class="sxs-lookup"><span data-stu-id="5e230-288">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="5e230-289">Stoccaggio su cross-docking e in blocco</span><span class="sxs-lookup"><span data-stu-id="5e230-289">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="5e230-290">Attualmente, entrambi gli ID lavoro hanno la stessa targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e230-290">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="5e230-291">Per completare i passaggi successivi, è necessario ottenere l'ID lavoro e l'ID targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e230-291">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="5e230-292">È possibile ottenere queste informazioni dai dettagli di lavoro per la riga ordine fornitore e la riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="5e230-292">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="5e230-293">In alternativa, puoi andare a **Gestione magazzino \> Lavoro \> Dettagli del lavoro** e filtrsre per il lavoro in cui il valore **Magazzino** è *51*.</span><span class="sxs-lookup"><span data-stu-id="5e230-293">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="5e230-294">Sul dispositivo mobile, vai a **In entrata \> Stoccaggio acquisto** e immetti la targa di destinazione dal lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e230-294">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="5e230-295">Nel campo **ID**, immetti l'ID targa di destinazione dai dettagli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e230-295">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="5e230-296">La pagina di preliveo di cross-docking mostra l'ubicazione di prelievo (*RECV*), la targa di destinazione (*targa*), l'articolo (*A0001*) e la quantità (*3*).</span><span class="sxs-lookup"><span data-stu-id="5e230-296">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="5e230-297">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-297">Select **OK**.</span></span>
1. <span data-ttu-id="5e230-298">Nel campo **Targa di destinazione**, immetti una targa di destinazione per l'ID targa che deve essere inserito (cross-docking) nell'ubicazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="5e230-298">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="5e230-299">È possibile selezionare qualsiasi ID targa di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="5e230-299">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="5e230-300">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-300">Select **OK**.</span></span>
1. <span data-ttu-id="5e230-301">Nella pagina successiva, nel campo **ID**, immetti l'ID targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e230-301">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="5e230-302">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-302">Select **OK**.</span></span>
1. <span data-ttu-id="5e230-303">Conferma il lavoro per selezionare la quantità rimanente di 2, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-303">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="5e230-304">Nella pagina successiva, seleziona **Fatto** per terminare il processo di raccolta e iniziare il processo di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="5e230-304">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="5e230-305">L'app per dispositivi mobili mostra l'ubicazione e la targa in cui collocare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5e230-305">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="5e230-306">Conferma il comando **Inserisci** dello stoccaggio in blocco selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-306">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="5e230-307">Nella pagina successiva, confermare il cross-docking **Inserisci** selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e230-307">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="5e230-308">Ricevi un messaggio di tipo Lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="5e230-308">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="5e230-309">Seleziona **Annulla** per uscire.</span><span class="sxs-lookup"><span data-stu-id="5e230-309">Select **Cancel** to exit.</span></span>

<span data-ttu-id="5e230-310">La seguente illustrazione mostra come il lavoro cross-docking completato potrebbe apparire in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5e230-310">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="5e230-311">![Lavoro di cross docking completato](media/PlannedCrossDockingWork.png "Lavoro di cross docking completato")</span><span class="sxs-lookup"><span data-stu-id="5e230-311">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>
