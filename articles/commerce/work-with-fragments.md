---
title: Utilizzare i frammenti
description: In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3df2d99ef10f909cedef16167fb8d5a0024683b3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210949"
---
# <a name="work-with-fragments"></a><span data-ttu-id="227c8-103">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="227c8-103">Work with fragments</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="227c8-104">In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="227c8-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="227c8-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="227c8-105">Overview</span></span>

<span data-ttu-id="227c8-106">I frammenti consentono un'esperienza di creazione centralizzata per le configurazioni di moduli che devono essere riutilizzate in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="227c8-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="227c8-107">Ad esempio, intestazioni, piè di pagina e banner sono spesso configurati come frammenti, in quanto sono condivisi da molte pagine.</span><span class="sxs-lookup"><span data-stu-id="227c8-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="227c8-108">È possibile considerare i frammenti come pagine Web in miniatura inseribili in altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="227c8-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="227c8-109">I frammenti hanno un ciclo di vita proprio.</span><span class="sxs-lookup"><span data-stu-id="227c8-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="227c8-110">In altre parole, vengono creati, utilizzati come riferimento, aggiornati ed eliminati come entità indipendenti negli strumenti di creazione.</span><span class="sxs-lookup"><span data-stu-id="227c8-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="227c8-111">Dopo che i frammenti sono stati configurati, possono essere utilizzati in tutte le aree della struttura del sito in cui l'uso dei moduli è consentito.</span><span class="sxs-lookup"><span data-stu-id="227c8-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="227c8-112">È possibile fare riferimento ai moduli in pagine, layout, modelli e altri frammenti.</span><span class="sxs-lookup"><span data-stu-id="227c8-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="227c8-113">I frammenti possono essere nidificati fino a sette livelli di profondità in altri frammenti.</span><span class="sxs-lookup"><span data-stu-id="227c8-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="227c8-114">Ad esempio, se si desidera promuovere un evento promozionale in molte pagine del sito, è possibile utilizzare un frammento.</span><span class="sxs-lookup"><span data-stu-id="227c8-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="227c8-115">Il primo passaggio del processo di creazione di un nuovo frammento consiste nel selezionare il tipo di modulo da cui iniziare.</span><span class="sxs-lookup"><span data-stu-id="227c8-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="227c8-116">Per questo esempio, genereremo un frammento da un modulo Hero.</span><span class="sxs-lookup"><span data-stu-id="227c8-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="227c8-117">I frammenti possono essere creati da qualsiasi tipo di modulo.</span><span class="sxs-lookup"><span data-stu-id="227c8-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="227c8-118">È quindi possibile configurare il frammento hero con lo specifico contenuto promozionale.</span><span class="sxs-lookup"><span data-stu-id="227c8-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="227c8-119">È anche possibile localizzarlo come necessario.</span><span class="sxs-lookup"><span data-stu-id="227c8-119">You can also localize it as you require.</span></span> <span data-ttu-id="227c8-120">Il nuovo frammento hero autonomo può quindi essere utilizzato come modulo preconfigurato in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="227c8-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="227c8-121">È possibile aggiungerlo facilmente a modelli, pagine specifiche o altri frammenti che possono contenere moduli Hero.</span><span class="sxs-lookup"><span data-stu-id="227c8-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="227c8-122">Tutte le posizioni in cui il frammento viene aggiunto sono riferimenti al frammento hero centrale creato.</span><span class="sxs-lookup"><span data-stu-id="227c8-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="227c8-123">Se si pubblicano modifiche al frammento, queste vengono immediatamente riflesse in tutte le posizioni in cui si fa riferimento al frammento nel sito.</span><span class="sxs-lookup"><span data-stu-id="227c8-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="227c8-124">Di conseguenza, i frammenti sono un modo potente ed efficiente di riutilizzare e gestire centralmente le configurazioni di moduli in un sito.</span><span class="sxs-lookup"><span data-stu-id="227c8-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="227c8-125">Un uso efficiente dei frammenti consente di aumentare notevolmente l'agilità e contribuisce a ridurre i costi associati alla gestione del contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="227c8-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="227c8-126">Nella figura seguente viene illustrato come è possibile utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="227c8-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Figura che mostra come utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="227c8-128">Creare un frammento</span><span class="sxs-lookup"><span data-stu-id="227c8-128">Create a fragment</span></span>

<span data-ttu-id="227c8-129">È possibile creare un nuovo frammento o salvare una configurazione di modulo esistente come frammento.</span><span class="sxs-lookup"><span data-stu-id="227c8-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="227c8-130">Salvare una configurazione di modulo esistente come frammento</span><span class="sxs-lookup"><span data-stu-id="227c8-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="227c8-131">Per convertire un modulo configurato precedentemente in un frammento riutilizzabile in Creazione di siti Web di Commerce, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="227c8-131">To convert a previously configured module to a reusable fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="227c8-132">Aprire una pagina o un modello che contiene il modulo da convertire in frammento.</span><span class="sxs-lookup"><span data-stu-id="227c8-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="227c8-133">Nel riquadro struttura a sinistra o direttamente nel generatore di pagine visivo, selezionare il modulo precedentemente configurato.</span><span class="sxs-lookup"><span data-stu-id="227c8-133">In the outline pane on the left or directly in visual page builder, select the previously configured module.</span></span>
1. <span data-ttu-id="227c8-134">Selezionare i puntini di sospensione (**...**) accanto al nome del modulo nel riquadro struttura o nella barra degli strumenti del modulo nel generatore di pagine visivo.</span><span class="sxs-lookup"><span data-stu-id="227c8-134">Select the ellipsis (**...**) next to the name of the module in either the outline pane or the selected module's toolbar in visual page builder.</span></span> 
1. <span data-ttu-id="227c8-135">Selezionare **Condividi come frammento**.</span><span class="sxs-lookup"><span data-stu-id="227c8-135">Select **Share as fragment**.</span></span> 
1. <span data-ttu-id="227c8-136">Nella finestra di dialogo **Salva come frammento** immettere un nome per il frammento.</span><span class="sxs-lookup"><span data-stu-id="227c8-136">In the **Save as fragment** dialog box, enter a name for the fragment.</span></span>
1. <span data-ttu-id="227c8-137">Selezionare **OK** per salvare la configurazione di modulo come frammento che è possibile aggiungere ad altre pagine.</span><span class="sxs-lookup"><span data-stu-id="227c8-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>
<!-- The following image shows how to save a module configuration as a fragment.-->
<!--![A screen capture of how to save a module configuration as a fragment](./media/save-as-fragment.png)-->

### <a name="create-a-new-fragment"></a><span data-ttu-id="227c8-138">Crea un nuovo frammento</span><span class="sxs-lookup"><span data-stu-id="227c8-138">Create a new fragment</span></span>

<span data-ttu-id="227c8-139">Per creare un nuovo frammento in Creazione di siti Web di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="227c8-139">To create a new fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="227c8-140">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="227c8-140">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="227c8-141">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="227c8-141">Select **New**.</span></span> <span data-ttu-id="227c8-142">Viene visualizzata una finestra di dialogo **Nuovo frammento** contenente tutti i tipi di modulo disponibili.</span><span class="sxs-lookup"><span data-stu-id="227c8-142">A **New fragment** dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="227c8-143">Come indicato in precedenza, i frammenti possono essere creati da qualsiasi tipo di modulo.</span><span class="sxs-lookup"><span data-stu-id="227c8-143">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="227c8-144">Selezionare un tipo di modulo per il frammento.</span><span class="sxs-lookup"><span data-stu-id="227c8-144">Select a module type for your fragment.</span></span>

<!-- The following image shows where to create a new fragment.-->
<!-- ![A screen capture of where to create a new fragment](./media/fragment-nav-menu.png)-->
> [!TIP]
> <span data-ttu-id="227c8-145">Se si seleziona un tipo di modulo contenitore generico, si avrà a disposizione la massima flessibilità quando si dovrà aggiornare e configurare il frammento in seguito.</span><span class="sxs-lookup"><span data-stu-id="227c8-145">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="227c8-146">Aggiungere, rimuovere o modificare frammenti in una pagina</span><span class="sxs-lookup"><span data-stu-id="227c8-146">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="227c8-147">Nelle procedure riportate di seguito viene descritto come aggiungere, rimuovere e modificare frammenti.</span><span class="sxs-lookup"><span data-stu-id="227c8-147">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="227c8-148">Aggiungere un frammento</span><span class="sxs-lookup"><span data-stu-id="227c8-148">Add a fragment</span></span>

<span data-ttu-id="227c8-149">Per aggiungere un frammento a una pagina in Creazione di siti Web di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="227c8-149">To add a fragment to a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="227c8-150">Nel riquadro a sinistra o direttamente nel generatore di pagine visivo, selezionare un contenitore o uno slot a cui i moduli figlio possono essere aggiunti.</span><span class="sxs-lookup"><span data-stu-id="227c8-150">In the outline pane on the left or directly in visual page builder, select a container or slot to which child modules can be added.</span></span>
1. <span data-ttu-id="227c8-151">Selezionare i puntini di sospensione (**...**) accanto al nome del contenitore o dello slot.</span><span class="sxs-lookup"><span data-stu-id="227c8-151">Select the ellipsis (**...**) next to the name of the container or slot.</span></span>  <span data-ttu-id="227c8-152">In alternativa, se si utilizza il generatore di pagine visivo, selezionare il simbolo più (**+**).</span><span class="sxs-lookup"><span data-stu-id="227c8-152">Alternately, if using visual page builder, select the plus symbol (**+**).</span></span>  
1. <span data-ttu-id="227c8-153">Selezionare **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="227c8-153">Select **Add fragment**.</span></span>
    <!-- ![A screen capture of how to add an existing fragment to a slot or container](./media/add-fragment.png)-->
 
    > [!NOTE]
    > <span data-ttu-id="227c8-154">Se il contenitore o lo slot non supporta nuovi moduli figlio, l'opzione **Aggiungi frammento** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="227c8-154">If the container or slot doesn't support new child modules, the **Add fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="227c8-155">Nella finestra di dialogo **Seleziona frammento**, cercare e selezionare un frammento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="227c8-155">In the **Select fragment** dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="227c8-156">Se non sono elencati frammenti disponibili, è necessario dapprima creare un frammento da un tipo di modulo che lo slot o il contenitore supporta.</span><span class="sxs-lookup"><span data-stu-id="227c8-156">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="227c8-157">Selezionare il frammento desiderato per aggiungerlo al contenitore o allo slot nella pagina.</span><span class="sxs-lookup"><span data-stu-id="227c8-157">Select your desired fragment to add it to the container or slot on your page.</span></span>
<!--    ![A screen capture of the fragment picker modal window](./media/fragment-picker.png)-->

> [!NOTE]
> <span data-ttu-id="227c8-158">I moduli consentiti in un contenitore o in uno slot sono definiti in base al modello della pagina o alle definizioni dei moduli.</span><span class="sxs-lookup"><span data-stu-id="227c8-158">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="227c8-159">Rimuovere un frammento</span><span class="sxs-lookup"><span data-stu-id="227c8-159">Remove a fragment</span></span>

<span data-ttu-id="227c8-160">Per rimuovere un frammento da uno slot o un contenitore in una pagina di Creazione di siti Web di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="227c8-160">To remove a fragment from a slot or container on a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="227c8-161">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al nome del frammento da rimuovere e quindi selezionare il simbolo del cestino.</span><span class="sxs-lookup"><span data-stu-id="227c8-161">In the outline pane on the left, select the ellipsis (**...**) next to the name of the fragment to be removed, and then select the trash can symbol.</span></span>  <span data-ttu-id="227c8-162">In alternativa, è possibile selezionare il frammento nel generatore di pagine visivo e selezionare il simbolo del cestino nella barra degli strumenti del frammento.</span><span class="sxs-lookup"><span data-stu-id="227c8-162">Alternately, you can select the fragment in visual page builder and select the trash can symbol in the fragment's toolbar.</span></span>
1. <span data-ttu-id="227c8-163">Quando viene richiesto di confermare la rimozione del frammento, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="227c8-163">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="227c8-164">Quando si rimuove un frammento da una pagina, si rimuove solo il riferimento allo stesso da quella pagina.</span><span class="sxs-lookup"><span data-stu-id="227c8-164">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="227c8-165">**Non** si elimina il frammento dal sito.</span><span class="sxs-lookup"><span data-stu-id="227c8-165">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="227c8-166">Per eliminare frammenti dal sito, è necessario utilizzare l'interfaccia utente del controllo frammenti.</span><span class="sxs-lookup"><span data-stu-id="227c8-166">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="227c8-167">È possibile eliminare frammenti da un sito solo se si fa riferimento agli stessi con un qualsiasi modello, pagina o altro frammento.</span><span class="sxs-lookup"><span data-stu-id="227c8-167">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="227c8-168">Modificare un frammento</span><span class="sxs-lookup"><span data-stu-id="227c8-168">Edit a fragment</span></span>

<span data-ttu-id="227c8-169">Per modificare i frammenti, è necessario utilizzare l'interfaccia utente dell'editor di frammenti.</span><span class="sxs-lookup"><span data-stu-id="227c8-169">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="227c8-170">Questa restrizione è dovuta alla struttura.</span><span class="sxs-lookup"><span data-stu-id="227c8-170">This restriction is by design.</span></span> <span data-ttu-id="227c8-171">Impedisce agli autori di confondere il processo di modifica dei moduli per una pagina specifica con il processo di modifica di frammenti che potrebbero essere condivisi da più pagine.</span><span class="sxs-lookup"><span data-stu-id="227c8-171">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="227c8-172">Per modificare un frammento in Creazione di siti Web di Commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="227c8-172">To edit a fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="227c8-173">Selezionare **Frammenti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="227c8-173">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="227c8-174">In **Frammenti**, selezionare il frammento da modificare.</span><span class="sxs-lookup"><span data-stu-id="227c8-174">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="227c8-175">Modificare le proprietà del modulo del frammento e la struttura come necessario.</span><span class="sxs-lookup"><span data-stu-id="227c8-175">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="227c8-176">Il processo è analogo a quello per modificare i moduli nella visualizzazione dell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="227c8-176">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="227c8-177">È anche possibile modificare un frammento selezionandolo in una pagina, in un modello o in un frammento padre e quindi selezionando **Modifica frammento** nel riquadro delle proprietà a destra.</span><span class="sxs-lookup"><span data-stu-id="227c8-177">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="227c8-178">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="227c8-178">Additional resources</span></span>

[<span data-ttu-id="227c8-179">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="227c8-179">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="227c8-180">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="227c8-180">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="227c8-181">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="227c8-181">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="227c8-182">Utilizzare i gruppi di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="227c8-182">Work with publish groups</span></span>](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]