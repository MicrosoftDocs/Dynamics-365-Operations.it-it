---
title: Migliorare una pagina di destinazione di categoria
description: In questo argomento viene descritto come migliorare le pagine categoria in Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 71348efba9fc1374b9e6599eb23f198d3851036e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003052"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="da618-103">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="da618-103">Enrich a category landing page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="da618-104">In questo argomento viene descritto come migliorare le pagine categoria in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="da618-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="da618-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="da618-105">Overview</span></span>

<span data-ttu-id="da618-106">Commerce fornisce una pagina di destinazione predefinita per le categorie che viene utilizzata quando i dati di categoria sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="da618-106">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="da618-107">Una pagina categoria predefinita contiene gli elementi necessari, ad esempio criteri di raffinamento, posizionamento dei prodotti categorizzati, opzioni,di ordinamento, un riepilogo delle scelte e controlli di impaginazione.</span><span class="sxs-lookup"><span data-stu-id="da618-107">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="da618-108">Tuttavia, anziché utilizzare la pagina categoria predefinita, è possibile utilizzare una pagina di destinazione per le categorie "migliorata" con più contenuto e più elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="da618-108">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="da618-109">Un miglioramento tipico potrebbe essere l'aggiunta alla pagina categoria di contenuto marketing specifico alla categoria.</span><span class="sxs-lookup"><span data-stu-id="da618-109">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="da618-110">Questo contenuto potrebbe includere il posizionamento dei prodotti nelle categorie per scopi di cross-selling, elenchi editoriali, immagini, video e altro testo.</span><span class="sxs-lookup"><span data-stu-id="da618-110">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="da618-111">È possibile modificare la pagina categoria predefinita o definire un'altra pagina categoria per una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="da618-111">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Pagina di destinazione di categoria migliorata](./media/CategoryLandingPages.png)

<span data-ttu-id="da618-113">Nello strumento di creazione, la pagina **Prodotto** include un elenco di categorie del canale che sono assegnate al sito.</span><span class="sxs-lookup"><span data-stu-id="da618-113">In the authoring tool, the **Product** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="da618-114">Se lo stato **Migliorata** è selezionato per una pagina categoria, quella pagina è stata migliorata.</span><span class="sxs-lookup"><span data-stu-id="da618-114">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="da618-115">In caso contrario, la pagina categoria predefinita e il contenuto vengono utilizzati per la categoria.</span><span class="sxs-lookup"><span data-stu-id="da618-115">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="da618-116">È possibile visualizzare l'anteprima delle pagine categoria migliorate e non migliorate selezionando il nome della categoria.</span><span class="sxs-lookup"><span data-stu-id="da618-116">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="da618-117">Per migliorare una pagina categoria, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="da618-117">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="da618-118">Nella pagina **Prodotti**, selezionare il nome della categoria per la quale si intende migliorare la pagina categoria.</span><span class="sxs-lookup"><span data-stu-id="da618-118">On the **Products** page, select the name of the category that you want to enrich the category page for.</span></span> <span data-ttu-id="da618-119">La pagina categoria predefinita per la categoria selezionata viene aperta nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="da618-119">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="da618-120">Selezionare **Migliora pagina categoria**.</span><span class="sxs-lookup"><span data-stu-id="da618-120">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="da618-121">Selezionare un modello per la pagina categoria migliorata.</span><span class="sxs-lookup"><span data-stu-id="da618-121">Select a template for the enriched category page.</span></span> <span data-ttu-id="da618-122">Se si apportano solo modifiche minori, è possibile selezionare la pagina categoria predefinita.</span><span class="sxs-lookup"><span data-stu-id="da618-122">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="da618-123">In alternativa, è possibile selezionare uno specifico modello di pagina categoria.</span><span class="sxs-lookup"><span data-stu-id="da618-123">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="da618-124">Quando si seleziona il modello, l'editor di pagine viene aperto e il modello selezionato viene utilizzato per creare una nuova pagina categoria per la categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="da618-124">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="da618-125">La pagina viene estratta ed è possibile apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="da618-125">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="da618-126">I moduli che utilizzano i dati di categoria utilizzano i dati dalla categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="da618-126">Modules that use category specification data use the data from your selected category.</span></span>
>
> <span data-ttu-id="da618-127">Le impostazioni del modello selezionato determinano le modifiche che è possibile apportare.</span><span class="sxs-lookup"><span data-stu-id="da618-127">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da618-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="da618-128">Additional resources</span></span>

[<span data-ttu-id="da618-129">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="da618-129">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="da618-130">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="da618-130">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="da618-131">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="da618-131">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="da618-132">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="da618-132">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="da618-133">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="da618-133">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="da618-134">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="da618-134">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="da618-135">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="da618-135">Verify page content accessibility</span></span>](verify-accessibility.md)
