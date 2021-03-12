---
title: Cluster di stoccaggio
description: I cluster di stoccaggio offrono un modo per prelevare più targhe contemporaneamente e portarle per lo stoccaggio in ubicazioni diverse. Possono essere molto utili per le attività di vendita al dettaglio, dove le targhe in genere non sono pallet completi di inventario.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 297792e90b3d2da0d738f5cbaa14779bc17ea3c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996200"
---
# <a name="putaway-clusters"></a><span data-ttu-id="e3e12-104">Cluster di stoccaggio</span><span class="sxs-lookup"><span data-stu-id="e3e12-104">Putaway clusters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3e12-105">I cluster di stoccaggio offrono un modo per prelevare più targhe contemporaneamente e portarle per lo stoccaggio in ubicazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="e3e12-105">Putaway clusters offer a way to pick multiple license plates at the same time and then take them for putaway in different locations.</span></span> <span data-ttu-id="e3e12-106">Questo processo è spesso denominato *milk run*.</span><span class="sxs-lookup"><span data-stu-id="e3e12-106">This process is often referred to as a *milk run*.</span></span> <span data-ttu-id="e3e12-107">I cluster di stoccaggio possono essere molto utili per le attività di vendita al dettaglio, dove le targhe in genere non sono pallet completi di inventario.</span><span class="sxs-lookup"><span data-stu-id="e3e12-107">Putaway clusters can be very useful for retail businesses, where license plates typically aren't full pallets of inventory.</span></span> 

## <a name="turn-on-the-cluster-putaway-feature"></a><span data-ttu-id="e3e12-108">Attivare la funzione stoccaggio cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-108">Turn on the cluster putaway feature</span></span>

<span data-ttu-id="e3e12-109">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="e3e12-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="e3e12-110">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="e3e12-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="e3e12-111">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e3e12-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="e3e12-112">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="e3e12-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="e3e12-113">**Nome funzionalità:** *Funzione stoccaggio cluster*</span><span class="sxs-lookup"><span data-stu-id="e3e12-113">**Feature name:** *Cluster putaway feature*</span></span>

## <a name="setup-for-the-example-scenario"></a><span data-ttu-id="e3e12-114">Configurazione per lo scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="e3e12-114">Setup for the example scenario</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="e3e12-115">Profili cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-115">Cluster profiles</span></span>

<span data-ttu-id="e3e12-116">Il profilo del cluster di stoccaggio determina dove andrà un articolo, in base all'ubicazione assegnata all'articolo al momento del ricevimento.</span><span class="sxs-lookup"><span data-stu-id="e3e12-116">The putaway cluster profile determines where an item will go, based on the location that is assigned to the item at the time of receipt.</span></span> <span data-ttu-id="e3e12-117">Se sono richiesti cluster diversi, è necessario creare cluster di stoccaggio diversi, uno per ciascuna voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="e3e12-117">If different clusters are required, different putaway clusters should be created, one for each mobile device menu item.</span></span>

1. <span data-ttu-id="e3e12-118">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Profili cluster**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-118">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="e3e12-119">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-119">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e3e12-120">Nella visualizzazione **Intestazione**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-120">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="e3e12-121">**ID profilo del cluster di stoccaggio:** *Stoccaggio cluster*</span><span class="sxs-lookup"><span data-stu-id="e3e12-121">**Putaway cluster profile ID:** *Cluster putaway*</span></span>
    - <span data-ttu-id="e3e12-122">**Nome ID profilo del cluster di stoccaggio:** *Stoccaggio cluster*</span><span class="sxs-lookup"><span data-stu-id="e3e12-122">**Putaway cluster profile ID Name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="e3e12-123">**Tipo di cluster:** *Stoccaggio*</span><span class="sxs-lookup"><span data-stu-id="e3e12-123">**Cluster type:** *Putaway*</span></span>
    - <span data-ttu-id="e3e12-124">**Numero sequenza:** accetta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="e3e12-124">**Sequence number:** Accept the default value.</span></span>

1. <span data-ttu-id="e3e12-125">Selezionare **Salva** per rendere disponibili i campi richiesti nella Scheda dettaglio **Generale**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-125">Select **Save** to make the required fields on the **General** FastTab available.</span></span>
1. <span data-ttu-id="e3e12-126">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-126">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="e3e12-127">**Tempistica assegnazione cluster:** *Al ricevimento*</span><span class="sxs-lookup"><span data-stu-id="e3e12-127">**Cluster assignment timing:** *At receipt*</span></span>

        <span data-ttu-id="e3e12-128">Questo campo definisce se il cluster di stoccaggio deve essere assegnato immediatamente quando viene ricevuto l'inventario o se deve essere ordinato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e3e12-128">This field defines whether the putaway cluster should be assigned immediately when the inventory is received, or whether it should be sorted later.</span></span>

    - <span data-ttu-id="e3e12-129">**Regola di assegnazione cluster:** *Manuale*</span><span class="sxs-lookup"><span data-stu-id="e3e12-129">**Cluster assignment rule:** *Manual*</span></span>

        <span data-ttu-id="e3e12-130">Questo campo indica se l'assegnazione del cluster deve essere determinata automaticamente dal sistema o manualmente dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e3e12-130">This field defines whether the cluster assignment should be determined automatically by the system or manually by the user.</span></span>

    - <span data-ttu-id="e3e12-131">**Codice direttiva:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="e3e12-131">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="e3e12-132">**Individuazione cluster di stoccaggio:** *Ricezione*</span><span class="sxs-lookup"><span data-stu-id="e3e12-132">**Putaway cluster locate:** *Receipt*</span></span>

        <span data-ttu-id="e3e12-133">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e12-133">The following values are available:</span></span>

        - <span data-ttu-id="e3e12-134">**Ricezione** – L'ubicazione viene individuata immediatamente durante l'entrata.</span><span class="sxs-lookup"><span data-stu-id="e3e12-134">**Receipt** – A location is found immediately during receipt.</span></span>
        - <span data-ttu-id="e3e12-135">**Chiusura cluster** - L'ubicazione viene individuata alla chiusura del cluster.</span><span class="sxs-lookup"><span data-stu-id="e3e12-135">**Cluster close** – A location is found when the cluster is closed.</span></span>
        - <span data-ttu-id="e3e12-136">**Diretto dall'utente** - Viene trovata una posizione quando la targa viene prelevata dal cluster per lo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="e3e12-136">**User directed** – A location is found when the license plate is picked from the cluster for putaway.</span></span> <span data-ttu-id="e3e12-137">In questo caso, non viene specificata alcuna ubicazione quando viene creato il lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="e3e12-137">In this case, no location is specified when the putaway work is created.</span></span> <span data-ttu-id="e3e12-138">Durante lo stoccaggio stesso, l'utente deve scansionare la targa o l'ID di lavoro per avviare la fase di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="e3e12-138">During the putaway itself, the user must scan the license plate or work ID to initiate the put step.</span></span> <span data-ttu-id="e3e12-139">Il sistema quindi trova di nuovo l'ubicazione di stoccaggio e dice all'utente dove collocare la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="e3e12-139">The system then finds the put location again and tells the user where to put the picked quantity.</span></span>

    - <span data-ttu-id="e3e12-140">**Cluster di stoccaggio per utente:** *No*</span><span class="sxs-lookup"><span data-stu-id="e3e12-140">**Putaway cluster per user:** *No*</span></span>

        <span data-ttu-id="e3e12-141">Questo campo definisce se ogni cluster deve essere univoco per ogni utente quando i cluster vengono assegnati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e3e12-141">This field defines whether each cluster should be unique per user when clusters are automatically assigned.</span></span> <span data-ttu-id="e3e12-142">È disponibile solo quando il campo **Regola di assegnazione cluster** è impostato su *Automatico*.</span><span class="sxs-lookup"><span data-stu-id="e3e12-142">It's available only when the **Cluster assignment rule** field is set to *Automatic*.</span></span>

    - <span data-ttu-id="e3e12-143">**Limitazione di unità:** Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="e3e12-143">**Unit restriction:** Leave this field blank.</span></span>

        <span data-ttu-id="e3e12-144">Questo campo definisce l'unità che deve essere ricevuta affinché il profilo sia valido.</span><span class="sxs-lookup"><span data-stu-id="e3e12-144">This field defines the unit that must be received for the profile to be valid.</span></span> <span data-ttu-id="e3e12-145">Se è lasciato vuoto, tutte le unità sono valide.</span><span class="sxs-lookup"><span data-stu-id="e3e12-145">If it's left blank, all units are valid.</span></span>

    - <span data-ttu-id="e3e12-146">**Interruzione unità di lavoro:** *Individuale*</span><span class="sxs-lookup"><span data-stu-id="e3e12-146">**Work unit break:** *Individual*</span></span>

        <span data-ttu-id="e3e12-147">Questo campo definisce se tutto l'inventario deve essere consolidato (utilizzando l'ID cluster e la targa) su una targa quando un cluster viene chiuso e se deve essere riposto come una singola targa o separatamente sulle targhe che sono state ricevute.</span><span class="sxs-lookup"><span data-stu-id="e3e12-147">This field defines whether all inventory should be consolidated (by using the cluster ID and the license plate) onto one license plate when a cluster is closed, and whether it should be put away as a single license plate or separately on the license plates that were received.</span></span> <span data-ttu-id="e3e12-148">Questo campo non è disponibile quando il campo **Individuazione cluster di stoccaggio** è impostato su *Ricezione*.</span><span class="sxs-lookup"><span data-stu-id="e3e12-148">This field is unavailable when the **Putaway cluster locate** field is set to *Receipt*.</span></span>

    - <span data-ttu-id="e3e12-149">**Il cluster persiste come targa padre:** *No*</span><span class="sxs-lookup"><span data-stu-id="e3e12-149">**Cluster persists as Parent License Plate:** *No*</span></span>

        <span data-ttu-id="e3e12-150">Se questa opzione è impostata su *Sì*, una volta completato il passaggio di inserimento, l'ID cluster diventerà una targa padre e tutti gli elementi sull'ID cluster verranno collegati a quella targa padre.</span><span class="sxs-lookup"><span data-stu-id="e3e12-150">If this option is set to *Yes*, when the put step is completed, the cluster ID will become a parent license plate, and all items on the cluster ID will be linked to that parent license plate.</span></span>

1. <span data-ttu-id="e3e12-151">Nella Scheda dettaglio **Ordinamento cluster** è possibile definire i criteri di ordinamento dello stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="e3e12-151">On the **Cluster sorting** FastTab, you can define putaway sorting criteria.</span></span> <span data-ttu-id="e3e12-152">Selezionare **Nuovo** nella barra degli strumenti per aggiungere una riga e quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-152">Select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="e3e12-153">**Numero sequenza:** accetta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="e3e12-153">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="e3e12-154">**Nome campo:** *WMSLocationId*</span><span class="sxs-lookup"><span data-stu-id="e3e12-154">**Field name:** *WMSLocationId*</span></span>

        <span data-ttu-id="e3e12-155">Questo campo definisce il campo che questa riga deve utilizzare come criterio di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="e3e12-155">This field defines the field that this line should use as a sorting criterion.</span></span>

    - <span data-ttu-id="e3e12-156">**Ordinamento:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="e3e12-156">**Sorting:** *Ascending*</span></span>

        <span data-ttu-id="e3e12-157">Questo campo definisce se l'ordinamento deve essere eseguito in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="e3e12-157">This field defines whether sorting should be done in ascending or descending order.</span></span>

1. <span data-ttu-id="e3e12-158">Nella Scheda dettaglio **Modello di lavoro cluster**, selezionare **Nuovo** nella barra degli strumenti per aggiungere una riga e quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-158">On the **Cluster work template** FastTab, select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="e3e12-159">**Tipo di ordine di lavoro:** *Ordini fornitore*</span><span class="sxs-lookup"><span data-stu-id="e3e12-159">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="e3e12-160">**Modello di lavoro:** *61 PO Diretto*</span><span class="sxs-lookup"><span data-stu-id="e3e12-160">**Work template:** *61 PO Direct*</span></span>

1. <span data-ttu-id="e3e12-161">Nel riquadro azioni selezionare **Salva** e quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-161">On the Action Pane, select **Save**, and then select **Edit query**.</span></span>
1. <span data-ttu-id="e3e12-162">Nella finestra di dialogo **Stoccaggio cluster**, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una seconda riga alla quey.</span><span class="sxs-lookup"><span data-stu-id="e3e12-162">In the **Cluster putaway** dialog box, on the **Range** tab, select **Add** to add a second line to the query.</span></span> <span data-ttu-id="e3e12-163">Quindi aggiornare le righe della query come mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e3e12-163">Then update the query lines as shown in the following table.</span></span>

    | <span data-ttu-id="e3e12-164">Tabella</span><span class="sxs-lookup"><span data-stu-id="e3e12-164">Table</span></span> | <span data-ttu-id="e3e12-165">Tabella derivata</span><span class="sxs-lookup"><span data-stu-id="e3e12-165">Derived table</span></span> | <span data-ttu-id="e3e12-166">Campo</span><span class="sxs-lookup"><span data-stu-id="e3e12-166">Field</span></span> | <span data-ttu-id="e3e12-167">Criteri</span><span class="sxs-lookup"><span data-stu-id="e3e12-167">Criteria</span></span> |
    |---|---|---|---|
    | <span data-ttu-id="e3e12-168">Lavoro</span><span class="sxs-lookup"><span data-stu-id="e3e12-168">Work</span></span> | <span data-ttu-id="e3e12-169">Lavoro</span><span class="sxs-lookup"><span data-stu-id="e3e12-169">Work</span></span> | <span data-ttu-id="e3e12-170">Magazzino</span><span class="sxs-lookup"><span data-stu-id="e3e12-170">Warehouse</span></span> | <span data-ttu-id="e3e12-171">*61*</span><span class="sxs-lookup"><span data-stu-id="e3e12-171">*61*</span></span> |
    | <span data-ttu-id="e3e12-172">Lavoro</span><span class="sxs-lookup"><span data-stu-id="e3e12-172">Work</span></span> | <span data-ttu-id="e3e12-173">Lavoro</span><span class="sxs-lookup"><span data-stu-id="e3e12-173">Work</span></span> | <span data-ttu-id="e3e12-174">ID lavoro</span><span class="sxs-lookup"><span data-stu-id="e3e12-174">Work ID</span></span> | <span data-ttu-id="e3e12-175">Lascia vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="e3e12-175">Leave this field blank.</span></span> |

1. <span data-ttu-id="e3e12-176">Selezionare **OK** per salvare la query e chiudere finestra dialogo.</span><span class="sxs-lookup"><span data-stu-id="e3e12-176">Select **OK** to save the query and close the dialog box.</span></span>
1. <span data-ttu-id="e3e12-177">Nel riquadro azioni selezionare **Salva** e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e3e12-177">On the Action Pane, select **Save**, and close the page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3e12-178">I campi nel profilo del cluster che appaiono inattivi quando **Genera ID cluster** è impostato su *Sì* non sono disponibili e non verranno presi in considerazione quando viene utilizzata questa funzione.</span><span class="sxs-lookup"><span data-stu-id="e3e12-178">Fields in the cluster profile that appear dimmed when **Generate cluster ID** is set to *Yes* are unavailable and won't be considered when this feature is used.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="e3e12-179">Voci di menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="e3e12-179">Mobile device menu items</span></span>

<span data-ttu-id="e3e12-180">Per questa funzione sono disponibili due nuove voci di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="e3e12-180">Two new mobile device menu items are available for this feature.</span></span> <span data-ttu-id="e3e12-181">La voce di menu **Ricevi e ordina cluster** viene utilizzata per ordinare l'inventario ricevuto in un cluster di stoccaggio al momento della ricezione.</span><span class="sxs-lookup"><span data-stu-id="e3e12-181">The **Receive and sort cluster** menu item is used to sort the received inventory into a putaway cluster upon receipt.</span></span> <span data-ttu-id="e3e12-182">La voce di menu **Stoccaggio cluster** viene utilizzata per riporre il cluster dopo che è stato assegnato.</span><span class="sxs-lookup"><span data-stu-id="e3e12-182">The **Cluster putaway** menu item is used to put the cluster away after it has been assigned.</span></span>

#### <a name="receive-and-sort-cluster"></a><span data-ttu-id="e3e12-183">Ricevi e ordina cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-183">Receive and sort cluster</span></span>

<span data-ttu-id="e3e12-184">Creare una nuova voce di menu del dispositivo mobile per la ricezione dell'inventario e l'ordinamento in un cluster.</span><span class="sxs-lookup"><span data-stu-id="e3e12-184">Create a new mobile device menu item for receiving inventory and sorting into a cluster.</span></span> <span data-ttu-id="e3e12-185">Questa voce di menu creerà il lavoro in entrata dopo la ricezione dell'inventario, il che indica che la voce di menu di ricezione verrà utilizzata per i cluster di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="e3e12-185">This menu item will create inbound work after inventory is received, which indicates that the receiving menu item will be used for putaway clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="e3e12-186">La voce di menu **Ricevi e ordina cluster** può essere utilizzata con le seguenti voci di menu di ricezione:</span><span class="sxs-lookup"><span data-stu-id="e3e12-186">The **Receive and sort cluster** menu item can be used with the following receiving menu items:</span></span>
>
> - <span data-ttu-id="e3e12-187">Ricevimento riga ordine acquisto</span><span class="sxs-lookup"><span data-stu-id="e3e12-187">Purchase order line receiving</span></span>
> - <span data-ttu-id="e3e12-188">Ricevimento articolo ordine acquisto</span><span class="sxs-lookup"><span data-stu-id="e3e12-188">Purchase order item receiving</span></span>
> - <span data-ttu-id="e3e12-189">Ricezione articoli di carico</span><span class="sxs-lookup"><span data-stu-id="e3e12-189">Load item receiving</span></span>

1. <span data-ttu-id="e3e12-190">Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-190">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="e3e12-191">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-191">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e3e12-192">Nella visualizzazione **Intestazione**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-192">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="e3e12-193">**Nome voce di menu:** *Ricevi e ordina cluster*</span><span class="sxs-lookup"><span data-stu-id="e3e12-193">**Menu item name:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="e3e12-194">**Titolo:** *Ricevi e ordina cluster*</span><span class="sxs-lookup"><span data-stu-id="e3e12-194">**Title:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="e3e12-195">**Modalità:** *Lavoro*</span><span class="sxs-lookup"><span data-stu-id="e3e12-195">**Mode:** *Work*</span></span>
    - <span data-ttu-id="e3e12-196">**Utilizza lavoro esistente:** *No*</span><span class="sxs-lookup"><span data-stu-id="e3e12-196">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="e3e12-197">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-197">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="e3e12-198">**Processo di creazione lavoro:** *Ricevimento articolo ordine acquisto*</span><span class="sxs-lookup"><span data-stu-id="e3e12-198">**Work creation process:** *Purchase order item receiving*</span></span>
    - <span data-ttu-id="e3e12-199">**Genera targa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="e3e12-199">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="e3e12-200">**Assegna cluster di stoccaggio:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="e3e12-200">**Assign putaway cluster:** *Yes*</span></span>

        > [!NOTE]
        > <span data-ttu-id="e3e12-201">L'opzione **Assegna cluster di stoccaggio** è disponibile solo per un'attività *Processo di creazione lavoro* composta da un unico passaggio in ricezione.</span><span class="sxs-lookup"><span data-stu-id="e3e12-201">The **Assign putaway cluster** option is available only for the one-step *Work creation process* activity for receiving.</span></span>

    <span data-ttu-id="e3e12-202">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="e3e12-202">Accept the default values for the remaining fields.</span></span>

1. <span data-ttu-id="e3e12-203">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-203">On the Action Pane, select **Save**.</span></span>

#### <a name="cluster-putaway"></a><span data-ttu-id="e3e12-204">Stoccaggio cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-204">Cluster putaway</span></span>

<span data-ttu-id="e3e12-205">Creare una nuova voce di menu del dispositivo mobile per stoccare il cluster dopo che è stato assegnato.</span><span class="sxs-lookup"><span data-stu-id="e3e12-205">Create a new mobile device menu item for putting the cluster away after it has been assigned.</span></span>

1. <span data-ttu-id="e3e12-206">Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="e3e12-207">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-207">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e3e12-208">Nella visualizzazione **Intestazione**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-208">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="e3e12-209">**Nome voce di menu:** *Stoccaggio cluster*</span><span class="sxs-lookup"><span data-stu-id="e3e12-209">**Menu item name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="e3e12-210">**Titolo:** *Stoccaggio cluster*</span><span class="sxs-lookup"><span data-stu-id="e3e12-210">**Title:** *Cluster putaway*</span></span>
    - <span data-ttu-id="e3e12-211">**Modalità:** *Lavoro*</span><span class="sxs-lookup"><span data-stu-id="e3e12-211">**Mode:** *Work*</span></span>
    - <span data-ttu-id="e3e12-212">**Utilizza lavoro esistente:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="e3e12-212">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="e3e12-213">Nella Scheda dettaglio **Generale**, impostare il campo **Diretto da** su *Stoccaggio cluster*.</span><span class="sxs-lookup"><span data-stu-id="e3e12-213">On the **General** FastTab, set the **Directed by** field to *Cluster putaway*.</span></span> <span data-ttu-id="e3e12-214">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="e3e12-214">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="e3e12-215">Nella Scheda dettaglio **Classi di lavoro** impostare la classe di lavoro valida per questa voce di menu del dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="e3e12-215">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item:</span></span>

    - <span data-ttu-id="e3e12-216">**ID classe lavoro:** *Acquisto*</span><span class="sxs-lookup"><span data-stu-id="e3e12-216">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="e3e12-217">**Tipo di ordine di lavoro:** *Ordini fornitore*</span><span class="sxs-lookup"><span data-stu-id="e3e12-217">**Work order type:** *Purchase orders*</span></span>

1. <span data-ttu-id="e3e12-218">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-218">On the Action Pane, select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="e3e12-219">Menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="e3e12-219">Mobile device menu</span></span>

<span data-ttu-id="e3e12-220">Aggiungere le voci di menu appena create al menu in entrata dell'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="e3e12-220">Add the menu items that you just created to the inbound menu of the mobile app.</span></span>

1. <span data-ttu-id="e3e12-221">Accedi a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-221">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="e3e12-222">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-222">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e3e12-223">Nell'elenco dei menu, selezionare **In entrata**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-223">In the menu list, select **Inbound**.</span></span>
1. <span data-ttu-id="e3e12-224">Nell'elenco **Menu e voci di menu disponibili**, trovare e selezionare la voce di menu **Ricevi e ordina cluster**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-224">In the **Available menus and menu items** list, find and select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="e3e12-225">Selezionare il pulsante freccia destra per spostare la voce di menu selezionata nell'elenco **Struttura menu**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-225">Select the right arrow button to move the selected menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="e3e12-226">Utilizzare il pulsante freccia su o freccia giù per spostare la voce di menu nella posizione desiderata nel menu.</span><span class="sxs-lookup"><span data-stu-id="e3e12-226">Use the up arrow or down arrow button to move the menu item into the desired position in the menu.</span></span>
1. <span data-ttu-id="e3e12-227">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-227">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="e3e12-228">Ripetere i passaggi da 4 a 7 per aggiungere le voci di menu rimanenti:</span><span class="sxs-lookup"><span data-stu-id="e3e12-228">Repeat steps 4 through 7 to add the remaining menu items:</span></span>

    - <span data-ttu-id="e3e12-229">Assegna cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-229">Assign cluster</span></span>
    - <span data-ttu-id="e3e12-230">Stoccaggio cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-230">Cluster putaway</span></span>

## <a name="example-scenario"></a><span data-ttu-id="e3e12-231">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="e3e12-231">Example scenario</span></span>

<span data-ttu-id="e3e12-232">Questo scenario simula l'elaborazione del cluster di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="e3e12-232">This scenario simulates putaway cluster processing.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="e3e12-233">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="e3e12-233">Create a purchase order</span></span>

1. <span data-ttu-id="e3e12-234">Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-234">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="e3e12-235">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e3e12-236">Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e3e12-236">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e3e12-237">**Conto fornitore:** *1001*</span><span class="sxs-lookup"><span data-stu-id="e3e12-237">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="e3e12-238">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="e3e12-238">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="e3e12-239">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-239">Select **OK**.</span></span>

    <span data-ttu-id="e3e12-240">Viene visualizzata la pagina **Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-240">The **All purchase orders** page appears.</span></span>

1. <span data-ttu-id="e3e12-241">Nella pagina **Tutti gli ordini fornitore** nella Scheda dettaglio **Righe ordine fornitore**, utilizzare il pulsante **Aggiungi riga** per aggiungere le seguenti righe:</span><span class="sxs-lookup"><span data-stu-id="e3e12-241">On the **All purchase orders** page, on the **Purchase order lines** FastTab, use the **Add line** button to add the following lines:</span></span>

    - <span data-ttu-id="e3e12-242">Riga ordine fornitore 1:</span><span class="sxs-lookup"><span data-stu-id="e3e12-242">Purchase order line 1:</span></span>

        - <span data-ttu-id="e3e12-243">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e3e12-243">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="e3e12-244">**Quantità:** *10*</span><span class="sxs-lookup"><span data-stu-id="e3e12-244">**Quantity:** *10*</span></span>

    - <span data-ttu-id="e3e12-245">Riga ordine fornitore 2:</span><span class="sxs-lookup"><span data-stu-id="e3e12-245">Purchase order line 2:</span></span>

        - <span data-ttu-id="e3e12-246">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e3e12-246">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="e3e12-247">**Quantità:** *20*</span><span class="sxs-lookup"><span data-stu-id="e3e12-247">**Quantity:** *20*</span></span>

    - <span data-ttu-id="e3e12-248">Riga ordine fornitore 3:</span><span class="sxs-lookup"><span data-stu-id="e3e12-248">Purchase order line 3:</span></span>

        - <span data-ttu-id="e3e12-249">**Numero articolo:** *M9215*</span><span class="sxs-lookup"><span data-stu-id="e3e12-249">**Item number:** *M9215*</span></span>
        - <span data-ttu-id="e3e12-250">**Quantità:** *30*</span><span class="sxs-lookup"><span data-stu-id="e3e12-250">**Quantity:** *30*</span></span>

1. <span data-ttu-id="e3e12-251">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-251">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="e3e12-252">Prendere nota del numero di ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e3e12-252">Make a note of the purchase order number.</span></span>

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a><span data-ttu-id="e3e12-253">Ricevi inventario e stoccalo dal dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="e3e12-253">Receive inventory and put it away from the mobile device</span></span>

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a><span data-ttu-id="e3e12-254">Ricevi e ordina l'inventario in un cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-254">Receive and sort the inventory into a cluster</span></span>

1. <span data-ttu-id="e3e12-255">Accedi all'app del magazzino come utente impostato per il magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="e3e12-255">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="e3e12-256">Nel menu principale, selezionare **In entrata**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-256">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="e3e12-257">Nel menu **In entrata** selezionare **Ricevi e ordina cluster**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-257">On the **Inbound** menu, select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="e3e12-258">Nel campo **Numero ordine fornitore**, immettere il numero dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e3e12-258">In the **Ponum** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="e3e12-259">Selezionare **OK** (il simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="e3e12-259">Select **OK** (the check mark button).</span></span>
1. <span data-ttu-id="e3e12-260">Selezionare il campo **Articolo**, quindi inserire il numero articolo *A0001* e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-260">Select the **Item** field, enter item number *A0001*, and then select **OK**.</span></span>
1. <span data-ttu-id="e3e12-261">Selezionare il campo **Qtà** inserire *10* utilizzando il tastierino numerico, quindi selezionare il pulsante del segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="e3e12-261">Select the **Qty** field, enter *10* by using the number pad, and then select the check mark button.</span></span>
1. <span data-ttu-id="e3e12-262">Nella pagina delle attività **Qtà** selezionare **OK** (il pulsante con il segno di spunta) per confermare la quantità inserita.</span><span class="sxs-lookup"><span data-stu-id="e3e12-262">On the **Qty** task page, select **OK** (the check mark button) to confirm the quantity that you entered.</span></span>
1. <span data-ttu-id="e3e12-263">Nella pagina delle attività **Articolo** selezionare **OK** per confermare che l'articolo *A0001* è stato inserito.</span><span class="sxs-lookup"><span data-stu-id="e3e12-263">On the **Item** task page, select **OK** to confirm that item *A0001* was entered.</span></span>
1. <span data-ttu-id="e3e12-264">Selezionare il campo **ID cluster** e inserire un valore per assegnare un ID al cluster che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="e3e12-264">Select the **Cluster ID** field, and enter a value to assign an ID for the cluster that you're creating.</span></span>

    <span data-ttu-id="e3e12-265">L'ID immesso qui verrà utilizzato quando vengono ricevuti i due articoli rimanenti nell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e3e12-265">The ID that you enter here will be used when the two remaining items on the purchase order are received.</span></span>

1. <span data-ttu-id="e3e12-266">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-266">Select **OK**.</span></span>

    <span data-ttu-id="e3e12-267">Viene visualizzata la pagina delle attività **Numero ordine fornitore** e viene visualizzato un messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="e3e12-267">The **Ponum** task page appears and shows a "Work completed" message.</span></span>

    <span data-ttu-id="e3e12-268">L'articolo *A0001* è stato ricevuto nell'ubicazione *RECV* e assegnato all'ID cluster immesso nel passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="e3e12-268">Item *A0001* has now been received into the *RECV* location and assigned to the cluster ID that you entered in step 10.</span></span>

1. <span data-ttu-id="e3e12-269">Ripetere i passaggi da 4 a 11 per ricevere i due articoli rimanenti dall'ordine fornitore e assegnarli all'ID cluster:</span><span class="sxs-lookup"><span data-stu-id="e3e12-269">Repeat steps 4 through 11 to receive the remaining two items from the purchase order and assign them to the cluster ID:</span></span>

    - <span data-ttu-id="e3e12-270">Quantità *20* per l'articolo *A0002*</span><span class="sxs-lookup"><span data-stu-id="e3e12-270">A quantity of *20* for item *A0002*</span></span>
    - <span data-ttu-id="e3e12-271">Quantità *30* per l'articolo *M9215*</span><span class="sxs-lookup"><span data-stu-id="e3e12-271">A quantity of *30* for item *M9215*</span></span>

#### <a name="close-the-cluster"></a><span data-ttu-id="e3e12-272">Chiudi il cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-272">Close the cluster</span></span>

<span data-ttu-id="e3e12-273">Prima di poter stoccare gli articoli nel cluster, è necessario chiudere il cluster.</span><span class="sxs-lookup"><span data-stu-id="e3e12-273">Before the items in the cluster can be put away, the cluster must be closed.</span></span>

1. <span data-ttu-id="e3e12-274">In Supply Chain Management, andare a **Gestione magazzino \> Lavoro \> In uscita \> Cluster di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-274">In Supply Chain Management, go to **Warehouse management \> Work \> Outbound \> Work clusters**.</span></span>
1. <span data-ttu-id="e3e12-275">Nella pagina **Cluster di lavoro** nella sezione **Cluster di lavoro** cercare nel campo **ID cluster** per l'ID cluster immesso in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e3e12-275">On the **Work clusters** page, in the **Work cluster** section, search the **Cluster ID** field for the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="e3e12-276">Se il cluster non viene visualizzato, potrebbe essere già stato chiuso.</span><span class="sxs-lookup"><span data-stu-id="e3e12-276">If the cluster isn't shown, it might already have been closed.</span></span> <span data-ttu-id="e3e12-277">Per determinare se il cluster è stato chiuso, selezionare la casella di controllo **Mostra lavoro chiuso** e cercare l'ID cluster immesso in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e3e12-277">To determine whether the cluster was closed, select the **Show closed work** check box, and search for the cluster ID that you entered earlier.</span></span> <span data-ttu-id="e3e12-278">Eseguire quindi uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e12-278">Then follow one of these steps:</span></span>

    - <span data-ttu-id="e3e12-279">Se il cluster è stato chiuso, saltare i passaggi rimanenti di questa procedura e passare alla procedura successiva, [Stocca il cluster](#put-the-cluster-away).</span><span class="sxs-lookup"><span data-stu-id="e3e12-279">If the cluster has been closed, skip the remaining steps of this procedure, and move on to the next procedure, [Put the cluster away](#put-the-cluster-away).</span></span>
    - <span data-ttu-id="e3e12-280">Se il cluster non è stato chiuso, seguire i passaggi rimanenti di questa procedura per chiudere manualmente il cluster.</span><span class="sxs-lookup"><span data-stu-id="e3e12-280">If the cluster hasn't been closed, follow the remaining steps of this procedure to manually close the cluster.</span></span> <span data-ttu-id="e3e12-281">Quindi passare alla procedura successiva.</span><span class="sxs-lookup"><span data-stu-id="e3e12-281">Then move on to the next procedure.</span></span>

1. <span data-ttu-id="e3e12-282">Nella sezione **Cluster di lavoro** selezionare l'ID cluster immesso in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e3e12-282">In the **Work cluster** section, select the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="e3e12-283">Nel riquadro azioni selezionare **Chiudi cluster**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-283">On the Action Pane, select **Close cluster**.</span></span>

    <span data-ttu-id="e3e12-284">Dopo che il cluster è stato chiuso, non viene più visualizzato nella sezione **Cluster di lavoro** (a meno che la casella di controllo **Mostra lavoro chiuso** sia selezionata).</span><span class="sxs-lookup"><span data-stu-id="e3e12-284">After the cluster has been closed, it's no longer shown in the **Work cluster** section (unless the **Show closed work** check box is selected).</span></span>

#### <a name="put-the-cluster-away"></a><span data-ttu-id="e3e12-285">Stocca cluster</span><span class="sxs-lookup"><span data-stu-id="e3e12-285">Put the cluster away</span></span>

1. <span data-ttu-id="e3e12-286">Accedi all'app del magazzino come utente impostato per il magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="e3e12-286">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="e3e12-287">Nel menu principale, selezionare **In entrata**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-287">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="e3e12-288">Nel menu **In entrata** selezionare **Stoccaggio cluster**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-288">On the **Inbound** menu, select **Cluster putaway**.</span></span>
1. <span data-ttu-id="e3e12-289">Selezionare **ID cluster** e inserire l'ID cluster immesso in precedenza per il cluster chiuso.</span><span class="sxs-lookup"><span data-stu-id="e3e12-289">Select **Cluster ID**, and enter the cluster ID that you entered earlier for the closed cluster.</span></span>
1. <span data-ttu-id="e3e12-290">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-290">Select **OK**.</span></span>

    <span data-ttu-id="e3e12-291">Viene visualizzata la pagina **Stoccaggio cluster: Prelievo**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-291">The **Cluster putaway: Pick** page appears.</span></span> <span data-ttu-id="e3e12-292">Mostra l'ID cluster, la posizione di prelievo, gli articoli (il valore *Multiplo* verrà visualizzato) e la quantità totale nel cluster che deve essere prelevata.</span><span class="sxs-lookup"><span data-stu-id="e3e12-292">It shows the cluster ID, the picking location, the items (the value *Multiple* will be shown), and the total quantity in the cluster that must be picked.</span></span>

1. <span data-ttu-id="e3e12-293">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-293">Select **OK**.</span></span>

    <span data-ttu-id="e3e12-294">Viene visualizzata la pagina **Stoccaggio cluster: Stoccaggio**.</span><span class="sxs-lookup"><span data-stu-id="e3e12-294">The **Cluster putaway: Put** page appears.</span></span> <span data-ttu-id="e3e12-295">Le istruzioni **Stoccaggio** identificano l'ID cluster, l'ubicazione di stoccaggio, gli articoli, la quantità totale e gli ID targa per gli articoli ricevuti nel cluster.</span><span class="sxs-lookup"><span data-stu-id="e3e12-295">The **Put** instructions identify the cluster ID, the put location, the items, the total quantity, and the license plate IDs for the items that have been received on the cluster.</span></span>

    <span data-ttu-id="e3e12-296">Sono disponibili le opzioni standard per ignorare o passare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e3e12-296">You have the standard options to override or pass this step.</span></span>

    <span data-ttu-id="e3e12-297">![Pagina Stoccaggio cluster: Stoccaggio](media/Cluster_putaway-Put.png "Pagina Stoccaggio cluster: Stoccaggio")</span><span class="sxs-lookup"><span data-stu-id="e3e12-297">![Cluster putaway: Put page](media/Cluster_putaway-Put.png "Cluster putaway: Put page")</span></span>

1. <span data-ttu-id="e3e12-298">Selezionare **OK** per confermare lo stoccaggio del cluster.</span><span class="sxs-lookup"><span data-stu-id="e3e12-298">Select **OK** to confirm the putaway of the cluster.</span></span>

    <span data-ttu-id="e3e12-299">Viene ricevuto un messaggio "Cluster completato".</span><span class="sxs-lookup"><span data-stu-id="e3e12-299">A "Cluster completed" message is shown.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="e3e12-300">Note e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="e3e12-300">Notes and tips</span></span>

<span data-ttu-id="e3e12-301">Per i casi in cui l'ID cluster diventa la targa padre per un pallet annidato, la posizione di stoccaggio viene fornita automaticamente quando l'ID cluster viene scansionato.</span><span class="sxs-lookup"><span data-stu-id="e3e12-301">For cases where the cluster ID becomes the parent license plate for a nested pallet, the put position is automatically given when the cluster ID is scanned.</span></span> <span data-ttu-id="e3e12-302">Non è necessario scansionare ulteriori targhe, anche se la generazione della targa è impostata su manuale.</span><span class="sxs-lookup"><span data-stu-id="e3e12-302">No further license plate must be scanned, even if license plate generation is set to manual.</span></span>
