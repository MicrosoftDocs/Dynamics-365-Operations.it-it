---
title: Gestire i metadati SEO
description: In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1e03ef346df92a94b0a403f241d0f7d1f64fd210
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794213"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="47820-103">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="47820-103">Manage SEO metadata</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="47820-104">In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="47820-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="47820-105">I metadati SEO per un sito possono essere gestiti utilizzando mappe del sito e metadati delle pagine.</span><span class="sxs-lookup"><span data-stu-id="47820-105">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="47820-106">Mappe del sito</span><span class="sxs-lookup"><span data-stu-id="47820-106">Site maps</span></span>

<span data-ttu-id="47820-107">Una mappa del sito è un elenco leggibile al computer, in formato XML, delle pagine del sito Web.</span><span class="sxs-lookup"><span data-stu-id="47820-107">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="47820-108">È utilizzato dai motori di ricerca, di modo che possano fornire risultati di ricerca migliori nel sito.</span><span class="sxs-lookup"><span data-stu-id="47820-108">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="47820-109">Le mappe del sito possono essere inserite dai motori di ricerca o pubblicate in un file robots.txt.</span><span class="sxs-lookup"><span data-stu-id="47820-109">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="47820-110">Dynamics 365 Commerce supporta la generazione automatica di mappe del sito.</span><span class="sxs-lookup"><span data-stu-id="47820-110">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="47820-111">Le mappe del sito sono aggiornate automaticamente quando si pubblicano le pagine o se ne annulla la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="47820-111">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="47820-112">Attivare la generazione della mappa del sito</span><span class="sxs-lookup"><span data-stu-id="47820-112">Turn on site map generation</span></span>

1. <span data-ttu-id="47820-113">Accedere allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="47820-113">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="47820-114">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="47820-114">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="47820-115">Selezionare **Gestione sito** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="47820-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="47820-116">Verificare che l'opzione **Mappe del sito abilitate** sia attivata.</span><span class="sxs-lookup"><span data-stu-id="47820-116">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="47820-117">Metadati delle pagine</span><span class="sxs-lookup"><span data-stu-id="47820-117">Page metadata</span></span>

<span data-ttu-id="47820-118">Dynamics 365 Commerce consente di gestire i metadati SEO di singole pagine.</span><span class="sxs-lookup"><span data-stu-id="47820-118">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="47820-119">È possibile visualizzare e modificare queste informazioni nella sezione **Proprietà SEO** di un contenitore pagina.</span><span class="sxs-lookup"><span data-stu-id="47820-119">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="47820-120">Sono supportate le seguenti proprietà dei metadati SEO:</span><span class="sxs-lookup"><span data-stu-id="47820-120">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="47820-121">Funzione</span><span class="sxs-lookup"><span data-stu-id="47820-121">Title</span></span>
- <span data-ttu-id="47820-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47820-122">Description</span></span>
- <span data-ttu-id="47820-123">Parole chiave SEO</span><span class="sxs-lookup"><span data-stu-id="47820-123">SEO keywords</span></span>
- <span data-ttu-id="47820-124">Etichette Aria</span><span class="sxs-lookup"><span data-stu-id="47820-124">Aria labels</span></span>
- <span data-ttu-id="47820-125">noindex</span><span class="sxs-lookup"><span data-stu-id="47820-125">noindex</span></span>
- <span data-ttu-id="47820-126">nofollow</span><span class="sxs-lookup"><span data-stu-id="47820-126">nofollow</span></span>
- <span data-ttu-id="47820-127">noarchive</span><span class="sxs-lookup"><span data-stu-id="47820-127">noarchive</span></span>
- <span data-ttu-id="47820-128">nocache</span><span class="sxs-lookup"><span data-stu-id="47820-128">nocache</span></span>
- <span data-ttu-id="47820-129">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="47820-129">noOpenDirectoryProject</span></span>
- <span data-ttu-id="47820-130">nosnippet</span><span class="sxs-lookup"><span data-stu-id="47820-130">nosnippet</span></span>
- <span data-ttu-id="47820-131">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="47820-131">noImageIndex</span></span>
- <span data-ttu-id="47820-132">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="47820-132">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="47820-133">Modificare i metadati della pagina</span><span class="sxs-lookup"><span data-stu-id="47820-133">Modify page metadata</span></span>

<span data-ttu-id="47820-134">Per modificare i metadati della pagina, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="47820-134">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="47820-135">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="47820-135">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="47820-136">Nel pannello di navigazione a sinistra, selezionare **Pagine**.</span><span class="sxs-lookup"><span data-stu-id="47820-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="47820-137">Selezionare la home page per aprirla nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="47820-137">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="47820-138">Nella barra dei comandi, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="47820-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="47820-139">Nel riquadro delle proprietà a destra, espandere **Metatag predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="47820-139">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="47820-140">Per aggiungere un nuovo metatag, selezionare **Aggiungi** e immettere il tag nel campo.</span><span class="sxs-lookup"><span data-stu-id="47820-140">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="47820-141">Per rimuovere un metatag esistente, selezionare il cestino a destra dello stesso.</span><span class="sxs-lookup"><span data-stu-id="47820-141">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="47820-142">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="47820-142">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="47820-143">Nel campo **Commenti**, immettere **Metatag aggiornati** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="47820-143">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="47820-144">Selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="47820-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="47820-145">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="47820-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="47820-146">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="47820-146">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="47820-147">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="47820-147">Additional resources</span></span>

[<span data-ttu-id="47820-148">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="47820-148">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="47820-149">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="47820-149">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="47820-150">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="47820-150">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="47820-151">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="47820-151">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="47820-152">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="47820-152">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="47820-153">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="47820-153">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="47820-154">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="47820-154">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="47820-155">Creare pagine di e-commerce dinamiche in base ai parametri URL</span><span class="sxs-lookup"><span data-stu-id="47820-155">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
