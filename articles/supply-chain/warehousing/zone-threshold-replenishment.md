---
title: Rifornimento soglia di zona
description: Il rifornimento basato su zone utilizza una strategia di rifornimento minimo/massimo (min/massimo), ma valuta intere zone di magazzino anziché solo singole ubicazioni. Pertanto, i responsabili del magazzino possono apprendere più rapidamente quando sono necessarie scorte aggiuntive in una zona di prelievo.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 2e83d6885bf7400916d633a49d3b19b8843b0269
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965504"
---
# <a name="zone-threshold-replenishment"></a><span data-ttu-id="a37d7-104">Rifornimento soglia di zona</span><span class="sxs-lookup"><span data-stu-id="a37d7-104">Zone threshold replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a37d7-105">Il rifornimento basato su zone utilizza una strategia di [rifornimento](replenishment.md) minimo/massimo (min/massimo), ma valuta intere zone di magazzino anziché solo singole ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="a37d7-105">Zone-based replenishment uses a minimum/maximum (min/max) [replenishment](replenishment.md) strategy, but it evaluates whole warehouse zones instead of just individual locations.</span></span> <span data-ttu-id="a37d7-106">Pertanto, i responsabili del magazzino possono apprendere più rapidamente quando sono necessarie scorte aggiuntive in una zona di prelievo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-106">Therefore, warehouse managers can more quickly learn when additional inventory is required in a picking zone.</span></span>

<span data-ttu-id="a37d7-107">L'impostazione per questa funzione è simile all'impostazione per il rifornimento in base all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-107">The setup for this feature resembles the setup for location-based replenishment.</span></span> <span data-ttu-id="a37d7-108">Tuttavia, quando si imposta un modello per il rifornimento minimo/massimo, è anche possibile specificare se la soglia deve essere valutata per ubicazione o per zona.</span><span class="sxs-lookup"><span data-stu-id="a37d7-108">However, when you set up a template for min/max replenishment, you can also specify whether the threshold should be evaluated per location or per zone.</span></span> <span data-ttu-id="a37d7-109">Se si imposta una valutazione basata su zone, è necessario aggiungere zone specifiche alla query di selezione delle zone.</span><span class="sxs-lookup"><span data-stu-id="a37d7-109">If you set up evaluation that is based on zones, you must add specific zones to the zone selection query.</span></span>

<span data-ttu-id="a37d7-110">Come il rifornimento min/max basato sull'ubicazione, il rifornimento min/max basato sulla zona si basa sull'impostazione di una soglia minima di scorte che attiva la creazione del lavoro di rifornimento per gli articoli selezionati.</span><span class="sxs-lookup"><span data-stu-id="a37d7-110">Like location-based min/max replenishment, zone-based min/max replenishment is based the setup of a minimum inventory threshold that triggers the creation of replenishment work for selected items.</span></span> <span data-ttu-id="a37d7-111">Questo lavoro di rifornimento aumenterà le scorte fino alla soglia massima specificata per la zona.</span><span class="sxs-lookup"><span data-stu-id="a37d7-111">This replenishment work will increase inventory up to the specified maximum threshold for the zone.</span></span>

> [!NOTE]
> <span data-ttu-id="a37d7-112">I processi di rifornimento della zona per le varianti di prodotto non sono supportati nella versione corrente.</span><span class="sxs-lookup"><span data-stu-id="a37d7-112">Zone replenishment processes for product variants aren't supported in the current release.</span></span>


<span data-ttu-id="a37d7-113">A differenza del rifornimento min/max basato sull'ubicazione, il rifornimento min/max basato sulla zona non richiede ubicazioni fisse per valutare se le ubicazioni devono contenere un articolo specifico.</span><span class="sxs-lookup"><span data-stu-id="a37d7-113">Unlike location-based min/max replenishment, zone-based min/max replenishment doesn't require fixed locations to evaluate whether locations should store a specific item.</span></span> <span data-ttu-id="a37d7-114">Pertanto, il rifornimento in base alla zona consente di utilizzare il rifornimento minimo/massimo anche se non disponi di ubicazioni fisse per ciascun articolo o variante dell'articolo nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="a37d7-114">Therefore, zone-based replenishment lets you use min/max replenishment even if you don't have fixed locations for each item or item variant in the warehouse.</span></span> <span data-ttu-id="a37d7-115">Quando una quantità nella zona scende al di sotto della soglia minima specificata, viene creato il lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-115">When a quantity in the zone falls below the specified minimum threshold, replenishment work is created.</span></span> <span data-ttu-id="a37d7-116">Le direttive sull'ubicazione determineranno in quale ubicazione specifica devono essere posizionate le scorte</span><span class="sxs-lookup"><span data-stu-id="a37d7-116">Location directives will determine which specific location the inventory should be put into.</span></span>

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a><span data-ttu-id="a37d7-117">Attiva la funzione di rifornimento della soglia di zona</span><span class="sxs-lookup"><span data-stu-id="a37d7-117">Turn on the Zone threshold replenishment feature</span></span>

<span data-ttu-id="a37d7-118">Prima di poter utilizzare la funzionalità *Rifornimento soglia di zona*, deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="a37d7-118">Before you can use the *Zone threshold replenishment* feature, it must be turned on in your system.</span></span> <span data-ttu-id="a37d7-119">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="a37d7-119">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a37d7-120">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a37d7-120">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a37d7-121">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="a37d7-121">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a37d7-122">**Nome funzionalità:** *Rifornimento soglia di zona*</span><span class="sxs-lookup"><span data-stu-id="a37d7-122">**Feature name:** *Zone threshold replenishment*</span></span>

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a><span data-ttu-id="a37d7-123">Impostare il rifornimento basato su zone</span><span class="sxs-lookup"><span data-stu-id="a37d7-123">Set up zone-based replenishment</span></span>

<span data-ttu-id="a37d7-124">Per impostare un rifornimento basato sulla zona, è necessario configurare diverse parti del sistema.</span><span class="sxs-lookup"><span data-stu-id="a37d7-124">To set up zone-based replenishment, you must configure several parts of the system.</span></span> <span data-ttu-id="a37d7-125">Questa sezione introduce le varie impostazioni e fornisce valori di dati dimostrativi che puoi immettere se desideri analizzare lo scenario alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-125">This section introduces the various settings and provides demo data values that you can enter if you want to work through the scenario at the end of this topic.</span></span>

### <a name="set-up-directive-codes"></a><span data-ttu-id="a37d7-126">Impostare i codici direttiva</span><span class="sxs-lookup"><span data-stu-id="a37d7-126">Set up directive codes</span></span>

<span data-ttu-id="a37d7-127">I [codici direttiva](control-warehouse-location-directives.md) ti consentono di essere più specifico quando definisci il modello di ubicazione utilizzato in un modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a37d7-127">[Directive codes](control-warehouse-location-directives.md) let you be more specific when you define the location template that is used in a work template.</span></span> <span data-ttu-id="a37d7-128">Ogni codice stabilisce un valore comune a cui è possibile fare riferimento quando si configura ciascun tipo di modello.</span><span class="sxs-lookup"><span data-stu-id="a37d7-128">Each code establishes a common value that you can refer to when you configure each type of template.</span></span>

#### <a name="view-and-edit-directive-codes"></a><span data-ttu-id="a37d7-129">Visualizzare e modificare i codici direttiva</span><span class="sxs-lookup"><span data-stu-id="a37d7-129">View and edit directive codes</span></span>

<span data-ttu-id="a37d7-130">Per visualizzare o modificare i codici direttiva, vai a **Gestione magazzino \> Impostazione \> Codici direttiva**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-130">To view or edit your directive codes, go to **Warehouse management \> Setup \> Directive codes**.</span></span>

#### <a name="prepare-demo-data-directive-codes"></a><span data-ttu-id="a37d7-131">Preparare i codici direttiva per i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="a37d7-131">Prepare demo data directive codes</span></span>

<span data-ttu-id="a37d7-132">Questo esempio mostra come preparare un codice direttiva.</span><span class="sxs-lookup"><span data-stu-id="a37d7-132">This example shows how to prepare a directive code.</span></span> <span data-ttu-id="a37d7-133">Se prevedi di analizzare lo scenario alla fine di questo argomento, utilizza i valori dei dati dimostrativi forniti qui.</span><span class="sxs-lookup"><span data-stu-id="a37d7-133">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="a37d7-134">Altrimenti, usa i tuoi valori.</span><span class="sxs-lookup"><span data-stu-id="a37d7-134">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="a37d7-135">Seleziona la persona giuridica **USMF** che deve utilizzare i dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="a37d7-135">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="a37d7-136">Vai a **Gestione magazzino \> Impostazioni \> Codici di direttiva**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-136">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="a37d7-137">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="a37d7-138">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-138">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-139">**Codice direttiva:** _Rifornimento zona_</span><span class="sxs-lookup"><span data-stu-id="a37d7-139">**Directive code:** _Zone replen_</span></span>
    - <span data-ttu-id="a37d7-140">**Descrizione della direttiva:** _Rifornimento zona_</span><span class="sxs-lookup"><span data-stu-id="a37d7-140">**Directive description:** _Zone replenishment_</span></span>

1. <span data-ttu-id="a37d7-141">Seleziona **Salva** per salvare il nuovo codice.</span><span class="sxs-lookup"><span data-stu-id="a37d7-141">Select **Save** to save the new code.</span></span>

### <a name="set-up-replenishment-templates"></a><span data-ttu-id="a37d7-142">Imposta modelli rifornimento</span><span class="sxs-lookup"><span data-stu-id="a37d7-142">Set up replenishment templates</span></span>

<span data-ttu-id="a37d7-143">I [modelli di rifornimento basato su quantità minima e massima](tasks/set-up-min-max-replenishment-process.md) sono il meccanismo principale per il mantenimento di livelli ottimali di ubicazioni di prelievo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-143">[Min/max replenishment templates](tasks/set-up-min-max-replenishment-process.md) are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="a37d7-144">In questi modelli, devi impostare le regole che verranno utilizzate per rifornire le scorte nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="a37d7-144">In these templates, you must set up the rules that will be used to replenish inventory in the warehouse.</span></span> <span data-ttu-id="a37d7-145">Il rifornimento per il quale è possibile utilizzare i modelli include il rifornimento basato sulla zona.</span><span class="sxs-lookup"><span data-stu-id="a37d7-145">The replenishment that the templates can be used for includes zone-based replenishment.</span></span>

#### <a name="view-and-edit-replenishment-templates"></a><span data-ttu-id="a37d7-146">Visualizzare e modificare i modelli di rifornimento</span><span class="sxs-lookup"><span data-stu-id="a37d7-146">View and edit replenishment templates</span></span>

<span data-ttu-id="a37d7-147">Un modello di rifornimento è un set di regole che controlla quando e come effettuare il rifornimento dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-147">A replenishment template is a set of rules that control when and how a location is replenished.</span></span> <span data-ttu-id="a37d7-148">Selezioni un modello per controllare quando e come viene effettuato il rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-148">You select a template to control when and how replenishment is done.</span></span> <span data-ttu-id="a37d7-149">Per visualizzare o modificare i modelli di rifornimento, vai a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-149">To view or edit your replenishment templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>

#### <a name="prepare-a-demo-data-replenishment-template"></a><span data-ttu-id="a37d7-150">Preparare un modello di rifornimento dei dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="a37d7-150">Prepare a demo data replenishment template</span></span>

<span data-ttu-id="a37d7-151">Questo esempio mostra come preparare un modello di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-151">This example shows how to prepare a replenishment template.</span></span> <span data-ttu-id="a37d7-152">Se prevedi di analizzare lo scenario alla fine di questo argomento, utilizza i valori dei dati dimostrativi forniti qui.</span><span class="sxs-lookup"><span data-stu-id="a37d7-152">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="a37d7-153">Altrimenti, usa i tuoi valori.</span><span class="sxs-lookup"><span data-stu-id="a37d7-153">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="a37d7-154">Seleziona la persona giuridica **USMF** che deve utilizzare i dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="a37d7-154">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="a37d7-155">Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-155">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="a37d7-156">Seleziona **Modifica** per mettere la pagina in modalità modifica.</span><span class="sxs-lookup"><span data-stu-id="a37d7-156">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="a37d7-157">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-157">On the Action Pane, select **New** to add a row to the **Overview** grid.</span></span>
1. <span data-ttu-id="a37d7-158">Nella nuova riga, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="a37d7-158">In the new row, set the following values.</span></span> <span data-ttu-id="a37d7-159">Accetta i valori predefiniti per tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="a37d7-159">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="a37d7-160">**Modello rifornimento:** _Rifornimento min/max zona_</span><span class="sxs-lookup"><span data-stu-id="a37d7-160">**Replenish template:** _Zone min/max replen_</span></span>
    - <span data-ttu-id="a37d7-161">**Descrizione:** _Rifornimento min/max zona_</span><span class="sxs-lookup"><span data-stu-id="a37d7-161">**Description:** _Zone min/max replenishment_</span></span>
    - <span data-ttu-id="a37d7-162">**Tipo di rifornimento:** _Minimo o massimo_</span><span class="sxs-lookup"><span data-stu-id="a37d7-162">**Replenishment type:** _Minimum or maximum_</span></span>

1. <span data-ttu-id="a37d7-163">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-163">Select **Save**.</span></span>
1. <span data-ttu-id="a37d7-164">Mentre la nuova riga è ancora selezionata nella griglia **Panoramica**, seleziona **Nuovo** sopra la griglia **Dettagli del modello rifornimento** per aggiungere una riga associata al modello di rifornimento *Rifornimento min/max zona* che hai appena creato.</span><span class="sxs-lookup"><span data-stu-id="a37d7-164">While the new row is still selected in the **Overview** grid, select **New** above the **Replenishment Template Details** grid to add a row that is associated with the *Zone Min/Max replen* replenishment template that you just created.</span></span>
1. <span data-ttu-id="a37d7-165">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-165">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-166">**Numero sequenza:** Immetti _1_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-166">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="a37d7-167">**Descrizione:** Immetti _Rifornimento zona prelievo_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-167">**Description:** Enter _Pick zone replenishment_.</span></span>
    - <span data-ttu-id="a37d7-168">**Unità di rifornimento:** Seleziona _EA_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-168">**Replenishment unit:** Select _ea_.</span></span>
    - <span data-ttu-id="a37d7-169">**Tipo di richiesta:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-169">**Request type:** Leave this field blank.</span></span>
    - <span data-ttu-id="a37d7-170">**Codice direttiva:** questo campo collega il modello di rifornimento a una direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-170">**Directive code:** This field links the replenishment template with a location directive.</span></span> <span data-ttu-id="a37d7-171">Seleziona il codice direttiva per i dati dimostrativi che hai creato in precedenza (_Rifornimento zona_).</span><span class="sxs-lookup"><span data-stu-id="a37d7-171">Select the demo data directive code that you created earlier (_Zone replen_).</span></span>
    - <span data-ttu-id="a37d7-172">**Modello di lavoro**: lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-172">**Work template:** Leave this field blank.</span></span>
    - <span data-ttu-id="a37d7-173">**Quantità minima:** questo campo imposta la quantità a cui verrà attivato il rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-173">**Minimum quantity:** This field sets the quantity that replenishment will be triggered at.</span></span> <span data-ttu-id="a37d7-174">Immetti _50_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-174">Enter _50_.</span></span>
    - <span data-ttu-id="a37d7-175">**Quantità massima:** questo campo imposta la quantità massima di un articolo che può essere presente in una zona.</span><span class="sxs-lookup"><span data-stu-id="a37d7-175">**Maximum quantity:** This field sets the maximum quantity of an item that can be present in a zone.</span></span> <span data-ttu-id="a37d7-176">Il lavoro di rifornimento generato aumenterà le scorte fino a questa quantità.</span><span class="sxs-lookup"><span data-stu-id="a37d7-176">Generated replenishment work will increase inventory to this quantity.</span></span> <span data-ttu-id="a37d7-177">Immetti _150_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-177">Enter _150_.</span></span>
    - <span data-ttu-id="a37d7-178">**Unità:** questo campo imposta l'unità per i valori minimo e massimo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-178">**Unit:** This field sets the unit for the minimum and maximum values.</span></span> <span data-ttu-id="a37d7-179">Seleziona _ea_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-179">Select _ea_.</span></span>
    - <span data-ttu-id="a37d7-180">**Incremento della domanda:** seleziona _Arrotonda_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-180">**Demand increment:** Select _Round up_.</span></span>
    - <span data-ttu-id="a37d7-181">**Rifornisci ubicazioni fisse vuote:** seleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-181">**Replenish empty fixed locations:** Select this check box.</span></span>
    - <span data-ttu-id="a37d7-182">**Rifornisci solo ubicazioni fisse:** seleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-182">**Replenish only fixed locations:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-183">**Modalità query prodotto:** seleziona _Query prodotto_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-183">**Product query mode:** Select _Product query_.</span></span>
    - <span data-ttu-id="a37d7-184">**Ambito soglia di rifornimento:** questo campo definisce se il modello deve valutare per zona o per ubicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="a37d7-184">**Replenishment threshold scope:** This field defines whether the template should evaluate by zone or by specific location.</span></span> <span data-ttu-id="a37d7-185">Seleziona _Zona_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-185">Select _Zone_.</span></span>
    - <span data-ttu-id="a37d7-186">**Magazzino:** seleziona _61_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-186">**Warehouse:** Select _61_.</span></span>

1. <span data-ttu-id="a37d7-187">Seleziona **Seleziona prodotti** sopra la griglia **Dettagli modello di rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-187">Select **Select products** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="a37d7-188">Nella finestra di dialogo **Query prodotto**, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-188">In the **Product query** dialog box, on the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="a37d7-189">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-189">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-190">**Tabella:** _Articoli_</span><span class="sxs-lookup"><span data-stu-id="a37d7-190">**Table:** _Items_</span></span>
    - <span data-ttu-id="a37d7-191">**Tabella derivata:** _Articoli_</span><span class="sxs-lookup"><span data-stu-id="a37d7-191">**Derived table:** _Items_</span></span>
    - <span data-ttu-id="a37d7-192">**Campo:** _Numero articolo_</span><span class="sxs-lookup"><span data-stu-id="a37d7-192">**Field:** _Item number_</span></span>
    - <span data-ttu-id="a37d7-193">**Criteri:** _A0001_</span><span class="sxs-lookup"><span data-stu-id="a37d7-193">**Criteria:** _A0001_</span></span>

1. <span data-ttu-id="a37d7-194">Seleziona **OK** per salvare la query e chiudere la finestra dialogo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-194">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="a37d7-195">Seleziona **Seleziona zone da rifornire** sopra la griglia **Dettagli modello di rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-195">Select **Select zones to replenish** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="a37d7-196">Nella finestra di dialogo **Query zona**, nella scheda **Intervallo**, aggiungi una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-196">In the **Zone query** dialog box, on the **Range** tab, add a row to the grid.</span></span>
1. <span data-ttu-id="a37d7-197">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-197">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-198">**Tabella:** _Zona magazzino_</span><span class="sxs-lookup"><span data-stu-id="a37d7-198">**Table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="a37d7-199">**Tabella derivata:** _Zona magazzino_</span><span class="sxs-lookup"><span data-stu-id="a37d7-199">**Derived table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="a37d7-200">**Campo:** _ID zona_</span><span class="sxs-lookup"><span data-stu-id="a37d7-200">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="a37d7-201">**Criteri:** _PIANO_</span><span class="sxs-lookup"><span data-stu-id="a37d7-201">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="a37d7-202">Seleziona **OK** per salvare la query e chiudere la finestra dialogo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-202">Select **OK** to save your query and close the dialog box.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="a37d7-203">Imposta direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="a37d7-203">Set up location directives</span></span>

<span data-ttu-id="a37d7-204">A differenza del rifornimento min/max basato sull'ubicazione, il rifornimento min/max basato sulla zona richiede l'impostazione di entrambe le direttive sull'ubicazione di prelievo e sull'ubicazione di stoccaggio, poiché il sistema valuta l'intera zona anziché solo l'ubicazione di prelievo per il lavoro in uscita.</span><span class="sxs-lookup"><span data-stu-id="a37d7-204">Unlike location-based min/max replenishment, zone-based min/max replenishment requires that you set up both pick location directives and put location directives, because the system evaluates the whole zone instead of just the pick location for outbound work.</span></span>

#### <a name="view-and-edit-location-directives"></a><span data-ttu-id="a37d7-205">Visualizzare e modificare le direttive sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="a37d7-205">View and edit location directives</span></span>

<span data-ttu-id="a37d7-206">Per visualizzare o modificare le direttive sull'ubicazione, vai a **Gestione magazzino \> Impostazione \> Direttive ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-206">To view or edit your location directives, go to **Warehouse management \> Setup \> Location directives**.</span></span>

<span data-ttu-id="a37d7-207">Per esempi che mostrano come utilizzare le impostazioni per creare le direttive sull'ubicazione di prelievo richieste e le direttive sull'ubicazione di stoccaggio, vedi la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="a37d7-207">For examples that show how to use the settings to create the required pick location directives and put location directives, see the next section.</span></span>

#### <a name="prepare-demo-data-location-directives"></a><span data-ttu-id="a37d7-208">Preparare le direttive sull'ubicazione per i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="a37d7-208">Prepare demo data location directives</span></span>

<span data-ttu-id="a37d7-209">Per preparare i dati dimostrativi in modo che possano essere utilizzati nello scenario alla fine di questo argomento, è necessario creare due direttive di ubicazione: una per il prelievo e una per lo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="a37d7-209">To prepare demo data so that it can be used in the scenario at the end of this topic, you must create two location directives: one for pick and one for put.</span></span>

##### <a name="create-a-replenishment-pick-directive"></a><span data-ttu-id="a37d7-210">Creare una direttiva di prelievo di rifornimento</span><span class="sxs-lookup"><span data-stu-id="a37d7-210">Create a replenishment pick directive</span></span>

1. <span data-ttu-id="a37d7-211">Seleziona la persona giuridica **USMF** che deve utilizzare i dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="a37d7-211">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="a37d7-212">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-212">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a37d7-213">Nel riquadro sinistro, imposta il campo **Tipo di ordine di lavoro** su _Rifornimento_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-213">In the left pane, set the **Work order type** field to _Replenishment_.</span></span>
1. <span data-ttu-id="a37d7-214">Nel riquadro azioni seleziona **Nuova** per creare una nuova direttiva.</span><span class="sxs-lookup"><span data-stu-id="a37d7-214">On the Action Pane, select **New** to create a new directive.</span></span>
1. <span data-ttu-id="a37d7-215">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a37d7-215">Set the following values:</span></span>

    - <span data-ttu-id="a37d7-216">**Numero sequenza:** accetta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a37d7-216">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="a37d7-217">**Nome:** immetti _Prelievo zona_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-217">**Name:** Enter _Zone pick_.</span></span>
    - <span data-ttu-id="a37d7-218">**Tipo di lavoro:** seleziona _Prelievo_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-218">**Work type:** Select _Pick_.</span></span>
    - <span data-ttu-id="a37d7-219">**Sito:** Seleziona _6_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-219">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="a37d7-220">**Magazzino:** seleziona _61_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-220">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="a37d7-221">**Codice direttiva:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-221">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="a37d7-222">**Più SKU:** imposta questa opzione su _No_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-222">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="a37d7-223">Seleziona **Salva** per creare una direttiva con le impostazioni che hai configurato finora.</span><span class="sxs-lookup"><span data-stu-id="a37d7-223">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="a37d7-224">Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-224">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="a37d7-225">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-225">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a37d7-226">**Numero sequenza:** Immetti _1_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-226">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="a37d7-227">**Da quantità:** immetti _0_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-227">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="a37d7-228">**A quantità:** immetti _10000000_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-228">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="a37d7-229">**Unità:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-229">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="a37d7-230">**Trova quantità:** seleziona _Nessuna_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-230">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="a37d7-231">**Limita per unità:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-231">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-232">**Arrotonda a unità:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-232">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-233">**Individua quantità di imballaggio:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-233">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-234">**Consenti divisione:** seleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-234">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="a37d7-235">Seleziona **Salva** per salvare la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="a37d7-235">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="a37d7-236">Mentre la tua nuova riga è ancora selezionata nella griglia **Righe**, seleziona **Nuova** nella Scheda dettaglio **Azioni direttiva ubicazione** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-236">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="a37d7-237">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-237">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-238">**Numero sequenza:** Immetti _1_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-238">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="a37d7-239">**Nome:** immetti _Preleva da blocco_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-239">**Name:** Enter _Pick from bulk_.</span></span>
    - <span data-ttu-id="a37d7-240">**Utilizzo ubicazioni fisse:** seleziona _Ubicazioni fisse e non fisse_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-240">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="a37d7-241">**Consenti inventario negativo:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-241">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-242">**Lotto abilitato:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-242">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-243">**Strategia:** seleziona _Nessuna_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-243">**Strategy:** Select _None_.</span></span>

1. <span data-ttu-id="a37d7-244">Seleziona **Salva** per salvare la nuova azione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-244">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="a37d7-245">Con la nuova azione ancora selezionata, seleziona **Modifica query** sopra la griglia **Azioni direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-245">While your new action still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="a37d7-246">Viene visualizzata una finestra di dialogo della query, in cui è possibile selezionare le ubicazioni da rifornire.</span><span class="sxs-lookup"><span data-stu-id="a37d7-246">A query dialog box appears, where you can select the locations to replenish from.</span></span> <span data-ttu-id="a37d7-247">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-247">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="a37d7-248">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-248">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-249">**Tabella:** _Ubicazioni_</span><span class="sxs-lookup"><span data-stu-id="a37d7-249">**Table:** _Locations_</span></span>
    - <span data-ttu-id="a37d7-250">**Tabella derivata:** _Ubicazioni_</span><span class="sxs-lookup"><span data-stu-id="a37d7-250">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="a37d7-251">**Campo:** _ID zona_</span><span class="sxs-lookup"><span data-stu-id="a37d7-251">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="a37d7-252">**Criteri:** _BULK_</span><span class="sxs-lookup"><span data-stu-id="a37d7-252">**Criteria:** _BULK_</span></span>

1. <span data-ttu-id="a37d7-253">Seleziona **OK** per salvare la query e chiudere la finestra dialogo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-253">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="a37d7-254">Seleziona **Salva** per salvare la direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-254">Select **Save** to save your location directive.</span></span>

##### <a name="create-a-replenishment-put-directive"></a><span data-ttu-id="a37d7-255">Creare una direttiva di stoccaggio di rifornimento</span><span class="sxs-lookup"><span data-stu-id="a37d7-255">Create a replenishment put directive</span></span>

1. <span data-ttu-id="a37d7-256">Nella pagina **Direttive di ubicazione**, nel riquadro sinistro, verifica che il campo **Tipo di ordine di lavoro** sia è ancora impostato su _Rifornimento_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-256">On the **Location directives** page, in the left pane, make sure that the **Work order type** field is still set to _Replenishment_.</span></span>
1. <span data-ttu-id="a37d7-257">Nel riquadro azioni seleziona **Nuova** per creare un'altra nuova direttiva.</span><span class="sxs-lookup"><span data-stu-id="a37d7-257">On the Action Pane, select **New** to create another new directive.</span></span>
1. <span data-ttu-id="a37d7-258">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a37d7-258">Set the following values:</span></span>

    - <span data-ttu-id="a37d7-259">**Numero sequenza:** accetta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a37d7-259">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="a37d7-260">**Nome:** immetti _Stoccaggio zona_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-260">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="a37d7-261">**Tipo di ordine di lavoro:** seleziona _Stoccaggio_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-261">**Work order type:** Select _Put_.</span></span>
    - <span data-ttu-id="a37d7-262">**Sito:** Seleziona _6_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-262">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="a37d7-263">**Magazzino:** seleziona _61_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-263">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="a37d7-264">**Codice direttiva:** seleziona _Rifornimento zona_ per collegare questa direttiva di ubicazione con il modello di rifornimento creato in precedenza utilizzando il codice creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a37d7-264">**Directive code:** Select _Zone replen_ to link this location directive with the replenishment template that you created earlier by using the code that you created earlier.</span></span>
    - <span data-ttu-id="a37d7-265">**Più SKU:** imposta questa opzione su _No_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-265">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="a37d7-266">Seleziona **Salva** per creare una direttiva con le impostazioni che hai configurato finora.</span><span class="sxs-lookup"><span data-stu-id="a37d7-266">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="a37d7-267">Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-267">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="a37d7-268">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-268">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a37d7-269">**Numero sequenza:** Immetti _1_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-269">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="a37d7-270">**Da quantità:** immetti _0_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-270">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="a37d7-271">**A quantità:** immetti _10000000_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-271">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="a37d7-272">**Unità:** lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-272">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="a37d7-273">**Trova quantità:** seleziona _Nessuna_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-273">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="a37d7-274">**Limita per unità:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-274">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-275">**Arrotonda a unità:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-275">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-276">**Individua quantità di imballaggio:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-276">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-277">**Consenti divisione:** seleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-277">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="a37d7-278">Seleziona **Salva** per salvare la nuova riga.</span><span class="sxs-lookup"><span data-stu-id="a37d7-278">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="a37d7-279">Mentre la tua nuova riga è ancora selezionata nella griglia **Righe**, seleziona **Nuova** nella Scheda dettaglio **Azioni direttiva ubicazione** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-279">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="a37d7-280">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-280">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-281">**Numero sequenza:** Immetti _1_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-281">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="a37d7-282">**Nome:** immetti _Stoccaggio zona_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-282">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="a37d7-283">**Utilizzo ubicazioni fisse:** seleziona _Ubicazioni fisse e non fisse_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-283">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="a37d7-284">**Consenti inventario negativo:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-284">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-285">**Lotto abilitato:** deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-285">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="a37d7-286">**Strategia:** seleziona _Consolida_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-286">**Strategy:** Select _Consolidate_.</span></span>

1. <span data-ttu-id="a37d7-287">Seleziona **Salva** per salvare la nuova azione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-287">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="a37d7-288">Con la nuova azione ancora selezionata, seleziona **Modifica query** sopra la griglia **Azioni direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-288">While your new action is still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="a37d7-289">Viene visualizzata una finestra di dialogo della query, in cui è possibile selezionare la zona da rifornire.</span><span class="sxs-lookup"><span data-stu-id="a37d7-289">A query dialog box appears, where you can select the zone to replenish to.</span></span> <span data-ttu-id="a37d7-290">Questa zona deve essere la stessa zona specificata nel modello di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-290">This zone should be the same zone that is specified in the replenishment template.</span></span> <span data-ttu-id="a37d7-291">Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a37d7-291">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="a37d7-292">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a37d7-292">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a37d7-293">**Tabella:** _Ubicazioni_</span><span class="sxs-lookup"><span data-stu-id="a37d7-293">**Table:** _Locations_</span></span>
    - <span data-ttu-id="a37d7-294">**Tabella derivata:** _Ubicazioni_</span><span class="sxs-lookup"><span data-stu-id="a37d7-294">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="a37d7-295">**Campo:** _ID zona_</span><span class="sxs-lookup"><span data-stu-id="a37d7-295">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="a37d7-296">**Criteri:** _PIANO_</span><span class="sxs-lookup"><span data-stu-id="a37d7-296">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="a37d7-297">Seleziona **OK** per salvare la query e chiudere la finestra dialogo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-297">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="a37d7-298">Seleziona **Salva** per salvare la direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-298">Select **Save** to save your location directive.</span></span>

## <a name="scenario"></a><span data-ttu-id="a37d7-299">Scenario</span><span class="sxs-lookup"><span data-stu-id="a37d7-299">Scenario</span></span>

<span data-ttu-id="a37d7-300">Questa sezione fornisce uno scenario di esempio che mostra come utilizzare la funzione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-300">This section provides a sample scenario that shows how to work with the feature.</span></span>

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a><span data-ttu-id="a37d7-301">Preparare i dati di esempio richiesti per lo scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="a37d7-301">Prepare the sample data that is required for the sample scenario</span></span>

<span data-ttu-id="a37d7-302">Prima di iniziare ad analizzare lo scenario, devi attivare i dati di esempio e impostare la funzionalità come descritto in questa sezione e nelle sezioni precedenti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-302">Before you start to work through the scenario, you must activate sample data and set up the feature as described in this section and in the previous sections of this topic.</span></span>

#### <a name="use-the-usmf-legal-entity"></a><span data-ttu-id="a37d7-303">Utilizzare la persona giuridica USMF</span><span class="sxs-lookup"><span data-stu-id="a37d7-303">Use the USMF legal entity</span></span>

<span data-ttu-id="a37d7-304">Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="a37d7-304">To work through the scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="a37d7-305">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="a37d7-305">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="prepare-additional-sample-data"></a><span data-ttu-id="a37d7-306">Preparare altri dati di esempio</span><span class="sxs-lookup"><span data-stu-id="a37d7-306">Prepare additional sample data</span></span>

<span data-ttu-id="a37d7-307">Dopo aver selezionato la persona giuridica **USMF**, aggiungi i dati di esempio aggiuntivi richiesti, come descritto nella sezione [Impostare il rifornimento basato su zone](#setup) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-307">After you've selected the **USMF** legal entity, add the additional sample data that is required, as described in the [Set up zone-based replenishment](#setup) section earlier in this topic.</span></span>

#### <a name="check-your-on-hand-inventory"></a><span data-ttu-id="a37d7-308">Controllare le scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="a37d7-308">Check your on-hand inventory</span></span>

<span data-ttu-id="a37d7-309">Segui questi passaggi per verificare che il sistema includa scorte sufficienti per supportare lo scenario di esempio.</span><span class="sxs-lookup"><span data-stu-id="a37d7-309">Follow these steps to make sure that your system includes enough inventory to support the sample scenario.</span></span>

1. <span data-ttu-id="a37d7-310">Verifica che vi siano scorte disponibili per l'articolo *A0001* in due diverse ubicazioni nella zona di prelievo (*PIANO*) specificata nel modello di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-310">Make sure that there is on-hand inventory for item *A0001* at two different locations in the pick zone (*FLOOR*) that is specified in the replenishment template.</span></span> <span data-ttu-id="a37d7-311">Tuttavia, le scorte totali dovrebbe essere inferiori alla quantità minima richiesta (*50*) specificata nel modello di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-311">However, the total inventory should be less than the required minimum quantity (*50*) that is specified on the replenishment template.</span></span> <span data-ttu-id="a37d7-312">In questo modo, puoi simulare il modo in cui si verifica il calcolo per l'intera zona anziché solo per una singola ubicazione.</span><span class="sxs-lookup"><span data-stu-id="a37d7-312">In this way, you can simulate how the calculation occurs for the whole zone instead of just for a single location.</span></span> <span data-ttu-id="a37d7-313">**Utilizza uno qualsiasi dei processi di magazzino per regolare le scorte in base alle esigenze.**</span><span class="sxs-lookup"><span data-stu-id="a37d7-313">**Use any of the warehouse processes to adjust inventory as required.**</span></span>
1. <span data-ttu-id="a37d7-314">Verifica che ci siano abbastanza scorte dell'articolo *A0001* in un'ubicazione in blocco specificata nella direttiva sull'ubicazione di prelievo zona in cui il lavoro di rifornimento dovrebbe prelevare gli articoli dall'ID zona *MASSA*.</span><span class="sxs-lookup"><span data-stu-id="a37d7-314">Make sure that there is enough inventory for item *A0001* at a bulk location that is specified in the zone pick location directive where the replenishment work should pick the items from zone ID *BULK*.</span></span> <span data-ttu-id="a37d7-315">Le scorte totali devono essere superiori alla quantità massima richiesta (*150*) specificata nel modello di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-315">The total inventory must be more than the required maximum quantity (*150*) that is specified in the replenishment template.</span></span>
1. <span data-ttu-id="a37d7-316">Facoltativo ma consigliato: attieniti alla seguente procedura per creare un giornale di registrazione delle scorte:</span><span class="sxs-lookup"><span data-stu-id="a37d7-316">Optional but recommended: Follow these steps to create an inventory adjustment journal:</span></span>

    1. <span data-ttu-id="a37d7-317">Vai a **Gestione magazzino \> Inserimenti nel giornale di registrazione \> Articoli \> Rettifica di magazzino**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-317">Go to **Inventory management \> Journal entries \> Items \> Inventory adjustment**.</span></span>
    1. <span data-ttu-id="a37d7-318">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-318">Select **New**.</span></span>
    1. <span data-ttu-id="a37d7-319">Nella finestra di dialogo **Crea giornale di registrazione magazzino**, nel campo **Magazzino**, seleziona *61*.</span><span class="sxs-lookup"><span data-stu-id="a37d7-319">In the **Create inventory journal** dialog box, in the **Warehouse** field, select *61*.</span></span>
    1. <span data-ttu-id="a37d7-320">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-320">Select **OK**.</span></span>
    1. <span data-ttu-id="a37d7-321">Nella Scheda dettaglio **Righe giornale di registrazione**, utilizza il pulsante **Nuova** per aggiungere tre righe alla griglia e impostare i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="a37d7-321">On the **Journal lines** FastTab, use the **New** button to add three lines to the grid, and set the following values.</span></span> <span data-ttu-id="a37d7-322">Dopo aver completato l'impostazione di ciascuna riga, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-322">After you've finished setting up each line, select **Save**.</span></span>

        - <span data-ttu-id="a37d7-323">**Riga 1:**</span><span class="sxs-lookup"><span data-stu-id="a37d7-323">**Line 1:**</span></span>

            - <span data-ttu-id="a37d7-324">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a37d7-324">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="a37d7-325">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="a37d7-325">**Site:** *6*</span></span>
            - <span data-ttu-id="a37d7-326">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="a37d7-326">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="a37d7-327">**Ubicazione:** *02A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="a37d7-327">**Location:** *02A01R1S1B*</span></span>
            - <span data-ttu-id="a37d7-328">**Targa:** seleziona una targa esistente nell'elenco o crea una nuova targa.</span><span class="sxs-lookup"><span data-stu-id="a37d7-328">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="a37d7-329">**Quantità:** *1000*</span><span class="sxs-lookup"><span data-stu-id="a37d7-329">**Quantity:** *1000*</span></span>

        - <span data-ttu-id="a37d7-330">**Riga 2:**</span><span class="sxs-lookup"><span data-stu-id="a37d7-330">**Line 2:**</span></span>

            - <span data-ttu-id="a37d7-331">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a37d7-331">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="a37d7-332">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="a37d7-332">**Site:** *6*</span></span>
            - <span data-ttu-id="a37d7-333">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="a37d7-333">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="a37d7-334">**Ubicazione:** *07A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="a37d7-334">**Location:** *07A01R2S1B*</span></span>
            - <span data-ttu-id="a37d7-335">**Targa:** seleziona una targa esistente nell'elenco o crea una nuova targa.</span><span class="sxs-lookup"><span data-stu-id="a37d7-335">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="a37d7-336">**Quantità:** *15*</span><span class="sxs-lookup"><span data-stu-id="a37d7-336">**Quantity:** *15*</span></span>

        - <span data-ttu-id="a37d7-337">**Riga 3:**</span><span class="sxs-lookup"><span data-stu-id="a37d7-337">**Line 3:**</span></span>

            - <span data-ttu-id="a37d7-338">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a37d7-338">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="a37d7-339">**Sito:** *6*</span><span class="sxs-lookup"><span data-stu-id="a37d7-339">**Site:** *6*</span></span>
            - <span data-ttu-id="a37d7-340">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="a37d7-340">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="a37d7-341">**Ubicazione:** *07A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="a37d7-341">**Location:** *07A01R1S1B*</span></span>
            - <span data-ttu-id="a37d7-342">**Targa:** seleziona una targa esistente nell'elenco o crea una nuova targa.</span><span class="sxs-lookup"><span data-stu-id="a37d7-342">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="a37d7-343">**Quantità:** *10*</span><span class="sxs-lookup"><span data-stu-id="a37d7-343">**Quantity:** *10*</span></span>

    1. <span data-ttu-id="a37d7-344">Nel riquadro azioni seleziona **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-344">On the Action Pane, select **Validate**.</span></span> <span data-ttu-id="a37d7-345">Risolvi eventuali errori rilevati prima di andare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a37d7-345">Address any errors that are found before you move on to the next step.</span></span>
    1. <span data-ttu-id="a37d7-346">Nel riquadro azioni seleziona **Registra** per registrare le scorte nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="a37d7-346">On the Action Pane, select **Post** to post the inventory to the warehouse.</span></span>

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a><span data-ttu-id="a37d7-347">Scenario di esempio: eseguire il rifornimento min/max basato sulla zona</span><span class="sxs-lookup"><span data-stu-id="a37d7-347">Sample scenario: Run zone-based min/max replenishment</span></span>

<span data-ttu-id="a37d7-348">Dopo che tutti i dati di esempio dei prerequisiti sono presenti, puoi attivare il rifornimento seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="a37d7-348">After all the prerequisite sample data is in place, you can trigger replenishment by following these steps.</span></span>

1. <span data-ttu-id="a37d7-349">Vai a **Gestione magazzino \> Rifornimento \> Rifornimenti**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-349">Go to **Warehouse management \> Replenishment \> Replenishments**.</span></span>
1. <span data-ttu-id="a37d7-350">Nella finestra di dialogo **Rifornimento**, nella Scheda dettaglio **Record da includere**, seleziona **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-350">In the **Replenishment** dialog box, on the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="a37d7-351">Nella finestra di dialogo **Richiesta di informazioni**, nella scheda **Intervallo**, modifica la riga della tabella predefinita nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a37d7-351">In the **Inquiry** dialog box, on the **Range** tab, edit the default table row in the following way:</span></span>

    - <span data-ttu-id="a37d7-352">**Tabella:** seleziona _Modelli di rifornimento_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-352">**Table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="a37d7-353">**Tabella derivata:** seleziona _Modelli di rifornimento_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-353">**Derived table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="a37d7-354">**Campo:** seleziona _Modello di rifornimento_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-354">**Field:** Select _Replenishment template_.</span></span>
    - <span data-ttu-id="a37d7-355">**Criteri:** seleziona _Rifornimento min/max zona_.</span><span class="sxs-lookup"><span data-stu-id="a37d7-355">**Criteria:** Select _Zone min/max replen_.</span></span> <span data-ttu-id="a37d7-356">Questo modello di rifornimento è il modello di rifornimento creato durante la preparazione dei dati dimostrativi per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="a37d7-356">This replenishment template is the replenishment template that you created while you were preparing the demo data for this scenario.</span></span>

1. <span data-ttu-id="a37d7-357">Seleziona **OK** per salvare la query e tornare alla finestra dialogo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-357">Select **OK** to save the query and go back to the **Replenishment** dialog box.</span></span>
1. <span data-ttu-id="a37d7-358">Seleziona **OK** per eseguire il modello di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="a37d7-358">Select **OK** to run the replenishment template.</span></span>

<span data-ttu-id="a37d7-359">Il lavoro di rifornimento viene ora creato per prelevare le scorte dalla zona *MASSA* e rifornirle nella zona *PIANO*.</span><span class="sxs-lookup"><span data-stu-id="a37d7-359">Replenishment work is now created to pick inventory from the *BULK* zone and replenish it to the *FLOOR* zone.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="a37d7-360">Note e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="a37d7-360">Notes and tips</span></span>

<span data-ttu-id="a37d7-361">Ecco alcune note e suggerimenti per utilizzare la funzionalità:</span><span class="sxs-lookup"><span data-stu-id="a37d7-361">Here are a few notes and tips for working with the feature:</span></span>

- <span data-ttu-id="a37d7-362">Per impostare il lavoro di rifornimento che va nella zona desiderata, puoi collegare le righe del modello di rifornimento e le direttive di ubicazione in uno dei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="a37d7-362">To set up replenishment work that goes to the desired zone, you can link the replenishment template lines and location directives in either of the following ways:</span></span>

    - <span data-ttu-id="a37d7-363">Modifica la query dell'intestazione della direttiva di ubicazione e filtra le righe del modello di rifornimento selezionato.</span><span class="sxs-lookup"><span data-stu-id="a37d7-363">Edit the location directive header query, and filter the selected replenishment template lines.</span></span>
    - <span data-ttu-id="a37d7-364">Utilizza un codice direttiva sulla riga del modello di rifornimento e associalo alla direttiva di ubicazione di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="a37d7-364">Use a directive code on the replenishment template line, and match it to the put location directive.</span></span>

- <span data-ttu-id="a37d7-365">Se stai utilizzando ubicazioni dinamiche, il lavoro di rifornimento verrà creato per la prima ubicazione disponibile o per un'ubicazione che contiene già scorte, se l'azione della direttiva ubicazione è impostata per utilizzare la strategia **Consolida**.</span><span class="sxs-lookup"><span data-stu-id="a37d7-365">If you're using dynamic locations, replenishment work will be created either for the first available location or for a location that already contains inventory, if the location directive action is set up to use the **Consolidate** strategy.</span></span>
- <span data-ttu-id="a37d7-366">Se stai utilizzando ubicazioni fisse anziché zone, è consigliabile utilizzare [rifornimento min/max standard](tasks/set-up-min-max-replenishment-process.md).</span><span class="sxs-lookup"><span data-stu-id="a37d7-366">If you're using fixed locations instead of zones, you should use [standard min/max replenishment](tasks/set-up-min-max-replenishment-process.md).</span></span>
