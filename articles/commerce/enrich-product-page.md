---
title: Migliorare una pagina prodotto
description: In questo argomento viene descritto come migliorare una pagina prodotto in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: d9c0f329d21cdda5c36a39a8c602d5925b720f52
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945745"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="72ea4-103">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="72ea4-103">Enrich a product page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="72ea4-104">In questo argomento viene descritto come migliorare una pagina prodotto in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="72ea4-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="72ea4-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="72ea4-105">Overview</span></span>

<span data-ttu-id="72ea4-106">Per impostazione predefinita, il sito utilizza una pagina generica per visualizzare i dati del prodotto.</span><span class="sxs-lookup"><span data-stu-id="72ea4-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="72ea4-107">Questa pagina include le informazioni di base sul prodotto e i controlli necessari per venderlo.</span><span class="sxs-lookup"><span data-stu-id="72ea4-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="72ea4-108">Tuttavia, è possibile aggiungere ulteriori immagini o testo per un prodotto specifico alle informazioni del Server Retail.</span><span class="sxs-lookup"><span data-stu-id="72ea4-108">However, you can supplement the information that comes from the Retail Server with additional images or text for a specific product.</span></span> <span data-ttu-id="72ea4-109">Questo processo è noto come miglioramento della pagina prodotto.</span><span class="sxs-lookup"><span data-stu-id="72ea4-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="72ea4-110">In molti casi, si intende utilizzare ulteriore contenuto specifico per i prodotti.</span><span class="sxs-lookup"><span data-stu-id="72ea4-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="72ea4-111">Quando si accede a **Vendita al dettaglio** nello strumento di creazione, è visibile un elenco di prodotti del canale assegnato al sito.</span><span class="sxs-lookup"><span data-stu-id="72ea4-111">When you go to **Retail** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="72ea4-112">Nell'elenco, la colonna **Migliorata** indica se la pagina prodotto di un prodotto è stata migliorata.</span><span class="sxs-lookup"><span data-stu-id="72ea4-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="72ea4-113">Se un segno di spunta è visualizzato nella colonna, una pagina prodotto migliorata esiste per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="72ea4-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="72ea4-114">Se nessun segno di spunta è visualizzato, il contenuto e la pagina prodotto predefiniti vengono utilizzati per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="72ea4-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="72ea4-115">È possibile visualizzare l'anteprima delle pagine prodotto migliorate e non migliorate selezionando un nome di prodotto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="72ea4-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="72ea4-116">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="72ea4-116">Enrich a product page</span></span>

<span data-ttu-id="72ea4-117">Per migliorare una pagina prodotto, attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="72ea4-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="72ea4-118">In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).</span><span class="sxs-lookup"><span data-stu-id="72ea4-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="72ea4-119">Selezionare **Prodotti** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="72ea4-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="72ea4-120">Selezionare un prodotto qualsiasi che non dispone di una pagina prodotto migliorata.</span><span class="sxs-lookup"><span data-stu-id="72ea4-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="72ea4-121">Nel riquadro azioni selezionare **Migliora pagina prodotto**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="72ea4-122">Selezionare **Modello PDP** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="72ea4-123">Nell'albero delle pagine a sinistra espandere, lo slot **Principale**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="72ea4-124">Selezionare il pulsante con i puntini di sospensione (**...**) per lo slot **Principale** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="72ea4-125">Selezionare **Contenitore 2** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="72ea4-126">Selezionare il pulsante con i puntini di sospensione per lo slot **Contenitore 2** e quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="72ea4-127">Selezionare **Funzionalità** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="72ea4-128">Nel riquadro delle proprietà a destra, nel campo **RTF**, immettere la descrizione aggiornata del prodotto.</span><span class="sxs-lookup"><span data-stu-id="72ea4-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="72ea4-129">Nel campo **Intestazione**, immettere il testo dell'intestazione e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="72ea4-130">Selezionare **Salva** e quindi selezionare **Archivia**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-130">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="72ea4-131">Nel campo **Commenti**, immettere **Prodotto migliorato**e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="72ea4-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="72ea4-132">Selezionare **Anteprima** per eseguire l'anteprima della pagina prodotto migliorata.</span><span class="sxs-lookup"><span data-stu-id="72ea4-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="72ea4-133">Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="72ea4-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="72ea4-134">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="72ea4-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72ea4-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="72ea4-135">Additional resources</span></span>

[<span data-ttu-id="72ea4-136">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="72ea4-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="72ea4-137">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="72ea4-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="72ea4-138">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="72ea4-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="72ea4-139">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="72ea4-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="72ea4-140">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="72ea4-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="72ea4-141">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="72ea4-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="72ea4-142">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="72ea4-142">Verify page content accessibility</span></span>](verify-accessibility.md)
