---
title: Posizionamento targa ubicazione
description: Il posizionamento della targa consente di vedere dove si trova una targa in un'ubicazione multi-pallet, ad esempio un'ubicazione che utilizza scaffalature per pallet a doppia profondità.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 7b0ebfb965e5a8f1bfe1857a9642d998dac2faf3
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431470"
---
# <a name="location-license-plate-positioning"></a><span data-ttu-id="8fa10-103">Posizionamento targa ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fa10-103">Location license plate positioning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8fa10-104">Il posizionamento della targa consente di vedere dove si trova una targa in un'ubicazione multi-pallet, ad esempio un'ubicazione che utilizza scaffalature per pallet a doppia profondità.</span><span class="sxs-lookup"><span data-stu-id="8fa10-104">License plate location positioning lets you see where a license plate is located in a multi-pallet location, such as a location that uses double-deep pallet racking.</span></span>

<span data-ttu-id="8fa10-105">La funzionalità aggiunge un numero progressivo a ciascuna targa che viene inserita in un'ubicazione di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="8fa10-105">The feature adds a sequence number to each license plate that is put into a storage location.</span></span> <span data-ttu-id="8fa10-106">Questo numero di sequenza viene utilizzato per ordinare le targhe nell'ubicazione di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="8fa10-106">This sequence number is used to order the license plates in the storage location.</span></span> <span data-ttu-id="8fa10-107">Pertanto, la funzionalità supporta in modo intelligente scenari in cui i clienti utilizzano un sistema di scaffalature a gravità e devono sapere, ai fini del prelievo, quale targa è rivolta verso la parte anteriore.</span><span class="sxs-lookup"><span data-stu-id="8fa10-107">Therefore, the feature intelligently supports scenarios where customers are using a gravity racking system and must know, for picking purposes, which license plate is front-facing.</span></span>

<span data-ttu-id="8fa10-108">Questo argomento presenta uno scenario che mostra come impostare e utilizzare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8fa10-108">This topic presents a scenario that shows how to set up and use the feature.</span></span>

## <a name="turn-on-the-location-license-plate-positioning-feature"></a><span data-ttu-id="8fa10-109">Attivare la funzionalità di posizionamento della targa di ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fa10-109">Turn on the Location license plate positioning feature</span></span>

<span data-ttu-id="8fa10-110">Prima di poter utilizzare il posizionamento di ubicazione della targa, tale funzionalità deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="8fa10-110">Before you can use license plate location positioning, the feature must be turned on in your system.</span></span> <span data-ttu-id="8fa10-111">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="8fa10-111">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="8fa10-112">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8fa10-112">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="8fa10-113">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="8fa10-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="8fa10-114">**Nome funzionalità:** *Posizionamento della targa di ubicazione*</span><span class="sxs-lookup"><span data-stu-id="8fa10-114">**Feature name:** *Location license plate positioning*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="8fa10-115">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="8fa10-115">Example scenario</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="8fa10-116">Rendi disponibili i dati di esempio</span><span class="sxs-lookup"><span data-stu-id="8fa10-116">Make sample data available</span></span>

<span data-ttu-id="8fa10-117">Per elaborare lo scenario utilizzando i valori suggeriti qui, devi utilizzare un sistema in cui sono installati i dati di esempio standard.</span><span class="sxs-lookup"><span data-stu-id="8fa10-117">To work through this scenario by using the values that are suggested here, you must work on a system where sample data is installed.</span></span> <span data-ttu-id="8fa10-118">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="8fa10-118">Additionally, you must select the **USMF** legal entity before you start.</span></span>

### <a name="set-up-the-feature-for-this-scenario"></a><span data-ttu-id="8fa10-119">Impostare la funzionalità per questo scenario</span><span class="sxs-lookup"><span data-stu-id="8fa10-119">Set up the feature for this scenario</span></span>

<span data-ttu-id="8fa10-120">Completa le seguenti procedure per impostare la funzionalità *Posizionamento della targa di ubicazione* per lo scenario presentato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8fa10-120">Complete the following procedures to set up the *Location license plate positioning* feature for the scenario that is presented in this topic.</span></span>

#### <a name="location-profiles"></a><span data-ttu-id="8fa10-121">Profili ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fa10-121">Location profiles</span></span>

<span data-ttu-id="8fa10-122">La funzionalità deve essere attivata nel profilo di ubicazione per ogni ubicazione in cui verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="8fa10-122">The feature must be turned on in the location profile for every location where it will be used.</span></span>

1. <span data-ttu-id="8fa10-123">Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-123">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="8fa10-124">Nell'elenco dei profili di ubicazione nel riquadro sinistro, seleziona **BULK-06**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-124">In the list of location profiles in the left pane, select **BULK-06**.</span></span>
1. <span data-ttu-id="8fa10-125">Nella Scheda dettaglio **Generale**, due nuove opzioni sono state aggiunte dalla funzionaità.</span><span class="sxs-lookup"><span data-stu-id="8fa10-125">On the **General** FastTab, two new options have been added by the feature.</span></span> <span data-ttu-id="8fa10-126">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fa10-126">Set the following values:</span></span>

    - <span data-ttu-id="8fa10-127">**Abilita posizione targa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="8fa10-127">**Enable license plate position:** *Yes*</span></span>

        <span data-ttu-id="8fa10-128">Quando questa opzione è impostata su *Sì*, la posizione della targa verrà mantenuta per le targhe nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fa10-128">When this option is set to *Yes*, the license plate position will be maintained for license plates in the location.</span></span>

    - <span data-ttu-id="8fa10-129">**Visualizza posizione targa dispositivo mobile:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="8fa10-129">**Display mobile device LP position:** *Yes*</span></span>

        <span data-ttu-id="8fa10-130">Quando questa opzione è impostata su *Sì*, la posizione della targa verrà mostrata agli utenti dei dispositivi mobili durante la regolazione e il conteggio.</span><span class="sxs-lookup"><span data-stu-id="8fa10-130">When this option is set to *Yes*, the license plate position will be shown to mobile device users during adjustment and counting.</span></span> <span data-ttu-id="8fa10-131">È possibile modificare l'impostazione di questa opzione solo quando la funzionalità è attivata.</span><span class="sxs-lookup"><span data-stu-id="8fa10-131">You can change the setting of this option only when the feature is turned on.</span></span>

1. <span data-ttu-id="8fa10-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-132">Select **Save**.</span></span>

#### <a name="location-directives"></a><span data-ttu-id="8fa10-133">Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fa10-133">Location directives</span></span>

1. <span data-ttu-id="8fa10-134">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-134">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="8fa10-135">Nel riquadro sinistro, verifica che il campo **Tipo di ordine di lavoro** sia impostato su *Ordini cliente*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-135">In the left pane, make sure that the **Work order type** field is set to *Sales orders*.</span></span>
1. <span data-ttu-id="8fa10-136">Nell'elenco delle direttive di ubicazione, seleziona **61 Prelievo ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-136">In the list of location directives, select **61 SO Pick order**.</span></span>
1. <span data-ttu-id="8fa10-137">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-137">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="8fa10-138">Nella Scheda dettaglio **Righe**, seleziona la riga che ha un valore **Numero progressivo** pari a *2*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-138">On the **Lines** FastTab, select the line that has a **Sequence number** value of *2*.</span></span>
1. <span data-ttu-id="8fa10-139">Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona la riga che ha un calore **Nome** di *Preleva per meno di pallet* (dovrebbe essere l'unica riga) e modificane il valore **Numero progressivo** su *2*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-139">On the **Location Directive Actions** FastTab, select the line that has a **Name** value of *Pick for less than pallet* (it should be the only line), and change its **Sequence number** value to *2*.</span></span>
1. <span data-ttu-id="8fa10-140">Seleziona **Nuovo** sopra la griglia per aggiungere una riga per una nuova azione di direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fa10-140">Select **New** above the grid to add a line for a new location directive action.</span></span>
1. <span data-ttu-id="8fa10-141">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8fa10-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="8fa10-142">**Numero progressivo:** *1*</span><span class="sxs-lookup"><span data-stu-id="8fa10-142">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="8fa10-143">**Nome:** *Posizione di prelievo 1*</span><span class="sxs-lookup"><span data-stu-id="8fa10-143">**Name:** *Pick position 1*</span></span>

1. <span data-ttu-id="8fa10-144">Con la nuova riga ancora selezionata, seleziona **Modifica query** sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="8fa10-144">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="8fa10-145">Nell'editor di query, seleziona la scheda **Join**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-145">In the query editor, select the **Joins** tab.</span></span>
1. <span data-ttu-id="8fa10-146">Espandi il join della tabella **Ubicazioni** per mostrare il join sulla tabella **Dimensioni inventariali**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-146">Expand the **Locations** table join to show the join to the **Inventory dimensions** table.</span></span>
1. <span data-ttu-id="8fa10-147">Espandi il join della tabella **Dimensioni inventariali** per mostrare il join sulla tabella **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-147">Expand the **Inventory dimensions** table join to show the join to the **On-hand inventory** table.</span></span>
1. <span data-ttu-id="8fa10-148">Seleziona **Dimensioni inventariali**, quindi seleziona **Aggiungi join tabella**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-148">Select **Inventory dimensions**, and then select **Add table join**.</span></span>
1. <span data-ttu-id="8fa10-149">Nell'elenco delle tabelle che appare, nella colonna **Relazione**, seleziona **Targa**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-149">In the list of tables that appears, in the **Relation** column, select **License plate (License plate)**.</span></span> <span data-ttu-id="8fa10-150">Quindi seleziona **Seleziona** per aggiungere **Targa** al join della tabella **Dimensioni inventariali**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-150">Then select **Select** to add **License plate** to the **Inventory dimensions** table join.</span></span>
1. <span data-ttu-id="8fa10-151">Mentre **Targa** è ancora selezionato, seleziona **Aggiungi join tabella**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-151">While **License plate** is still selected, select **Add table join**.</span></span>
1. <span data-ttu-id="8fa10-152">Nell'elenco delle tabelle che appare, nella colonna **Relazione**, seleziona **Posizionamento targa ubicazione (targa)**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-152">In the list of tables that appears, in the **Relation** column, select **Location license plate positioning (License plate)**.</span></span> <span data-ttu-id="8fa10-153">Quindi seleziona **Seleziona** per aggiungere **Posizionamento targa ubicazione** al join della tabella **Dimensioni inventariali**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-153">Then select **Select** to add **Location license plate positioning** to the **Inventory dimensions** table join.</span></span>

    <span data-ttu-id="8fa10-154">![Join di tabella](media/LpTableJoin.png "Join di tabella")</span><span class="sxs-lookup"><span data-stu-id="8fa10-154">![Table joins](media/LpTableJoin.png "Table joins")</span></span>

1. <span data-ttu-id="8fa10-155">Seleziona **OK** per confermare le tabelle con join aggiornate e chiudere l'editor delle query.</span><span class="sxs-lookup"><span data-stu-id="8fa10-155">Select **OK** to confirm the updated joined tables and close the query editor.</span></span>
1. <span data-ttu-id="8fa10-156">Nella scheda dettaglio **Azioni direttiva di ubicazione**, seleziona **Modifica query** nuovamente per riaprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="8fa10-156">On the **Location Directive Actions** FastTab, select **Edit query** again to reopen to the query editor.</span></span>
1. <span data-ttu-id="8fa10-157">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="8fa10-157">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="8fa10-158">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8fa10-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="8fa10-159">**Tabella:** *Posizionamento della targa di ubicazione*</span><span class="sxs-lookup"><span data-stu-id="8fa10-159">**Table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="8fa10-160">**Tabella derivata:** *Posizionamento della targa di ubicazione*</span><span class="sxs-lookup"><span data-stu-id="8fa10-160">**Derived table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="8fa10-161">**Campo:** *Posizione targa*</span><span class="sxs-lookup"><span data-stu-id="8fa10-161">**Field:** *LP Position*</span></span>
    - <span data-ttu-id="8fa10-162">**Criteri:** *1*</span><span class="sxs-lookup"><span data-stu-id="8fa10-162">**Criteria:** *1*</span></span>

    <span data-ttu-id="8fa10-163">![Nuovo intervallo](media/LpPositionCriteria.png "Nuovo intervallo")</span><span class="sxs-lookup"><span data-stu-id="8fa10-163">![New range](media/LpPositionCriteria.png "New range")</span></span>

1. <span data-ttu-id="8fa10-164">Seleziona **OK** per confermare le modifiche e chiudere l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="8fa10-164">Select **OK** to confirm your changes and close the query editor.</span></span>

### <a name="set-up-sample-data-for-this-scenario"></a><span data-ttu-id="8fa10-165">Impostare i dati di esempio per questo scenario</span><span class="sxs-lookup"><span data-stu-id="8fa10-165">Set up sample data for this scenario</span></span>

<span data-ttu-id="8fa10-166">Per questo scenario, l'utente deve accedere all'app per dispositivi mobili di magazzino utilizzando un lavoratore impostato per il magazzino *61* per eseguire lavori.</span><span class="sxs-lookup"><span data-stu-id="8fa10-166">For this scenario, the user must sign in to the warehousing mobile app by using a worker who is set up for warehouse *61* to perform work.</span></span> <span data-ttu-id="8fa10-167">L'utente deve anche completare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="8fa10-167">The user must also complete transactions.</span></span>

<span data-ttu-id="8fa10-168">Perché la funzionalità *Posizionamento targa ubicazione* aggiunge un nuovo identificatore per le posizioni della targa in un'ubicazione, è necessario prima creare alcuni dati per supportare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="8fa10-168">Because the *Location license plate positioning* feature adds a new identifier for license plate positions in a location, you must first create some data to support the scenario.</span></span>

#### <a name="spot-count-the-first-location"></a><span data-ttu-id="8fa10-169">Conteggio ciclo a campione della prima ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fa10-169">Spot-count the first location</span></span>

1. <span data-ttu-id="8fa10-170">Apri l'app per dispositivi mobili magazzino e accedi al magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-170">Open the warehousing mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="8fa10-171">Vai a **Inventario \> Conteggio ciclo a campione**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-171">Go to **Inventory \> Spot Counting**.</span></span>
1. <span data-ttu-id="8fa10-172">Nella pagina **Conteggio ciclo a campione**, imposta il campo **Posizione** su *01A01R1S1B*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-172">On the **Spot Counting** page, set the **Location** field to *01A01R1S1B*.</span></span>
1. <span data-ttu-id="8fa10-173">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-173">Select **OK**.</span></span>

    <span data-ttu-id="8fa10-174">La pagina mostra l'ubicazione che hai inserito.</span><span class="sxs-lookup"><span data-stu-id="8fa10-174">The page shows the location that you entered.</span></span> <span data-ttu-id="8fa10-175">Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"</span><span class="sxs-lookup"><span data-stu-id="8fa10-175">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="8fa10-176">Seleziona **Aggiorna** per aggiungere un conteggio nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fa10-176">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="8fa10-177">Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Articolo**, quindi immetti il valore *A0001*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-177">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0001*.</span></span>
1. <span data-ttu-id="8fa10-178">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-178">Select **OK**.</span></span>
1. <span data-ttu-id="8fa10-179">Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Targa**, quindi immetti il valore *LP1001* (o qualsiasi altro numero di targa a tua scelta).</span><span class="sxs-lookup"><span data-stu-id="8fa10-179">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1001* (or any other license plate number of your choice).</span></span>

    <span data-ttu-id="8fa10-180">La pagina **Conteggio ciclo: aggiungi nuova targa o articolo** mostra **Posizione targa 1**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-180">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="8fa10-181">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-181">Select **OK**.</span></span>

    <span data-ttu-id="8fa10-182">È ora necessario specificare la quantità dell'articolo conteggiato sulla targa.</span><span class="sxs-lookup"><span data-stu-id="8fa10-182">You must now specify the quantity of the item that is counted on the license plate.</span></span>

1. <span data-ttu-id="8fa10-183">Imposta il campo **Qtà** su *10*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-183">Set the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="8fa10-184">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-184">Select **OK**.</span></span>

    <span data-ttu-id="8fa10-185">La pagina mostra l'ubicazione che hai inserito.</span><span class="sxs-lookup"><span data-stu-id="8fa10-185">The page shows the location that you entered.</span></span> <span data-ttu-id="8fa10-186">Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"</span><span class="sxs-lookup"><span data-stu-id="8fa10-186">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="8fa10-187">Seleziona **Aggiorna** per aggiungere un altro conteggio nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fa10-187">Select **Refresh** to add another count in the location.</span></span>
1. <span data-ttu-id="8fa10-188">Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Articolo**, quindi immetti il valore *A0002*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-188">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="8fa10-189">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-189">Select **OK**.</span></span>
1. <span data-ttu-id="8fa10-190">Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Targa**, quindi immetti il valore *LP1002* (o qualsiasi altro numero di targa a tua scelta, a condizione che differisca dal numero di targa specificato in precedenza).</span><span class="sxs-lookup"><span data-stu-id="8fa10-190">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1002* (or any other license plate number of your choice, provided that it differs from the license plate number that you specified earlier).</span></span>
1. <span data-ttu-id="8fa10-191">Modifica la posizione della targa impostando il campo **Posizione targa** su *2*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-191">Change the license plate position by setting the **LP Position** field to *2*.</span></span>
1. <span data-ttu-id="8fa10-192">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-192">Select **OK**.</span></span>
1. <span data-ttu-id="8fa10-193">Specifica la quantità dell'articolo conteggiato sulla targa impostando il campo **Qtà** su *10*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-193">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="8fa10-194">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-194">Select **OK**.</span></span>

    <span data-ttu-id="8fa10-195">La pagina mostra l'ubicazione che hai inserito.</span><span class="sxs-lookup"><span data-stu-id="8fa10-195">The page shows the location that you entered.</span></span> <span data-ttu-id="8fa10-196">Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"</span><span class="sxs-lookup"><span data-stu-id="8fa10-196">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="8fa10-197">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-197">Select **OK**.</span></span>

<span data-ttu-id="8fa10-198">Il lavoro è ora completato.</span><span class="sxs-lookup"><span data-stu-id="8fa10-198">Work is now completed.</span></span>

#### <a name="spot-count-the-second-location"></a><span data-ttu-id="8fa10-199">Conteggio ciclo a campione della seconda ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fa10-199">Spot-count the second location</span></span>

1. <span data-ttu-id="8fa10-200">Nella pagina **Conteggio ciclo a campione**, imposta il campo **Posizione** su *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-200">On the **Spot Counting** page, set the **Location** field to *01A01R1S2B*.</span></span>
1. <span data-ttu-id="8fa10-201">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-201">Select **OK**.</span></span>

    <span data-ttu-id="8fa10-202">La pagina mostra l'ubicazione che hai inserito.</span><span class="sxs-lookup"><span data-stu-id="8fa10-202">The page shows the location that you entered.</span></span> <span data-ttu-id="8fa10-203">Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"</span><span class="sxs-lookup"><span data-stu-id="8fa10-203">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="8fa10-204">Seleziona **Aggiorna** per aggiungere un conteggio nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fa10-204">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="8fa10-205">Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Articolo**, quindi immetti il valore *A0002*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-205">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="8fa10-206">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-206">Select **OK**.</span></span>
1. <span data-ttu-id="8fa10-207">Nella pagina **Conteggio ciclo: aggiungi nuova targa o articolo**, seleziona il campo **Targa**, quindi immetti il valore *LP1003* (o qualsiasi altro numero di targa a tua scelta, a condizione che differisca da entrambi i numeri di targa specificati nella procedura precedente).</span><span class="sxs-lookup"><span data-stu-id="8fa10-207">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1003* (or any other license plate number of your choice, provided that it differs from the both the license plate numbers that you specified in the previous procedure).</span></span>

    <span data-ttu-id="8fa10-208">La pagina **Conteggio ciclo: aggiungi nuova targa o articolo** mostra **Posizione targa 1**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-208">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="8fa10-209">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-209">Select **OK**.</span></span>
1. <span data-ttu-id="8fa10-210">Specifica la quantità dell'articolo conteggiato sulla targa impostando il campo **Qtà** su *10*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-210">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="8fa10-211">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-211">Select **OK**.</span></span>

    <span data-ttu-id="8fa10-212">La pagina mostra l'ubicazione che hai inserito.</span><span class="sxs-lookup"><span data-stu-id="8fa10-212">The page shows the location that you entered.</span></span> <span data-ttu-id="8fa10-213">Mostra anche il seguente messaggio: "Ubucazione completata, aggiungere nuova targa o articolo?"</span><span class="sxs-lookup"><span data-stu-id="8fa10-213">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="8fa10-214">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-214">Select **OK**.</span></span>

<span data-ttu-id="8fa10-215">Il lavoro è ora completato.</span><span class="sxs-lookup"><span data-stu-id="8fa10-215">Work is now completed.</span></span>

#### <a name="work-details"></a><span data-ttu-id="8fa10-216">Dettagli lavoro</span><span class="sxs-lookup"><span data-stu-id="8fa10-216">Work details</span></span>

> [!NOTE]
> <span data-ttu-id="8fa10-217">I conteggi ciclo dell'app per dispositivi mobili creano un lavoro di conteggio ciclo in Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8fa10-217">Spot counts from the mobile app create cycle counting work in Microsoft Dynamics 365.</span></span> <span data-ttu-id="8fa10-218">Il lavoro richiede che i conteggi vengano accettati prima che vengano registrati nell'inventario.</span><span class="sxs-lookup"><span data-stu-id="8fa10-218">The work requires that the counts be accepted before they are posted to inventory.</span></span>

1. <span data-ttu-id="8fa10-219">Accedere a Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8fa10-219">Sign in to Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="8fa10-220">Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-220">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="8fa10-221">Nella scheda **Panoramica**, cerca le righe che hanno i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8fa10-221">On the **Overview** tab, look for the lines that have the following values:</span></span>

    - <span data-ttu-id="8fa10-222">**Tipo di ordine di lavoro:** *Conteggio ciclo*</span><span class="sxs-lookup"><span data-stu-id="8fa10-222">**Work order type:** *Cycle counting*</span></span>
    - <span data-ttu-id="8fa10-223">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="8fa10-223">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="8fa10-224">**Stato del lavoro:** *Revisione in sospeso*</span><span class="sxs-lookup"><span data-stu-id="8fa10-224">**Work status:** *Pending review*</span></span>

    <span data-ttu-id="8fa10-225">Due ID lavoro dovrebbero essere stati creati per queste righe.</span><span class="sxs-lookup"><span data-stu-id="8fa10-225">Two work IDs should have been created for these lines.</span></span> <span data-ttu-id="8fa10-226">I conteggi per entrambi questi ID di lavoro devono essere accettati.</span><span class="sxs-lookup"><span data-stu-id="8fa10-226">The counts for both these work IDs must be accepted.</span></span>

1. <span data-ttu-id="8fa10-227">Nella griglia, seleziona il primo ID di lavoro per il tipo di ordine di lavoro *Conteggio ciclo*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-227">In the grid, select the first work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="8fa10-228">Nella scheda **Lavoro** del riquadro azioni, nel gruppo **Lavoro**, seleziona **Conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-228">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="8fa10-229">Vengono visualizzate due righe, una per ogni articolo e targa.</span><span class="sxs-lookup"><span data-stu-id="8fa10-229">Two lines are shown, one for each item and license plate.</span></span> <span data-ttu-id="8fa10-230">I valori nei campi **Quantità conteggiata**, **Ubicazione**, **Targa** e **Articolo** devono corrispondere alle voci di conteggio create sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="8fa10-230">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span> <span data-ttu-id="8fa10-231">Se uno di questi campi non è visibile, seleziona **Visualizza dimensioni** nel riquadro azioni per aggiungerli alla griglia.</span><span class="sxs-lookup"><span data-stu-id="8fa10-231">If any of these fields aren't visible, select **Display dimensions** on the Action Pane to add them to the grid.</span></span>

1. <span data-ttu-id="8fa10-232">Seleziona entrambe le righe.</span><span class="sxs-lookup"><span data-stu-id="8fa10-232">Select both lines.</span></span>
1. <span data-ttu-id="8fa10-233">Nel riquadro azioni, seleziona **Accetta conteggio**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-233">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="8fa10-234">Si riceve un messaggio "Registrazione - Giornale di registrazione".</span><span class="sxs-lookup"><span data-stu-id="8fa10-234">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="8fa10-235">Seleziona **Dettagli messaggio** per visualizzare il numero di giornale di registrazione pubblicato.</span><span class="sxs-lookup"><span data-stu-id="8fa10-235">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="8fa10-236">Chiudi i dettagli del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8fa10-236">Close the message details.</span></span>
1. <span data-ttu-id="8fa10-237">Aggiorna la pagina **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-237">Refresh the **Work** page.</span></span>

    <span data-ttu-id="8fa10-238">Il primo ID lavoro è stato chiuso e non viene più visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8fa10-238">The first work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="8fa10-239">Per visualizzare il lavoro chiuso, seleziona la casella di controllo **Mostra chiuso** sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="8fa10-239">To view closed work, select the **Show closed** check box above the grid.</span></span>

    <span data-ttu-id="8fa10-240">Ora accetterai il lavoro per la targa nell'ubicazione *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-240">You will now accept the work for the license plate in the *01A01R1S2B* location.</span></span>

1. <span data-ttu-id="8fa10-241">Nella scheda **Panoramica**, seleziona il secondo ID di lavoro per il tipo di ordine di lavoro *Conteggio ciclo*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-241">On the **Overview** tab, select the second work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="8fa10-242">Nella scheda **Lavoro** del riquadro azioni, nel gruppo **Lavoro**, seleziona **Conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-242">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="8fa10-243">Viene visualizzata una riga, per l'articolo e la targa.</span><span class="sxs-lookup"><span data-stu-id="8fa10-243">One line is shown, for the item and license plate.</span></span> <span data-ttu-id="8fa10-244">I valori nei campi **Quantità conteggiata**, **Ubicazione**, **Targa** e **Articolo** devono corrispondere alle voci di conteggio create sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="8fa10-244">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span>

1. <span data-ttu-id="8fa10-245">Seleziona la riga.</span><span class="sxs-lookup"><span data-stu-id="8fa10-245">Select the line.</span></span>
1. <span data-ttu-id="8fa10-246">Nel riquadro azioni, seleziona **Accetta conteggio**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-246">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="8fa10-247">Si riceve un messaggio "Registrazione - Giornale di registrazione".</span><span class="sxs-lookup"><span data-stu-id="8fa10-247">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="8fa10-248">Seleziona **Dettagli messaggio** per visualizzare il numero di giornale di registrazione pubblicato.</span><span class="sxs-lookup"><span data-stu-id="8fa10-248">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="8fa10-249">Chiudi i dettagli del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8fa10-249">Close the message details.</span></span>
1. <span data-ttu-id="8fa10-250">Aggiorna la pagina **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-250">Refresh the **Work** page.</span></span>

    <span data-ttu-id="8fa10-251">Il secondo ID lavoro è stato chiuso e non viene più visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8fa10-251">The second work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="8fa10-252">Per visualizzare il lavoro chiuso, seleziona la casella di controllo **Mostra chiuso** sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="8fa10-252">To view closed work, select the **Show closed** check box above the grid.</span></span>

#### <a name="on-hand-by-location"></a><span data-ttu-id="8fa10-253">Disponibili per ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fa10-253">On-hand by location</span></span>

1. <span data-ttu-id="8fa10-254">Vai a **Gestione magazzino \> Richieste di informazioni e report \> Disponibili per ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-254">Go to **Warehouse management \> Inquiries and reports \> On-hand by location**.</span></span>
1. <span data-ttu-id="8fa10-255">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fa10-255">Set the following values:</span></span>

    - <span data-ttu-id="8fa10-256">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="8fa10-256">**Site:** *6*</span></span>
    - <span data-ttu-id="8fa10-257">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="8fa10-257">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="8fa10-258">**Aggiorna informazioni in ubicazioni:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="8fa10-258">**Refresh across locations:** *Yes*</span></span>

1. <span data-ttu-id="8fa10-259">Notare che l'ubicazione *01A01R1S1B* ha due targhe:</span><span class="sxs-lookup"><span data-stu-id="8fa10-259">Notice that location *01A01R1S1B* has two license plates:</span></span>

    - <span data-ttu-id="8fa10-260">**A0001**, dove il campo **Posizione targa** è impostato su *1*</span><span class="sxs-lookup"><span data-stu-id="8fa10-260">**A0001**, where the **LP Position** field is set to *1*</span></span>
    - <span data-ttu-id="8fa10-261">**A0002**, dove il campo **Posizione targa** è impostato su *2*</span><span class="sxs-lookup"><span data-stu-id="8fa10-261">**A0002**, where the **LP Position** field is set to *2*</span></span>

1. <span data-ttu-id="8fa10-262">Notare che l'ubicazione *01A01R1S2B* ha una targa:</span><span class="sxs-lookup"><span data-stu-id="8fa10-262">Notice that location *01A01R1S2B* has one license plate:</span></span>

    - <span data-ttu-id="8fa10-263">**A0002**, dove il campo **Posizione targa** è impostato su *1*</span><span class="sxs-lookup"><span data-stu-id="8fa10-263">**A0002**, where the **LP Position** field is set to *1*</span></span>

### <a name="sales-order-scenario"></a><span data-ttu-id="8fa10-264">Scenario dell'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="8fa10-264">Sales order scenario</span></span>

<span data-ttu-id="8fa10-265">Ora che la funzionalità *Posizionamento targa di ubicazione* è stata impostata e le scorte sono in transito, è necessario creare un ordine cliente per generare il lavoro di prelievo che indirizzerà l'operatore di magazzino a prelevare l'articolo *A0002* dall'ubicazione di inventario in cui si trova l'ID pallet *1*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-265">Now that the *Location license plate positioning* feature has been set up, and the inventory has been staged, you must create a sales order to generate picking work that will direct the warehouse worker to pick item *A0002* from the inventory location where the pallet ID is in position *1*.</span></span>

1. <span data-ttu-id="8fa10-266">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-266">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="8fa10-267">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-267">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8fa10-268">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8fa10-268">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="8fa10-269">**Conto cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="8fa10-269">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="8fa10-270">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="8fa10-270">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="8fa10-271">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-271">Select **OK**.</span></span>
1. <span data-ttu-id="8fa10-272">Una nuova riga viene aggiunta alla griglia nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-272">A new line is added to the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="8fa10-273">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8fa10-273">On this new line, set the following values:</span></span>

    - <span data-ttu-id="8fa10-274">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="8fa10-274">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="8fa10-275">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="8fa10-275">**Quantity:** *1*</span></span>

1. <span data-ttu-id="8fa10-276">Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-276">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="8fa10-277">Nella pagina **Prenotazione**, quindi nel riquadro azioni, seleziona **Prenota lotto** per prenotare le scorte per la riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8fa10-277">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve inventory for the order line.</span></span>
1. <span data-ttu-id="8fa10-278">Chiudi la pagina **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-278">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="8fa10-279">Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-279">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="8fa10-280">Ricevi un messaggio informativi che indica l'ID ondata e l'ID spedizione creati per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="8fa10-280">You receive an informational message that indicates the wave ID and shipment ID that were created for the order.</span></span>

1. <span data-ttu-id="8fa10-281">Nella scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino** sopra la griglia, seleziona **Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-281">On the **Sales order lines** FastTab, on the **Warehouse** menu above the grid, select **Work details**.</span></span>
1. <span data-ttu-id="8fa10-282">La pagina **Lavoro** viene visualizzata e mostra il lavoro creato per la riga delle vendite.</span><span class="sxs-lookup"><span data-stu-id="8fa10-282">The **Work** page appears and shows the work that was created for the sales line.</span></span> <span data-ttu-id="8fa10-283">Prendi nota dell'ID lavoro mostrato.</span><span class="sxs-lookup"><span data-stu-id="8fa10-283">Make a note of the work ID that is shown.</span></span>

### <a name="sales-picking-scenario"></a><span data-ttu-id="8fa10-284">Scenario di raccolta delle vendite</span><span class="sxs-lookup"><span data-stu-id="8fa10-284">Sales picking scenario</span></span>

1. <span data-ttu-id="8fa10-285">Apri l'app per dispositivi mobili e accedi al magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-285">Open the mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="8fa10-286">Vai a **In uscita \> Prelievo vendite**.</span><span class="sxs-lookup"><span data-stu-id="8fa10-286">Go to **Outbound \> Sales picking**.</span></span>
1. <span data-ttu-id="8fa10-287">Nella pagina **Esegui scansione ID lavoro/ID targa**, seleziona il campo **ID**, quindi immetti l'ID lavoro dalla riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="8fa10-287">On the **Scan a work ID / license plate ID** page, select the **ID** field, and then enter the work ID from the sales line.</span></span>
1. <span data-ttu-id="8fa10-288">Si noti che il lavoro di prelievo indirizza l'utente a prelevare l'articolo *A0002* dall'ubicazione *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="8fa10-288">Notice that the picking work directs you to pick item *A0002* from location *01A01R1S2B*.</span></span> <span data-ttu-id="8fa10-289">Ricevi questa istruzione perché l'articolo *A0002* è su una targa che è in posizione *1* in quella ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fa10-289">You receive this instruction because item *A0002* is on a license plate that is in position *1* in that location.</span></span>

    <span data-ttu-id="8fa10-290">![Ubicazione posizione 1](media/LocationLicensePlatePositioning.png "Ubicazione posizione 1")</span><span class="sxs-lookup"><span data-stu-id="8fa10-290">![Position 1 location](media/LocationLicensePlatePositioning.png "Position 1 location")</span></span>

1. <span data-ttu-id="8fa10-291">Immetti l'ID targa creato per l'ubicazione, quindi segui le istruzioni per selezionare l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="8fa10-291">Enter the license plate ID that you created for the location, and then follow the prompts to pick the sales order.</span></span>
