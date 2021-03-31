---
title: Utilizzare i moduli
description: In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: eddee09fa81c18bc464b7768921981e6b5159a3e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210901"
---
# <a name="work-with-modules"></a><span data-ttu-id="fe697-103">Utilizzare i moduli</span><span class="sxs-lookup"><span data-stu-id="fe697-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe697-104">In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe697-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fe697-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="fe697-105">Overview</span></span>

<span data-ttu-id="fe697-106">I moduli sono blocchi predefiniti logici che costituiscono la struttura della pagina e hanno scopi e finalità.</span><span class="sxs-lookup"><span data-stu-id="fe697-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="fe697-107">Alcuni moduli sono contenitori di alto livello e il loro solo scopo è di contenere e organizzare altri moduli (moduli figlio).</span><span class="sxs-lookup"><span data-stu-id="fe697-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="fe697-108">Altri moduli, ad esempio un modulo Posizionamento immagine semplice, hanno uno scopo molto specifico.</span><span class="sxs-lookup"><span data-stu-id="fe697-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="fe697-109">Altri moduli, come il modulo Sequenza, non rientrano in nessuna di queste due categorie.</span><span class="sxs-lookup"><span data-stu-id="fe697-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="fe697-110">Per impostazione predefinita, il sito di Dynamics 365 Commerce include una libreria di moduli che consente di ottenere la maggior parte degli scenari di e-Commere di base.</span><span class="sxs-lookup"><span data-stu-id="fe697-110">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="fe697-111">Dovrebbe essere possibile poter creare un sito di e-Commerce end-to-end utilizzando questi moduli.</span><span class="sxs-lookup"><span data-stu-id="fe697-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="fe697-112">Tuttavia, è anche possibile che si intenda personalizzare tali moduli o creare nuovi moduli personalizzati per specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="fe697-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="fe697-113">Se si desidera creare moduli personalizzati, un kit SDK di progettazione di moduli è disponibile per creare una libreria di moduli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fe697-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="fe697-114">Moduli contenitore e slot</span><span class="sxs-lookup"><span data-stu-id="fe697-114">Container modules and slots</span></span>

<span data-ttu-id="fe697-115">Come indicato in precedenza, alcuni moduli sono progettati per contenere moduli figlio.</span><span class="sxs-lookup"><span data-stu-id="fe697-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="fe697-116">Questi moduli sono noti come *contenitori* e consentono l'utilizzo di gerarchie di moduli nidificati.</span><span class="sxs-lookup"><span data-stu-id="fe697-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="fe697-117">I moduli contenitore includono *slot*.</span><span class="sxs-lookup"><span data-stu-id="fe697-117">Container modules include *slots*.</span></span> <span data-ttu-id="fe697-118">Gli slot sono utilizzati per gestire il layout e lo scopo dei moduli figlio nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="fe697-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="fe697-119">Un esempio è un modulo contenitore pagina di base (un modulo di livello superiore per qualsiasi pagina) che definisce vari slot importanti:</span><span class="sxs-lookup"><span data-stu-id="fe697-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="fe697-120">Uno slot di intestazione</span><span class="sxs-lookup"><span data-stu-id="fe697-120">A header slot</span></span>
- <span data-ttu-id="fe697-121">Uno slot di intestazione secondaria</span><span class="sxs-lookup"><span data-stu-id="fe697-121">A sub-header slot</span></span>
- <span data-ttu-id="fe697-122">Uno slot principale</span><span class="sxs-lookup"><span data-stu-id="fe697-122">A main slot</span></span>
- <span data-ttu-id="fe697-123">Uno slot piè di pagina</span><span class="sxs-lookup"><span data-stu-id="fe697-123">A footer slot</span></span>
- <span data-ttu-id="fe697-124">Uno slot di piè di pagina secondario</span><span class="sxs-lookup"><span data-stu-id="fe697-124">A sub-footer slot</span></span>

<span data-ttu-id="fe697-125">Lo sviluppatore del modulo definisce tali slot e determina quali e quanti moduli figlio possono essere inseriti direttamente all'interno di tale modulo.</span><span class="sxs-lookup"><span data-stu-id="fe697-125">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="fe697-126">Ad esempio, lo slot intestazione potrebbe supportare solo un modulo di tipo **modulo Intestazione**, mentre lo slot corpo potrebbe supportare un numero illimitato di moduli di qualsiasi tipo (tranne altri moduli contenitore pagina).</span><span class="sxs-lookup"><span data-stu-id="fe697-126">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="fe697-127">Negli strumenti di creazione, gli autori di pagine non devono sapere in anticipo quali moduli possono e non possono essere inseriti in ogni slot.</span><span class="sxs-lookup"><span data-stu-id="fe697-127">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="fe697-128">Quando gli autori di pagine selezionano uno slot e quindi tentano di selezionare un modulo da aggiungere allo slot, vedono una visualizzazione filtrata dei tipi di modulo supportati per quello slot.</span><span class="sxs-lookup"><span data-stu-id="fe697-128">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="fe697-129">Moduli contenuto</span><span class="sxs-lookup"><span data-stu-id="fe697-129">Content modules</span></span>

<span data-ttu-id="fe697-130">I moduli contenuto contengono contenuto ed elementi multimediali, come testo (ad esempio, titoli, paragrafi e collegamenti) o riferimenti ad asset (ad esempio, immagini, video e PDF).</span><span class="sxs-lookup"><span data-stu-id="fe697-130">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="fe697-131">Tipici tipi di moduli di contenuto includono blocchi di contenuto, blocchi di testo e moduli banner promozionali.</span><span class="sxs-lookup"><span data-stu-id="fe697-131">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="fe697-132">I moduli di questi tre tipi possono contenere testo o elementi multimediali e non richiedono moduli figlio per rendere qualcosa visibile in una pagina.</span><span class="sxs-lookup"><span data-stu-id="fe697-132">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="fe697-133">La maggior parte delle attività di creazione di pagine e contenuto quotidiane tipiche comporta moduli contenuto, in particolare perché questi moduli definiscono il contenuto effettivo di cui viene eseguito il rendering nei moduli contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="fe697-133">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="fe697-134">Molti moduli contenuto sono disponibili e questi moduli sono in genere gli ultimi pezzi che saranno aggiunti alla gerarchia di moduli nidificati di una pagina.</span><span class="sxs-lookup"><span data-stu-id="fe697-134">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="fe697-135">Nella figura seguente viene illustrato come i moduli sono nidificati negli slot di moduli contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="fe697-135">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Moduli nidificati](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="fe697-137">Aggiungere o rimuovere moduli</span><span class="sxs-lookup"><span data-stu-id="fe697-137">Add or remove modules</span></span>

<span data-ttu-id="fe697-138">Nelle procedure riportate di seguito viene descritto come aggiungere e rimuovere moduli.</span><span class="sxs-lookup"><span data-stu-id="fe697-138">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="fe697-139">Aggiungere un modulo</span><span class="sxs-lookup"><span data-stu-id="fe697-139">Add a module</span></span>

<span data-ttu-id="fe697-140">Per aggiungere un modulo a uno slot o contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe697-140">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="fe697-141">Nel riquadro a sinistra o direttamente nel canvas principale, selezionare un contenitore o uno slot a cui un modulo figlio può essere aggiunto.</span><span class="sxs-lookup"><span data-stu-id="fe697-141">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe697-142">Lo strumento di progettazione di moduli definisce l'elenco dei tipi di modulo che possono essere aggiunti a uno slot di modulo specifico.</span><span class="sxs-lookup"><span data-stu-id="fe697-142">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="fe697-143">Gli autori di modelli possono quindi affinare le opzioni per moduli consentite per garantire un'ottimizzazione del motore di ricerca coerente e l'efficacia di creazione per tutte le pagine generate da un modello specifico.</span><span class="sxs-lookup"><span data-stu-id="fe697-143">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="fe697-144">Durante l'aggiunta di un modulo a uno slot, la finestra di dialogo **Aggiungi modulo** viene automaticamente filtrata in modo da visualizzare solo i moduli che sono supportati nel contenitore o nello slot selezionato.</span><span class="sxs-lookup"><span data-stu-id="fe697-144">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="fe697-145">L'elenco di moduli consentiti viene determinato dal modello della pagina o dalla definizione del modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="fe697-145">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="fe697-146">Se si utilizza il riquadro di contorno, selezionare i puntini di sospensione (**...**) accanto al nome del modulo, quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="fe697-146">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="fe697-147">Se si utilizzano i controlli direttamente nel canvas, selezionare il simbolo più (**+**) in uno slot vuoto o adiacente al modulo attualmente selezionato, quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="fe697-147">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fe697-148">Se un contenitore o uno slot non supporta nuovi moduli figlio, l'opzione **Aggiungi modulo** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="fe697-148">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="fe697-149">Nella finestra di dialogo **Aggiungi modulo**, selezionare un modulo da aggiungere alla pagina.</span><span class="sxs-lookup"><span data-stu-id="fe697-149">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="fe697-150">**Blocco di contenuto** è un buon tipo di modulo con cui i principianti possono lavorare.</span><span class="sxs-lookup"><span data-stu-id="fe697-150">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="fe697-151">Selezionare **OK** per aggiungere il modulo selezionato al contenitore o allo slot selezionato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="fe697-151">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="fe697-152">Rimuovere un modulo</span><span class="sxs-lookup"><span data-stu-id="fe697-152">Remove a module</span></span>

<span data-ttu-id="fe697-153">Per rimuovere un modulo da uno slot o un contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe697-153">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="fe697-154">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al nome del modulo da rimuovere e quindi selezionare il simbolo del cestino.</span><span class="sxs-lookup"><span data-stu-id="fe697-154">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="fe697-155">In alternativa, nel canvas principale è possibile selezionare il simbolo del cestino sulla barra degli strumenti di un modulo selezionato.</span><span class="sxs-lookup"><span data-stu-id="fe697-155">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="fe697-156">Quando viene richiesto di confermare la rimozione del modulo, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe697-156">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="fe697-157">Spostare un modulo in una una posizione</span><span class="sxs-lookup"><span data-stu-id="fe697-157">Move a module to a new position</span></span>

<span data-ttu-id="fe697-158">Per spostare un modulo in una nuova posizione all'interno della pagina, utilizzare uno dei seguenti metodi.</span><span class="sxs-lookup"><span data-stu-id="fe697-158">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="fe697-159">Spostare un modulo utilizzando il riquadro struttura</span><span class="sxs-lookup"><span data-stu-id="fe697-159">Move a module using the outline pane</span></span>

<span data-ttu-id="fe697-160">Per spostare un modulo utilizzando il riquadro struttura, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="fe697-160">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="fe697-161">Selezionare e tenere premuto il modulo che si desidera spostare nel riquadro struttura, quindi trascinare il modulo in una nuova posizione nella struttura.</span><span class="sxs-lookup"><span data-stu-id="fe697-161">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="fe697-162">La linea blu nel contorno e nel canvas indica dove è possibile posizionare il modulo.</span><span class="sxs-lookup"><span data-stu-id="fe697-162">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="fe697-163">Rilasciare il modulo per inserirlo nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="fe697-163">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="fe697-164">Spostare un modulo direttamente nel canvas</span><span class="sxs-lookup"><span data-stu-id="fe697-164">Move a module directly within the canvas</span></span>

<span data-ttu-id="fe697-165">Per spostare un modulo direttamente nel canvas, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="fe697-165">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="fe697-166">Selezionare il modulo che si desidera spostare nel canvas.</span><span class="sxs-lookup"><span data-stu-id="fe697-166">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="fe697-167">Selezionare un simbolo di freccia rivolta verso l'alto o verso il basso nella barra degli strumenti del modulo, quindi trascinare la freccia in una nuova posizione sulla pagina.</span><span class="sxs-lookup"><span data-stu-id="fe697-167">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="fe697-168">La linea blu nel contorno e nel canvas indica dove è possibile posizionare il modulo.</span><span class="sxs-lookup"><span data-stu-id="fe697-168">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="fe697-169">Se un modulo non può essere spostato verso l'alto o verso il basso, quel simbolo di freccia verrà disattivato.</span><span class="sxs-lookup"><span data-stu-id="fe697-169">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="fe697-170">Rilasciare il modulo per inserirlo nella nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="fe697-170">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="fe697-171">Spostare un modulo utilizzando il menu dei puntini di sospensione</span><span class="sxs-lookup"><span data-stu-id="fe697-171">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="fe697-172">Per spostare un modulo utilizzando il menu dei puntini di sospensione, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="fe697-172">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="fe697-173">Selezionare un modulo nella struttura o nel canvas.</span><span class="sxs-lookup"><span data-stu-id="fe697-173">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="fe697-174">Selezionare i puntini di sospensione (**...**) accanto al nome del modulo nel riquadro struttura o nella barra degli strumenti del modulo nel canvas.</span><span class="sxs-lookup"><span data-stu-id="fe697-174">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="fe697-175">Se il modulo può essere spostato verso l'alto o verso il basso all'interno del contenitore o dello slot, verranno visualizzate le opzioni per **Sposta su** o **Sposta giù**.</span><span class="sxs-lookup"><span data-stu-id="fe697-175">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="fe697-176">Selezionare l'opzione di spostamento desiderata per spostare il modulo verso l'alto o verso il basso rispetto ai suoi elementi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="fe697-176">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="fe697-177">Configurare moduli</span><span class="sxs-lookup"><span data-stu-id="fe697-177">Configure modules</span></span>

<span data-ttu-id="fe697-178">Nelle procedure riportate di seguito viene descritto come configurare moduli contenuto e contenitore.</span><span class="sxs-lookup"><span data-stu-id="fe697-178">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="fe697-179">Configurare un modulo contenuto</span><span class="sxs-lookup"><span data-stu-id="fe697-179">Configure a content module</span></span>

<span data-ttu-id="fe697-180">Per configurare un modulo contenuto in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe697-180">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="fe697-181">Nella riquadro a sinistra, espandere la struttura e selezionare qualsiasi modulo contenuto (ad esempio **Blocco di contenuto**).</span><span class="sxs-lookup"><span data-stu-id="fe697-181">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="fe697-182">In alternativa, è possibile selezionare il modulo nel canvas principale.</span><span class="sxs-lookup"><span data-stu-id="fe697-182">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="fe697-183">Nel riquadro delle proprietà del modulo sulla destra, immettere le proprietà per tutti i controlli del modulo desiderati.</span><span class="sxs-lookup"><span data-stu-id="fe697-183">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="fe697-184">Selezionare **Salva** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="fe697-184">On the command bar, select **Save**.</span></span> <span data-ttu-id="fe697-185">Ciò aggiornerà anche la canvas di anteprima.</span><span class="sxs-lookup"><span data-stu-id="fe697-185">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="fe697-186">Modificare le proprietà del testo del modulo</span><span class="sxs-lookup"><span data-stu-id="fe697-186">Edit module text properties</span></span>

<span data-ttu-id="fe697-187">Le proprietà del testo del modulo che non sono di sola lettura possono essere modificate direttamente nel canvas.</span><span class="sxs-lookup"><span data-stu-id="fe697-187">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="fe697-188">Per modificare le proprietà del testo del modulo, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="fe697-188">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="fe697-189">Selezionare il controllo del testo nel canvas, quindi posizionare il cursore nel punto in cui desideri modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="fe697-189">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="fe697-190">Immettere il contenuto del testo.</span><span class="sxs-lookup"><span data-stu-id="fe697-190">Enter your text content.</span></span>
1. <span data-ttu-id="fe697-191">Selezionare un punto qualsiasi al di fuori del contenuto del testo per continuare a modificare altro contenuto.</span><span class="sxs-lookup"><span data-stu-id="fe697-191">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="fe697-192">Selezione immagine in linea</span><span class="sxs-lookup"><span data-stu-id="fe697-192">Inline image selection</span></span>

<span data-ttu-id="fe697-193">Le immagini del modulo che non sono di sola lettura possono essere modificate direttamente dal canvas.</span><span class="sxs-lookup"><span data-stu-id="fe697-193">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="fe697-194">Per scegliere una nuova immagine per un modulo di contenuto, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe697-194">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="fe697-195">Nel canvas, fare doppio clic sull'immagine.</span><span class="sxs-lookup"><span data-stu-id="fe697-195">In the canvas, double-click the image.</span></span> <span data-ttu-id="fe697-196">Questo farà apparire la finestra di selezione dei file multimediali.</span><span class="sxs-lookup"><span data-stu-id="fe697-196">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="fe697-197">Trovare e selezionare una nuova immagine da utilizzare, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe697-197">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="fe697-198">Il rendering della nuova immagine viene ora effettuato nel canvas.</span><span class="sxs-lookup"><span data-stu-id="fe697-198">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="fe697-199">Configurare un modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="fe697-199">Configure a container module</span></span>

<span data-ttu-id="fe697-200">Per configurare un modulo contenitore in una pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe697-200">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="fe697-201">Selezionare un modulo contenitore nella pagina (ad esempio un modulo contenitore fluido o Sequenza).</span><span class="sxs-lookup"><span data-stu-id="fe697-201">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="fe697-202">Nel riquadro delle proprietà a destra, espandere i controlli nidificati selezionando le intestazioni e impostare tutti i valori di controllo necessari.</span><span class="sxs-lookup"><span data-stu-id="fe697-202">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="fe697-203">Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del contenitore o di qualsiasi slot nel contenitore e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="fe697-203">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="fe697-204">Aggiungere quindi i moduli figlio al contenitore selezionato.</span><span class="sxs-lookup"><span data-stu-id="fe697-204">Then, add child modules to the selected container.</span></span> <span data-ttu-id="fe697-205">Per ulteriori informazioni, vedere la sezione [Utilizzare i moduli](#add-a-module) descritta precedentemente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fe697-205">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="fe697-206">Se molteplici moduli figlio esistono come elementi di pari livello in un contenitore padre, è possibile modificarne l'ordine di visualizzazione nel contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="fe697-206">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="fe697-207">Selezionare il pulsante con i puntini di sospensione per un modulo e quindi utilizzare i tasti freccia GIÙ o SU.</span><span class="sxs-lookup"><span data-stu-id="fe697-207">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe697-208">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fe697-208">Additional resources</span></span>

[<span data-ttu-id="fe697-209">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="fe697-209">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="fe697-210">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="fe697-210">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="fe697-211">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="fe697-211">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="fe697-212">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="fe697-212">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="fe697-213">Aggiungere un modulo contenitore a una pagina</span><span class="sxs-lookup"><span data-stu-id="fe697-213">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="fe697-214">Utilizzare i gruppi di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="fe697-214">Work with publish groups</span></span>](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]