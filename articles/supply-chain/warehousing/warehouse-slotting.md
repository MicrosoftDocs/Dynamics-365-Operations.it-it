---
title: Assegnazione magazzino
description: Questo argomento fornisce informazioni sull'assegnazione magazzino. L'assegnazione magazzino consente di consolidare la domanda per articolo e unità di misura dagli ordini con stato Ordinato, Prenotato o Rilasciato. Aiuta i responsabili del magazzino a pianificare in modo intelligente le ubicazioni di prelievo prima di rilasciare ordini al magazzino e creare attività di prelievo.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0851af976dd73b7f13372880587187f546091bec
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248597"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="b90cd-105">Assegnazione magazzino</span><span class="sxs-lookup"><span data-stu-id="b90cd-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b90cd-106">Diverse funzionalità di assegnazione magazzino sono disponibili per i responsabili del magazzino per pianificare in modo intelligente le ubicazioni di prelievo prima di rilasciare ordini al magazzino e creare attività di prelievo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="b90cd-107">La *funzionalità di assegnazione magazzino* consente di consolidare la domanda per articolo e unità di misura dagli ordini con stato *Ordinato*, *Prenotato* o *Rilasciato*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="b90cd-108">La domanda generata può quindi essere applicata alle ubicazioni che verranno utilizzate per il prelievo, in base a quantità, unità, dimensioni fisiche, ubicazioni fisse e altro.</span><span class="sxs-lookup"><span data-stu-id="b90cd-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="b90cd-109">Dopo aver stabilito il piano di assegnazione, è possibile creare un lavoro di rifornimento per portare la quantità appropriata di scorte in ciascuna ubicazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="b90cd-110">La funzionalità *Assegnazione magazzino per ordini di trasferimento* consente ai responsabili del magazzino di rifornire le ubicazioni di prelievo, in base alla domanda degli ordini di trasferimento non ancora rilasciati al magazzino.</span><span class="sxs-lookup"><span data-stu-id="b90cd-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="b90cd-111">Assicura che le ubicazioni di prelievo includano tutti gli articoli necessari per gli ordini di trasferimento dopo che sono stati rilasciati al magazzino.</span><span class="sxs-lookup"><span data-stu-id="b90cd-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="b90cd-112">Questa funzione richiede anche l'attivazione della *funzionalità di assegnazione magazzino*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="b90cd-113">La funzione *Allocazione dell'assegnazione di magazzino migliorata* aggiunge un'opzione per le righe del modello utilizzate dalla *funzione di assegnazione magazzino*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="b90cd-114">L'opzione consente al sistema di considerare le scorte disponibili esistenti in un'ubicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="b90cd-115">Pertanto, potrebbero essere generati meno rifornimenti per l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="b90cd-116">La funzione *Allocazione dell'assegnazione di magazzino migliorata* richiede anche l'attivazione della *funzione di assegnazione magazzino*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="b90cd-117">Opzionalmente può essere utilizzato insieme alla funzione *Assegnazione magazzino per ordini di trasferimento*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="b90cd-118">Attivare le funzioni di assegnazione magazzino</span><span class="sxs-lookup"><span data-stu-id="b90cd-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="b90cd-119">Prima di poter utilizzare queste funzionalità, è necessario attivarle nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b90cd-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="b90cd-120">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle funzionalità e attivarle se sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="b90cd-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="b90cd-121">Attivare le seguenti funzionalità come richiesto:</span><span class="sxs-lookup"><span data-stu-id="b90cd-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="b90cd-122">Funzionalità di assegnazione magazzino</span><span class="sxs-lookup"><span data-stu-id="b90cd-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="b90cd-123">Assegnazione magazzino per ordini di trasferimento</span><span class="sxs-lookup"><span data-stu-id="b90cd-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b90cd-124">La *funzione di assegnazione magazzino* deve essere attivata prima di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="b90cd-125">Allocazione dell'assegnazione di magazzino migliorata</span><span class="sxs-lookup"><span data-stu-id="b90cd-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b90cd-126">La *funzione di assegnazione magazzino* deve essere attivata prima di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="b90cd-127">Configurare l'assegnazione magazzino</span><span class="sxs-lookup"><span data-stu-id="b90cd-127">Set up warehouse slotting</span></span>

<span data-ttu-id="b90cd-128">Per utilizzare l'assegnazione magazzino, devi configurare gli elementi seguenti nel sistema:</span><span class="sxs-lookup"><span data-stu-id="b90cd-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="b90cd-129">Livelli unità di misura assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="b90cd-130">Codici direttiva</span><span class="sxs-lookup"><span data-stu-id="b90cd-130">Directive codes</span></span>
- <span data-ttu-id="b90cd-131">Modelli di assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-131">Slotting templates</span></span>
- <span data-ttu-id="b90cd-132">Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="b90cd-133">Creare livelli di unità di misura per l'assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="b90cd-134">I livelli di unità di misura consentono di raggruppare più unità di misura ai fini dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="b90cd-135">Ad esempio, se vengono prelevate più dimensioni di scatole dalla stessa area di selezione delle scatole, è possibile creare un livello per tutte le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b90cd-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="b90cd-136">**È necessario creare una riga per ogni unità di misura che dovrebbe far parte del livello.**</span><span class="sxs-lookup"><span data-stu-id="b90cd-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="b90cd-137">Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Livelli di unità di misura assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="b90cd-138">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-138">Select **New**.</span></span>
1. <span data-ttu-id="b90cd-139">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="b90cd-140">**Livello unità di misura:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="b90cd-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="b90cd-141">**Descrizione:** *Ogni pallet di scatole*</span><span class="sxs-lookup"><span data-stu-id="b90cd-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="b90cd-142">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-142">Select **Save**.</span></span>
1. <span data-ttu-id="b90cd-143">Nella Scheda dettaglio **Unità di misura**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b90cd-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b90cd-144">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-145">**Unità:** *Scatola*</span><span class="sxs-lookup"><span data-stu-id="b90cd-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="b90cd-146">**Descrizione:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="b90cd-147">Verrà compilato automaticamente quando salvi le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b90cd-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="b90cd-148">**Classe di unità:** *Quantità*</span><span class="sxs-lookup"><span data-stu-id="b90cd-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="b90cd-149">Seleziona **Nuova** per aggiungere una seconda riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b90cd-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="b90cd-150">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-151">**Unità:** *unità*</span><span class="sxs-lookup"><span data-stu-id="b90cd-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="b90cd-152">**Descrizione:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="b90cd-153">Verrà compilato automaticamente quando salvi le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b90cd-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="b90cd-154">**Classe di unità:** *Quantità*</span><span class="sxs-lookup"><span data-stu-id="b90cd-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="b90cd-155">Seleziona **Nuova** per aggiungere una terza riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b90cd-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="b90cd-156">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-157">**Unità:** *PALLET*</span><span class="sxs-lookup"><span data-stu-id="b90cd-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="b90cd-158">**Descrizione:** lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="b90cd-159">Verrà compilato automaticamente quando salvi le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b90cd-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="b90cd-160">**Classe di unità:** *Quantità*</span><span class="sxs-lookup"><span data-stu-id="b90cd-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="b90cd-161">Seleziona **Salva** per salvare il livello.</span><span class="sxs-lookup"><span data-stu-id="b90cd-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="b90cd-162">Creare un codice di direttiva per l'assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-162">Create a directive code for slotting</span></span>

<span data-ttu-id="b90cd-163">È necessario selezionare il codice di direttiva che deve essere associato a un modello.</span><span class="sxs-lookup"><span data-stu-id="b90cd-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="b90cd-164">Vai a **Gestione magazzino \> Impostazioni \> Codici di direttiva**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="b90cd-165">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b90cd-166">Nel campo **Codice direttiva**, immetti *Assegnazione*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="b90cd-167">Nel campo **Descrizione direttiva**, immetti *Assegnazione*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="b90cd-168">Configurare modelli di assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-168">Set up slotting templates</span></span>

<span data-ttu-id="b90cd-169">Ogni modello di assegnazione controlla il modo in cui le scorte vengono assegnate alle ubicazioni per un magazzino specifico.</span><span class="sxs-lookup"><span data-stu-id="b90cd-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="b90cd-170">Ogni modello deve includere una riga per ciascuna specifica assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="b90cd-171">Utilizza le procedure in questa sezione per impostare i modelli di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="b90cd-172">Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="b90cd-173">Seleziona **Nuovo** per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="b90cd-173">Select **New** to create a template.</span></span>

<span data-ttu-id="b90cd-174">Successivamente, devi impostare l'intestazione del modello, le specifiche di assegnazione e le direttive di ubicazione, come spiegato nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b90cd-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="b90cd-175">L'impostazione per l'assegnazione per ordini di trasferimento è simile a quella per l'assegnazione per ordini cliente, ma il campo **Tipo di domanda** è impostato su *Ordini di trasferimento* anziché *Ordine cliente*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="b90cd-176">Impostare l'intestazione per un modello di assegnazione ordini cliente</span><span class="sxs-lookup"><span data-stu-id="b90cd-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="b90cd-177">Nell'intestazione del modello, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="b90cd-178">**Modello di assegnazione:** _61_</span><span class="sxs-lookup"><span data-stu-id="b90cd-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="b90cd-179">**Descrizione:** _61_</span><span class="sxs-lookup"><span data-stu-id="b90cd-179">**Description:** _61_</span></span>
    - <span data-ttu-id="b90cd-180">**Tipo di domanda:** *Ordine cliente*</span><span class="sxs-lookup"><span data-stu-id="b90cd-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="b90cd-181">Attualmente, *Ordini cliente* e *Ordini di trasferimento* sono gli unici tipi di domanda supportati.</span><span class="sxs-lookup"><span data-stu-id="b90cd-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="b90cd-182">È possibile selezionare *Ordini di trasferimento* solo se la funzionalità *Assegnazione magazzino per ordini di trasferimento* è attivata.</span><span class="sxs-lookup"><span data-stu-id="b90cd-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="b90cd-183">**Strategia della domanda:** _Ordinato_</span><span class="sxs-lookup"><span data-stu-id="b90cd-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="b90cd-184">In questo campo sono disponibili i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="b90cd-185">**Ordinato**: l'intera quantità ordinata nell'ordine cliente deve essere considerata domanda.</span><span class="sxs-lookup"><span data-stu-id="b90cd-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="b90cd-186">**Prenotata**: solo le quantità della riga ordine cliente prenotate (fisiche e ordinate) devono essere considerate domanda.</span><span class="sxs-lookup"><span data-stu-id="b90cd-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="b90cd-187">**Rilasciato** - La quantità rilasciata deve essere considerata come domanda.</span><span class="sxs-lookup"><span data-stu-id="b90cd-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="b90cd-188">**Magazzino:** _61_</span><span class="sxs-lookup"><span data-stu-id="b90cd-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="b90cd-189">**Consenti domanda ondata per utilizzare le quantità non prenotate:** _Sì_</span><span class="sxs-lookup"><span data-stu-id="b90cd-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="b90cd-190">Puoi inoltre specificare una query per restringere l'ambito della domanda che viene valutata.</span><span class="sxs-lookup"><span data-stu-id="b90cd-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="b90cd-191">Impostare le specifiche di assegnazione per ciascun modello</span><span class="sxs-lookup"><span data-stu-id="b90cd-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="b90cd-192">Per ogni modello di ordine cliente creato, attenersi alla seguente procedura per aggiungere una riga per ciascuna specifica di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="b90cd-193">Nella Scheda dettaglio **Dettagli modello di assegnazione**, seleziona **Nuova** per creare una riga di modello.</span><span class="sxs-lookup"><span data-stu-id="b90cd-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="b90cd-194">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-195">**Sequenza:** _1_</span><span class="sxs-lookup"><span data-stu-id="b90cd-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="b90cd-196">**Descrizione:** _Ubicazione fissa_</span><span class="sxs-lookup"><span data-stu-id="b90cd-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="b90cd-197">**Quantità minima:** _1_</span><span class="sxs-lookup"><span data-stu-id="b90cd-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="b90cd-198">Questo campo definisce la quantità minima di domanda richiesta per la riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="b90cd-199">**Quantità massima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="b90cd-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="b90cd-200">Questo campo definisce la quantità massima di domanda valida per la riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="b90cd-201">**Unità:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="b90cd-202">Questo campo definisce l'unità di misura a cui si riferiscono le quantità minima e massima.</span><span class="sxs-lookup"><span data-stu-id="b90cd-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="b90cd-203">**Livello unità di misura:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="b90cd-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="b90cd-204">Questo campo definisce le unità di misura della domanda valide per la riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="b90cd-205">Per ulteriori informazioni, vedi la sezione [Impostare livelli di unità di misura per l'assegnazione](#unit-tiers) descritta in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b90cd-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="b90cd-206">**Criteri assegnazione fascia:** _Consider qtà_</span><span class="sxs-lookup"><span data-stu-id="b90cd-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="b90cd-207">In questo campo sono disponibili i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="b90cd-208">**Presumi vuoto**: questo sistema dovrebbe presumere che tutte le ubicazioni nell'area di prelievo siano vuote e non dovrebbe controllare tali ubicazioni per le scorte.</span><span class="sxs-lookup"><span data-stu-id="b90cd-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="b90cd-209">**Considera qtà**: il sistema dovrebbe controllar ele ubicazioni nell'area di prelievo per le scorte e ignorare tutte le ubicazioni che non sono vuote.</span><span class="sxs-lookup"><span data-stu-id="b90cd-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="b90cd-210">**Considera scorte** - Il sistema verifica se un'ubicazione di destinazione contiene le quantità non prenotate per l'articolo nella riga di domanda.</span><span class="sxs-lookup"><span data-stu-id="b90cd-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="b90cd-211">Se la quantità è sufficiente a soddisfare almeno un'unità della riga di domanda, il record del piano di assegnazione generato viene ridotto della quantità disponibile.</span><span class="sxs-lookup"><span data-stu-id="b90cd-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="b90cd-212">Ad esempio, se la domanda è di 10 casi e un caso è disponibile, la domanda individuata sarà di nove casi.</span><span class="sxs-lookup"><span data-stu-id="b90cd-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="b90cd-213">Se la domanda è di 10 casi e un caso è disponibile, la domanda individuata sarà di 10 casi.</span><span class="sxs-lookup"><span data-stu-id="b90cd-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="b90cd-214">Questo valore è disponibile solo quando la funzionalità *Allocazione dell'assegnazione di magazzino migliorata* è attivata.</span><span class="sxs-lookup"><span data-stu-id="b90cd-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="b90cd-215">**Codice direttiva:** _Assegnazione_</span><span class="sxs-lookup"><span data-stu-id="b90cd-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="b90cd-216">Questo campo definisce la direttiva di ubicazione utilizzata per trovare l'ubicazione di prelievo del lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="b90cd-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="b90cd-217">**Ubicazione di overflow:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="b90cd-218">Questo campo definisce l'ubicazione in cui viene effettuato l'inventario se non è possibile trovare un'ubicazione per la quantità durante l'elaborazione della riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="b90cd-219">**Consenti rallentamento:** _Sì_</span><span class="sxs-lookup"><span data-stu-id="b90cd-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="b90cd-220">Quando questa opzione è impostata su *Sì*, se una domanda non può essere assegnata, verrà creato un lavoro di spostamento per estrarre le scorte dalle ubicazioni in cui sono presenti , ma dove non è stata effettuata alcuna assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="b90cd-221">Il modello viene quindi eseguito nuovamente.</span><span class="sxs-lookup"><span data-stu-id="b90cd-221">The template is then run again.</span></span> <span data-ttu-id="b90cd-222">Questa volta, ignora le scorte nelle ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="b90cd-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="b90cd-223">Questa funzionalità funziona al meglio quando il campo **Criteri assegnazione fascia** è impostato su _Considera qtà_.</span><span class="sxs-lookup"><span data-stu-id="b90cd-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="b90cd-224">**Utilizzo ubicazioni fisse** _Solo ubicazioni fisse per il prodotto_</span><span class="sxs-lookup"><span data-stu-id="b90cd-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="b90cd-225">In questo campo sono disponibili i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="b90cd-226">**Ubicazioni fisse e non fisse**: il sistema non dovrebbe essere limitato all'uso di ubicazioni fisse.</span><span class="sxs-lookup"><span data-stu-id="b90cd-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="b90cd-227">**Solo ubicazioni fisse per il prodotto**: il sistema deve effettuare assegnazioni solo in ubicazioni fisse per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="b90cd-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="b90cd-228">**Solo ubicazioni fisse per la variante prodotto**: il sistema deve effettuare assegnazioni solo in ubicazioni fisse per la variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="b90cd-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="b90cd-229">Se il modello di assegnazione contiene almeno una riga in cui il campo **Criteri assegnazione fascia** è impostato su *Considera scorte*, i rallentamenti non sono più consentiti per nessuna riga del modello.</span><span class="sxs-lookup"><span data-stu-id="b90cd-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="b90cd-230">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-230">Select **Save**.</span></span>
1. <span data-ttu-id="b90cd-231">Seleziona **Nuova** per creare una seconda riga del modello.</span><span class="sxs-lookup"><span data-stu-id="b90cd-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="b90cd-232">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-233">**Sequenza:** _2_</span><span class="sxs-lookup"><span data-stu-id="b90cd-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="b90cd-234">**Descrizione:** _Altro_</span><span class="sxs-lookup"><span data-stu-id="b90cd-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="b90cd-235">**Qtà minima:** _1_</span><span class="sxs-lookup"><span data-stu-id="b90cd-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="b90cd-236">**Qtà massima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="b90cd-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="b90cd-237">**Unità:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="b90cd-238">**Livello unità di misura:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="b90cd-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="b90cd-239">**Criteri assegnazione fascia:** _Consider qtà_</span><span class="sxs-lookup"><span data-stu-id="b90cd-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="b90cd-240">**Codice direttiva:** _Assegnazione_</span><span class="sxs-lookup"><span data-stu-id="b90cd-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="b90cd-241">**Ubicazione di overflow:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="b90cd-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="b90cd-242">**Consenti rallentamento:** _Sì_</span><span class="sxs-lookup"><span data-stu-id="b90cd-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="b90cd-243">**Utilizza ubicazioni fisse:** seleziona _Ubicazioni fisse e non fisse_</span><span class="sxs-lookup"><span data-stu-id="b90cd-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="b90cd-244">Nella query per la seconda riga, dovrai ora specificare i criteri utilizzati per determinare in quali ubicazioni è possibile assegnare la domanda per quella riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="b90cd-245">Seleziona la riga in cui il campo **Sequenza** è impostato su *2*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="b90cd-246">Selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="b90cd-247">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b90cd-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="b90cd-248">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-249">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b90cd-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="b90cd-250">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b90cd-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="b90cd-251">**Campo:** *ID profilo ubicazione*</span><span class="sxs-lookup"><span data-stu-id="b90cd-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="b90cd-252">**Criteri:** *Pick-06* (seleziona il doppio segno più \[**++**\] nel campo per espandere l'elenco, quindi seleziona *Pick-06* - *Sito di prelievo 6* .)</span><span class="sxs-lookup"><span data-stu-id="b90cd-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="b90cd-253">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="b90cd-254">Imposta direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-254">Set up location directives</span></span>

<span data-ttu-id="b90cd-255">Almeno una direttiva di ubicazione deve essere impostata per supportare i prelievi di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="b90cd-256">Utilizza le procedure in questa sezione per impostare una nuova *direttiva di ubicazione di rifornimento* per i prelievi di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="b90cd-257">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b90cd-258">Nel riquadro sinistro, nel campo **Tipo di ordine di lavoro**, seleziona *Rifornimento*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="b90cd-259">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b90cd-260">Nell'intestazione della nuova direttiva ubicazione, nel campo **Nome**, immetti *Prelievo di assegnazione 61*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="b90cd-261">Nel campo **Numero sequenza** accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b90cd-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="b90cd-262">Configurare la scheda dettaglio Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="b90cd-263">Nella Scheda dettaglio **Direttive ubicazione**, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="b90cd-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="b90cd-264">Accetta i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="b90cd-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="b90cd-265">**Tipo di lavoro:** _Prelievo_</span><span class="sxs-lookup"><span data-stu-id="b90cd-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="b90cd-266">**Sito:** _6_</span><span class="sxs-lookup"><span data-stu-id="b90cd-266">**Site:** _6_</span></span>
    - <span data-ttu-id="b90cd-267">**Magazzino:** _61_</span><span class="sxs-lookup"><span data-stu-id="b90cd-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="b90cd-268">**Codice direttiva:** _Assegnazione_</span><span class="sxs-lookup"><span data-stu-id="b90cd-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="b90cd-269">Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b90cd-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="b90cd-270">Configurare la Scheda dettaglio Righe</span><span class="sxs-lookup"><span data-stu-id="b90cd-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="b90cd-271">Nella Scheda dettaglio **Righe** seleziona **Nuova** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="b90cd-272">Nella nuova riga, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="b90cd-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="b90cd-273">**Da quantità:** _0_</span><span class="sxs-lookup"><span data-stu-id="b90cd-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="b90cd-274">**A quantità:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="b90cd-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="b90cd-275">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="b90cd-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="b90cd-276">Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b90cd-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="b90cd-277">Configurare la scheda dettaglio Azioni direttiva ubicazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="b90cd-278">Nella Scheda dettaglio **Azioni direttiva ubicazione** seleziona **Nuova** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="b90cd-279">Nella nuova riga, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="b90cd-279">On the new line, set the following values.</span></span> <span data-ttu-id="b90cd-280">Accetta i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="b90cd-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="b90cd-281">**Numero sequenza:** accetta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b90cd-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="b90cd-282">**Nome:** _In blocco_</span><span class="sxs-lookup"><span data-stu-id="b90cd-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="b90cd-283">**Strategia:** _Nessuna_</span><span class="sxs-lookup"><span data-stu-id="b90cd-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="b90cd-284">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="b90cd-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="b90cd-285">Seleziona **Salva** per rendere il pulsante **Modifica query** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b90cd-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="b90cd-286">Modificare la query</span><span class="sxs-lookup"><span data-stu-id="b90cd-286">Edit the query</span></span>

1. <span data-ttu-id="b90cd-287">Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="b90cd-288">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="b90cd-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="b90cd-289">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-290">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b90cd-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="b90cd-291">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="b90cd-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="b90cd-292">**Campo:** *ID zona*</span><span class="sxs-lookup"><span data-stu-id="b90cd-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="b90cd-293">**Criteri:** *In blocco* (seleziona il doppio segno più \[**++**\] nel campo per espandere l'elenco, quindi seleziona *In blocco*.)</span><span class="sxs-lookup"><span data-stu-id="b90cd-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="b90cd-294">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="b90cd-295">Scenario</span><span class="sxs-lookup"><span data-stu-id="b90cd-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="b90cd-296">Impostare lo scenario</span><span class="sxs-lookup"><span data-stu-id="b90cd-296">Set up the scenario</span></span>

<span data-ttu-id="b90cd-297">Per questo scenario, utilizzare i dati di esempio incorporati e creare i record descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="b90cd-298">Utilizzare i dati di esempio USMF</span><span class="sxs-lookup"><span data-stu-id="b90cd-298">Use the USMF sample data</span></span>

<span data-ttu-id="b90cd-299">Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="b90cd-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="b90cd-300">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="b90cd-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="b90cd-301">Creare domanda</span><span class="sxs-lookup"><span data-stu-id="b90cd-301">Create demand</span></span>

<span data-ttu-id="b90cd-302">Seguire questi passaggi per creare la domanda a cui applicare l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="b90cd-303">Vai a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="b90cd-304">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b90cd-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="b90cd-305">Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona _US-007_.</span><span class="sxs-lookup"><span data-stu-id="b90cd-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="b90cd-306">Nel campo **Magazzino** selezionare _61_.</span><span class="sxs-lookup"><span data-stu-id="b90cd-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="b90cd-307">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-307">Select **OK**.</span></span>
1. <span data-ttu-id="b90cd-308">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b90cd-308">The new sales order is opened.</span></span> <span data-ttu-id="b90cd-309">Include una riga vuota nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b90cd-310">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-311">**Articolo:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="b90cd-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="b90cd-312">**Quantità:** _20_</span><span class="sxs-lookup"><span data-stu-id="b90cd-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="b90cd-313">Seleziona **Aggiungi riga** per aggiungere una nuova riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="b90cd-314">**Articolo:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="b90cd-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="b90cd-315">**Quantità:** _8_</span><span class="sxs-lookup"><span data-stu-id="b90cd-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="b90cd-316">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-316">Select **Save**.</span></span>
1. <span data-ttu-id="b90cd-317">Seleziona **Nuovo** per creare un secondo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b90cd-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="b90cd-318">Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona _US-008_.</span><span class="sxs-lookup"><span data-stu-id="b90cd-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="b90cd-319">Nel campo **Magazzino** selezionare _61_.</span><span class="sxs-lookup"><span data-stu-id="b90cd-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="b90cd-320">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b90cd-320">The new sales order is opened.</span></span> <span data-ttu-id="b90cd-321">Include una riga vuota nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b90cd-322">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b90cd-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="b90cd-323">**Articolo:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="b90cd-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="b90cd-324">**Quantità:** _1_</span><span class="sxs-lookup"><span data-stu-id="b90cd-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="b90cd-325">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="b90cd-326">Eseguire un tipico scenario di assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="b90cd-327">Dopo che tutti gli elementi dei prerequisiti sono presenti, come descritto nella sezione precedente, sei pronto per provare la funzione utilizzando ogni esercizio in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="b90cd-328">Genera domanda</span><span class="sxs-lookup"><span data-stu-id="b90cd-328">Generate demand</span></span>

1. <span data-ttu-id="b90cd-329">Vai a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli assegnazione** e seleziona il modello di assegnazione che hai creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b90cd-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="b90cd-330">Nel riquadro azioni, seleziona **Genera domanda**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="b90cd-331">Questo comando valuta tutta la domanda presente nel sistema e corrisponde alla query del modello di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="b90cd-332">La domanda totale per tutti gli ordini viene quindi consolidata su una riga per quantità/unità di misura.</span><span class="sxs-lookup"><span data-stu-id="b90cd-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="b90cd-333">Un messaggio informativo appare quando il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="b90cd-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="b90cd-334">Domanda di assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-334">Slotting demand</span></span>

<span data-ttu-id="b90cd-335">La *domanda di assegnazione* mostra i risultati della generazione della domanda, in base all'impostazione del modello di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="b90cd-336">Nel riquadro azioni seleziona **Domanda di assegnazione** per visualizzare i risultati dal comando **Genera domanda**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="b90cd-337">Le righe nella domanda di assegnazione possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="b90cd-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="b90cd-338">Puoi eliminare una riga, aggiungere una nuova riga o modificare i dettagli della riga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="b90cd-339">Puoi modificare manualmente la domanda oppure importarla da un sistema esterno utilizzando la gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b90cd-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="b90cd-340">Qualunque sia il contenuto della domanda di assegnazione verrà utilizzata nel passaggio successivo, indipendentemente da dove provenga.</span><span class="sxs-lookup"><span data-stu-id="b90cd-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="b90cd-341">Rileva la richiesta</span><span class="sxs-lookup"><span data-stu-id="b90cd-341">Locate demand</span></span>

<span data-ttu-id="b90cd-342">Dopo che la domanda è stata generata, è necessario utilizzare il comando **Trova la domanda** per generare il *piano di assegnazione*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="b90cd-343">Nel riquadro azioni, seleziona **Trova domanda**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="b90cd-344">Viene eseguito il processo di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b90cd-344">The slotting process runs.</span></span> <span data-ttu-id="b90cd-345">Un messaggio informativo appare quando il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="b90cd-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="b90cd-346">Piano di assegnazione</span><span class="sxs-lookup"><span data-stu-id="b90cd-346">Slotting plan</span></span>

<span data-ttu-id="b90cd-347">Il piano di assegnazione mostra l'ubicazione a cui è stato assegnato ciascun articolo/quantità, se è stato utilizzato l'overflow, se è stato creato il lavoro di rallentamento e la riga del modello utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b90cd-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="b90cd-348">*Qualsiasi domanda che non è stato possibile assegnare è evidenziata in rosso.*</span><span class="sxs-lookup"><span data-stu-id="b90cd-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="b90cd-349">Nel riquadro azioni seleziona **Piano di assegnazione** per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="b90cd-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="b90cd-350">I processi **Genera domanda**, **Individua domanda** ed **Esegui rifornimento** vengono ora eseguiti in una sandbox.</span><span class="sxs-lookup"><span data-stu-id="b90cd-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="b90cd-351">(Questi processi sono disponibili dal riquadro azioni nella pagina **Modelli di assegnazione**.)</span><span class="sxs-lookup"><span data-stu-id="b90cd-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="b90cd-352">I processi **Genera domanda**, **Individua domanda** ed **Esegui rifornimento** hanno un blocco per garantire che non possano essere attivati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b90cd-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="b90cd-353">In caso contrario, i dati utilizzati potrebbero essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="b90cd-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="b90cd-354">I processi **Genera domanda** e **Individua domanda** mostrano un avviso se l'esecuzione non ha generato record o se nei record mancano informazioni.</span><span class="sxs-lookup"><span data-stu-id="b90cd-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="b90cd-355">Quando si seleziona **Piano di assegnazione**, la pagina non include i pulsanti **Nuovo**, **Modifica** o **Elimina** nel riquadro azioni, perché l'origine dati non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="b90cd-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="b90cd-356">Quando si seleziona **Esegui rifornimento**, il sistema convalida il modello di assegnazione selezionato e i processi.</span><span class="sxs-lookup"><span data-stu-id="b90cd-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="b90cd-357">Creare rifornimento</span><span class="sxs-lookup"><span data-stu-id="b90cd-357">Create replenishment</span></span>

<span data-ttu-id="b90cd-358">Dopo aver creato il piano di assegnazione, è necessario creare il *lavoro di rifornimento*, in base al piano.</span><span class="sxs-lookup"><span data-stu-id="b90cd-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="b90cd-359">Nel riquadro azioni seleziona **Esegui rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="b90cd-360">Un messaggio informativo appare quando il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="b90cd-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="b90cd-361">Questo messaggio indica il numero di intestazioni create per l'ID build di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b90cd-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="b90cd-362">Le direttive di ubicazione che verranno utilizzate sono identificate in base al codice della direttiva specificato su ciascuna riga del modello.</span><span class="sxs-lookup"><span data-stu-id="b90cd-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="b90cd-363">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="b90cd-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="b90cd-364">Configurare l'assegnazione automatica</span><span class="sxs-lookup"><span data-stu-id="b90cd-364">Set up automatic slotting</span></span>

<span data-ttu-id="b90cd-365">Dopo aver inserito tutti gli elementi richiesti, è possibile impostare l'assegnazione per l'esecuzione automatica seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="b90cd-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="b90cd-366">Vai a **Gestione magazzino \> Rifornimento \> Esegui assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="b90cd-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="b90cd-367">Specifica le fasi di assegnazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="b90cd-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="b90cd-368">Seleziona una o più delle seguenti fasi di assegnazione:</span><span class="sxs-lookup"><span data-stu-id="b90cd-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="b90cd-369">Genera domanda</span><span class="sxs-lookup"><span data-stu-id="b90cd-369">Generate demand</span></span>
    - <span data-ttu-id="b90cd-370">Rileva la richiesta</span><span class="sxs-lookup"><span data-stu-id="b90cd-370">Locate demand</span></span>
    - <span data-ttu-id="b90cd-371">Crea lavoro di rifornimento</span><span class="sxs-lookup"><span data-stu-id="b90cd-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="b90cd-372">I passaggi di assegnazione sono progressivi.</span><span class="sxs-lookup"><span data-stu-id="b90cd-372">The slotting steps are progressive.</span></span> <span data-ttu-id="b90cd-373">Se vuoi selezionare *Trova domanda*, devi prima selezionare *Genera domanda*.</span><span class="sxs-lookup"><span data-stu-id="b90cd-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="b90cd-374">Specifica il modello di assegnazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b90cd-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="b90cd-375">Imposta la ricorrenza per l'esecuzione automatica, se lo desideri.</span><span class="sxs-lookup"><span data-stu-id="b90cd-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="b90cd-376">Per gli esercizi nello scenario, **non** impostare l'assegnazione automatica.</span><span class="sxs-lookup"><span data-stu-id="b90cd-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]