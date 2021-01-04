---
title: Rifornimento superiore alla capacità dell'ubicazione
description: Questo argomento fornisce informazioni sulla funzionalità di rifornimento superiore alla capacità dell'ubicazione. Questa funzionalità consente a tutto il lavoro di rifornimento da eseguire obbligatoriamente durante la giornata di essere creato e gestisce la disponibilità di tale lavoro di rifornimento per garantire che l'ubicazione di prelievo non esaurisca le scorte né superi la capacità.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 8e9ae16fea892d1d6b6a6b5d06137576623e7f5b
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431538"
---
# <a name="replenishment-over-location-capacity"></a><span data-ttu-id="3272e-104">Rifornimento superiore alla capacità dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="3272e-104">Replenishment over location capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3272e-105">Alcuni magazzini ad alto volume o con limitazioni di spazio devono spedire una quantità di un articolo in un giorno uperiore alla capacità dell'ubicazione di prelievo.</span><span class="sxs-lookup"><span data-stu-id="3272e-105">Some high-volume or space-constrained warehouses must ship more quantity of an item in a day than will fit in the picking location.</span></span> <span data-ttu-id="3272e-106">La funzionalità *Rifornimento superiore alla capacità dell'ubicazione* consente a tutto il lavoro di rifornimento da eseguire obbligatoriamente durante la giornata di essere creato e gestisce la disponibilità di tale lavoro di rifornimento per garantire che l'ubicazione di prelievo non esaurisca le scorte né superi la capacità.</span><span class="sxs-lookup"><span data-stu-id="3272e-106">The *Replenishment over location capacity* feature enables all replenishment work that will be required for the day to be created and manages availability of that replenishment work to ensure that the picking location neither runs out of inventory nor goes above capacity.</span></span>

<span data-ttu-id="3272e-107">La funzionalità consente di creare una quantità di lavoro di rifornimento superiore alla capacità di un'ubicazione e blocca il completamento del lavoro di rifornimento quando l'ubicazione è piena.</span><span class="sxs-lookup"><span data-stu-id="3272e-107">The feature enables more replenishment work to be created than will fit in a location, and it blocks replenishment work from being completed when the location is full.</span></span> <span data-ttu-id="3272e-108">Man mano che le scorte in un'ubicazione di calano al di sotto di una soglia configurabile, viene reso disponibile ulteriore lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-108">As inventory in the picking location drops below a configurable threshold, more replenishment work is made available.</span></span>

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a><span data-ttu-id="3272e-109">Attivare la funzionalità Rifornimento superiore alla capacità dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="3272e-109">Turn on the Replenishment over location capacity feature</span></span>

<span data-ttu-id="3272e-110">Per rendere disponibile questa funzionalità, abilitare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in quest'ordine):</span><span class="sxs-lookup"><span data-stu-id="3272e-110">To make this feature available, turn on the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in this order):</span></span>

1. <span data-ttu-id="3272e-111">Blocco lavoro a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="3272e-111">Organization-wide work blocking</span></span>
1. <span data-ttu-id="3272e-112">Rifornimento superiore alla capacità dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="3272e-112">Replenishment over location capacity</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="3272e-113">Configurare la funzionalità per lo scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="3272e-113">Set up the feature for the example scenario</span></span>

<span data-ttu-id="3272e-114">Questa sezione fornisce linee guida e un esempio che mostra come configurare questa funzionalità e preparare i dati di esempio per lo scenario di esempio illustrato più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3272e-114">This section provides guidelines and an example that shows how to set up this feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="enable-sample-data"></a><span data-ttu-id="3272e-115">Abilitare dati di esempio</span><span class="sxs-lookup"><span data-stu-id="3272e-115">Enable sample data</span></span>

<span data-ttu-id="3272e-116">Per elaborare lo [scenario di esempio](#example-scenario) utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="3272e-116">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="3272e-117">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="3272e-117">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="location-profile"></a><span data-ttu-id="3272e-118">Profilo ubicazione</span><span class="sxs-lookup"><span data-stu-id="3272e-118">Location profile</span></span>

<span data-ttu-id="3272e-119">Abilita la funzionalità di rifornimento superiore alla capacità nel profilo ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-119">Enable the replenish over capacity functionality on the location profile.</span></span>

1. <span data-ttu-id="3272e-120">Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="3272e-120">Go to **Warehouse management \> Setup \> Warehouse \> Locations profiles**.</span></span>
1. <span data-ttu-id="3272e-121">Nel riquadro sinistro selezionare **PICK-06**.</span><span class="sxs-lookup"><span data-stu-id="3272e-121">In the left pane, select **PICK-06**.</span></span>
1. <span data-ttu-id="3272e-122">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3272e-122">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="3272e-123">Nella Scheda dettaglio **Rifornimento**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3272e-123">On the **Replenishment** FastTab, set the following values:</span></span>

    - <span data-ttu-id="3272e-124">**Supera la capacità di ubicazione:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="3272e-124">**Exceed Location Capacity:** *Yes*</span></span>

        <span data-ttu-id="3272e-125">Se l'opzione è attivata, la capacità massima dell'ubicazione potrà superare il lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-125">When enabled, the maximum capacity of the location will be allowed to be exceeded by replenishment work.</span></span> <span data-ttu-id="3272e-126">Questo abilita anche altri campi nella Scheda dettaglio **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="3272e-126">This also enables other fields on the **Replenishment** FastTab.</span></span>

    - <span data-ttu-id="3272e-127">**Tipo di soglia disponibilità del lavoro:** *Quantità*</span><span class="sxs-lookup"><span data-stu-id="3272e-127">**Work availability threshold type:** *Quantity*</span></span>

        <span data-ttu-id="3272e-128">Questo campo definisce il metodo utilizzato per determinare quando è necessario rilasciare più lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-128">This field defines the method that is used to determine when more work should be released.</span></span> <span data-ttu-id="3272e-129">È possibile rilasciare in base alla quantità o a una percentuale.</span><span class="sxs-lookup"><span data-stu-id="3272e-129">You can release by either quantity or a percentage:</span></span>

        - <span data-ttu-id="3272e-130">*Percentuale*: seleziona questa opzione per utilizzare la capacità percentuale basata su limiti di stoccaggio o metriche di volume.</span><span class="sxs-lookup"><span data-stu-id="3272e-130">*Percent* – Select this option to use percentage capacity that is based on stocking limits or volumetrics.</span></span> <span data-ttu-id="3272e-131">Selezionando questa opzione si abilita il campo **Percentuale overflow** e si disabilitano i due campi relativi alla quantità, **Quantità di overflow** e **Unità di overflow**.</span><span class="sxs-lookup"><span data-stu-id="3272e-131">Selecting this option enables the **Overflow percentage** field, and disables the two quantity related fields,  **Overflow quantity** and **Overflow unit**.</span></span>

            <span data-ttu-id="3272e-132">È possibile utilizzare questa opzione se le ubicazioni di prelievo utilizzano metriche volume.</span><span class="sxs-lookup"><span data-stu-id="3272e-132">You can use this option if the picking locations use volumetrics.</span></span>

            <span data-ttu-id="3272e-133">Se questa opzione è selezionata, impostare il campo **Percentuale overflow** sulla percentuale in corrispondenza della quale sarà reso disponibili più lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-133">If this option is selected, set the **Overflow percentage** field to the percentage at which more replenishment work will be made available.</span></span>

        - <span data-ttu-id="3272e-134">*Quantità*: selezionare questa opzione per utilizzare un valore di quantità specifico.</span><span class="sxs-lookup"><span data-stu-id="3272e-134">*Quantity* – Select this option to use a specific quantity value.</span></span> <span data-ttu-id="3272e-135">Selezionando questa opzione si abilita il campo **Percentuale overflow** e si disabilitano i due campi relativi alla quantità, **Quantità di overflow** e **Unità di overflow**.</span><span class="sxs-lookup"><span data-stu-id="3272e-135">Selecting this option disables the **Overflow percentage** field and enables **Overflow quantity** and **Overflow unit** fields.</span></span>

            <span data-ttu-id="3272e-136">Utilizzare questa opzione quando non si utilizza metrica di volume per le ubicazioni che vengono rifornite o quando si dispone di quantità costanti per cui si desidera portare più scorte nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-136">Use this option when you aren't using volumetrics for the locations that are being replenished, or when you have consistent quantities at which you want more inventory to be brought to the location.</span></span>

           <span data-ttu-id="3272e-137">Se questa opzione è selezionata, impostare i campi **Quantità di overflow** e **Unità di overflow** per la quantità e l'unità in cui verrà reso disponibile più lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-137">If this option is selected, set the **Overflow quantity** and **Overflow unit** fields to the quantity and unit at which more replenishment work will be made available.</span></span>

    - <span data-ttu-id="3272e-138">**Quantità di overflow:** *0,65*</span><span class="sxs-lookup"><span data-stu-id="3272e-138">**Overflow quantity:** *0.65*</span></span>

        <span data-ttu-id="3272e-139">Questo campo definisce la quantità in cui si verifica l'overflo dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-139">This field defines the quantity at which the location overflows.</span></span>

        <span data-ttu-id="3272e-140">Il lavoro sarà disponibile ogni volta che la somma della quantità disponibile e della quantità di lavoro e nell'ubicazione è inferiore a questo valore.</span><span class="sxs-lookup"><span data-stu-id="3272e-140">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this value.</span></span> <span data-ttu-id="3272e-141">Qualsiasi lavoro di rifornimento superiore a questo valore verrà bloccato e deve essere sbloccato manualmente.</span><span class="sxs-lookup"><span data-stu-id="3272e-141">Any replenishment work above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="3272e-142">I limiti di stoccaggio dell'ubicazione vengono considerati quando viene calcolata la quantità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-142">Location stocking limits are considered when the work quantity is calculated.</span></span>

    - <span data-ttu-id="3272e-143">**Unità di overflow:** *PL*</span><span class="sxs-lookup"><span data-stu-id="3272e-143">**Overflow unit:** *PL*</span></span>

        <span data-ttu-id="3272e-144">Questo campo definisce l'unità associata alla quantità di overflow.</span><span class="sxs-lookup"><span data-stu-id="3272e-144">This field defines the unit that is associated with the overflow quantity.</span></span>

        <span data-ttu-id="3272e-145">In questo caso, verrà reso disponibile altro lavoro di rifornimento quando l'ubicazione scende a 0,65 pallet (PL).</span><span class="sxs-lookup"><span data-stu-id="3272e-145">In this case, more replenishment work will be made available when the location gets down to 0.65 pallet (PL).</span></span>

    - <span data-ttu-id="3272e-146">**Percentuale overflow**</span><span class="sxs-lookup"><span data-stu-id="3272e-146">**Overflow percentage**</span></span>

        <span data-ttu-id="3272e-147">Questo campo definisce la percentuale in cui si verifica l'overflow dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-147">This field defines the percentage at which the location overflows.</span></span>

        <span data-ttu-id="3272e-148">Il lavoro sarà disponibile ogni volta che la somma della quantità disponibile e della quantità di lavoro e nell'ubicazione è inferiore a questa percentuale.</span><span class="sxs-lookup"><span data-stu-id="3272e-148">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this percentage.</span></span> <span data-ttu-id="3272e-149">Qualsiasi percentuale della quantità di lavoro di rifornimento superiore a questo valore verrà bloccata e deve essere sbloccata manualmente.</span><span class="sxs-lookup"><span data-stu-id="3272e-149">Any replenishment work quantity percentage above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="3272e-150">I limiti di stoccaggio dell'ubicazione vengono considerati quando viene calcolata la percentuale di quantità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-150">Location stocking limits are considered when the work quantity percentage is calculated.</span></span> <span data-ttu-id="3272e-151">Se non vengono definiti limiti di stoccaggio per l'ubicazione, la percentuale della quantità di lavoro viene calcolata in base al volume se i limiti di volume sono definiti per il profilo dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-151">If no location stocking limits are defined, the work quantity percentage is calculated by volume if volume constraints are defined for the location profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3272e-152">Se si utilizzano i dati dimostrativi per la persona giuridica **USMF** ed è stata precedentemente attivata la funzionalità *Posizionamento targa ubicazione*, è necessario disattivare l'impostazione **Abilita posizionamento targa** per il profilo di ubicazione **BULK-06** per completare i passaggi su dispositivo mobile nello scenario di esempio.</span><span class="sxs-lookup"><span data-stu-id="3272e-152">If you're using the demo data for the **USMF** legal entity and previously turned on the *Location license plate positioning* feature, you must turn off the **Enable license plate positioning** setting for the **BULK-06** location profile to complete the mobile steps in the example scenario.</span></span>

### <a name="wave-step-code"></a><span data-ttu-id="3272e-153">Codice del passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="3272e-153">Wave step code</span></span>

> [!NOTE]
> <span data-ttu-id="3272e-154">Per configurare un codice di passaggio di ondata come descritto qui, è consigliabule prima utilizzare la [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare la funzionalità denominata *Codice passaggio ondata a livello di organizzazione*.</span><span class="sxs-lookup"><span data-stu-id="3272e-154">To set up a wave step code as described here, you might first have to use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named *Organization wide wave step code*.</span></span>

1. <span data-ttu-id="3272e-155">Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Codici passaggio ondata**.</span><span class="sxs-lookup"><span data-stu-id="3272e-155">Go to **Warehouse Management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="3272e-156">Selezionare **Nuovo** e impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3272e-156">Select **New**, and set the following values:</span></span>

    - <span data-ttu-id="3272e-157">**Codice passaggio ondata:** *Rifornimento*</span><span class="sxs-lookup"><span data-stu-id="3272e-157">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="3272e-158">**Descrizione passaggio ondata:** *Rifornimento*</span><span class="sxs-lookup"><span data-stu-id="3272e-158">**Wave step description:** *Replenishment*</span></span>
    - <span data-ttu-id="3272e-159">**Tipo di passaggio ondata:** *Rifornimento*</span><span class="sxs-lookup"><span data-stu-id="3272e-159">**Wave step type:** *Replenishment*</span></span>

1. <span data-ttu-id="3272e-160">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3272e-160">Select **Save**.</span></span>

### <a name="replenishment-template"></a><span data-ttu-id="3272e-161">Modello di rifornimento</span><span class="sxs-lookup"><span data-stu-id="3272e-161">Replenishment template</span></span>

<span data-ttu-id="3272e-162">I modelli rifornimento rappresentano un set di regole che controlla quando e come effettuare il rifornimento dell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-162">Replenishment templates are a set of rules that control when and how a location is replenished.</span></span>

1. <span data-ttu-id="3272e-163">Vai a **Gestione magazzino \> Impostazione \> Rifornimento \> Modelli di rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="3272e-163">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="3272e-164">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3272e-164">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="3272e-165">Nella sezione **Panoramica**, selezionare la riga in cui il campo **Modello di rifornimento** è impostato su *Riforniomento domanda*.</span><span class="sxs-lookup"><span data-stu-id="3272e-165">In the **Overview** section, select the line where the **Replenish template** field is set to *Demand replenish*.</span></span>
1. <span data-ttu-id="3272e-166">Imposta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3272e-166">Set the following values:</span></span>

    - <span data-ttu-id="3272e-167">**Codice passaggio ondata:** *Rifornimento*</span><span class="sxs-lookup"><span data-stu-id="3272e-167">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="3272e-168">**Consenti domanda ondata per utilizzare le quantità non prenotate:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="3272e-168">**Allow wave demand to use unreserved quantities:** *Yes*</span></span>

1. <span data-ttu-id="3272e-169">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3272e-169">Select **Save**.</span></span>

### <a name="wave-template"></a><span data-ttu-id="3272e-170">Modello ondata</span><span class="sxs-lookup"><span data-stu-id="3272e-170">Wave template</span></span>

1. <span data-ttu-id="3272e-171">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="3272e-171">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="3272e-172">Nel riquadro sinistro, impostare il campo **Tipo di modello ondata** su *Spedizione*.</span><span class="sxs-lookup"><span data-stu-id="3272e-172">In the left pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="3272e-173">Selezionare il modello **61 spedizione** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3272e-173">Select template **61 Shipping** in the list.</span></span>
1. <span data-ttu-id="3272e-174">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3272e-174">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="3272e-175">Nella scheda dettaglio **Generale**, impostare l'opzione **Automatizza rilascio lavoro di rifornimento** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="3272e-175">On the **General** FastTab, set the **Automate replenishment work release** option to *Yes*.</span></span>

    <span data-ttu-id="3272e-176">Impostare questa opzione su *Sì* per creare lavoro di rifornimento basato sulla domanda e per rilasciarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3272e-176">Set this option to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="3272e-177">È necessario aggiungere il metodo ondata di rifornimento al modello di ondata e creare un modello rifornimento di tipo **Domanda ondata**.</span><span class="sxs-lookup"><span data-stu-id="3272e-177">You must add the replenishment wave method to the wave template and create a replenishment template of the **Wave demand** type.</span></span> <span data-ttu-id="3272e-178">Impostare un modello di rifornimento nella pagina **Modelli di rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="3272e-178">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="3272e-179">Per configurare un modello di rifornimento, è necessario aggiungere il metodo di rifornimento al modello ondata.</span><span class="sxs-lookup"><span data-stu-id="3272e-179">To set up a replenishment template, you must add the replenish method to the wave template.</span></span>

1. <span data-ttu-id="3272e-180">Nella Scheda dettaglio **Metodi**, nella colonna **Metodi selezionati**, trova la seguente riga:</span><span class="sxs-lookup"><span data-stu-id="3272e-180">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="3272e-181">**Nome metodo:** *Rifornimento*</span><span class="sxs-lookup"><span data-stu-id="3272e-181">**Method name:** *replenish*</span></span>
    - <span data-ttu-id="3272e-182">**Nome:** *Rifornimento*</span><span class="sxs-lookup"><span data-stu-id="3272e-182">**Name:** *Replenishment*</span></span>

1. <span data-ttu-id="3272e-183">Impostare il campo **Codice passagio ondata** per questa riga su *Rifornimento*.</span><span class="sxs-lookup"><span data-stu-id="3272e-183">Set the **Wave step code** field for this line to *Replen*.</span></span>
1. <span data-ttu-id="3272e-184">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3272e-184">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="3272e-185">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="3272e-185">Example scenario</span></span>

<span data-ttu-id="3272e-186">Dopo aver reso disponibili tutti i dati di esempio precedentemente descritti e averli configurati, è possibile utilizzare questo scenario per provare la funzionalità *Rifornimento superiore alla capacità dell'ubicazione*.</span><span class="sxs-lookup"><span data-stu-id="3272e-186">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Replenishment over location capacity* feature.</span></span> <span data-ttu-id="3272e-187">I valori mostrati in questo scenario presuppongono che si stia lavorando con i dati dimostrativi standard, che sia stata selezionata la persona giuridica **USMF** e che sono stati preparati i record di esempio descritti in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3272e-187">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="3272e-188">Questo scenario serve anche come esempio che mostra come la funzionalità può essere utilizzata in uno scenario di produzione.</span><span class="sxs-lookup"><span data-stu-id="3272e-188">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-replenishment-work"></a><span data-ttu-id="3272e-189">Crea lavoro di rifornimento</span><span class="sxs-lookup"><span data-stu-id="3272e-189">Create replenishment work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="3272e-190">Creare l'ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="3272e-190">Create sales order 1</span></span>

1. <span data-ttu-id="3272e-191">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="3272e-191">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="3272e-192">Nel riquadro azioni, scegli **Nuovo** per aprire una finestra di dialogo per la creazione di un nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-192">On the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="3272e-193">Nella finestra di dialogo, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3272e-193">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="3272e-194">**Conto cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="3272e-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="3272e-195">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="3272e-195">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="3272e-196">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3272e-196">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="3272e-197">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-197">The new sales order is opened.</span></span> <span data-ttu-id="3272e-198">Include una nuova riga vuota nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="3272e-198">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="3272e-199">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3272e-199">On this line, set the following values:</span></span>

    - <span data-ttu-id="3272e-200">**Numero articolo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="3272e-200">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="3272e-201">**Quantità:** *40*</span><span class="sxs-lookup"><span data-stu-id="3272e-201">**Quantity:** *40*</span></span>

1. <span data-ttu-id="3272e-202">Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="3272e-202">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="3272e-203">Nella pagina **Prenotazione**, selezionare **Prenota lotto**.</span><span class="sxs-lookup"><span data-stu-id="3272e-203">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="3272e-204">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3272e-204">Close the page.</span></span>
1. <span data-ttu-id="3272e-205">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="3272e-205">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="3272e-206">Viene visualizzato un messaggio informativo che mostra l'ID ondata e spedizione creati.</span><span class="sxs-lookup"><span data-stu-id="3272e-206">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="3272e-207">Viene inoltre creata un'ondata di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-207">A replenishment wave is also created.</span></span>

    <span data-ttu-id="3272e-208">Viene inoltre visualizzato un messaggio di avviso che indica "L'ID lavoro XXXX non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".</span><span class="sxs-lookup"><span data-stu-id="3272e-208">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="3272e-209">Creare l'ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="3272e-209">Create sales order 2</span></span>

1. <span data-ttu-id="3272e-210">Nella pagina **Tutti gli ordini cliente**, nel riquadro azioni, scegliere **Nuovo** per aprire una finestra di dialogo per la creazione di un nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-210">On the **All sales orders**, page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="3272e-211">Nella finestra di dialogo, impostare il seguente valore:</span><span class="sxs-lookup"><span data-stu-id="3272e-211">In the dialog box, set the following value:</span></span>

    - <span data-ttu-id="3272e-212">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="3272e-212">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="3272e-213">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="3272e-213">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="3272e-214">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3272e-214">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="3272e-215">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-215">The new sales order is opened.</span></span> <span data-ttu-id="3272e-216">Include una nuova riga vuota nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="3272e-216">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="3272e-217">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3272e-217">On this line, set the following values:</span></span>

    - <span data-ttu-id="3272e-218">**Numero articolo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="3272e-218">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="3272e-219">**Quantità:** *60*</span><span class="sxs-lookup"><span data-stu-id="3272e-219">**Quantity:** *60*</span></span>

1. <span data-ttu-id="3272e-220">Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="3272e-220">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="3272e-221">Nella pagina **Prenotazione**, selezionare **Prenota lotto**.</span><span class="sxs-lookup"><span data-stu-id="3272e-221">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="3272e-222">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3272e-222">Close the page.</span></span>
1. <span data-ttu-id="3272e-223">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="3272e-223">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="3272e-224">Viene visualizzato un messaggio informativo che mostra l'ID ondata e spedizione creati.</span><span class="sxs-lookup"><span data-stu-id="3272e-224">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="3272e-225">Viene inoltre creata un'ondata di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-225">A replenishment wave is also created.</span></span>

    <span data-ttu-id="3272e-226">Viene inoltre visualizzato un messaggio di avviso che indica "L'ID lavoro XXXX non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".</span><span class="sxs-lookup"><span data-stu-id="3272e-226">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="3272e-227">Creare l'ordine cliente 3</span><span class="sxs-lookup"><span data-stu-id="3272e-227">Create sales order 3</span></span>

1. <span data-ttu-id="3272e-228">Nella pagina **Tutti gli ordini cliente**, nel riquadro azioni, scegliere **Nuovo** per aprire una finestra di dialogo per la creazione di un nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-228">On the **All sales orders** page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="3272e-229">Nella finestra di dialogo, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3272e-229">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="3272e-230">**Conto cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="3272e-230">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="3272e-231">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="3272e-231">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="3272e-232">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3272e-232">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="3272e-233">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-233">The new sales order is opened.</span></span> <span data-ttu-id="3272e-234">Include una nuova riga vuota nella Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="3272e-234">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="3272e-235">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3272e-235">On this line, set the following values:</span></span>

    - <span data-ttu-id="3272e-236">**Numero articolo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="3272e-236">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="3272e-237">**Quantità:** *30*</span><span class="sxs-lookup"><span data-stu-id="3272e-237">**Quantity:** *30*</span></span>

1. <span data-ttu-id="3272e-238">Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="3272e-238">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="3272e-239">Nella pagina **Prenotazione**, selezionare **Prenota lotto**.</span><span class="sxs-lookup"><span data-stu-id="3272e-239">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="3272e-240">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3272e-240">Close the page.</span></span>
1. <span data-ttu-id="3272e-241">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="3272e-241">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="3272e-242">Viene visualizzato un messaggio informativo che mostra l'ID ondata e spedizione creati.</span><span class="sxs-lookup"><span data-stu-id="3272e-242">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="3272e-243">Viene inoltre creata un'ondata di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-243">A replenishment wave is also created.</span></span>

    <span data-ttu-id="3272e-244">Viene inoltre visualizzato un messaggio di avviso che indica "L'ID lavoro XXXX non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".</span><span class="sxs-lookup"><span data-stu-id="3272e-244">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="view-work-details"></a><span data-ttu-id="3272e-245">Visualizzare i dettagli del lavoro</span><span class="sxs-lookup"><span data-stu-id="3272e-245">View work details</span></span>

1. <span data-ttu-id="3272e-246">Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3272e-246">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="3272e-247">Nella sezione **Panoramica**, filtrare la colonna **Magazzino** per il magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="3272e-247">In the **Overview** section, filter the **Warehouse** column for warehouse *61*.</span></span>
1. <span data-ttu-id="3272e-248">Dovresti vedere che sono stati creati sette ID lavoro per i tre ordini cliente della domanda.</span><span class="sxs-lookup"><span data-stu-id="3272e-248">You should see that seven work IDs were created for the three demand sales orders.</span></span>

    - <span data-ttu-id="3272e-249">Tre dei sette ID lavoro hanno un valore **Tipo di ordine di lavoro** di *Rifornimento* e quattro hanno un valore **Tipo di ordine di lavoro** di *Ordini di vendita*.</span><span class="sxs-lookup"><span data-stu-id="3272e-249">Three of the seven work IDs have a **Work order type** value of *Replenishment*, and four have a **Work order type** value of *Sales orders*.</span></span>
    - <span data-ttu-id="3272e-250">Tutti e tre gli ID lavoro che hanno un valore **Tipo di ordine di lavoro** di *Rifornimento* hanno le stesse ubicazioni *Preleva* e *Inserisci* nella sezione **Righe**:</span><span class="sxs-lookup"><span data-stu-id="3272e-250">All three work IDs that have a **Work order type** value of *Replenishment* have the same *Pick* and *Put* locations in the **Lines** section:</span></span>

        - <span data-ttu-id="3272e-251">**Preleva:** *02A01R5S1B*</span><span class="sxs-lookup"><span data-stu-id="3272e-251">**Pick:** *02A01R5S1B*</span></span>
        - <span data-ttu-id="3272e-252">**Inserisci:** *06A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="3272e-252">**Put:** *06A01R2S1B*</span></span>

    - <span data-ttu-id="3272e-253">Sono stati creati due ID lavoro per l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="3272e-253">Two work IDs were created for sales order 1.</span></span>

1. <span data-ttu-id="3272e-254">Prendi nota degli ID lavoro per gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-254">Make a note of the work IDs for the sales orders.</span></span>

<span data-ttu-id="3272e-255">A seconda delle quantità disponibili, le quantità di lavoro create potrebbero variare leggermente.</span><span class="sxs-lookup"><span data-stu-id="3272e-255">Depending on your on-hand quantities, the work quantities that are created might vary slightly.</span></span> <span data-ttu-id="3272e-256">Tuttavia, nel complesso, le intestazioni di lavoro create devono corrispondere a questo esempio di scenario.</span><span class="sxs-lookup"><span data-stu-id="3272e-256">However, overall, the work headers that are created should match this scenario example.</span></span>

#### <a name="on-hand-inventory-license-plate-id"></a><span data-ttu-id="3272e-257">ID targa delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="3272e-257">On-hand inventory license plate ID</span></span>

<span data-ttu-id="3272e-258">Più avanti in questo scenario, si utilizzerà l'app del magazzino (o un emulatore), dove sarà necessario identificare la targa per completare gli scenari di prelievo e rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-258">Later in this scenario, you will use the warehouse app (or an emulator), where you must identify the license plate to complete the picking and replenishment scenarios.</span></span>

<span data-ttu-id="3272e-259">Per trovare gli ID targa necessari in seguito, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="3272e-259">To find the license plate IDs that you will need later, follow these steps.</span></span>

1. <span data-ttu-id="3272e-260">Passare a **Gestione articoli \> Richieste di informazioni e report \> Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="3272e-260">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="3272e-261">Selezionare il pulsante **Mostra filtri** per aprire il riquadro del filtro.</span><span class="sxs-lookup"><span data-stu-id="3272e-261">Select the **Show filters** button to open the filter pane.</span></span>
1. <span data-ttu-id="3272e-262">Immettere i seguenti criteri di filtro per ottenere le targhe per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="3272e-262">Enter the following filtering criteria to get the license plates for the scenario.</span></span> <span data-ttu-id="3272e-263">Utilizzare il filtro *inizia con*.</span><span class="sxs-lookup"><span data-stu-id="3272e-263">Use the *begins with* filter.</span></span>

    - <span data-ttu-id="3272e-264">**Numero articolo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="3272e-264">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="3272e-265">**Magazzino:** *61*</span><span class="sxs-lookup"><span data-stu-id="3272e-265">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="3272e-266">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="3272e-266">Select **Apply**.</span></span>
1. <span data-ttu-id="3272e-267">Nel riquadro azioni selezionare **Dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="3272e-267">On the Action Pane, select **Dimensions**.</span></span>
1. <span data-ttu-id="3272e-268">Nella finestra di dialogo **Visualizzazione delle dimensioni**, **Dimensioni di immagazzinamento**, selezionare tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="3272e-268">In the **Dimensions display** dialog box, in the **Storage Dimensions** section, select all the values.</span></span>
1. <span data-ttu-id="3272e-269">Nella sezione **Transazioni**, selezionare **Codice articolo** e **Quantità \<\> 0**.</span><span class="sxs-lookup"><span data-stu-id="3272e-269">In the **Transactions** section, select **Item number** and **Quantity \<\> 0**.</span></span>
1. <span data-ttu-id="3272e-270">Al termine, selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3272e-270">When you've finished, select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="3272e-271">La griglia **Disponibilità** mostra i numeri di targa per l'articolo *T0100* in ogni ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-271">The **On-hand** grid shows the license plate numbers for item *T0100* in each location.</span></span> <span data-ttu-id="3272e-272">Prendere nota della targa che si trova in ogni ubicazione, perché questa informazione sdarà necessaria in seguito.</span><span class="sxs-lookup"><span data-stu-id="3272e-272">Make a note of the license plate that is in each location, because you will need this information later.</span></span>
1. <span data-ttu-id="3272e-273">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3272e-273">Close the page.</span></span>

### <a name="process-steps"></a><span data-ttu-id="3272e-274">Passaggi processo</span><span class="sxs-lookup"><span data-stu-id="3272e-274">Process steps</span></span>

<span data-ttu-id="3272e-275">Verrà eseguito il rifornimento dell'ubicazione di magazzino per i primi due ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-275">You will perform the warehouse location replenishment for the first two work IDs.</span></span> <span data-ttu-id="3272e-276">Il lavoro sul terzo lavoro di rifornimento sarà bloccato fino a quando il livello di scorte nell'ubicazione di prelievo non scenderà al di sotto della soglia.</span><span class="sxs-lookup"><span data-stu-id="3272e-276">Work on the third replenishment work will be blocked until the inventory level in the picking location falls below the threshold.</span></span>

#### <a name="replenishment"></a><span data-ttu-id="3272e-277">Rifornimento</span><span class="sxs-lookup"><span data-stu-id="3272e-277">Replenishment</span></span>

1. <span data-ttu-id="3272e-278">Accedere all'app di magazzino come utente nel magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="3272e-278">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="3272e-279">(Immettere *61* come ID utente e *1* come password).</span><span class="sxs-lookup"><span data-stu-id="3272e-279">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="3272e-280">Passare a **Inventario \> Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="3272e-280">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="3272e-281">Viene richiesto di completare il primo lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-281">You're prompted to complete the first replenishment work.</span></span> <span data-ttu-id="3272e-282">Vengono visualizzati il numero, la quantità e l'ubicazione di prelievo dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="3272e-282">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="3272e-283">Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3272e-283">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="3272e-284">Selezionare il pulsante **OK** (simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="3272e-284">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="3272e-285">Il sistema genera un numero di targa di destinazione per la nuova targa per l'articolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="3272e-285">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="3272e-286">Selezionare **OK** per confermare il valore.</span><span class="sxs-lookup"><span data-stu-id="3272e-286">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="3272e-287">Viene mostrato il lavoro di inserimento che indica all'utente di inserire la targa di destinazione nell'ubicazione di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-287">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="3272e-288">L'ubicazione *Inserisci* dovrebbe essere **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="3272e-288">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="3272e-289">Confermare i dettagli di inserimento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-289">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="3272e-290">Viene visualizzato il messaggio "Lavoro completato" e vengono visualizzati i dettagli della successiva attività di prelievo di rifornimento: il numero dell'articolo, la quantità e l'ubicazione da cui prelevare.</span><span class="sxs-lookup"><span data-stu-id="3272e-290">You receive a "Work Completed" message, and the details of the next replenishment pick task are shown: the item number, quantity, and location to pick from.</span></span> <span data-ttu-id="3272e-291">L'ubicazione di prelievo sarà la stessa della prima ubicazione di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-291">The picking location will be the same as the first replenishment location.</span></span> <span data-ttu-id="3272e-292">Pertanto, la targa avrà lo stesso ID targa utilizzato per la prima attività del lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-292">Therefore, the license plate will have the same license plate ID that was used for the first replenishment work task.</span></span>

1. <span data-ttu-id="3272e-293">Ripetere i passaggi precedenti per completare il lavoro di rifornimento per la seconda attività del lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-293">Repeat the preceding steps to complete the replenishment work for the second work task.</span></span> <span data-ttu-id="3272e-294">La quantità e la targa di destinazione differiranno dalla quantità e dalla targa di destinazione per la prima attività del lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-294">The quantity and target license plate will differ from the quantity and target license plate for the first work task.</span></span>

<span data-ttu-id="3272e-295">Al termine del secondo lavoro di rifornimento, viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="3272e-295">After the second replenishment work is completed, you receive a "Work Completed" message.</span></span> <span data-ttu-id="3272e-296">Il dispositivo mobile informa inoltre che non è disponibile alcun lavoro, anche se rimangono alcuni lavori di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-296">The mobile device also informs you that there is no work available, even though some replenishment work remains.</span></span> <span data-ttu-id="3272e-297">Questo comportamento si verifica perché il lavoro di rifornimento ha uno stato di disponibilità di *Tenuto* ed è quindi contrassegnato come **bloccato**.</span><span class="sxs-lookup"><span data-stu-id="3272e-297">This behavior occurs because the replenishment work has an availability status of *Held* and is therefore marked as **Blocked**.</span></span>

<span data-ttu-id="3272e-298">Lo stato *Tenuto* è stato attivato perché il profilo di ubicazione per l'ubicazione di prelievo a cui viene assegnato il lavoro ha un valore **Quantità di overflow** di *0,65 PL*.</span><span class="sxs-lookup"><span data-stu-id="3272e-298">The *Held* status was triggered because the location profile for the picking location that the work is being assigned to has an **Overflow quantity** value of *0.65 PL*.</span></span> <span data-ttu-id="3272e-299">Le due precedenti attività di rifornimento hanno riempito l'ubicazione quasi fino al limite di overflow per l'articolo *T0100*.</span><span class="sxs-lookup"><span data-stu-id="3272e-299">The two previous replenishment work tasks filled the location almost to its overflow limit for item *T0100*.</span></span> <span data-ttu-id="3272e-300">(La conversione di unità per l'articolo è *1 PL = 100 ea*.) Pertanto, il lavoro di rifornimento rimanente provocherebbe il superamento del limite di overflow per l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-300">(The unit conversion for the item is *1 PL = 100 ea*.) Therefore, the remaining replenishment work would cause the location to exceed its overflow limit.</span></span>

<span data-ttu-id="3272e-301">Fino a quando non viene prelevata una quantità sufficiente di scorte dall'ubicazione per portarla al di sotto della soglia di rilascio di lavoro sulla voce di menu del dispositivo mobile, questo lavoro di rifornimento rimarrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="3272e-301">Until enough inventory is picked from the location to bring it below the work release threshold on the mobile device menu item, this replenishment work will remain blocked.</span></span>

#### <a name="sales-order-pick"></a><span data-ttu-id="3272e-302">Prelievo ordine cliente</span><span class="sxs-lookup"><span data-stu-id="3272e-302">Sales order pick</span></span>

<span data-ttu-id="3272e-303">Prima che l'attività di rifornimento rimanente possa essere completata, le scorte nell'ubicazione di prelievo devono diminuire fino a un livello in cui è possibile sbloccare il rimanente lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-303">Before the remaining replenishment work task can be completed, the picking location must be depleted of inventory to a level where the remaining replenishment work can be unblocked.</span></span> <span data-ttu-id="3272e-304">In altre parole, la somma della quantità di scorte disponibili nell'ubicazione e la quantità di rifornimento non possono superare il valore **Quantità di overflow**.</span><span class="sxs-lookup"><span data-stu-id="3272e-304">In other words, the sum of the quantity of on-hand inventory in the location and the replenishment quantity can't exceed the **Overflow quantity** value.</span></span> <span data-ttu-id="3272e-305">Quando questa somma è inferiore alla quantità di overflow, il restante lavoro di rifornimento verrà sbloccato.</span><span class="sxs-lookup"><span data-stu-id="3272e-305">When this sum is less than the overflow quantity, the remaining replenishment work will be unblocked.</span></span>

1. <span data-ttu-id="3272e-306">Accedere all'app di magazzino come utente nel magazzino *61*.</span><span class="sxs-lookup"><span data-stu-id="3272e-306">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="3272e-307">(Immettere *61* come ID utente e *1* come password).</span><span class="sxs-lookup"><span data-stu-id="3272e-307">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="3272e-308">Passare a **In uscita \> Prelievo vendite**.</span><span class="sxs-lookup"><span data-stu-id="3272e-308">Go to **Outbound \> Sales Picking**.</span></span>
1. <span data-ttu-id="3272e-309">Immettere il primo ID lavoro per l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="3272e-309">Enter the first work ID for sales order 1.</span></span>

    <span data-ttu-id="3272e-310">Fare riferimento agli ID lavoro per gli ordini di vendita annotati in precedenza, nella pagina **Dettagli del lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3272e-310">Refer to the work IDs for sales orders that you made a note of earlier, on the **Work details** page.</span></span> <span data-ttu-id="3272e-311">L'ID lavoro inserito qui genererà il lavoro di prelievo per una quantità di 10 ea da due ubicazioni separate.</span><span class="sxs-lookup"><span data-stu-id="3272e-311">The work ID that you enter here will generate pick work for a quantity of 10 ea from two separate locations.</span></span>

1. <span data-ttu-id="3272e-312">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-312">Select **OK**.</span></span>

    <span data-ttu-id="3272e-313">La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare per la prima ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-313">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the first location.</span></span>

1. <span data-ttu-id="3272e-314">Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3272e-314">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="3272e-315">Selezionare il pulsante **OK** (simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="3272e-315">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="3272e-316">La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare per la successiva ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-316">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the next location.</span></span>

1. <span data-ttu-id="3272e-317">Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3272e-317">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="3272e-318">Selezionare il pulsante **OK** (simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="3272e-318">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="3272e-319">La pagina **Ordini cliente: inserisci** indica di stoccare entrambi i lavori di prelievo completati nell'ubicazione di staging in uscita.</span><span class="sxs-lookup"><span data-stu-id="3272e-319">The **Sales orders: Put** page instructs you to put away both the completed picking works to the outbound staging location.</span></span>

1. <span data-ttu-id="3272e-320">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-320">Select **OK**.</span></span>

    <span data-ttu-id="3272e-321">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="3272e-321">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="3272e-322">Immettere il secondo ID lavoro per l'ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="3272e-322">Enter the second work ID for sales order 1.</span></span>

    <span data-ttu-id="3272e-323">Esiste solo un'attività di prelievo per questo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-323">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="3272e-324">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-324">Select **OK**.</span></span>

    <span data-ttu-id="3272e-325">La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare.</span><span class="sxs-lookup"><span data-stu-id="3272e-325">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="3272e-326">Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3272e-326">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="3272e-327">La targa specificata sarà una delle targhe generate dal sistema dalle attività di lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-327">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="3272e-328">Per assicurarsi di acquisire l'ID targa corretto, controllare il livello di scorte nella pagibna **Scorte disponibili** per l'articolo, l'ubicazione e la quantità.</span><span class="sxs-lookup"><span data-stu-id="3272e-328">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="3272e-329">Selezionare il pulsante **OK** (simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="3272e-329">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="3272e-330">Confermare le istruzioni per l'attività di isnerimento nell'ubicazione di staging in uscita.</span><span class="sxs-lookup"><span data-stu-id="3272e-330">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="3272e-331">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-331">Select **OK**.</span></span>

    <span data-ttu-id="3272e-332">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="3272e-332">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="3272e-333">L'ordine di vendita 2 è bloccato dal prelievo perché l'attività di rifornimento a cui è collegato non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="3272e-333">Sales order 2 is blocked from picking because the replenishment task that it's linked to isn't completed.</span></span> <span data-ttu-id="3272e-334">Attualmente, vi è ancora una quantità di 30 ea nell'ubicazione di prelievo e la quantità di rifornimento per l'ordine di vendita 2 è di 60 ea.</span><span class="sxs-lookup"><span data-stu-id="3272e-334">Currently, there is still a quantity of 30 ea in the picking location, and the replenishment quantity for sales order 2 is 60 ea.</span></span> <span data-ttu-id="3272e-335">La somma delle scorte disponibili e delle scorte di rifornimento (90 ea) supera la quantità di overflow di 0,65 PL (o 65 ea).</span><span class="sxs-lookup"><span data-stu-id="3272e-335">The sum of the on-hand inventory and the replenishment inventory (90 ea) exceeds the overflow quantity of 0.65 PL (or 65 ea).</span></span> <span data-ttu-id="3272e-336">Prima di completare il lavoro di rifornimento, è necessario eseguire il prelievo per l'ordine di vendita 3.</span><span class="sxs-lookup"><span data-stu-id="3272e-336">Before the replenishment work can be completed, sales order 3 must be picked.</span></span>

1. <span data-ttu-id="3272e-337">Immettere l'ID lavoro per l'ordine cliente 3.</span><span class="sxs-lookup"><span data-stu-id="3272e-337">Enter the work ID for sales order 3.</span></span>

    <span data-ttu-id="3272e-338">Esiste solo un'attività di prelievo per questo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-338">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="3272e-339">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-339">Select **OK**.</span></span>

    <span data-ttu-id="3272e-340">La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare.</span><span class="sxs-lookup"><span data-stu-id="3272e-340">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="3272e-341">Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3272e-341">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="3272e-342">La targa specificata sarà una delle targhe generate dal sistema dalle attività di lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-342">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="3272e-343">Per assicurarsi di acquisire l'ID targa corretto, controllare il livello di scorte nella pagibna **Scorte disponibili** per l'articolo, l'ubicazione e la quantità.</span><span class="sxs-lookup"><span data-stu-id="3272e-343">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="3272e-344">Selezionare il pulsante **OK** (simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="3272e-344">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="3272e-345">Confermare le istruzioni per l'attività di isnerimento nell'ubicazione di staging in uscita.</span><span class="sxs-lookup"><span data-stu-id="3272e-345">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="3272e-346">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-346">Select **OK**.</span></span>

    <span data-ttu-id="3272e-347">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="3272e-347">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="3272e-348">Non appena la somma della quantità disponibile nell'ubicazione di prelievo e la quantità di rifornimento è inferiore alla soglia, sarà possibile elaborare il restante lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-348">As soon as the sum of the on-hand quantity in the picking location and the replenishment quantity is below the threshold, you will be able to process the remaining replenishment work.</span></span>

<span data-ttu-id="3272e-349">Tornare alla pagina **Dettagli del lavoro** e notare che la disponibilità del lavoro di rifornimento per la parte finale di rifornimento (per l'ordine di vendita 2) è *Aperto*, perché ora c'è abbastanza spazio nell'ubicazione per accettare il rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-349">Return to the **Work details** page, and notice that the replenishment work availability for the final piece of replenishment (for sales order 2) is *Open*, because there is now enough space in the location to accept the replenishment.</span></span>

<span data-ttu-id="3272e-350">Ora puoi elaborare questo lavoro di rifornimento tramite il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="3272e-350">You can now process this replenishment work via the mobile device.</span></span>

1. <span data-ttu-id="3272e-351">Passare a **Inventario \> Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="3272e-351">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="3272e-352">Viene richiesto di completare il lavoro di rifornimento rimanente.</span><span class="sxs-lookup"><span data-stu-id="3272e-352">You're prompted to complete the remaining replenishment work.</span></span> <span data-ttu-id="3272e-353">Vengono visualizzati il numero, la quantità e l'ubicazione di prelievo dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="3272e-353">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="3272e-354">Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3272e-354">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="3272e-355">Selezionare il pulsante **OK** (simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="3272e-355">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="3272e-356">Il sistema genera un numero di targa di destinazione per la nuova targa per l'articolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="3272e-356">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="3272e-357">Selezionare **OK** per confermare il valore.</span><span class="sxs-lookup"><span data-stu-id="3272e-357">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="3272e-358">Viene mostrato il lavoro di inserimento che indica all'utente di inserire la targa di destinazione nell'ubicazione di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-358">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="3272e-359">L'ubicazione *Inserisci* dovrebbe essere **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="3272e-359">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="3272e-360">Confermare i dettagli di inserimento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-360">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="3272e-361">Vengono visualizzati i messaggi "Lavoro completato" e "Nessun lavoro disponibile".</span><span class="sxs-lookup"><span data-stu-id="3272e-361">You receive "Work Completed" and "No Work Available" messages.</span></span>

<span data-ttu-id="3272e-362">Ora è possibile scegliere l'ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="3272e-362">You can now pick sales order 2.</span></span> <span data-ttu-id="3272e-363">Si è sbloccato quando sono stati completati i lavori di rifornimento collegati all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3272e-363">It became unblocked when the replenishment work that is linked to the sales order was completed.</span></span>

1. <span data-ttu-id="3272e-364">Immettere l'ID lavoro per l'ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="3272e-364">Enter the work ID for sales order 2.</span></span>

    <span data-ttu-id="3272e-365">Esiste solo un'attività di prelievo per questo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="3272e-365">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="3272e-366">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-366">Select **OK**.</span></span>

    <span data-ttu-id="3272e-367">La pagina delle attività **Ordini cliente: prelievo** mostra il numero di articolo, la quantità e l'ubicazione da cui prelevare.</span><span class="sxs-lookup"><span data-stu-id="3272e-367">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="3272e-368">Nel campo **Targa**, immettere il numero di targa per l'articolo nell'ubicazione visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3272e-368">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="3272e-369">La targa specificata sarà la targa generata dal sistema dall'attività di lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="3272e-369">The license plate that you specify will be the system-generated license plate from the replenishment work task.</span></span> <span data-ttu-id="3272e-370">Per assicurarsi di acquisire l'ID targa corretto, controllare il livello di scorte nella pagibna **Scorte disponibili** per l'articolo, l'ubicazione e la quantità.</span><span class="sxs-lookup"><span data-stu-id="3272e-370">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="3272e-371">Selezionare il pulsante **OK** (simbolo del segno di spunta).</span><span class="sxs-lookup"><span data-stu-id="3272e-371">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="3272e-372">Confermare le istruzioni per l'attività di isnerimento nell'ubicazione di staging in uscita.</span><span class="sxs-lookup"><span data-stu-id="3272e-372">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="3272e-373">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3272e-373">Select **OK**.</span></span>

    <span data-ttu-id="3272e-374">Viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="3272e-374">You receive a "Work Completed" message.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="3272e-375">Note e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="3272e-375">Notes and tips</span></span>

- <span data-ttu-id="3272e-376">Questa funzionalità funziona con tutti i tipi di rifornimento: domanda ondata, min / max, domanda di carico e assegnazione.</span><span class="sxs-lookup"><span data-stu-id="3272e-376">This functionality works with all types of replenishment: wave demand, min/max, load demand, and slotting.</span></span>
- <span data-ttu-id="3272e-377">È possibile sovrascrivere manualmente la disponibilità del lavoro di rifornimento per ciascuna intestazione di lavoro dalla pagina **Dettagli del lavoro** se si desidera.</span><span class="sxs-lookup"><span data-stu-id="3272e-377">You can manually override the replenishment work availability for each work header from the **Work details** page if you want.</span></span>
- <span data-ttu-id="3272e-378">Quando il sistema imposta la disponibilità del lavoro di rifornimento, considera qualsiasi inventario che si trova già nell'ubicazione prima del completamento di qualsiasi lavoro</span><span class="sxs-lookup"><span data-stu-id="3272e-378">When the system sets the replenishment work availability, it considers any inventory that is already in the location before any work is completed</span></span>
- <span data-ttu-id="3272e-379">Ogni lavoro dell'ordine di vendita è collegato a un lavoro di rifornimento specifico.</span><span class="sxs-lookup"><span data-stu-id="3272e-379">Each piece of sales order work is linked to a specific replenishment work.</span></span> <span data-ttu-id="3272e-380">Non esiste una corrispondente funzionalità di disponibilità del lavoro di vendita.</span><span class="sxs-lookup"><span data-stu-id="3272e-380">There is no corresponding sales work availability functionality.</span></span>
