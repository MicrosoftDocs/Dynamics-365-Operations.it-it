---
title: Modulo visualizzazione rapida
description: In questo argomento vengono descritti i moduli visualizzazione rapida e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d7e88163fd9b8dc4f5636ed29e2c4248aece52bf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792173"
---
# <a name="quick-view-module"></a><span data-ttu-id="53724-103">Modulo di visualizzazione rapida</span><span class="sxs-lookup"><span data-stu-id="53724-103">Quick view module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="53724-104">In questo argomento vengono descritti i moduli visualizzazione rapida e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="53724-104">This topic covers quick view modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="53724-105">Il modulo di visualizzazione rapida consente agli utenti di visualizzare rapidamente le informazioni sui prodotti quando esplorano i prodotti in una pagina di elenco e di aggiungere uno o più prodotti al carrello dalla pagina di elenco, senza dover andare alla pagina dei dettagli del prodotto (PDP).</span><span class="sxs-lookup"><span data-stu-id="53724-105">The quick view module lets users quickly view product information when they browse products on a list page, and add one or more products to the cart from the list page, without having to go to the product details page (PDP).</span></span> <span data-ttu-id="53724-106">Il modulo di visualizzazione rapida fornisce una panoramica delle informazioni sul prodotto richieste dagli utenti per prendere la decisione "aggiungi al carrello".</span><span class="sxs-lookup"><span data-stu-id="53724-106">The quick view module provides an overview of the product information that users require to make an "add to cart" decision.</span></span> <span data-ttu-id="53724-107">Fornisce inoltre un collegamento al PDP, in modo che gli utenti possano visualizzare ulteriori dettagli del prodotto e opzioni di acquisto.</span><span class="sxs-lookup"><span data-stu-id="53724-107">It also provides a link to the PDP, so that users can view additional product details and purchase options.</span></span>

<span data-ttu-id="53724-108">Il modulo di visualizzazione rapida è supportato dai moduli [raccolta di prodotti](product-collection-module-overview.md) e [risultati di ricerca](search-result-module.md).</span><span class="sxs-lookup"><span data-stu-id="53724-108">The quick view module is supported by the [product collection](product-collection-module-overview.md) and [search results](search-result-module.md) modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53724-109">Il modulo di visualizzazione rapida è disponibile a partire dalla versione Commerce 10.0.17.</span><span class="sxs-lookup"><span data-stu-id="53724-109">The quick view module is available as of the Commerce version 10.0.17 release.</span></span>

<span data-ttu-id="53724-110">L'immagine seguente mostra un esempio di modulo di visualizzazione rapida in una pagina elenco di prodotti.</span><span class="sxs-lookup"><span data-stu-id="53724-110">The following illustration shows an example of a quick view module on a product list page.</span></span>

![Esempio di un modulo di visualizzazione rapida su una pagina elenco di prodotti](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a><span data-ttu-id="53724-112">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="53724-112">Module properties</span></span>

<span data-ttu-id="53724-113">Il modulo di visualizzazione rapida supporta alcune delle stesse funzioni del modulo Buy box.</span><span class="sxs-lookup"><span data-stu-id="53724-113">The quick view module supports some of the same functions as the buy box module.</span></span> <span data-ttu-id="53724-114">Pertanto, le proprietà di un modulo di visualizzazione rapida assomigliano alle proprietà di un modulo buy box.</span><span class="sxs-lookup"><span data-stu-id="53724-114">Therefore, the properties of a quick view module resemble the properties of a buy box module.</span></span>

| <span data-ttu-id="53724-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="53724-115">Property</span></span> | <span data-ttu-id="53724-116">Valori</span><span class="sxs-lookup"><span data-stu-id="53724-116">Values</span></span> | <span data-ttu-id="53724-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53724-117">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="53724-118">Tag intestazione</span><span class="sxs-lookup"><span data-stu-id="53724-118">Heading tag</span></span> | <span data-ttu-id="53724-119">**H1**, **H2**, **H3**, **H4**, **H5** o **H6**</span><span class="sxs-lookup"><span data-stu-id="53724-119">**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**</span></span> | <span data-ttu-id="53724-120">Questa proprietà definisce il tag di intestazione per il titolo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="53724-120">This property defines the heading tag for the product title.</span></span> <span data-ttu-id="53724-121">Se il modulo visualizzazione rapida si trova nella parte superiore della pagina, questa proprietà deve essere impostata su **H1** per soddisfare gli standard di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="53724-121">If the quick view module is at the top of the page, this property should be set to **H1** to meet accessibility standards.</span></span> |
| <span data-ttu-id="53724-122">Consenti prezzo personalizzato</span><span class="sxs-lookup"><span data-stu-id="53724-122">Allow custom price</span></span> | <span data-ttu-id="53724-123">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="53724-123">**True** or **False**</span></span> | <span data-ttu-id="53724-124">Se questa proprietà è impostata su **True**, l'utente può inserire un prezzo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="53724-124">If this property is set to **True**, the user can enter a custom price.</span></span> |
| <span data-ttu-id="53724-125">Prezzo minimo</span><span class="sxs-lookup"><span data-stu-id="53724-125">Minimum price</span></span> | <span data-ttu-id="53724-126">Integer</span><span class="sxs-lookup"><span data-stu-id="53724-126">Integer</span></span> | <span data-ttu-id="53724-127">Questa proprietà è applicabile solo se la proprietà **Consenti prezzo personalizzato** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="53724-127">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="53724-128">Definisce il prezzo minimo che l'utente può inserire (ad esempio, $ 1).</span><span class="sxs-lookup"><span data-stu-id="53724-128">It defines the minimum price that the user can enter (for example, $1).</span></span> |
| <span data-ttu-id="53724-129">Prezzo massimo</span><span class="sxs-lookup"><span data-stu-id="53724-129">Maximum price</span></span> | <span data-ttu-id="53724-130">Integer</span><span class="sxs-lookup"><span data-stu-id="53724-130">Integer</span></span> | <span data-ttu-id="53724-131">Questa proprietà è applicabile solo se la proprietà **Consenti prezzo personalizzato** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="53724-131">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="53724-132">Definisce il prezzo massimo che l'utente può inserire (ad esempio, $ 1.000).</span><span class="sxs-lookup"><span data-stu-id="53724-132">It defines the maximum price that the user can enter (for example, $1,000).</span></span> |

## <a name="commerce-site-builder-settings"></a><span data-ttu-id="53724-133">Impostazioni di Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="53724-133">Commerce site builder settings</span></span>

<span data-ttu-id="53724-134">Come il modulo Buy box, il modulo di visualizzazione rapida rispetta le impostazioni in **Impostazioni sito \> Estensioni \> Aggiungi prodotto al carrello**.</span><span class="sxs-lookup"><span data-stu-id="53724-134">Like the buy box module, the quick view module respects the settings at **Site Settings \> Extensions \> Add product to cart**.</span></span> <span data-ttu-id="53724-135">Comunque, l'impostazione **Vai a pagina carrello** viene ignorata, perché non è coerente con lo scopo del modulo di visualizzazione rapida, che è quello di consentire agli utenti di sfogliare più prodotti in una pagina di elenco e aggiungerli al carrello senza uscire dalla pagina elenco.</span><span class="sxs-lookup"><span data-stu-id="53724-135">However, the **Navigate to cart page** setting is ignored, because it's inconsistent with the purpose of the quick view module, which is to enable users to browse multiple products on a list page and add them to the cart without moving away from the list page.</span></span>

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a><span data-ttu-id="53724-136">Aggiungere un modulo visualizzazione rapida a un modulo di raccolta prodotti</span><span class="sxs-lookup"><span data-stu-id="53724-136">Add a quick view module to a product collection module</span></span>

<span data-ttu-id="53724-137">Un modulo di visualizzazione rapida può essere aggiunto ai moduli raccolta di prodotti e risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="53724-137">A quick view module can be added to the product collection and search results modules.</span></span>

<span data-ttu-id="53724-138">Per aggiungere un modulo visualizzazione prodotti a un modulo di raccolta prodotti in Creazione di siti Web di Commerce, effettua le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="53724-138">To add a quick view module to a product collection module in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="53724-139">Vai a **Pagine** e seleziona la home page per il sito Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="53724-139">Go to **Pages**, and then select the home page for the Fabrikam site.</span></span>
1. <span data-ttu-id="53724-140">Vai un modulo di **raccolta prodotti** nella home page, seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="53724-140">Go to any **Product Collection** module on the homepage, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="53724-141">Nella finestra di dialogo **Aggiungi modulo** seleziona il modulo **Visualizzazione rapida** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="53724-141">In the **Add Module** dialog box, select the **Quick View** module, and then select **OK**.</span></span>
1. <span data-ttu-id="53724-142">Nel riquadro delle proprietà del modulo **visualizzazione rapida** seleziona **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="53724-142">In the properties pane of the **Quick View** module, select **Heading**.</span></span> <span data-ttu-id="53724-143">Nella finestra di dialogo **Intestazione** imposta il campo **Livello di intestazione** su **H2** e quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="53724-143">In the **Heading** dialog box, set the **Heading Level** field to **H2**, and then select **OK**.</span></span>
1. <span data-ttu-id="53724-144">Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="53724-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="53724-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="53724-145">Additional resources</span></span>

[<span data-ttu-id="53724-146">Panoramica della libreria moduli</span><span class="sxs-lookup"><span data-stu-id="53724-146">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="53724-147">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="53724-147">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="53724-148">Modulo Raccolta prodotti</span><span class="sxs-lookup"><span data-stu-id="53724-148">Product collection module</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="53724-149">Modulo dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="53724-149">Search results module</span></span>](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
