---
title: Stoccaggio a parete - stoccaggio in magazzino
description: Questo argomento fornisce informazioni sulla funzionalità Stoccaggio a parete - stoccaggio in magazzino. Questa funzionalità consente di gestire scenari in cui è necessario consolidare un prodotto in un'area di gestione temporanea di preimballaggio, in base a criteri configurabili. Aiuta a ridurre i tempi di prelievo perché consente di prelevare una singola targa di destinazione singola e può utilizzare più posizioni di stoccaggio rispetto a un prelievo cluster.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 12501b90e4b31ec11e3c59784ace9fd9a8b7d934
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017830"
---
# <a name="put-to-wall---put-to-store"></a><span data-ttu-id="ab64e-105">Stoccaggio a parete - stoccaggio in magazzino</span><span class="sxs-lookup"><span data-stu-id="ab64e-105">Put to wall - put to store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab64e-106">La funzionalità *Stoccaggio a parete - stoccaggio in magazzino* consente di gestire scenari in cui è necessario consolidare un prodotto in un'area di gestione temporanea di preimballaggio, in base a criteri configurabili.</span><span class="sxs-lookup"><span data-stu-id="ab64e-106">The *Put to wall - put to store* functionality lets you handle scenarios where you must consolidate a product to a prepack staging area, based on configurable criteria.</span></span> <span data-ttu-id="ab64e-107">Poiché questa funzionalità consente il prelievo su una singola targa di destinazione e può utilizzare più posizioni di stoccaggio rispetto al prelievo cluster, le aziende che spediscono a punti vendita o gestiscono piccoli articoli trarranno vantaggio dalla riduzione dei tempi di prelievo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-107">Because this functionality allows for picking to a single target license plate and can use more put positions than cluster picking, companies that ship to stores or handle small items will benefit from decreased picking time.</span></span>

<span data-ttu-id="ab64e-108">Il flusso di lavoro per questa funzionalità indirizza il prodotto prelevato a un'ubicazione di ordinamento per la distribuzione in vari tipi di contenitori.</span><span class="sxs-lookup"><span data-stu-id="ab64e-108">The workflow for this functionality directs picked product to a sorting location for distribution into various types of containers.</span></span> <span data-ttu-id="ab64e-109">In generale, ogni ubicazione di ordinamento include più posizioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-109">Generally, each sorting location includes multiple sort positions.</span></span> <span data-ttu-id="ab64e-110">Ogni posizione di ordinamento viene assegnata in base ai criteri impostati dal processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="ab64e-110">Each sort position is assigned according to the criteria that are set by the business process.</span></span> <span data-ttu-id="ab64e-111">I criteri tipici sono la destinazione finale, la spedizione o il carico.</span><span class="sxs-lookup"><span data-stu-id="ab64e-111">Typical criteria are the final destination, shipment, or load.</span></span> <span data-ttu-id="ab64e-112">Dopo l'arrivo di un prodotto, questo viene distribuito a ciascuna posizione di ordinamento, in base alla quantità associata all'ordine, alla destinazione, alla spedizione o al carico.</span><span class="sxs-lookup"><span data-stu-id="ab64e-112">After a product arrives, it's distributed to each sort position, based on the quantity that is associated with the order, destination, shipment, or load.</span></span> <span data-ttu-id="ab64e-113">Quando un container è pieno o completo, viene spostato in un'ubicazione di gestione temporanea o in un'ubicazione di spedizione per un'ulteriore gestione, a seconda del processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="ab64e-113">When a container is full or complete, it's moved to a staging location or a shipping location for further handling, depending on the business process.</span></span>

<span data-ttu-id="ab64e-114">Questa funzionalità di magazzino è anche indicata con altri nomi, ad esempio "put-to-light".</span><span class="sxs-lookup"><span data-stu-id="ab64e-114">This warehousing functionality is also referred to by other names, such as put-to-light and break opens.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="ab64e-115">Attivare la funzionalità Ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="ab64e-115">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="ab64e-116">Prima di poter usare la funzionalità *Stoccaggio a parete - stoccaggio in magazzino* , è necessario attivare la funzionalità *Ordinamento in uscita* nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ab64e-116">Before you can use the *Put to wall - put to store* functionality, the *Outbound sorting* feature must be turned on in your system.</span></span> <span data-ttu-id="ab64e-117">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="ab64e-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="ab64e-118">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ab64e-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ab64e-119">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="ab64e-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ab64e-120">**Nome funzionalità:** *Ordinamento in uscita*</span><span class="sxs-lookup"><span data-stu-id="ab64e-120">**Feature name:** *Outbound sorting*</span></span>

<span data-ttu-id="ab64e-121">La funzionalità *Ordinamento in uscita* può essere utilizzata insieme alla funzionalità *Codice passaggio ondata a livello di organizzazione* se è attivata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-121">The *Outbound sorting* feature can be used in conjunction with the *Organization wide wave step code* feature if it's turned on.</span></span> <span data-ttu-id="ab64e-122">È inoltre necessario attivare questa funzionalità se si useranno codici predefiniti impostati nei codici passaggio ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-122">You must also turn on this feature if you will use predefined codes that are set up in wave step codes.</span></span> <span data-ttu-id="ab64e-123">Nell'area di lavoro **Gestione funzionalità** , questa funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ab64e-123">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="ab64e-124">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="ab64e-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ab64e-125">**Nome funzionalità:** *Codice passaggio ondata a livello di organizzazione*</span><span class="sxs-lookup"><span data-stu-id="ab64e-125">**Feature name:** *Organization wide wave step code*</span></span>

## <a name="setup"></a><span data-ttu-id="ab64e-126">Configurazione</span><span class="sxs-lookup"><span data-stu-id="ab64e-126">Setup</span></span>

<span data-ttu-id="ab64e-127">Per questa demo, sono utilizzati i dati e il magazzino Contoso standard *62*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-127">For this demo, standard Contoso data and warehouse *62* are used.</span></span> <span data-ttu-id="ab64e-128">Vengono inoltre utilizzate alcune aggiunte che verranno annotate in seguito.</span><span class="sxs-lookup"><span data-stu-id="ab64e-128">Some additions that are noted later are also used.</span></span>

### <a name="location-type"></a><span data-ttu-id="ab64e-129">Tipo di ubicazione</span><span class="sxs-lookup"><span data-stu-id="ab64e-129">Location type</span></span>

1. <span data-ttu-id="ab64e-130">Andare a **Gestione magazzino \> Impostazione \> Magazzino \> Tipi di ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-130">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="ab64e-131">Nel riquadro azioni selezionare **Nuovo** per creare un tipo di ubicazione per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-131">On the Action Pane, select **New** to create a location type for sorting.</span></span>
1. <span data-ttu-id="ab64e-132">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-132">Set the following values:</span></span>

    - <span data-ttu-id="ab64e-133">**Tipo di ubicazione:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="ab64e-133">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="ab64e-134">**Descrizione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-134">**Description:** *Sort*</span></span>

1. <span data-ttu-id="ab64e-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-135">Select **Save**.</span></span>

### <a name="warehouse-management-parameters"></a><span data-ttu-id="ab64e-136">Parametri di gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="ab64e-136">Warehouse management parameters</span></span>

1. <span data-ttu-id="ab64e-137">Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-137">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="ab64e-138">Nella scheda **Generale** della Scheda dettaglio **Tipi di ubicazione** , nel campo **Tipo di ubicazione di ordinamento** , immettere *ORDINAMENTO*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-138">On the **General** tab, on the **Location types** FastTab, in the **Sorting location type** field, enter *SORT*.</span></span>
1. <span data-ttu-id="ab64e-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-139">Select **Save**.</span></span>

### <a name="location-profile"></a><span data-ttu-id="ab64e-140">Profilo dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="ab64e-140">Location profile</span></span>

1. <span data-ttu-id="ab64e-141">Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-141">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="ab64e-142">Nel riquadro azioni selezionare **Nuovo** per creare un profilo di ubicazione per l'ubicazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-142">On the Action Pane, select **New** to create a location profile for the sorting location.</span></span>
1. <span data-ttu-id="ab64e-143">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-143">In the header, set the following values:</span></span>

    - <span data-ttu-id="ab64e-144">**ID profilo ubicazione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-144">**Location profile ID:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-145">**Nome:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-145">**Name:** *Sort*</span></span>

1. <span data-ttu-id="ab64e-146">Nella Scheda dettaglio **Generale** , imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-146">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ab64e-147">**Formato ubicazione** *PACK*</span><span class="sxs-lookup"><span data-stu-id="ab64e-147">**Location format:** *PACK*</span></span>
    - <span data-ttu-id="ab64e-148">**Tipo di ubicazione:** *ORDINAMENTO*</span><span class="sxs-lookup"><span data-stu-id="ab64e-148">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="ab64e-149">**Usa rilevamento targa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="ab64e-149">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="ab64e-150">**Consenti articoli combinati:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="ab64e-150">**Allow mixed items:** *Yes*</span></span>
    - <span data-ttu-id="ab64e-151">**Consenti stati inventario combinati:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="ab64e-151">**Allow mixed inventory statuses:** *Yes*</span></span>

1. <span data-ttu-id="ab64e-152">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-152">Select **Save**.</span></span>

### <a name="locations"></a><span data-ttu-id="ab64e-153">Ubicazioni</span><span class="sxs-lookup"><span data-stu-id="ab64e-153">Locations</span></span>

1. <span data-ttu-id="ab64e-154">Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-154">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="ab64e-155">Deselezionare la casella di controllo **Genera cifre di controllo per ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-155">Clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="ab64e-156">Nel riquadro azioni, selezionare **Nuovo** , quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-156">On the Action Pane, select **New** , and then set the following values:</span></span>

    - <span data-ttu-id="ab64e-157">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="ab64e-157">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="ab64e-158">**Ubicazione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-158">**Location:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-159">**ID profilo ubicazione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-159">**Location profile ID:** *Sort*</span></span>

1. <span data-ttu-id="ab64e-160">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-160">Select **Save**.</span></span>

### <a name="packing-profiles"></a><span data-ttu-id="ab64e-161">Profili imballaggio</span><span class="sxs-lookup"><span data-stu-id="ab64e-161">Packing profiles</span></span>

1. <span data-ttu-id="ab64e-162">Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Profili imballaggio**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-162">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="ab64e-163">Nel riquadro azioni, selezionare **Nuovo** , quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-163">On the Action Pane, select **New** , and then set the following values:</span></span>

    - <span data-ttu-id="ab64e-164">**ID profilo imballaggio:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-164">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-165">**Descrizione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-165">**Description:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-166">**Criteri imballaggio contenitore:** Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-166">**Container packing policy:** Leave this field blank.</span></span>
    - <span data-ttu-id="ab64e-167">**Modalità ID contenitore:** *Auto*</span><span class="sxs-lookup"><span data-stu-id="ab64e-167">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="ab64e-168">**Tipo di contenitore:** *PALLET 48X48*</span><span class="sxs-lookup"><span data-stu-id="ab64e-168">**Container type:** *PALLET 48X48*</span></span>
    - <span data-ttu-id="ab64e-169">**Crea automaticamente il contenitore alla chiusura:** Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-169">**Autocreate container at container close:** Leave this field blank.</span></span>

1. <span data-ttu-id="ab64e-170">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-170">Select **Save**.</span></span>

### <a name="wave-step-codes"></a><span data-ttu-id="ab64e-171">Codici del passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="ab64e-171">Wave step codes</span></span>

<span data-ttu-id="ab64e-172">Se la funzionalità *Codice passaggio ondata a livello di organizzazione* è stata attivata, impostare il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="ab64e-172">If you turned on the *Organization wide wave step code* feature, set up the following code.</span></span>

1. <span data-ttu-id="ab64e-173">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Codici passaggio ondata**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-173">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="ab64e-174">Nel riquadro azioni, selezionare **Nuovo** , quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-174">On the Action Pane, select **New** , and then set the following values:</span></span>

    - <span data-ttu-id="ab64e-175">**Codice passaggio ondata:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-175">**Wave step code:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-176">**Descrizione passaggio ondata:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-176">**Wave step description:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-177">**Tipo di passaggio ondata:** *Modello di ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-177">**Wave step type:** *Sort template*</span></span>

1. <span data-ttu-id="ab64e-178">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-178">Select **Save**.</span></span>

### <a name="outbound-sorting-template"></a><span data-ttu-id="ab64e-179">Modello di ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="ab64e-179">Outbound sorting template</span></span>

<span data-ttu-id="ab64e-180">Il modello di ordinamento controlla se vengono create posizioni di ordinamento, quali criteri vengono utilizzati e altri attributi del processo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-180">The sorting template controls whether sort positions are created, what criteria are used, and other attributes of the sorting process.</span></span>

1. <span data-ttu-id="ab64e-181">Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Modello di ordinamento in uscita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-181">Go to **Warehouse management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="ab64e-182">Nel riquadro azioni selezionare **Nuovo** per creare un modello di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-182">On the Action Pane, select **New** to create a sorting template.</span></span>
1. <span data-ttu-id="ab64e-183">Nell'intestazione del nuovo modello, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-183">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="ab64e-184">**ID modello di ordinamento in uscita:** *Ordinamento ondata*</span><span class="sxs-lookup"><span data-stu-id="ab64e-184">**Outbound sorting template ID:** *Wave Sort*</span></span>
    - <span data-ttu-id="ab64e-185">**Descrizione:** *Ordinamento ondate*</span><span class="sxs-lookup"><span data-stu-id="ab64e-185">**Description:** *Wave sort*</span></span>
    - <span data-ttu-id="ab64e-186">**Tipo di modello di ordinamento:** *Domanda ondata*</span><span class="sxs-lookup"><span data-stu-id="ab64e-186">**Sort template type:** *Wave demand*</span></span>

        <span data-ttu-id="ab64e-187">Questo campo definisce il processo per cui viene utilizzato il modello di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-187">This field defines the process that the sorting template is used for.</span></span> <span data-ttu-id="ab64e-188">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-188">The following values are available:</span></span>

        - <span data-ttu-id="ab64e-189">**Domanda ondata** - Il modello di ordinamento viene utilizzato per il processo *Stoccaggio a parete*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-189">**Wave demand** – The sorting template is used for the *Put to wall* process.</span></span> <span data-ttu-id="ab64e-190">Questo tipo di modello è utilizzato per ignorare la stazione del collo ed elaborare le scorte direttamente dall'ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-190">This template type is used to bypass the pack station and process inventory directly out of the wave.</span></span> <span data-ttu-id="ab64e-191">È possibile utilizzare questo tipo solo se il metodo di elaborazione dell'ondata di **ordinamento** , è incluso nel modello di ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-191">You can use this type only if the **sorting** wave process method is included in the wave template.</span></span>
        - <span data-ttu-id="ab64e-192">**Contenitore** - Il modello di ordinamento viene utilizzato per il processo *Costruzione di pallet dopo imballaggio*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-192">**Container** – The sorting template is used for the *Pallet building after packing* process.</span></span> <span data-ttu-id="ab64e-193">Questo tipo di modello viene utilizzato per elaborare i contenitori che sono chiusi nel centro di imballaggio e devono essere ordinati in pallet.</span><span class="sxs-lookup"><span data-stu-id="ab64e-193">This template type is used to process containers that are closed at the pack station and must be sorted onto pallets.</span></span>

    - <span data-ttu-id="ab64e-194">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="ab64e-194">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="ab64e-195">**Ubicazione:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-195">**Location:** *Sort*</span></span>

1. <span data-ttu-id="ab64e-196">Nella Scheda dettaglio **Generale** , imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-196">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ab64e-197">**Ordina tipo di verifica:** selezionare *Scansione posizione*</span><span class="sxs-lookup"><span data-stu-id="ab64e-197">**Sort verification:** *Position scan*</span></span>

        <span data-ttu-id="ab64e-198">Questo campo definisce la verifica necessaria durante l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-198">This field defines the verification that is required during sorting.</span></span> <span data-ttu-id="ab64e-199">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-199">The following values are available:</span></span>

        - <span data-ttu-id="ab64e-200">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="ab64e-200">None</span></span>
        - <span data-ttu-id="ab64e-201">Scansione targa</span><span class="sxs-lookup"><span data-stu-id="ab64e-201">License plate scan</span></span>
        - <span data-ttu-id="ab64e-202">Scansione posizione</span><span class="sxs-lookup"><span data-stu-id="ab64e-202">Position scan</span></span>

    - <span data-ttu-id="ab64e-203">**Crea lavoro in posizione chiusa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="ab64e-203">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="ab64e-204">Se questa opzione è impostata su *Sì* , quando la posizione è chiusa, verrà creato il lavoro per spostare le scorte nell'ubicazione di spedizione finale.</span><span class="sxs-lookup"><span data-stu-id="ab64e-204">If this option is set to *Yes* , when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="ab64e-205">Se è impostata su *No* , le scorte verranno immediatamente prelevate nell'ordine quando la posizione viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="ab64e-205">If it's set to *No* , inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="ab64e-206">**Assegnazione di posizione:** *Manuale*</span><span class="sxs-lookup"><span data-stu-id="ab64e-206">**Position assignment:** *Manual*</span></span>

        <span data-ttu-id="ab64e-207">Questo campo definisce il tipo di assegnazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-207">This field defines the type of position assignment.</span></span> <span data-ttu-id="ab64e-208">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-208">The following values are available:</span></span>

        - <span data-ttu-id="ab64e-209">**Manuale** - L'utente deve sempre indicare in quale posizione le scorte devono essere ordinate.</span><span class="sxs-lookup"><span data-stu-id="ab64e-209">**Manual** – The user must always indicate which position the inventory should be sorted to.</span></span>
        - <span data-ttu-id="ab64e-210">**Automatico** - Il sistema inserisce automaticamente le scorte in una posizione quando possibile, in base alle suddivisioni del modello di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-210">**Automatic** – The system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

    - <span data-ttu-id="ab64e-211">**Assegna criteri di posizione di ordinamento:** *Utilizza solo posizione vuota*</span><span class="sxs-lookup"><span data-stu-id="ab64e-211">**Assign sort position criteria:** *Only use empty position*</span></span>

        <span data-ttu-id="ab64e-212">Questo campo controlla se le scorte già presenti in posizioni di ordinamento vengono considerate durante l'assegnazione di una posizione per la domanda.</span><span class="sxs-lookup"><span data-stu-id="ab64e-212">This field controls whether inventory that is already present on sort positions is taken into account when a position is assigned for the demand.</span></span> <span data-ttu-id="ab64e-213">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-213">The following values are available:</span></span>

        - <span data-ttu-id="ab64e-214">**Utilizza solo posizione vuota** - Le posizioni che hanno già scorte associate verranno prese in considerazione</span><span class="sxs-lookup"><span data-stu-id="ab64e-214">**Only use empty position** – Positions that already have inventory associated with them will be taken into account</span></span>
        - <span data-ttu-id="ab64e-215">**Presupponi posizione vuota** - Qualsiasi scorta già presente nella posizione verrà ignorata durante l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-215">**Assume position empty** – Any inventory that is already on the position will be disregarded during assignment.</span></span> <span data-ttu-id="ab64e-216">Verranno utilizzate tutte le posizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="ab64e-216">All available positions will be used.</span></span>

    - <span data-ttu-id="ab64e-217">**Codice passaggio ondata:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-217">**Wave step code:** *Sort*</span></span>

        <span data-ttu-id="ab64e-218">Se la funzionalità *Codice passaggio ondata a livello di organizzazione* è attivata, anche il codice passaggio ondata *Ordinamento* deve essere impostato nei codici passaggio ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-218">If the *Organization wide wave step code* feature is turned on, the *Sort* wave step code must also be set up in wave step codes.</span></span>

    - <span data-ttu-id="ab64e-219">**Chiudi automaticamente posizione ordinamento:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="ab64e-219">**Auto close sort position:** *Yes*</span></span>

        <span data-ttu-id="ab64e-220">Se questa opzione è impostata su *Sì* , la posizione di ordinamento verrà chiusa automaticamente quando tutto il lavoro che arriva in quella posizione risulta completato.</span><span class="sxs-lookup"><span data-stu-id="ab64e-220">If this option is set to *Yes* , the sort position will automatically be closed when all work that comes to the position has been completed.</span></span>

    - <span data-ttu-id="ab64e-221">**Numero di posizioni di ordinamento:** *3*</span><span class="sxs-lookup"><span data-stu-id="ab64e-221">**Number of sort positions:** *3*</span></span>

        <span data-ttu-id="ab64e-222">Questo campo definisce il numero massimo di posizioni di ordinamento che il sistema creerà.</span><span class="sxs-lookup"><span data-stu-id="ab64e-222">This field defines the maximum number of sort positions that the system will create.</span></span>

    - <span data-ttu-id="ab64e-223">**Prefisso posizione di ordinamento:** *SP-*</span><span class="sxs-lookup"><span data-stu-id="ab64e-223">**Sort position prefix:** *SP-*</span></span>

        <span data-ttu-id="ab64e-224">Questo campo definisce il prefisso che il sistema assegna prima del numero di posizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-224">This field defines the prefix that the system assigns before the position number.</span></span>

    - <span data-ttu-id="ab64e-225">**Imballa automaticamente posizione ordinamento:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="ab64e-225">**Auto pack sort position:** *Yes*</span></span>

        <span data-ttu-id="ab64e-226">Se questa opzione è impostata su *Sì* le scorte nella posizione di ordinamento verranno imballate in un contenitore quando la posizione è chiusa.</span><span class="sxs-lookup"><span data-stu-id="ab64e-226">If this option is set to *Yes* , the inventory on the sort position will be packed into a container when the position is closed.</span></span>

    - <span data-ttu-id="ab64e-227">**ID profilo imballaggio:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-227">**Packing profile ID:** *Sort*</span></span>

        <span data-ttu-id="ab64e-228">Questo campo definisce il profilo di imballaggio che verrà utilizzato quando la posizione di ordinamento viene imballata in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="ab64e-228">This field defines the packing profile that will be used when the sort position is packed into a container.</span></span>

1. <span data-ttu-id="ab64e-229">Nel riquadro azioni selezionare **Modifica query** per specificare i criteri utilizzati per questo modello di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-229">On the Action Pane, select **Edit query** to specify the criteria that are used for this sorting template.</span></span>
1. <span data-ttu-id="ab64e-230">Nella finestra di dialogo della query, nella scheda **Ordinamento** , selezionare **Nuovo** per aggiungere una riga e quindi impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-230">In the query dialog box, on the **Sorting** tab, select **New** to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="ab64e-231">**Tabella:** *Carica dettagli*</span><span class="sxs-lookup"><span data-stu-id="ab64e-231">**Table:** *Load details*</span></span>
    - <span data-ttu-id="ab64e-232">**Tabella derivata:** *Carica dettagli*</span><span class="sxs-lookup"><span data-stu-id="ab64e-232">**Derived table:** *Load details*</span></span>
    - <span data-ttu-id="ab64e-233">**Campo:** *ID spedizione*</span><span class="sxs-lookup"><span data-stu-id="ab64e-233">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="ab64e-234">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="ab64e-234">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="ab64e-235">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-235">Select **OK**.</span></span>
1. <span data-ttu-id="ab64e-236">È possibile che venga visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?".</span><span class="sxs-lookup"><span data-stu-id="ab64e-236">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="ab64e-237">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-237">Select **Yes**.</span></span>

    <span data-ttu-id="ab64e-238">Il pulsante **Interruzioni del modello di ordinamento in uscita** nel riquadro azioni diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="ab64e-238">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="ab64e-239">Nel riquadro azioni selezionare **Interruzioni del modello di ordinamento in uscita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-239">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="ab64e-240">Selezionare la casella di controllo **Raggruppa per campo** per raggruppare l'ID spedizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-240">Select the **Group by field** check box to group by shipment ID.</span></span>

    <span data-ttu-id="ab64e-241">Questa impostazione creerà una posizione di ordinamento per spedizione che è un contenitore nell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-241">This setting will create one sort position per shipment that is a container in the wave.</span></span>

1. <span data-ttu-id="ab64e-242">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-242">Select **OK**.</span></span>

### <a name="wave-process-methods"></a><span data-ttu-id="ab64e-243">Metodi di elaborazione ondata</span><span class="sxs-lookup"><span data-stu-id="ab64e-243">Wave process methods</span></span>

1. <span data-ttu-id="ab64e-244">Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-244">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="ab64e-245">Nel riquadro azioni, seleziona **Rigenera metodi**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-245">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="ab64e-246">Il metodo **Ordinamento** viene aggiunto all'elenco dei metodi disponibili e il tipo di metodo di ondata *Spedizione* è selezionato per tale metodo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-246">The **sorting** method is added to the list of available methods, and the *Shipping* wave template type is selected for it.</span></span>

### <a name="wave-templates"></a><span data-ttu-id="ab64e-247">Modelli ondata</span><span class="sxs-lookup"><span data-stu-id="ab64e-247">Wave templates</span></span>

<span data-ttu-id="ab64e-248">Modificare il modello di ondata utilizzato per l'ordinamento della domanda ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-248">Edit the wave template that is used for wave demand sorting.</span></span>

1. <span data-ttu-id="ab64e-249">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-249">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="ab64e-250">Nel campo **Tipo di modello ondata** selezionare *Spedizione*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-250">In the **Wave template type** field, select *Shipping*.</span></span>
1. <span data-ttu-id="ab64e-251">Selezionare il modello **62 Spedizione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-251">Select the existing **62 Shipping default** template.</span></span>
1. <span data-ttu-id="ab64e-252">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-252">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ab64e-253">Nella Scheda dettaglio **Generale** , apportare le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="ab64e-253">On the **General** FastTab, make the following changes:</span></span>

    - <span data-ttu-id="ab64e-254">Impostare l'opzione **Elabora ondata al rilascio in magazzino** su *No*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-254">Set the **Process wave at release to warehouse** option to *No*.</span></span>
    - <span data-ttu-id="ab64e-255">Impostare l'opzione **Assegna a ondate aperte** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-255">Set the **Assign to open waves** option to *Yes*.</span></span>

1. <span data-ttu-id="ab64e-256">Nella scheda dettaglio **Metodi** impostare il metodo **ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-256">On the **Methods** FastTab, set up the **sorting** method:</span></span>

    1. <span data-ttu-id="ab64e-257">Nella griglia **Metodi rimanenti** , selezionare **ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-257">In the **Remaining Methods** grid, select **sorting**.</span></span>
    2. <span data-ttu-id="ab64e-258">Selezionare il pulsante freccia DESTRA per spostare **ordinamento** nella griglia **Metodi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-258">Select the right arrow button to move **sorting** to the **Selected Methods** grid.</span></span>
    3. <span data-ttu-id="ab64e-259">Nella griglia **Metodi selezionati** , selezionare **ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-259">In the **Selected Methods** grid, select **sorting**.</span></span>
    4. <span data-ttu-id="ab64e-260">Impostare il campo **Codice passaggio ondata** su *Ordinamento*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-260">Set the **Wave step code** field to *Sort*.</span></span>

1. <span data-ttu-id="ab64e-261">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-261">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="ab64e-262">Voci di menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="ab64e-262">Mobile device menu items</span></span>

1. <span data-ttu-id="ab64e-263">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-263">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="ab64e-264">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-264">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ab64e-265">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-265">In the header, set the following values:</span></span>

    - <span data-ttu-id="ab64e-266">**Nome voce di menu** *Ordina*</span><span class="sxs-lookup"><span data-stu-id="ab64e-266">**Menu item name:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-267">**Titolo:** *Ordina*</span><span class="sxs-lookup"><span data-stu-id="ab64e-267">**Title:** *Sort*</span></span>
    - <span data-ttu-id="ab64e-268">**Modalità:** *Indiretta*</span><span class="sxs-lookup"><span data-stu-id="ab64e-268">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="ab64e-269">**Utilizza lavoro esistente:** *No*</span><span class="sxs-lookup"><span data-stu-id="ab64e-269">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="ab64e-270">Nella Scheda dettaglio **Generale** , imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-270">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ab64e-271">**Codice attività:** *Ordinamento in uscita*</span><span class="sxs-lookup"><span data-stu-id="ab64e-271">**Activity code:** *Outbound sorting*</span></span>
    - <span data-ttu-id="ab64e-272">**Usa guida al processo:** *Sì* (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="ab64e-272">**Use process guide:** *Yes* (default value)</span></span>
    - <span data-ttu-id="ab64e-273">**ID modello di ordinamento in uscita:** *Ordinamento ondata*</span><span class="sxs-lookup"><span data-stu-id="ab64e-273">**Outbound sorting template ID:** *Wave Sort*</span></span>

1. <span data-ttu-id="ab64e-274">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-274">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="ab64e-275">Menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="ab64e-275">Mobile device menu</span></span>

1. <span data-ttu-id="ab64e-276">Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-276">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="ab64e-277">Nell'elenco dei menu, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-277">In the list of menus, select **Outbound**.</span></span>
1. <span data-ttu-id="ab64e-278">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-278">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ab64e-279">Nella griglia **Menu e voci di menu disponibili** , trovare e selezionare la voce di menu **Ordina** appena creata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-279">In the **Available Menus And Menu Items** grid, find and select the **Sort** menu item that you just created.</span></span>
1. <span data-ttu-id="ab64e-280">Selezionare il pulsante freccia DESTRA per spostare **Ordina** nell'elenco **Struttura menu**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-280">Select the right arrow button to move **Sort** to the **Menu Structure** grid.</span></span> <span data-ttu-id="ab64e-281">In questo modo, si aggiunge la voce di menu al menu **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-281">In this way, you add the menu item to the **Outbound** menu.</span></span>
1. <span data-ttu-id="ab64e-282">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-282">Select **Save**.</span></span>

### <a name="location-directives"></a><span data-ttu-id="ab64e-283">Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="ab64e-283">Location directives</span></span>

<span data-ttu-id="ab64e-284">È necessario creare direttive sull'ubicazione per guidare il lavoro creato dopo il completamento dell'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-284">You must create location directives to guide the work that is created after the sorting is completed.</span></span>

1. <span data-ttu-id="ab64e-285">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-285">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="ab64e-286">Nel campo **Tipo ordine di lavoro** selezionare *Prelievo scorte ordinate*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-286">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="ab64e-287">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-287">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ab64e-288">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-288">In the header, set the following values:</span></span>

    - <span data-ttu-id="ab64e-289">**Sequenza:** *1*</span><span class="sxs-lookup"><span data-stu-id="ab64e-289">**Sequence:** *1*</span></span>
    - <span data-ttu-id="ab64e-290">**Nome:** *Stoccaggio in Portellone*</span><span class="sxs-lookup"><span data-stu-id="ab64e-290">**Name:** *Put to Baydoor*</span></span>

1. <span data-ttu-id="ab64e-291">Nella Scheda dettaglio **Direttive ubicazione** , impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-291">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ab64e-292">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="ab64e-292">**Work type:** *Put*</span></span>
    - <span data-ttu-id="ab64e-293">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="ab64e-293">**Site:** *6*</span></span>
    - <span data-ttu-id="ab64e-294">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="ab64e-294">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="ab64e-295">**Codice direttiva:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-295">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="ab64e-296">**Più SKU:** *No*</span><span class="sxs-lookup"><span data-stu-id="ab64e-296">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="ab64e-297">Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.</span><span class="sxs-lookup"><span data-stu-id="ab64e-297">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="ab64e-298">Nella Scheda dettaglio **Righe** , selezionare **Nuovo** , quindi impostare i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="ab64e-298">On the **Lines** FastTab, select **New** , and then set the following values.</span></span> <span data-ttu-id="ab64e-299">Accettare i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="ab64e-299">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="ab64e-300">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="ab64e-300">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="ab64e-301">**Da quantità:** *0*</span><span class="sxs-lookup"><span data-stu-id="ab64e-301">**From quantity:** *0*</span></span>
    - <span data-ttu-id="ab64e-302">**A quantità:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="ab64e-302">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="ab64e-303">Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.</span><span class="sxs-lookup"><span data-stu-id="ab64e-303">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="ab64e-304">Nella Scheda dettaglio **Azioni direttiva ubicazione** , selezionare **Nuovo** , quindi impostare i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="ab64e-304">On the **Location Directive Actions** FastTab, select **New** , and then set the following values.</span></span> <span data-ttu-id="ab64e-305">Accettare i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="ab64e-305">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="ab64e-306">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="ab64e-306">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="ab64e-307">**Nome:** *Portellone*</span><span class="sxs-lookup"><span data-stu-id="ab64e-307">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="ab64e-308">Selezionare **Salva** per rendere disponibile il pulsante **Modifica query** nella barra degli strumenti **Azioni direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-308">Select **Save** to make the **Edit query** button on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="ab64e-309">Nella scheda dettaglio **Azioni direttiva ubicazione** , seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-309">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="ab64e-310">Nella finestra di dialogo della query, nella scheda **Intervallo** , trovare la riga in cui il campo **Campo** è impostato su *Ubicazione*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-310">In the query dialog box, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="ab64e-311">Impostare il campo **Criteri** per questa riga su *Portellone*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-311">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="ab64e-312">Selezionare **OK** per confermare la modifica.</span><span class="sxs-lookup"><span data-stu-id="ab64e-312">Select **OK** to confirm the edit.</span></span>

### <a name="work-classes"></a><span data-ttu-id="ab64e-313">Classi lavoro</span><span class="sxs-lookup"><span data-stu-id="ab64e-313">Work classes</span></span>

1. <span data-ttu-id="ab64e-314">Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-314">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="ab64e-315">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-315">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ab64e-316">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-316">In the header, set the following values:</span></span>

    - <span data-ttu-id="ab64e-317">**ID classe lavoro:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-317">**Work class ID:** *Sorting*</span></span>
    - <span data-ttu-id="ab64e-318">**Descrizione** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-318">**Description:** *Sorting*</span></span>
    - <span data-ttu-id="ab64e-319">**Tipo ordine di lavoro:** *Prelievo scorte ordinate*</span><span class="sxs-lookup"><span data-stu-id="ab64e-319">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="ab64e-320">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-320">Select **Save**.</span></span>

### <a name="work-templates"></a><span data-ttu-id="ab64e-321">Modelli di lavoro</span><span class="sxs-lookup"><span data-stu-id="ab64e-321">Work templates</span></span>

1. <span data-ttu-id="ab64e-322">Andare a **Gestione magazzino \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-322">Go to **Warehouse management \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="ab64e-323">Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-323">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="ab64e-324">Nella griglia, selezionare il modello di lavoro **62 Prelievo da imballare**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-324">In the grid, select the **62 Pick to pack** work template.</span></span>
1. <span data-ttu-id="ab64e-325">Nel riquadro azioni, selezionare **Suddivisioni intestazione lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-325">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="ab64e-326">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-326">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ab64e-327">Nella riga in cui il campo **Nome campo** è impostato su *ID spedizione* , deselezionare la casella di controllo **Raggruppa per questo campo**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-327">On the line where the **Field name** field is set to *Shipment ID* , clear the **Group by this field** check box.</span></span>
1. <span data-ttu-id="ab64e-328">Selezionare **Salva** e quindi chiudere la finestra di dialogo **Suddivisioni intestazione lavoro**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-328">Select **Save** , and then close the **Work header breaks** dialog box.</span></span>
1. <span data-ttu-id="ab64e-329">Nel campo **Tipo ordine di lavoro** selezionare *Prelievo scorte ordinate*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-329">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="ab64e-330">Selezionare **Nuovo** per creare un modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ab64e-330">Select **New** to create a work template.</span></span>
1. <span data-ttu-id="ab64e-331">Nella sezione **Panoramica** , impostare i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="ab64e-331">In the **Overview** section, set the following values.</span></span> <span data-ttu-id="ab64e-332">Accettare i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="ab64e-332">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="ab64e-333">**Modello di lavoro:** *Prelievo ordinato*</span><span class="sxs-lookup"><span data-stu-id="ab64e-333">**Work template:** *Sorted picking*</span></span>
    - <span data-ttu-id="ab64e-334">**Descrizione modello di lavoro:** *Prelievo ordinato*</span><span class="sxs-lookup"><span data-stu-id="ab64e-334">**Work template description:** *Sorted picking*</span></span>

1. <span data-ttu-id="ab64e-335">Selezionare **Salva** per rendere disponibile la Scheda dettaglio **Dettagli modello di lavoro** .</span><span class="sxs-lookup"><span data-stu-id="ab64e-335">Select **Save** to make the **Work Template Details** section available.</span></span>
1. <span data-ttu-id="ab64e-336">Nella sezione **Dettagli modello di lavoro** , si creeranno due righe.</span><span class="sxs-lookup"><span data-stu-id="ab64e-336">In the **Work Template Details** section, you will create two lines.</span></span> <span data-ttu-id="ab64e-337">Selezionare **Nuovo** , quindi impostare i seguenti valori per la riga 1:</span><span class="sxs-lookup"><span data-stu-id="ab64e-337">Select **New** , and then set the following values for line 1:</span></span>

    - <span data-ttu-id="ab64e-338">**Tipo di lavoro:** *Prelevare*</span><span class="sxs-lookup"><span data-stu-id="ab64e-338">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="ab64e-339">**Obbligatorio:** Selezionato (= *Sì* )</span><span class="sxs-lookup"><span data-stu-id="ab64e-339">**Mandatory:** Selected (= *Yes* )</span></span>
    - <span data-ttu-id="ab64e-340">**ID classe lavoro:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-340">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="ab64e-341">Selezionare di nuovo **Nuovo** , quindi impostare i seguenti valori per la riga 2:</span><span class="sxs-lookup"><span data-stu-id="ab64e-341">Select **New** again, and then set the following values for line 2:</span></span>

    - <span data-ttu-id="ab64e-342">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="ab64e-342">**Work type:** *Put*</span></span>
    - <span data-ttu-id="ab64e-343">**Obbligatorio:** Selezionato (= *Sì* )</span><span class="sxs-lookup"><span data-stu-id="ab64e-343">**Mandatory:** Selected (= *Yes* )</span></span>
    - <span data-ttu-id="ab64e-344">**ID classe lavoro:** *Ordinamento*</span><span class="sxs-lookup"><span data-stu-id="ab64e-344">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="ab64e-345">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-345">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="ab64e-346">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="ab64e-346">Example scenario</span></span>

<span data-ttu-id="ab64e-347">Questo scenario simula una situazione in cui nel magazzino sono stoccati piccoli articoli in ubicazioni e devono essere imballarli in scatole prima di essere spediti e dove la funzionalità centro di imballaggio non è veramente appropriata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-347">This scenario simulates a situation where the warehouse stores small items in locations and must pack them into boxes before they are shipped, and where packing station functionality isn't really suitable.</span></span> <span data-ttu-id="ab64e-348">I lavoratori prelevano contemporaneamente ordini per più clienti e indirizzi diversi per aumentare la velocità di prelievo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-348">Workers pick orders for multiple customers and different addresses at the same time to increase the picking speed.</span></span> <span data-ttu-id="ab64e-349">Dopo che il prelievo è stato completato, i lavoratori arrivano all'ubicazione di ordinamento, dove gli articoli prelevati possono essere ordinati nella scatola corretta, in base ai criteri richiesti.</span><span class="sxs-lookup"><span data-stu-id="ab64e-349">After picking has been completed, the workers arrive at the sorting location, where the picked items can be sorted to the correct box, based on required criteria.</span></span> <span data-ttu-id="ab64e-350">In questo esempio, l'ID spedizione verrà utilizzato per determinare la scatola corretta, poiché ogni spedizione ha un indirizzo diverso.</span><span class="sxs-lookup"><span data-stu-id="ab64e-350">In this example, the shipment ID will be used to determine the correct box, because each shipment has a different address.</span></span> <span data-ttu-id="ab64e-351">Dopo che tutti gli articoli del carico vengono imballati e ordinati per spedizione, le scatole verranno spostate nell'area di gestione temporanea e infine caricate su un camion.</span><span class="sxs-lookup"><span data-stu-id="ab64e-351">After all items from the load are packed and sorted by shipment, the boxes will be moved to the staging area and eventually loaded onto a truck.</span></span>

<span data-ttu-id="ab64e-352">Prima di iniziare lo scenario, assicurarsi che tutte le funzionalità standard del magazzino siano impostate correttamente per il proprio magazzino.</span><span class="sxs-lookup"><span data-stu-id="ab64e-352">Before you start the scenario, make sure that all standard warehouse functionality is set up correctly for your warehouse.</span></span> <span data-ttu-id="ab64e-353">Il magazzino Contoso standard *62* è usato per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-353">Standard Contoso warehouse *62* is used for this purpose.</span></span> <span data-ttu-id="ab64e-354">Le configurazioni standard non sono state modificate, oltre a quanto descritto nell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-354">Standard configurations haven't been changed, besides what is described in the setup.</span></span>

### <a name="create-demand"></a><span data-ttu-id="ab64e-355">Creare domanda</span><span class="sxs-lookup"><span data-stu-id="ab64e-355">Create demand</span></span>

<span data-ttu-id="ab64e-356">Prima di poter dimostrare la funzionalità, è necessario creare una domanda.</span><span class="sxs-lookup"><span data-stu-id="ab64e-356">Before the functionality can be demonstrated, you must create some demand.</span></span> <span data-ttu-id="ab64e-357">Per questo scenario, verranno creati tre ordini cliente per tre diversi clienti per simulare indirizzi di consegna diversi.</span><span class="sxs-lookup"><span data-stu-id="ab64e-357">For this scenario, you will create three sales orders for three different customers to simulate different delivery addresses.</span></span> <span data-ttu-id="ab64e-358">In questo modo, si creeranno tre spedizioni distinte.</span><span class="sxs-lookup"><span data-stu-id="ab64e-358">In this way, you will create three separate shipments.</span></span>

<span data-ttu-id="ab64e-359">Prima di creare ordini cliente e spedizioni, verificare che le ubicazioni di prelievo dispongano di scorte sufficienti per tutti gli articoli degli ordini.</span><span class="sxs-lookup"><span data-stu-id="ab64e-359">Before you create sales orders and shipments, make sure that the pick locations have enough inventory for all the items on the orders.</span></span> <span data-ttu-id="ab64e-360">Rivedere le impostazioni della direttiva di ubicazione per confermare le ubicazioni di prelievo utilizzate per il prelievo degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="ab64e-360">Review the location directive settings to confirm the picking locations that are used for sales order picking.</span></span> <span data-ttu-id="ab64e-361">Se è necessario regolare le scorte, puoi creare movimenti manuali, utilizza il rifornimento o utilizza qualsiasi altro flusso, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="ab64e-361">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span> <span data-ttu-id="ab64e-362">Quindi prenotare le scorte.</span><span class="sxs-lookup"><span data-stu-id="ab64e-362">Then reserve the inventory.</span></span>

1. <span data-ttu-id="ab64e-363">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-363">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="ab64e-364">Selezionare **Nuovo** per creare un ordine cliente per ordine 1.</span><span class="sxs-lookup"><span data-stu-id="ab64e-364">Select **New** to create a sales order for order 1.</span></span>
1. <span data-ttu-id="ab64e-365">Nella finestra di dialogo **Crea ordine cliente** , imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-365">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="ab64e-366">**Cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="ab64e-366">**Customer:** *US-001*</span></span>
    - <span data-ttu-id="ab64e-367">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="ab64e-367">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="ab64e-368">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-368">Select **OK**.</span></span>
1. <span data-ttu-id="ab64e-369">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-369">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ab64e-370">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-370">Set the following values:</span></span>

    - <span data-ttu-id="ab64e-371">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ab64e-371">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="ab64e-372">**Quantità:** *5*</span><span class="sxs-lookup"><span data-stu-id="ab64e-372">**Quantity:** *5*</span></span>

1. <span data-ttu-id="ab64e-373">Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-373">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="ab64e-374">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="ab64e-374">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="ab64e-375">**Quantità:** *10*</span><span class="sxs-lookup"><span data-stu-id="ab64e-375">**Quantity:** *10*</span></span>

1. <span data-ttu-id="ab64e-376">Ripetere i passaggi seguenti per ciascuna riga di vendita nell'ordine per prenotare le relative scorte:</span><span class="sxs-lookup"><span data-stu-id="ab64e-376">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="ab64e-377">Nella scheda dettaglio **Righe ordine cliente** , nel menu **Scorte** , seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-377">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="ab64e-378">Nella pagina **Prenotazione** selezionare **Prenota lotto** e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ab64e-378">On the **Reservation** page, select **Reserve lot** , and then close the page.</span></span>
    1. <span data-ttu-id="ab64e-379">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-379">Select **Save**.</span></span>

1. <span data-ttu-id="ab64e-380">Selezionare **Nuovo** per creare un ordine cliente per ordine 2.</span><span class="sxs-lookup"><span data-stu-id="ab64e-380">Select **New** to create a sales order for order 2.</span></span>
1. <span data-ttu-id="ab64e-381">Nella finestra di dialogo **Crea ordine cliente** , imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-381">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="ab64e-382">**Cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="ab64e-382">**Customer:** *US-004*</span></span>
    - <span data-ttu-id="ab64e-383">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="ab64e-383">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="ab64e-384">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-384">Select **OK**.</span></span>
1. <span data-ttu-id="ab64e-385">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-385">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ab64e-386">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-386">Set the following values:</span></span>

    - <span data-ttu-id="ab64e-387">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ab64e-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="ab64e-388">**Quantità:** *7*</span><span class="sxs-lookup"><span data-stu-id="ab64e-388">**Quantity:** *7*</span></span>

1. <span data-ttu-id="ab64e-389">Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-389">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="ab64e-390">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="ab64e-390">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="ab64e-391">**Quantità:** *3*</span><span class="sxs-lookup"><span data-stu-id="ab64e-391">**Quantity:** *3*</span></span>

1. <span data-ttu-id="ab64e-392">Ripetere i passaggi seguenti per ciascuna riga di vendita nell'ordine per prenotare le relative scorte:</span><span class="sxs-lookup"><span data-stu-id="ab64e-392">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="ab64e-393">Nella scheda dettaglio **Righe ordine cliente** , nel menu **Scorte** , seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-393">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="ab64e-394">Nella pagina **Prenotazione** selezionare **Prenota lotto** e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ab64e-394">On the **Reservation** page, select **Reserve lot** , and then close the page.</span></span>
    1. <span data-ttu-id="ab64e-395">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-395">Select **Save**.</span></span>

1. <span data-ttu-id="ab64e-396">Selezionare **Nuovo** per creare un ordine cliente per ordine 3.</span><span class="sxs-lookup"><span data-stu-id="ab64e-396">Select **New** to create a sales order for order 3.</span></span>
1. <span data-ttu-id="ab64e-397">Nella finestra di dialogo **Crea ordine cliente** , imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ab64e-397">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="ab64e-398">**Cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="ab64e-398">**Customer:** *US-007*</span></span>
    - <span data-ttu-id="ab64e-399">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="ab64e-399">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="ab64e-400">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-400">Select **OK**.</span></span>
1. <span data-ttu-id="ab64e-401">Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-401">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ab64e-402">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab64e-402">Set the following values:</span></span>

    - <span data-ttu-id="ab64e-403">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ab64e-403">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="ab64e-404">**Quantità:** *8*</span><span class="sxs-lookup"><span data-stu-id="ab64e-404">**Quantity:** *8*</span></span>

1. <span data-ttu-id="ab64e-405">Per prenotare le scorte per la riga di vendita, attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ab64e-405">Follow these steps to reserve inventory for the sales line:</span></span>

    1. <span data-ttu-id="ab64e-406">Nella scheda dettaglio **Righe ordine cliente** , nel menu **Scorte** , seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-406">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="ab64e-407">Nella pagina **Prenotazione** selezionare **Prenota lotto** e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ab64e-407">On the **Reservation** page, select **Reserve lot** , and then close the page.</span></span>
    1. <span data-ttu-id="ab64e-408">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-408">Select **Save**.</span></span>

<span data-ttu-id="ab64e-409">Completare la seguente procedura per rilasciare ogni ordine cliente al magazzino.</span><span class="sxs-lookup"><span data-stu-id="ab64e-409">Complete the following procedure to release each sales order to the warehouse.</span></span> <span data-ttu-id="ab64e-410">Verranno create tre spedizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="ab64e-410">Three different shipments will be created.</span></span> <span data-ttu-id="ab64e-411">Quindi si aggiungeranno tutte e tre le spedizioni a una nuova ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-411">You will then add all three shipments to one new wave.</span></span>

1. <span data-ttu-id="ab64e-412">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-412">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="ab64e-413">Nella griglia, selezionare il primo ordine cliente creato.</span><span class="sxs-lookup"><span data-stu-id="ab64e-413">In the grid, select the first sales order that you created.</span></span>
1. <span data-ttu-id="ab64e-414">Nel riquadro azioni, nella scheda **Magazzino** , seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-414">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="ab64e-415">Viene visualizzato un messaggio informativo che mostra l'ID ondata e l'ID spedizione creati.</span><span class="sxs-lookup"><span data-stu-id="ab64e-415">You receive an informational message that shows the wave ID and shipment ID that were created.</span></span>

1. <span data-ttu-id="ab64e-416">Ripetere i passaggi precedenti per rilasciare gli ordini cliente 2 e 3 al magazzino.</span><span class="sxs-lookup"><span data-stu-id="ab64e-416">Repeat the previous steps to release sales orders 2 and 3 to the warehouse.</span></span> <span data-ttu-id="ab64e-417">Si noti che il messaggio informativo visualizzato indica che è stata aggiunta una spedizione all'ondata creata al momento del rilascio dell'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="ab64e-417">Notice that the informational message that you receive indicates that a shipment has been added to the wave that was created when you released sales order 1.</span></span>
1. <span data-ttu-id="ab64e-418">Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-418">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="ab64e-419">Selezionare l'ID ondata creato dal rilascio degli ordini cliente per aprire la pagina **Ondate**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-419">Select the wave ID that was created from the release of the sales orders to open the **Waves** page.</span></span> <span data-ttu-id="ab64e-420">Questa pagina mostra i dettagli dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-420">This page shows the wave details.</span></span> <span data-ttu-id="ab64e-421">La Scheda dettaglio **Righe ondata** mostra le spedizioni create.</span><span class="sxs-lookup"><span data-stu-id="ab64e-421">The **Wave lines** FastTab shows the shipments that were created.</span></span>

    <span data-ttu-id="ab64e-422">È ora necessario creare lavoro per portare gli articoli dalle ubicazioni di prelievo all'ubicazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-422">You must now create work to bring items from the picking locations to the sorting location.</span></span>

1. <span data-ttu-id="ab64e-423">Nel riquadro azioni selezionare **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-423">On the Action Pane, select **Process**.</span></span>

    <span data-ttu-id="ab64e-424">Durante l'elaborazione delle ondate, il metodo di ordinamento utilizzerà il modello di ordinamento per assegnare le scorte alle posizioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-424">During wave processing, the sorting method will use the sorting template to assign the inventory to sort positions.</span></span> <span data-ttu-id="ab64e-425">Al termine dell'elaborazione dell'ondata viene visualizzato un messaggio informativo che indica che l'ondata è stata pubblicata e che il lavoro è stato creato.</span><span class="sxs-lookup"><span data-stu-id="ab64e-425">When wave processing is completed, you receive an informational message that states that the wave has been posted and work has been created.</span></span>

1. <span data-ttu-id="ab64e-426">Nel riquadro azioni, nella scheda **Ondata** , nel gruppo **Informazioni correlate** , selezionare **Lavoro** per visualizzare il lavoro creato.</span><span class="sxs-lookup"><span data-stu-id="ab64e-426">On the Action Pane, on the **Wave** tab, in the **Related information** group, select **Work** to view the work that was created.</span></span> <span data-ttu-id="ab64e-427">Prendere nota dell'ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="ab64e-427">Make a note of the work ID.</span></span>
1. <span data-ttu-id="ab64e-428">Selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Assegnazioni di posizioni di ordinamento in uscita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-428">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="ab64e-429">Nella colonna di sinistra è possibile visualizzare la posizione di ordinamento in uscita creata per ciascuna spedizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-429">In the left column, you can view the outbound sorting position that was created for each shipment.</span></span>
1. <span data-ttu-id="ab64e-430">Nella Scheda dettaglio **Criteri di posizione di ordinamento** , è possibile visualizzare l'ID spedizione per quella posizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-430">On the **Sort position criteria** FastTab, you can view the shipment ID for that position.</span></span>

<span data-ttu-id="ab64e-431">Un ID lavoro è stato creato per portare le scorte dalle ubicazioni di prelievo all'ubicazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-431">One work ID has been created to bring inventory from the picking locations to the sorting location.</span></span> <span data-ttu-id="ab64e-432">Per completare il lavoro, sarà necessario l'ID lavoro creato durante l'elaborazione dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-432">To complete the work, you will need the work ID that was created during wave processing.</span></span>

### <a name="sales-order-picking-to-the-sorting-location"></a><span data-ttu-id="ab64e-433">Prelievo dell'ordine cliente nell'ubicazione di ordinamento</span><span class="sxs-lookup"><span data-stu-id="ab64e-433">Sales order picking to the sorting location</span></span>

1. <span data-ttu-id="ab64e-434">Accedere all'app per dispositivi mobili come lavoratore nel magazzino *62*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-434">Sign in to the mobile app as a worker in warehouse *62*.</span></span>
1. <span data-ttu-id="ab64e-435">Nel menu principale, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-435">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="ab64e-436">Nel menu **In uscita** , selezionare **Prelievo vendite**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-436">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="ab64e-437">Selezionare il campo **ID** , quindi immettere l'ID lavoro dall'elaborazione dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-437">Select the **ID** field, and then enter the work ID from the wave processing.</span></span>
1. <span data-ttu-id="ab64e-438">Conferma l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-438">Confirm your entry.</span></span>

    <span data-ttu-id="ab64e-439">Successivamente, viene richiesto di immettere una targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-439">Next, you're prompted to enter a target license plate (LP).</span></span> <span data-ttu-id="ab64e-440">Si noti che la riga 1 dell'ordine di vendita 1 è ciò che deve essere prelevato e aggiunto alla targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-440">Notice that line 1 from sales order 1 is what must be picked and added to the target license plate.</span></span> <span data-ttu-id="ab64e-441">Vengono visualizzati il numero, la quantità, la descrizione e l'ubicazione di prelievo dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-441">The item number, quantity, item description, and pick location are shown.</span></span>

1. <span data-ttu-id="ab64e-442">Nel campo **Targa destinazione** , immettere il numero di targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-442">In the **Target LP** field, enter a license plate number.</span></span>

    <span data-ttu-id="ab64e-443">Si preleveranno tutte le righe create dall'ondata elaborata sulla stessa targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-443">You will pick all lines that were created from the processed wave onto the same target license plate.</span></span>

1. <span data-ttu-id="ab64e-444">Conferma l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-444">Confirm your entry.</span></span>

    <span data-ttu-id="ab64e-445">L'app per dispositivi mobili ora presenta una serie di pagine **Prelievo** che indicano l'ubicazione di prelievo e l'articolo e la quantità che devono essere prelevati.</span><span class="sxs-lookup"><span data-stu-id="ab64e-445">The mobile app now presents a series of **Pick** pages that point you to the picking location, and to the item and quantity that must be picked.</span></span> <span data-ttu-id="ab64e-446">Dopo che l'elemento prelevato è stato aggiunto alla targa, si confermerà il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-446">After the picked item is added to the license plate, you will confirm the pick work.</span></span> <span data-ttu-id="ab64e-447">L'ultima pagina sarà il lavoro per stoccare gli articoli prelevati nell'ubicazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-447">The last page will be the work to put the picked items into the sorting location.</span></span>

1. <span data-ttu-id="ab64e-448">Confermare il primo lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-448">Confirm the first pick work.</span></span>
1. <span data-ttu-id="ab64e-449">Viene visualizzato il lavoro di prelievo successivo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-449">The next pick work is shown.</span></span> <span data-ttu-id="ab64e-450">Confermare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-450">Confirm the pick.</span></span>
1. <span data-ttu-id="ab64e-451">Continuare a confermare il lavoro di prelievo rimanente.</span><span class="sxs-lookup"><span data-stu-id="ab64e-451">Continue to confirm the remaining pick work.</span></span>
1. <span data-ttu-id="ab64e-452">L'ultimo passaggio consiste nel completare il lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="ab64e-452">The last step is to complete the put work.</span></span> <span data-ttu-id="ab64e-453">Confermare lo stoccaggio nell'ubicazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-453">Confirm the put-away to the sorting location.</span></span>

    <span data-ttu-id="ab64e-454">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="ab64e-454">You receive a "Work completed" message.</span></span>

1. <span data-ttu-id="ab64e-455">Chiudere **Prelievo vendite** nell'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ab64e-455">Exit **Sales Picking** on the mobile app.</span></span>

### <a name="sortingput-to-wall"></a><span data-ttu-id="ab64e-456">Ordinamento/Stoccaggio a parete</span><span class="sxs-lookup"><span data-stu-id="ab64e-456">Sorting/put-to-wall</span></span>

<span data-ttu-id="ab64e-457">Ora che tutte le scorte sono state stoccate nella posizione di ordinamento, devono essere ordinate nell'ubicazione di ordinamento corretta.</span><span class="sxs-lookup"><span data-stu-id="ab64e-457">Now that all inventory has been put to the sorting location, it must be sorted to the correct sort position.</span></span>

1. <span data-ttu-id="ab64e-458">Accedere all'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ab64e-458">Sign in to the mobile app.</span></span>
1. <span data-ttu-id="ab64e-459">Nel menu principale, selezionare **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="ab64e-459">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="ab64e-460">Nel menu **In uscita** , selezionare **Ordina** per iniziare a ordinare gli articoli.</span><span class="sxs-lookup"><span data-stu-id="ab64e-460">On the **Outbound** menu, select **Sort** to start to sort the items.</span></span>
1. <span data-ttu-id="ab64e-461">Nel campo **TARGA/CON** , immettere la targa di destinazione del lavoro dell'ordine cliente prelevato.</span><span class="sxs-lookup"><span data-stu-id="ab64e-461">In the **LP/CON** field, enter the target license plate of the picked sales order work.</span></span>
1. <span data-ttu-id="ab64e-462">Conferma l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-462">Confirm your entry.</span></span>
1. <span data-ttu-id="ab64e-463">Immettere il numero di articolo da ordinare per primo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-463">Enter the item number to sort first.</span></span>
1. <span data-ttu-id="ab64e-464">Il sistema determina la prima posizione di ordinamento che deve essere visualizzata.</span><span class="sxs-lookup"><span data-stu-id="ab64e-464">The system determines the first sort position that should be shown.</span></span> <span data-ttu-id="ab64e-465">Confermare la posizione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-465">Confirm the sort position.</span></span>
1. <span data-ttu-id="ab64e-466">Viene richiesto di assegnare una targa alla posizione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-466">You're prompted to assign a license plate to the sort position.</span></span> <span data-ttu-id="ab64e-467">Selezionare il campo **TARGA** , immettere un numero di targa, quindi confermare l'immissione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-467">Select the **LP** field, enter a license plate number, and then confirm your entry.</span></span>

    <span data-ttu-id="ab64e-468">Poiché la posizione di ordinamento è correlata all'ID spedizione, si ordineranno gli articoli prelevati in una targa specifica per la spedizione in uscita e l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ab64e-468">Because the sort position is related to the shipment ID, you will sort the picked items into a license plate that is specific to the outbound shipment and sales order.</span></span>

    <span data-ttu-id="ab64e-469">La pagina successiva mostra l'ID articolo, la quantità, l'ID posizione di ordinamento e gli ID targa "da" (prelievo) e "a" (ordinamento).</span><span class="sxs-lookup"><span data-stu-id="ab64e-469">The next page shows the item ID, quantity, sort position ID, and the "from" (picking) and "to" (sorting) license plate IDs.</span></span> <span data-ttu-id="ab64e-470">Le informazioni contenute in questa pagina indicano di ordinare l'articolo e le quantità specificati dalla targa di prelievo nella targa di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-470">The information on this page instructs you to sort the specified item and quantities from the picking license plate into the sorting license plate.</span></span>

1. <span data-ttu-id="ab64e-471">Confermare la posizione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-471">Confirm the sort position.</span></span>
1. <span data-ttu-id="ab64e-472">Ordinare gli articoli nella prima posizione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-472">Sort the items in the first sort position.</span></span> <span data-ttu-id="ab64e-473">Al termine, il sistema indirizza alla posizione di ordinamento successiva.</span><span class="sxs-lookup"><span data-stu-id="ab64e-473">When you've finished, the system directs you to the next sort position.</span></span>
1. <span data-ttu-id="ab64e-474">Ripetere questo processo per tutte le righe prelevate nell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ab64e-474">Repeat this process for all picked lines on the work order.</span></span> <span data-ttu-id="ab64e-475">È necessario usare questo processo anche quando vi sono più righe di prelievo che hanno lo stesso numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="ab64e-475">You should also use this process when there are multiple pick lines that have the same item number.</span></span>

    <span data-ttu-id="ab64e-476">Quando si ripete questo processo per tutti gli articoli, il sistema valuta i criteri dall'articolo sottoposto a scansione successivo (riga di lavoro) e determina in quale posizione di ordinamento deve essere stoccato.</span><span class="sxs-lookup"><span data-stu-id="ab64e-476">As you repeat this process for all items, the system evaluates the criteria from the next scanned item (work line) and determines which sorting position it should be put to.</span></span> <span data-ttu-id="ab64e-477">L'articolo viene automaticamente stoccato nella posizione di ordinamento corretta.</span><span class="sxs-lookup"><span data-stu-id="ab64e-477">You're automatically directed to put the item to the correct sort position.</span></span> <span data-ttu-id="ab64e-478">A seconda della configurazione di conferma, viene anche richiesto di confermare questa azione immettendo il numero di posizione o l'ID targa.</span><span class="sxs-lookup"><span data-stu-id="ab64e-478">Depending on the confirmation setup, you're also directed to confirm this action by entering the position number or license plate ID.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab64e-479">Se l'ordinamento automatico è attivato, la sostituzione manuale non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ab64e-479">If automatic sorting is turned on, manual override isn't available.</span></span>

1. <span data-ttu-id="ab64e-480">Al termine, in Microsoft Dynamics 365 Supply Chain Management, aprire la pagina **Assegnazioni di posizioni di ordinamento in uscita** per esaminare lo stato delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="ab64e-480">When you've finished, in Microsoft Dynamics 365 Supply Chain Management, open the **Outbound sorting position assignments** page to review the status of the positions.</span></span>

    - <span data-ttu-id="ab64e-481">Se le posizioni vengono chiuse automaticamente, selezionare **Mostra chiuse** per mostrare le posizioni chiuse.</span><span class="sxs-lookup"><span data-stu-id="ab64e-481">If positions are closed automatically, select **Show closed** to show the closed positions.</span></span>
    - <span data-ttu-id="ab64e-482">Si noti che le transazioni delle posizioni di ordinamento sono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="ab64e-482">Notice that sort position transactions are shown.</span></span> <span data-ttu-id="ab64e-483">L'articolo e la quantità elaborati tramite la posizione sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="ab64e-483">The item and quantity that were processed through the position are shown.</span></span>

    <span data-ttu-id="ab64e-484">Quando si configura il modello di ordinamento in uscita, si imposta l'opzione **Chiudi automaticamente posizione ordinamento** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-484">When you set up the outbound sorting template, you set the **Auto close sort position** option to *Yes*.</span></span> <span data-ttu-id="ab64e-485">Pertanto, la posizione viene automaticamente chiusa dopo lo stoccaggio nella stessa delle ultime scorte previste.</span><span class="sxs-lookup"><span data-stu-id="ab64e-485">Therefore, the position is automatically closed after the last expected inventory is put to it.</span></span> <span data-ttu-id="ab64e-486">Lo stato delle posizioni di ordinamento è **Chiusa** ed è stato creato lavoro per spostare le scorte ordinate nell'ubicazione *Portellone*.</span><span class="sxs-lookup"><span data-stu-id="ab64e-486">The sort positions are in **Closed** status, and work has been created to move the sorted inventory to *Baydoor* location.</span></span>

1. <span data-ttu-id="ab64e-487">Completare il lavoro di prelievo delle scorte ordinate per spostare le scorte nell'ubicazione di spedizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-487">Complete the sorted inventory picking work to move the inventory to the shipping location.</span></span> <span data-ttu-id="ab64e-488">Quando le scorte sono pronte, confermarne la spedizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-488">When the inventory is ready, ship-confirm it.</span></span>

> [!NOTE]
> <span data-ttu-id="ab64e-489">Affinché il lavoro di prelievo delle scorte ordinate venga elaborato correttamente, una voce di menu del dispositivo mobile con un ID classe di lavoro dove il campo **Tipo ordine di lavoro** è impostato su *Prelievo scorte ordinate* deve essere usato per il movimento e il processo di caricamento.</span><span class="sxs-lookup"><span data-stu-id="ab64e-489">For sorted inventory picking work to be processed correctly, a mobile device menu item that has a work class ID where the **Work order type** field is set to *Sorted inventory picking* should be used for the movement and loading process.</span></span>

### <a name="manually-close-a-position-optional"></a><span data-ttu-id="ab64e-490">Chiudere manualmente una posizione (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ab64e-490">Manually close a position (optional)</span></span>

<span data-ttu-id="ab64e-491">Se le posizioni di ordinamento devono essere chiuse manualmente, l'opzione **Chiudi automaticamente posizione ordinamento** per il modello di ordinamento in uscita deve essere impostata su *No* e la chiusura deve essere eseguita prima che le scorte possano essere spostate nell'area Portellone.</span><span class="sxs-lookup"><span data-stu-id="ab64e-491">If sort positions should be closed manually, the **Auto close sort position** option for the outbound sorting template must be set to *No* , and closing must be done before inventory can be moved to the bay door area.</span></span> <span data-ttu-id="ab64e-492">Le posizioni possono essere chiuse in vari modi:</span><span class="sxs-lookup"><span data-stu-id="ab64e-492">Positions can be closed in various ways:</span></span>

- <span data-ttu-id="ab64e-493">Via l'app di magazzino:</span><span class="sxs-lookup"><span data-stu-id="ab64e-493">Via the warehouse app:</span></span>

    - <span data-ttu-id="ab64e-494">L'utente può eseguire la scansione di uno degli articoli già presenti nella posizione e quindi selezionare **Chiudi** per chiudere la posizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-494">The user can scan one of the items that are already on the position and then select **Close** to close the position.</span></span>
    - <span data-ttu-id="ab64e-495">Se l'utente esegue la scansione di un contenitore che è già stato ordinato, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="ab64e-495">If the user scans a container that has already been sorted container, an error message is shown.</span></span> <span data-ttu-id="ab64e-496">Tuttavia, l'utente può comunque continuare a chiudere la posizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-496">However, the user can still continue to close the position.</span></span>

- <span data-ttu-id="ab64e-497">Nella pagina **Assegnazioni di posizioni di ordinamento in uscita** di Microsoft Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="ab64e-497">From the Microsoft Dynamics 365 Supply Chain Management **Outbound sorting position assignments** page:</span></span>

    - <span data-ttu-id="ab64e-498">L'utente può selezionare il record della posizione di ordinamento in uscita e quindi selezionare **Chiudi posizione** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="ab64e-498">The user can select the outbound sorting position record and then select **Close position** on the Action Pane.</span></span>

## <a name="tips"></a><span data-ttu-id="ab64e-499">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="ab64e-499">Tips</span></span>

- <span data-ttu-id="ab64e-500">Gli articoli non possono essere spostati tra le posizioni dopo che sono stati assegnati a una di queste.</span><span class="sxs-lookup"><span data-stu-id="ab64e-500">Items can't be moved between positions after they have been assigned to one.</span></span> <span data-ttu-id="ab64e-501">Il sistema valuta la quantità di ogni articolo da assegnare a una specifica posizione.</span><span class="sxs-lookup"><span data-stu-id="ab64e-501">The system evaluates how many of each item should go to a specific position.</span></span>
- <span data-ttu-id="ab64e-502">Il modello di ordinamento può essere configurato per creare automaticamente contenitori quando le posizioni sono chiuse.</span><span class="sxs-lookup"><span data-stu-id="ab64e-502">Sorts template can be configured to automatically create containers when positions are closed.</span></span> <span data-ttu-id="ab64e-503">Questo approccio creerà una struttura ID contenitore standard basata sul profilo di imballaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="ab64e-503">This approach will create standard container ID structure that is based on the specified packing profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab64e-504">Dopo che il lavoro di movimento è stato creato dall'ubicazione di ordinamento, non è necessario annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="ab64e-504">After movement work has been created from the sorting location, you must not cancel the work.</span></span> <span data-ttu-id="ab64e-505">In caso contrario, la posizione e i relativi contenitori verranno eliminati dal sistema e non saranno disponibili per ulteriori elaborazioni.</span><span class="sxs-lookup"><span data-stu-id="ab64e-505">Otherwise, the position and the containers in it will be deleted from the system and unavailable for further processing.</span></span> <span data-ttu-id="ab64e-506">Anche le scorte verranno rimosse.</span><span class="sxs-lookup"><span data-stu-id="ab64e-506">The inventory will also be removed.</span></span>
