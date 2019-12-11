---
title: Utilizzare i moduli
description: In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.
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
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 06a26e5dfd35bf229e67ed27213210d0da726bdf
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698075"
---
# <a name="work-with-modules"></a><span data-ttu-id="45997-103">Utilizzare i moduli</span><span class="sxs-lookup"><span data-stu-id="45997-103">Work with modules</span></span>

<span data-ttu-id="45997-104">In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="45997-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="45997-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="45997-105">Overview</span></span>

<span data-ttu-id="45997-106">I moduli sono blocchi predefiniti logici che costituiscono la struttura della pagina e hanno scopi e finalità.</span><span class="sxs-lookup"><span data-stu-id="45997-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="45997-107">Alcuni moduli sono contenitori di alto livello e il loro solo scopo è di contenere e organizzare altri moduli (moduli figlio).</span><span class="sxs-lookup"><span data-stu-id="45997-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="45997-108">Altri moduli, ad esempio un modulo Posizionamento immagine semplice, hanno uno scopo molto specifico.</span><span class="sxs-lookup"><span data-stu-id="45997-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="45997-109">Altri moduli, come il modulo Sequenza, non rientrano in nessuna di queste due categorie.</span><span class="sxs-lookup"><span data-stu-id="45997-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="45997-110">Per impostazione predefinita, il sito di Dynamics 365 Commerce include una libreria di moduli dello starter kit che consente di ottenere la maggior parte degli scenari di e-Commere di base.</span><span class="sxs-lookup"><span data-stu-id="45997-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="45997-111">Dovrebbe essere possibile poter creare un sito di e-Commerce end-to-end utilizzando questi moduli.</span><span class="sxs-lookup"><span data-stu-id="45997-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="45997-112">Tuttavia, è anche possibile che si intenda personalizzare tali moduli o creare nuovi moduli personalizzati per specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="45997-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="45997-113">Se si desidera creare moduli personalizzati, un kit SDK di progettazione di moduli è disponibile per creare una libreria di moduli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="45997-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="45997-114">Moduli contenitore e slot</span><span class="sxs-lookup"><span data-stu-id="45997-114">Container modules and slots</span></span>

<span data-ttu-id="45997-115">Come indicato in precedenza, alcuni moduli sono progettati per contenere moduli figlio.</span><span class="sxs-lookup"><span data-stu-id="45997-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="45997-116">Questi moduli sono noti come *contenitori* e consentono l'utilizzo di gerarchie di moduli nidificati.</span><span class="sxs-lookup"><span data-stu-id="45997-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="45997-117">I moduli contenitore includono *slot*.</span><span class="sxs-lookup"><span data-stu-id="45997-117">Container modules include *slots*.</span></span> <span data-ttu-id="45997-118">Gli slot sono utilizzati per gestire il layout e lo scopo dei moduli figlio nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="45997-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="45997-119">Un esempio è un modulo contenitore pagina di base (un modulo di livello superiore per qualsiasi pagina) che definisce vari slot importanti:</span><span class="sxs-lookup"><span data-stu-id="45997-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="45997-120">Uno slot di intestazione</span><span class="sxs-lookup"><span data-stu-id="45997-120">A header slot</span></span>
- <span data-ttu-id="45997-121">Uno slot corpo</span><span class="sxs-lookup"><span data-stu-id="45997-121">A body slot</span></span>
- <span data-ttu-id="45997-122">Uno slot piè di pagina</span><span class="sxs-lookup"><span data-stu-id="45997-122">A footer slot</span></span>

<span data-ttu-id="45997-123">Lo sviluppatore del modulo definisce tali slot e determina quali e quanti moduli figlio possono essere inseriti direttamente all'interno di tale modulo.</span><span class="sxs-lookup"><span data-stu-id="45997-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="45997-124">Ad esempio, lo slot intestazione potrebbe supportare solo un modulo di tipo **modulo Intestazione**, mentre lo slot corpo potrebbe supportare un numero illimitato di moduli di qualsiasi tipo (tranne altri moduli contenitore pagina).</span><span class="sxs-lookup"><span data-stu-id="45997-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="45997-125">Negli strumenti di creazione, gli autori di pagine non devono sapere in anticipo quali moduli possono e non possono essere inseriti in ogni slot.</span><span class="sxs-lookup"><span data-stu-id="45997-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="45997-126">Quando gli autori di pagine selezionano uno slot e quindi tentano di selezionare un modulo da aggiungere allo slot, vedono una visualizzazione filtrata dei tipi di modulo supportati per quello slot.</span><span class="sxs-lookup"><span data-stu-id="45997-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="45997-127">Moduli contenuto</span><span class="sxs-lookup"><span data-stu-id="45997-127">Content modules</span></span>

<span data-ttu-id="45997-128">I moduli contenuto contengono contenuto ed elementi multimediali, come testo (ad esempio, titoli, paragrafi e collegamenti) o riferimenti ad asset (ad esempio, immagini, video e PDF).</span><span class="sxs-lookup"><span data-stu-id="45997-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="45997-129">Esempi di tipi di modulo contenuto tipici sono **Hero**, **Funzionalità** e **Banner**.</span><span class="sxs-lookup"><span data-stu-id="45997-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="45997-130">I moduli di questi tre tipi possono contenere testo o elementi multimediali e non richiedono moduli figlio per rendere qualcosa visibile in una pagina.</span><span class="sxs-lookup"><span data-stu-id="45997-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="45997-131">La maggior parte delle attività di creazione di pagine e contenuto quotidiane tipiche comporta moduli contenuto, in particolare perché questi moduli definiscono il contenuto effettivo di cui viene eseguito il rendering nei moduli contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="45997-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="45997-132">Molti moduli contenuto sono disponibili e questi moduli sono in genere gli ultimi pezzi che saranno aggiunti alla gerarchia di moduli nidificati di una pagina.</span><span class="sxs-lookup"><span data-stu-id="45997-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="45997-133">Nella figura seguente viene illustrato come i moduli sono nidificati negli slot di moduli contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="45997-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Moduli nidificati](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="45997-135">Aggiungere o rimuovere moduli</span><span class="sxs-lookup"><span data-stu-id="45997-135">Add or remove modules</span></span>

<span data-ttu-id="45997-136">Nelle procedure riportate di seguito viene descritto come aggiungere e rimuovere moduli.</span><span class="sxs-lookup"><span data-stu-id="45997-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="45997-137">Aggiungere un modulo</span><span class="sxs-lookup"><span data-stu-id="45997-137">Add a module</span></span>

<span data-ttu-id="45997-138">Per aggiungere un modulo a uno slot o contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="45997-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="45997-139">Nel riquadro a sinistra, selezionare un contenitore o uno slot a cui un modulo figlio può essere aggiunto.</span><span class="sxs-lookup"><span data-stu-id="45997-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45997-140">Lo strumento di progettazione di moduli definisce l'elenco dei tipi di modulo che possono essere aggiunti a uno slot di modulo specifico.</span><span class="sxs-lookup"><span data-stu-id="45997-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="45997-141">Gli autori di modelli possono quindi affinare le opzioni per moduli consentite per garantire un'ottimizzazione del motore di ricerca coerente e l'efficacia di creazione per tutte le pagine generate da un modello specifico.</span><span class="sxs-lookup"><span data-stu-id="45997-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="45997-142">Selezionare il pulsante con i puntini di sospensione (**...**) e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="45997-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="45997-143">Viene visualizzata la finestra di dialogo **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="45997-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="45997-144">Questa finestra di dialogo viene automaticamente filtrata in modo da visualizzare solo i moduli che sono supportati nel contenitore o nello slot selezionato.</span><span class="sxs-lookup"><span data-stu-id="45997-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="45997-145">L'elenco di moduli viene determinato dal modello della pagina o dalla definizione del modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="45997-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45997-146">Se un contenitore o uno slot non supporta nuovi moduli figlio, l'opzione **Aggiungi modulo** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="45997-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="45997-147">Nella finestra di dialogo, cercare e selezionare un modulo da aggiungere alla pagina.</span><span class="sxs-lookup"><span data-stu-id="45997-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="45997-148">**Funzionalità** e **Hero** sono tipi di modulo ottimi per gli utenti inesperti.</span><span class="sxs-lookup"><span data-stu-id="45997-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="45997-149">Selezionare **OK** per aggiungere il modulo selezionato al contenitore o allo slot selezionato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="45997-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="45997-150">Rimuovere un modulo</span><span class="sxs-lookup"><span data-stu-id="45997-150">Remove a module</span></span>

<span data-ttu-id="45997-151">Per rimuovere un modulo da uno slot o un contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="45997-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="45997-152">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del modulo da rimuovere e quindi selezionare il pulsante Cestino.</span><span class="sxs-lookup"><span data-stu-id="45997-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="45997-153">Quando viene richiesto di confermare la rimozione del modulo, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="45997-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="45997-154">Configurare moduli</span><span class="sxs-lookup"><span data-stu-id="45997-154">Configure modules</span></span>

<span data-ttu-id="45997-155">Nelle procedure riportate di seguito viene descritto come configurare moduli contenuto e contenitore.</span><span class="sxs-lookup"><span data-stu-id="45997-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="45997-156">Configurare un modulo contenuto</span><span class="sxs-lookup"><span data-stu-id="45997-156">Configure a content module</span></span>

<span data-ttu-id="45997-157">Per configurare un modulo contenuto in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="45997-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="45997-158">Nella riquadro a sinistra, selezionare un tipo di modulo contenuto (ad esempio **Funzionalità**, **Hero** o **Banner**).</span><span class="sxs-lookup"><span data-stu-id="45997-158">In the outline pane on the left, select a content module type (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="45997-159">Nel riquadro delle proprietà a destra, espandere i controlli nidificati selezionando le intestazioni e impostare tutti i valori di controllo necessari.</span><span class="sxs-lookup"><span data-stu-id="45997-159">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="45997-160">Se il riquadro delle proprietà include una sezione **Configurazione dati**, selezionarla per espanderla.</span><span class="sxs-lookup"><span data-stu-id="45997-160">If the properties pane has a **Data Configuration** section, select it to expand it.</span></span> <span data-ttu-id="45997-161">Altrimenti, andare al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="45997-161">Otherwise, go to step 5.</span></span>
1. <span data-ttu-id="45997-162">Se è presente un pulsante **Aggiungi origine dati**, selezionarlo e quindi selezionare gli elementi contenuto da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="45997-162">If there is a **Add Data Source** button, select it, and then select the content items to add.</span></span>
1. <span data-ttu-id="45997-163">Immettere le impostazioni per qualsiasi controllo di modulo necessario o desiderato.</span><span class="sxs-lookup"><span data-stu-id="45997-163">Enter settings for any required or desired module controls.</span></span>
1. <span data-ttu-id="45997-164">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="45997-164">Select **Save**.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="45997-165">Configurare un modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="45997-165">Configure a container module</span></span>

<span data-ttu-id="45997-166">Per configurare un modulo contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="45997-166">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="45997-167">Selezionare un modulo contenitore nella pagina (ad esempio un modulo contenitore fluido o Sequenza).</span><span class="sxs-lookup"><span data-stu-id="45997-167">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="45997-168">Nel riquadro delle proprietà a destra, espandere i controlli nidificati selezionando le intestazioni e impostare tutti i valori di controllo necessari.</span><span class="sxs-lookup"><span data-stu-id="45997-168">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="45997-169">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del contenitore o di qualsiasi slot nel contenitore e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="45997-169">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="45997-170">Aggiungere quindi i moduli figlio al contenitore selezionato.</span><span class="sxs-lookup"><span data-stu-id="45997-170">Then add child modules to the selected container.</span></span> <span data-ttu-id="45997-171">Per ulteriori informazioni, vedere la procedura [Aggiungere un modulo](#add-a-module) descritta precedentemente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="45997-171">For more information, see the [Add a module](#add-a-module) procedure earlier in this topic.</span></span>
1. <span data-ttu-id="45997-172">Se molteplici moduli figlio esistono come elementi di pari livello in un contenitore padre, è possibile modificarne l'ordine di visualizzazione nel contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="45997-172">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="45997-173">Selezionare il pulsante con i puntini di sospensione per un modulo e quindi utilizzare i tasti freccia GIÙ o SU.</span><span class="sxs-lookup"><span data-stu-id="45997-173">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45997-174">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="45997-174">Additional resources</span></span>

[<span data-ttu-id="45997-175">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="45997-175">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="45997-176">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="45997-176">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="45997-177">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="45997-177">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="45997-178">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="45997-178">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="45997-179">Aggiungere un modulo contenitore a una pagina</span><span class="sxs-lookup"><span data-stu-id="45997-179">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="45997-180">Aggiungere moduli Posizionamento contenuti a una pagina</span><span class="sxs-lookup"><span data-stu-id="45997-180">Add content placement modules to a page</span></span>](add-content-placement-modules.md)

