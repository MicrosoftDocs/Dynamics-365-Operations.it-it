---
title: Combinazione dimensioni prodotto ubicazione
description: Questo argomento fornisce informazioni sulla combinazione di dimensioni del prodotti di ubicazione. Questa funzionalità del profilo di ubicazione consente di migliorare la gestione dell'ubicazione quando vengono utilizzate varianti di prodotto o prodotti con dimensioni, ad esempio nel settore della moda. Consente di decidere se configurazioni, colori, stili e dimensioni possono essere combinati per un profilo di ubicazione specifico o se solo una di queste dimensioni o una combinazione di esse può essere collocata nella stessa ubicazione.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 28f59052a74b6d8b263c7a8a8b6061f2c4b34c89
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831292"
---
# <a name="location-product-dimension-mixing"></a><span data-ttu-id="6d877-105">Combinazione dimensioni prodotto ubicazione</span><span class="sxs-lookup"><span data-stu-id="6d877-105">Location product dimension mixing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d877-106">La combinazione delle dimensioni del prodotto di ubicazione è una funzionalità del profilo di ubicazione che consente di migliorare la gestione dell'ubicazione quando vengono utilizzate varianti di prodotto o prodotti con dimensioni, ad esempio nel settore della moda.</span><span class="sxs-lookup"><span data-stu-id="6d877-106">Location product dimension mixing is location profile functionality that helps improve location management when product variants or products that have dimensions are used, such as in the fashion industry.</span></span> <span data-ttu-id="6d877-107">Consente di decidere se configurazioni, colori, stili e dimensioni possono essere combinati per un profilo di ubicazione specifico o se solo una di queste dimensioni o una combinazione di esse può essere collocata nella stessa ubicazione.</span><span class="sxs-lookup"><span data-stu-id="6d877-107">It lets you decide whether configurations, colors, styles, and sizes can be mixed for a specific location profile, or whether just one of these dimensions or a combination of them can be put to the same location.</span></span>

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a><span data-ttu-id="6d877-108">Attivare la funzionalità di combinazione delle dimensioni del prodotto di ubicazione</span><span class="sxs-lookup"><span data-stu-id="6d877-108">Turn on the Location product dimension mixing feature</span></span>

<span data-ttu-id="6d877-109">Prima di poter utilizzare la combinazione delle dimensioni del prodotto di ubicazione, tale funzionalità deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="6d877-109">Before you can use location product dimension mixing, the feature must be turned on in your system.</span></span> <span data-ttu-id="6d877-110">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="6d877-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6d877-111">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6d877-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6d877-112">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="6d877-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6d877-113">**Nome funzionalità:** *Combinazione dimensioni prodotto ubicazione*</span><span class="sxs-lookup"><span data-stu-id="6d877-113">**Feature name:** *Location product dimension mixing*</span></span>

## <a name="setup"></a><span data-ttu-id="6d877-114">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="6d877-114">Setup</span></span>

<span data-ttu-id="6d877-115">Ogni ubicazione del magazzino deve disporre di un profilo che descrive le proprietà dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="6d877-115">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location.</span></span> <span data-ttu-id="6d877-116">Pertanto, tutte le ubicazioni che utilizzano lo stesso profilo ubicazione saranno in grado di consentire la combinazione delle dimensioni del prodotto dopo che è stato impostato.</span><span class="sxs-lookup"><span data-stu-id="6d877-116">Therefore, all locations that use the same location profile will be able to allow product dimension mixing after it has been set up.</span></span>

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a><span data-ttu-id="6d877-117">Configurare i profili di ubicazione per consentire la combinazione delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="6d877-117">Configure location profiles to allow product dimension mixing</span></span>

1. <span data-ttu-id="6d877-118">Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6d877-118">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="6d877-119">Nell'elenco dei profili di ubicazione, seleziona **BULK**.</span><span class="sxs-lookup"><span data-stu-id="6d877-119">In the list of location profiles, select **BULK**.</span></span>
1. <span data-ttu-id="6d877-120">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6d877-120">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6d877-121">Nella Scheda dettaglio **Generale**, imposta l'opzione **Abilita combinazione specifica dimensioni prodotto di ubicazione** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="6d877-121">On the **General** FastTab, set the **Enable location product dimension specific mixing** option to *Yes*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d877-122">È possibile impostare questa opzione su *Sì* solo se l'opzione **Consenti articoli combinati** è impostata su *No*.</span><span class="sxs-lookup"><span data-stu-id="6d877-122">You can set this option to *Yes* only if the **Allow mixed items** option is set to *No*.</span></span>

1. <span data-ttu-id="6d877-123">Nella Scheda dettaglio **Combinazione dimensioni prodotto consentita**, imposta l'opzione **Dimensione** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="6d877-123">On the **Allowed product dimension mixing** FastTab, set the **Size** option to *Yes*.</span></span> <span data-ttu-id="6d877-124">Nello scenario descritto in questo argomento, la combinazione può essere eseguita solo per prodotti che hanno valori diversi per **Dimensione**.</span><span class="sxs-lookup"><span data-stu-id="6d877-124">In the scenario that is described in this topic, mixing can be done only for products that have different **Size** dimensions.</span></span> <span data-ttu-id="6d877-125">Tuttavia, sono disponibili anche altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="6d877-125">However, other options are also available.</span></span>
1. <span data-ttu-id="6d877-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6d877-126">Select **Save**.</span></span>

### <a name="create-a-new-product-master-and-product-variants"></a><span data-ttu-id="6d877-127">Creare una nuova rappresentazione generale prodotto e varianti di prodotto</span><span class="sxs-lookup"><span data-stu-id="6d877-127">Create a new product master and product variants</span></span>

1. <span data-ttu-id="6d877-128">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Rappresentazioni generali prodotto**.</span><span class="sxs-lookup"><span data-stu-id="6d877-128">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="6d877-129">Nel riquadro azioni seleziona **Nuova** per creare una rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="6d877-129">On the Action Pane, select **New** to create a product master.</span></span>
1. <span data-ttu-id="6d877-130">Nella finestra di dialogo **Nuovo prodotto**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-130">In the **New product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6d877-131">**Tipo di prodotto:** *Articolo*</span><span class="sxs-lookup"><span data-stu-id="6d877-131">**Product type:** *Item*</span></span>
    - <span data-ttu-id="6d877-132">**Sottotipo di prodotto:** *Rappresentazione generale prodotto*</span><span class="sxs-lookup"><span data-stu-id="6d877-132">**Product subtype:** *Product master*</span></span>
    - <span data-ttu-id="6d877-133">**Numero prodotto:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="6d877-133">**Product number:** *B0001*</span></span>
    - <span data-ttu-id="6d877-134">**Nome prodotto:** *Dimensione B0001*</span><span class="sxs-lookup"><span data-stu-id="6d877-134">**Product name:** *B0001 Size*</span></span>
    - <span data-ttu-id="6d877-135">**Gruppo di dimensioni prodotto:** *Dimensione*</span><span class="sxs-lookup"><span data-stu-id="6d877-135">**Product dimension group:** *Size*</span></span>
    - <span data-ttu-id="6d877-136">**Tecnologia di configurazione:** *Varianti predefinite*</span><span class="sxs-lookup"><span data-stu-id="6d877-136">**Configuration technology:** *Predefined variant*</span></span>

1. <span data-ttu-id="6d877-137">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d877-137">Select **OK**.</span></span>
1. <span data-ttu-id="6d877-138">Nella pagina **Dettagli prodotto**, nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-138">On the **Product details** page, on the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6d877-139">**Genera varianti automaticamente:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6d877-139">**Generate variants automatically:** *Yes*</span></span>
    - <span data-ttu-id="6d877-140">**Gruppo di dimensioni:** *CASUALDHIR*</span><span class="sxs-lookup"><span data-stu-id="6d877-140">**Size group:** *CASUALDHIR*</span></span>

1. <span data-ttu-id="6d877-141">Per visualizzare le varianti predefinite, nel riquadro azioni seleziona **Varianti prodotto**.</span><span class="sxs-lookup"><span data-stu-id="6d877-141">To view the predefined variants, on the Action Pane, select **Product variants**.</span></span>

    <span data-ttu-id="6d877-142">La pagina **Varianti prodotto** viene visualizzata e mostra un elenco di varianti dalla configurazione del gruppo di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6d877-142">The **Product variants** page appears and shows a list of variants from the configuration of the size group.</span></span>

### <a name="release-products-to-the-usmf-company"></a><span data-ttu-id="6d877-143">Rilasciare i prodotti a società USMF</span><span class="sxs-lookup"><span data-stu-id="6d877-143">Release products to the USMF company</span></span>

1. <span data-ttu-id="6d877-144">Nel riquadro azioni seleziona **Rilascia prodotti**.</span><span class="sxs-lookup"><span data-stu-id="6d877-144">On the Action Pane, select **Release products**.</span></span>
1. <span data-ttu-id="6d877-145">Nella pagina **Seleziona prodotti da rilasciare**, Verifica che il numero di prodotto *B0001* sia nell'elenco, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6d877-145">On the **Select products to release** page, confirm that product number *B0001* is in the list, and then select **Next**.</span></span>
1. <span data-ttu-id="6d877-146">Seleziona **Avanti** per confermare le varianti del prodotto da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="6d877-146">Select **Next** to confirm the product variants to release.</span></span>
1. <span data-ttu-id="6d877-147">Nella pagina **Seleziona aziende a cui rilasciare**, seleziona *USMF*, quindi seleziona **Avanti** per confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="6d877-147">On the **Select companies to release to** page, select *USMF*, and then select **Next** to confirm the selection.</span></span>
1. <span data-ttu-id="6d877-148">Nella pagina **Conferma selezione**, seleziona **Fine** per completare il rilascio.</span><span class="sxs-lookup"><span data-stu-id="6d877-148">On the **Confirm selection** page, select **Finish** to complete the release.</span></span>

    <span data-ttu-id="6d877-149">Ricevi un messaggio di tipo "Operazione completata".</span><span class="sxs-lookup"><span data-stu-id="6d877-149">You receive an "Operation completed" message.</span></span>

### <a name="update-a-released-product-in-the-usmf-company"></a><span data-ttu-id="6d877-150">Aggiornare un prodotto rilasciato nella società USMF</span><span class="sxs-lookup"><span data-stu-id="6d877-150">Update a released product in the USMF company</span></span>

1. <span data-ttu-id="6d877-151">Assicurati di aver effettuato l'accesso all'azienda **USMF**.</span><span class="sxs-lookup"><span data-stu-id="6d877-151">Make sure that you're signed in to the **USMF** company.</span></span>
1. <span data-ttu-id="6d877-152">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati** per terminare la creazione del prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="6d877-152">Go to **Product information management \> Products \> Released products** to finish creating the released product.</span></span>
1. <span data-ttu-id="6d877-153">Trova e seleziona il numero dell'articolo *B0001* per aprire la pagina **Dettagli prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="6d877-153">Find and select item number *B0001* to open the **Released product details** page.</span></span>
1. <span data-ttu-id="6d877-154">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6d877-154">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6d877-155">Nella Scheda dettaglio **Generale**, verifica che **Gruppo di modelli di articoli** sia impostato su *FIFO*.</span><span class="sxs-lookup"><span data-stu-id="6d877-155">On the **General** FastTab, make sure that the **Item model group** field is set to *FIFO*.</span></span>
1. <span data-ttu-id="6d877-156">Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Gruppi di dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="6d877-156">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Dimension groups**.</span></span>
1. <span data-ttu-id="6d877-157">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d877-157">Set the following values:</span></span>

    - <span data-ttu-id="6d877-158">**Gruppo di dimensioni di immagazzinamento:** *Ondata*</span><span class="sxs-lookup"><span data-stu-id="6d877-158">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="6d877-159">**Gruppo di dimensioni di tracciabilità:** *Nessuno*</span><span class="sxs-lookup"><span data-stu-id="6d877-159">**Tracking dimension group:** *None*</span></span>

1. <span data-ttu-id="6d877-160">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d877-160">Select **OK**.</span></span>
1. <span data-ttu-id="6d877-161">Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Gerarchia prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="6d877-161">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Reservation hierarchy**.</span></span>
1. <span data-ttu-id="6d877-162">Imposta il campo **Gerarchia prenotazioni** su *Predefinito*, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d877-162">Set the **Reservation hierarchy** field to *Default*, and then select **OK**.</span></span>
1. <span data-ttu-id="6d877-163">Nella Scheda dettaglio **Generale**, nella sezione **Amministrazione**, nota che le tue selezioni sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="6d877-163">On the **General** FastTab, in the **Administration** section, notice that your selections have been updated.</span></span>
1. <span data-ttu-id="6d877-164">Nella Scheda dettaglio **Acquisto**, nel campo **Prezzo**, immetti *10*.</span><span class="sxs-lookup"><span data-stu-id="6d877-164">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="6d877-165">Nella Scheda dettaglio **Gestisci costi** seleziona il gruppo *Audio* nel campo **Gruppo di articoli**.</span><span class="sxs-lookup"><span data-stu-id="6d877-165">On the **Manage costs** FastTab, in the **Item group** field, enter *Audio*.</span></span>
1. <span data-ttu-id="6d877-166">Nella Scheda dettaglio **Acquisto**, nel campo **Prezzo**, immetti *10*.</span><span class="sxs-lookup"><span data-stu-id="6d877-166">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="6d877-167">Nell Scheda dettaglio **Magazzino**, nel campo **ID gruppo di sequenze unità**, immetti *ea*.</span><span class="sxs-lookup"><span data-stu-id="6d877-167">On the **Warehouse** FastTab, in the **Unit sequence group ID** field, enter *ea*.</span></span>
1. <span data-ttu-id="6d877-168">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6d877-168">Select **Save**.</span></span>

### <a name="create-a-location-directive"></a><span data-ttu-id="6d877-169">Creare una direttiva ubicazione</span><span class="sxs-lookup"><span data-stu-id="6d877-169">Create a location directive</span></span>

1. <span data-ttu-id="6d877-170">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="6d877-170">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6d877-171">Nel riquadro sinistro, nel campo **Tipo di ordine di lavoro**, seleziona *Ordini fornitore*.</span><span class="sxs-lookup"><span data-stu-id="6d877-171">In the left pane, in the **Work order type** field, select *Purchase orders*.</span></span>
1. <span data-ttu-id="6d877-172">Nell'elenco, seleziona la direttiva di ubicazione denominata *24 PO diretto*.</span><span class="sxs-lookup"><span data-stu-id="6d877-172">In the list, select the location directive that is named *24 PO Direct*.</span></span>
1. <span data-ttu-id="6d877-173">Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6d877-173">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6d877-174">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6d877-175">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="6d877-175">**Sequence number:** *1*</span></span>

        <span data-ttu-id="6d877-176">La nuova riga dovrebbe trovarsi davanti alla riga precedentemente esistente.</span><span class="sxs-lookup"><span data-stu-id="6d877-176">The new line should be in front of the previously existing line.</span></span> <span data-ttu-id="6d877-177">Per apportare la modifica, utilizza i pulsanti **Sposta su** e **Sposta giù** sulla barra degli strumenti o modificare il valore **Numero progressivo** della riga esistente su *2*.</span><span class="sxs-lookup"><span data-stu-id="6d877-177">To make the change, use the **Move up** and **Move down** buttons on the toolbar, or change the existing line's **Sequence number** value to *2*.</span></span>

    - <span data-ttu-id="6d877-178">**Nome:** *Inserisci su profilo di ubicazione BULK*</span><span class="sxs-lookup"><span data-stu-id="6d877-178">**Name:** *Put to BULK Location profile*</span></span>
    - <span data-ttu-id="6d877-179">**Utilizzo ubicazioni fisse:** *Ubicazioni fisse e non fisse*</span><span class="sxs-lookup"><span data-stu-id="6d877-179">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>
    - <span data-ttu-id="6d877-180">**Consenti inventario negativo:** *Deseleziona questa casella di controllo (=No)*</span><span class="sxs-lookup"><span data-stu-id="6d877-180">**Allow negative inventory:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="6d877-181">**Lotto abilitato:** *Deseleziona questa casella di controllo (=No)*</span><span class="sxs-lookup"><span data-stu-id="6d877-181">**Batch enabled:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="6d877-182">**Strategia:** *Nessuna*</span><span class="sxs-lookup"><span data-stu-id="6d877-182">**Strategy:** *None*</span></span>

1. <span data-ttu-id="6d877-183">Con la nuova riga ancora selezionata, seleziona **Modifica query** sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="6d877-183">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="6d877-184">Nella finestra di dialogo della query, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6d877-184">In the query dialog box, on the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="6d877-185">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-185">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6d877-186">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="6d877-186">**Table:** *Locations*</span></span>
    - <span data-ttu-id="6d877-187">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="6d877-187">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="6d877-188">**Campo:** *ID profilo ubicazione*</span><span class="sxs-lookup"><span data-stu-id="6d877-188">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="6d877-189">**Criteri:** *BULK*</span><span class="sxs-lookup"><span data-stu-id="6d877-189">**Criteria:** *BULK*</span></span>

1. <span data-ttu-id="6d877-190">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d877-190">Select **OK**.</span></span>
1. <span data-ttu-id="6d877-191">Nella pagina **Direttive ubicazione**, nel riquadro azioni, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6d877-191">On the **Location directives** page, on the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6d877-192">Nella Scheda dettaglio **Azioni direttiva ubicazione** nel campo **Strategia**, se utilizzi la strategia di ubicazione *Consolida*, la configurazione della Scheda dettaglio **Combinazione dimensioni prodotto consentita** in **Profili ubicazione** verrà sovrascritta e gli elementi verranno collocati nella stessa ubicazione anche se questo comportamento non è consentito dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="6d877-192">On the **Location Directive Actions** FastTab **Strategy** field, if you use the *Consolidate* location strategy, the setup of the **Allowed product dimension mixing** FastTab on the **Location profiles** will be overridden, and items will be put to the same location even if this behavior isn't allowed by the setup.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="6d877-193">Creare una voce di menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="6d877-193">Create a mobile device menu item</span></span>

1. <span data-ttu-id="6d877-194">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6d877-194">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6d877-195">Nel riquadro azioni seleziona **Nuovo** per creare una voce di menu da utilizzare per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6d877-195">On the Action Pane, select **New** to create a menu item to use for sorting.</span></span>
1. <span data-ttu-id="6d877-196">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-196">In the header, set the following values:</span></span>

    - <span data-ttu-id="6d877-197">**Nome voce di menu:** *Ricezione riga PO*</span><span class="sxs-lookup"><span data-stu-id="6d877-197">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="6d877-198">**Titolo:** *Ricezione riga PO*</span><span class="sxs-lookup"><span data-stu-id="6d877-198">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="6d877-199">**Modalità:** *Lavoro*</span><span class="sxs-lookup"><span data-stu-id="6d877-199">**Mode:** *Work*</span></span>
    - <span data-ttu-id="6d877-200">**Utilizza lavoro esistente:** *No*</span><span class="sxs-lookup"><span data-stu-id="6d877-200">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="6d877-201">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-201">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6d877-202">**Processo di creazione lavoro:** *Ricevimento e stoccaggio riga ordine acquisto*</span><span class="sxs-lookup"><span data-stu-id="6d877-202">**Work creation process:** *Purchase order line receiving and putaway*</span></span>
    - <span data-ttu-id="6d877-203">**Genera targa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="6d877-203">**Generate license plate:** *Yes*</span></span>

1. <span data-ttu-id="6d877-204">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6d877-204">Select **Save**.</span></span>

### <a name="configure-the-mobile-device-menu"></a><span data-ttu-id="6d877-205">Configurare i menu dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="6d877-205">Configure the mobile device menu</span></span>

1. <span data-ttu-id="6d877-206">Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="6d877-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="6d877-207">Nell'elenco dei menu, seleziona **In entrata**.</span><span class="sxs-lookup"><span data-stu-id="6d877-207">In the list of menus, select **Inbound**.</span></span>
1. <span data-ttu-id="6d877-208">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6d877-208">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6d877-209">Nell'elenco **Menu e voci di menu disponibili**, trova e seleziona la voce di menu **Ricezione riga PO**.</span><span class="sxs-lookup"><span data-stu-id="6d877-209">In the **Available Menus And Menu Items** list, find and select the **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="6d877-210">Seleziona il pulsante freccia destra per spostare la voce di menu **Ricezione riga PO** sull'elenco **Struttura menu**.</span><span class="sxs-lookup"><span data-stu-id="6d877-210">Select the right arrow button to move the **PO line receiving** menu item to the **Menu Structure** list.</span></span> <span data-ttu-id="6d877-211">In questo modo, aggiungi la nuova voce di menu al menu selezionato.</span><span class="sxs-lookup"><span data-stu-id="6d877-211">In this way, you add your new menu item to the selected menu.</span></span>
1. <span data-ttu-id="6d877-212">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6d877-212">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="6d877-213">Scenario</span><span class="sxs-lookup"><span data-stu-id="6d877-213">Scenario</span></span>

<span data-ttu-id="6d877-214">Questo scenario dimostrativo mostra come due diverse varianti di prodotto possono essere messe nella stessa ubicazione quando il profilo di ubicazione non consente articoli combinati, ma la funzionalità *Combinazione dimensioni prodotto ubicazione*.</span><span class="sxs-lookup"><span data-stu-id="6d877-214">This demo scenario shows how two different product variants can be put to the same location when the location profile doesn't allow for mixed items, but the *Location product dimension mixing* feature is enabled.</span></span> <span data-ttu-id="6d877-215">In questo caso, utilizzerai la variante **Dimensione** come criterio.</span><span class="sxs-lookup"><span data-stu-id="6d877-215">In this case, you will use the **Size** variant as the criterion.</span></span>

<span data-ttu-id="6d877-216">Prima di iniziare, assicurati che ci siano ubicazioni vuote nel magazzino *24* che usano il profilo di ubicazione *BULK*.</span><span class="sxs-lookup"><span data-stu-id="6d877-216">Before you begin, make sure that there are empty locations in warehouse *24* that use the *BULK* location profile.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="6d877-217">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="6d877-217">Create a purchase order</span></span>

<span data-ttu-id="6d877-218">Creerai un ordine fornitore che ha tre righe: due righe per lo stesso numero di prodotto ma diverse varianti **Dimensione** e una terza riga per un prodotto diverso che non ha varianti.</span><span class="sxs-lookup"><span data-stu-id="6d877-218">You will create a purchase order that has three lines: two lines for the same product number but different **Size** variants, and a third line for a different product that has no variants.</span></span>

1. <span data-ttu-id="6d877-219">Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="6d877-219">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="6d877-220">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6d877-220">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6d877-221">Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-221">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6d877-222">**Conto fornitore:** *1001*</span><span class="sxs-lookup"><span data-stu-id="6d877-222">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="6d877-223">**Magazzino:** *24*</span><span class="sxs-lookup"><span data-stu-id="6d877-223">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="6d877-224">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d877-224">Select **OK**.</span></span>
1. <span data-ttu-id="6d877-225">L'ordine fornitore viene creato e una nuova riga viene aggiunta sulla Scheda dettaglio **Righe ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="6d877-225">The purchase order is created, and a new line is added on the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="6d877-226">Prendere nota del numero di ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="6d877-226">Make a note of the purchase order number.</span></span>
1. <span data-ttu-id="6d877-227">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-227">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6d877-228">**Numero articolo:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="6d877-228">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="6d877-229">**Dimensione** *L*</span><span class="sxs-lookup"><span data-stu-id="6d877-229">**Size** *L*</span></span>
    - <span data-ttu-id="6d877-230">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="6d877-230">**Quantity:** *2*</span></span>

1. <span data-ttu-id="6d877-231">Seleziona **Aggiungi riga** sopra la griglia per aggiungere un secondo ordine fornitore, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-231">Select **Add line** above the grid to add a second purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="6d877-232">**Numero articolo:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="6d877-232">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="6d877-233">**Dimensione** *XL*</span><span class="sxs-lookup"><span data-stu-id="6d877-233">**Size** *XL*</span></span>
    - <span data-ttu-id="6d877-234">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="6d877-234">**Quantity:** *2*</span></span>

1. <span data-ttu-id="6d877-235">Seleziona **Aggiungi riga** per aggiungere una terza riga ordine fornitore, quindi imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="6d877-235">Select **Add line** to add a third purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="6d877-236">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6d877-236">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="6d877-237">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="6d877-237">**Quantity:** *1*</span></span>

<span data-ttu-id="6d877-238">1.Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6d877-238">1.Select **Save**.</span></span>

### <a name="receive-purchase-order-lines-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="6d877-239">Ricevere le righe ordine fornitore nell'app per dispositivi mobili Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="6d877-239">Receive purchase order lines in the Warehouse Management mobile app</span></span>

1. <span data-ttu-id="6d877-240">Accedi all'app per dispositivi mobili Gestione magazzino come utente abilitato per il magazzino *24*.</span><span class="sxs-lookup"><span data-stu-id="6d877-240">Sign in to the Warehouse Management mobile app as a user who is enabled for warehouse *24*.</span></span>
1. <span data-ttu-id="6d877-241">Seleziona il menu **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="6d877-241">Select the **Inbound** menu.</span></span>
1. <span data-ttu-id="6d877-242">Seleziona **Ricezione riga PO**.</span><span class="sxs-lookup"><span data-stu-id="6d877-242">Select **PO Line receiving**.</span></span>
1. <span data-ttu-id="6d877-243">Seleziona il campo **PONUM**, quindi inserisci il numero dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="6d877-243">Select the **PONUM** field, and then enter the purchase order number.</span></span>
1. <span data-ttu-id="6d877-244">Conferma l'immissione selezionando il pulsante di conferma (✔) nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="6d877-244">Confirm your entry by selecting the confirm button ( ✔ ) at the bottom of the page.</span></span>
1. <span data-ttu-id="6d877-245">Immetti il numero di riga dall'ordine fornitore che viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="6d877-245">Enter the line number from the purchase order that is being received.</span></span> <span data-ttu-id="6d877-246">Seleziona il campo **LINENUM**, quindi utilizza il tastierino numerico per immettere *1*.</span><span class="sxs-lookup"><span data-stu-id="6d877-246">Select the **LINENUM** field, and then use the number pad to enter *1*.</span></span>
1. <span data-ttu-id="6d877-247">Conferma l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="6d877-247">Confirm your entry.</span></span>
1. <span data-ttu-id="6d877-248">Immetti la quantità da ricevere.</span><span class="sxs-lookup"><span data-stu-id="6d877-248">Enter the quantity to receive.</span></span> <span data-ttu-id="6d877-249">Seleziona il segno più (**+**) due volte per aumentare il valore nel campo **Qtà** su *2*.</span><span class="sxs-lookup"><span data-stu-id="6d877-249">Select the plus sign (**+**) button two times to increase the value in the **Qty** field to *2*.</span></span>
1. <span data-ttu-id="6d877-250">Registra l'inserimento selezionando il pulsante (✔) nella parte inferiore della pagina, quindi conferma l'inserimento selezionando nuovamente il pulsante (✔).</span><span class="sxs-lookup"><span data-stu-id="6d877-250">Register your entry by selecting the button ( ✔ ) at the bottom of the page, and then confirm your entry by selecting the button ( ✔ ) again.</span></span>
1. <span data-ttu-id="6d877-251">Visualizza le informazioni nella pagina **Ordini fornitore: Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="6d877-251">View the information on the **Purchase orders: Put** page.</span></span> <span data-ttu-id="6d877-252">Questa pagina mostra il lavoro che è stato creato per lo sttoccaggio (Lavoro 1).</span><span class="sxs-lookup"><span data-stu-id="6d877-252">This page shows the work that has been created for the put-away (Work 1).</span></span>

    <span data-ttu-id="6d877-253">Viene visualizzata l'ubicazione di stoccaggio dell'articolo ricevuto, la targa, l'articolo, le dimensioni e la quantità dell'attività **Ricezione riga PO** appena completata.</span><span class="sxs-lookup"><span data-stu-id="6d877-253">The location where the received item will be put away, the license plate, the item, the size, and the quantity of the **PO Line receiving** task that you just completed are shown.</span></span>

1. <span data-ttu-id="6d877-254">Conferma il lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="6d877-254">Confirm the put-away work.</span></span>
1. <span data-ttu-id="6d877-255">Ripeti i passaggi da 4 a 11 per la riga ordine fornitore 2.</span><span class="sxs-lookup"><span data-stu-id="6d877-255">Repeat the steps 4 through 11 for the purchase order line 2.</span></span> <span data-ttu-id="6d877-256">Tuttavia, al passaggio 8, specifica una quantità di *1*.</span><span class="sxs-lookup"><span data-stu-id="6d877-256">However, in step 8, specify a quantity of *1*.</span></span>

    <span data-ttu-id="6d877-257">Il nuovo lavoro di stoccaggio (Lavoro 2) viene creato nella stessa ubicazione del Lavoro 1.</span><span class="sxs-lookup"><span data-stu-id="6d877-257">New put-away work (Work 2) is created for the same location as Work 1.</span></span>

1. <span data-ttu-id="6d877-258">Ripeti i passaggi da 4 a 11 per la riga ordine fornitore 2.</span><span class="sxs-lookup"><span data-stu-id="6d877-258">Repeat the steps 4 through 11 again for purchase order line 2.</span></span> <span data-ttu-id="6d877-259">Al passaggio 8, specifica la quantità rimanente di *1*.</span><span class="sxs-lookup"><span data-stu-id="6d877-259">In step 8, specify the remaining quantity of *1*.</span></span>

    <span data-ttu-id="6d877-260">Il nuovo lavoro di stoccaggio (Lavoro 3) viene creato nella stessa ubicazione del Lavoro 1 e Lavoro 2.</span><span class="sxs-lookup"><span data-stu-id="6d877-260">New put-away work (Work 3) is created for the same location as Work 1 and Work 2.</span></span> <span data-ttu-id="6d877-261">Questo comportamento si verifica perché viene utilizzata la strategia della direttiva di ubicazione *Consolida* e la Scheda dettaglio **Combinazione dimensioni prodotto consentita** nella configurazione *Massa* **Profili di ubicazione** consente la combinazione della variante **Dimensione** in un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="6d877-261">This behavior occurs because the *Consolidate* location directive strategy is used, and the **Allowed product dimension mixing** FastTab on the *Bulk* **Location profiles** setup allows the **Size** variant to be mixed on a location.</span></span>

1. <span data-ttu-id="6d877-262">Ripeti i passaggi da 4 a 11 per la riga ordine fornitore 3.</span><span class="sxs-lookup"><span data-stu-id="6d877-262">Repeat the steps 4 through 11 for purchase order line 3.</span></span> <span data-ttu-id="6d877-263">Nel passaggio 8, specifica una quantità di *1* per il numero articolo *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6d877-263">In step 8, specify a quantity of *1* for item number *A0001*.</span></span>

    <span data-ttu-id="6d877-264">Il nuovo lavoro di stoccaggio (Lavoro 4) viene creato per una diversa ubicazione da quella utilizzata per le righe ordine fornitore 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="6d877-264">New put-away work (Work 4) is created for a different location than the location that is used for purchase order lines 1 and 2.</span></span> <span data-ttu-id="6d877-265">Questo comportamento si verifica perché il profilo di ubicazione non consente prodotti combinati, ma consente dimensioni combinate della stessa rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="6d877-265">This behavior occurs because the location profile doesn't allow for mixed products, but it does allow for mixed dimensions of the same product master.</span></span>

1. <span data-ttu-id="6d877-266">Seleziona il pulsante Menu nella parte superiore della pagina (a volte indicato come hamburger o pulsante hamburger), quindi seleziona **Annulla** per uscire da **Ricezione riga PO**.</span><span class="sxs-lookup"><span data-stu-id="6d877-266">Select the Menu button at the top of the page (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit **PO Line receiving**.</span></span>

> [!TIP]
> <span data-ttu-id="6d877-267">Puoi ripetere questo scenario, ma questa volta, imposta **Dimensione** - *No* nella Scheda dettaglio **Consenti combinazione dimensioni prodotto** sul *BULK* **Profili di ubicazione**, in modo che nessuna delle dimensioni del prodotto possa essere combinata.</span><span class="sxs-lookup"><span data-stu-id="6d877-267">You can repeat this scenario, but this time, set **Size** - *No* under the **Allow product dimension mixing** FastTab on the *BULK* **Location profiles**, so that none of the product dimensions can be mixed.</span></span> <span data-ttu-id="6d877-268">In questo caso, quando si riceve l'ordine fornitore, ciascuna variante di prodotto verrà inserita in una nuova ubicazione.</span><span class="sxs-lookup"><span data-stu-id="6d877-268">In this case, when you receive the purchase order, each product variant will be put to a new location.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]