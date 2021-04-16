---
title: Sequenza lavori gestiti dal sistema
description: Questo argomento fornisce informazioni sulla sequenza di lavori gestiti dal sistema. Questa funzionalità consente di ordinare e filtrare gli ordini di lavoro che il sistema presenta agli utenti per l'esecuzione. È utile in scenari in cui sono richiesti criteri aggiuntivi per guidare il processo di prelievo di magazzino.
author: Mirzaab
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 5387aaf5a5e0d20ac22595fbea86a25fdf38a771
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831124"
---
# <a name="system-directed-work-sequencing"></a><span data-ttu-id="2c77f-105">Sequenza lavori gestiti dal sistema</span><span class="sxs-lookup"><span data-stu-id="2c77f-105">System-directed work sequencing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c77f-106">Sequenza lavori gestiti dal sistema consente di ordinare e filtrare gli ordini di lavoro che il sistema presenta agli utenti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2c77f-106">System-directed work sequencing lets you sort and filter the work orders that the system presents to users for execution.</span></span> <span data-ttu-id="2c77f-107">È utile in scenari in cui sono richiesti criteri aggiuntivi (come il tempo di spedizione, la zona di prelievo, il profilo di ubicazione o una combinazione di vari criteri) per guidare il processo di prelievo in magazzino.</span><span class="sxs-lookup"><span data-stu-id="2c77f-107">It's helpful in scenarios where additional criteria (such as the time of shipping, the picking zone, the location profile, or a combination of various criteria) are required to drive the warehouse picking process.</span></span>

<span data-ttu-id="2c77f-108">Questa funzionalità estende l'attuale funzionalità di selezione diretta dal sistema aggiungendo un ordine di query diretto dal sistema, in cui gli utenti possono impostare una sequenza e una o più query che valuteranno tutti gli ordini di lavoro creati.</span><span class="sxs-lookup"><span data-stu-id="2c77f-108">This functionality extends the current system-directed picking functionality by adding a system-directed query order, where users can set up a sequence and one or more queries that will evaluate all work orders that are created.</span></span> <span data-ttu-id="2c77f-109">Verranno acquisiti e presentati solo gli ordini di lavoro che soddisfano i criteri specificati nell'impostazione della voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="2c77f-109">Only work orders that meet the criteria that are specified in the setup of the mobile device menu item will be captured and presented.</span></span>

<span data-ttu-id="2c77f-110">Pertanto, questa funzionalità consente un'ulteriore ottimizzazione dei processi di prelievo in magazzino in quanto identifica gli ordini di lavoro che soddisfano i criteri specificati, li assegna alla voce di menu del dispositivo mobile corretta e li presenta a un lavoratore, in base a un set di competenze, attrezzature di prelievo o altri requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="2c77f-110">Therefore, this functionality allows for further optimization of warehouse picking processes as it identifies work orders that match the specified criteria, assigns them to the correct mobile device menu item, and then presents them to a worker, based on a specific skill set, picking equipment, or other requirement.</span></span>

> [!NOTE]
> <span data-ttu-id="2c77f-111">Se sono necessari criteri diversi, è necessario utilizzare più voci di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="2c77f-111">If different criteria are needed, multiple mobile device menu items must be used.</span></span>

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a><span data-ttu-id="2c77f-112">Attivare la funzionalità di sequenza lavoro gestiti dal sistema a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="2c77f-112">Turn on the Organization-wide system directed work sequencing feature</span></span>

<span data-ttu-id="2c77f-113">Prima di poter utilizzare la sequenza lavori gestita dal sistema, tale funzionalità deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="2c77f-113">Before you can use system-directed work sequencing, the feature must be turned on in your system.</span></span> <span data-ttu-id="2c77f-114">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="2c77f-114">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="2c77f-115">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="2c77f-115">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="2c77f-116">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="2c77f-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="2c77f-117">**Nome funzione:** *Sequenza del lavoro diretto al sistema a livello di organizzazione*</span><span class="sxs-lookup"><span data-stu-id="2c77f-117">**Feature name:** *Organization-wide system directed work sequencing*</span></span>

## <a name="setup"></a><span data-ttu-id="2c77f-118">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="2c77f-118">Setup</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="2c77f-119">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="2c77f-119">Make demo data available</span></span>

<span data-ttu-id="2c77f-120">Per elaborare lo scenario utilizzando i record e i valori di esempio presentati in questo argomento, devi utilizzare un sistema in cui sono installati i dati dimostrativi standard.</span><span class="sxs-lookup"><span data-stu-id="2c77f-120">To work through the scenario by using the values that are presented in this topic, you must work on a system where the standard demo data is installed.</span></span> <span data-ttu-id="2c77f-121">Inoltre, è necessario selezionare la persona giuridica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-121">Additionally, you must select the **USMF** legal entity.</span></span> <span data-ttu-id="2c77f-122">Lo scenario utilizza il magazzino *51* dai dati demo.</span><span class="sxs-lookup"><span data-stu-id="2c77f-122">The scenario uses warehouse *51* from the demo data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c77f-123">Prima di rilasciare gli ordini al magazzino, devi assicurarti che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli degli ordini.</span><span class="sxs-lookup"><span data-stu-id="2c77f-123">Before you release the orders to the warehouse, make sure that the pick locations have enough inventory for all the items on the orders.</span></span>
>
> <span data-ttu-id="2c77f-124">I dati USMF predefiniti dovrebbero supportare questo scenario.</span><span class="sxs-lookup"><span data-stu-id="2c77f-124">Default USMF data should support this scenario.</span></span> <span data-ttu-id="2c77f-125">Se non stai utilizzando dati dimostrativi, rivedi Rivedere l'impostazione **Direttiva ubicazione** per apprendere quali ubicazioni di prelievo vengono utilizzate per il prelievo dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-125">If you aren't using demo data, review the **Location directive** setting to learn which picking locations are used for sales order picking.</span></span> <span data-ttu-id="2c77f-126">Se è necessario regolare le scorte, puoi creare movimenti manuali, utilizza il rifornimento o utilizza qualsiasi altro flusso, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="2c77f-126">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span>

### <a name="set-up-a-mobile-device-menu-item"></a><span data-ttu-id="2c77f-127">Configurare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="2c77f-127">Set up a mobile device menu item</span></span>

1. <span data-ttu-id="2c77f-128">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-128">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="2c77f-129">Nell'elenco delle voci di menu del dispositivo mobile, seleziona **Selezione vendite - Sistema**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-129">In the list of mobile device menu items, select **Sales Picking – System**.</span></span> <span data-ttu-id="2c77f-130">La voce di menu richiesta dovrebbe già esistere.</span><span class="sxs-lookup"><span data-stu-id="2c77f-130">The required menu item should already exist.</span></span> 
1. <span data-ttu-id="2c77f-131">Verificare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2c77f-131">Confirm the following settings:</span></span>

    - <span data-ttu-id="2c77f-132">Nella Scheda dettaglio **Generale**, il campo **Diretto da** deve essere impostato su *Diretto dal sistema*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-132">On the **General** FastTab, the **Directed by** field should be set to *System directed*.</span></span>
    - <span data-ttu-id="2c77f-133">la Scheda dettaglio **Classi di lavoro** dovrebbe mostrare le seguenti impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2c77f-133">The **Work classes** FastTab should show the following settings.</span></span>

        | <span data-ttu-id="2c77f-134">ID classe lavoro</span><span class="sxs-lookup"><span data-stu-id="2c77f-134">Work class ID</span></span> | <span data-ttu-id="2c77f-135">Tipo ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="2c77f-135">Work order type</span></span> |
        |---|---|
        | <span data-ttu-id="2c77f-136">Sales</span><span class="sxs-lookup"><span data-stu-id="2c77f-136">Sales</span></span> | <span data-ttu-id="2c77f-137">Gestione ordini cliente</span><span class="sxs-lookup"><span data-stu-id="2c77f-137">Sales orders</span></span> |
        | <span data-ttu-id="2c77f-138">Prelievo SO</span><span class="sxs-lookup"><span data-stu-id="2c77f-138">SO Pick</span></span> | <span data-ttu-id="2c77f-139">Gestione ordini cliente</span><span class="sxs-lookup"><span data-stu-id="2c77f-139">Sales orders</span></span> |

1. <span data-ttu-id="2c77f-140">Nel riquadro azioni seleziona **Query della sequenza di lavoro diretta dal sistema**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-140">On the Action Pane, select **System directed work sequence queries**.</span></span>
1. <span data-ttu-id="2c77f-141">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-141">Select **Edit**.</span></span>
1. <span data-ttu-id="2c77f-142">Elimina la riga esistente, quindi conferma l'azione selezionando **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-142">Delete the existing line, and then confirm the action by selecting **Yes**.</span></span>
1. <span data-ttu-id="2c77f-143">Nel riquadro azioni seleziona **Nuova** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="2c77f-143">On the Action Pane, select **New** to create a line.</span></span>
1. <span data-ttu-id="2c77f-144">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2c77f-145">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="2c77f-145">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="2c77f-146">**Campo descrizione:** *Quantità di lavoro inferiore a 20 e decrescente*</span><span class="sxs-lookup"><span data-stu-id="2c77f-146">**Description field:** *Work quantity less than 20 and Descending*</span></span>

1. <span data-ttu-id="2c77f-147">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-147">Select **Save**.</span></span>
1. <span data-ttu-id="2c77f-148">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-148">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="2c77f-149">Nella scheda **Join**, espandi la gerarchia di join per mostrare la tabella **Righe di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-149">On the **Joins** tab, expand the join hierarchy to show the **Work lines** table.</span></span>
1. <span data-ttu-id="2c77f-150">Seleziona il join della tabella **Righe di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-150">Select the **Work lines** table join.</span></span>
1. <span data-ttu-id="2c77f-151">Seleziona **Aggiungi tabella join**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-151">Select **Add table join**.</span></span>
1. <span data-ttu-id="2c77f-152">Nell'elenco che appare, trova e seleziona la riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2c77f-152">In the list that appears, find and select the row that has the following settings:</span></span>

    - <span data-ttu-id="2c77f-153">**Modalità join:** *n:1*</span><span class="sxs-lookup"><span data-stu-id="2c77f-153">**Join mode:** *n:1*</span></span>
    - <span data-ttu-id="2c77f-154">**Relazione:** *Ubicazioni (ubicazione)*</span><span class="sxs-lookup"><span data-stu-id="2c77f-154">**Relation:** *Locations (Location)*</span></span>

1. <span data-ttu-id="2c77f-155">Selezionare **Select**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-155">Select **Select**.</span></span>

    <span data-ttu-id="2c77f-156">Le ubicazioni vengono aggiunte al join della tabella.</span><span class="sxs-lookup"><span data-stu-id="2c77f-156">Locations are added to the table join.</span></span>

1. <span data-ttu-id="2c77f-157">Sulla scheda **Ordinamento**, seleziona e **Aggiungi** per aggiungere una riga.</span><span class="sxs-lookup"><span data-stu-id="2c77f-157">On the **Sorting** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="2c77f-158">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2c77f-159">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-159">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2c77f-160">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-160">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2c77f-161">**Campo:** *Quantità di lavoro* (nella finestra di messaggio che appare, seleziona **Sì** per aggiungere l'ordinamento a questo campo).</span><span class="sxs-lookup"><span data-stu-id="2c77f-161">**Field:** *Work quantity* (In the message box that appears, select **Yes** to add sorting to this field.)</span></span>
    - <span data-ttu-id="2c77f-162">**Direzione di ricerca:** *Decrescente*</span><span class="sxs-lookup"><span data-stu-id="2c77f-162">**Search direction:** *Descending*</span></span>

1. <span data-ttu-id="2c77f-163">Seleziona la scheda **Intervallo**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-163">Select the **Range** tab.</span></span>

    <span data-ttu-id="2c77f-164">Se nella sequenza devono essere inclusi solo criteri di lavoro specifici, è possibile specificarli nella scheda **Intervallo**. In questo esempio, è consigliabile includere solo lavori in cui la quantità è inferiore a 20 ea (l'unità di misura più bassa).</span><span class="sxs-lookup"><span data-stu-id="2c77f-164">If only specific work criteria should be included in the sequencing, you can specify them on the **Range** tab. In this example, you want to include only work where the quantity is less than 20 ea (the lowest unit of measure).</span></span>

    <span data-ttu-id="2c77f-165">Nota che alcune righe sono già incluse.</span><span class="sxs-lookup"><span data-stu-id="2c77f-165">Notice that some lines are already included.</span></span> <span data-ttu-id="2c77f-166">Tali righe non devono essere rimosse.</span><span class="sxs-lookup"><span data-stu-id="2c77f-166">Those lines should not be removed.</span></span>

1. <span data-ttu-id="2c77f-167">Seleziona **Aggiungi** per aggiungere una riga.</span><span class="sxs-lookup"><span data-stu-id="2c77f-167">Select **Add** to add a line.</span></span>
1. <span data-ttu-id="2c77f-168">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-168">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2c77f-169">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-169">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2c77f-170">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-170">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2c77f-171">**Campo:** *Quantità inventario lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-171">**Field:** *Inventory work quantity*</span></span>
    - <span data-ttu-id="2c77f-172">**Criteri:** *\<20* (meno di 20)</span><span class="sxs-lookup"><span data-stu-id="2c77f-172">**Criteria:** *\<20* (less than 20)</span></span>

1. <span data-ttu-id="2c77f-173">Seleziona **Aggiungi** per aggiungere un'altra riga.</span><span class="sxs-lookup"><span data-stu-id="2c77f-173">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="2c77f-174">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2c77f-175">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-175">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="2c77f-176">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-176">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="2c77f-177">**Campo:** *Tipo di lavoro*</span><span class="sxs-lookup"><span data-stu-id="2c77f-177">**Field:** *Work type*</span></span>
    - <span data-ttu-id="2c77f-178">**Criteri:** *Prelievo*</span><span class="sxs-lookup"><span data-stu-id="2c77f-178">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="2c77f-179">Seleziona **Aggiungi** per aggiungere un'altra riga.</span><span class="sxs-lookup"><span data-stu-id="2c77f-179">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="2c77f-180">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="2c77f-181">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="2c77f-181">**Table:** *Locations*</span></span>
    - <span data-ttu-id="2c77f-182">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="2c77f-182">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="2c77f-183">**Campo:** *ID profilo ubicazione*</span><span class="sxs-lookup"><span data-stu-id="2c77f-183">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="2c77f-184">**Criteri:** *!STAGE*</span><span class="sxs-lookup"><span data-stu-id="2c77f-184">**Criteria:** *!STAGE*</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="2c77f-185">Assicurati di includere il punto esclamativo (*!*) di fronte a *STAGE*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-185">Be sure to include the exclamation point (*!*) in front of *STAGE*.</span></span>

1. <span data-ttu-id="2c77f-186">Seleziona **OK** per salvare e chiudere la query.</span><span class="sxs-lookup"><span data-stu-id="2c77f-186">Select **OK** to save and close the query.</span></span>
1. <span data-ttu-id="2c77f-187">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-187">Select **Save**.</span></span>
1. <span data-ttu-id="2c77f-188">Chiudi la pagina per tornare alla pagina **Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-188">Close the page to return to the **Mobile device menu items** page.</span></span>

> [!NOTE]
> <span data-ttu-id="2c77f-189">Questa configurazione definisce i criteri che verranno utilizzati per inserire il lavoro idoneo alla voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="2c77f-189">This setup defines the criteria that will be used to feed eligible work to the mobile device menu item.</span></span> <span data-ttu-id="2c77f-190">Se aggiungi più righe di criteri alla query, il sistema utilizzerà prima la riga della query con il numero di sequenza più basso.</span><span class="sxs-lookup"><span data-stu-id="2c77f-190">If you add more criteria lines to the query, the system will use the query line that has lowest sequence number first.</span></span> <span data-ttu-id="2c77f-191">In altre parole, tutti i lavori idonei per la sequenza numero 1 verranno prima presentati all'utente per primi, seguiti da tutti i lavori per la sequenza numero 2.</span><span class="sxs-lookup"><span data-stu-id="2c77f-191">In other words, all eligible work for sequence number 1 will be presented to the user first, and then all work for sequence number 2.</span></span> <span data-ttu-id="2c77f-192">Pertanto, se un intervallo e un ordinamento specifici devono essere utilizzati insieme, devono essere specificati nella stessa query della sequenza di lavoro diretta dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2c77f-192">Therefore, if a specific range and sorting must be used together, they should be specified in the same system-directed work sequence query.</span></span>
>
> <span data-ttu-id="2c77f-193">Questa configurazione acquisirà qualsiasi lavoro che abbia almeno una riga in cui la quantità è inferiore a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="2c77f-193">This setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="2c77f-194">Pertanto, se il lavoro ha una riga in cui la quantità è esattamente di 20 ea o più di 20 ea, sarà valida, a condizione che abbia anche almeno una riga in cui la quantità è inferiore a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="2c77f-194">Therefore, if the work has a line where the quantity is exactly 20 ea or more than 20 ea, it will be valid, provided that it also has at least one line where the quantity is less than 20 ea.</span></span>

### <a name="location-directives"></a><span data-ttu-id="2c77f-195">Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="2c77f-195">Location directives</span></span>

<span data-ttu-id="2c77f-196">Se si utilizzano i dati Contoso predefiniti, la query per l'azione della direttiva ubicazione non richiederà modifiche.</span><span class="sxs-lookup"><span data-stu-id="2c77f-196">If you're using default Contoso data, the query for the location directive action won't require changes.</span></span> <span data-ttu-id="2c77f-197">Tuttavia, per assicurarsi che le direttive di ubicazione acquisiscano gli articoli negli ordini cliente quando si applica la funzionalità in un ambiente non Contoso, crea una nuova direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="2c77f-197">However, to make sure that the location directives will capture the items on the sales orders when you apply the feature in a non-Contoso environment, create a new location directive.</span></span> <span data-ttu-id="2c77f-198">Per verificare le impostazioni nell'ambiente demo, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="2c77f-198">To verify the settings in the demo environment, follow these steps.</span></span>

1. <span data-ttu-id="2c77f-199">Andare a **Gestione magazzino** \> **Impostazioni** \> **Direttive ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-199">Go to **Warehouse management** \> **Setup** \> **Location directives**.</span></span>
1. <span data-ttu-id="2c77f-200">Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-200">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="2c77f-201">Seleziona la direttiva ubicazione denominata *Prelievo 51*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-201">Select the location directive that is named *51 Pick*.</span></span>
1. <span data-ttu-id="2c77f-202">Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona la riga per l'azione **Prelievo**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-202">On the **Location Directive Actions** FastTab, select the line for the **Pick** action.</span></span>
1. <span data-ttu-id="2c77f-203">Seleziona **Modifica query** sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="2c77f-203">Select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="2c77f-204">Rivedi la query **Intervallo**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-204">Review the **Range** query.</span></span>

    1. <span data-ttu-id="2c77f-205">Trova la riga in cui il campo **Campo** è impostato su *Ubicazione*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-205">Find the line where the **Field** field is set to *Location*.</span></span>
    2. <span data-ttu-id="2c77f-206">Verifica che il campo **Criteri** sia vuoto (ovvero non ci sono restrizioni).</span><span class="sxs-lookup"><span data-stu-id="2c77f-206">Make sure that the **Criteria** field is blank (that is, there are no restrictions).</span></span>

## <a name="scenario"></a><span data-ttu-id="2c77f-207">Scenario</span><span class="sxs-lookup"><span data-stu-id="2c77f-207">Scenario</span></span>

### <a name="create-sales-order-picking-work"></a><span data-ttu-id="2c77f-208">Creare lavoro di prelievo ordini cliente</span><span class="sxs-lookup"><span data-stu-id="2c77f-208">Create sales order picking work</span></span>

<span data-ttu-id="2c77f-209">Prima di eseguire il prelievo diretto dal sistema, è necessario creare alcuni lavori in uscita.</span><span class="sxs-lookup"><span data-stu-id="2c77f-209">Before system-directed picking is run, some outbound work should be created.</span></span> <span data-ttu-id="2c77f-210">Per questo scenario, verranno creati quattro ordini cliente basati sulle query della sequenza di lavoro diretta dal sistema specificate.</span><span class="sxs-lookup"><span data-stu-id="2c77f-210">For this scenario, you will create four sales orders that are based on the specified system-directed work sequence queries.</span></span>

<span data-ttu-id="2c77f-211">Prenoterai le quantità di scorte per ciascun ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-211">You will reserve inventory quantities for each sales order.</span></span> <span data-ttu-id="2c77f-212">Pertanto, le scorte prenotate non possono quindi essere prelevate dal magazzino per altri ordini, a meno che la prenotazione o parte di questa non venga annullata.</span><span class="sxs-lookup"><span data-stu-id="2c77f-212">Therefore, reserved inventory can't be withdrawn from the warehouse for other orders unless the inventory reservation, or part of the inventory reservation, is canceled.</span></span>

<span data-ttu-id="2c77f-213">Rilascerai quindi ciascun ordine cliente nel magazzino per creare il lavoro in uscita.</span><span class="sxs-lookup"><span data-stu-id="2c77f-213">You will then release each sales order to the warehouse to create the outbound work.</span></span>

#### <a name="sales-order-1"></a><span data-ttu-id="2c77f-214">Ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="2c77f-214">Sales order 1</span></span>

1. <span data-ttu-id="2c77f-215">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-215">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="2c77f-216">Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="2c77f-216">On the Action Pane, select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="2c77f-217">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-217">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2c77f-218">Nella sezione **Cliente**, imposta il campo **Conto cliente** su *US-004*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-218">In the **Customer** section, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="2c77f-219">Nella sezione **Generale** imposta il campo **Magazzino** su *51*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-219">In the **General** section, set the **Warehouse** field to *51*.</span></span>

1. <span data-ttu-id="2c77f-220">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2c77f-220">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="2c77f-221">Prendi nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-221">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="2c77f-222">Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-222">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="2c77f-223">**Numero articolo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="2c77f-223">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="2c77f-224">**Quantità:** *20*</span><span class="sxs-lookup"><span data-stu-id="2c77f-224">**Quantity:** *20*</span></span>

1. <span data-ttu-id="2c77f-225">Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-225">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="2c77f-226">Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare le scorte.</span><span class="sxs-lookup"><span data-stu-id="2c77f-226">On the **Reservation** page, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="2c77f-227">Chiudi la pagina **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-227">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="2c77f-228">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino** per creare lavoro per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="2c77f-228">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse** to create work for the warehouse.</span></span>

    <span data-ttu-id="2c77f-229">Ricevi messaggi informativi che mostrano l'ID ondata e gli ID spedizione creati per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-229">You receive informational messages that show the wave ID and shipment IDs that were created for the sales order.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="2c77f-230">Ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="2c77f-230">Sales order 2</span></span>

1. <span data-ttu-id="2c77f-231">Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="2c77f-231">On the Action Pane, select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="2c77f-232">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-232">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2c77f-233">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="2c77f-233">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="2c77f-234">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="2c77f-234">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="2c77f-235">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2c77f-235">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="2c77f-236">Prendi nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-236">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="2c77f-237">Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-237">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="2c77f-238">**Numero articolo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="2c77f-238">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="2c77f-239">**Quantità:** *5*</span><span class="sxs-lookup"><span data-stu-id="2c77f-239">**Quantity:** *5*</span></span>

1. <span data-ttu-id="2c77f-240">Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-240">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="2c77f-241">**Numero articolo:** *M9201*</span><span class="sxs-lookup"><span data-stu-id="2c77f-241">**Item number:** *M9201*</span></span>
    - <span data-ttu-id="2c77f-242">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="2c77f-242">**Quantity:** *1*</span></span>

1. <span data-ttu-id="2c77f-243">Prenota scorte per entrambe le righe.</span><span class="sxs-lookup"><span data-stu-id="2c77f-243">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="2c77f-244">Rilascia l'ordine ordini al magazzino.</span><span class="sxs-lookup"><span data-stu-id="2c77f-244">Release the order to the warehouse.</span></span>

#### <a name="sales-order-3"></a><span data-ttu-id="2c77f-245">Ordine cliente 3</span><span class="sxs-lookup"><span data-stu-id="2c77f-245">Sales order 3</span></span>

1. <span data-ttu-id="2c77f-246">Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 3.</span><span class="sxs-lookup"><span data-stu-id="2c77f-246">On the Action Pane, select **New** to create sales order 3.</span></span>
1. <span data-ttu-id="2c77f-247">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-247">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2c77f-248">**Conto cliente:** *US-009*</span><span class="sxs-lookup"><span data-stu-id="2c77f-248">**Customer account:** *US-009*</span></span>
    - <span data-ttu-id="2c77f-249">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="2c77f-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="2c77f-250">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2c77f-250">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="2c77f-251">Prendi nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-251">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="2c77f-252">Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-252">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="2c77f-253">**Numero articolo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="2c77f-253">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="2c77f-254">**Quantità:** *7*</span><span class="sxs-lookup"><span data-stu-id="2c77f-254">**Quantity:** *7*</span></span>

1. <span data-ttu-id="2c77f-255">Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-255">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="2c77f-256">**Numero articolo:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="2c77f-256">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="2c77f-257">**Quantità:** *8*</span><span class="sxs-lookup"><span data-stu-id="2c77f-257">**Quantity:** *8*</span></span>

1. <span data-ttu-id="2c77f-258">Prenota scorte per entrambe le righe.</span><span class="sxs-lookup"><span data-stu-id="2c77f-258">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="2c77f-259">Rilascia l'ordine ordini al magazzino.</span><span class="sxs-lookup"><span data-stu-id="2c77f-259">Release the order to the warehouse.</span></span>

#### <a name="sales-order-4"></a><span data-ttu-id="2c77f-260">Ordine cliente 4</span><span class="sxs-lookup"><span data-stu-id="2c77f-260">Sales order 4</span></span>

1. <span data-ttu-id="2c77f-261">Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 4.</span><span class="sxs-lookup"><span data-stu-id="2c77f-261">On the Action Pane, select **New** to create sales order 4.</span></span>
1. <span data-ttu-id="2c77f-262">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-262">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2c77f-263">**Conto cliente:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="2c77f-263">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="2c77f-264">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="2c77f-264">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="2c77f-265">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2c77f-265">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="2c77f-266">Prendi nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-266">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="2c77f-267">Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-267">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="2c77f-268">**Numero articolo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="2c77f-268">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="2c77f-269">**Quantità:** *25*</span><span class="sxs-lookup"><span data-stu-id="2c77f-269">**Quantity:** *25*</span></span>

1. <span data-ttu-id="2c77f-270">Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c77f-270">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="2c77f-271">**Numero articolo:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="2c77f-271">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="2c77f-272">**Quantità:** *10*</span><span class="sxs-lookup"><span data-stu-id="2c77f-272">**Quantity:** *10*</span></span>

1. <span data-ttu-id="2c77f-273">Prenota scorte per entrambe le righe.</span><span class="sxs-lookup"><span data-stu-id="2c77f-273">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="2c77f-274">Rilascia l'ordine ordini al magazzino.</span><span class="sxs-lookup"><span data-stu-id="2c77f-274">Release the order to the warehouse.</span></span>

### <a name="get-work-ids-for-the-work-that-was-created"></a><span data-ttu-id="2c77f-275">Ottenere gli ID lavoro per il lavoro che è stato creato</span><span class="sxs-lookup"><span data-stu-id="2c77f-275">Get work IDs for the work that was created</span></span>

1. <span data-ttu-id="2c77f-276">Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-276">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="2c77f-277">Filtra il campo **Magazzino** in modo che il lavoro venga mostrato solo per il magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-277">Filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="2c77f-278">Dovrebbero essere stati creati quattro ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c77f-278">Four work IDs should have been created.</span></span> <span data-ttu-id="2c77f-279">Prendi nota dell'ID di lavoro per ciascun ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-279">Make a note of the work ID for each sales order.</span></span>

    | <span data-ttu-id="2c77f-280">ID ordine cliente</span><span class="sxs-lookup"><span data-stu-id="2c77f-280">Sales order ID</span></span> | <span data-ttu-id="2c77f-281">ID lavoro</span><span class="sxs-lookup"><span data-stu-id="2c77f-281">Work ID</span></span> | <span data-ttu-id="2c77f-282">Quantità lavoro</span><span class="sxs-lookup"><span data-stu-id="2c77f-282">Work quantity</span></span> |
    |---|---|---|
    | <span data-ttu-id="2c77f-283">Ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="2c77f-283">Sales Order 1</span></span> | <span data-ttu-id="2c77f-284">ID lavoro 1</span><span class="sxs-lookup"><span data-stu-id="2c77f-284">Work ID 1</span></span> | <span data-ttu-id="2c77f-285">20 ea</span><span class="sxs-lookup"><span data-stu-id="2c77f-285">20 ea</span></span> |
    | <span data-ttu-id="2c77f-286">Ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="2c77f-286">Sales Order 2</span></span> | <span data-ttu-id="2c77f-287">ID lavoro 2</span><span class="sxs-lookup"><span data-stu-id="2c77f-287">Work ID 2</span></span> | <span data-ttu-id="2c77f-288">6 ea (somma di entrambe le righe)</span><span class="sxs-lookup"><span data-stu-id="2c77f-288">6 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="2c77f-289">Ordine cliente 3</span><span class="sxs-lookup"><span data-stu-id="2c77f-289">Sales Order 3</span></span> | <span data-ttu-id="2c77f-290">ID lavoro 3</span><span class="sxs-lookup"><span data-stu-id="2c77f-290">Work ID 3</span></span> | <span data-ttu-id="2c77f-291">15 ea (somma di entrambe le righe)</span><span class="sxs-lookup"><span data-stu-id="2c77f-291">15 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="2c77f-292">Ordine cliente 4</span><span class="sxs-lookup"><span data-stu-id="2c77f-292">Sales Order 4</span></span> | <span data-ttu-id="2c77f-293">ID lavoro 4</span><span class="sxs-lookup"><span data-stu-id="2c77f-293">Work ID 4</span></span> | <span data-ttu-id="2c77f-294">35 ea (somma di entrambe le righe)</span><span class="sxs-lookup"><span data-stu-id="2c77f-294">35 ea (sum of both lines)</span></span> |

<span data-ttu-id="2c77f-295">Prima di eseguire il flusso sul dispositivo mobile, verifica che solo il lavoro appena creato sia nello stato *Aperto* per il magazzino *51* e il tipo di ordine di lavoro *Ordine cliente*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-295">Before you run the flow on the mobile device, make sure that only the work that you just created is in *Open* status for warehouse *51* and the *Sales order* work order type.</span></span> <span data-ttu-id="2c77f-296">Altrimenti, i risultati del test potrebbero variare, poiché il prelievo diretto dal sistema includerà tutto il lavoro idoneo.</span><span class="sxs-lookup"><span data-stu-id="2c77f-296">Otherwise, the results of the test might vary, because the system-direct picking will include all eligible work.</span></span>

1. <span data-ttu-id="2c77f-297">Vai a **Gestione magazzino \> Lavoro \> In uscita \> Lavoro acquisti aperto**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-297">Go to **Warehouse management \> Work \> Outbound \> Open sales work**.</span></span>
1. <span data-ttu-id="2c77f-298">Nella griglia **Lavoro acquisti aperto**, filtra il campo **Magazzino** in modo che il lavoro venga mostrato solo per il magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-298">In the **Open sales work** grid, filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="2c77f-299">Conferma che vengono visualizzati solo i quattro ID lavoro creati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2c77f-299">Confirm that only the four work IDs that you created earlier are shown.</span></span>
1. <span data-ttu-id="2c77f-300">Chiudi la pagina **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-300">Close the **Work** page.</span></span>

### <a name="mobile-device-flow-execution"></a><span data-ttu-id="2c77f-301">Esecuzione dei flussi su dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="2c77f-301">Mobile device flow execution</span></span>

<span data-ttu-id="2c77f-302">In base alla configurazione, il sistema inserirà il lavoro dell'utente che viene ordinato dalla quantità più elevata della riga di lavoro alla più bassa.</span><span class="sxs-lookup"><span data-stu-id="2c77f-302">Based on the setup, the system will feed the user work that is sorted from the highest work line quantity to the lowest.</span></span> <span data-ttu-id="2c77f-303">La quantità su ogni riga sarà inferiore a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="2c77f-303">The quantity on every line will be less than 20 ea.</span></span>

<span data-ttu-id="2c77f-304">Ricorda che questa configurazione acquisirà qualsiasi lavoro che abbia almeno una riga in cui la quantità è inferiore a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="2c77f-304">Remember that this setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="2c77f-305">Pertanto, se il lavoro ha un'altra riga in cui la quantità è esattamente 20 ea o più di 20 ea, anche questa sarà valida.</span><span class="sxs-lookup"><span data-stu-id="2c77f-305">Therefore, if the work has another line where the quantity is exactly 20 ea or more than 20 ea, it will also be valid.</span></span>

#### <a name="mobile-app"></a><span data-ttu-id="2c77f-306">App per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="2c77f-306">Mobile app</span></span>

1. <span data-ttu-id="2c77f-307">Accedi all'app di magazzino come utente nel magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-307">Sign in to the warehousing app as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="2c77f-308">Vai a **In uscita \> Selezione vendite - Sistema**.</span><span class="sxs-lookup"><span data-stu-id="2c77f-308">Go to **Outbound \> Sales Picking - System**.</span></span>

    <span data-ttu-id="2c77f-309">Viene presentato il passaggio di prelievo per l'ID lavoro *4*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-309">The pick step for work ID *4* is presented.</span></span> <span data-ttu-id="2c77f-310">Questo ID lavoro viene presentato per primo a causa dell'impostazione dell'ordine di query diretto dal sistema, in cui è stato specificato che la sequenza del lavoro deve corrispondere alla quantità della riga di lavoro decrescente.</span><span class="sxs-lookup"><span data-stu-id="2c77f-310">This work ID is presented first because of the setup of the system-directed query order, where you specified that work should be sequenced based on descending work line quantity.</span></span>

1. <span data-ttu-id="2c77f-311">Completa il prelievo richiesto e chiudi l'ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c77f-311">Complete the required pick and put to close the work ID.</span></span>

    <span data-ttu-id="2c77f-312">Quindi, viene presentato l'ID lavoro *3*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-312">Next, work ID *3* is presented.</span></span> <span data-ttu-id="2c77f-313">Una delle sue righe di lavoro è la seguente nella sequenza, in base alla quantità delle righe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c77f-313">One of its work lines is next in the sequence, based on the work line quantity.</span></span>

1. <span data-ttu-id="2c77f-314">Completa il prelievo e chiudi l'ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c77f-314">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="2c77f-315">Quindi, viene presentato l'ID lavoro *2*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-315">Next, work ID *2* is presented.</span></span> <span data-ttu-id="2c77f-316">La riga di prelievo di questo lavoro è la prossima nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="2c77f-316">This work's pick line is next in the sequence.</span></span>

1. <span data-ttu-id="2c77f-317">Completa il prelievo e chiudi l'ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c77f-317">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="2c77f-318">Nessun ulteriore lavoro dovrebbe essere presentato.</span><span class="sxs-lookup"><span data-stu-id="2c77f-318">No further work should be presented to you.</span></span> <span data-ttu-id="2c77f-319">L'ID lavoro *1* non è idoneo per questa voce di menu del dispositivo mobile, poiché la query specifica che le intestazioni di lavoro sono considerate solo se la quantità sulle righe di lavoro è inferiore a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="2c77f-319">Work ID *1* isn't eligible for this mobile device menu item, because the query specifies that work headers are considered only if the quantity on the work lines is less than 20 ea.</span></span>

## <a name="tips"></a><span data-ttu-id="2c77f-320">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="2c77f-320">Tips</span></span>

<span data-ttu-id="2c77f-321">Le query della sequenza di lavoro dirette dal sistema sono *inclusive*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-321">The system-directed work sequence queries are *inclusive*.</span></span> <span data-ttu-id="2c77f-322">È importante ricordare questo fatto per alcune configurazioni.</span><span class="sxs-lookup"><span data-stu-id="2c77f-322">It's important that you remember this fact for some setups.</span></span> <span data-ttu-id="2c77f-323">Ad esempio, vuoi che una voce di menu specifica elabori il lavoro solo dove si trova l'unità di lavoro *ea* e specifichi tale limitazione nella scheda **Intervallo** della query.</span><span class="sxs-lookup"><span data-stu-id="2c77f-323">For example, you want a specific menu item to process only work where the work unit is *ea*, and you specify that restriction on the **Range** tab of the query.</span></span> <span data-ttu-id="2c77f-324">In questo caso, tutto il lavoro in cui almeno una riga di lavoro ha l'unità di lavoro impostata su *ea* sarà inserita sul lavoratore.</span><span class="sxs-lookup"><span data-stu-id="2c77f-324">In this case, all work where at least one work line has the work unit set to *ea* will be fed to the worker.</span></span> <span data-ttu-id="2c77f-325">Pertanto, questo lavoro potrebbe includere anche lavori in cui le righe di lavoro hanno un'unità di lavoro diversa da *ea* (ad esempio *scatola* o *pallet*).</span><span class="sxs-lookup"><span data-stu-id="2c77f-325">Therefore, this work might also include work where work lines have a work unit other than *ea* (such as *box* or *pallet*).</span></span> <span data-ttu-id="2c77f-326">La query esclude il lavoro solo dove nessuna riga di lavoro ha l'unità di lavoro impostata su *ea*.</span><span class="sxs-lookup"><span data-stu-id="2c77f-326">The query will exclude only work where no work line has the work unit set to *ea*.</span></span>

<span data-ttu-id="2c77f-327">Pertanto, nell'esempio di questo scenario, l'ID lavoro *4* è stato anche acquisito dalla query.</span><span class="sxs-lookup"><span data-stu-id="2c77f-327">Therefore, in the example from this scenario, work ID *4* was also captured by the query.</span></span> <span data-ttu-id="2c77f-328">Quando è stato creato, sono state aggiunte due righe: una per 25 ea e una per 10 ea.</span><span class="sxs-lookup"><span data-stu-id="2c77f-328">When it was created, two lines were added: one for 25 ea and another for 10 ea.</span></span> <span data-ttu-id="2c77f-329">Il lavoro è stato ancora presentato all'utente, poiché almeno una riga di lavoro ha una quantità inferiore a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="2c77f-329">The work was still presented to the user, because at least one work line has a quantity of less than 20 ea.</span></span>

<span data-ttu-id="2c77f-330">A seconda dello scenario, è possibile impedire questo comportamento utilizzando le suddivisioni del lavoro.</span><span class="sxs-lookup"><span data-stu-id="2c77f-330">Depending on the scenario, you can prevent this behavior by using work breaks.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]