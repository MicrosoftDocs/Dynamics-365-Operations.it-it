---
title: Salvare, visualizzare in anteprima e pubblicare una pagina
description: In questo argomento viene descritto come salvare, visualizzare in anteprima e pubblicare una pagina in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: db4866b22060b764fdde3e4a44e99e969133c0a0
ms.sourcegitcommit: f16db76c1c235dfa445b50614bcee9219782d6dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "3961612"
---
# <a name="save-preview-and-publish-a-page"></a><span data-ttu-id="9f81a-103">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="9f81a-103">Save, preview, and publish a page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9f81a-104">In questo argomento viene descritto come salvare, visualizzare in anteprima e pubblicare una pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9f81a-104">This topic describes how to save, preview, and publish a page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="save-a-page"></a><span data-ttu-id="9f81a-105">Salvare una pagina</span><span class="sxs-lookup"><span data-stu-id="9f81a-105">Save a page</span></span>

<span data-ttu-id="9f81a-106">Per salvare una pagina, è necessario che questa sia estratta e aperta nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="9f81a-106">To save a page, you must have it checked out to yourself and open in the page editor.</span></span> <span data-ttu-id="9f81a-107">Per estrarre una pagina, selezionare **Modifica** sulla barra comandi.</span><span class="sxs-lookup"><span data-stu-id="9f81a-107">To check out a page, select **Edit** on the command bar.</span></span> <span data-ttu-id="9f81a-108">Dopo aver terminato la modifica di una pagina, è necessario salvarla immediatamente per assicurarsi che le modifiche siano memorizzate.</span><span class="sxs-lookup"><span data-stu-id="9f81a-108">After you've finished editing a page, you should immediately save it to ensure that your changes are stored.</span></span>

<span data-ttu-id="9f81a-109">Quando si salva una pagina, le modifiche sono visibili solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="9f81a-109">When you save a page, the changes are visible only to you.</span></span> <span data-ttu-id="9f81a-110">Lo scopo principale dell'operazione di salvataggio è l'archiviazione delle modifiche quando la pagina non è ancora pronta per essere archiviata.</span><span class="sxs-lookup"><span data-stu-id="9f81a-110">The save operation is intended primarily to store changes while the page isn't yet ready to be checked in.</span></span> <span data-ttu-id="9f81a-111">Al termine della modifica della pagina, si consiglia di archiviarla, di modo che le modifiche siano visibili anche agli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="9f81a-111">When you've finished modifying the page, we recommend that you check it in, so that the changes become visible to others.</span></span> <span data-ttu-id="9f81a-112">La pagina può quindi essere estratta anche da altri utenti che devono modificarla.</span><span class="sxs-lookup"><span data-stu-id="9f81a-112">At that point, the page can also be checked out by other users who must modify it.</span></span>

## <a name="preview-a-page"></a><span data-ttu-id="9f81a-113">Visualizzare l'anteprima di una pagina</span><span class="sxs-lookup"><span data-stu-id="9f81a-113">Preview a page</span></span>

<span data-ttu-id="9f81a-114">Lo strumento di creazione offre due tipi di funzionalità di anteprima: il generatore di pagine visivo, che è un riquadro di anteprima WYSIWYG nell'editor di pagine, e una finestra di anteprima distinta.</span><span class="sxs-lookup"><span data-stu-id="9f81a-114">The authoring tool offers two kinds of preview features: visual page builder, which is a "what you see is what you get" (WYSIWYG) preview pane in the page editor, and a separate preview window.</span></span>

<span data-ttu-id="9f81a-115">Quando si utilizza l'editor di pagine, un'anteprima WYSIWYG viene visualizzata nel riquadro centrale.</span><span class="sxs-lookup"><span data-stu-id="9f81a-115">While you're using the page editor, a "what you see is what you get" (WYSIWYG) preview appears in the center pane.</span></span> <span data-ttu-id="9f81a-116">Questa anteprima viene automaticamente aggiornata ogni volta che si salva la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f81a-116">This preview is automatically updated whenever you save the page.</span></span> <span data-ttu-id="9f81a-117">È anche possibile aggiornarla manualmente selezionando **Aggiorna** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9f81a-117">You can also manually update it by selecting **Refresh** on the command bar.</span></span> <span data-ttu-id="9f81a-118">L'anteprima visualizza la pagina esattamente come sarà visibile agli utenti del sito, ma con gli helper di creazione nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="9f81a-118">The preview renders the page just as the site's users will see it, but authoring helpers are rendered on top of it.</span></span>

<span data-ttu-id="9f81a-119">Al termine della modifica della pagina, è possibile visualizzarne l'anteprima per stabilire quali clienti la vedranno.</span><span class="sxs-lookup"><span data-stu-id="9f81a-119">When you've finished modifying the page, you might want to preview it to see what customers will see.</span></span> <span data-ttu-id="9f81a-120">Per visualizzare l'anteprima di una pagina, selezionare **Anteprima** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9f81a-120">To preview a page, select **Preview** on the command bar.</span></span> <span data-ttu-id="9f81a-121">L'anteprima sarà visualizzata in una finestra del browser distinta.</span><span class="sxs-lookup"><span data-stu-id="9f81a-121">The preview will appear in a separate browser window.</span></span> <span data-ttu-id="9f81a-122">La pagina nella finestra di anteprima appare esattamente come risulterà visibile agli utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="9f81a-122">The page in the preview window is rendered just as the site's user will see it.</span></span> <span data-ttu-id="9f81a-123">È possibile ridimensionare la finestra per assicurare il corretto rendering di moduli reattivi in tutte le porte di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f81a-123">You can resize the window to make sure that responsive modules are correctly rendered in all view ports.</span></span>

> [!NOTE]
> <span data-ttu-id="9f81a-124">Per visualizzare l'anteprima di contenuto non pubblicato, è necessario disporre di autorizzazioni di autenticazione appropriate.</span><span class="sxs-lookup"><span data-stu-id="9f81a-124">Authentication and correct permissions are required to preview unpublished content.</span></span> <span data-ttu-id="9f81a-125">Di conseguenza, se si condivide l'URL dell'anteprima con qualcuno, quella persona deve disporre delle autorizzazioni appropriate per accedere al contenuto.</span><span class="sxs-lookup"><span data-stu-id="9f81a-125">Therefore, if you share the URL of the preview with someone, that person must have the correct permissions to access the content.</span></span>

## <a name="publish-a-page"></a><span data-ttu-id="9f81a-126">Pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="9f81a-126">Publish a page</span></span>

<span data-ttu-id="9f81a-127">Una volta che la pagina è pronta, è necessario pubblicarla, di modo che gli utenti esterni possano visualizzare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="9f81a-127">When your page is ready, the next step is to publish it, so that external users can view the content.</span></span> <span data-ttu-id="9f81a-128">Prima di poter pubblicare una pagina, è necessario archiviarla selezionando **Fine modifica** sulla barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9f81a-128">Before you can publish a page, you must check it in by selecting **Finish editing** on the command bar.</span></span>

<span data-ttu-id="9f81a-129">È possibile pubblicare le pagine e annullarne la pubblicazione mediante il controllo pagina o l'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="9f81a-129">You can publish and unpublish pages from either the page inspector or the page editor.</span></span> <span data-ttu-id="9f81a-130">Il controllo pagina visualizza un elenco di pagine e consente operazioni in blocco.</span><span class="sxs-lookup"><span data-stu-id="9f81a-130">The page inspector shows a list of pages and allows for bulk operations.</span></span> <span data-ttu-id="9f81a-131">L'editor di pagine può essere utilizzato per pubblicare o annullare la pubblicazione della pagina he visualizza.</span><span class="sxs-lookup"><span data-stu-id="9f81a-131">The page editor can be used to publish or unpublish only the single page that is open in it.</span></span>

<span data-ttu-id="9f81a-132">Per pubblicare una o più pagine mediante il controllo pagina, selezionare le pagine, assicurarsi che siano state archiviate e quindi selezionare **Pubblica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9f81a-132">To publish one or more pages from the page inspector, select the pages, make sure that they are checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="9f81a-133">Le pagine vengono pubblicate e si riceve una notifica sull'operazione nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="9f81a-133">The pages are published, and you receive a notification about the operation in the authoring tool.</span></span>

<span data-ttu-id="9f81a-134">Per pubblicare una singola pagina mediante l'editor di pagine, la procedura è analoga.</span><span class="sxs-lookup"><span data-stu-id="9f81a-134">To publish a single page from the page editor, the procedure is similar.</span></span> <span data-ttu-id="9f81a-135">Quando la pagina è aperta nell'editor di pagine, assicurarsi che sia stata archiviata e quindi selezionare **Pubblica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9f81a-135">While the page is open in the page editor, make sure that it has been checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="9f81a-136">La pagina viene pubblicata e si riceve una notifica sull'operazione.</span><span class="sxs-lookup"><span data-stu-id="9f81a-136">The page is published, and you receive a notification about the operation.</span></span>

<span data-ttu-id="9f81a-137">Quando si pubblica una pagina, viene pubblicato solo il contenuto della stessa.</span><span class="sxs-lookup"><span data-stu-id="9f81a-137">When you publish a page, just the page content is published.</span></span> <span data-ttu-id="9f81a-138">Gli utenti possono accedere alla pagina e visualizzarla solo quando si ha un URL ad esso associato.</span><span class="sxs-lookup"><span data-stu-id="9f81a-138">You and other users can go to the page and view it only after a URL is associated with it.</span></span> <span data-ttu-id="9f81a-139">L'URL deve essere pubblicato separatamente.</span><span class="sxs-lookup"><span data-stu-id="9f81a-139">The URL must be published separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f81a-140">Prima di pubblicare una pagina, tutte le immagini o i frammenti a cui la pagina fa riferimento devono già essere pubblicati.</span><span class="sxs-lookup"><span data-stu-id="9f81a-140">Before you can publish a page, any images or fragments that the page references must already be published.</span></span>

## <a name="save-preview-and-publish-a-home-page"></a><span data-ttu-id="9f81a-141">Salvare, visualizzare in anteprima e pubblicare una home page</span><span class="sxs-lookup"><span data-stu-id="9f81a-141">Save, preview, and publish a home page</span></span>

<span data-ttu-id="9f81a-142">Per salvare, visualizzare in anteprima e pubblicare una home page, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="9f81a-142">To save, preview, and publish a home page, follow these steps.</span></span>

1. <span data-ttu-id="9f81a-143">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="9f81a-143">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="9f81a-144">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="9f81a-144">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="9f81a-145">Trovare e selezionare la home page per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="9f81a-145">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="9f81a-146">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="9f81a-146">Select **Edit**.</span></span>
1. <span data-ttu-id="9f81a-147">Modificare la pagina come necessario.</span><span class="sxs-lookup"><span data-stu-id="9f81a-147">Modify the page as you require.</span></span>
1. <span data-ttu-id="9f81a-148">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="9f81a-148">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="9f81a-149">Nel campo **Commenti**, immettere una nota sulle modifiche apportate e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f81a-149">In the **Comments** field, enter a note about the changes that you made, and then select **OK**.</span></span>
1. <span data-ttu-id="9f81a-150">Selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="9f81a-150">Select **Preview** to preview your page.</span></span> <span data-ttu-id="9f81a-151">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="9f81a-151">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="9f81a-152">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="9f81a-152">Select **Publish**.</span></span>

## <a name="publish-a-url"></a><span data-ttu-id="9f81a-153">Pubblicare un URL</span><span class="sxs-lookup"><span data-stu-id="9f81a-153">Publish a URL</span></span>

<span data-ttu-id="9f81a-154">Per pubblicare un URL, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="9f81a-154">To publish a URL, follow these steps.</span></span>

1. <span data-ttu-id="9f81a-155">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="9f81a-155">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="9f81a-156">Nel pannello di navigazione a sinistra, selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="9f81a-156">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="9f81a-157">Trovare e selezionare l'URL da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="9f81a-157">Find and select the URL to publish.</span></span>
1. <span data-ttu-id="9f81a-158">Nella barra dei comandi, selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="9f81a-158">On the command bar, select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f81a-159">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9f81a-159">Additional resources</span></span>

[<span data-ttu-id="9f81a-160">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="9f81a-160">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="9f81a-161">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="9f81a-161">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="9f81a-162">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="9f81a-162">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="9f81a-163">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="9f81a-163">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="9f81a-164">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="9f81a-164">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="9f81a-165">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="9f81a-165">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="9f81a-166">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="9f81a-166">Verify page content accessibility</span></span>](verify-accessibility.md)
