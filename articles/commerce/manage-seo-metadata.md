---
title: Gestire i metadati SEO
description: In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b69d9d2769023967e2b94fef1b8fcf6b5b3357c5
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698351"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="f8134-103">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="f8134-103">Manage SEO metadata</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f8134-104">In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f8134-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f8134-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f8134-105">Overview</span></span>

<span data-ttu-id="f8134-106">I metadati SEO per un sito possono essere gestiti utilizzando mappe del sito e metadati delle pagine.</span><span class="sxs-lookup"><span data-stu-id="f8134-106">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="f8134-107">Mappe del sito</span><span class="sxs-lookup"><span data-stu-id="f8134-107">Site maps</span></span>

<span data-ttu-id="f8134-108">Una mappa del sito è un elenco leggibile al computer, in formato XML, delle pagine del sito Web.</span><span class="sxs-lookup"><span data-stu-id="f8134-108">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="f8134-109">È utilizzato dai motori di ricerca, di modo che possano fornire risultati di ricerca migliori nel sito.</span><span class="sxs-lookup"><span data-stu-id="f8134-109">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="f8134-110">Le mappe del sito possono essere inserite dai motori di ricerca o pubblicate in un file robots.txt.</span><span class="sxs-lookup"><span data-stu-id="f8134-110">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="f8134-111">Dynamics 365 Commerce supporta la generazione automatica di mappe del sito.</span><span class="sxs-lookup"><span data-stu-id="f8134-111">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="f8134-112">Le mappe del sito sono aggiornate automaticamente quando si pubblicano le pagine o se ne annulla la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f8134-112">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="f8134-113">Attivare la generazione della mappa del sito</span><span class="sxs-lookup"><span data-stu-id="f8134-113">Turn on site map generation</span></span>

1. <span data-ttu-id="f8134-114">Accedere allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="f8134-114">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="f8134-115">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="f8134-115">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f8134-116">Selezionare **Gestione sito** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="f8134-116">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="f8134-117">Verificare che l'opzione **Mappe del sito abilitate** sia attivata.</span><span class="sxs-lookup"><span data-stu-id="f8134-117">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="f8134-118">Metadati delle pagine</span><span class="sxs-lookup"><span data-stu-id="f8134-118">Page metadata</span></span>

<span data-ttu-id="f8134-119">Dynamics 365 Commerce consente di gestire i metadati SEO di singole pagine.</span><span class="sxs-lookup"><span data-stu-id="f8134-119">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="f8134-120">È possibile visualizzare e modificare queste informazioni nella sezione **Proprietà SEO** di un contenitore pagina.</span><span class="sxs-lookup"><span data-stu-id="f8134-120">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="f8134-121">Sono supportate le seguenti proprietà dei metadati SEO:</span><span class="sxs-lookup"><span data-stu-id="f8134-121">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="f8134-122">Funzione</span><span class="sxs-lookup"><span data-stu-id="f8134-122">Title</span></span>
- <span data-ttu-id="f8134-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8134-123">Description</span></span>
- <span data-ttu-id="f8134-124">Parole chiave SEO</span><span class="sxs-lookup"><span data-stu-id="f8134-124">SEO keywords</span></span>
- <span data-ttu-id="f8134-125">Etichette Aria</span><span class="sxs-lookup"><span data-stu-id="f8134-125">Aria labels</span></span>
- <span data-ttu-id="f8134-126">noindex</span><span class="sxs-lookup"><span data-stu-id="f8134-126">noindex</span></span>
- <span data-ttu-id="f8134-127">nofollow</span><span class="sxs-lookup"><span data-stu-id="f8134-127">nofollow</span></span>
- <span data-ttu-id="f8134-128">noarchive</span><span class="sxs-lookup"><span data-stu-id="f8134-128">noarchive</span></span>
- <span data-ttu-id="f8134-129">nocache</span><span class="sxs-lookup"><span data-stu-id="f8134-129">nocache</span></span>
- <span data-ttu-id="f8134-130">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="f8134-130">noOpenDirectoryProject</span></span>
- <span data-ttu-id="f8134-131">nosnippet</span><span class="sxs-lookup"><span data-stu-id="f8134-131">nosnippet</span></span>
- <span data-ttu-id="f8134-132">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="f8134-132">noImageIndex</span></span>
- <span data-ttu-id="f8134-133">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="f8134-133">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="f8134-134">Modificare i metadati della pagina</span><span class="sxs-lookup"><span data-stu-id="f8134-134">Modify page metadata</span></span>

<span data-ttu-id="f8134-135">Per modificare i metadati della pagina, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8134-135">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="f8134-136">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="f8134-136">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f8134-137">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="f8134-137">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="f8134-138">Selezionare la home page per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="f8134-138">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="f8134-139">Nel riquadro azioni selezionare **Estrai**.</span><span class="sxs-lookup"><span data-stu-id="f8134-139">On the Action Pane, select **Check Out**.</span></span>
1. <span data-ttu-id="f8134-140">Nel riquadro delle proprietà a destra, espandere **Metatag predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="f8134-140">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="f8134-141">Per aggiungere un nuovo metatag, selezionare **Aggiungi** e immettere il tag nel campo.</span><span class="sxs-lookup"><span data-stu-id="f8134-141">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span>

    <span data-ttu-id="f8134-142">Per rimuovere un metatag esistente, selezionare il cestino a destra dello stesso.</span><span class="sxs-lookup"><span data-stu-id="f8134-142">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>

1. <span data-ttu-id="f8134-143">Selezionare **Salva** e quindi selezionare **Archivia**.</span><span class="sxs-lookup"><span data-stu-id="f8134-143">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="f8134-144">Nel campo **Commenti**, immettere **Metatag aggiornati** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8134-144">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="f8134-145">Selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="f8134-145">Select **Preview** to preview your page.</span></span> <span data-ttu-id="f8134-146">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="f8134-146">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="f8134-147">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="f8134-147">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8134-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f8134-148">Additional resources</span></span>

[<span data-ttu-id="f8134-149">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="f8134-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="f8134-150">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="f8134-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="f8134-151">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="f8134-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="f8134-152">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="f8134-152">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="f8134-153">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="f8134-153">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="f8134-154">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="f8134-154">Enrich a category landing page</span></span>](enrich-category-page.md)

