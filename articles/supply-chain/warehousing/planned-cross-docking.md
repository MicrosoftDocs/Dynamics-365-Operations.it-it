---
title: Cross-docking pianificato
description: Questo argomento descrive il cross-docking pianificato avanzato, in cui la quantità di scorte richiesta per un ordine viene indirizzata direttamente dalla ricevuta o dalla creazione alla banchina di uscita o alla zona di transito corretta. Tutte le scorte rimanenti dall'origine in entrata vengono indirizzate all'ubicazione di magazzino corretta attraverso il normale processo di stoccaggio.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 49807c90c145eee55fae2d515fd19925eb2d944c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810416"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="b94d2-104">Cross-docking pianificato</span><span class="sxs-lookup"><span data-stu-id="b94d2-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b94d2-105">Questo argomento descrive il cross docking pianificato avanzato.</span><span class="sxs-lookup"><span data-stu-id="b94d2-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="b94d2-106">Il cross-docking è un processo di magazzino in cui la quantità di scorte richiesta per un ordine viene indirizzata direttamente dalla ricevuta o dalla creazione alla banchina di uscita o alla zona di transito corretta.</span><span class="sxs-lookup"><span data-stu-id="b94d2-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="b94d2-107">Tutte le scorte rimanenti dall'origine in entrata vengono indirizzate all'ubicazione di magazzino corretta attraverso il normale processo di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="b94d2-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="b94d2-108">Il cross-docking consente ai lavoratori di saltare lo stoccaggio in entrata e il prelievo in uscita delle scorte già contrassegnate per un ordine in uscita.</span><span class="sxs-lookup"><span data-stu-id="b94d2-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="b94d2-109">Pertanto, il numero di volte in cui l'inventario viene toccato viene ridotto al minimo, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="b94d2-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="b94d2-110">Inoltre, poiché vi è una minore interazione con il sistema, i risparmi di tempo e spazio nello shop floor del magazzino aumentano.</span><span class="sxs-lookup"><span data-stu-id="b94d2-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="b94d2-111">Prima di poter eseguire il cross-docking, l'utente deve configurare un nuovo modello di cross-docking, in cui sono specificati l'origine di approvvigionamento e altri set di requisiti per il cross-docking.</span><span class="sxs-lookup"><span data-stu-id="b94d2-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="b94d2-112">Quando viene creato l'ordine di uscita, la riga deve essere contrassegnata a fronte di un ordine di entrata che contiene lo stesso articolo.</span><span class="sxs-lookup"><span data-stu-id="b94d2-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="b94d2-113">Al momento della ricezione dell'ordine in entrata, la configurazione del cross-docking identifica automaticamente la necessità di cross-docking e crea il lavoro di movimentazione per la quantità richiesta, in base all'impostazione della direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="b94d2-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="b94d2-114">Le transazioni di magazzino **non** sono esenti da registrazione quando viene annullato il lavoro di cross-docking, anche se l'impostazione per questa funzionalità è attivata nei parametri di gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="b94d2-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="b94d2-115">Attivare le funzionalità di cross docking pianificato</span><span class="sxs-lookup"><span data-stu-id="b94d2-115">Turn on the planned cross docking features</span></span>

<span data-ttu-id="b94d2-116">Se il sistema in uso non include già le funzionalità descritte in questo argomento, vedere [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attivare le seguenti funzionalità nel seguente ordine:</span><span class="sxs-lookup"><span data-stu-id="b94d2-116">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="b94d2-117">*Cross-docking pianificato*</span><span class="sxs-lookup"><span data-stu-id="b94d2-117">*Planned cross docking*</span></span>
2. <span data-ttu-id="b94d2-118">*Modelli di cross-docking con direttive di ubicazione*</span><span class="sxs-lookup"><span data-stu-id="b94d2-118">*Cross docking templates with location directives*</span></span>

## <a name="setup"></a><span data-ttu-id="b94d2-119">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="b94d2-119">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="b94d2-120">Rigenerare i metodi di registrazione del carico</span><span class="sxs-lookup"><span data-stu-id="b94d2-120">Regenerate load posting methods</span></span>

<span data-ttu-id="b94d2-121">Il cross-docking pianificato è implementato come metodo di registrazione del carico.</span><span class="sxs-lookup"><span data-stu-id="b94d2-121">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="b94d2-122">Dopo aver attivato la funzionalità, è necessario rigenerare i metodi.</span><span class="sxs-lookup"><span data-stu-id="b94d2-122">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="b94d2-123">Accedi a **Gestione magazzino** \> Impostazione \> Metodi di registrazione carico.</span><span class="sxs-lookup"><span data-stu-id="b94d2-123">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="b94d2-124">Nel riquadro azioni, seleziona **Rigenera metodi**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-124">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="b94d2-125">Quando la rigenerazione è completa, dovresti vedere un metodo che ha un valore **Nome del metodo** di *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-125">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="b94d2-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b94d2-126">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="b94d2-127">Creare un modello di cross-docking</span><span class="sxs-lookup"><span data-stu-id="b94d2-127">Create a cross-docking template</span></span>

1. <span data-ttu-id="b94d2-128">Vai a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di cross-docking**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-128">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="b94d2-129">Nel riquadro azioni seleziona **Nuovo** per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="b94d2-129">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="b94d2-130">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-130">In the header, set the following values:</span></span>

    - <span data-ttu-id="b94d2-131">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="b94d2-131">**Sequence:** *1*</span></span>

        <span data-ttu-id="b94d2-132">Questo campo definisce l'ordine in cui vengono valutati i modelli.</span><span class="sxs-lookup"><span data-stu-id="b94d2-132">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="b94d2-133">**ID modello di cross-docking:** *51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-133">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="b94d2-134">**Descrizione:** *Magazzino 51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-134">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="b94d2-135">**Criteri di rilascio della domanda:** *Prima del ricevimento della fornitura*</span><span class="sxs-lookup"><span data-stu-id="b94d2-135">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="b94d2-136">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-136">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b94d2-137">L'impostazione sulla Scheda dettaglio **Pianificazione** controlla il funzionamento del modello.</span><span class="sxs-lookup"><span data-stu-id="b94d2-137">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="b94d2-138">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b94d2-138">Set the following values:</span></span>

    - <span data-ttu-id="b94d2-139">**Fabbisogno della domanda:** *Nessuno*</span><span class="sxs-lookup"><span data-stu-id="b94d2-139">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="b94d2-140">Questo campo definisce il fabbisogno di scorte della domanda.</span><span class="sxs-lookup"><span data-stu-id="b94d2-140">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="b94d2-141">Se la domanda deve essere collegata all'offerta prima del rilascio, seleziona *Contrassegno*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-141">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="b94d2-142">Se la domanda deve essere prenotata dall'ordine a fronte dell'offerta prima del rilascio, seleziona *Prenotazione ordine*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-142">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="b94d2-143">**Tipo di individuazione:** *Ubicazioni di spedizione*</span><span class="sxs-lookup"><span data-stu-id="b94d2-143">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="b94d2-144">Questo campo definisce se il lavoro di cross-docking deve utilizzare le ubicazioni di transito/carico dalla spedizione o se deve utilizzare le direttive di ubicazione per trovare le proprie ubicazioni di transizione/carico.</span><span class="sxs-lookup"><span data-stu-id="b94d2-144">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="b94d2-145">**Modello di lavoro**: lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b94d2-145">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="b94d2-146">Questo campo definisce il modello di lavoro che deve essere utilizzato quando viene creato il lavoro di cross-docking.</span><span class="sxs-lookup"><span data-stu-id="b94d2-146">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="b94d2-147">**Riconvalida al ricevimento della fornitura:** *No*</span><span class="sxs-lookup"><span data-stu-id="b94d2-147">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="b94d2-148">Questa opzione definisce se la fornitura deve essere riconvalidata al momento del ricevimento.</span><span class="sxs-lookup"><span data-stu-id="b94d2-148">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="b94d2-149">Se questa opzione è impostata su *Sì*, vengono controllati sia l'intervallo di tempo massimo sia l'intervallo di giorni di scadenza.</span><span class="sxs-lookup"><span data-stu-id="b94d2-149">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="b94d2-150">**Codice direttiva:** lasciare vuoto questo campo</span><span class="sxs-lookup"><span data-stu-id="b94d2-150">**Directive code** Leave this field blank</span></span>

        <span data-ttu-id="b94d2-151">Questa opzione consente al sistema di utilizzare le direttive di ubicazione per determinare l'ubicazione migliore in cui spostare l'inventario cross-docking.</span><span class="sxs-lookup"><span data-stu-id="b94d2-151">This option enables the system to use location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="b94d2-152">È possibile configurarla assegnando un codice direttiva a ciascun modello di cross-docking pertinente.</span><span class="sxs-lookup"><span data-stu-id="b94d2-152">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="b94d2-153">Ogni codice di direttiva identifica una direttiva di ubicazione univoca.</span><span class="sxs-lookup"><span data-stu-id="b94d2-153">Each directive code identifies a unique location directive.</span></span>

    - <span data-ttu-id="b94d2-154">**Convalida finestra temporale:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="b94d2-154">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="b94d2-155">Questa opzione definisce se la finestra temporale massima deve essere valutata quando viene selezionata una fonte di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="b94d2-155">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="b94d2-156">Se questa opzione è impostata su *Sì*, diventano disponibili i campi correlati alle finestre di tempo massimo e minimo.</span><span class="sxs-lookup"><span data-stu-id="b94d2-156">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="b94d2-157">**Intervallo di tempo massimo:** *5*</span><span class="sxs-lookup"><span data-stu-id="b94d2-157">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="b94d2-158">Il campo definisce il periodo massimo consentito tra l'arrivo della fornitura e la partenza della domanda.</span><span class="sxs-lookup"><span data-stu-id="b94d2-158">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b94d2-159">**Unità intervallo di tempo massimo:** *Giorni*</span><span class="sxs-lookup"><span data-stu-id="b94d2-159">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b94d2-160">**Intervallo di tempo minimo:** *0*</span><span class="sxs-lookup"><span data-stu-id="b94d2-160">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="b94d2-161">Il campo definisce il periodo minimo consentito tra l'arrivo della fornitura e la partenza della domanda.</span><span class="sxs-lookup"><span data-stu-id="b94d2-161">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b94d2-162">**Unità intervallo di tempo minimo:** *Giorni*</span><span class="sxs-lookup"><span data-stu-id="b94d2-162">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b94d2-163">**Intervallo giorni di scadenza:** *0*</span><span class="sxs-lookup"><span data-stu-id="b94d2-163">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="b94d2-164">*Criteri FEFO (first out first first out):* questo campo definisce il numero massimo di giorni tra la data di scadenza del lotto in scadenza al momento che è attualmente nel magazzino e il lotto in ricezione.</span><span class="sxs-lookup"><span data-stu-id="b94d2-164">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="b94d2-165">Nella Scheda dettaglio **Fonti di approvvigionamento**, si specificano i tipi di fornitura validi per questo modello.</span><span class="sxs-lookup"><span data-stu-id="b94d2-165">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="b94d2-166">Seleziona **Nuovo**, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-166">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="b94d2-167">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="b94d2-167">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b94d2-168">**Fonte di approvvigionamento:** *Ordine fornitore*</span><span class="sxs-lookup"><span data-stu-id="b94d2-168">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="b94d2-169">Creare una classe di lavoro</span><span class="sxs-lookup"><span data-stu-id="b94d2-169">Create a work class</span></span>

1. <span data-ttu-id="b94d2-170">Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-170">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="b94d2-171">Nel riquadro azioni seleziona **Nuova** per creare una nuova classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b94d2-171">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="b94d2-172">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b94d2-172">Set the following values:</span></span>

    - <span data-ttu-id="b94d2-173">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b94d2-173">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b94d2-174">**Descrizione:** *Cross-docking*</span><span class="sxs-lookup"><span data-stu-id="b94d2-174">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="b94d2-175">**Tipo di ordine di lavoro:** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="b94d2-175">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="b94d2-176">Creare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="b94d2-176">Create a work template</span></span>

1. <span data-ttu-id="b94d2-177">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-177">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b94d2-178">Imposta il campo **Tipo ordine di lavoro** su *Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-178">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b94d2-179">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla scheda **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-179">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="b94d2-180">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b94d2-181">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="b94d2-181">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b94d2-182">**Modello di lavoro:** *Cross-docking 51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-182">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="b94d2-183">**Descrizione modello di lavoro:** *Cross-docking 51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-183">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="b94d2-184">Seleziona **Salva** per rendere la Scheda dettaglio **Dettagli modello di lavoro** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b94d2-184">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="b94d2-185">Nella Scheda dettaglio **Dettagli modello di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b94d2-185">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b94d2-186">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b94d2-187">**Tipo di lavoro:** *Prelevare*</span><span class="sxs-lookup"><span data-stu-id="b94d2-187">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="b94d2-188">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b94d2-188">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b94d2-189">Seleziona **Nuova** per aggiungere un'altra riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-189">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="b94d2-190">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="b94d2-190">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b94d2-191">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b94d2-191">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b94d2-192">Seleziona **Salva** e verifica che la casella di controllo **Valido** sia selezionata per il modello *51 Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-192">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="b94d2-193">Gli ID della classe di lavoro per i tipi di lavoro *Preleva* e *Inserisci* devono essere gli stessi.</span><span class="sxs-lookup"><span data-stu-id="b94d2-193">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="b94d2-194">Creare direttive di ubicazione</span><span class="sxs-lookup"><span data-stu-id="b94d2-194">Create location directives</span></span>

1. <span data-ttu-id="b94d2-195">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-195">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b94d2-196">Nel riquadro sinistro, imposta il campo **Tipo di ordine di lavoro** su *Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-196">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b94d2-197">Nel riquadro azioni, seleziona **Nuovo**, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-197">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="b94d2-198">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="b94d2-198">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b94d2-199">**Nome:** *51 inserisci cross-docking*</span><span class="sxs-lookup"><span data-stu-id="b94d2-199">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="b94d2-200">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="b94d2-200">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b94d2-201">**Sito:** *5*</span><span class="sxs-lookup"><span data-stu-id="b94d2-201">**Site:** *5*</span></span>
    - <span data-ttu-id="b94d2-202">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-202">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b94d2-203">Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b94d2-203">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="b94d2-204">Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b94d2-204">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b94d2-205">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-205">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b94d2-206">**Da quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="b94d2-206">**From quantity:** *1*</span></span>
    - <span data-ttu-id="b94d2-207">**A quantità:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="b94d2-207">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="b94d2-208">Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b94d2-208">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="b94d2-209">Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b94d2-209">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b94d2-210">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-210">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b94d2-211">**Nome:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="b94d2-211">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="b94d2-212">**Utilizzo ubicazioni fisse:** *Ubicazioni fisse e non fisse*</span><span class="sxs-lookup"><span data-stu-id="b94d2-212">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="b94d2-213">Seleziona **Salva** per rendere il pulsante **Modifica query** nella barra degli strumenti **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b94d2-213">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="b94d2-214">Seleziona **Modifica query** per aprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="b94d2-214">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="b94d2-215">Nella scheda **Intervallo**, verifica che siano configurate le seguenti due righe:</span><span class="sxs-lookup"><span data-stu-id="b94d2-215">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="b94d2-216">Riga 1:</span><span class="sxs-lookup"><span data-stu-id="b94d2-216">Line 1:</span></span>

        - <span data-ttu-id="b94d2-217">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b94d2-217">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b94d2-218">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b94d2-218">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b94d2-219">**Campo:** *Magazzino*</span><span class="sxs-lookup"><span data-stu-id="b94d2-219">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="b94d2-220">**Criteri:** *51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-220">**Criteria:** *51*</span></span>

    - <span data-ttu-id="b94d2-221">Riga 2:</span><span class="sxs-lookup"><span data-stu-id="b94d2-221">Line 2:</span></span>

        - <span data-ttu-id="b94d2-222">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b94d2-222">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b94d2-223">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b94d2-223">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b94d2-224">**Campo:** *Ubicazione*</span><span class="sxs-lookup"><span data-stu-id="b94d2-224">**Field:** *Location*</span></span>
        - <span data-ttu-id="b94d2-225">**Criteri:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="b94d2-225">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="b94d2-226">Seleziona **OK** per chiudere l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="b94d2-226">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="b94d2-227">Creare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="b94d2-227">Create a mobile device menu item</span></span>

1. <span data-ttu-id="b94d2-228">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-228">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="b94d2-229">Nell'elenco delle voci di menu nel riquadro sinistro, seleziona **Stoccaggio dell'ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-229">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="b94d2-230">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-230">Select **Edit**.</span></span>
1. <span data-ttu-id="b94d2-231">Nella Scheda dettaglio **Classi di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b94d2-231">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b94d2-232">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b94d2-233">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b94d2-233">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b94d2-234">**Tipo di ordine di lavoro:** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="b94d2-234">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="b94d2-235">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-235">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="b94d2-236">Scenario</span><span class="sxs-lookup"><span data-stu-id="b94d2-236">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="b94d2-237">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="b94d2-237">Create a purchase order</span></span>

<span data-ttu-id="b94d2-238">Segui questi passaggi per creare un ordine fornitore come fonte di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="b94d2-238">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="b94d2-239">Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-239">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="b94d2-240">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-240">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b94d2-241">Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-241">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b94d2-242">**Conto fornitore:** *104*</span><span class="sxs-lookup"><span data-stu-id="b94d2-242">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="b94d2-243">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-243">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b94d2-244">Seleziona **OK** e prendi nota del numero dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b94d2-244">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="b94d2-245">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-245">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="b94d2-246">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-246">On this line, set the following values:</span></span>

    - <span data-ttu-id="b94d2-247">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b94d2-247">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b94d2-248">**Quantità:** *5*</span><span class="sxs-lookup"><span data-stu-id="b94d2-248">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="b94d2-249">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="b94d2-249">Create a sales order</span></span>

<span data-ttu-id="b94d2-250">Segui questi passaggi per creare un ordine cliente come origine della domanda.</span><span class="sxs-lookup"><span data-stu-id="b94d2-250">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="b94d2-251">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-251">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b94d2-252">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-252">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b94d2-253">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-253">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b94d2-254">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="b94d2-254">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="b94d2-255">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="b94d2-255">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b94d2-256">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-256">Select **OK**.</span></span>
1. <span data-ttu-id="b94d2-257">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-257">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b94d2-258">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b94d2-258">On this line, set the following values:</span></span>

    - <span data-ttu-id="b94d2-259">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b94d2-259">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b94d2-260">**Quantità:** *3*</span><span class="sxs-lookup"><span data-stu-id="b94d2-260">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="b94d2-261">Creare cross-docking pianificato</span><span class="sxs-lookup"><span data-stu-id="b94d2-261">Create planned cross-docking</span></span>

<span data-ttu-id="b94d2-262">Segui questi passaggi per creare il cross-docking pianificato dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b94d2-262">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="b94d2-263">Nella pagina **Dettagli ordine cliente** per l'ordine cliente appena creato, nel riquadro azioni, nella scheda **Magazzino** del gruppo **Azioni**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-263">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="b94d2-264">L'operazione di rilascio in magazzino crea una riga di spedizione e di carico per la riga ordine client e tenta di allocare le scorte.</span><span class="sxs-lookup"><span data-stu-id="b94d2-264">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="b94d2-265">Viene visualizzato un messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="b94d2-265">You receive an informational message.</span></span> <span data-ttu-id="b94d2-266">Viene inoltre visualizzato il seguente messaggio di avviso: "Nessun lavoro creato per l'ondata XXXX.</span><span class="sxs-lookup"><span data-stu-id="b94d2-266">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="b94d2-267">Vedi il registro della cronologia di creazione del lavoro per i dettagli. "</span><span class="sxs-lookup"><span data-stu-id="b94d2-267">See the work creation history log for details."</span></span> <span data-ttu-id="b94d2-268">Questo comportamento è previsto perché non sono presenti scorte nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="b94d2-268">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="b94d2-269">Nella scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino**, seleziona **Dettagli spedizione**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-269">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="b94d2-270">La pagina **Dettagli spedizione** viene visualizzata e mostra la spedizione creata per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b94d2-270">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="b94d2-271">Nella Scheda dettaglio **Righe di carico**, il campo **Quantità cross-dockin pianificata** è impostato su *3*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-271">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="b94d2-272">Poiché non erano disponibili scorte nel magazzino, ma una fonte di approvvigionamento valida arriverà entro l'intervallo di tempo definito nel modello di cross-docking, la quantità cross-docking è stata creata.</span><span class="sxs-lookup"><span data-stu-id="b94d2-272">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="b94d2-273">Nella Scheda dettaglio **Righe di carico**, seleziona **Cross-docking pianificato** per visualizzare i dettagli del cross-docking creato.</span><span class="sxs-lookup"><span data-stu-id="b94d2-273">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="b94d2-274">Elaborare il cross-docking</span><span class="sxs-lookup"><span data-stu-id="b94d2-274">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="b94d2-275">Ricezione dell'ordine fornitore nell'app per dispositivi mobili di magazzino</span><span class="sxs-lookup"><span data-stu-id="b94d2-275">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="b94d2-276">Il sistema riceverà la quantità di 5 dall'ordine fornitore nell'ubicazione di ricevimento e creerà due parti del lavoro.</span><span class="sxs-lookup"><span data-stu-id="b94d2-276">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="b94d2-277">Il primo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Cross docking* ed è collegato all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b94d2-277">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="b94d2-278">Ha una quantità di 3 ed è diretto al luogo di spedizione finale in modo che possa essere spedito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b94d2-278">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="b94d2-279">Il secondo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Ordini fornitore* ed è collegato all'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="b94d2-279">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="b94d2-280">Ha la quantità rimanente di 2 che non era cross-docking ed è indirizzata allo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="b94d2-280">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="b94d2-281">Accedi al dispositivo mobile come un utente in magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-281">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="b94d2-282">Vai a **In entrata \> Entrata acquisto**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-282">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="b94d2-283">Nel campo **Numero ordine fornitore**, inserisci il numero dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="b94d2-283">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="b94d2-284">Nel campo **Qtà** immetti *5*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-284">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="b94d2-285">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-285">Select **OK**.</span></span>
1. <span data-ttu-id="b94d2-286">Nella pagina successiva, imposta il campo **Articolo** su *A0001*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-286">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="b94d2-287">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-287">Select **OK**.</span></span>
1. <span data-ttu-id="b94d2-288">Nella pagina successiva, conferma i valori **Numero ordine fornitore**, **Articolo** e **Quantità** selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-288">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="b94d2-289">Ricevi un messaggio di tipo Lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="b94d2-289">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b94d2-290">Seleziona **Annulla** per uscire.</span><span class="sxs-lookup"><span data-stu-id="b94d2-290">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="b94d2-291">Stoccaggio su cross-docking e in blocco</span><span class="sxs-lookup"><span data-stu-id="b94d2-291">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="b94d2-292">Attualmente, entrambi gli ID lavoro hanno la stessa targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b94d2-292">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="b94d2-293">Per completare i passaggi successivi, è necessario ottenere l'ID lavoro e l'ID targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b94d2-293">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="b94d2-294">È possibile ottenere queste informazioni dai dettagli di lavoro per la riga ordine fornitore e la riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b94d2-294">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="b94d2-295">In alternativa, puoi andare a **Gestione magazzino \> Lavoro \> Dettagli del lavoro** e filtrsre per il lavoro in cui il valore **Magazzino** è *51*.</span><span class="sxs-lookup"><span data-stu-id="b94d2-295">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="b94d2-296">Sul dispositivo mobile, vai a **In entrata \> Stoccaggio acquisto** e immetti la targa di destinazione dal lavoro.</span><span class="sxs-lookup"><span data-stu-id="b94d2-296">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="b94d2-297">Nel campo **ID**, immetti l'ID targa di destinazione dai dettagli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b94d2-297">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="b94d2-298">La pagina di preliveo di cross-docking mostra l'ubicazione di prelievo (*RECV*), la targa di destinazione (*targa*), l'articolo (*A0001*) e la quantità (*3*).</span><span class="sxs-lookup"><span data-stu-id="b94d2-298">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="b94d2-299">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-299">Select **OK**.</span></span>
1. <span data-ttu-id="b94d2-300">Nel campo **Targa di destinazione**, immetti una targa di destinazione per l'ID targa che deve essere inserito (cross-docking) nell'ubicazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="b94d2-300">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="b94d2-301">È possibile selezionare qualsiasi ID targa di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="b94d2-301">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="b94d2-302">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-302">Select **OK**.</span></span>
1. <span data-ttu-id="b94d2-303">Nella pagina successiva, nel campo **ID**, immetti l'ID targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b94d2-303">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="b94d2-304">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-304">Select **OK**.</span></span>
1. <span data-ttu-id="b94d2-305">Conferma il lavoro per selezionare la quantità rimanente di 2, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-305">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="b94d2-306">Nella pagina successiva, seleziona **Fatto** per terminare il processo di raccolta e iniziare il processo di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="b94d2-306">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="b94d2-307">L'app per dispositivi mobili mostra l'ubicazione e la targa in cui collocare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b94d2-307">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="b94d2-308">Conferma il comando **Inserisci** dello stoccaggio in blocco selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-308">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="b94d2-309">Nella pagina successiva, confermare il cross-docking **Inserisci** selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="b94d2-309">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="b94d2-310">Ricevi un messaggio di tipo Lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="b94d2-310">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b94d2-311">Seleziona **Annulla** per uscire.</span><span class="sxs-lookup"><span data-stu-id="b94d2-311">Select **Cancel** to exit.</span></span>

<span data-ttu-id="b94d2-312">La seguente illustrazione mostra come il lavoro cross-docking completato potrebbe apparire in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b94d2-312">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b94d2-313">![Lavoro di cross docking completato](media/PlannedCrossDockingWork.png "Lavoro di cross docking completato")</span><span class="sxs-lookup"><span data-stu-id="b94d2-313">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]