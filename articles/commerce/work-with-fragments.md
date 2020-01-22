---
title: Utilizzare i frammenti
description: In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 32482538b2913e6585257bcf7a1cbe780d3cdd30
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914702"
---
# <a name="work-with-fragments"></a><span data-ttu-id="27ecb-103">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="27ecb-103">Work with fragments</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="27ecb-104">In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="27ecb-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="27ecb-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="27ecb-105">Overview</span></span>

<span data-ttu-id="27ecb-106">I frammenti consentono un'esperienza di creazione centralizzata per le configurazioni di moduli che devono essere riutilizzate in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="27ecb-107">Ad esempio, intestazioni, piè di pagina e banner sono spesso configurati come frammenti, in quanto sono condivisi da molte pagine.</span><span class="sxs-lookup"><span data-stu-id="27ecb-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="27ecb-108">È possibile considerare i frammenti come pagine Web in miniatura inseribili in altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="27ecb-109">I frammenti hanno un ciclo di vita proprio.</span><span class="sxs-lookup"><span data-stu-id="27ecb-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="27ecb-110">In altre parole, vengono creati, utilizzati come riferimento, aggiornati ed eliminati come entità indipendenti negli strumenti di creazione.</span><span class="sxs-lookup"><span data-stu-id="27ecb-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="27ecb-111">Dopo che i frammenti sono stati configurati, possono essere utilizzati in tutte le aree della struttura del sito in cui l'uso dei moduli è consentito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="27ecb-112">È possibile fare riferimento ai moduli in pagine, layout, modelli e altri frammenti.</span><span class="sxs-lookup"><span data-stu-id="27ecb-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="27ecb-113">I frammenti possono essere nidificati fino a sette livelli di profondità in altri frammenti.</span><span class="sxs-lookup"><span data-stu-id="27ecb-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="27ecb-114">Ad esempio, se si desidera promuovere un evento promozionale in molte pagine del sito, è possibile utilizzare un frammento.</span><span class="sxs-lookup"><span data-stu-id="27ecb-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="27ecb-115">Il primo passaggio del processo di creazione di un nuovo frammento consiste nel selezionare il tipo di modulo da cui iniziare.</span><span class="sxs-lookup"><span data-stu-id="27ecb-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="27ecb-116">Per questo esempio, genereremo un frammento da un modulo Hero.</span><span class="sxs-lookup"><span data-stu-id="27ecb-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="27ecb-117">I frammenti possono essere creati da qualsiasi tipo di modulo.</span><span class="sxs-lookup"><span data-stu-id="27ecb-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="27ecb-118">È quindi possibile configurare il frammento hero con lo specifico contenuto promozionale.</span><span class="sxs-lookup"><span data-stu-id="27ecb-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="27ecb-119">È anche possibile localizzarlo come necessario.</span><span class="sxs-lookup"><span data-stu-id="27ecb-119">You can also localize it as you require.</span></span> <span data-ttu-id="27ecb-120">Il nuovo frammento hero autonomo può quindi essere utilizzato come modulo preconfigurato in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="27ecb-121">È possibile aggiungerlo facilmente a modelli, pagine specifiche o altri frammenti che possono contenere moduli Hero.</span><span class="sxs-lookup"><span data-stu-id="27ecb-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="27ecb-122">Tutte le posizioni in cui il frammento viene aggiunto sono riferimenti al frammento hero centrale creato.</span><span class="sxs-lookup"><span data-stu-id="27ecb-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="27ecb-123">Se si pubblicano modifiche al frammento, queste vengono immediatamente riflesse in tutte le posizioni in cui si fa riferimento al frammento nel sito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="27ecb-124">Di conseguenza, i frammenti sono un modo potente ed efficiente di riutilizzare e gestire centralmente le configurazioni di moduli in un sito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="27ecb-125">Un uso efficiente dei frammenti consente di aumentare notevolmente l'agilità e contribuisce a ridurre i costi associati alla gestione del contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="27ecb-126">Nella figura seguente viene illustrato come è possibile utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="27ecb-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Figura che mostra come utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="27ecb-128">Creare un frammento</span><span class="sxs-lookup"><span data-stu-id="27ecb-128">Create a fragment</span></span>

<span data-ttu-id="27ecb-129">È possibile creare un nuovo frammento o salvare una configurazione di modulo esistente come frammento.</span><span class="sxs-lookup"><span data-stu-id="27ecb-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="create-a-new-fragment"></a><span data-ttu-id="27ecb-130">Creare un nuovo frammento</span><span class="sxs-lookup"><span data-stu-id="27ecb-130">Create a new fragment</span></span>

<span data-ttu-id="27ecb-131">Per creare un nuovo frammento, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="27ecb-131">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="27ecb-132">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="27ecb-132">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="27ecb-133">Selezionare **Nuovo frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="27ecb-133">Select **New Page Fragment**.</span></span> <span data-ttu-id="27ecb-134">Viene visualizzata una finestra di dialogo contenente tutti i tipi di modulo disponibili.</span><span class="sxs-lookup"><span data-stu-id="27ecb-134">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="27ecb-135">Come indicato in precedenza, i frammenti possono essere creati da qualsiasi tipo di modulo.</span><span class="sxs-lookup"><span data-stu-id="27ecb-135">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="27ecb-136">Selezionare un tipo di modulo per il frammento e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="27ecb-136">Select a module type for your fragment, and then select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="27ecb-137">Se si seleziona un tipo di modulo contenitore generico, si avrà a disposizione la massima flessibilità quando si dovrà aggiornare e configurare il frammento in seguito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-137">By selecting a generic container module type, you get the most flexibility when you must update and configure your fragment later.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="27ecb-138">Salvare una configurazione di modulo esistente come frammento</span><span class="sxs-lookup"><span data-stu-id="27ecb-138">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="27ecb-139">Per convertire un modulo configurato precedentemente in un frammento riutilizzabile, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="27ecb-139">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="27ecb-140">Aprire una pagina o un modello che contiene il modulo da convertire in frammento.</span><span class="sxs-lookup"><span data-stu-id="27ecb-140">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="27ecb-141">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al nome del modulo e quindi selezionare **Salva come frammento**.</span><span class="sxs-lookup"><span data-stu-id="27ecb-141">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module, and then select **Save as Fragment**.</span></span> <span data-ttu-id="27ecb-142">Viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="27ecb-142">A dialog box appears.</span></span>
1. <span data-ttu-id="27ecb-143">Immettere un nome e i metadati per il frammento.</span><span class="sxs-lookup"><span data-stu-id="27ecb-143">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="27ecb-144">Selezionare **OK** per salvare la configurazione di modulo come frammento che è possibile aggiungere ad altre pagine.</span><span class="sxs-lookup"><span data-stu-id="27ecb-144">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="27ecb-145">Aggiungere, rimuovere o modificare frammenti in una pagina</span><span class="sxs-lookup"><span data-stu-id="27ecb-145">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="27ecb-146">Nelle procedure riportate di seguito viene descritto come aggiungere, rimuovere e modificare frammenti.</span><span class="sxs-lookup"><span data-stu-id="27ecb-146">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="27ecb-147">Aggiungere un frammento</span><span class="sxs-lookup"><span data-stu-id="27ecb-147">Add a fragment</span></span>

<span data-ttu-id="27ecb-148">Per aggiungere un frammento a una pagina, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-148">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="27ecb-149">Nella riquadro a sinistra, selezionare un contenitore o uno slot a cui è possibile aggiungere moduli figlio.</span><span class="sxs-lookup"><span data-stu-id="27ecb-149">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="27ecb-150">Selezionare il pulsante con i puntini di sospensione al nome del contenitore o dello slot, quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="27ecb-150">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="27ecb-151">Viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="27ecb-151">A dialog box appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27ecb-152">Se il contenitore o lo slot non supporta nuovi moduli figlio, l'opzione **Aggiungi frammento** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="27ecb-152">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>

1. <span data-ttu-id="27ecb-153">Nella finestra di dialogo, cercare e selezionare un frammento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="27ecb-153">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="27ecb-154">Se non sono elencati frammenti disponibili, è necessario dapprima creare un frammento da un tipo di modulo che lo slot o il contenitore supporta.</span><span class="sxs-lookup"><span data-stu-id="27ecb-154">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="27ecb-155">Selezionare **OK** per aggiungere il frammento selezionato al contenitore o allo slot selezionato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="27ecb-155">Select **OK** to add the selected fragment to the selected container or slot on your page.</span></span>

> [!NOTE]
> <span data-ttu-id="27ecb-156">I moduli consentiti in un contenitore o in uno slot sono definiti in base al modello della pagina o alle definizioni dei moduli.</span><span class="sxs-lookup"><span data-stu-id="27ecb-156">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="27ecb-157">Rimuovere un frammento</span><span class="sxs-lookup"><span data-stu-id="27ecb-157">Remove a fragment</span></span>

<span data-ttu-id="27ecb-158">Per rimuovere un frammento da uno slot o un contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="27ecb-158">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="27ecb-159">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del frammento da rimuovere e quindi selezionare il pulsante Cestino.</span><span class="sxs-lookup"><span data-stu-id="27ecb-159">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="27ecb-160">Quando viene richiesto di confermare la rimozione del frammento, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="27ecb-160">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="27ecb-161">Quando si rimuove un frammento da una pagina, si rimuove solo il riferimento allo stesso da quella pagina.</span><span class="sxs-lookup"><span data-stu-id="27ecb-161">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="27ecb-162">**Non** si elimina il frammento dal sito.</span><span class="sxs-lookup"><span data-stu-id="27ecb-162">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="27ecb-163">Per eliminare frammenti dal sito, è necessario utilizzare l'interfaccia utente del controllo frammenti.</span><span class="sxs-lookup"><span data-stu-id="27ecb-163">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="27ecb-164">È possibile eliminare frammenti da un sito solo se si fa riferimento agli stessi con un qualsiasi modello, pagina o altro frammento.</span><span class="sxs-lookup"><span data-stu-id="27ecb-164">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="27ecb-165">Modificare un frammento</span><span class="sxs-lookup"><span data-stu-id="27ecb-165">Edit a fragment</span></span>

<span data-ttu-id="27ecb-166">Per modificare i frammenti, è necessario utilizzare l'interfaccia utente dell'editor di frammenti.</span><span class="sxs-lookup"><span data-stu-id="27ecb-166">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="27ecb-167">Questa restrizione è dovuta alla struttura.</span><span class="sxs-lookup"><span data-stu-id="27ecb-167">This restriction is by design.</span></span> <span data-ttu-id="27ecb-168">Impedisce agli autori di confondere il processo di modifica dei moduli per una pagina specifica con il processo di modifica di frammenti che potrebbero essere condivisi da più pagine.</span><span class="sxs-lookup"><span data-stu-id="27ecb-168">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="27ecb-169">Per modificare un frammento, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="27ecb-169">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="27ecb-170">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="27ecb-170">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="27ecb-171">In **Frammenti**, selezionare il frammento da modificare.</span><span class="sxs-lookup"><span data-stu-id="27ecb-171">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="27ecb-172">Modificare le proprietà del modulo del frammento e la struttura come necessario.</span><span class="sxs-lookup"><span data-stu-id="27ecb-172">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="27ecb-173">Il processo è analogo a quello per modificare i moduli nella visualizzazione dell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="27ecb-173">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="27ecb-174">È anche possibile modificare un frammento selezionandolo in una pagina, in un modello o in un frammento padre e quindi selezionando **Modifica frammento** nel riquadro delle proprietà a destra.</span><span class="sxs-lookup"><span data-stu-id="27ecb-174">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27ecb-175">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="27ecb-175">Additional resources</span></span>

[<span data-ttu-id="27ecb-176">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="27ecb-176">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="27ecb-177">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="27ecb-177">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="27ecb-178">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="27ecb-178">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="27ecb-179">Utilizzare i gruppi di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="27ecb-179">Work with publish groups</span></span>](publish-groups.md)
