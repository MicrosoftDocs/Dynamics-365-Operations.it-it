---
title: Utilizzare i layout preimpostati
description: In questo argomento viene descritto come utilizzare i layout preimpostati in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a2539880e76ffb1861e0d18227a935a2ef35c120
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210877"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="7042e-103">Utilizzare i layout preimpostati</span><span class="sxs-lookup"><span data-stu-id="7042e-103">Work with preset layouts</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7042e-104">In questo argomento viene descritto come utilizzare i layout preimpostati in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7042e-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7042e-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="7042e-105">Overview</span></span>

<span data-ttu-id="7042e-106">Prima di completare le procedure in questo argomento, assicurarsi di leggere [Layout personalizzati e preimpostati](templates-layouts-overview.md#preset-and-custom-layouts).</span><span class="sxs-lookup"><span data-stu-id="7042e-106">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="7042e-107">Per una panoramica generale, vedere [Panoramica modelli e layout](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7042e-107">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="7042e-108">Creare un nuovo layout preimpostato</span><span class="sxs-lookup"><span data-stu-id="7042e-108">Create a new preset layout</span></span>

<span data-ttu-id="7042e-109">Un layout preimpostato può essere creato in due modi.</span><span class="sxs-lookup"><span data-stu-id="7042e-109">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="7042e-110">È possibile salvare un layout personalizzato esistente come nuovo layout preimpostato oppure creare un layout preimpostato da zero.</span><span class="sxs-lookup"><span data-stu-id="7042e-110">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="7042e-111">Creare un layout preimpostato da un layout personalizzato esistente</span><span class="sxs-lookup"><span data-stu-id="7042e-111">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="7042e-112">Per creare un layout preimpostato da un layout personalizzato esistente, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="7042e-112">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="7042e-113">Aprire una pagina esistente che attualmente non utilizza un layout preimpostato e che ha una struttura di modulo che si intende riutilizzare per altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="7042e-113">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="7042e-114">Selezionare **Modifica** per estrarre la pagina.</span><span class="sxs-lookup"><span data-stu-id="7042e-114">Select **Edit** to check out the page.</span></span>
1. <span data-ttu-id="7042e-115">Selezionare **Salva come nuovo layout**.</span><span class="sxs-lookup"><span data-stu-id="7042e-115">Select **Save as new layout**.</span></span> <span data-ttu-id="7042e-116">Viene visualizzata la finestra di dialogo **Salva come nuovo layout** .</span><span class="sxs-lookup"><span data-stu-id="7042e-116">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="7042e-117">Immettere un nome e una descrizione per il layout preimpostato.</span><span class="sxs-lookup"><span data-stu-id="7042e-117">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="7042e-118">I valori immessi sono visibili ad altri autori quando questi creano nuove pagine a partire dal layout o passano a tale layout.</span><span class="sxs-lookup"><span data-stu-id="7042e-118">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="7042e-119">Di conseguenza, immettere valori che saranno utili ad altri autori di pagine.</span><span class="sxs-lookup"><span data-stu-id="7042e-119">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="7042e-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7042e-120">Select **OK**.</span></span>

<span data-ttu-id="7042e-121">Il layout preimpostato sarà ora disponibile quando si creano nuove pagine o si seleziona un layout diverso per una pagina nella stessa gerarchia di modelli.</span><span class="sxs-lookup"><span data-stu-id="7042e-121">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="7042e-122">Per determinare rapidamente se una pagina specifica è attualmente associata a un layout preimpostato, selezionare la pagina nella visualizzazione con l'elenco di pagine ed esaminare i metadati del layout nel riquadro delle proprietà a destra.</span><span class="sxs-lookup"><span data-stu-id="7042e-122">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="7042e-123">Creare un nuovo layout preimpostato</span><span class="sxs-lookup"><span data-stu-id="7042e-123">Create a new preset layout</span></span>

<span data-ttu-id="7042e-124">Per creare un layout preimpostato da zero, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="7042e-124">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="7042e-125">Nel pannello di navigazione a sinistra, selezionare **Layout**.</span><span class="sxs-lookup"><span data-stu-id="7042e-125">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="7042e-126">Selezionare **Nuovo layout**.</span><span class="sxs-lookup"><span data-stu-id="7042e-126">Select **New Layout**.</span></span> <span data-ttu-id="7042e-127">Viene visualizzata la finestra di dialogo **Nuovo layout**.</span><span class="sxs-lookup"><span data-stu-id="7042e-127">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="7042e-128">Selezionare il modello da utilizzare per il layout preimpostato.</span><span class="sxs-lookup"><span data-stu-id="7042e-128">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="7042e-129">Immettere un nome e una descrizione per il layout preimpostato.</span><span class="sxs-lookup"><span data-stu-id="7042e-129">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="7042e-130">I valori immessi sono visibili ad altri autori quando questi creano nuove pagine a partire dal layout o passano a tale layout.</span><span class="sxs-lookup"><span data-stu-id="7042e-130">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="7042e-131">Di conseguenza, immettere valori che saranno utili ad altri autori di pagine.</span><span class="sxs-lookup"><span data-stu-id="7042e-131">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="7042e-132">Selezionare **OK** per creare il nuovo layout preimpostato e aprire l'editor di layout.</span><span class="sxs-lookup"><span data-stu-id="7042e-132">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="7042e-133">Nell'editor di layout, aggiungere e configurare moduli utilizzando l'albero a sinistra e il riquadro delle proprietà a destra.</span><span class="sxs-lookup"><span data-stu-id="7042e-133">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="7042e-134">(il processo è analogo a quello per l'aggiunta e la configurazione di moduli per un modello nell'editor di modelli). La disposizione dei moduli e le impostazioni predefinite bloccate diventano la configurazione di moduli centralizzata di qualsiasi pagina che utilizza questo layout preimpostato.</span><span class="sxs-lookup"><span data-stu-id="7042e-134">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="7042e-135">Modificare un layout preimpostato</span><span class="sxs-lookup"><span data-stu-id="7042e-135">Modify a preset layout</span></span>

<span data-ttu-id="7042e-136">Per modificare un layout preimpostato, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="7042e-136">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="7042e-137">Nel pannello di navigazione a sinistra, selezionare **Layout**.</span><span class="sxs-lookup"><span data-stu-id="7042e-137">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="7042e-138">Nell'editor di layout, nell'albero a sinistra, selezionare il modulo da modificare.</span><span class="sxs-lookup"><span data-stu-id="7042e-138">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="7042e-139">Quindi eseguire uno qualsiasi delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7042e-139">Then follow any of these steps:</span></span>

    - <span data-ttu-id="7042e-140">Per spostare un modulo verso l'alto o verso il basso nel relativo modulo padre, selezionare il pulsante con i puntini di sospensione (**...**) per il modulo, quindi selezionare **Sposta su** o **Sposta giù**.</span><span class="sxs-lookup"><span data-stu-id="7042e-140">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="7042e-141">Per modificare le impostazioni predefinite di un modulo, utilizzare il riquadro delle proprietà per immettere valori predefiniti ed eventualmente bloccarli per tutte le pagine downstream.</span><span class="sxs-lookup"><span data-stu-id="7042e-141">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="7042e-142">Per aggiungere nuovi moduli o frammenti a moduli contenitore, selezionare il pulsante con i puntini di sospensione e quindi **Aggiungi modulo** o **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="7042e-142">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="7042e-143">Per rimuovere un modulo dal layout, selezionare il pulsante con i puntini di sospensione e quindi **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="7042e-143">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="7042e-144">Modificare il tema di un layout preimpostato</span><span class="sxs-lookup"><span data-stu-id="7042e-144">Change a preset layout theme</span></span>

<span data-ttu-id="7042e-145">Una procedura tipica consiste nell'impostare un tema predefinito per tutte le pagine che utilizzano un layout preimpostato.</span><span class="sxs-lookup"><span data-stu-id="7042e-145">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="7042e-146">Per impostare o modificare il tema di tutte le pagine figlio che utilizzano il layout preimpostato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="7042e-146">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="7042e-147">Nell'editor di layout, nell'albero a sinistra, selezionare il modulo contenitore pagina</span><span class="sxs-lookup"><span data-stu-id="7042e-147">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="7042e-148">(in genere, questo modulo è il secondo nodo ed è denominato **Pagina predefinita**).</span><span class="sxs-lookup"><span data-stu-id="7042e-148">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="7042e-149">Nel riquadro delle proprietà a destra, nel campo **Tema**, selezionare un tema.</span><span class="sxs-lookup"><span data-stu-id="7042e-149">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="7042e-150">Salva, archiviare, visualizzare in anteprima e pubblicare un layout preimpostato</span><span class="sxs-lookup"><span data-stu-id="7042e-150">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="7042e-151">Per salvare e archiviare il layout preimpostato, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="7042e-151">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="7042e-152">Selezionare **Salva** nella parte superiore dell'editor di layout.</span><span class="sxs-lookup"><span data-stu-id="7042e-152">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="7042e-153">Le modifiche salvate non influiscono sulle pagine downstream fino a che non vengono archiviate.</span><span class="sxs-lookup"><span data-stu-id="7042e-153">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="7042e-154">Selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="7042e-154">Select **Finish editing**.</span></span> <span data-ttu-id="7042e-155">Le modifiche sono ora individuabili per i flussi di lavoro downstream.</span><span class="sxs-lookup"><span data-stu-id="7042e-155">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="7042e-156">Per visualizzare l'anteprima delle modifiche, aprire una pagina esistente che utilizza il layout preimpostato o creare una nuova pagina a partire dal layout.</span><span class="sxs-lookup"><span data-stu-id="7042e-156">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="7042e-157">Dopo avere visualizzato un'anteprima delle modifiche al layout preimpostato, eseguire una di queste operazioni per pubblicare il layout sul sito live:</span><span class="sxs-lookup"><span data-stu-id="7042e-157">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="7042e-158">Andare a **Layout**, selezionare il layout e quindi **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="7042e-158">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="7042e-159">Selezionare il nome del layout per aprire l'editor del layout, quindi selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="7042e-159">Select the layout name to open the layout editor, and then select **Publish**.</span></span>
* <span data-ttu-id="7042e-160">Pubblicare una pagina che fa riferimento al layout non pubblicato.</span><span class="sxs-lookup"><span data-stu-id="7042e-160">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="7042e-161">Il layout viene pubblicato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7042e-161">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="7042e-162">Molteplici pagine possono fare riferimento ai layout preimpostati.</span><span class="sxs-lookup"><span data-stu-id="7042e-162">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="7042e-163">Quando si pubblica un layout preimpostato, tenere presente che è possibile alterare il layout di molteplici pagine.</span><span class="sxs-lookup"><span data-stu-id="7042e-163">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7042e-164">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7042e-164">Additional resources</span></span>

[<span data-ttu-id="7042e-165">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="7042e-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="7042e-166">Utilizzare i modelli</span><span class="sxs-lookup"><span data-stu-id="7042e-166">Work with templates</span></span>](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]