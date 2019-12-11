---
title: Utilizzare i frammenti
description: In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: d92b9077f8584bfa0710bbaacbc7caa3220baa4a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698098"
---
# <a name="work-with-fragments"></a><span data-ttu-id="ccdbc-103">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="ccdbc-103">Work with fragments</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ccdbc-104">In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ccdbc-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ccdbc-105">Overview</span></span>

<span data-ttu-id="ccdbc-106">I frammenti consentono un'esperienza di creazione centralizzata per le configurazioni di moduli che devono essere riutilizzate in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="ccdbc-107">Ad esempio, intestazioni, piè di pagina e banner sono spesso configurati come frammenti, in quanto sono condivisi da molte pagine.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="ccdbc-108">È possibile considerare i frammenti come pagine Web in miniatura inseribili in altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="ccdbc-109">I frammenti hanno un ciclo di vita proprio.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="ccdbc-110">In altre parole, vengono creati, utilizzati come riferimento, aggiornati ed eliminati come entità indipendenti negli strumenti di creazione.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="ccdbc-111">Dopo che i frammenti sono stati configurati, possono essere utilizzati in tutte le aree della struttura del sito in cui l'uso dei moduli è consentito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="ccdbc-112">È possibile fare riferimento ai moduli in pagine, layout, modelli e altri frammenti.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="ccdbc-113">I frammenti possono essere nidificati fino a sette livelli di profondità in altri frammenti.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="ccdbc-114">Ad esempio, se si desidera promuovere un evento promozionale in molte pagine del sito, è possibile utilizzare un frammento.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="ccdbc-115">Il primo passaggio del processo di creazione di un nuovo frammento consiste nel selezionare il tipo di modulo da cui iniziare.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="ccdbc-116">Per questo esempio, genereremo un frammento da un modulo Hero.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="ccdbc-117">I frammenti possono essere creati da qualsiasi tipo di modulo.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="ccdbc-118">È quindi possibile configurare il frammento hero con lo specifico contenuto promozionale.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="ccdbc-119">È anche possibile localizzarlo come necessario.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-119">You can also localize it as you require.</span></span> <span data-ttu-id="ccdbc-120">Il nuovo frammento hero autonomo può quindi essere utilizzato come modulo preconfigurato in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="ccdbc-121">È possibile aggiungerlo facilmente a modelli, pagine specifiche o altri frammenti che possono contenere moduli Hero.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="ccdbc-122">Tutte le posizioni in cui il frammento viene aggiunto sono riferimenti al frammento hero centrale creato.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="ccdbc-123">Se si pubblicano modifiche al frammento, queste vengono immediatamente riflesse in tutte le posizioni in cui si fa riferimento al frammento nel sito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="ccdbc-124">Di conseguenza, i frammenti sono un modo potente ed efficiente di riutilizzare e gestire centralmente le configurazioni di moduli in un sito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="ccdbc-125">Un uso efficiente dei frammenti consente di aumentare notevolmente l'agilità e contribuisce a ridurre i costi associati alla gestione del contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="ccdbc-126">Nella figura seguente viene illustrato come è possibile utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Figura che mostra come utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="ccdbc-128">Creare un frammento</span><span class="sxs-lookup"><span data-stu-id="ccdbc-128">Create a fragment</span></span>

<span data-ttu-id="ccdbc-129">È possibile creare un nuovo frammento o salvare una configurazione di modulo esistente come frammento.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="create-a-new-fragment"></a><span data-ttu-id="ccdbc-130">Creare un nuovo frammento</span><span class="sxs-lookup"><span data-stu-id="ccdbc-130">Create a new fragment</span></span>

<span data-ttu-id="ccdbc-131">Per creare un nuovo frammento, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-131">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="ccdbc-132">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-132">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="ccdbc-133">Selezionare **Nuovo frammento pagina**.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-133">Select **New Page Fragment**.</span></span> <span data-ttu-id="ccdbc-134">Viene visualizzata una finestra di dialogo contenente tutti i tipi di modulo disponibili.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-134">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="ccdbc-135">Come indicato in precedenza, i frammenti possono essere creati da qualsiasi tipo di modulo.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-135">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="ccdbc-136">Selezionare un tipo di modulo per il frammento e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-136">Select a module type for your fragment, and then select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="ccdbc-137">Se si seleziona un tipo di modulo contenitore generico, si avrà a disposizione la massima flessibilità quando si dovrà aggiornare e configurare il frammento in seguito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-137">By selecting a generic container module type, you get the most flexibility when you must update and configure your fragment later.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="ccdbc-138">Salvare una configurazione di modulo esistente come frammento</span><span class="sxs-lookup"><span data-stu-id="ccdbc-138">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="ccdbc-139">Per convertire un modulo configurato precedentemente in un frammento riutilizzabile, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-139">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="ccdbc-140">Aprire una pagina o un modello che contiene il modulo da convertire in frammento.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-140">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="ccdbc-141">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al nome del modulo e quindi selezionare **Salva come frammento**.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-141">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module, and then select **Save as Fragment**.</span></span> <span data-ttu-id="ccdbc-142">Viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-142">A dialog box appears.</span></span>
1. <span data-ttu-id="ccdbc-143">Immettere un nome e i metadati per il frammento.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-143">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="ccdbc-144">Selezionare **OK** per salvare la configurazione di modulo come frammento che è possibile aggiungere ad altre pagine.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-144">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="ccdbc-145">Aggiungere, rimuovere o modificare frammenti in una pagina</span><span class="sxs-lookup"><span data-stu-id="ccdbc-145">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="ccdbc-146">Nelle procedure riportate di seguito viene descritto come aggiungere, rimuovere e modificare frammenti.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-146">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="ccdbc-147">Aggiungere un frammento</span><span class="sxs-lookup"><span data-stu-id="ccdbc-147">Add a fragment</span></span>

<span data-ttu-id="ccdbc-148">Per aggiungere un frammento a una pagina, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-148">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="ccdbc-149">Nella riquadro a sinistra, selezionare un contenitore o uno slot a cui è possibile aggiungere moduli figlio.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-149">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="ccdbc-150">Selezionare il pulsante con i puntini di sospensione al nome del contenitore o dello slot, quindi selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-150">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="ccdbc-151">Viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-151">A dialog box appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ccdbc-152">Se il contenitore o lo slot non supporta nuovi moduli figlio, l'opzione **Aggiungi frammento** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-152">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>

1. <span data-ttu-id="ccdbc-153">Nella finestra di dialogo, cercare e selezionare un frammento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-153">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="ccdbc-154">Se non sono elencati frammenti disponibili, è necessario dapprima creare un frammento da un tipo di modulo che lo slot o il contenitore supporta.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-154">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="ccdbc-155">Selezionare **OK** per aggiungere il frammento selezionato al contenitore o allo slot selezionato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-155">Select **OK** to add the selected fragment to the selected container or slot on your page.</span></span>

> [!NOTE]
> <span data-ttu-id="ccdbc-156">I moduli consentiti in un contenitore o in uno slot sono definiti in base al modello della pagina o alle definizioni dei moduli.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-156">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="ccdbc-157">Rimuovere un frammento</span><span class="sxs-lookup"><span data-stu-id="ccdbc-157">Remove a fragment</span></span>

<span data-ttu-id="ccdbc-158">Per rimuovere un frammento da uno slot o un contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-158">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="ccdbc-159">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del frammento da rimuovere e quindi selezionare il pulsante Cestino.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-159">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="ccdbc-160">Quando viene richiesto di confermare la rimozione del frammento, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-160">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="ccdbc-161">Quando si rimuove un frammento da una pagina, si rimuove solo il riferimento allo stesso da quella pagina.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-161">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="ccdbc-162">**Non** si elimina il frammento dal sito.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-162">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="ccdbc-163">Per eliminare frammenti dal sito, è necessario utilizzare l'interfaccia utente del controllo frammenti.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-163">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="ccdbc-164">È possibile eliminare frammenti da un sito solo se si fa riferimento agli stessi con un qualsiasi modello, pagina o altro frammento.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-164">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="ccdbc-165">Modificare un frammento</span><span class="sxs-lookup"><span data-stu-id="ccdbc-165">Edit a fragment</span></span>

<span data-ttu-id="ccdbc-166">Per modificare i frammenti, è necessario utilizzare l'interfaccia utente dell'editor di frammenti.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-166">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="ccdbc-167">Questa restrizione è dovuta alla struttura.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-167">This restriction is by design.</span></span> <span data-ttu-id="ccdbc-168">Impedisce agli autori di confondere il processo di modifica dei moduli per una pagina specifica con il processo di modifica di frammenti che potrebbero essere condivisi da più pagine.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-168">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="ccdbc-169">Per modificare un frammento, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-169">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="ccdbc-170">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-170">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="ccdbc-171">In **Frammenti**, selezionare il frammento da modificare.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-171">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="ccdbc-172">Modificare le proprietà del modulo del frammento e la struttura come necessario.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-172">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="ccdbc-173">Il processo è analogo a quello per modificare i moduli nella visualizzazione dell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-173">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="ccdbc-174">È anche possibile modificare un frammento selezionandolo in una pagina, in un modello o in un frammento padre e quindi selezionando **Modifica frammento** nel riquadro delle proprietà a destra.</span><span class="sxs-lookup"><span data-stu-id="ccdbc-174">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ccdbc-175">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ccdbc-175">Additional resources</span></span>

[<span data-ttu-id="ccdbc-176">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="ccdbc-176">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="ccdbc-177">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="ccdbc-177">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="ccdbc-178">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="ccdbc-178">Work with preset layouts</span></span>](work-with-layouts.md)
