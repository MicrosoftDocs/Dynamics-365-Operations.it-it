---
title: Salvare, visualizzare in anteprima e pubblicare una pagina
description: In questo argomento viene descritto come salvare, visualizzare in anteprima e pubblicare una pagina in Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 04200264fabca265484b5e66426810efe8028a50
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002817"
---
# <a name="save-preview-and-publish-a-page"></a><span data-ttu-id="a77c1-103">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="a77c1-103">Save, preview, and publish a page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a77c1-104">In questo argomento viene descritto come salvare, visualizzare in anteprima e pubblicare una pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a77c1-104">This topic describes how to save, preview, and publish a page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="save-a-page"></a><span data-ttu-id="a77c1-105">Salvare una pagina</span><span class="sxs-lookup"><span data-stu-id="a77c1-105">Save a page</span></span>

<span data-ttu-id="a77c1-106">Per salvare una pagina, è necessario che questa sia estratta e aperta nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="a77c1-106">To save a page, you must have it checked out to yourself and open in the page editor.</span></span> <span data-ttu-id="a77c1-107">Una pagina deve essere salvata subito dopo averla modificata, per garantire l'archiviazione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="a77c1-107">You should save a page immediately after you modify it, to help guarantee that your changes are stored.</span></span>

<span data-ttu-id="a77c1-108">Quando si salva una pagina, le modifiche sono visibili solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="a77c1-108">When you save a page, the changes are visible only to you.</span></span> <span data-ttu-id="a77c1-109">Lo scopo principale dell'operazione di salvataggio è l'archiviazione delle modifiche quando la pagina non è ancora pronta per essere archiviata.</span><span class="sxs-lookup"><span data-stu-id="a77c1-109">The save operation is intended primarily to store changes while the page isn't yet ready to be checked in.</span></span> <span data-ttu-id="a77c1-110">Al termine della modifica della pagina, si consiglia di archiviarla, di modo che le modifiche siano visibili anche agli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="a77c1-110">When you've finished modifying the page, we recommend that you check it in, so that the changes become visible to others.</span></span> <span data-ttu-id="a77c1-111">La pagina può quindi essere estratta anche da altri utenti che devono modificarla.</span><span class="sxs-lookup"><span data-stu-id="a77c1-111">At that point, the page can also be checked out by other users who must modify it.</span></span>

## <a name="preview-a-page"></a><span data-ttu-id="a77c1-112">Visualizzare l'anteprima di una pagina</span><span class="sxs-lookup"><span data-stu-id="a77c1-112">Preview a page</span></span>

<span data-ttu-id="a77c1-113">Lo strumento di creazione offre due tipi di funzionalità di anteprima: un riquadro di anteprima WYSIWYG nell'editor di pagine e una finestra di anteprima distinta.</span><span class="sxs-lookup"><span data-stu-id="a77c1-113">The authoring tool offers two kinds of preview features: a "what you see is what you get" (WYSIWYG) preview pane in the page editor and a separate preview window.</span></span>

<span data-ttu-id="a77c1-114">Quando si utilizza l'editor di pagine, un'anteprima WYSIWYG viene visualizzata nel riquadro centrale.</span><span class="sxs-lookup"><span data-stu-id="a77c1-114">While you're using the page editor, a "what you see is what you get" (WYSIWYG) preview appears in the center pane.</span></span> <span data-ttu-id="a77c1-115">Questa anteprima viene automaticamente aggiornata ogni volta che si salva la pagina.</span><span class="sxs-lookup"><span data-stu-id="a77c1-115">This preview is automatically updated whenever you save the page.</span></span> <span data-ttu-id="a77c1-116">È anche possibile aggiornarla manualmente selezionando **Aggiorna** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a77c1-116">You can also manually update it by selecting **Refresh** on the command bar.</span></span> <span data-ttu-id="a77c1-117">L'anteprima WYSIWYG visualizza la pagina esattamente come sarà visibile agli utenti del sito, ma con gli helper di creazione nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="a77c1-117">The WYSIWYG preview renders the page just as the site's users will see it, but authoring helpers are rendered on top of it.</span></span>

<span data-ttu-id="a77c1-118">Al termine della modifica della pagina, è possibile visualizzarne l'anteprima per stabilire quali clienti la vedranno.</span><span class="sxs-lookup"><span data-stu-id="a77c1-118">When you've finished modifying the page, you might want to preview it to see what customers will see.</span></span> <span data-ttu-id="a77c1-119">Per visualizzare l'anteprima di una pagina, selezionare **Anteprima** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a77c1-119">To preview a page, select **Preview** on the command bar.</span></span> <span data-ttu-id="a77c1-120">L'anteprima sarà visualizzata in una finestra del browser distinta.</span><span class="sxs-lookup"><span data-stu-id="a77c1-120">The preview will appear in a separate browser window.</span></span> <span data-ttu-id="a77c1-121">La pagina nella finestra di anteprima appare esattamente come risulterà visibile agli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="a77c1-121">The page in the preview window is rendered just as the site's user will see it.</span></span> <span data-ttu-id="a77c1-122">È possibile ridimensionare la finestra per assicurare il corretto rendering di moduli reattivi in tutte le porte di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="a77c1-122">You can resize the window to make sure that responsive modules are correctly rendered in all view ports.</span></span>

> [!NOTE]
> <span data-ttu-id="a77c1-123">Per visualizzare l'anteprima di contenuto non pubblicato, è necessario disporre di autorizzazioni di autenticazione appropriate.</span><span class="sxs-lookup"><span data-stu-id="a77c1-123">Authentication and correct permissions are required to preview unpublished content.</span></span> <span data-ttu-id="a77c1-124">Di conseguenza, se si condivide l'URL dell'anteprima con qualcuno, quella persona deve disporre delle autorizzazioni appropriate per accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="a77c1-124">Therefore, if you share the URL of the preview with someone, that person must have the correct permissions to access the content.</span></span>

## <a name="publish-a-page"></a><span data-ttu-id="a77c1-125">Pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="a77c1-125">Publish a page</span></span>

<span data-ttu-id="a77c1-126">Una volta che la pagina è pronta, è necessario pubblicarla, di modo che gli utenti esterni possano visualizzare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="a77c1-126">When your page is ready, the next step is to publish it, so that external users can view the content.</span></span> <span data-ttu-id="a77c1-127">Prima di poter pubblicare una pagina, è necessario archiviarla.</span><span class="sxs-lookup"><span data-stu-id="a77c1-127">Before you can publish a page, you must check it in.</span></span>

<span data-ttu-id="a77c1-128">È possibile pubblicare le pagine e annullarne la pubblicazione mediante il controllo pagina o l'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="a77c1-128">You can publish and unpublish pages from either the page inspector or the page editor.</span></span> <span data-ttu-id="a77c1-129">Il controllo pagina visualizza un elenco di pagine e consente operazioni in blocco.</span><span class="sxs-lookup"><span data-stu-id="a77c1-129">The page inspector shows a list of pages and allows for bulk operations.</span></span> <span data-ttu-id="a77c1-130">L'editor di pagine può essere utilizzato per pubblicare o annullare la pubblicazione della pagina he visualizza.</span><span class="sxs-lookup"><span data-stu-id="a77c1-130">The page editor can be used to publish or unpublish only the single page that is open in it.</span></span>

<span data-ttu-id="a77c1-131">Per pubblicare una o più pagine mediante il controllo pagina, selezionare le pagine, assicurarsi che siano state archiviate e quindi selezionare **Pubblica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a77c1-131">To publish one or more pages from the page inspector, select the pages, make sure that they are checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="a77c1-132">Le pagine vengono pubblicate e si riceve una notifica sull'operazione nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="a77c1-132">The pages are published, and you receive a notification about the operation in the authoring tool.</span></span>

<span data-ttu-id="a77c1-133">Per pubblicare una singola pagina mediante l'editor di pagine, la procedura è analoga.</span><span class="sxs-lookup"><span data-stu-id="a77c1-133">To publish a single page from the page editor, the procedure is similar.</span></span> <span data-ttu-id="a77c1-134">Quando la pagina è aperta nell'editor di pagine, assicurarsi che sia stata archiviata e quindi selezionare **Pubblica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a77c1-134">While the page is open in the page editor, make sure that it has been checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="a77c1-135">La pagina viene pubblicata e si riceve una notifica sull'operazione.</span><span class="sxs-lookup"><span data-stu-id="a77c1-135">The page is published, and you receive a notification about the operation.</span></span>

<span data-ttu-id="a77c1-136">Quando si pubblica una pagina, viene pubblicato solo il contenuto della stessa.</span><span class="sxs-lookup"><span data-stu-id="a77c1-136">When you publish a page, just the page content is published.</span></span> <span data-ttu-id="a77c1-137">Gli utenti possono accedere alla pagina e visualizzarla solo quando si ha un URL ad esso associato.</span><span class="sxs-lookup"><span data-stu-id="a77c1-137">You and other users can go to the page and view it only after a URL is associated with it.</span></span> <span data-ttu-id="a77c1-138">L'URL deve essere pubblicato separatamente.</span><span class="sxs-lookup"><span data-stu-id="a77c1-138">The URL must be published separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a77c1-139">Prima di pubblicare una pagina, tutte le immagini o i frammenti a cui la pagina fa riferimento devono già essere pubblicati.</span><span class="sxs-lookup"><span data-stu-id="a77c1-139">Before you can publish a page, any images or fragments that the page references must already be published.</span></span>

## <a name="save-preview-and-publish-a-home-page"></a><span data-ttu-id="a77c1-140">Salvare, visualizzare in anteprima e pubblicare una home page</span><span class="sxs-lookup"><span data-stu-id="a77c1-140">Save, preview, and publish a home page</span></span>

<span data-ttu-id="a77c1-141">Per salvare, visualizzare in anteprima e pubblicare una home page, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="a77c1-141">To save, preview, and publish a home page, follow these steps.</span></span>

1. <span data-ttu-id="a77c1-142">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="a77c1-142">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="a77c1-143">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="a77c1-143">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="a77c1-144">Trovare e selezionare la home page per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="a77c1-144">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="a77c1-145">Selezionare **Estrai**.</span><span class="sxs-lookup"><span data-stu-id="a77c1-145">Select **Check Out**.</span></span>
1. <span data-ttu-id="a77c1-146">Modificare la pagina come necessario.</span><span class="sxs-lookup"><span data-stu-id="a77c1-146">Modify the page as you require.</span></span>
1. <span data-ttu-id="a77c1-147">Selezionare **Salva** e quindi selezionare **Archivia**.</span><span class="sxs-lookup"><span data-stu-id="a77c1-147">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="a77c1-148">Nel campo **Commenti**, immettere una nota sulle modifiche apportate e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a77c1-148">In the **Comments** field, enter a note about the changes that you made, and then select **OK**.</span></span>
1. <span data-ttu-id="a77c1-149">Selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="a77c1-149">Select **Preview** to preview your page.</span></span> <span data-ttu-id="a77c1-150">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="a77c1-150">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="a77c1-151">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="a77c1-151">Select **Publish**.</span></span>

## <a name="publish-a-url"></a><span data-ttu-id="a77c1-152">Pubblicare un URL</span><span class="sxs-lookup"><span data-stu-id="a77c1-152">Publish a URL</span></span>

<span data-ttu-id="a77c1-153">Per pubblicare un URL, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="a77c1-153">To publish a URL, follow these steps.</span></span>

1. <span data-ttu-id="a77c1-154">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="a77c1-154">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="a77c1-155">Nel pannello di navigazione a sinistra, selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="a77c1-155">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="a77c1-156">Trovare e selezionare l'URL da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="a77c1-156">Find and select the URL to publish.</span></span>
1. <span data-ttu-id="a77c1-157">Nella barra dei comandi, selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="a77c1-157">On the command bar, select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a77c1-158">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a77c1-158">Additional resources</span></span>

[<span data-ttu-id="a77c1-159">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="a77c1-159">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="a77c1-160">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="a77c1-160">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="a77c1-161">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="a77c1-161">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="a77c1-162">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="a77c1-162">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="a77c1-163">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="a77c1-163">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="a77c1-164">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="a77c1-164">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="a77c1-165">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="a77c1-165">Verify page content accessibility</span></span>](verify-accessibility.md)
