---
title: Posizione cluster piena
description: In questo argomento vengono fornite informazioni sulla funzionalità Posizione cluster piena. Questa funzione offre un'alternativa all'applicazione più rigida delle regole di interruzione del lavoro quando viene utilizzato il prelievo del cluster perché consente un margine di errore più ampio nei vincoli volumetrici dei contenitori o dei totali.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8d030afb568b158e6caf48b0044d595d6ec024f6
ms.sourcegitcommit: 06f64550b2043582de4018bdd3924fcc1fd5d310
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802216"
---
# <a name="cluster-position-full"></a><span data-ttu-id="4a596-104">Posizione cluster piena</span><span class="sxs-lookup"><span data-stu-id="4a596-104">Cluster position full</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4a596-105">La funzione *Posizione cluster piena* offre un'alternativa all'applicazione più rigida delle regole di interruzione del lavoro quando viene utilizzato il prelievo del cluster perché consente un margine di errore più ampio nei vincoli volumetrici dei contenitori o dei totali.</span><span class="sxs-lookup"><span data-stu-id="4a596-105">The *Cluster position full* feature offers an alternative to more rigid enforcement of work break rules when cluster picking is used, because it enables a larger margin of error in the volumetric constraints of containers or totes.</span></span> <span data-ttu-id="4a596-106">In uno scenario comune, non tutti gli articoli di un ordine di lavoro rientrano un contenitore selezionato.</span><span class="sxs-lookup"><span data-stu-id="4a596-106">In a common scenario, not all items on a work order fit into a selected container.</span></span> <span data-ttu-id="4a596-107">I lavoratori del magazzino che effettuano il prelievo del cluster hanno poche opzioni in questo scenario: devono passare a una dimensione del contenitore più grande o collaborare con il proprio supervisore per trovare una soluzione diversa.</span><span class="sxs-lookup"><span data-stu-id="4a596-107">Warehouse workers who are cluster picking have few options in this scenario: they must either change to a larger container size or work with their supervisor to come up with a different solution.</span></span>

<span data-ttu-id="4a596-108">Questa funzione introduce la possibilità di eseguire il pulsante **Completo** su una delle unità di lavoro in un cluster.</span><span class="sxs-lookup"><span data-stu-id="4a596-108">This feature introduces the ability to run the **Full** button on one of the work units in a cluster.</span></span> <span data-ttu-id="4a596-109">Nelle versioni precedenti, questa opzione era disponibile solo per il prelievo regolare degli ordini, non per il prelievo in gruppo.</span><span class="sxs-lookup"><span data-stu-id="4a596-109">In older versions, this option was available only for regular order picking, not for cluster picking.</span></span> <span data-ttu-id="4a596-110">Tuttavia, questa funzionalità è diversa dal pulsante **Completo** standard in quanto annulla il lavoro rimanente.</span><span class="sxs-lookup"><span data-stu-id="4a596-110">However, this feature differs from the standard **Full** button in that it cancels the remaining work.</span></span> <span data-ttu-id="4a596-111">Non suggerisce all'utente di aggiungere un altro contenitore allo stesso cluster e non crea automaticamente nuovo lavoro.</span><span class="sxs-lookup"><span data-stu-id="4a596-111">It doesn't suggest that the user add another bin to the same cluster, and it doesn't automatically create new work.</span></span>

## <a name="turn-on-the-cluster-position-full-feature"></a><span data-ttu-id="4a596-112">Attivare la funzionalità Posizione cluster piena</span><span class="sxs-lookup"><span data-stu-id="4a596-112">Turn on the Cluster position full feature</span></span>

<span data-ttu-id="4a596-113">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="4a596-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="4a596-114">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="4a596-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="4a596-115">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="4a596-115">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="4a596-116">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="4a596-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="4a596-117">**Nome funzionalità:** *Posizione cluster piena*</span><span class="sxs-lookup"><span data-stu-id="4a596-117">**Feature name:** *Cluster position full*</span></span>

## <a name="setup"></a><span data-ttu-id="4a596-118">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="4a596-118">Setup</span></span>

<span data-ttu-id="4a596-119">Questa sezione fornisce le linee guida e un esempio che mostra come configurare e utilizzare la funzionalità *Posizione cluster piena*.</span><span class="sxs-lookup"><span data-stu-id="4a596-119">This section provides guidelines, and an example that shows how to set up and use the *Cluster position full* feature.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="4a596-120">Rendi disponibili i dati di esempio</span><span class="sxs-lookup"><span data-stu-id="4a596-120">Make sample data available</span></span>

<span data-ttu-id="4a596-121">Per elaborare lo [scenario di esempio](#example-scenario) utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="4a596-121">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="4a596-122">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="4a596-122">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="4a596-123">È inoltre possibile utilizzare questo scenario di esempio come indicazioni per l'utilizzo di questa funzionalità in un sistema di produzione.</span><span class="sxs-lookup"><span data-stu-id="4a596-123">You can also use the example scenario as guidance for working with this feature on a production system.</span></span> <span data-ttu-id="4a596-124">Tuttavia, in tal caso, è necessario sostituire i valori per le impostazioni descritte qui.</span><span class="sxs-lookup"><span data-stu-id="4a596-124">However, in that case, you must substitute your own values for the settings that are described here.</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="4a596-125">Profili cluster</span><span class="sxs-lookup"><span data-stu-id="4a596-125">Cluster profiles</span></span>

<span data-ttu-id="4a596-126">È necessario specificare se gli ID cluster vengono generati automaticamente, quante posizioni vengono utilizzate, quando i cluster vengono interrotti e come viene sequenziato e verificato il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="4a596-126">You must specify whether cluster IDs are automatically generated, how many positions are used, when clusters are broken, and how the picking work is sequenced and verified.</span></span>

1. <span data-ttu-id="4a596-127">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Profili cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a596-127">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="4a596-128">Nel riquadro elenco, selezionare il record **Crea cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a596-128">In the list pane, select the **Create Cluster** record.</span></span>
1. <span data-ttu-id="4a596-129">Nella Scheda dettaglio **Generale**, verificare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4a596-129">On the **General** FastTab, verify the following values:</span></span>

    - <span data-ttu-id="4a596-130">**Genera ID cluster:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="4a596-130">**Generate cluster ID:** *Yes*</span></span>
    - <span data-ttu-id="4a596-131">**Attiva posizioni:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="4a596-131">**Activate positions:** *Yes*</span></span>
    - <span data-ttu-id="4a596-132">**Numero di posizioni:** *2*</span><span class="sxs-lookup"><span data-stu-id="4a596-132">**Number of positions:** *2*</span></span>
    - <span data-ttu-id="4a596-133">**Nome posizione:** *Numerico*</span><span class="sxs-lookup"><span data-stu-id="4a596-133">**Position name:** *Numeric*</span></span>
    - <span data-ttu-id="4a596-134">**Suddividi cluster a:** *Inserisci*</span><span class="sxs-lookup"><span data-stu-id="4a596-134">**Break cluster at:** *Put*</span></span>
    - <span data-ttu-id="4a596-135">**Ordina tipo di verifica:** *Scansione posizione*</span><span class="sxs-lookup"><span data-stu-id="4a596-135">**Sort verification type:** *Position scan*</span></span>

1. <span data-ttu-id="4a596-136">Nella scheda dettaglio **Ordinamento cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a596-136">In the **Cluster sorting** FastTab.</span></span> <span data-ttu-id="4a596-137">La griglia deve essere vuota (ovvero, non deve contenere righe).</span><span class="sxs-lookup"><span data-stu-id="4a596-137">The grid should be blank (that is, it should contain no lines).</span></span>

### <a name="work-templates"></a><span data-ttu-id="4a596-138">Modelli di lavoro</span><span class="sxs-lookup"><span data-stu-id="4a596-138">Work templates</span></span>

<span data-ttu-id="4a596-139">È necessario definire la modalità di prelievo del lavoro per il prelievo del cluster.</span><span class="sxs-lookup"><span data-stu-id="4a596-139">You must define how the picking work for cluster picking is created.</span></span>

1. <span data-ttu-id="4a596-140">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="4a596-140">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="4a596-141">Nella parte superiore della pagina, impostare il campo **Tipo di ordine di lavoro** su *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="4a596-141">At the top of the page, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="4a596-142">Assicurarsi che siano elencati i seguenti modelli di lavoro dai dati demo.</span><span class="sxs-lookup"><span data-stu-id="4a596-142">Make sure that the following work templates from the demo data are listed.</span></span> <span data-ttu-id="4a596-143">Se non sono disponibili, non è possibile completare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="4a596-143">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="4a596-144">Fase ordine cliente 61</span><span class="sxs-lookup"><span data-stu-id="4a596-144">61 SO Stage</span></span>
    - <span data-ttu-id="4a596-145">Prelievo cluster ordine cliente 61</span><span class="sxs-lookup"><span data-stu-id="4a596-145">61 SO Cluster pick</span></span>

### <a name="location-directives"></a><span data-ttu-id="4a596-146">Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="4a596-146">Location directives</span></span>

<span data-ttu-id="4a596-147">È necessario specificare da dove vengono prelevati gli articoli e dove vengono inseriti.</span><span class="sxs-lookup"><span data-stu-id="4a596-147">You must specify where items are picked from and where they are put.</span></span>

1. <span data-ttu-id="4a596-148">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="4a596-148">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="4a596-149">Nell'intestazione elenco, impostare il campo **Tipo ordine di lavoro** su *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="4a596-149">In the list header, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="4a596-150">Assicurarsi che siano elencate le seguenti direttive ordine cliente dai dati demo.</span><span class="sxs-lookup"><span data-stu-id="4a596-150">Make sure that the following sales order directives from the demo data are listed.</span></span> <span data-ttu-id="4a596-151">Se non sono disponibili, non è possibile completare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="4a596-151">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="4a596-152">Prelievo cluster 61</span><span class="sxs-lookup"><span data-stu-id="4a596-152">61 Cluster pick</span></span>
    - <span data-ttu-id="4a596-153">Prelievo ordine ordine cliente 61</span><span class="sxs-lookup"><span data-stu-id="4a596-153">61 SO Pick order</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="4a596-154">Voci di menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="4a596-154">Mobile device menu items</span></span>

<span data-ttu-id="4a596-155">È necessario configurare una voce di menu del dispositivo mobile per utilizzare il lavoro esistente che è diretto dal prelievo del cluster.</span><span class="sxs-lookup"><span data-stu-id="4a596-155">You must configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="4a596-156">Nella voce di menu del dispositivo mobile per il prelievo cluster, il parametro **Consenti suddivisione del lavoro** deve essere attivato e la classe di lavoro *Prelievo ordine cliente* deve essere aggiunta.</span><span class="sxs-lookup"><span data-stu-id="4a596-156">In the mobile device menu item for cluster picking, the **Allow splitting of work** parameter must be turned on, and the *SO Pick* work class must be added.</span></span>

1. <span data-ttu-id="4a596-157">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="4a596-157">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="4a596-158">Nel riquadro elenco, selezionare il record **Creazione prelievo del cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a596-158">In the list pane, select the **Cluster Pick Create** record.</span></span>
1. <span data-ttu-id="4a596-159">Nel riquadro azioni, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4a596-159">Select **Edit** in the Action pane.</span></span>
1. <span data-ttu-id="4a596-160">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4a596-160">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="4a596-161">**Diretto da:** *Prelievo del cluster*</span><span class="sxs-lookup"><span data-stu-id="4a596-161">**Directed by:** *Cluster picking*</span></span>
    - <span data-ttu-id="4a596-162">**Genera targa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="4a596-162">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="4a596-163">**Consenti suddivisione del lavoro:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="4a596-163">**Allow splitting of work:** *Yes*</span></span>
    - <span data-ttu-id="4a596-164">**ID profilo cluster:** *Crea cluster*</span><span class="sxs-lookup"><span data-stu-id="4a596-164">**Cluster profile ID:** *Create Cluster*</span></span>

    <span data-ttu-id="4a596-165">Accetta i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="4a596-165">Accept the default values for all other fields.</span></span>

1. <span data-ttu-id="4a596-166">Nella scheda dettaglio **Classi di lavoro** aggiungere le seguenti due righe, come richiesto:</span><span class="sxs-lookup"><span data-stu-id="4a596-166">On the **Work classes** FastTab, add the following two lines, as required:</span></span>

    - <span data-ttu-id="4a596-167">Riga 1 (normalmente presente nei dati demo):</span><span class="sxs-lookup"><span data-stu-id="4a596-167">Line 1 (usually present in demo data):</span></span>

        - <span data-ttu-id="4a596-168">**ID classe lavoro:** *Vendita*</span><span class="sxs-lookup"><span data-stu-id="4a596-168">**Work class ID:** *Sales*</span></span> 
        - <span data-ttu-id="4a596-169">**Tipo di ordine di lavoro:** *Ordini cliente*</span><span class="sxs-lookup"><span data-stu-id="4a596-169">**Work order type:** *Sales orders*</span></span>

    - <span data-ttu-id="4a596-170">Riga 2 (probabilmente non presente nei dati demo):</span><span class="sxs-lookup"><span data-stu-id="4a596-170">Line 2 (probably not present in demo data):</span></span>

        - <span data-ttu-id="4a596-171">**ID classe lavoro:** *Prelievo ordine cliente*</span><span class="sxs-lookup"><span data-stu-id="4a596-171">**Work class ID:** *SO Pick*</span></span>
        - <span data-ttu-id="4a596-172">**Tipo di ordine di lavoro:** *Ordini cliente*</span><span class="sxs-lookup"><span data-stu-id="4a596-172">**Work order type:** *Sales orders*</span></span>

1. <span data-ttu-id="4a596-173">Andare a **Impostazione conferma lavoro** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="4a596-173">Go to **Work confirmation setup** in the Action pane.</span></span>
1. <span data-ttu-id="4a596-174">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4a596-174">Select **Edit**.</span></span>
1. <span data-ttu-id="4a596-175">Immettere i seguenti valori nella riga della griglia.</span><span class="sxs-lookup"><span data-stu-id="4a596-175">Enter the following values on the line in grid.</span></span>
    - <span data-ttu-id="4a596-176">**Tipo di lavoro** - *Prelevare*</span><span class="sxs-lookup"><span data-stu-id="4a596-176">**Work type** - *Pick*</span></span>
    - <span data-ttu-id="4a596-177">**Conferma del prodotto** - *Selezionare la casella di controllo*</span><span class="sxs-lookup"><span data-stu-id="4a596-177">**Product confirmation** - *Select the check box*</span></span>

1. <span data-ttu-id="4a596-178">Selezionare **Salva** nel riquadro azioni e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4a596-178">Select **Save** in the Action pane and close the page.</span></span>

## <a name="create-picking-work"></a><span data-ttu-id="4a596-179">Creare il lavoro di prelievo</span><span class="sxs-lookup"><span data-stu-id="4a596-179">Create picking work</span></span>

<span data-ttu-id="4a596-180">Prima di poter iniziare il prelievo dei cluster, è necessario creare del lavoro in uscita.</span><span class="sxs-lookup"><span data-stu-id="4a596-180">Before you can start cluster picking, you must create some outbound work.</span></span> <span data-ttu-id="4a596-181">Il profilo cluster creato in precedenza specifica due posizioni cluster.</span><span class="sxs-lookup"><span data-stu-id="4a596-181">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="4a596-182">Pertanto, è necessario creare almeno due ID lavoro per il prelievo degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="4a596-182">Therefore, at least two work IDs must be created for sales order picking.</span></span> <span data-ttu-id="4a596-183">Per questo scenario, le transazioni avverranno nel magazzino *61* e useranno gli articoli *L0101* e *T0100*.</span><span class="sxs-lookup"><span data-stu-id="4a596-183">For this scenario, transactions will occur in warehouse *61*, and they will use items *L0101* and *T0100*.</span></span> <span data-ttu-id="4a596-184">I dati della demo dovrebbero avere scorte sufficienti di questi articoli.</span><span class="sxs-lookup"><span data-stu-id="4a596-184">The demo data should have enough on-hand inventory of these items.</span></span> <span data-ttu-id="4a596-185">Assicurarsi di disporre di scorte sufficienti per completare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="4a596-185">Make sure that you have enough inventory to complete the transactions.</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="4a596-186">Creare l'ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="4a596-186">Create sales order 1</span></span>

1. <span data-ttu-id="4a596-187">Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="4a596-187">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="4a596-188">Selezionare **Nuovo** per creare l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="4a596-188">Select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="4a596-189">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4a596-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="4a596-190">**Conto cliente:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="4a596-190">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="4a596-191">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="4a596-191">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="4a596-192">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a596-192">Select **OK**.</span></span>
1. <span data-ttu-id="4a596-193">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="4a596-193">The new sales order is opened.</span></span> <span data-ttu-id="4a596-194">Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una riga che abbia le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4a596-194">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="4a596-195">**Numero articolo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="4a596-195">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="4a596-196">**Quantità:** *5*</span><span class="sxs-lookup"><span data-stu-id="4a596-196">**Quantity:** *5*</span></span>

1. <span data-ttu-id="4a596-197">Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.</span><span class="sxs-lookup"><span data-stu-id="4a596-197">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="4a596-198">Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una seconda riga che abbia le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4a596-198">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="4a596-199">**Numero articolo:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="4a596-199">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="4a596-200">**Quantità:** *20*</span><span class="sxs-lookup"><span data-stu-id="4a596-200">**Quantity:** *20*</span></span>

1. <span data-ttu-id="4a596-201">Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.</span><span class="sxs-lookup"><span data-stu-id="4a596-201">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="4a596-202">Per ogni riga che appena aggiunta, seguire questi passaggi per prenotare le scorte:</span><span class="sxs-lookup"><span data-stu-id="4a596-202">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="4a596-203">Selezionare la riga da prenotare.</span><span class="sxs-lookup"><span data-stu-id="4a596-203">Select the line to reserve.</span></span>
    2. <span data-ttu-id="4a596-204">Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="4a596-204">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="4a596-205">Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.</span><span class="sxs-lookup"><span data-stu-id="4a596-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="4a596-206">Chiudi la pagina **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="4a596-206">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="4a596-207">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="4a596-207">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="4a596-208">Quando il rilascio è completato, verranno ricevuti messaggi informativi che mostrano l'ID ondata e l'ID carico creati.</span><span class="sxs-lookup"><span data-stu-id="4a596-208">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="4a596-209">Creare l'ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="4a596-209">Create sales order 2</span></span>

1. <span data-ttu-id="4a596-210">Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="4a596-210">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="4a596-211">Selezionare **Nuovo** per creare l'ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="4a596-211">Select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="4a596-212">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4a596-212">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="4a596-213">**Conto cliente:** *US-011*</span><span class="sxs-lookup"><span data-stu-id="4a596-213">**Customer account:** *US-011*</span></span>
    - <span data-ttu-id="4a596-214">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="4a596-214">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="4a596-215">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a596-215">Select **OK**.</span></span>
1. <span data-ttu-id="4a596-216">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="4a596-216">The new sales order is opened.</span></span> <span data-ttu-id="4a596-217">Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una riga che abbia le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4a596-217">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="4a596-218">**Numero articolo:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="4a596-218">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="4a596-219">**Quantità:** *20*</span><span class="sxs-lookup"><span data-stu-id="4a596-219">**Quantity:** *20*</span></span>

1. <span data-ttu-id="4a596-220">Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.</span><span class="sxs-lookup"><span data-stu-id="4a596-220">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="4a596-221">Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una seconda riga che abbia le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4a596-221">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="4a596-222">**Numero articolo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="4a596-222">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="4a596-223">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="4a596-223">**Quantity:** *2*</span></span>

1. <span data-ttu-id="4a596-224">Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.</span><span class="sxs-lookup"><span data-stu-id="4a596-224">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="4a596-225">Per ogni riga che appena aggiunta, seguire questi passaggi per prenotare le scorte:</span><span class="sxs-lookup"><span data-stu-id="4a596-225">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="4a596-226">Selezionare la riga da prenotare.</span><span class="sxs-lookup"><span data-stu-id="4a596-226">Select the line to reserve.</span></span>
    2. <span data-ttu-id="4a596-227">Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="4a596-227">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="4a596-228">Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.</span><span class="sxs-lookup"><span data-stu-id="4a596-228">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="4a596-229">Chiudi la pagina **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="4a596-229">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="4a596-230">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="4a596-230">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="4a596-231">Quando il rilascio è completato, verranno ricevuti messaggi informativi che mostrano l'ID ondata e l'ID carico creati.</span><span class="sxs-lookup"><span data-stu-id="4a596-231">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="get-work-ids-and-license-plate-numbers"></a><span data-ttu-id="4a596-232">Ottenere gli ID lavoro e i numeri di targa</span><span class="sxs-lookup"><span data-stu-id="4a596-232">Get work IDs and license plate numbers</span></span>

<span data-ttu-id="4a596-233">Dovrebbero essere stati creati due ID lavoro, ciascuno dei quali ha due righe di selezione.</span><span class="sxs-lookup"><span data-stu-id="4a596-233">Two work IDs should have been created, each of which has two pick lines.</span></span> <span data-ttu-id="4a596-234">Seguire questi passaggi per trovare gli ID lavoro e le assegnazioni delle targhe.</span><span class="sxs-lookup"><span data-stu-id="4a596-234">Follow these steps to find the work IDs and license plate assignments.</span></span>

1. <span data-ttu-id="4a596-235">Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="4a596-235">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="4a596-236">Nella griglia **Panoramica** cercare la colonna **Numero ordine** per i due ordini cliente appena creati.</span><span class="sxs-lookup"><span data-stu-id="4a596-236">In the **Overview** grid, search the **Order number** column for the two sales orders that you just created.</span></span> <span data-ttu-id="4a596-237">Prendere nota dell'ID lavoro corrispondente per ciascun ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="4a596-237">For each sales order, make a note of the corresponding work ID.</span></span>
1. <span data-ttu-id="4a596-238">Selezionare la riga per ogni ordine cliente per visualizzare le informazioni correlate nella griglia **Righe**.</span><span class="sxs-lookup"><span data-stu-id="4a596-238">Select the row for each sales order to show related information in the **Lines** grid.</span></span> <span data-ttu-id="4a596-239">Prendere nota della posizione da cui verrà prelevato ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="4a596-239">Make a note of the location that each item will be picked from.</span></span>
1. <span data-ttu-id="4a596-240">Passare a **Gestione articoli \> Richieste di informazioni e report \> Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="4a596-240">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="4a596-241">Nel riquadro azioni, scegliere **Dimensioni** per aprire la finestra di dialogo **Visualizzazione dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="4a596-241">On the Action Pane, select **Dimensions** to open the **Dimension display** dialog box.</span></span>
1. <span data-ttu-id="4a596-242">Assicurarsi che le caselle di controllo **Targa**, **Magazzino** e **Numero articolo** siano selezionate, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a596-242">Make sure that the **License plate**, **Warehouse**, and **Item number** check boxes are selected, and then select **OK**.</span></span>
1. <span data-ttu-id="4a596-243">Nel riquadro **Filtro** impostare i seguenti filtri:</span><span class="sxs-lookup"><span data-stu-id="4a596-243">In the **Filter** pane, set the following filters:</span></span>

    - <span data-ttu-id="4a596-244">**Numero articolo** - **è uno tra** - *L0101* e *T100*</span><span class="sxs-lookup"><span data-stu-id="4a596-244">**Item number** – **is one of** – *L0101* and *T100*</span></span>
    - <span data-ttu-id="4a596-245">**Magazzino** - **inizia con** - *61*</span><span class="sxs-lookup"><span data-stu-id="4a596-245">**Warehouse** – **begins with** – *61*</span></span>

1. <span data-ttu-id="4a596-246">Prendere nota dei valori **Targa** visualizzati.</span><span class="sxs-lookup"><span data-stu-id="4a596-246">Make a note of the **License plate** values that are shown.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="4a596-247">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="4a596-247">Example scenario</span></span>

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a><span data-ttu-id="4a596-248">Esecuzione del flusso del dispositivo mobile: impostazione della conferma del lavoro per il prodotto</span><span class="sxs-lookup"><span data-stu-id="4a596-248">Mobile device flow execution – Work confirmation setup for the product</span></span>

1. <span data-ttu-id="4a596-249">Accedere all'app di magazzino come utente nel magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="4a596-249">Sign in to the warehouse app as a user in warehouse *61*.</span></span>
1. <span data-ttu-id="4a596-250">Andare a **In uscita \> Creazione prelievo del cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a596-250">Go to **Outbound \> Cluster pick create**.</span></span>

    <span data-ttu-id="4a596-251">Viene visualizzata la pagina **ATTIVITÀ: assegnare il lavoro al cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a596-251">The **TASK: Assign work to Cluster** page appears.</span></span>

1. <span data-ttu-id="4a596-252">Immettere l'ID lavoro per l'ordine cliente 1 per assegnarlo alla posizione cluster 1.</span><span class="sxs-lookup"><span data-stu-id="4a596-252">Enter the work ID for sales order 1 to assign it to cluster position 1.</span></span>
1. <span data-ttu-id="4a596-253">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-253">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="4a596-254">Immettere l'ID lavoro per l'ordine cliente 2 per assegnarlo alla posizione cluster 2.</span><span class="sxs-lookup"><span data-stu-id="4a596-254">Enter the work ID for sales order 2 to assign it to cluster position 2.</span></span>
1. <span data-ttu-id="4a596-255">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-255">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="4a596-256">Viene visualizzata la pagina **ATTIVITÀ: Creazione prelievo del cluster: prelievo** che mostra *Articolo L0101 2 PL*.</span><span class="sxs-lookup"><span data-stu-id="4a596-256">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item L0101 2 PL*.</span></span>

<span data-ttu-id="4a596-257">Poiché il profilo cluster imposta il numero di posizioni su 2, il sistema indirizza automaticamente al primo prelievo consolidato: due pallet (PL) dell'articolo *L0101*.</span><span class="sxs-lookup"><span data-stu-id="4a596-257">Because the cluster profile set the number of positions to 2, the system automatically directs you to the first consolidate pick: two pallets (PL) of item *L0101*.</span></span>

<span data-ttu-id="4a596-258">In qualsiasi momento durante i seguenti passaggi, è possibile selezionare la scheda **Dettagli** per visualizzare ulteriori informazioni sull'attività, come la posizione di prelievo.</span><span class="sxs-lookup"><span data-stu-id="4a596-258">At any time during the following steps, you can select the **Details** tab to view additional information about the task, such as the picking location.</span></span>

1. <span data-ttu-id="4a596-259">Impostare il campo **ARTICOLO** su *L0101*.</span><span class="sxs-lookup"><span data-stu-id="4a596-259">Set the **ITEM** field to *L0101*.</span></span> <span data-ttu-id="4a596-260">Ciò conferma il numero di articolo, richiesto per questa voce di menu (è stata configurata in precedenza selezionando **Impostazione conferma lavoro** dalla pagina **Voce di menu del dispositivo mobile** quando è stata creata questa voce di menu).</span><span class="sxs-lookup"><span data-stu-id="4a596-260">This confirms the item number, which is required for this menu item (you configured this earlier by selecting **Work confirmation setup**  from the **Mobile device menu item** page when you created this menu item).</span></span>
1. <span data-ttu-id="4a596-261">Immettere il numero di targa associato all'articolo nella posizione da cui si sta prelevando.</span><span class="sxs-lookup"><span data-stu-id="4a596-261">Enter the license plate number that is associated with the item in the location that is being picked.</span></span> <span data-ttu-id="4a596-262">Verranno prelevati due pallet.</span><span class="sxs-lookup"><span data-stu-id="4a596-262">You will pick two pallets.</span></span>
1. <span data-ttu-id="4a596-263">Impostare il campo **LP** su *LP\_PICK\_01*.</span><span class="sxs-lookup"><span data-stu-id="4a596-263">Set the **LP** field to *LP\_PICK\_01*.</span></span>
1. <span data-ttu-id="4a596-264">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-264">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="4a596-265">Viene visualizzata la pagina **ATTIVITÀ: Ordinamento: Creazione prelievo del cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a596-265">The **TASK: Sort: Cluster Pick Create** page appears.</span></span> <span data-ttu-id="4a596-266">Qui, i due pallet prelevati vengono ordinati in una posizione di prelievo.</span><span class="sxs-lookup"><span data-stu-id="4a596-266">Here, you will sort the two picked pallets into a pick position.</span></span> <span data-ttu-id="4a596-267">Questa posizione potrebbe essere un totalizzatore o un contenitore utilizzato per separare le scorte prelevate dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="4a596-267">This position might be a tote or container that is used to separate the picked inventory by sales order.</span></span>

1. <span data-ttu-id="4a596-268">Visualizzare i dettagli mostrati per l'articolo (*L0101*) e la quantità (*20* ea) che verrà ordinato nella posizione 1 (per l'ordine cliente 1).</span><span class="sxs-lookup"><span data-stu-id="4a596-268">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="4a596-269">Impostare il campo **NOME POSIZIONE** su *1*.</span><span class="sxs-lookup"><span data-stu-id="4a596-269">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="4a596-270">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-270">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="4a596-271">Visualizzare i dettagli mostrati per l'articolo (*L0101*) e la quantità (*20* ea) che verrà ordinato nella posizione 2 (per l'ordine cliente 2).</span><span class="sxs-lookup"><span data-stu-id="4a596-271">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="4a596-272">Impostare il campo **NOME POSIZIONE** su *2*.</span><span class="sxs-lookup"><span data-stu-id="4a596-272">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="4a596-273">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-273">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="4a596-274">Viene visualizzata la pagina **ATTIVITÀ: Creazione prelievo del cluster: prelievo** che mostra *Articolo T0100 7 ea*.</span><span class="sxs-lookup"><span data-stu-id="4a596-274">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item T0100 7 ea*.</span></span>

<span data-ttu-id="4a596-275">In questo scenario, la posizione 1 non può accettare l'intera quantità di articoli che devono essere prelevati per evadere l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="4a596-275">In this scenario, position 1 can't accept the full quantity of items that must be picked to fulfill sales order 1.</span></span> <span data-ttu-id="4a596-276">Una posizione deve essere contrassegnata come piena.</span><span class="sxs-lookup"><span data-stu-id="4a596-276">A position must be marked as full.</span></span> <span data-ttu-id="4a596-277">In questo scenario, si esegue un prelievo parziale del secondo articolo.</span><span class="sxs-lookup"><span data-stu-id="4a596-277">In this scenario, you will do a partial pick of the second item.</span></span> <span data-ttu-id="4a596-278">Il secondo articolo verrà prelevato parzialmente per la posizione 1 e verrà creato un nuovo lavoro per prelevare la quantità rimanente per evadere l'ordine.</span><span class="sxs-lookup"><span data-stu-id="4a596-278">The second item will be partially picked for position 1, and new work will be created to pick the remaining quantity to fulfill the order.</span></span>

1. <span data-ttu-id="4a596-279">Selezionare il pulsante Menu (a volte indicato come hamburger o pulsante hamburger), quindi selezionare **Posizione piena**.</span><span class="sxs-lookup"><span data-stu-id="4a596-279">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Position full**.</span></span>
1. <span data-ttu-id="4a596-280">Identificare la posizione piena e selezionare *1*.</span><span class="sxs-lookup"><span data-stu-id="4a596-280">Identify the position that is full, and select *1*.</span></span>
1. <span data-ttu-id="4a596-281">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-281">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="4a596-282">Immettere la quantità di prelievo che può ancora essere prelevata nella posizione 1.</span><span class="sxs-lookup"><span data-stu-id="4a596-282">Enter the pick quantity that can still be picked into position 1.</span></span> <span data-ttu-id="4a596-283">Il sistema può determinare quale numero di articolo viene prelevato.</span><span class="sxs-lookup"><span data-stu-id="4a596-283">The system can determine which item number is being picked.</span></span>
1. <span data-ttu-id="4a596-284">Immetti *2*.</span><span class="sxs-lookup"><span data-stu-id="4a596-284">Enter *2*.</span></span>
1. <span data-ttu-id="4a596-285">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-285">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="4a596-286">Confermare il numero di articolo per completare il prelievo dell'articolo rimanente nella posizione 2.</span><span class="sxs-lookup"><span data-stu-id="4a596-286">Confirm the item number to complete the pick of the remaining item into position 2.</span></span>
1. <span data-ttu-id="4a596-287">Impostare il campo **ARTICOLO** su *T0100*.</span><span class="sxs-lookup"><span data-stu-id="4a596-287">Set the **ITEM** field to *T0100*.</span></span>
1. <span data-ttu-id="4a596-288">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-288">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="4a596-289">Immettere la targa da cui viene prelevato l'articolo impostando il campo **LP** su *LPREPL04*.</span><span class="sxs-lookup"><span data-stu-id="4a596-289">Enter the license plate that the item is being picked from by setting the **LP** field to *LPREPL04*.</span></span>
1. <span data-ttu-id="4a596-290">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-290">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="4a596-291">Visualizzare i dettagli mostrati per l'articolo (*T0100*) e la quantità (*2* ea) che verrà ordinato nella posizione 2 (per l'ordine cliente 2).</span><span class="sxs-lookup"><span data-stu-id="4a596-291">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="4a596-292">Impostare il campo **NOME POSIZIONE** su *2*.</span><span class="sxs-lookup"><span data-stu-id="4a596-292">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="4a596-293">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-293">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="4a596-294">Visualizzare i dettagli mostrati per l'articolo (*T0100*) e la quantità (*2* ea) che verrà ordinato nella posizione 1 (per l'ordine cliente 1).</span><span class="sxs-lookup"><span data-stu-id="4a596-294">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="4a596-295">Impostare il campo **NOME POSIZIONE** su *1*.</span><span class="sxs-lookup"><span data-stu-id="4a596-295">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="4a596-296">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-296">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="4a596-297">Viene visualizzata la pagina **ATTIVITÀ: Creazione prelievo del cluster: Inserimento**.</span><span class="sxs-lookup"><span data-stu-id="4a596-297">The **TASK: Cluster Pick Create: Put** page appears.</span></span>

<span data-ttu-id="4a596-298">In questo scenario, il prelievo del cluster è stato completato e all'utente viene chiesto di riporre gli articoli prelevati dalla posizione 1 e dalla posizione 2 nella posizione di gestione temporanea *STAGE01*.</span><span class="sxs-lookup"><span data-stu-id="4a596-298">In this scenario, the cluster pick has been completed, and the user is directed to put away the picked items from position 1 and position 2 into staging location *STAGE01*.</span></span>

1. <span data-ttu-id="4a596-299">Esaminare le informazioni nella pagina.</span><span class="sxs-lookup"><span data-stu-id="4a596-299">Review the information on the page.</span></span> <span data-ttu-id="4a596-300">Mostra che una quantità totale di *44* sarà messa nella posizione di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="4a596-300">It shows that a total quantity of *44* will be put to the staging location.</span></span>
1. <span data-ttu-id="4a596-301">Selezionare **OK** (segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="4a596-301">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="4a596-302">Viene ricevuto un messaggio di tipo "Cluster completato".</span><span class="sxs-lookup"><span data-stu-id="4a596-302">You receive a "Cluster Completed" message.</span></span>

<span data-ttu-id="4a596-303">Ora è possibile usare la voce di menu **Prelievo vendite** per prelevare la quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="4a596-303">You can now use the **Sales Picking** menu item to pick the remaining quantity.</span></span> <span data-ttu-id="4a596-304">È quindi possibile utilizzare la voce di menu **Caricamento vendite** per spostare gli articoli dalla posizione di gestione temporanea alla banchina di carico.</span><span class="sxs-lookup"><span data-stu-id="4a596-304">You can then use the **Sales loading** menu item to move the items from the staging location to the loading dock.</span></span>
