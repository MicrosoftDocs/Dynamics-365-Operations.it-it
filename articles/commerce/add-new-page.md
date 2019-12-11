---
title: Aggiungere una nuova pagina di sito
description: In questo argomento viene descritto come aggiungere una nuova pagina di sito in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: d5ab90343220e427a80cc4dde17c628ba64ac69e
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696740"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="4277d-103">Aggiungere una nuova pagina di sito</span><span class="sxs-lookup"><span data-stu-id="4277d-103">Add a new site page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4277d-104">In questo argomento viene descritto come aggiungere una nuova pagina di sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4277d-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4277d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="4277d-105">Overview</span></span>

<span data-ttu-id="4277d-106">Dopo aver creato modelli e frammenti per il sito, è necessario iniziare a creare le pagine che li utilizzano.</span><span class="sxs-lookup"><span data-stu-id="4277d-106">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="4277d-107">Per iniziare, selezionare un modello o un layout, un nome di pagina e un URL di pagina.</span><span class="sxs-lookup"><span data-stu-id="4277d-107">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="4277d-108">Modello o layout</span><span class="sxs-lookup"><span data-stu-id="4277d-108">Template or layout</span></span>

<span data-ttu-id="4277d-109">È possibile utilizzare un modello o un layout per la nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="4277d-109">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="4277d-110">Per ulteriori informazioni, vedere [Panoramica modelli e layout](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4277d-110">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="4277d-111">Nome pagina</span><span class="sxs-lookup"><span data-stu-id="4277d-111">Page name</span></span>

<span data-ttu-id="4277d-112">Scegliere un nome di pagina univoco.</span><span class="sxs-lookup"><span data-stu-id="4277d-112">The page name must be unique to your page.</span></span> <span data-ttu-id="4277d-113">Deve inoltre essere descrittivo, di modo che sia facile trovare la pagina e identificarne lo scopo.</span><span class="sxs-lookup"><span data-stu-id="4277d-113">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="4277d-114">Scegliere il nome di pagina attentamente, in quanto non può essere modificato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="4277d-114">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="4277d-115">URL pagina</span><span class="sxs-lookup"><span data-stu-id="4277d-115">Page URL</span></span>

<span data-ttu-id="4277d-116">È possibile immettere un URL per la nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="4277d-116">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="4277d-117">Quando si crea una pagina, è possibile immettere una stringa che sarà utilizzata per formare un URL completo.</span><span class="sxs-lookup"><span data-stu-id="4277d-117">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="4277d-118">Tale stringa è nota come URL relativo o slug URL.</span><span class="sxs-lookup"><span data-stu-id="4277d-118">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="4277d-119">Un URL completo viene quindi generato in base allo slug URL e la nuova pagina viene assegnata a tale URL.</span><span class="sxs-lookup"><span data-stu-id="4277d-119">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="4277d-120">Lo slug URL può essere modificato in seguito, dopo la pubblicazione della pagina.</span><span class="sxs-lookup"><span data-stu-id="4277d-120">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="4277d-121">Per ulteriori informazioni, vedere [Creare un URL di pagina](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="4277d-121">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4277d-122">Dynamics 365 Commerce scollega gli URL e il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4277d-122">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="4277d-123">Ovvero, è possibile creare una pagina che non è associata a un URL e un URL che non è associato a una pagina.</span><span class="sxs-lookup"><span data-stu-id="4277d-123">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="4277d-124">Di conseguenza, è possibile eseguire lo swapping di contenuto per un URL senza periodo di inattività e gli reindirizzamenti sono più facili da gestire.</span><span class="sxs-lookup"><span data-stu-id="4277d-124">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="4277d-125">Aggiungere una nuova pagina</span><span class="sxs-lookup"><span data-stu-id="4277d-125">Add a new page</span></span>

<span data-ttu-id="4277d-126">Per aggiungere un nuova pagina, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="4277d-126">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="4277d-127">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="4277d-127">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="4277d-128">Selezionare **Nuova pagina**.</span><span class="sxs-lookup"><span data-stu-id="4277d-128">Select **New Page**.</span></span>
1. <span data-ttu-id="4277d-129">Nella finestra di dialogo **Nuova pagina** selezionare un modello e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="4277d-129">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="4277d-130">Nel campo **Nome pagina**, immettere un nome di pagina, ad esempio **Nuova pagina**.</span><span class="sxs-lookup"><span data-stu-id="4277d-130">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="4277d-131">Nel campo **URL**, immettere una stringa (slug URL) per completare l'URL (ad esempio **nuovapagina**).</span><span class="sxs-lookup"><span data-stu-id="4277d-131">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="4277d-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4277d-132">Select **OK**.</span></span> <span data-ttu-id="4277d-133">Viene visualizzato l'editor delle pagine.</span><span class="sxs-lookup"><span data-stu-id="4277d-133">The page editor appears.</span></span> <span data-ttu-id="4277d-134">Si noti che un'intestazione e un piè di pagina vengono automaticamente aggiunti alla pagina, in base al modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="4277d-134">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="4277d-135">Nella struttura delle pagine, selezionare lo slot **Principale**, il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="4277d-135">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4277d-136">Selezionare **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="4277d-136">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="4277d-137">Selezionare **Contenitore fluido**, il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="4277d-137">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="4277d-138">Selezionare **Blocco ricco di contenuti** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="4277d-138">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="4277d-139">Selezionare **Blocco ricco di contenuti**, il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="4277d-139">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="4277d-140">Selezionare **Elemento blocco ricco di contenuti** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="4277d-140">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="4277d-141">Nel riquadro delle proprietà a destra, selezionare **Paragrafo**, quindi nel campo immettere **Testo di prova**.</span><span class="sxs-lookup"><span data-stu-id="4277d-141">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="4277d-142">Selezionare **Salva** e quindi selezionare **Archivia**.</span><span class="sxs-lookup"><span data-stu-id="4277d-142">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="4277d-143">Nel campo **Commenti**, immettere **Aggiunta nuova pagina** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4277d-143">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="4277d-144">Selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="4277d-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="4277d-145">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="4277d-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="4277d-146">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="4277d-146">Select **Publish**.</span></span>
1. <span data-ttu-id="4277d-147">Nel percorso di navigazione (barra di navigazione), selezionare **Fabrikam** (o il nome del sito).</span><span class="sxs-lookup"><span data-stu-id="4277d-147">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="4277d-148">Nel pannello di navigazione a sinistra, selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="4277d-148">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="4277d-149">Trovare e selezionare l'URL (**nuovapagina**) nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4277d-149">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="4277d-150">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="4277d-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4277d-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4277d-151">Additional resources</span></span>

[<span data-ttu-id="4277d-152">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="4277d-152">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="4277d-153">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="4277d-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="4277d-154">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="4277d-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="4277d-155">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="4277d-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="4277d-156">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="4277d-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="4277d-157">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="4277d-157">Enrich a category landing page</span></span>](enrich-category-page.md)
