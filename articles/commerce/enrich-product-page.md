---
title: Migliorare una pagina prodotto
description: In questo argomento viene descritto come migliorare una pagina prodotto in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: f6c1a9474ed514426386b1d7b4a72b62129cdb8a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799048"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="2753b-103">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="2753b-103">Enrich a product page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2753b-104">In questo argomento viene descritto come migliorare una pagina prodotto in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2753b-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2753b-105">Per impostazione predefinita, il sito utilizza una pagina generica per visualizzare i dati del prodotto.</span><span class="sxs-lookup"><span data-stu-id="2753b-105">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="2753b-106">Questa pagina include le informazioni di base sul prodotto e i controlli necessari per venderlo.</span><span class="sxs-lookup"><span data-stu-id="2753b-106">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="2753b-107">Tuttavia, è possibile aggiungere ulteriori immagini o testo per un prodotto specifico alle informazioni di Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="2753b-107">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="2753b-108">Questo processo è noto come miglioramento della pagina prodotto.</span><span class="sxs-lookup"><span data-stu-id="2753b-108">This process is known as enriching the product page.</span></span>

<span data-ttu-id="2753b-109">In molti casi, si intende utilizzare ulteriore contenuto specifico per i prodotti.</span><span class="sxs-lookup"><span data-stu-id="2753b-109">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="2753b-110">Quando si accede a **Retail e Commerce** nello strumento di creazione, è visibile un elenco di prodotti del canale assegnato al sito.</span><span class="sxs-lookup"><span data-stu-id="2753b-110">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="2753b-111">Nell'elenco, la colonna **Migliorata** indica se la pagina prodotto di un prodotto è stata migliorata.</span><span class="sxs-lookup"><span data-stu-id="2753b-111">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="2753b-112">Se un segno di spunta è visualizzato nella colonna, una pagina prodotto migliorata esiste per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="2753b-112">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="2753b-113">Se nessun segno di spunta è visualizzato, il contenuto e la pagina prodotto predefiniti vengono utilizzati per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="2753b-113">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="2753b-114">È possibile visualizzare l'anteprima delle pagine prodotto migliorate e non migliorate selezionando un nome di prodotto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2753b-114">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="2753b-115">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="2753b-115">Enrich a product page</span></span>

<span data-ttu-id="2753b-116">Per migliorare una pagina prodotto, attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="2753b-116">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="2753b-117">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="2753b-117">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="2753b-118">Selezionare **Prodotti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="2753b-118">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="2753b-119">Selezionare un prodotto qualsiasi che non dispone di una pagina prodotto migliorata.</span><span class="sxs-lookup"><span data-stu-id="2753b-119">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="2753b-120">Nel riquadro azioni selezionare **Migliora pagina prodotto**.</span><span class="sxs-lookup"><span data-stu-id="2753b-120">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="2753b-121">Selezionare **Modello PDP** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="2753b-121">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="2753b-122">Nell'albero delle pagine a sinistra espandere, lo slot **Principale**.</span><span class="sxs-lookup"><span data-stu-id="2753b-122">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="2753b-123">Selezionare il pulsante con i puntini di sospensione (**...**) per lo slot **Principale** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="2753b-123">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="2753b-124">Selezionare **Contenitore 2** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="2753b-124">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="2753b-125">Selezionare il pulsante con i puntini di sospensione per lo slot **Contenitore 2** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="2753b-125">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="2753b-126">Selezionare **Funzionalità** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="2753b-126">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="2753b-127">Nel riquadro delle proprietà a destra, nel campo **RTF**, immettere la descrizione aggiornata del prodotto.</span><span class="sxs-lookup"><span data-stu-id="2753b-127">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="2753b-128">Nel campo **Intestazione**, immettere il testo dell'intestazione e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2753b-128">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="2753b-129">Selezionare **Salva** e quindi selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="2753b-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="2753b-130">Nel campo **Commenti**, immettere **Prodotto migliorato** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2753b-130">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="2753b-131">Selezionare **Anteprima** per eseguire l'anteprima della pagina prodotto migliorata.</span><span class="sxs-lookup"><span data-stu-id="2753b-131">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="2753b-132">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="2753b-132">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="2753b-133">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="2753b-133">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2753b-134">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2753b-134">Additional resources</span></span>

[<span data-ttu-id="2753b-135">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="2753b-135">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="2753b-136">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="2753b-136">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="2753b-137">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="2753b-137">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="2753b-138">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="2753b-138">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="2753b-139">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="2753b-139">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="2753b-140">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="2753b-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="2753b-141">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="2753b-141">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="2753b-142">Creare pagine di e-commerce dinamiche in base ai parametri URL</span><span class="sxs-lookup"><span data-stu-id="2753b-142">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
