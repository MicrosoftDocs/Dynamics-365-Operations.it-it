---
title: Migliorare una pagina di destinazione di categoria
description: In questo argomento viene descritto come migliorare le pagine categoria in Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fbcf6ec60723b726e022b4e17bbde4c903e5cb57
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238781"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="9f467-103">Migliorare una pagina di destinazione di categoria</span><span class="sxs-lookup"><span data-stu-id="9f467-103">Enrich a category landing page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9f467-104">In questo argomento viene descritto come migliorare le pagine categoria in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9f467-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9f467-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9f467-105">Overview</span></span>

<span data-ttu-id="9f467-106">Commerce fornisce una pagina di destinazione predefinita per le categorie che viene utilizzata quando i dati di categoria sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="9f467-106">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="9f467-107">Una pagina categoria predefinita contiene gli elementi necessari, ad esempio criteri di raffinamento, posizionamento dei prodotti categorizzati, opzioni,di ordinamento, un riepilogo delle scelte e controlli di impaginazione.</span><span class="sxs-lookup"><span data-stu-id="9f467-107">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="9f467-108">Tuttavia, anziché utilizzare la pagina categoria predefinita, è possibile utilizzare una pagina di destinazione per le categorie "migliorata" con più contenuto e più elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="9f467-108">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="9f467-109">Un miglioramento tipico potrebbe essere l'aggiunta alla pagina categoria di contenuto marketing specifico alla categoria.</span><span class="sxs-lookup"><span data-stu-id="9f467-109">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="9f467-110">Questo contenuto potrebbe includere il posizionamento dei prodotti nelle categorie per scopi di cross-selling, elenchi editoriali, immagini, video e altro testo.</span><span class="sxs-lookup"><span data-stu-id="9f467-110">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="9f467-111">È possibile modificare la pagina categoria predefinita o definire un'altra pagina categoria per una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="9f467-111">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Pagina di destinazione di categoria migliorata](./media/CategoryLandingPages.png)

<span data-ttu-id="9f467-113">In Creazione di siti Web di Commerce, la pagina **Prodotti** include un elenco di categorie del canale assegnate al sito.</span><span class="sxs-lookup"><span data-stu-id="9f467-113">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="9f467-114">Se lo stato **Migliorata** è selezionato per una pagina categoria, quella pagina è stata migliorata.</span><span class="sxs-lookup"><span data-stu-id="9f467-114">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="9f467-115">In caso contrario, la pagina categoria predefinita e il contenuto vengono utilizzati per la categoria.</span><span class="sxs-lookup"><span data-stu-id="9f467-115">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="9f467-116">È possibile visualizzare l'anteprima delle pagine categoria migliorate e non migliorate selezionando il nome della categoria.</span><span class="sxs-lookup"><span data-stu-id="9f467-116">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="9f467-117">Per migliorare una pagina categoria, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="9f467-117">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="9f467-118">Nella pagina **Prodotti**, selezionare il nome della categoria per la quale si intende migliorare la pagina categoria.</span><span class="sxs-lookup"><span data-stu-id="9f467-118">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="9f467-119">La pagina categoria predefinita per la categoria selezionata viene aperta nell'editor di pagine.</span><span class="sxs-lookup"><span data-stu-id="9f467-119">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="9f467-120">Selezionare **Migliora pagina categoria**.</span><span class="sxs-lookup"><span data-stu-id="9f467-120">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="9f467-121">Selezionare un modello per la pagina categoria migliorata.</span><span class="sxs-lookup"><span data-stu-id="9f467-121">Select a template for the enriched category page.</span></span> <span data-ttu-id="9f467-122">Se si apportano solo modifiche minori, è possibile selezionare la pagina categoria predefinita.</span><span class="sxs-lookup"><span data-stu-id="9f467-122">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="9f467-123">In alternativa, è possibile selezionare uno specifico modello di pagina categoria.</span><span class="sxs-lookup"><span data-stu-id="9f467-123">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="9f467-124">Quando si seleziona il modello, l'editor di pagine viene aperto e il modello selezionato viene utilizzato per creare una nuova pagina categoria per la categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="9f467-124">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="9f467-125">La pagina viene estratta ed è possibile apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="9f467-125">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="9f467-126">I moduli che utilizzano i dati di categoria utilizzano i dati dalla categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="9f467-126">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="9f467-127">Le impostazioni del modello selezionato determinano le modifiche che è possibile apportare.</span><span class="sxs-lookup"><span data-stu-id="9f467-127">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f467-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9f467-128">Additional resources</span></span>

[<span data-ttu-id="9f467-129">Modificare una pagina di sito esistente</span><span class="sxs-lookup"><span data-stu-id="9f467-129">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="9f467-130">Aggiungere una nuova pagina del sito</span><span class="sxs-lookup"><span data-stu-id="9f467-130">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="9f467-131">Selezionare layout di pagina</span><span class="sxs-lookup"><span data-stu-id="9f467-131">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="9f467-132">Gestire i metadati SEO</span><span class="sxs-lookup"><span data-stu-id="9f467-132">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="9f467-133">Salvare, visualizzare in anteprima e pubblicare una pagina</span><span class="sxs-lookup"><span data-stu-id="9f467-133">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="9f467-134">Migliorare una pagina prodotto</span><span class="sxs-lookup"><span data-stu-id="9f467-134">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="9f467-135">Verificare l'accessibilità del contenuto della pagina</span><span class="sxs-lookup"><span data-stu-id="9f467-135">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="9f467-136">Creare pagine di e-commerce dinamiche in base ai parametri URL</span><span class="sxs-lookup"><span data-stu-id="9f467-136">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]