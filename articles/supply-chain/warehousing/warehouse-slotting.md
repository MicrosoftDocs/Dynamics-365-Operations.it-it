---
title: Assegnazione magazzino
description: Questo argomento fornisce informazioni sull'assegnazione magazzino. L'assegnazione magazzino consente di consolidare la domanda per articolo e unità di misura dagli ordini con stato Ordinato, Prenotato o Rilasciato. Aiuta i responsabili del magazzino a pianificare in modo intelligente le ubicazioni di prelievo prima di rilasciare ordini al magazzino e creare attività di prelievo.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: f6764f8bc082962af37d4775b6fe53d8704658eb
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597460"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="d53d5-105">Assegnazione magazzino</span><span class="sxs-lookup"><span data-stu-id="d53d5-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d53d5-106">L'assegnazione magazzino consente di consolidare la domanda per articolo e unità di misura dagli ordini con stato *Ordinato*, *Prenotato* o *Rilasciato*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-106">Warehouse slotting lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="d53d5-107">La domanda generata può quindi essere applicata alle ubicazioni che verranno utilizzate per il prelievo, in base a quantità, unità, dimensioni fisiche, ubicazioni fisse e altro.</span><span class="sxs-lookup"><span data-stu-id="d53d5-107">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="d53d5-108">Dopo aver stabilito il piano di assegnazione, è possibile creare un lavoro di rifornimento per portare la quantità appropriata di scorte in ciascuna ubicazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-108">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="d53d5-109">Questa funzionalità aiuta i responsabili del magazzino a pianificare in modo intelligente le ubicazioni di prelievo prima di rilasciare ordini al magazzino e creare attività di prelievo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-109">This functionality helps warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

## <a name="turn-on-the-warehouse-slotting-feature"></a><span data-ttu-id="d53d5-110">Attivare la funzione di assegnazione magazzino</span><span class="sxs-lookup"><span data-stu-id="d53d5-110">Turn on the warehouse slotting feature</span></span>

<span data-ttu-id="d53d5-111">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d53d5-111">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="d53d5-112">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="d53d5-112">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="d53d5-113">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d53d5-113">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="d53d5-114">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="d53d5-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="d53d5-115">**Nome funzionalità:** *Assegnazione magazzino*</span><span class="sxs-lookup"><span data-stu-id="d53d5-115">**Feature name:** *Warehouse slotting feature*</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="d53d5-116">Configurare l'assegnazione magazzino</span><span class="sxs-lookup"><span data-stu-id="d53d5-116">Set up warehouse slotting</span></span>

<span data-ttu-id="d53d5-117">Per utilizzare l'assegnazione magazzino, devi configurare gli elementi seguenti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d53d5-117">To use warehouse slotting, you must set up the following elements in your system.</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="d53d5-118">Creare livelli di unità di misura per l'assegnazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-118">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="d53d5-119">I livelli di unità di misura consentono di raggruppare più unità di misura ai fini dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-119">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="d53d5-120">Ad esempio, se vengono prelevate più dimensioni di scatole dalla stessa area di selezione delle scatole, è possibile creare un livello per tutte le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d53d5-120">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="d53d5-121">**È necessario creare una riga per ogni unità di misura che dovrebbe far parte del livello.**</span><span class="sxs-lookup"><span data-stu-id="d53d5-121">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="d53d5-122">Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Livelli di unità di misura assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-122">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="d53d5-123">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-123">Select **New**.</span></span>
1. <span data-ttu-id="d53d5-124">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-124">In the header, set the following values:</span></span>

    - <span data-ttu-id="d53d5-125">**Livello unità di misura:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="d53d5-125">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="d53d5-126">**Descrizione:** *Ogni pallet di scatole*</span><span class="sxs-lookup"><span data-stu-id="d53d5-126">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="d53d5-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-127">Select **Save**.</span></span>
1. <span data-ttu-id="d53d5-128">Nella Scheda dettaglio **Unità di misura**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="d53d5-128">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="d53d5-129">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-129">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-130">**Unità:** *Scatola*</span><span class="sxs-lookup"><span data-stu-id="d53d5-130">**Unit:** *Box*</span></span>
    - <span data-ttu-id="d53d5-131">**Descrizione:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-131">**Description:** Leave this field blank.</span></span> <span data-ttu-id="d53d5-132">Verrà compilato automaticamente quando salvi le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d53d5-132">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="d53d5-133">**Classe di unità:** *Quantità*</span><span class="sxs-lookup"><span data-stu-id="d53d5-133">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="d53d5-134">Seleziona **Nuova** per aggiungere una seconda riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="d53d5-134">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="d53d5-135">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-136">**Unità:** *unità*</span><span class="sxs-lookup"><span data-stu-id="d53d5-136">**Unit:** *ea*</span></span>
    - <span data-ttu-id="d53d5-137">**Descrizione:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-137">**Description:** Leave this field blank.</span></span> <span data-ttu-id="d53d5-138">Verrà compilato automaticamente quando salvi le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d53d5-138">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="d53d5-139">**Classe di unità:** *Quantità*</span><span class="sxs-lookup"><span data-stu-id="d53d5-139">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="d53d5-140">Seleziona **Nuova** per aggiungere una terza riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="d53d5-140">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="d53d5-141">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-142">**Unità:** *PALLET*</span><span class="sxs-lookup"><span data-stu-id="d53d5-142">**Unit:** *PL*</span></span>
    - <span data-ttu-id="d53d5-143">**Descrizione:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-143">**Description:** Leave this field blank.</span></span> <span data-ttu-id="d53d5-144">Verrà compilato automaticamente quando salvi le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d53d5-144">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="d53d5-145">**Classe di unità:** *Quantità*</span><span class="sxs-lookup"><span data-stu-id="d53d5-145">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="d53d5-146">Seleziona **Salva** per salvare il livello.</span><span class="sxs-lookup"><span data-stu-id="d53d5-146">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="d53d5-147">Creare un codice di direttiva per l'assegnazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-147">Create a directive code for slotting</span></span>

<span data-ttu-id="d53d5-148">È necessario selezionare il codice di direttiva che deve essere associato a un modello.</span><span class="sxs-lookup"><span data-stu-id="d53d5-148">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="d53d5-149">Vai a **Gestione magazzino \> Impostazioni \> Codici di direttiva**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-149">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="d53d5-150">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-150">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d53d5-151">Nel campo **Codice direttiva**, immetti *Assegnazione*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-151">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="d53d5-152">Nel campo **Descrizione direttiva**, immetti *Assegnazione*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-152">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="d53d5-153">Configurare modelli di assegnazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-153">Set up slotting templates</span></span>

<span data-ttu-id="d53d5-154">Ogni modello di assegnazione controlla il modo in cui le scorte vengono assegnate alle ubicazioni per un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="d53d5-154">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="d53d5-155">Ogni modello deve includere una riga per ciascuna specifica assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-155">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="d53d5-156">Utilizza le procedure in questa sezione per impostare i modelli di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-156">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="d53d5-157">Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-157">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="d53d5-158">Seleziona **Nuovo** per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="d53d5-158">Select **New** to create a template.</span></span>

<span data-ttu-id="d53d5-159">Successivamente, devi impostare l'intestazione del modello, le specifiche di assegnazione e le direttive di ubicazione, come spiegato nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d53d5-159">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span>

#### <a name="set-up-a-slotting-template-header"></a><span data-ttu-id="d53d5-160">Impostare un'intestazione del modello di assegnazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-160">Set up a slotting template header</span></span>

1. <span data-ttu-id="d53d5-161">Nell'intestazione del modello, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-161">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="d53d5-162">**Modello di assegnazione:** _61_</span><span class="sxs-lookup"><span data-stu-id="d53d5-162">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="d53d5-163">**Descrizione:** _61_</span><span class="sxs-lookup"><span data-stu-id="d53d5-163">**Description:** _61_</span></span>
    - <span data-ttu-id="d53d5-164">**Tipo di domanda:** *Ordine cliente*</span><span class="sxs-lookup"><span data-stu-id="d53d5-164">**Demand type:** *Sales order*</span></span>

        <span data-ttu-id="d53d5-165">Attualmente, l'unico tipo di domanda supportato è *Ordine cliente*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-165">Currently, *Sales order* is the only demand type that is supported.</span></span>

    - <span data-ttu-id="d53d5-166">**Strategia della domanda:** _Ordinato_</span><span class="sxs-lookup"><span data-stu-id="d53d5-166">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="d53d5-167">In questo campo sono disponibili i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-167">The following values are available in this field:</span></span>

        - <span data-ttu-id="d53d5-168">**Ordinato**: l'intera quantità ordinata nell'ordine cliente deve essere considerata domanda.</span><span class="sxs-lookup"><span data-stu-id="d53d5-168">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="d53d5-169">**Prenotata**: solo le quantità della riga ordine cliente prenotate (fisiche e ordinate) devono essere considerate domanda.</span><span class="sxs-lookup"><span data-stu-id="d53d5-169">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>

    - <span data-ttu-id="d53d5-170">**Magazzino:** _61_</span><span class="sxs-lookup"><span data-stu-id="d53d5-170">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="d53d5-171">**Consenti domanda ondata per utilizzare le quantità non prenotate:** _Sì_</span><span class="sxs-lookup"><span data-stu-id="d53d5-171">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="d53d5-172">Puoi inoltre specificare una query per restringere l'ambito della domanda che viene valutata.</span><span class="sxs-lookup"><span data-stu-id="d53d5-172">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="d53d5-173">Impostare le specifiche di assegnazione per ciascun modello</span><span class="sxs-lookup"><span data-stu-id="d53d5-173">Set up slotting specifications for each template</span></span>

<span data-ttu-id="d53d5-174">Per ogni modello creato, attieniti alla seguente procedura per aggiungere una riga per ciascuna specifica di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-174">For each template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="d53d5-175">Nella Scheda dettaglio **Dettagli modello di assegnazione**, seleziona **Nuova** per creare una riga di modello.</span><span class="sxs-lookup"><span data-stu-id="d53d5-175">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="d53d5-176">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-176">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-177">**Sequenza:** _1_</span><span class="sxs-lookup"><span data-stu-id="d53d5-177">**Sequence:** _1_</span></span>
    - <span data-ttu-id="d53d5-178">**Descrizione:** _Ubicazione fissa_</span><span class="sxs-lookup"><span data-stu-id="d53d5-178">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="d53d5-179">**Quantità minima:** _1_</span><span class="sxs-lookup"><span data-stu-id="d53d5-179">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="d53d5-180">Questo campo definisce la quantità minima di domanda richiesta per la riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-180">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="d53d5-181">**Quantità massima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="d53d5-181">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="d53d5-182">Questo campo definisce la quantità massima di domanda valida per la riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-182">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="d53d5-183">**Unità:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-183">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="d53d5-184">Questo campo definisce l'unità di misura a cui si riferiscono le quantità minima e massima.</span><span class="sxs-lookup"><span data-stu-id="d53d5-184">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="d53d5-185">**Livello unità di misura:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="d53d5-185">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="d53d5-186">Questo campo definisce le unità di misura della domanda valide per la riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-186">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="d53d5-187">Per ulteriori informazioni, vedi la sezione [Impostare livelli di unità di misura per l'assegnazione](#unit-tiers) descritta in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d53d5-187">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="d53d5-188">**Criteri assegnazione fascia:** _Consider qtà_</span><span class="sxs-lookup"><span data-stu-id="d53d5-188">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="d53d5-189">In questo campo sono disponibili i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-189">The following values are available in this field:</span></span>

        - <span data-ttu-id="d53d5-190">**Presumi vuoto**: questo sistema dovrebbe presumere che tutte le ubicazioni nell'area di prelievo siano vuote e non dovrebbe controllare tali ubicazioni per le scorte.</span><span class="sxs-lookup"><span data-stu-id="d53d5-190">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="d53d5-191">**Considera qtà**: il sistema dovrebbe controllar ele ubicazioni nell'area di prelievo per le scorte e ignorare tutte le ubicazioni che non sono vuote.</span><span class="sxs-lookup"><span data-stu-id="d53d5-191">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>

    - <span data-ttu-id="d53d5-192">**Codice direttiva:** _Assegnazione_</span><span class="sxs-lookup"><span data-stu-id="d53d5-192">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="d53d5-193">Questo campo definisce la direttiva di ubicazione utilizzata per trovare l'ubicazione di prelievo del lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="d53d5-193">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="d53d5-194">**Ubicazione di overflow:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-194">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="d53d5-195">Questo campo definisce l'ubicazione in cui viene effettuato l'inventario se non è possibile trovare un'ubicazione per la quantità durante l'elaborazione della riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-195">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="d53d5-196">**Consenti rallentamento:** _Sì_</span><span class="sxs-lookup"><span data-stu-id="d53d5-196">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="d53d5-197">Quando questa opzione è impostata su *Sì*, se una domanda non può essere assegnata, verrà creato un lavoro di spostamento per estrarre le scorte dalle ubicazioni in cui sono presenti , ma dove non è stata effettuata alcuna assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-197">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="d53d5-198">Il modello viene quindi eseguito nuovamente.</span><span class="sxs-lookup"><span data-stu-id="d53d5-198">The template is then run again.</span></span> <span data-ttu-id="d53d5-199">Questa volta, ignora le scorte nelle ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="d53d5-199">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="d53d5-200">Questa funzionalità funziona al meglio quando il campo **Criteri assegnazione fascia** è impostato su _Considera qtà_.</span><span class="sxs-lookup"><span data-stu-id="d53d5-200">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="d53d5-201">**Utilizzo ubicazioni fisse** _Solo ubicazioni fisse per il prodotto_</span><span class="sxs-lookup"><span data-stu-id="d53d5-201">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="d53d5-202">In questo campo sono disponibili i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-202">The following values are available in this field:</span></span>

        - <span data-ttu-id="d53d5-203">**Ubicazioni fisse e non fisse**: il sistema non dovrebbe essere limitato all'uso di ubicazioni fisse.</span><span class="sxs-lookup"><span data-stu-id="d53d5-203">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="d53d5-204">**Solo ubicazioni fisse per il prodotto**: il sistema deve effettuare assegnazioni solo in ubicazioni fisse per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="d53d5-204">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="d53d5-205">**Solo ubicazioni fisse per la variante prodotto**: il sistema deve effettuare assegnazioni solo in ubicazioni fisse per la variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="d53d5-205">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

1. <span data-ttu-id="d53d5-206">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-206">Select **Save**.</span></span>
1. <span data-ttu-id="d53d5-207">Seleziona **Nuova** per creare una seconda riga del modello.</span><span class="sxs-lookup"><span data-stu-id="d53d5-207">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="d53d5-208">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-209">**Sequenza:** _2_</span><span class="sxs-lookup"><span data-stu-id="d53d5-209">**Sequence:** _2_</span></span>
    - <span data-ttu-id="d53d5-210">**Descrizione:** _Altro_</span><span class="sxs-lookup"><span data-stu-id="d53d5-210">**Description:** _Other_</span></span>
    - <span data-ttu-id="d53d5-211">**Qtà minima:** _1_</span><span class="sxs-lookup"><span data-stu-id="d53d5-211">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="d53d5-212">**Qtà massima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="d53d5-212">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="d53d5-213">**Unità:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-213">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="d53d5-214">**Livello unità di misura:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="d53d5-214">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="d53d5-215">**Criteri assegnazione fascia:** _Consider qtà_</span><span class="sxs-lookup"><span data-stu-id="d53d5-215">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="d53d5-216">**Codice direttiva:** _Assegnazione_</span><span class="sxs-lookup"><span data-stu-id="d53d5-216">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="d53d5-217">**Ubicazione di overflow:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-217">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="d53d5-218">**Consenti rallentamento:** _Sì_</span><span class="sxs-lookup"><span data-stu-id="d53d5-218">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="d53d5-219">**Utilizza ubicazioni fisse:** seleziona _Ubicazioni fisse e non fisse_</span><span class="sxs-lookup"><span data-stu-id="d53d5-219">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="d53d5-220">Nella query per la seconda riga, dovrai ora specificare i criteri utilizzati per determinare in quali ubicazioni è possibile assegnare la domanda per quella riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-220">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="d53d5-221">Seleziona la riga in cui il campo **Sequenza** è impostato su *2*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-221">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="d53d5-222">Selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-222">Select **Edit query**.</span></span>
1. <span data-ttu-id="d53d5-223">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="d53d5-223">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="d53d5-224">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-224">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-225">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="d53d5-225">**Table:** *Locations*</span></span>
    - <span data-ttu-id="d53d5-226">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="d53d5-226">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="d53d5-227">**Campo:** *ID profilo ubicazione*</span><span class="sxs-lookup"><span data-stu-id="d53d5-227">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="d53d5-228">**Criteri:** *Pick-06* (seleziona il doppio segno più \[**++**\] nel campo per espandere l'elenco, quindi seleziona *Pick-06* - *Sito di prelievo 6* .)</span><span class="sxs-lookup"><span data-stu-id="d53d5-228">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="d53d5-229">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-229">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="d53d5-230">Imposta direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-230">Set up location directives</span></span>

<span data-ttu-id="d53d5-231">Almeno una direttiva di ubicazione deve essere impostata per supportare i prelievi di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-231">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="d53d5-232">Utilizza le procedure in questa sezione per impostare una nuova *direttiva di ubicazione di rifornimento* per i prelievi di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-232">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="d53d5-233">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-233">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="d53d5-234">Nel riquadro sinistro, nel campo **Tipo di ordine di lavoro**, seleziona *Rifornimento*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-234">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="d53d5-235">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d53d5-236">Nell'intestazione della nuova direttiva ubicazione, nel campo **Nome**, immetti *Prelievo di assegnazione 61*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-236">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="d53d5-237">Configurare la scheda dettaglio Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-237">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="d53d5-238">Nella Scheda dettaglio **Direttive ubicazione**, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="d53d5-238">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="d53d5-239">Accetta i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="d53d5-239">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="d53d5-240">**Tipo di lavoro:** _Prelievo_</span><span class="sxs-lookup"><span data-stu-id="d53d5-240">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="d53d5-241">**Sito:** _6_</span><span class="sxs-lookup"><span data-stu-id="d53d5-241">**Site:** _6_</span></span>
    - <span data-ttu-id="d53d5-242">**Magazzino:** _61_</span><span class="sxs-lookup"><span data-stu-id="d53d5-242">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="d53d5-243">**Codice direttiva:** _Assegnazione_</span><span class="sxs-lookup"><span data-stu-id="d53d5-243">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="d53d5-244">Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.</span><span class="sxs-lookup"><span data-stu-id="d53d5-244">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="d53d5-245">Configurare la Scheda dettaglio Righe</span><span class="sxs-lookup"><span data-stu-id="d53d5-245">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="d53d5-246">Nella Scheda dettaglio **Righe** seleziona **Nuova** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-246">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="d53d5-247">Nella nuova riga, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="d53d5-247">On the new line, set the following values.</span></span> <span data-ttu-id="d53d5-248">Accetta i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="d53d5-248">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="d53d5-249">**Da quantità:** _0_</span><span class="sxs-lookup"><span data-stu-id="d53d5-249">**From quantity:** _0_</span></span>
    - <span data-ttu-id="d53d5-250">**A quantità:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="d53d5-250">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="d53d5-251">Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="d53d5-251">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="d53d5-252">Configurare la scheda dettaglio Azioni direttiva ubicazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-252">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="d53d5-253">Nella Scheda dettaglio **Azioni direttiva ubicazione** seleziona **Nuova** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-253">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="d53d5-254">Nella nuova riga, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="d53d5-254">On the new line, set the following values.</span></span> <span data-ttu-id="d53d5-255">Accetta i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="d53d5-255">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="d53d5-256">**Nome:** _In blocco_</span><span class="sxs-lookup"><span data-stu-id="d53d5-256">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="d53d5-257">**Strategia:** _Nessuna_</span><span class="sxs-lookup"><span data-stu-id="d53d5-257">**Strategy:** _None_</span></span>

1. <span data-ttu-id="d53d5-258">Seleziona **Salva** per rendere il pulsante **Modifica query** disponibile.</span><span class="sxs-lookup"><span data-stu-id="d53d5-258">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="d53d5-259">Modificare la query</span><span class="sxs-lookup"><span data-stu-id="d53d5-259">Edit the query</span></span>

1. <span data-ttu-id="d53d5-260">Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-260">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="d53d5-261">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="d53d5-261">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="d53d5-262">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-262">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-263">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="d53d5-263">**Table:** *Locations*</span></span>
    - <span data-ttu-id="d53d5-264">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="d53d5-264">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="d53d5-265">**Campo:** *ID zona*</span><span class="sxs-lookup"><span data-stu-id="d53d5-265">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="d53d5-266">**Criteri:** *In blocco* (seleziona il doppio segno più \[**++**\] nel campo per espandere l'elenco, quindi seleziona *In blocco*.)</span><span class="sxs-lookup"><span data-stu-id="d53d5-266">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="d53d5-267">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-267">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="d53d5-268">Scenario</span><span class="sxs-lookup"><span data-stu-id="d53d5-268">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="d53d5-269">Impostare lo scenario</span><span class="sxs-lookup"><span data-stu-id="d53d5-269">Set up the scenario</span></span>

<span data-ttu-id="d53d5-270">Per questo scenario, utilizzare i dati di esempio incorporati e creare i record descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-270">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="d53d5-271">Utilizzare i dati di esempio USMF</span><span class="sxs-lookup"><span data-stu-id="d53d5-271">Use the USMF sample data</span></span>

<span data-ttu-id="d53d5-272">Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="d53d5-272">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="d53d5-273">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="d53d5-273">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="d53d5-274">Creare domanda</span><span class="sxs-lookup"><span data-stu-id="d53d5-274">Create demand</span></span>

<span data-ttu-id="d53d5-275">Seguire questi passaggi per creare la domanda a cui applicare l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-275">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="d53d5-276">Vai a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-276">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="d53d5-277">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="d53d5-277">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="d53d5-278">Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona _US-007_.</span><span class="sxs-lookup"><span data-stu-id="d53d5-278">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="d53d5-279">Nel campo **Magazzino** selezionare _61_.</span><span class="sxs-lookup"><span data-stu-id="d53d5-279">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="d53d5-280">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-280">Select **OK**.</span></span>
1. <span data-ttu-id="d53d5-281">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="d53d5-281">The new sales order is opened.</span></span> <span data-ttu-id="d53d5-282">Include una riga vuota nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-282">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="d53d5-283">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-283">On this line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-284">**Articolo:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="d53d5-284">**Item:** _L0101_</span></span>
    - <span data-ttu-id="d53d5-285">**Quantità:** _20_</span><span class="sxs-lookup"><span data-stu-id="d53d5-285">**Quantity:** _20_</span></span>

1. <span data-ttu-id="d53d5-286">Seleziona **Aggiungi riga** per aggiungere una nuova riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-286">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="d53d5-287">**Articolo:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="d53d5-287">**Item:** _T0100_</span></span>
    - <span data-ttu-id="d53d5-288">**Quantità:** _8_</span><span class="sxs-lookup"><span data-stu-id="d53d5-288">**Quantity:** _8_</span></span>

1. <span data-ttu-id="d53d5-289">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-289">Select **Save**.</span></span>
1. <span data-ttu-id="d53d5-290">Seleziona **Nuovo** per creare un secondo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="d53d5-290">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="d53d5-291">Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona _US-008_.</span><span class="sxs-lookup"><span data-stu-id="d53d5-291">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="d53d5-292">Nel campo **Magazzino** selezionare _61_.</span><span class="sxs-lookup"><span data-stu-id="d53d5-292">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="d53d5-293">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="d53d5-293">The new sales order is opened.</span></span> <span data-ttu-id="d53d5-294">Include una riga vuota nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-294">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="d53d5-295">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d53d5-295">On this line, set the following values:</span></span>

    - <span data-ttu-id="d53d5-296">**Articolo:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="d53d5-296">**Item:** _T0100_</span></span>
    - <span data-ttu-id="d53d5-297">**Quantità:** _1_</span><span class="sxs-lookup"><span data-stu-id="d53d5-297">**Quantity:** _1_</span></span>

1. <span data-ttu-id="d53d5-298">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-298">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="d53d5-299">Eseguire un tipico scenario di assegnazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-299">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="d53d5-300">Dopo che tutti gli elementi dei prerequisiti sono presenti, come descritto nella sezione precedente, sei pronto per provare la funzione utilizzando ogni esercizio in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-300">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="d53d5-301">Genera domanda</span><span class="sxs-lookup"><span data-stu-id="d53d5-301">Generate demand</span></span>

1. <span data-ttu-id="d53d5-302">Vai a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli assegnazione** e seleziona il modello di assegnazione che hai creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d53d5-302">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="d53d5-303">Nel riquadro azioni, seleziona **Genera domanda**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-303">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="d53d5-304">Questo comando valuta tutta la domanda presente nel sistema e corrisponde alla query del modello di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-304">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="d53d5-305">La domanda totale per tutti gli ordini viene quindi consolidata su una riga per quantità/unità di misura.</span><span class="sxs-lookup"><span data-stu-id="d53d5-305">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="d53d5-306">Un messaggio informativo appare quando il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="d53d5-306">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="d53d5-307">Domanda di assegnazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-307">Slotting demand</span></span>

<span data-ttu-id="d53d5-308">La *domanda di assegnazione* mostra i risultati della generazione della domanda, in base all'impostazione del modello di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-308">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="d53d5-309">Nel riquadro azioni seleziona **Domanda di assegnazione** per visualizzare i risultati dal comando **Genera domanda**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-309">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="d53d5-310">Le righe nella domanda di assegnazione possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="d53d5-310">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="d53d5-311">Puoi eliminare una riga, aggiungere una nuova riga o modificare i dettagli della riga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-311">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="d53d5-312">Puoi modificare manualmente la domanda oppure importarla da un sistema esterno utilizzando la gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d53d5-312">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="d53d5-313">Qualunque sia il contenuto della domanda di assegnazione verrà utilizzata nel passaggio successivo, indipendentemente da dove provenga.</span><span class="sxs-lookup"><span data-stu-id="d53d5-313">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="d53d5-314">Rileva la richiesta</span><span class="sxs-lookup"><span data-stu-id="d53d5-314">Locate demand</span></span>

<span data-ttu-id="d53d5-315">Dopo che la domanda è stata generata, è necessario utilizzare il comando **Trova la domanda** per generare il *piano di assegnazione*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-315">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="d53d5-316">Nel riquadro azioni, seleziona **Trova domanda**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-316">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="d53d5-317">Viene eseguito il processo di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-317">The slotting process runs.</span></span> <span data-ttu-id="d53d5-318">Un messaggio informativo appare quando il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="d53d5-318">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="d53d5-319">Piano di assegnazione</span><span class="sxs-lookup"><span data-stu-id="d53d5-319">Slotting plan</span></span>

<span data-ttu-id="d53d5-320">Il piano di assegnazione mostra l'ubicazione a cui è stato assegnato ciascun articolo/quantità, se è stato utilizzato l'overflow, se è stato creato il lavoro di rallentamento e la riga del modello utilizzata.</span><span class="sxs-lookup"><span data-stu-id="d53d5-320">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="d53d5-321">**Qualsiasi domanda che non è stato possibile assegnare è evidenziata in rosso.**</span><span class="sxs-lookup"><span data-stu-id="d53d5-321">**Any demand that could not be slotted is highlighted in red.**</span></span>

- <span data-ttu-id="d53d5-322">Nel riquadro azioni seleziona **Piano di assegnazione** per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="d53d5-322">On the Action Pane, select **Slotting plan** to view the results.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="d53d5-323">Creare rifornimento</span><span class="sxs-lookup"><span data-stu-id="d53d5-323">Create replenishment</span></span>

<span data-ttu-id="d53d5-324">Dopo aver creato il piano di assegnazione, è necessario creare il *lavoro di rifornimento*, in base al piano.</span><span class="sxs-lookup"><span data-stu-id="d53d5-324">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="d53d5-325">Nel riquadro azioni seleziona **Esegui rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-325">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="d53d5-326">Un messaggio informativo appare quando il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="d53d5-326">An informational message appears when the process is completed.</span></span> <span data-ttu-id="d53d5-327">Questo messaggio indica il numero di intestazioni create per l'ID build di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d53d5-327">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="d53d5-328">Le direttive di ubicazione che verranno utilizzate sono identificate in base al codice della direttiva specificato su ciascuna riga del modello.</span><span class="sxs-lookup"><span data-stu-id="d53d5-328">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="d53d5-329">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="d53d5-329">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="d53d5-330">Configurare l'assegnazione automatica</span><span class="sxs-lookup"><span data-stu-id="d53d5-330">Set up automatic slotting</span></span>

<span data-ttu-id="d53d5-331">Dopo aver inserito tutti gli elementi richiesti, è possibile impostare l'assegnazione per l'esecuzione automatica seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d53d5-331">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="d53d5-332">Vai a **Gestione magazzino \> Rifornimento \> Esegui assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="d53d5-332">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="d53d5-333">Specifica le fasi di assegnazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d53d5-333">Specify the slotting steps to run.</span></span> <span data-ttu-id="d53d5-334">Seleziona una o più delle seguenti fasi di assegnazione:</span><span class="sxs-lookup"><span data-stu-id="d53d5-334">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="d53d5-335">Genera domanda</span><span class="sxs-lookup"><span data-stu-id="d53d5-335">Generate demand</span></span>
    - <span data-ttu-id="d53d5-336">Rileva la richiesta</span><span class="sxs-lookup"><span data-stu-id="d53d5-336">Locate demand</span></span>
    - <span data-ttu-id="d53d5-337">Crea lavoro di rifornimento</span><span class="sxs-lookup"><span data-stu-id="d53d5-337">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="d53d5-338">I passaggi di assegnazione sono progressivi.</span><span class="sxs-lookup"><span data-stu-id="d53d5-338">The slotting steps are progressive.</span></span> <span data-ttu-id="d53d5-339">Se vuoi selezionare *Trova domanda*, devi prima selezionare *Genera domanda*.</span><span class="sxs-lookup"><span data-stu-id="d53d5-339">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="d53d5-340">Specifica il modello di assegnazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d53d5-340">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="d53d5-341">Imposta la ricorrenza per l'esecuzione automatica, se lo desideri.</span><span class="sxs-lookup"><span data-stu-id="d53d5-341">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="d53d5-342">Per gli esercizi nello scenario, **non** impostare l'assegnazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d53d5-342">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
