---
title: Creare varianti prodotto predefinite
description: Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 442a5f5b321833c170cfecc4069e62a1254605cd
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270482"
---
# <a name="predefined-product-variants"></a><span data-ttu-id="1622f-103">Varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="1622f-103">Predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a><span data-ttu-id="1622f-104">Scenario di esempio: Creare varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="1622f-104">Example scenario: Create predefined product variants</span></span>

<span data-ttu-id="1622f-105">Questa scenario di esempio mostra come creare varianti prodotto per una rappresentazione generale prodotto mediante combinazioni di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-105">This example scenario shows how to create product variants for a product master using a combinations of product dimensions.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="1622f-106">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="1622f-106">Make demo data available</span></span>

<span data-ttu-id="1622f-107">Per eseguire questo scenario usando i valori soggeriti qui, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica *USMF*.</span><span class="sxs-lookup"><span data-stu-id="1622f-107">To follow this scenario using the values suggested here, you must have demo data installed, and you must select the *USMF* legal entity.</span></span>

### <a name="step-1-create-a-product-master"></a><span data-ttu-id="1622f-108">Passaggio 1: Creare una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="1622f-108">Step 1: Create a product master</span></span>

<span data-ttu-id="1622f-109">Per creare una rappresentazione generale prodotto:</span><span class="sxs-lookup"><span data-stu-id="1622f-109">To create a product master:</span></span>

1. <span data-ttu-id="1622f-110">Andare a **Gestione informazioni sul prodotto > Prodotti > Rappresentazioni generali prodotto**.</span><span class="sxs-lookup"><span data-stu-id="1622f-110">Go to **Product information management > Products > Product masters**.</span></span>
1. <span data-ttu-id="1622f-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1622f-111">Select **New**.</span></span>
1. <span data-ttu-id="1622f-112">Se il campo **Numero prodotto** non mostra già un numero, inserisci un valore.</span><span class="sxs-lookup"><span data-stu-id="1622f-112">If the **Product number** field doesn't already show a number, then enter a value.</span></span> <span data-ttu-id="1622f-113">Questo è obbligatorio solo se nessuna sequenza numerica è stata impostata per il campo.</span><span class="sxs-lookup"><span data-stu-id="1622f-113">This is only required if no number sequence has been set for this field.</span></span>
1. <span data-ttu-id="1622f-114">Immettere un nome nel campo **Nome prodotto**.</span><span class="sxs-lookup"><span data-stu-id="1622f-114">Enter a name in the **Product name** field.</span></span>
1. <span data-ttu-id="1622f-115">Nel campo **Gruppo di dimensioni prodotto** selezionare il gruppo di dimensioni prodotto *SizeCol* (dimensione e colore).</span><span class="sxs-lookup"><span data-stu-id="1622f-115">In the **Product dimension group** field, select the product dimension group *SizeCol* (Size and Color).</span></span>
1. <span data-ttu-id="1622f-116">Selezionare **OK** per creare e aprire la nuova rappresentazione generale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-116">Select **OK** to create and open the new product master.</span></span>

### <a name="step-2-add-product-dimensions"></a><span data-ttu-id="1622f-117">Passaggio 2: Aggiungere dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="1622f-117">Step 2: Add product dimensions</span></span>

<span data-ttu-id="1622f-118">In questo esempio viene illustrato come immettere manualmente le dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="1622f-119">È inoltre possibile scegliere di selezionare un gruppo di dimensioni, colore o stile che include i valori della dimensione prodotto si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1622f-119">You can also choose to select a size, color, or style group that includes the product dimension values you want to use.</span></span>

<span data-ttu-id="1622f-120">Per aggiungere dimensioni prodotto:</span><span class="sxs-lookup"><span data-stu-id="1622f-120">To add product dimensions:</span></span>

1. <span data-ttu-id="1622f-121">Con la nuova rappresentazione generale prodotto ancora aperta, selezionare **Dimensioni prodotto** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="1622f-121">With your new product master still open, select **Product dimensions** on the Action Pane.</span></span>
1. <span data-ttu-id="1622f-122">Apri la scheda **Dimensione** e seleziona **Nuovo** sulla barra degli strumenti per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="1622f-122">Open the **Size** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="1622f-123">Per ogni nuova riga, effettua le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="1622f-123">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="1622f-124">**Dimensione:** seleziona un valore di dimensione.</span><span class="sxs-lookup"><span data-stu-id="1622f-124">**Size:** Select a size value.</span></span>
    - <span data-ttu-id="1622f-125">**Nome**: immetti un nome per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="1622f-125">**Name:** Enter a name for the size.</span></span>
1. <span data-ttu-id="1622f-126">Selezionare **Nuovo** sulla barra degli strumenti e aggiungi una seconda dimensione alla griglia con nuovi **Dimensione** e **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1622f-126">Select **New** on the toolbar and add a second size to the grid with a new **Size** and **Name**.</span></span>
1. <span data-ttu-id="1622f-127">Apri la scheda **Colori** e seleziona **Nuovo** sulla barra degli strumenti per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="1622f-127">Open the **Colors** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="1622f-128">Per ogni nuova riga, effettua le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="1622f-128">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="1622f-129">**Colore:** Seleziona un valore di colore.</span><span class="sxs-lookup"><span data-stu-id="1622f-129">**Color:** Select a color value.</span></span>
    - <span data-ttu-id="1622f-130">**Nome**: immetti un nome per il colore.</span><span class="sxs-lookup"><span data-stu-id="1622f-130">**Name:** Enter a name for the color.</span></span>
1. <span data-ttu-id="1622f-131">Selezionare **Nuovo** sulla barra degli strumenti e aggiungi un secondo colore alla griglia con nuovi **Colore** e **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1622f-131">Select **New** on the toolbar and add a second color to the grid with a new **Color** and **Name**.</span></span>
1. <span data-ttu-id="1622f-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1622f-132">Select **Save**.</span></span>
1. <span data-ttu-id="1622f-133">Chiudi la pagina per tornare alla tua nuova rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-133">Close the page to return to your new product master.</span></span>

### <a name="step-3-generate-product-variants"></a><span data-ttu-id="1622f-134">Passaggio 3: Generare varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="1622f-134">Step 3: Generate product variants</span></span>

> [!NOTE]
> <span data-ttu-id="1622f-135">Questa sezione descrive come generare varianti prodotto quando la funzionalità *Miglioramenti della pagina Suggerimenti variante* non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1622f-135">This section describes how to generate product variants when the *Variant suggestions page improvements* feature isn't enabled.</span></span> <span data-ttu-id="1622f-136">Consulta la sezione successiva per i dettagli su come generare varianti prodotto quando tale funzionalità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1622f-136">See the next section for details about how to generate product variants when that feature is available.</span></span>

<span data-ttu-id="1622f-137">Per generare varianti prodotto:</span><span class="sxs-lookup"><span data-stu-id="1622f-137">To generate product variants:</span></span>

1. <span data-ttu-id="1622f-138">Con la nuova rappresentazione generale prodotto ancora aperta, selezionare **Varianti prodotto** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="1622f-138">With your new product master still open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="1622f-139">Nel riquadro azioni seleziona **Suggerimenti variante**.</span><span class="sxs-lookup"><span data-stu-id="1622f-139">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="1622f-140">Il sistema genera un elenco con tutte le possibili combinazioni delle dimensioni e dei colori definiti per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-140">The system generates a list with all possible combinations of the sizes and colors you defined for the product.</span></span> <span data-ttu-id="1622f-141">Selezionare **Seleziona tutto** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="1622f-141">Select **Select all** on the toolbar.</span></span>
    - <span data-ttu-id="1622f-142">In questo esempio selezionare tutte le possibili varianti.</span><span class="sxs-lookup"><span data-stu-id="1622f-142">In this example, select all of the possible variants.</span></span> <span data-ttu-id="1622f-143">Se si desidera utilizzare solo un sottoinsieme delle possibili combinazioni di dimensioni prodotto, selezionare solo le caselle di controllo richieste in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="1622f-143">If you only want to use a subset of the possible product dimension combinations, select only the required check boxes as needed.</span></span>  
1. <span data-ttu-id="1622f-144">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="1622f-144">Select **Create**.</span></span>
1. <span data-ttu-id="1622f-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1622f-145">Select **Save**.</span></span>

## <a name="improved-variant-suggestions"></a><span data-ttu-id="1622f-146">Miglioramenti ai suggerimenti variante</span><span class="sxs-lookup"><span data-stu-id="1622f-146">Improved variant suggestions</span></span>

<span data-ttu-id="1622f-147">La funzionalità *Miglioramenti della pagina Suggerimenti variante* migliora la pagina **Suggerimenti variante** per affrontare i problemi di prestazioni e usabilità per le aziende che hanno un numero elevato di combinazioni di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-147">The *Variant suggestions page improvements* feature improves the **Variant suggestions** page to address performance and usability issues for companies that have a high number of product dimension combinations.</span></span> <span data-ttu-id="1622f-148">Il processo migliorato per la selezione dei valori delle dimensioni prodotto per cui generare suggerimenti di varianti rende più veloce e più facile identificare e rilasciare la serie pertinente di varianti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-148">The enhanced process for selecting the product dimension values for which to generate variant suggestions makes it faster and easier to identify and release the relevant set of product variants.</span></span>

<span data-ttu-id="1622f-149">I seguenti miglioramenti vengono aggiunti da questa funzione:</span><span class="sxs-lookup"><span data-stu-id="1622f-149">The following improvements are added by this feature:</span></span>

- <span data-ttu-id="1622f-150">**Generazione posticipata di suggerimenti su varianti:** la pagina **Suggerimenti variante** non mostra più i suggerimenti quando viene aperta per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="1622f-150">**Deferred generation of variant suggestions:** The **Variant suggestions** page no longer shows suggestions when you first open it.</span></span> <span data-ttu-id="1622f-151">Invece, è necessario scegliere esplicitamente i valori necessari e quindi selezionare il pulsante **Suggerisci** per generare le combinazioni.</span><span class="sxs-lookup"><span data-stu-id="1622f-151">Instead, you must explicitly choose which values you will need and then select the **Suggest** button to generate the combinations.</span></span> <span data-ttu-id="1622f-152">Ciò rende il processo più visibile e interattivo.</span><span class="sxs-lookup"><span data-stu-id="1622f-152">This makes the process more visible and interactive.</span></span>
- <span data-ttu-id="1622f-153">**Selezione di valori di dimensioni:** Quando si dispone di molti valori di dimensione, in genere si è interessati a generare suggerimenti di varianti che ne includano solo alcuni (ad esempio quando si introduce un nuovo set di colori o stili).</span><span class="sxs-lookup"><span data-stu-id="1622f-153">**Selection of dimensions values:** When you have many dimension values, you are typically interested in generating variant suggestions that include just a few of them (such as when introducing a new set of colors or styles).</span></span> <span data-ttu-id="1622f-154">Con il design migliorato, è possibile selezionare i valori di dimensione per i quali si desidera generare suggerimenti di varianti di prodotto.</span><span class="sxs-lookup"><span data-stu-id="1622f-154">With the improved design, you can select the dimension values for which you want to generate product variant suggestions.</span></span> <span data-ttu-id="1622f-155">Ciò aumenta notevolmente la rilevanza delle varianti suggerite e migliora sia le prestazioni del sistema sia la produttività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1622f-155">This greatly increases the relevance of the suggested variants and improves both system performance and user productivity.</span></span>

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a><span data-ttu-id="1622f-156">Attivare la funzionalità Miglioramenti della pagina Suggerimenti variante</span><span class="sxs-lookup"><span data-stu-id="1622f-156">Turn on the Variant suggestions page improvements feature</span></span>

<span data-ttu-id="1622f-157">Prima di poter utilizzare la funzionalità *Miglioramenti della pagina Suggerimenti variante*, tale funzionalità deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="1622f-157">Before you can use *Variant suggestions page improvements* feature, it must be turned on in your system.</span></span> <span data-ttu-id="1622f-158">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="1622f-158">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="1622f-159">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1622f-159">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="1622f-160">**Modulo:** *Gestione informazioni sul prodotto*</span><span class="sxs-lookup"><span data-stu-id="1622f-160">**Module:** *Product information management*</span></span>
- <span data-ttu-id="1622f-161">**Nome funzionalità:** *Miglioramenti della pagina Suggerimenti variante*</span><span class="sxs-lookup"><span data-stu-id="1622f-161">**Feature name:** *Variant suggestions page improvements*</span></span>

### <a name="work-with-the-improved-variant-suggestions"></a><span data-ttu-id="1622f-162">Lavorare con i suggerimenti di varianti migliorati</span><span class="sxs-lookup"><span data-stu-id="1622f-162">Work with the improved variant suggestions</span></span>

<span data-ttu-id="1622f-163">Per generare suggerimenti di varianti prodotto quando la funzionalità *Miglioramenti della pagina Suggerimenti variante* è abilitata:</span><span class="sxs-lookup"><span data-stu-id="1622f-163">To generate product variant suggestions when the *Variant suggestions page improvements* feature is enabled:</span></span>

1. <span data-ttu-id="1622f-164">Aprire o creare una rappresentazione generale del prodotto e aggiungervi le dimensioni del prodotto richieste, come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="1622f-164">Open or create a product master and add the required product dimensions to it, as described in the previous section.</span></span>
1. <span data-ttu-id="1622f-165">Con la rappresentazione generale prodotto aperta, selezionare **Varianti prodotto** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="1622f-165">With the product master open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="1622f-166">Nel riquadro azioni seleziona **Suggerimenti variante**.</span><span class="sxs-lookup"><span data-stu-id="1622f-166">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="1622f-167">Selezionare i valori da usare per ognuna delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="1622f-167">Select the values that you want to use for each of the dimensions.</span></span>
1. <span data-ttu-id="1622f-168">Nella barra degli strumenti in alto, seleziona **Suggerisci**.</span><span class="sxs-lookup"><span data-stu-id="1622f-168">On the top toolbar, select **Suggest**.</span></span>
1. <span data-ttu-id="1622f-169">Il sistema genera un elenco con tutte le possibili combinazioni delle dimensioni e dei colori selezionati.</span><span class="sxs-lookup"><span data-stu-id="1622f-169">The system generates a list with all possible combinations of the sizes and colors you selected.</span></span> <span data-ttu-id="1622f-170">Nella scheda dettaglio **Varianti suggerite**, selezionare la casella di controllo per ciascuna combinazione di dimensioni prodotto che si desidera utilizzare oppure selezionare **Seleziona tutto** sulla barra degli strumenti per selezionarle tutte.</span><span class="sxs-lookup"><span data-stu-id="1622f-170">On the **Suggested variants** FastTab, select the check box for each product dimension combination that you want to use, or select **Select all** on the toolbar to select all of them.</span></span>  
1. <span data-ttu-id="1622f-171">Selezionare **Crea** per aggiungere le varianti alla rappresentazione generale prodotto corrente.</span><span class="sxs-lookup"><span data-stu-id="1622f-171">Select **Create** to add the variants to the current product master.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
