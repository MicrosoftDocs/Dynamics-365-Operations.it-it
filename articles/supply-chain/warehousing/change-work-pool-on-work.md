---
title: Modifica pool di lavoro nel lavoro
description: Questo argomento spiega come utilizzare il pulsante Modifica pool di lavoro per gli elementi di lavoro per modificare il pool di lavoro del lavoro esistente.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: cdd0a1b6d022c958e00a1ba8fa87a8715ff88ce5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808896"
---
# <a name="change-work-pool-on-work"></a><span data-ttu-id="a7a20-103">Modifica pool di lavoro nel lavoro</span><span class="sxs-lookup"><span data-stu-id="a7a20-103">Change work pool on work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7a20-104">È possibile utilizzare i pool di lavoro per organizzare il lavoro in gruppi.</span><span class="sxs-lookup"><span data-stu-id="a7a20-104">You can use work pools to organize work into groups.</span></span> <span data-ttu-id="a7a20-105">Ad esempio, è possibile creare un pool di lavoro per classificare il lavoro che si verifica in un'ubicazione specifica del magazzino.</span><span class="sxs-lookup"><span data-stu-id="a7a20-105">For example, you can create a work pool to classify work that occurs in a specific warehouse location.</span></span>

<span data-ttu-id="a7a20-106">La funzionalità *Modifica pool di lavoro nel lavoro* aggiunge un pulsante **Modifica pool di lavoro** nel riquadro azioni per gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-106">The *Change work pool on work* feature adds a **Change work pool** button to the Action Pane for work items.</span></span> <span data-ttu-id="a7a20-107">Pertanto, i responsabili del magazzino possono facilmente modificare il pool di lavoro del lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="a7a20-107">Therefore, warehouse managers can easily change the work pool of existing work.</span></span> <span data-ttu-id="a7a20-108">Questa funzionalità consente ai manager di reagire rapidamente ai cambiamenti nello shop floor del magazzino e aiuta a migliorare la loro capacità di adattarsi alle situazioni mutevoli e alla necessità di trasferire il lavoro a un altro pool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-108">This feature lets managers react quickly to changes on the warehouse shop floor, and it helps improve their ability to adapt to changing situations and the need to transfer work to another work pool.</span></span>

## <a name="turn-on-the-change-work-pool-on-work-feature"></a><span data-ttu-id="a7a20-109">Attivare la funzionalità Modifica pool di lavoro nel lavoro</span><span class="sxs-lookup"><span data-stu-id="a7a20-109">Turn on the Change work pool on work feature</span></span>

<span data-ttu-id="a7a20-110">Prima di iniziare a configurare o utilizzare questa funzionalità, è necessario assicurarsi che sia disponibile nel sistema.</span><span class="sxs-lookup"><span data-stu-id="a7a20-110">Before you begin to set up or use this feature, you must make sure that it's available in your system.</span></span> <span data-ttu-id="a7a20-111">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="a7a20-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a7a20-112">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a7a20-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a7a20-113">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="a7a20-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a7a20-114">**Nome funzionalità:** *Modifica pool di lavoro nel lavoro*</span><span class="sxs-lookup"><span data-stu-id="a7a20-114">**Feature name:** *Change work pool on work*</span></span>

## <a name="set-up-the-change-work-pool-on-work-feature"></a><span data-ttu-id="a7a20-115">Configurare la funzionalità Modifica pool di lavoro nel lavoro</span><span class="sxs-lookup"><span data-stu-id="a7a20-115">Set up the Change work pool on work feature</span></span>

<span data-ttu-id="a7a20-116">Per utilizzare questa funzionalità, è necessario configurare alcuni pool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-116">To use this feature, you must have some work pools set up.</span></span> <span data-ttu-id="a7a20-117">Si potrebbe inoltre configurare i modelli di lavoro in modo che assegnino automaticamente un pool.</span><span class="sxs-lookup"><span data-stu-id="a7a20-117">You might also set up your work templates so that they automatically assign a pool.</span></span> <span data-ttu-id="a7a20-118">Se vuoi analizzare lo scenario di esempio fornito più avanti in questo argomento, configura il sistema come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a7a20-118">If you want to work through the example scenario that is provided later in this topic, set up your system as described in this section.</span></span>

### <a name="set-up-work-pools"></a><span data-ttu-id="a7a20-119">Configurare pool di lavoro</span><span class="sxs-lookup"><span data-stu-id="a7a20-119">Set up work pools</span></span>

<span data-ttu-id="a7a20-120">I pool di lavoro consentono di organizzare gli elementi di lavoro per tipo.</span><span class="sxs-lookup"><span data-stu-id="a7a20-120">Work pools let you organize work items by type.</span></span> <span data-ttu-id="a7a20-121">Per utilizzare la funzionalità *Modifica pool di lavoro nel lavoro*, è necessario disporre di almeno due pool di lavoro disponibili.</span><span class="sxs-lookup"><span data-stu-id="a7a20-121">To work with the *Change work pool on work* feature, you must have at least two work pools available.</span></span> <span data-ttu-id="a7a20-122">Per visualizzare e aggiungere pool di lavoro, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="a7a20-122">To view and add work pools, follow these steps.</span></span>

1. <span data-ttu-id="a7a20-123">Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Pool di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-123">Go to **Warehouse management \> Setup \> Work \> Work pools**.</span></span>
1. <span data-ttu-id="a7a20-124">Se si utilizzano dati dimostrativi della società **USMF** e lo scenario di esempio più avanti in questo argomento, aggiungere due pool di lavoro con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="a7a20-124">If you're working with demo data from the **USMF** company and will work through the example scenario later in this topic, add two work pools that have the following settings:</span></span>

    - <span data-ttu-id="a7a20-125">Pool di lavoro 1:</span><span class="sxs-lookup"><span data-stu-id="a7a20-125">Work pool 1:</span></span>

        - <span data-ttu-id="a7a20-126">**ID pool di lavoro:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="a7a20-126">**Work pool ID:** *Webshop*</span></span>
        - <span data-ttu-id="a7a20-127">**Descrizione:** *Negozio Web*</span><span class="sxs-lookup"><span data-stu-id="a7a20-127">**Description:** *Web Shop*</span></span>

    - <span data-ttu-id="a7a20-128">Pool di lavoro 2:</span><span class="sxs-lookup"><span data-stu-id="a7a20-128">Work pool 2:</span></span>

        - <span data-ttu-id="a7a20-129">**ID pool di lavoro:** *CallCenter*</span><span class="sxs-lookup"><span data-stu-id="a7a20-129">**Work pool ID:** *CallCenter*</span></span>
        - <span data-ttu-id="a7a20-130">**Descrizione** *Servizio clienti*</span><span class="sxs-lookup"><span data-stu-id="a7a20-130">**Description:** *Call Center*</span></span>

1. <span data-ttu-id="a7a20-131">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-131">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="a7a20-132">Imposta modelli di lavoro</span><span class="sxs-lookup"><span data-stu-id="a7a20-132">Set up work templates</span></span>

<span data-ttu-id="a7a20-133">Per ciascuno dei modelli di lavoro, è possibile impostare un pool di lavoro predefinito, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="a7a20-133">For each of your work templates, you can set a default work pool, as you require.</span></span> <span data-ttu-id="a7a20-134">Per ogni modello pertinente, si assegna un pool di lavoro nella colonna **ID pool di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-134">For each relevant template, you assign a work pool in the **Work pool ID** column.</span></span> <span data-ttu-id="a7a20-135">In questo caso, tutti gli elementi di lavoro generati utilizzando un determinato modello ereditano automaticamente il pool di lavoro assegnato.</span><span class="sxs-lookup"><span data-stu-id="a7a20-135">In this case, all work items that are generated by using a given template automatically inherit the assigned work pool.</span></span> <span data-ttu-id="a7a20-136">Se si utilizzano dati dimostrativi della società **USMF** e lo scenario di esempio più avanti in questo argomento, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="a7a20-136">If you're working with the demo data from the **USMF** company and will work through the example scenario later in this topic, follow these steps.</span></span>

1. <span data-ttu-id="a7a20-137">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-137">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="a7a20-138">Nel riquadro azioni seleziona **Modifica** per mettere la pagina in modalità modifica.</span><span class="sxs-lookup"><span data-stu-id="a7a20-138">On the Action Pane, select **Edit** to put the page into editing mode.</span></span>
1. <span data-ttu-id="a7a20-139">Modificare il modello impostando i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a7a20-139">Edit the template by setting the following values:</span></span>

    - <span data-ttu-id="a7a20-140">**Modello di lavoro:** *62 Prelievo da imballare*</span><span class="sxs-lookup"><span data-stu-id="a7a20-140">**Work template:** *62 Pick to pack*</span></span>
    - <span data-ttu-id="a7a20-141">**ID pool di lavoro:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="a7a20-141">**Work pool ID:** *Webshop*</span></span>

1. <span data-ttu-id="a7a20-142">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-142">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="a7a20-143">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="a7a20-143">Example scenario</span></span>

<span data-ttu-id="a7a20-144">Questo scenario mostra come modificare il flusso di elaborazione per un elemento di lavoro esistente modificandone il pool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-144">This scenario shows how to change the stream of processing for an existing work item by changing its work pool.</span></span> <span data-ttu-id="a7a20-145">Utilizza i dati demo della società **USMF** e le impostazioni suggerite in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a7a20-145">It uses demo data from the **USMF** company and the settings that were suggested earlier in this topic.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="a7a20-146">Creare un ordine cliente e rilasciarlo nel magazzino</span><span class="sxs-lookup"><span data-stu-id="a7a20-146">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="a7a20-147">Confermare che l'inventario disponibile sia sufficiente per gli articoli *A0001* e *A0002* nel magazzino *62*.</span><span class="sxs-lookup"><span data-stu-id="a7a20-147">Confirm that there is enough on-hand inventory for items *A0001* and *A0002* in warehouse *62*.</span></span> <span data-ttu-id="a7a20-148">Vai a **Gestione inventario \> Richieste di informazioni e report \> Elenco scorte disponibili** e modificare i filtri come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a7a20-148">Go to **Inventory management \> Inquiries and reports \> On-hand list**, and edit the filters as shown here:</span></span>

    - <span data-ttu-id="a7a20-149">Il valore **Magazzino** inizia con *62*.</span><span class="sxs-lookup"><span data-stu-id="a7a20-149">The **Warehouse** value begins with *62*.</span></span>
    - <span data-ttu-id="a7a20-150">Il valore **Numero articolo** è *A001* o *A002*.</span><span class="sxs-lookup"><span data-stu-id="a7a20-150">The **Item number** value is either *A001* or *A002*.</span></span>

    <span data-ttu-id="a7a20-151">Tutti i dati dimostrativi devono avere una quantità pari a 10.</span><span class="sxs-lookup"><span data-stu-id="a7a20-151">Demo data should have a quantity of 10 each.</span></span>

    <span data-ttu-id="a7a20-152">Successivamente, è necessario creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a7a20-152">Next, you must create a sales order.</span></span>

1. <span data-ttu-id="a7a20-153">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-153">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a7a20-154">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-154">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a7a20-155">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a7a20-155">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a7a20-156">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="a7a20-156">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="a7a20-157">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="a7a20-157">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="a7a20-158">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a7a20-158">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="a7a20-159">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a7a20-159">The new sales order is opened.</span></span> <span data-ttu-id="a7a20-160">Dovrebbe includere una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-160">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="a7a20-161">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a7a20-161">On this line, set the following values:</span></span>

    - <span data-ttu-id="a7a20-162">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a7a20-162">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="a7a20-163">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="a7a20-163">**Quantity:** *2*</span></span>

1. <span data-ttu-id="a7a20-164">Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-164">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="a7a20-165">Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.</span><span class="sxs-lookup"><span data-stu-id="a7a20-165">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="a7a20-166">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a7a20-166">Close the page.</span></span>
1. <span data-ttu-id="a7a20-167">Nella Scheda dettaglio **Righe ordine cliente**, selezionare **Aggiungi riga** per aggiungere un'altra riga all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a7a20-167">On the **Sales order lines** FastTab, select **Add line** to add another line to your sales order.</span></span> <span data-ttu-id="a7a20-168">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a7a20-168">On this line, set the following values:</span></span>

    - <span data-ttu-id="a7a20-169">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="a7a20-169">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="a7a20-170">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="a7a20-170">**Quantity:** *2*</span></span>

1. <span data-ttu-id="a7a20-171">Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-171">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="a7a20-172">Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.</span><span class="sxs-lookup"><span data-stu-id="a7a20-172">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="a7a20-173">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a7a20-173">Close the page.</span></span>
1. <span data-ttu-id="a7a20-174">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-174">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="a7a20-175">Ricevere messaggi informativi che mostrano l'ID ondata e l'ID spedizione creati dal rilascio.</span><span class="sxs-lookup"><span data-stu-id="a7a20-175">You receive informational messages that show the wave ID and shipment ID that were created from the release.</span></span> <span data-ttu-id="a7a20-176">Prendere nota dell'ID ondata.</span><span class="sxs-lookup"><span data-stu-id="a7a20-176">Make a note of the wave ID.</span></span>

### <a name="review-the-outbound-wave"></a><span data-ttu-id="a7a20-177">Esaminare l'ondata in uscita</span><span class="sxs-lookup"><span data-stu-id="a7a20-177">Review the outbound wave</span></span>

1. <span data-ttu-id="a7a20-178">Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-178">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="a7a20-179">Nella griglia, cercare l'ID ondata creata dal rilascio dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a7a20-179">In the grid, search for the wave ID that was created from the release of the sales order.</span></span>
1. <span data-ttu-id="a7a20-180">Selezionare l'ID ondata per visualizzare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="a7a20-180">Select the wave ID to view the details.</span></span>
1. <span data-ttu-id="a7a20-181">Nella Scheda dettaglio **Righe ondata**, assicurarsi che venga visualizzato un ID spedizione per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a7a20-181">On the **Wave lines** FastTab, make sure that a shipment ID is shown for the sales order.</span></span>

    > [!TIP]
    > <span data-ttu-id="a7a20-182">Se l'opzione **Elabora ondata al rilascio in magazzino** è impostata su *No* nella configurazione per il modello dell'ondata di spedizione, è necessario elaborare manualmente l'ondata selezionando **Processo** nella scheda **Ondata** del riquadro azioni per creare lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-182">If the **Process wave at release to warehouse** option is set to *No* in the setup for the shipping wave template, you must manually process the wave by selecting **Process** from the **Wave** tab on the Action Pane to create work.</span></span>

1. <span data-ttu-id="a7a20-183">Assicurarsi che l'ondata sia stata elaborata.</span><span class="sxs-lookup"><span data-stu-id="a7a20-183">Make sure that the wave has been processed.</span></span> <span data-ttu-id="a7a20-184">Questa elaborazione crea il lavoro richiesto.</span><span class="sxs-lookup"><span data-stu-id="a7a20-184">This processing creates the required work.</span></span>

### <a name="view-work-details-and-change-the-work-pool"></a><span data-ttu-id="a7a20-185">Visualizzare i dettagli del lavoro e modificare il pool di lavoro</span><span class="sxs-lookup"><span data-stu-id="a7a20-185">View work details and change the work pool</span></span>

<span data-ttu-id="a7a20-186">È possibile usare la pagina **Dettagli lavoro** per visualizzare il lavoro creato e gestire il pool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-186">You can use the **Work details** page to view the work that was created and to manage the work pool.</span></span>

1. <span data-ttu-id="a7a20-187">Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-187">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="a7a20-188">Selezionare la riga per il lavoro appena creato.</span><span class="sxs-lookup"><span data-stu-id="a7a20-188">Select the row for the work that was just created.</span></span> <span data-ttu-id="a7a20-189">La colonna **Numero ordine** mostrerà il numero dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a7a20-189">The **Order number** column will show the sales order number.</span></span>

    <span data-ttu-id="a7a20-190">Il campo **ID pool di lavoro** verrà impostato sull'ID del pool di lavoro impostato nel modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-190">The **Work pool ID** field will be set to the work pool ID that was set up in the work template.</span></span>

    > [!TIP]
    > <span data-ttu-id="a7a20-191">Se il campo **ID pool di lavoro** non è visibile, aggiungere la colonna alla griglia e quindi aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="a7a20-191">If you don't see the **Work pool ID** field, add the column to the grid, and then refresh the page.</span></span>

1. <span data-ttu-id="a7a20-192">Per modificare il pool di lavoro associato all'ID lavoro, nel riquadro azioni, nella scheda **Lavoro**, selezionare **Modifica ID pool di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="a7a20-192">To change the work pool that is associated with the work ID, on the Action Pane, on the **Work** tab, select **Change Work pool ID**.</span></span>
1. <span data-ttu-id="a7a20-193">Nella finestra di dialogo **Modifica pool di lavoro**, nella Scheda dettaglio **Parametri**, nel campo **ID pool di lavoro**, selezionare *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="a7a20-193">In the **Change work pool** dialog box, on the **Parameters** FastTab, in the **Work pool ID** field, select *CallCenter*.</span></span>
1. <span data-ttu-id="a7a20-194">Selezionare **OK** per applicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="a7a20-194">Select **OK** to apply your change.</span></span>
1. <span data-ttu-id="a7a20-195">Si noti che il valore del campo **ID pool di lavoro** è stato ora cambiato in *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="a7a20-195">Notice that the value of the **Work pool ID** field has now been changed to *CallCenter*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7a20-196">Quando viene visualizzata la finestra di dialogo **Modifica pool di lavoro**, il campo **ID pool di lavoro** potrebbe essere vuoto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a7a20-196">When the **Change work pool** dialog box appears, the **Work pool ID** field might be blank by default.</span></span> <span data-ttu-id="a7a20-197">Se il campo è vuoto quando si seleziona **OK** per applicare le modifiche, si rimuoverà il pool di lavoro completamente dal lavoro.</span><span class="sxs-lookup"><span data-stu-id="a7a20-197">If the field is blank when you select **OK** to apply changes, you will remove the work pool completely from the work.</span></span>
>
> <span data-ttu-id="a7a20-198">Oltre a cambiare pool di lavoro, è possibile utilizzare questa procedura per aggiungere un pool di lavoro a qualsiasi elemento di lavoro che non ne ha uno o per rimuovere un pool di lavoro da qualsiasi elemento di lavoro che ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="a7a20-198">In addition to switching work pools, you can use this procedure to add a work pool to any work item that doesn't have one, or to remove a work pool from any work item that does have one.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]