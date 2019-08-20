---
title: Dimensioni prodotto
description: 'Esistono quattro dimensioni prodotto: Colore, Configurazione, Dimensioni e Stile. Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto. Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.'
author: cvocph
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3391679696c0e1dd84840821480ccbfb544829a6
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863038"
---
# <a name="product-dimensions"></a><span data-ttu-id="5f599-105">Dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="5f599-105">Product dimensions</span></span>

[!include [banner](../includes/banner.md)]

[!include [Retail name](../includes/retail-name.md)]

<span data-ttu-id="5f599-106">Esistono quattro dimensioni prodotto: Colore, Configurazione, Dimensioni e Stile.</span><span class="sxs-lookup"><span data-stu-id="5f599-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="5f599-107">Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="5f599-108">Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="5f599-109">Le dimensioni prodotto sono caratteristiche che servono a identificare una variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="5f599-110">È possibile utilizzare combinazioni di dimensioni prodotto per definire le varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="5f599-111">Per creare una variante prodotto, è necessario definire almeno una dimensione prodotto per una rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>

## <a name="product-variants"></a><span data-ttu-id="5f599-112">Varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="5f599-112">Product variants</span></span>

<span data-ttu-id="5f599-113">Le varianti prodotto vengono indicate anche con il termine articoli.</span><span class="sxs-lookup"><span data-stu-id="5f599-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="5f599-114">Un articolo è un prodotto tangibile, non corrisponde a un servizio.</span><span class="sxs-lookup"><span data-stu-id="5f599-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="5f599-115">È anche possibile definire una rappresentazione generale prodotto con il tipo Servizio.</span><span class="sxs-lookup"><span data-stu-id="5f599-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="5f599-116">Utilizzando il tipo di servizio, è possibile specificare varianti prodotto che includono servizi.</span><span class="sxs-lookup"><span data-stu-id="5f599-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="5f599-117">Ad esempio, è possibile specificare una rappresentazione generale prodotto per le varianti prodotto e consulenza per il lavoro che viene eseguito da consulenti senior e junior.</span><span class="sxs-lookup"><span data-stu-id="5f599-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="5f599-118">Dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="5f599-118">Product dimensions</span></span>
<span data-ttu-id="5f599-119">Le seguenti dimensioni prodotto sono disponibili: Colore, Configurazione, Dimensioni e Stile.</span><span class="sxs-lookup"><span data-stu-id="5f599-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="5f599-120">Una variante prodotto può essere generata in base ai valori delle dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="5f599-121">I valori di dimensioni prodotto, ad esempio Dimensione, Colore e Stile, possono essere creati nelle pagine **Dimensioni**, **Colore** e **Stile**, a cui è possibile accedere dai seguenti percorsi: **Gestione delle informazioni sul prodotto** &gt; **Impostazioni** &gt; **Gruppi di varianti e di dimensione** &gt; **Dimensioni/colori/stili**.</span><span class="sxs-lookup"><span data-stu-id="5f599-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="5f599-122">I valori di dimensione prodotto per la dimensione di configurazione in genere vengono creati utilizzando il configuratore prodotto o il configuratore basato su dimensioni.</span><span class="sxs-lookup"><span data-stu-id="5f599-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="5f599-123">Le dimensioni prodotto possono essere create e gestite anche nella pagina **Dimensioni prodotto** alla quale è possibile accedere dalle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f599-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="5f599-124">Fare clic su **Gestione informazioni sul prodotto** &gt; **Prodotti** &gt; **Rappresentazioni generali prodotto**.</span><span class="sxs-lookup"><span data-stu-id="5f599-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="5f599-125">Nel **riquadro azioni**, fare clic su **Dimensioni prodotto**.</span><span class="sxs-lookup"><span data-stu-id="5f599-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="5f599-126">Fare clic su **Gestione informazioni sul prodotto** &gt; **Prodotti** &gt; **Tutti i prodotti e tutte le rappresentazioni generali prodotto**.</span><span class="sxs-lookup"><span data-stu-id="5f599-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="5f599-127">Selezionare una rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-127">Select a product master.</span></span> <span data-ttu-id="5f599-128">Nel **riquadro azioni**, fare clic su **Dimensioni prodotto**.</span><span class="sxs-lookup"><span data-stu-id="5f599-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="5f599-129">Fare clic su **Gestione informazioni sul prodotto** &gt; **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="5f599-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="5f599-130">Selezionare una rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-130">Select a product master.</span></span> <span data-ttu-id="5f599-131">Nel **riquadro azioni**, fare clic su **Prodotto**.</span><span class="sxs-lookup"><span data-stu-id="5f599-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="5f599-132">Nel gruppo **Rappresentazione generale prodotto**, fare clic su **Dimensioni prodotto**.</span><span class="sxs-lookup"><span data-stu-id="5f599-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="5f599-133">Il numero di varianti che è possibile creare per un articolo è limitato al numero di combinazioni possibili di dimensione prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>

| <span data-ttu-id="5f599-134">**Suggerimento**</span><span class="sxs-lookup"><span data-stu-id="5f599-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5f599-135">Quando, ad esempio, si utilizza un prodotto in una riga ordine, selezionare le dimensioni prodotto per identificare la variante prodotto che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5f599-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="5f599-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f599-136">Example</span></span>
<span data-ttu-id="5f599-137">Una società vende jeans denim.</span><span class="sxs-lookup"><span data-stu-id="5f599-137">A company sells denim jeans.</span></span> <span data-ttu-id="5f599-138">L'articolo, i jeans, utilizza le dimensioni prodotto Colore e Dimensione.</span><span class="sxs-lookup"><span data-stu-id="5f599-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="5f599-139">I jeans vengono venduti in tre diversi colori e sei taglie diverse.</span><span class="sxs-lookup"><span data-stu-id="5f599-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="5f599-140">Colori: Blu, Nero, Marrone Dimensioni: XS, S, M, XL, XXL Non tutte le dimensioni sono disponibili in tutti i tre colori.</span><span class="sxs-lookup"><span data-stu-id="5f599-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="5f599-141">Se tutte le combinazioni fossero disponibili, risulterebbero 18 tipi di jeans diversi.</span><span class="sxs-lookup"><span data-stu-id="5f599-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="5f599-142">In questo esempio, vengono prodotte solo le seguenti nove combinazioni di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="5f599-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="5f599-143">Colore</span><span class="sxs-lookup"><span data-stu-id="5f599-143">Color</span></span> | <span data-ttu-id="5f599-144">Dimensione</span><span class="sxs-lookup"><span data-stu-id="5f599-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="5f599-145">Blu</span><span class="sxs-lookup"><span data-stu-id="5f599-145">Blue</span></span>  | <span data-ttu-id="5f599-146">XS</span><span class="sxs-lookup"><span data-stu-id="5f599-146">XS</span></span>   |
| <span data-ttu-id="5f599-147">Blu</span><span class="sxs-lookup"><span data-stu-id="5f599-147">Blue</span></span>  | <span data-ttu-id="5f599-148">D</span><span class="sxs-lookup"><span data-stu-id="5f599-148">S</span></span>    |
| <span data-ttu-id="5f599-149">Blu</span><span class="sxs-lookup"><span data-stu-id="5f599-149">Blue</span></span>  | <span data-ttu-id="5f599-150">L</span><span class="sxs-lookup"><span data-stu-id="5f599-150">M</span></span>    |
| <span data-ttu-id="5f599-151">Nero</span><span class="sxs-lookup"><span data-stu-id="5f599-151">Black</span></span> | <span data-ttu-id="5f599-152">L</span><span class="sxs-lookup"><span data-stu-id="5f599-152">M</span></span>    |
| <span data-ttu-id="5f599-153">Nero</span><span class="sxs-lookup"><span data-stu-id="5f599-153">Black</span></span> | <span data-ttu-id="5f599-154">L</span><span class="sxs-lookup"><span data-stu-id="5f599-154">L</span></span>    |
| <span data-ttu-id="5f599-155">Nero</span><span class="sxs-lookup"><span data-stu-id="5f599-155">Black</span></span> | <span data-ttu-id="5f599-156">XL</span><span class="sxs-lookup"><span data-stu-id="5f599-156">XL</span></span>   |
| <span data-ttu-id="5f599-157">Marrone</span><span class="sxs-lookup"><span data-stu-id="5f599-157">Brown</span></span> | <span data-ttu-id="5f599-158">L</span><span class="sxs-lookup"><span data-stu-id="5f599-158">L</span></span>    |
| <span data-ttu-id="5f599-159">Marrone</span><span class="sxs-lookup"><span data-stu-id="5f599-159">Brown</span></span> | <span data-ttu-id="5f599-160">XL</span><span class="sxs-lookup"><span data-stu-id="5f599-160">XL</span></span>   |
| <span data-ttu-id="5f599-161">Marrone</span><span class="sxs-lookup"><span data-stu-id="5f599-161">Brown</span></span> | <span data-ttu-id="5f599-162">XXL</span><span class="sxs-lookup"><span data-stu-id="5f599-162">XXL</span></span>  |





