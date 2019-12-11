---
title: Modulo Funzionalità
description: In questo argomento vengono descritti i moduli Funzionalità e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785286"
---
# <a name="feature-module"></a><span data-ttu-id="10e5e-103">Modulo Funzionalità</span><span class="sxs-lookup"><span data-stu-id="10e5e-103">Feature module</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="10e5e-104">In questo argomento vengono descritti i moduli Funzionalità e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="10e5e-104">This topic covers feature modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="10e5e-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10e5e-105">Overview</span></span>

<span data-ttu-id="10e5e-106">Un modulo Funzionalità è utilizzato per commercializzare prodotti o promozioni mediante una combinazione di immagini e testo.</span><span class="sxs-lookup"><span data-stu-id="10e5e-106">A feature module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="10e5e-107">Ad esempio, un rivenditore può aggiungere un modulo Funzionalità a una pagina dettagli prodotto per evidenziare le caratteristiche del prodotto.</span><span class="sxs-lookup"><span data-stu-id="10e5e-107">For example, a retailer can add a feature module to a product details page to highlight the features of the product.</span></span>

<span data-ttu-id="10e5e-108">Un modulo Funzionalità è basato sui dati del sistema di gestione dei contenuti (CMS).</span><span class="sxs-lookup"><span data-stu-id="10e5e-108">A feature module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="10e5e-109">È un modulo autonomo che non dipende da alcun altro modulo nella pagina.</span><span class="sxs-lookup"><span data-stu-id="10e5e-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="10e5e-110">Un modulo Funzionalità può essere utilizzato in qualsiasi pagina del sito in cui un rivenditore desidera commercializzare o promuovere qualcosa (ad esempio prodotti, vendite o caratteristiche).</span><span class="sxs-lookup"><span data-stu-id="10e5e-110">A feature module can be put on any site page where a retailer wants to market or promote something (for example products, sales, or features).</span></span>

## <a name="examples-of-feature-modules-in-e-commerce"></a><span data-ttu-id="10e5e-111">Esempi di moduli Funzionalità in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="10e5e-111">Examples of feature modules in e-Commerce</span></span>

<span data-ttu-id="10e5e-112">Un modulo Funzionalità può essere utilizzato nelle pagine seguenti:</span><span class="sxs-lookup"><span data-stu-id="10e5e-112">A feature module can used on the following pages:</span></span>

- <span data-ttu-id="10e5e-113">Una pagina dettagli prodotto, per presentare le caratteristiche del prodotto.</span><span class="sxs-lookup"><span data-stu-id="10e5e-113">A product details page, to showcase product features</span></span>
- <span data-ttu-id="10e5e-114">La home page, per promuovere prodotti.</span><span class="sxs-lookup"><span data-stu-id="10e5e-114">The home page, to promote products</span></span>
- <span data-ttu-id="10e5e-115">Una pagina categoria, per evidenziare una categoria di prodotti.</span><span class="sxs-lookup"><span data-stu-id="10e5e-115">A category page, to highlight a category of products</span></span>

## <a name="feature-module-properties"></a><span data-ttu-id="10e5e-116">Proprietà del modulo Funzionalità</span><span class="sxs-lookup"><span data-stu-id="10e5e-116">Feature module properties</span></span>

| <span data-ttu-id="10e5e-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="10e5e-117">Property name</span></span>     | <span data-ttu-id="10e5e-118">Valori</span><span class="sxs-lookup"><span data-stu-id="10e5e-118">Values</span></span> | <span data-ttu-id="10e5e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10e5e-119">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="10e5e-120">Immagine</span><span class="sxs-lookup"><span data-stu-id="10e5e-120">Image</span></span>             | <span data-ttu-id="10e5e-121">File di immagine</span><span class="sxs-lookup"><span data-stu-id="10e5e-121">Image file</span></span> | <span data-ttu-id="10e5e-122">Un'immagine può essere utilizzata per commercializzare il prodotto o una promozione.</span><span class="sxs-lookup"><span data-stu-id="10e5e-122">An image can be used to market the product or promotion.</span></span> <span data-ttu-id="10e5e-123">Un'immagine può essere caricata nella raccolta di immagini o è possibile utilizzare un'immagine esistente.</span><span class="sxs-lookup"><span data-stu-id="10e5e-123">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="10e5e-124">Intestazione</span><span class="sxs-lookup"><span data-stu-id="10e5e-124">Heading</span></span>           | <span data-ttu-id="10e5e-125">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="10e5e-125">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="10e5e-126">Ogni modulo Funzionalità può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="10e5e-126">Every feature module can have a heading.</span></span> <span data-ttu-id="10e5e-127">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="10e5e-127">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="10e5e-128">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="10e5e-128">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="10e5e-129">Paragrafo</span><span class="sxs-lookup"><span data-stu-id="10e5e-129">Paragraph</span></span>         | <span data-ttu-id="10e5e-130">Testo di paragrafo</span><span class="sxs-lookup"><span data-stu-id="10e5e-130">Paragraph text</span></span> | <span data-ttu-id="10e5e-131">I moduli Funzionalità supportano testo di paragrafo in formato RTF.</span><span class="sxs-lookup"><span data-stu-id="10e5e-131">Feature modules support paragraph text in rich text format.</span></span> <span data-ttu-id="10e5e-132">Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo nonché collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="10e5e-132">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="10e5e-133">Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo.</span><span class="sxs-lookup"><span data-stu-id="10e5e-133">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="10e5e-134">Collega</span><span class="sxs-lookup"><span data-stu-id="10e5e-134">Link</span></span>              | <span data-ttu-id="10e5e-135">Testo del collegamento, URL del collegamento, etichetta ARIA e **Apri collegamento in una nuova scheda**</span><span class="sxs-lookup"><span data-stu-id="10e5e-135">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="10e5e-136">I moduli Funzionalità supportano uno o più collegamenti "invito all'azione".</span><span class="sxs-lookup"><span data-stu-id="10e5e-136">Feature modules support one or more "call to action" links.</span></span> <span data-ttu-id="10e5e-137">Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari.</span><span class="sxs-lookup"><span data-stu-id="10e5e-137">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="10e5e-138">Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="10e5e-138">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="10e5e-139">I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda.</span><span class="sxs-lookup"><span data-stu-id="10e5e-139">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="10e5e-140">Posizionamento immagine</span><span class="sxs-lookup"><span data-stu-id="10e5e-140">Image placement</span></span>   | <span data-ttu-id="10e5e-141">**A destra**, **A sinistra**, **In alto** o **In basso**</span><span class="sxs-lookup"><span data-stu-id="10e5e-141">**Right**, **Left**, **Top**, or **Bottom**</span></span> | <span data-ttu-id="10e5e-142">Questa proprietà definisce la posizione dell'immagine rispetto al testo.</span><span class="sxs-lookup"><span data-stu-id="10e5e-142">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="10e5e-143">Ad esempio, se l'opzione **A destra** è selezionata, l'immagine viene visualizzata a destra del testo.</span><span class="sxs-lookup"><span data-stu-id="10e5e-143">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="10e5e-144">Dimensioni colonna immagine</span><span class="sxs-lookup"><span data-stu-id="10e5e-144">Image column size</span></span> | <span data-ttu-id="10e5e-145">Un valore da **1** a **12**</span><span class="sxs-lookup"><span data-stu-id="10e5e-145">A value from **1** through **12**</span></span> | <span data-ttu-id="10e5e-146">Questa proprietà definisce la dimensione dell'immagine rispetto al testo.</span><span class="sxs-lookup"><span data-stu-id="10e5e-146">This property defines the size of the image relative to the text.</span></span> <span data-ttu-id="10e5e-147">La dimensione è espressa come numero di colonne nella pagina.</span><span class="sxs-lookup"><span data-stu-id="10e5e-147">Size is expressed as a number of columns on the page.</span></span> <span data-ttu-id="10e5e-148">Vi sono 12 colonne in una pagina.</span><span class="sxs-lookup"><span data-stu-id="10e5e-148">There are 12 columns on a page.</span></span> <span data-ttu-id="10e5e-149">Per impostazione predefinita, l'immagine e il testo hanno la stessa dimensione (sei colonne ciascuno).</span><span class="sxs-lookup"><span data-stu-id="10e5e-149">By default, the image and text have equal size (six columns each).</span></span> <span data-ttu-id="10e5e-150">Tuttavia, la dimensione può essere modificata secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="10e5e-150">However, the size can be adjusted as required.</span></span> |

## <a name="add-a-feature-module-to-a-new-page"></a><span data-ttu-id="10e5e-151">Aggiungere un modulo Funzionalità a una nuova pagina</span><span class="sxs-lookup"><span data-stu-id="10e5e-151">Add a feature module to a new page</span></span> 

<span data-ttu-id="10e5e-152">Per aggiungere un modulo Funzionalità a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="10e5e-152">To add a feature module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="10e5e-153">Andare a **Modelli** e creare un modello di pagina denominato **Modello funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-153">Go to **Templates**, and create a page template that is named **feature template**.</span></span>
1. <span data-ttu-id="10e5e-154">Nello slot **Principale** della pagina predefinita, aggiungere un modulo Funzionalità.</span><span class="sxs-lookup"><span data-stu-id="10e5e-154">In the **Main** slot of the default page, add a feature module.</span></span>
1. <span data-ttu-id="10e5e-155">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="10e5e-155">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="10e5e-156">Utilizzare il modello funzionalità appena creato per creare una pagina denominata **Pagina funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-156">Use the feature template that you just created to create a page that is named **feature page**.</span></span>
1. <span data-ttu-id="10e5e-157">Nello slot **Principale** della pagina predefinita, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-157">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="10e5e-158">Nella finestra di dialogo **Aggiungi modulo** sotto **Seleziona moduli**, selezionare un modulo Funzionalità e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-158">In the **Add Module** dialog box, under **Select Modules**, select a feature module, and then select **OK**.</span></span>
1. <span data-ttu-id="10e5e-159">Nell'albero a sinistra, selezionare il modulo Funzionalità.</span><span class="sxs-lookup"><span data-stu-id="10e5e-159">In the outline tree on the left, select the feature module.</span></span>
1. <span data-ttu-id="10e5e-160">Nel riquadro delle proprietà a destra, selezionare **Aggiungi immagine**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-160">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="10e5e-161">Quindi selezionare un'immagine esistente o caricare una nuova immagine.</span><span class="sxs-lookup"><span data-stu-id="10e5e-161">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="10e5e-162">Selezionare **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-162">Select **Heading**.</span></span>
1. <span data-ttu-id="10e5e-163">Nella finestra di dialogo **Intestazione**, aggiungere il testo dell'intestazione, selezionare il livello di intestazione e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-163">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="10e5e-164">Sotto **RTF**, aggiungere testo come necessario.</span><span class="sxs-lookup"><span data-stu-id="10e5e-164">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="10e5e-165">Selezionare **Aggiungi collegamento azione**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-165">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="10e5e-166">Nella finestra di dialogo **Collegamento azione**, aggiungere il testo, un URL e un'etichetta ARIA per il collegamento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="10e5e-166">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="10e5e-167">Salvare la pagina e visualizzare un'anteprima delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="10e5e-167">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="10e5e-168">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="10e5e-168">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="10e5e-169">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="10e5e-169">Additional resources</span></span>

[<span data-ttu-id="10e5e-170">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="10e5e-170">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="10e5e-171">Modulo Avviso</span><span class="sxs-lookup"><span data-stu-id="10e5e-171">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="10e5e-172">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="10e5e-172">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="10e5e-173">Modulo Blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="10e5e-173">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="10e5e-174">Modulo Posizionamento contenuti</span><span class="sxs-lookup"><span data-stu-id="10e5e-174">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="10e5e-175">Modulo Hero</span><span class="sxs-lookup"><span data-stu-id="10e5e-175">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="10e5e-176">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="10e5e-176">Video player module</span></span>](add-video-player.md)
