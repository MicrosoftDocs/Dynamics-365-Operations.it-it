---
title: Modulo dei risultati di ricerca
description: Questo argomento tratta i moduli dei risultati di ricerca e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d852fe1a81b1e42484bc49ae136ef8613a2d3a5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254771"
---
# <a name="search-results-module"></a><span data-ttu-id="677d6-103">Modulo dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="677d6-103">Search results module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="677d6-104">Questo argomento tratta i moduli dei risultati di ricerca e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="677d6-104">This topic covers search results modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="677d6-105">Il modulo dei risultati di ricerca restituisce i risultati della ricerca del prodotto e un elenco di criteri di affinamento applicabili per i prodotti.</span><span class="sxs-lookup"><span data-stu-id="677d6-105">The search results module returns product search results and a list of applicable refiners for the products.</span></span> <span data-ttu-id="677d6-106">Moduli dei risultati di ricerca nei siti Dynamics 365 Commerce possono essere utilizzati per visualizzare le pagine per i seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="677d6-106">Search results modules on Dynamics 365 Commerce sites can be used to render pages for the following scenarios:</span></span>

- <span data-ttu-id="677d6-107">Risultati della ricerca avviati da una ricerca utente</span><span class="sxs-lookup"><span data-stu-id="677d6-107">Search results that are initiated by a user search</span></span>
- <span data-ttu-id="677d6-108">I risultati di ricerca che mostrano un insieme specifico di prodotti, ad esempio "Acquista articoli simili"</span><span class="sxs-lookup"><span data-stu-id="677d6-108">Search results that show a specific set of products, such as "Shop similar looks"</span></span>
- <span data-ttu-id="677d6-109">Elenchi di prodotti appartenenti a una categoria</span><span class="sxs-lookup"><span data-stu-id="677d6-109">Lists of products that belong to a category</span></span>

<span data-ttu-id="677d6-110">Per ulteriori informazioni sulle pagine dei risultati di ricerca e categoria, vedi [Pagina di destinazione della categoria predefinita e panoramica della pagina dei risultati di ricerca](category-search-page-overview.md).</span><span class="sxs-lookup"><span data-stu-id="677d6-110">For more information about category and search results pages, see [Default category landing page and search results page overview](category-search-page-overview.md).</span></span>

<span data-ttu-id="677d6-111">La figura seguente mostra un esempio di una pagina dei risultati della ricerca per una categoria per il sito Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="677d6-111">The following illustration shows an example of a search results page for a category on the Fabrikam site.</span></span>

![Esempio di pagina dei risultati della ricerca sul sito Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a><span data-ttu-id="677d6-113">Proprietà del modulo dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="677d6-113">Search results module properties</span></span>

<span data-ttu-id="677d6-114">La tabella seguente elenca le proprietà dei moduli dei risultati di ricerca, insieme ai relativi valori e descrizioni.</span><span class="sxs-lookup"><span data-stu-id="677d6-114">The following table lists the properties of search result modules, together with their values and descriptions.</span></span>

| <span data-ttu-id="677d6-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="677d6-115">Property</span></span> | <span data-ttu-id="677d6-116">Valori</span><span class="sxs-lookup"><span data-stu-id="677d6-116">Values</span></span> | <span data-ttu-id="677d6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="677d6-117">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="677d6-118">Articoli per pagina</span><span class="sxs-lookup"><span data-stu-id="677d6-118">Items per page</span></span> | <span data-ttu-id="677d6-119">Integer</span><span class="sxs-lookup"><span data-stu-id="677d6-119">Integer</span></span> | <span data-ttu-id="677d6-120">Il numero di articoli che devono essere visualizzati su ciascuna pagina.</span><span class="sxs-lookup"><span data-stu-id="677d6-120">The number of items that should be shown on each page.</span></span> |
| <span data-ttu-id="677d6-121">Consenti di tornare indietro su PDP</span><span class="sxs-lookup"><span data-stu-id="677d6-121">Allow back on PDP</span></span> | <span data-ttu-id="677d6-122">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="677d6-122">**True** or **False**</span></span> | <span data-ttu-id="677d6-123">Se questa proprietà è impostata su **True**, quando un utente seleziona un prodotto nella pagina dei risultati di ricerca, il Percorso di navigazione nella pagina dei dettagli del prodotto (PDP) che viene aperto mostrerà un collegamento "Torna ai risultati".</span><span class="sxs-lookup"><span data-stu-id="677d6-123">If this property is set to **True**, when a user selects a product on the search results page, the breadcrumb navigation on the product details page (PDP) that is opened will show a "Back to results" link.</span></span> |
| <span data-ttu-id="677d6-124">Espandi affinamenti</span><span class="sxs-lookup"><span data-stu-id="677d6-124">Expand Refiners</span></span> | <span data-ttu-id="677d6-125">**Tutto**, **1**, **2**, **3**, o **4**</span><span class="sxs-lookup"><span data-stu-id="677d6-125">**All**, **1**, **2**, **3**, or **4**</span></span> | <span data-ttu-id="677d6-126">Il numero di affinamenti principali da espandere quando viene caricata una pagina.</span><span class="sxs-lookup"><span data-stu-id="677d6-126">The number of top refiners that should be expanded when a page is loaded.</span></span> <span data-ttu-id="677d6-127">Ad esempio, se questa proprietà è impostata su **3**, verranno espansi i primi tre criteri di affinamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="677d6-127">For example, if this property is set to **3**, the first three refiners on the page will be expanded.</span></span> |
| <span data-ttu-id="677d6-128">Nascondi visualizzazione gerarchia di categorie</span><span class="sxs-lookup"><span data-stu-id="677d6-128">Hide category hierarchy display</span></span> | <span data-ttu-id="677d6-129">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="677d6-129">**True** or **False**</span></span> | <span data-ttu-id="677d6-130">Se questa proprietà è impostata su **True**, la visualizzazione della gerarchia delle categorie nella pagina verrà nascosta.</span><span class="sxs-lookup"><span data-stu-id="677d6-130">If this property is set to **True**, the category hierarchy display on the page will be hidden.</span></span> <span data-ttu-id="677d6-131">Questa proprietà deve essere impostata su **True** se stai usando il [modulo Percorso di navigazione](add-breadcrumb.md) per mostrare la gerarchia delle categorie.</span><span class="sxs-lookup"><span data-stu-id="677d6-131">This property should be set to **True** if you're using the [breadcrumb module](add-breadcrumb.md) to show the category hierarchy.</span></span>|
| <span data-ttu-id="677d6-132">Includi attributi del prodotto nei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="677d6-132">Include product attributes in search results</span></span> | <span data-ttu-id="677d6-133">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="677d6-133">**True** or **False**</span></span> | <span data-ttu-id="677d6-134">Se questa proprietà è impostata su **True**, verranno restituiti gli attributi per i prodotti nei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="677d6-134">If this property is set to **True**, attributes will be returned for the products in the search results.</span></span> <span data-ttu-id="677d6-135">Sebbene questi attributi possano essere visualizzati su un sito di Commerce, è necessaria un'estensione.</span><span class="sxs-lookup"><span data-stu-id="677d6-135">Although these attributes can be shown on a Commerce site, an extension is required.</span></span>|
| <span data-ttu-id="677d6-136">Mostra i prezzi del rapporto</span><span class="sxs-lookup"><span data-stu-id="677d6-136">Show affiliation prices</span></span> | <span data-ttu-id="677d6-137">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="677d6-137">**True** or **False**</span></span> | <span data-ttu-id="677d6-138">Se questa proprietà è impostata su **True**, i prezzi di affiliazione per i prodotti verranno visualizzati nei risultati di ricerca quando un utente che ha eseguito l'accesso naviga alla pagina.</span><span class="sxs-lookup"><span data-stu-id="677d6-138">If this property is set to **True**, affiliation prices for products will be shown in the search results when a signed-in user browses the page.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="677d6-139">In Dynamics 365 Commerce versione 10.0.16 e successive, la configurazione **Mostra prezzi di affiliazione** può essere utilizzata per mostrare i prezzi di affiliazione sulla pagina.</span><span class="sxs-lookup"><span data-stu-id="677d6-139">In the Dynamics 365 Commerce 10.0.16 release and later, the **Show affiliation prices** configuration can be used to show affiliation prices on the page.</span></span>

## <a name="supported-modules"></a><span data-ttu-id="677d6-140">Moduli supportati</span><span class="sxs-lookup"><span data-stu-id="677d6-140">Supported modules</span></span>

<span data-ttu-id="677d6-141">Il modulo di risultati di ricerca supporta il [modulo di visualizzazione rapida](quick-view-module.md), che consente agli utenti di visualizzare le informazioni sul prodotto e aggiungere articoli al carrello da una pagina di risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="677d6-141">The search results module supports the [quick view module](quick-view-module.md), which lets users view product information and add items to the cart from the search results page.</span></span>

## <a name="add-a-search-results-module-to-a-category-page"></a><span data-ttu-id="677d6-142">Aggiungere un modulo dei risultati di ricerca a una pagina di categoria</span><span class="sxs-lookup"><span data-stu-id="677d6-142">Add a search results module to a category page</span></span>

<span data-ttu-id="677d6-143">Per aggiungere un modulo di risultati di ricerca a una pagina di categoria effettua le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="677d6-143">To add a search results module to a category page, follow these steps.</span></span>

1. <span data-ttu-id="677d6-144">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="677d6-144">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="677d6-145">Nella finestra di dialogo **Nuovo modello**, immetti il nome **Risultati di ricerca** e seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="677d6-145">In the **New template** dialog box, enter the name **Search results**, and then select **OK**.</span></span>
1. <span data-ttu-id="677d6-146">Nello slot **Corpo** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="677d6-146">In the **Body** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="677d6-147">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="677d6-147">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="677d6-148">Nello slot **Principale** del modulo **Pagina predefinita**, seleziona i puntini di sospensione (...) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="677d6-148">In the **Main** slot of the **Default Page** module, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="677d6-149">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="677d6-149">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="677d6-150">Nello slot **Contenitore** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="677d6-150">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="677d6-151">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Percorso di navigazione** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="677d6-151">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="677d6-152">Nel riquadro delle proprietà **Percorso di navigazione** immetti il valore **1** per **Numero minimo ricorrenze**.</span><span class="sxs-lookup"><span data-stu-id="677d6-152">In the **Breadcrumb** properties pane, enter the value **1** for **Min Occurs**.</span></span>
1. <span data-ttu-id="677d6-153">Nello slot **Contenitore** seleziona i puntini di sospensione (...), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="677d6-153">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="677d6-154">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Risultati di ricerca** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="677d6-154">In the **Add Module** dialog box, select the **Search results** module, and then select **OK**.</span></span>
1. <span data-ttu-id="677d6-155">Nel riquadro delle proprietà **Risultati di ricerca**, immetti il valore **1** per **Numero minimo ricorrenze** e quindi imposta qualsiasi altra proprietà richiesta per il modulo dei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="677d6-155">In the **Search results** properties pane, enter the value **1** for **Min Occurs**, and then set any other required properties for the search results module.</span></span> <span data-ttu-id="677d6-156">Impostando queste proprietà nel modello, ti assicuri che qualsiasi personalizzazione per una pagina di categoria specifica includerà automaticamente queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="677d6-156">By setting these properties in the template, you ensure that any customizations to a specific category page will automatically include these settings.</span></span>
1. <span data-ttu-id="677d6-157">Selezionare **Fine modifica**, quindi selezionare **Pubblica** per pubblicare il modello.</span><span class="sxs-lookup"><span data-stu-id="677d6-157">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>
1. <span data-ttu-id="677d6-158">Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="677d6-158">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="677d6-159">Nella finestra di dialogo **Scegli un modello**, seleziona il modello **Risultati di ricerca** creato, quindi immetti **Pagina categoria** per **Nome pagina**, e seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="677d6-159">In the **Choose a template** dialog box, select the **Search results** template that you created, enter **Category page** for **Page name**, and then select **OK**.</span></span> <span data-ttu-id="677d6-160">Poiché tutti i valori sono impostati nel modello, la pagina è pronta per essere pubblicata.</span><span class="sxs-lookup"><span data-stu-id="677d6-160">Because all the values are set in the template, the page is ready to be published.</span></span>
1. <span data-ttu-id="677d6-161">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="677d6-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="677d6-162">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="677d6-162">Additional resources</span></span>

[<span data-ttu-id="677d6-163">Panoramica della pagina di destinazione di categoria e della pagina dei risultati di ricerca predefinite</span><span class="sxs-lookup"><span data-stu-id="677d6-163">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="677d6-164">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="677d6-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="677d6-165">Modulo visualizzazione rapida</span><span class="sxs-lookup"><span data-stu-id="677d6-165">Quick view module</span></span>](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]