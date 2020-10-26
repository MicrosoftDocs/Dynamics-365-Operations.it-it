---
title: Modificare una pagina di sito esistente
description: In questo argomento viene descritto come modificare una pagina di sito esistente in Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8ca23dcf568cb0df6934f0d6201e4aafba5f9ba1
ms.sourcegitcommit: f16db76c1c235dfa445b50614bcee9219782d6dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "3961636"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="9d046-103">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="9d046-103">Modify an existing site page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9d046-104">In questo argomento viene descritto come modificare una pagina di sito esistente in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d046-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9d046-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9d046-105">Overview</span></span>

<span data-ttu-id="9d046-106">Quando si deve modificare una pagina, è necessario innanzi tutto aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="9d046-106">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="9d046-107">Accedere al sito che contiene la pagina, quindi nell'elenco delle pagine, trovare la pagina desiderata.</span><span class="sxs-lookup"><span data-stu-id="9d046-107">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="9d046-108">Se non è possibile trovare la pagina, utilizzare la funzionalità di ricerca avanzata dello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="9d046-108">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="9d046-109">Digitare il nome esatto della pagina oppure le prime lettere dello stesso e quindi un asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="9d046-109">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="9d046-110">Viene visualizzato un elenco filtrato delle pagine.</span><span class="sxs-lookup"><span data-stu-id="9d046-110">A filtered list of pages appears.</span></span> <span data-ttu-id="9d046-111">È possibile utilizzare questo elenco per trovare la pagina desiderata.</span><span class="sxs-lookup"><span data-stu-id="9d046-111">You can use this list to find the page that you want.</span></span> <span data-ttu-id="9d046-112">Una volta trovata la pagina corretta, selezionare il nome della pagina per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="9d046-112">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="9d046-113">Se la pagina è visibile nel controllo pagina, è possibile selezionare **Modifica** e controllare la pagina prima di aprirla nell'editor delle pagine.</span><span class="sxs-lookup"><span data-stu-id="9d046-113">If your page is visible in the page inspector, you can select **Edit** and check the page out before you open it in the page editor.</span></span> <span data-ttu-id="9d046-114">In questo modo, è possibile estrarre più pagine contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9d046-114">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="9d046-115">Dopo l'apertura della pagina nell'editor di pagine, è necessario verificare che sia stata estratta.</span><span class="sxs-lookup"><span data-stu-id="9d046-115">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="9d046-116">La barra dei comandi nello strumento di creazione è dinamica, sensibile al contesto e allo stato.</span><span class="sxs-lookup"><span data-stu-id="9d046-116">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="9d046-117">Di conseguenza, mostra solo le azioni che è possibile eseguire attualmente nella pagina.</span><span class="sxs-lookup"><span data-stu-id="9d046-117">Therefore, it shows only the actions that you can currently perform on the page.</span></span> <span data-ttu-id="9d046-118">Ad esempio, se la pagina non è stata estratta da te, i pulsanti **Salvare** e **Fine modifica** non verranno visualizzati nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9d046-118">For example, if the page isn't checked out to you, the **Save** and **Finish editing** buttons don't appear on the command bar.</span></span> <span data-ttu-id="9d046-119">Lo stato della pagina è inoltre visualizzato sul lato destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="9d046-119">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="9d046-120">Se la pagina non è ancora stata estratta, selezionare **Modificare** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9d046-120">If the page isn't already checked out to you, select **Edit** on the command bar.</span></span> <span data-ttu-id="9d046-121">La barra dei comandi cambia per riflettere il nuovo stato della pagina.</span><span class="sxs-lookup"><span data-stu-id="9d046-121">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="9d046-122">Viene inoltre visualizzata una notifica indicante che la pagina è stata estratta.</span><span class="sxs-lookup"><span data-stu-id="9d046-122">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="9d046-123">L'operazione successiva consiste nell'apportare le modifiche effettive.</span><span class="sxs-lookup"><span data-stu-id="9d046-123">The next step is to make your actual changes.</span></span> <span data-ttu-id="9d046-124">In genere, si utilizza l'albero delle pagine a sinistra per trovare e selezionare il modulo che si desidera modificare e quindi si apportano le modifiche nel riquadro delle proprietà a destra.</span><span class="sxs-lookup"><span data-stu-id="9d046-124">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="9d046-125">Tuttavia, la modifica può talvolta comportare l'aggiunta o la rimozione di modelli o frammenti.</span><span class="sxs-lookup"><span data-stu-id="9d046-125">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="9d046-126">Per aggiungere un frammento o un modulo, trovare lo slot a cui si desidera aggiungere il modulo o il frammento utilizzando l'albero delle pagine, quindi selezionare il pulsante con i puntini di sospensione (**...**) per quello slot.</span><span class="sxs-lookup"><span data-stu-id="9d046-126">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="9d046-127">Viene visualizzato un menu che include i comandi per aggiungere un modulo o un frammento.</span><span class="sxs-lookup"><span data-stu-id="9d046-127">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="9d046-128">Per rimuovere un modulo o un frammento, trovarlo e selezionarlo nell'albero delle pagine, selezionare il pulsante con i puntini di sospensione e quindi selezionare il comando per eseguire la rimozione.</span><span class="sxs-lookup"><span data-stu-id="9d046-128">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="9d046-129">È anche possibile visualizzare e modificare le proprietà di qualsiasi modulo visibile nell'anteprima del generatore di pagine visivo selezionando il modulo direttamente.</span><span class="sxs-lookup"><span data-stu-id="9d046-129">You can also view and edit the properties for any module that is visible in the visual page builder preview by selecting it directly.</span></span>

<span data-ttu-id="9d046-130">Dopo aver finito di apportare le modifiche e visualizzare in anteprima il loro effetto, è consigliabile archiviare la pagina selezionando **Fine modifica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9d046-130">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Finish editing** on the command bar.</span></span> 

<span data-ttu-id="9d046-131">Per pubblicare immediatamente le modifiche, selezionare **Pubblica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9d046-131">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="9d046-132">L'ultima versione archiviata della pagina modificata viene pubblicata e diventa disponibile per gli utenti esterni che visualizzano il sito.</span><span class="sxs-lookup"><span data-stu-id="9d046-132">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="9d046-133">Esempio: modificare il video nella home page</span><span class="sxs-lookup"><span data-stu-id="9d046-133">Example: Change the video on the home page</span></span>

<span data-ttu-id="9d046-134">Nell'esempio seguente viene descritto come modificare la home page cambiando il video nel modulo Lettore video.</span><span class="sxs-lookup"><span data-stu-id="9d046-134">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="9d046-135">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="9d046-135">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="9d046-136">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="9d046-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="9d046-137">Trovare e selezionare la home page per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="9d046-137">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="9d046-138">Nella barra dei comandi, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="9d046-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="9d046-139">Nella struttura delle pagine, selezionare lo slot **Principale**.</span><span class="sxs-lookup"><span data-stu-id="9d046-139">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="9d046-140">Sotto lo slot **Principale**, espandere tutti i moduli contenitore fluidi.</span><span class="sxs-lookup"><span data-stu-id="9d046-140">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="9d046-141">Trovare e selezionare il modulo Lettore video.</span><span class="sxs-lookup"><span data-stu-id="9d046-141">Find and select the video player module.</span></span>
1. <span data-ttu-id="9d046-142">Nel riquadro delle proprietà a destra, selezionare la proprietà **Video**.</span><span class="sxs-lookup"><span data-stu-id="9d046-142">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="9d046-143">Viene visualizzato lo strumento di selezione di asset.</span><span class="sxs-lookup"><span data-stu-id="9d046-143">The asset picker appears.</span></span>
1. <span data-ttu-id="9d046-144">Nello strumento, selezionare un asset video disponibile oppure selezionare **Carica nuovo asset** per caricare un nuovo asset video.</span><span class="sxs-lookup"><span data-stu-id="9d046-144">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="9d046-145">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d046-145">Select **OK**.</span></span>
1. <span data-ttu-id="9d046-146">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="9d046-146">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="9d046-147">Nel campo **Commenti**, immettere **Modificato il video** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d046-147">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="9d046-148">Selezionare **Anteprima** per visualizzare l'anteprima della pagina caricata.</span><span class="sxs-lookup"><span data-stu-id="9d046-148">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="9d046-149">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="9d046-149">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="9d046-150">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="9d046-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d046-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9d046-151">Additional resources</span></span>

[<span data-ttu-id="9d046-152">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="9d046-152">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="9d046-153">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="9d046-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="9d046-154">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="9d046-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="9d046-155">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="9d046-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="9d046-156">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="9d046-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="9d046-157">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="9d046-157">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="9d046-158">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="9d046-158">Verify page content accessibility</span></span>](verify-accessibility.md)
