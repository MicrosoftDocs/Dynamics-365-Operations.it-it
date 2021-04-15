---
title: Aggiungere una nuova pagina del sito
description: In questo argomento viene descritto come aggiungere una nuova pagina di sito in Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4a2ecc3ef3ff3f708cec50e42777b50ec4576e25
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797553"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="8d6c1-103">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="8d6c1-103">Add a new site page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8d6c1-104">In questo argomento viene descritto come aggiungere una nuova pagina di sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8d6c1-105">Dopo aver creato modelli e frammenti per il sito, è necessario iniziare a creare le pagine che li utilizzano.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-105">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="8d6c1-106">Per iniziare, selezionare un modello o un layout, un nome di pagina e un URL di pagina.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-106">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="8d6c1-107">Modello o layout</span><span class="sxs-lookup"><span data-stu-id="8d6c1-107">Template or layout</span></span>

<span data-ttu-id="8d6c1-108">È possibile utilizzare un modello o un layout per la nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-108">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="8d6c1-109">Per ulteriori informazioni, vedere [Panoramica modelli e layout](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8d6c1-109">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="8d6c1-110">Nome pagina</span><span class="sxs-lookup"><span data-stu-id="8d6c1-110">Page name</span></span>

<span data-ttu-id="8d6c1-111">Scegliere un nome di pagina univoco.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-111">The page name must be unique to your page.</span></span> <span data-ttu-id="8d6c1-112">Deve inoltre essere descrittivo, di modo che sia facile trovare la pagina e identificarne lo scopo.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-112">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="8d6c1-113">Scegliere il nome di pagina attentamente, in quanto non può essere modificato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-113">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="8d6c1-114">URL pagina</span><span class="sxs-lookup"><span data-stu-id="8d6c1-114">Page URL</span></span>

<span data-ttu-id="8d6c1-115">È possibile immettere un URL per la nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-115">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="8d6c1-116">Quando si crea una pagina, è possibile immettere una stringa che sarà utilizzata per formare un URL completo.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-116">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="8d6c1-117">Tale stringa è nota come URL relativo o slug URL.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-117">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="8d6c1-118">Un URL completo viene quindi generato in base allo slug URL e la nuova pagina viene assegnata a tale URL.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-118">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="8d6c1-119">Lo slug URL può essere modificato in seguito, dopo la pubblicazione della pagina.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-119">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="8d6c1-120">Per ulteriori informazioni, vedere [Creare un URL di pagina](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="8d6c1-120">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8d6c1-121">Dynamics 365 Commerce scollega gli URL e il contenuto.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-121">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="8d6c1-122">Ovvero, è possibile creare una pagina che non è associata a un URL e un URL che non è associato a una pagina.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-122">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="8d6c1-123">Di conseguenza, è possibile eseguire lo swapping di contenuto per un URL senza periodo di inattività e gli reindirizzamenti sono più facili da gestire.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-123">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="8d6c1-124">Aggiungere una nuova pagina</span><span class="sxs-lookup"><span data-stu-id="8d6c1-124">Add a new page</span></span>

<span data-ttu-id="8d6c1-125">Per aggiungere un nuova pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-125">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="8d6c1-126">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="8d6c1-126">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="8d6c1-127">Selezionare **Nuova pagina**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-127">Select **New Page**.</span></span>
1. <span data-ttu-id="8d6c1-128">Nella finestra di dialogo **Nuova pagina** selezionare un modello e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-128">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="8d6c1-129">Nel campo **Nome pagina**, immettere un nome di pagina, ad esempio **Nuova pagina**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-129">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="8d6c1-130">Nel campo **URL**, immettere una stringa (slug URL) per completare l'URL (ad esempio **nuovapagina**).</span><span class="sxs-lookup"><span data-stu-id="8d6c1-130">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="8d6c1-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-131">Select **OK**.</span></span> <span data-ttu-id="8d6c1-132">Viene visualizzato l'editor delle pagine.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-132">The page editor appears.</span></span> <span data-ttu-id="8d6c1-133">Si noti che un'intestazione e un piè di pagina vengono automaticamente aggiunti alla pagina, in base al modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-133">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="8d6c1-134">Nella struttura delle pagine, selezionare lo slot **Principale**, il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-134">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8d6c1-135">Selezionare **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-135">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="8d6c1-136">Selezionare **Contenitore fluido**, il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-136">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="8d6c1-137">Selezionare **Blocco ricco di contenuti** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-137">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="8d6c1-138">Selezionare **Blocco ricco di contenuti**, il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-138">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="8d6c1-139">Selezionare **Elemento blocco ricco di contenuti** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-139">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="8d6c1-140">Nel riquadro delle proprietà a destra, selezionare **Paragrafo**, quindi nel campo immettere **Testo di prova**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-140">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="8d6c1-141">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-141">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8d6c1-142">Nel campo **Commenti**, immettere **Aggiunta nuova pagina** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-142">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="8d6c1-143">Selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-143">Select **Preview** to preview your page.</span></span> <span data-ttu-id="8d6c1-144">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-144">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="8d6c1-145">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="8d6c1-145">Select **Publish**.</span></span>
1. <span data-ttu-id="8d6c1-146">Nel percorso di navigazione (barra di navigazione), selezionare **Fabrikam** (o il nome del sito).</span><span class="sxs-lookup"><span data-stu-id="8d6c1-146">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="8d6c1-147">Nel pannello di navigazione a sinistra, selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-147">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="8d6c1-148">Trovare e selezionare l'URL (**nuovapagina**) nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8d6c1-148">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="8d6c1-149">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="8d6c1-149">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8d6c1-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8d6c1-150">Additional resources</span></span>

[<span data-ttu-id="8d6c1-151">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="8d6c1-151">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="8d6c1-152">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="8d6c1-152">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="8d6c1-153">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="8d6c1-153">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="8d6c1-154">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="8d6c1-154">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="8d6c1-155">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="8d6c1-155">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="8d6c1-156">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="8d6c1-156">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="8d6c1-157">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="8d6c1-157">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="8d6c1-158">Creare pagine di e-commerce dinamiche in base ai parametri URL</span><span class="sxs-lookup"><span data-stu-id="8d6c1-158">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
