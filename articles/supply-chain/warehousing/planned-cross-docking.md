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
ms.openlocfilehash: 11e044e04e05c68af676bf97e6085e9975da5c1d
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911250"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="6dc9c-104">Cross-docking pianificato</span><span class="sxs-lookup"><span data-stu-id="6dc9c-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6dc9c-105">Questo argomento descrive il cross docking pianificato avanzato.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="6dc9c-106">Il cross-docking è un processo di magazzino in cui la quantità di scorte richiesta per un ordine viene indirizzata direttamente dalla ricevuta o dalla creazione alla banchina di uscita o alla zona di transito corretta.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="6dc9c-107">Tutte le scorte rimanenti dall'origine in entrata vengono indirizzate all'ubicazione di magazzino corretta attraverso il normale processo di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="6dc9c-108">Il cross-docking consente ai lavoratori di saltare lo stoccaggio in entrata e il prelievo in uscita delle scorte già contrassegnate per un ordine in uscita.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="6dc9c-109">Pertanto, il numero di volte in cui l'inventario viene toccato viene ridotto al minimo, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="6dc9c-110">Inoltre, poiché vi è una minore interazione con il sistema, i risparmi di tempo e spazio nello shop floor del magazzino aumentano.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="6dc9c-111">Prima di poter eseguire il cross-docking, devi configurare un nuovo modello di cross-docking, in cui sono specificati l'origine di approvvigionamento e altri set di requisiti per il cross-docking.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-111">Before you can run cross-docking, you must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="6dc9c-112">Quando viene creato l'ordine di uscita, la riga deve essere contrassegnata a fronte di un ordine di entrata che contiene lo stesso articolo.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span> <span data-ttu-id="6dc9c-113">Puoi selezionare il campo Codice direttiva nel modello di cross-docking, in modo simile al modo in cui si impostano gli ordini di rifornimento e fornitore.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-113">You can select the directive code field on the cross-docking template, similar to the way you set up replenishment and purchase orders.</span></span>

<span data-ttu-id="6dc9c-114">Al momento della ricezione dell'ordine in entrata, la configurazione del cross-docking identifica automaticamente la necessità di cross-docking e crea il lavoro di movimentazione per la quantità richiesta, in base all'impostazione della direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-114">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="6dc9c-115">Le transazioni di magazzino *non* sono esenti da registrazione quando viene annullato il lavoro di cross-docking, anche se l'impostazione per questa funzionalità è attivata nei parametri di gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-115">Inventory transactions are *not* unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="6dc9c-116">Attivare le funzionalità di cross docking pianificato</span><span class="sxs-lookup"><span data-stu-id="6dc9c-116">Turn on the planned cross docking features</span></span>

<span data-ttu-id="6dc9c-117">Se il sistema in uso non include già le funzionalità descritte in questo argomento, vedere [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attivare le seguenti funzionalità nel seguente ordine:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="6dc9c-118">*Cross-docking pianificato*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-118">*Planned cross docking*</span></span>
1. <span data-ttu-id="6dc9c-119">*Modelli di cross-docking con direttive di ubicazione*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-119">*Cross docking templates with location directives*</span></span>
    > [!NOTE]
    > <span data-ttu-id="6dc9c-120">Questa funzionalità abilita il campo **Codice direttiva** affinché sia specificato nel modello di cross-docking, in modo simile al modo in cui si impostano i modelli di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-120">This feature enables the **Directive code** field to be specified on the cross-docking template, similar to the way you set up replenishment templates.</span></span> <span data-ttu-id="6dc9c-121">L'abilitazione di questa funzionalità impedisce di aggiungere un codice direttiva nelle righe del modello di lavoro cross-docking per la riga *Stoccaggio* finale.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-121">Enabling this feature prevents you from adding a directive code on the cross-docking work template lines for the final *Put* line.</span></span> <span data-ttu-id="6dc9c-122">Ciò garantisce che la posizione di stoccaggio finale possa essere determinata durante la creazione del lavoro prima di considerare i modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-122">This ensures that the final put location can be determined during work creation before considering work templates.</span></span>

## <a name="setup"></a><span data-ttu-id="6dc9c-123">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="6dc9c-123">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="6dc9c-124">Rigenerare i metodi di registrazione del carico</span><span class="sxs-lookup"><span data-stu-id="6dc9c-124">Regenerate load posting methods</span></span>

<span data-ttu-id="6dc9c-125">Il cross-docking pianificato è implementato come metodo di registrazione del carico.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-125">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="6dc9c-126">Dopo aver attivato la funzionalità, è necessario rigenerare i metodi.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-126">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="6dc9c-127">Accedi a **Gestione magazzino** \> Impostazione \> Metodi di registrazione carico.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-127">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="6dc9c-128">Nel riquadro azioni, seleziona **Rigenera metodi**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-128">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="6dc9c-129">Quando la rigenerazione è completa, dovresti vedere un metodo che ha un valore **Nome del metodo** di *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-129">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="6dc9c-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-130">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="6dc9c-131">Creare un modello di cross-docking</span><span class="sxs-lookup"><span data-stu-id="6dc9c-131">Create a cross-docking template</span></span>

1. <span data-ttu-id="6dc9c-132">Vai a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di cross-docking**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-132">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="6dc9c-133">Nel riquadro azioni seleziona **Nuovo** per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-133">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="6dc9c-134">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-134">In the header, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-135">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-135">**Sequence:** *1*</span></span>

        <span data-ttu-id="6dc9c-136">Questo campo definisce l'ordine in cui vengono valutati i modelli.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-136">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="6dc9c-137">**ID modello di cross-docking:** *51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-137">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="6dc9c-138">**Descrizione:** *Magazzino 51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-138">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="6dc9c-139">**Criteri di rilascio della domanda:** *Prima del ricevimento della fornitura*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-139">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="6dc9c-140">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-140">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6dc9c-141">L'impostazione sulla Scheda dettaglio **Pianificazione** controlla il funzionamento del modello.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-141">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="6dc9c-142">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-142">Set the following values:</span></span>

    - <span data-ttu-id="6dc9c-143">**Fabbisogno della domanda:** *Nessuno*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-143">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="6dc9c-144">Questo campo definisce il fabbisogno di scorte della domanda.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-144">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="6dc9c-145">Se la domanda deve essere collegata all'offerta prima del rilascio, seleziona *Contrassegno*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-145">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="6dc9c-146">Se la domanda deve essere prenotata dall'ordine a fronte dell'offerta prima del rilascio, seleziona *Prenotazione ordine*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-146">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="6dc9c-147">**Tipo di individuazione:** *Ubicazioni di spedizione*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-147">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="6dc9c-148">Questo campo definisce se il lavoro di cross-docking deve utilizzare le ubicazioni di transito/carico dalla spedizione o se deve utilizzare le direttive di ubicazione per trovare le proprie ubicazioni di transizione/carico.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-148">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="6dc9c-149">**Modello di lavoro**: lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-149">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="6dc9c-150">Questo campo definisce il modello di lavoro che deve essere utilizzato quando viene creato il lavoro di cross-docking.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-150">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="6dc9c-151">**Riconvalida al ricevimento della fornitura:** *No*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-151">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="6dc9c-152">Questa opzione definisce se la fornitura deve essere riconvalidata al momento del ricevimento.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-152">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="6dc9c-153">Se questa opzione è impostata su *Sì*, vengono controllati sia l'intervallo di tempo massimo sia l'intervallo di giorni di scadenza.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-153">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="6dc9c-154">**Codice direttiva:** lascia vuoto questo campo</span><span class="sxs-lookup"><span data-stu-id="6dc9c-154">**Directive code:** Leave this field blank</span></span>

        <span data-ttu-id="6dc9c-155">Questa opzione è abilitata tramite la funzionalità *Modelli di cross docking con direttive di ubicazione*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-155">This option is enabled by the *Cross docking templates with location directives* feature.</span></span> <span data-ttu-id="6dc9c-156">Il sistema utilizza le direttive di ubicazione per determinare l'ubicazione migliore in cui spostare l'inventario cross-docking.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-156">The system uses location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="6dc9c-157">È possibile configurarla assegnando un codice direttiva a ciascun modello di cross-docking pertinente.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-157">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="6dc9c-158">Se il codice direttiva è impostato, il sistema cercherà direttive di ubicazione in base al codice direttiva quando viene generato il lavoro.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-158">If a directive code is set, the system will search location directives by directive code when work is generated.</span></span> <span data-ttu-id="6dc9c-159">In questo modo, puoi limitare le direttive di ubicazione utilizzate per un particolare modello di cross-docking.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-159">In this way, you can limit location directives that are used for a particular cross-docking template.</span></span>

    - <span data-ttu-id="6dc9c-160">**Convalida finestra temporale:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-160">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="6dc9c-161">Questa opzione definisce se la finestra temporale massima deve essere valutata quando viene selezionata una fonte di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-161">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="6dc9c-162">Se questa opzione è impostata su *Sì*, diventano disponibili i campi correlati alle finestre di tempo massimo e minimo.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-162">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="6dc9c-163">**Intervallo di tempo massimo:** *5*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-163">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="6dc9c-164">Il campo definisce il periodo massimo consentito tra l'arrivo della fornitura e la partenza della domanda.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-164">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="6dc9c-165">**Unità intervallo di tempo massimo:** *Giorni*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-165">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="6dc9c-166">**Intervallo di tempo minimo:** *0*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-166">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="6dc9c-167">Il campo definisce il periodo minimo consentito tra l'arrivo della fornitura e la partenza della domanda.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-167">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="6dc9c-168">**Unità intervallo di tempo minimo:** *Giorni*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-168">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="6dc9c-169">**Intervallo giorni di scadenza:** *0*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-169">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="6dc9c-170">*Criteri FEFO (first out first first out):* questo campo definisce il numero massimo di giorni tra la data di scadenza del lotto in scadenza al momento che è attualmente nel magazzino e il lotto in ricezione.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-170">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="6dc9c-171">Nella Scheda dettaglio **Fonti di approvvigionamento**, si specificano i tipi di fornitura validi per questo modello.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-171">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="6dc9c-172">Seleziona **Nuovo**, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-172">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="6dc9c-173">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-173">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6dc9c-174">**Fonte di approvvigionamento:** *Ordine fornitore*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-174">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="6dc9c-175">Creare una classe di lavoro</span><span class="sxs-lookup"><span data-stu-id="6dc9c-175">Create a work class</span></span>

1. <span data-ttu-id="6dc9c-176">Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-176">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="6dc9c-177">Nel riquadro azioni seleziona **Nuova** per creare una nuova classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-177">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="6dc9c-178">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-178">Set the following values:</span></span>

    - <span data-ttu-id="6dc9c-179">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-179">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="6dc9c-180">**Descrizione:** *Cross-docking*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-180">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="6dc9c-181">**Tipo di ordine di lavoro:** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-181">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="6dc9c-182">Creare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="6dc9c-182">Create a work template</span></span>

1. <span data-ttu-id="6dc9c-183">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-183">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="6dc9c-184">Imposta il campo **Tipo ordine di lavoro** su *Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-184">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="6dc9c-185">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla scheda **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-185">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="6dc9c-186">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-187">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-187">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6dc9c-188">**Modello di lavoro:** *Cross-docking 51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-188">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="6dc9c-189">**Descrizione modello di lavoro:** *Cross-docking 51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-189">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="6dc9c-190">Seleziona **Salva** per rendere la Scheda dettaglio **Dettagli modello di lavoro** disponibile.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-190">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="6dc9c-191">Nella Scheda dettaglio **Dettagli modello di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-191">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6dc9c-192">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-192">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-193">**Tipo di lavoro:** *Prelevare*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-193">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="6dc9c-194">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-194">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="6dc9c-195">Seleziona **Nuova** per aggiungere un'altra riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-195">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="6dc9c-196">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-196">**Work type:** *Put*</span></span>
    - <span data-ttu-id="6dc9c-197">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-197">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="6dc9c-198">Seleziona **Salva** e verifica che la casella di controllo **Valido** sia selezionata per il modello *51 Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-198">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="6dc9c-199">Gli ID della classe di lavoro per i tipi di lavoro *Preleva* e *Inserisci* devono essere gli stessi.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-199">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="6dc9c-200">Creare direttive di ubicazione</span><span class="sxs-lookup"><span data-stu-id="6dc9c-200">Create location directives</span></span>

1. <span data-ttu-id="6dc9c-201">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-201">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6dc9c-202">Nel riquadro sinistro, imposta il campo **Tipo di ordine di lavoro** su *Cross-docking*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-202">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="6dc9c-203">Nel riquadro azioni, seleziona **Nuovo**, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-203">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="6dc9c-204">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-204">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6dc9c-205">**Nome:** *51 inserisci cross-docking*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-205">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="6dc9c-206">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-206">**Work type:** *Put*</span></span>
    - <span data-ttu-id="6dc9c-207">**Sito:** *5*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-207">**Site:** *5*</span></span>
    - <span data-ttu-id="6dc9c-208">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-208">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6dc9c-209">Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-209">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="6dc9c-210">Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-210">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6dc9c-211">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-211">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-212">**Da quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-212">**From quantity:** *1*</span></span>
    - <span data-ttu-id="6dc9c-213">**A quantità:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-213">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="6dc9c-214">Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-214">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="6dc9c-215">Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-215">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6dc9c-216">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-216">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-217">**Nome:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-217">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="6dc9c-218">**Utilizzo ubicazioni fisse:** *Ubicazioni fisse e non fisse*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-218">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="6dc9c-219">Seleziona **Salva** per rendere il pulsante **Modifica query** nella barra degli strumenti **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-219">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="6dc9c-220">Seleziona **Modifica query** per aprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-220">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="6dc9c-221">Nella scheda **Intervallo**, verifica che siano configurate le seguenti due righe:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-221">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="6dc9c-222">Riga 1:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-222">Line 1:</span></span>

        - <span data-ttu-id="6dc9c-223">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-223">**Table:** *Locations*</span></span>
        - <span data-ttu-id="6dc9c-224">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-224">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="6dc9c-225">**Campo:** *Magazzino*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-225">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="6dc9c-226">**Criteri:** *51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-226">**Criteria:** *51*</span></span>

    - <span data-ttu-id="6dc9c-227">Riga 2:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-227">Line 2:</span></span>

        - <span data-ttu-id="6dc9c-228">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-228">**Table:** *Locations*</span></span>
        - <span data-ttu-id="6dc9c-229">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-229">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="6dc9c-230">**Campo:** *Ubicazione*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-230">**Field:** *Location*</span></span>
        - <span data-ttu-id="6dc9c-231">**Criteri:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-231">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="6dc9c-232">Seleziona **OK** per chiudere l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-232">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="6dc9c-233">Creare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="6dc9c-233">Create a mobile device menu item</span></span>

1. <span data-ttu-id="6dc9c-234">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-234">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6dc9c-235">Nell'elenco delle voci di menu nel riquadro sinistro, seleziona **Stoccaggio dell'ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-235">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="6dc9c-236">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-236">Select **Edit**.</span></span>
1. <span data-ttu-id="6dc9c-237">Nella Scheda dettaglio **Classi di lavoro**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-237">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6dc9c-238">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-238">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-239">**ID classe lavoro:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-239">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="6dc9c-240">**Tipo di ordine di lavoro:** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-240">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="6dc9c-241">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-241">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="6dc9c-242">Scenario</span><span class="sxs-lookup"><span data-stu-id="6dc9c-242">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="6dc9c-243">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="6dc9c-243">Create a purchase order</span></span>

<span data-ttu-id="6dc9c-244">Segui questi passaggi per creare un ordine fornitore come fonte di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-244">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="6dc9c-245">Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-245">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="6dc9c-246">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-246">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6dc9c-247">Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-247">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-248">**Conto fornitore:** *104*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-248">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="6dc9c-249">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6dc9c-250">Seleziona **OK** e prendi nota del numero dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-250">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="6dc9c-251">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-251">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="6dc9c-252">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-252">On this line, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-253">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-253">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="6dc9c-254">**Quantità:** *5*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-254">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="6dc9c-255">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="6dc9c-255">Create a sales order</span></span>

<span data-ttu-id="6dc9c-256">Segui questi passaggi per creare un ordine cliente come origine della domanda.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-256">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="6dc9c-257">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-257">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6dc9c-258">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-258">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6dc9c-259">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-259">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-260">**Conto cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-260">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="6dc9c-261">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-261">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6dc9c-262">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-262">Select **OK**.</span></span>
1. <span data-ttu-id="6dc9c-263">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-263">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="6dc9c-264">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6dc9c-264">On this line, set the following values:</span></span>

    - <span data-ttu-id="6dc9c-265">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-265">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="6dc9c-266">**Quantità:** *3*</span><span class="sxs-lookup"><span data-stu-id="6dc9c-266">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="6dc9c-267">Creare cross-docking pianificato</span><span class="sxs-lookup"><span data-stu-id="6dc9c-267">Create planned cross-docking</span></span>

<span data-ttu-id="6dc9c-268">Segui questi passaggi per creare il cross-docking pianificato dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-268">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="6dc9c-269">Nella pagina **Dettagli ordine cliente** per l'ordine cliente appena creato, nel riquadro azioni, nella scheda **Magazzino** del gruppo **Azioni**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-269">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6dc9c-270">L'operazione di rilascio in magazzino crea una riga di spedizione e di carico per la riga ordine client e tenta di allocare le scorte.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-270">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="6dc9c-271">Viene visualizzato un messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-271">You receive an informational message.</span></span> <span data-ttu-id="6dc9c-272">Viene inoltre visualizzato il seguente messaggio di avviso: "Nessun lavoro creato per l'ondata XXXX.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-272">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="6dc9c-273">Vedi il registro della cronologia di creazione del lavoro per i dettagli. "</span><span class="sxs-lookup"><span data-stu-id="6dc9c-273">See the work creation history log for details."</span></span> <span data-ttu-id="6dc9c-274">Questo comportamento è previsto perché non sono presenti scorte nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-274">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="6dc9c-275">Nella scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino**, seleziona **Dettagli spedizione**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-275">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="6dc9c-276">La pagina **Dettagli spedizione** viene visualizzata e mostra la spedizione creata per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-276">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="6dc9c-277">Nella Scheda dettaglio **Righe di carico**, il campo **Quantità cross-dockin pianificata** è impostato su *3*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-277">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="6dc9c-278">Poiché non erano disponibili scorte nel magazzino, ma una fonte di approvvigionamento valida arriverà entro l'intervallo di tempo definito nel modello di cross-docking, la quantità cross-docking è stata creata.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-278">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="6dc9c-279">Nella Scheda dettaglio **Righe di carico**, seleziona **Cross-docking pianificato** per visualizzare i dettagli del cross-docking creato.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-279">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="6dc9c-280">Elaborare il cross-docking</span><span class="sxs-lookup"><span data-stu-id="6dc9c-280">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="6dc9c-281">Ricezione dell'ordine fornitore nell'app per dispositivi mobili di magazzino</span><span class="sxs-lookup"><span data-stu-id="6dc9c-281">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="6dc9c-282">Il sistema riceverà la quantità di 5 dall'ordine fornitore nell'ubicazione di ricevimento e creerà due parti del lavoro.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-282">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="6dc9c-283">Il primo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Cross docking* ed è collegato all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-283">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="6dc9c-284">Ha una quantità di 3 ed è diretto al luogo di spedizione finale in modo che possa essere spedito immediatamente.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-284">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="6dc9c-285">Il secondo ID lavoro creato ha un valore **Tipo di ordine di lavoro** di *Ordini fornitore* ed è collegato all'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-285">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="6dc9c-286">Ha la quantità rimanente di 2 che non era cross-docking ed è indirizzata allo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-286">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="6dc9c-287">Accedi al dispositivo mobile come un utente in magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-287">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="6dc9c-288">Vai a **In entrata \> Entrata acquisto**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-288">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="6dc9c-289">Nel campo **Numero ordine fornitore**, inserisci il numero dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-289">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="6dc9c-290">Nel campo **Qtà** immetti *5*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-290">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="6dc9c-291">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-291">Select **OK**.</span></span>
1. <span data-ttu-id="6dc9c-292">Nella pagina successiva, imposta il campo **Articolo** su *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-292">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="6dc9c-293">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-293">Select **OK**.</span></span>
1. <span data-ttu-id="6dc9c-294">Nella pagina successiva, conferma i valori **Numero ordine fornitore**, **Articolo** e **Quantità** selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-294">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="6dc9c-295">Ricevi un messaggio di tipo Lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-295">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="6dc9c-296">Seleziona **Annulla** per uscire.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-296">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="6dc9c-297">Stoccaggio su cross-docking e in blocco</span><span class="sxs-lookup"><span data-stu-id="6dc9c-297">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="6dc9c-298">Attualmente, entrambi gli ID lavoro hanno la stessa targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-298">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="6dc9c-299">Per completare i passaggi successivi, è necessario ottenere l'ID lavoro e l'ID targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-299">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="6dc9c-300">È possibile ottenere queste informazioni dai dettagli di lavoro per la riga ordine fornitore e la riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-300">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="6dc9c-301">In alternativa, puoi andare a **Gestione magazzino \> Lavoro \> Dettagli del lavoro** e filtrsre per il lavoro in cui il valore **Magazzino** è *51*.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-301">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="6dc9c-302">Sul dispositivo mobile, vai a **In entrata \> Stoccaggio acquisto** e immetti la targa di destinazione dal lavoro.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-302">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="6dc9c-303">Nel campo **ID**, immetti l'ID targa di destinazione dai dettagli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-303">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="6dc9c-304">La pagina di preliveo di cross-docking mostra l'ubicazione di prelievo (*RECV*), la targa di destinazione (*targa*), l'articolo (*A0001*) e la quantità (*3*).</span><span class="sxs-lookup"><span data-stu-id="6dc9c-304">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="6dc9c-305">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-305">Select **OK**.</span></span>
1. <span data-ttu-id="6dc9c-306">Nel campo **Targa di destinazione**, immetti una targa di destinazione per l'ID targa che deve essere inserito (cross-docking) nell'ubicazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-306">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="6dc9c-307">È possibile selezionare qualsiasi ID targa di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-307">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="6dc9c-308">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-308">Select **OK**.</span></span>
1. <span data-ttu-id="6dc9c-309">Nella pagina successiva, nel campo **ID**, immetti l'ID targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-309">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="6dc9c-310">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-310">Select **OK**.</span></span>
1. <span data-ttu-id="6dc9c-311">Conferma il lavoro per selezionare la quantità rimanente di 2, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-311">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="6dc9c-312">Nella pagina successiva, seleziona **Fatto** per terminare il processo di raccolta e iniziare il processo di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-312">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="6dc9c-313">L'app per dispositivi mobili mostra l'ubicazione e la targa in cui collocare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-313">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="6dc9c-314">Conferma il comando **Inserisci** dello stoccaggio in blocco selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-314">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="6dc9c-315">Nella pagina successiva, confermare il cross-docking **Inserisci** selezionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-315">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="6dc9c-316">Ricevi un messaggio di tipo Lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-316">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="6dc9c-317">Seleziona **Annulla** per uscire.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-317">Select **Cancel** to exit.</span></span>

<span data-ttu-id="6dc9c-318">La seguente illustrazione mostra come il lavoro cross-docking completato potrebbe apparire in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6dc9c-318">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="6dc9c-319">![Lavoro di cross docking completato](media/PlannedCrossDockingWork.png "Lavoro di cross docking completato")</span><span class="sxs-lookup"><span data-stu-id="6dc9c-319">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]