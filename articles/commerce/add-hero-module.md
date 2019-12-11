---
title: Modulo Hero
description: In questo argomento vengono descritti i moduli Hero e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785394"
---
# <a name="hero-module"></a><span data-ttu-id="e6889-103">Modulo Hero</span><span class="sxs-lookup"><span data-stu-id="e6889-103">Hero module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e6889-104">In questo argomento vengono descritti i moduli Hero e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6889-104">This topic covers hero modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e6889-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e6889-105">Overview</span></span>

<span data-ttu-id="e6889-106">Un modulo Hero è utilizzato per commercializzare prodotti o promozioni mediante una combinazione di immagini e testo.</span><span class="sxs-lookup"><span data-stu-id="e6889-106">A hero module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="e6889-107">Ad esempio, un rivenditore può aggiungere un modulo Hero alla home page di un sito di e-Commerce per promuovere un nuovo prodotto e attirare l'attenzione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="e6889-107">For example, a retailer can add a hero module to the home page of an e-Commerce site to promote a new product and attract the attention of customers.</span></span>

<span data-ttu-id="e6889-108">Un modulo Hero è basato sui dati del sistema di gestione dei contenuti (CMS).</span><span class="sxs-lookup"><span data-stu-id="e6889-108">A hero module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="e6889-109">È un modulo autonomo che non dipende da alcun altro modulo nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e6889-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="e6889-110">Un modulo Hero può essere utilizzato in qualsiasi pagina del sito in cui un rivenditore desidera commercializzare o promuovere qualcosa (ad esempio prodotti, vendite o caratteristiche).</span><span class="sxs-lookup"><span data-stu-id="e6889-110">A hero module can be put on any site page where a retailer wants to market or promote something (for example, products, sales, or features).</span></span>

## <a name="examples-of-hero-module-in-e-commerce"></a><span data-ttu-id="e6889-111">Esempi di modulo Hero in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="e6889-111">Examples of hero module in e-Commerce</span></span>

- <span data-ttu-id="e6889-112">Un modulo Hero può essere utilizzato nella home page di un sito di e-Commerce per mettere in evidenza promozioni e nuovi prodotti.</span><span class="sxs-lookup"><span data-stu-id="e6889-112">A hero module can be used on the home page of an e-Commerce site to highlight promotions and new products.</span></span>
- <span data-ttu-id="e6889-113">Un modulo Hero può essere utilizzato in una pagina dettagli prodotto per visualizzare informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="e6889-113">A hero module can be used on a product details page to showcase product information.</span></span>
- <span data-ttu-id="e6889-114">Molteplici moduli Hero possono essere utilizzati in un modulo Sequenza per mettere in evidenza più prodotti o promozioni.</span><span class="sxs-lookup"><span data-stu-id="e6889-114">Multiple hero modules can be put inside a carousel module to highlight multiple products or promotions.</span></span>

## <a name="hero-module-properties"></a><span data-ttu-id="e6889-115">Proprietà del modulo Hero</span><span class="sxs-lookup"><span data-stu-id="e6889-115">Hero module properties</span></span>

| <span data-ttu-id="e6889-116">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="e6889-116">Property name</span></span>  | <span data-ttu-id="e6889-117">Valori</span><span class="sxs-lookup"><span data-stu-id="e6889-117">Values</span></span> | <span data-ttu-id="e6889-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6889-118">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="e6889-119">Immagine</span><span class="sxs-lookup"><span data-stu-id="e6889-119">Image</span></span>          | <span data-ttu-id="e6889-120">File di immagine</span><span class="sxs-lookup"><span data-stu-id="e6889-120">Image file</span></span> | <span data-ttu-id="e6889-121">Un'immagine può essere utilizzata per presentare un prodotto o una promozione.</span><span class="sxs-lookup"><span data-stu-id="e6889-121">An image can be used to showcase a product or a promotion.</span></span> <span data-ttu-id="e6889-122">Un'immagine può essere caricata nella raccolta di immagini o è possibile utilizzare un'immagine esistente.</span><span class="sxs-lookup"><span data-stu-id="e6889-122">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="e6889-123">Intestazione</span><span class="sxs-lookup"><span data-stu-id="e6889-123">Heading</span></span>        | <span data-ttu-id="e6889-124">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="e6889-124">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="e6889-125">Ogni modulo Hero può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="e6889-125">Every hero module can have a heading.</span></span> <span data-ttu-id="e6889-126">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="e6889-126">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="e6889-127">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="e6889-127">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="e6889-128">Paragrafo</span><span class="sxs-lookup"><span data-stu-id="e6889-128">Paragraph</span></span>      | <span data-ttu-id="e6889-129">Testo di paragrafo</span><span class="sxs-lookup"><span data-stu-id="e6889-129">Paragraph text</span></span> | <span data-ttu-id="e6889-130">I moduli Hero supportano testo di paragrafo in formato RTF.</span><span class="sxs-lookup"><span data-stu-id="e6889-130">Hero modules support paragraph text in rich text format.</span></span> <span data-ttu-id="e6889-131">Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo nonché collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="e6889-131">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="e6889-132">Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo.</span><span class="sxs-lookup"><span data-stu-id="e6889-132">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="e6889-133">Collega</span><span class="sxs-lookup"><span data-stu-id="e6889-133">Link</span></span>           | <span data-ttu-id="e6889-134">Testo del collegamento, URL del collegamento, etichetta ARIA e **Apri collegamento in una nuova scheda**</span><span class="sxs-lookup"><span data-stu-id="e6889-134">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="e6889-135">I moduli Hero supportano uno o più collegamenti "invito all'azione".</span><span class="sxs-lookup"><span data-stu-id="e6889-135">Hero modules support one or more "call to action" links.</span></span> <span data-ttu-id="e6889-136">Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari.</span><span class="sxs-lookup"><span data-stu-id="e6889-136">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="e6889-137">Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="e6889-137">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="e6889-138">I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda.</span><span class="sxs-lookup"><span data-stu-id="e6889-138">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="e6889-139">Posizionamento del testo</span><span class="sxs-lookup"><span data-stu-id="e6889-139">Text placement</span></span> | <span data-ttu-id="e6889-140">**Sinistra in alto**, **Destra in alto**, **Centro in alto**, **Sinistra in basso**, **Destra in basso**, **Centro in basso**, **Centro a sinistra**, **Centro a destra**, **Al centro**.</span><span class="sxs-lookup"><span data-stu-id="e6889-140">**Top Left**, **Top Right**, **Top Center**, **Bottom Left**, **Bottom Right**, **Bottom Center**, **Center Left**, **Center Right**, or **Center Center**</span></span> | <span data-ttu-id="e6889-141">Questa proprietà definisce la posizione dell'immagine rispetto al testo.</span><span class="sxs-lookup"><span data-stu-id="e6889-141">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="e6889-142">Ad esempio, se l'opzione **A destra** è selezionata, l'immagine viene visualizzata a destra del testo.</span><span class="sxs-lookup"><span data-stu-id="e6889-142">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="e6889-143">Tema testo</span><span class="sxs-lookup"><span data-stu-id="e6889-143">Text theme</span></span>     | <span data-ttu-id="e6889-144">**Chiaro** o **Scuro**</span><span class="sxs-lookup"><span data-stu-id="e6889-144">**Light** or **Dark**</span></span> | <span data-ttu-id="e6889-145">Una combinazione di colori può essere definita per il testo, in base all'immagine di sfondo.</span><span class="sxs-lookup"><span data-stu-id="e6889-145">A color scheme can be defined for the text, based on the background image.</span></span> <span data-ttu-id="e6889-146">Ad esempio, se l'immagine ha uno sfondo scuro, un tema chiaro può essere utilizzato per rendere il testo più visibile e per soddisfare i rapporti di contrasto dei colori per scopi di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="e6889-146">For example, if the image has a dark background, a light theme can be applied to make the text more visible and to meet color contrast ratios for accessibility purposes.</span></span> |
| <span data-ttu-id="e6889-147">Gradiente</span><span class="sxs-lookup"><span data-stu-id="e6889-147">Gradient</span></span>       | <span data-ttu-id="e6889-148">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="e6889-148">**True** or **False**</span></span> | <span data-ttu-id="e6889-149">Un gradiente può essere applicato all'immagine per soddisfare i rapporti di contrasto dei colori per scopi di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="e6889-149">A gradient can be applied to the image to meet color contrast ratios for accessibility purposes.</span></span> |

## <a name="add-a-hero-module-to-a-new-page"></a><span data-ttu-id="e6889-150">Aggiungere un modulo Hero a una nuova pagina</span><span class="sxs-lookup"><span data-stu-id="e6889-150">Add a hero module to a new page</span></span>

<span data-ttu-id="e6889-151">Per aggiungere un modulo Hero a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e6889-151">To add a hero module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="e6889-152">Andare a **Modelli** e creare un modello di pagina denominato **Modello hero**.</span><span class="sxs-lookup"><span data-stu-id="e6889-152">Go to **Templates**, and create a page template that is named **hero template**.</span></span>
1. <span data-ttu-id="e6889-153">Nello slot **Principale** della pagina predefinita, aggiungere un modulo Hero.</span><span class="sxs-lookup"><span data-stu-id="e6889-153">In the **Main** slot of the default page, add a hero module.</span></span>
1. <span data-ttu-id="e6889-154">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="e6889-154">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="e6889-155">Utilizzare il modello hero appena creato per creare una pagina denominata **Pagina hero**.</span><span class="sxs-lookup"><span data-stu-id="e6889-155">Use the hero template that you just created to create a page that is named **hero page**.</span></span>
1. <span data-ttu-id="e6889-156">Nello slot **Principale** della pagina predefinita, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="e6889-156">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e6889-157">Nella finestra di dialogo **Aggiungi modulo** sotto **Seleziona moduli**, selezionare il modulo Hero e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6889-157">In the **Add Module** dialog box, under **Select Modules**, select the hero module, and then select **OK**.</span></span>
1. <span data-ttu-id="e6889-158">Nell'albero a sinistra, selezionare il modulo Hero.</span><span class="sxs-lookup"><span data-stu-id="e6889-158">In the outline tree on the left, select the hero module.</span></span>
1. <span data-ttu-id="e6889-159">Nel riquadro delle proprietà a destra, selezionare **Aggiungi immagine**.</span><span class="sxs-lookup"><span data-stu-id="e6889-159">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="e6889-160">Quindi selezionare un'immagine esistente o caricare una nuova immagine.</span><span class="sxs-lookup"><span data-stu-id="e6889-160">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="e6889-161">Selezionare **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="e6889-161">Select **Heading**.</span></span>
1. <span data-ttu-id="e6889-162">Nella finestra di dialogo **Intestazione**, aggiungere il testo dell'intestazione, selezionare il livello di intestazione e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6889-162">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="e6889-163">Sotto **RTF**, aggiungere testo come necessario.</span><span class="sxs-lookup"><span data-stu-id="e6889-163">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="e6889-164">Selezionare **Aggiungi collegamento azione**.</span><span class="sxs-lookup"><span data-stu-id="e6889-164">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="e6889-165">Nella finestra di dialogo **Collegamento azione**, aggiungere il testo, un URL e un'etichetta ARIA per il collegamento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6889-165">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="e6889-166">Salvare la pagina e visualizzare un'anteprima delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="e6889-166">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="e6889-167">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="e6889-167">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6889-168">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e6889-168">Additional resources</span></span>

[<span data-ttu-id="e6889-169">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="e6889-169">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e6889-170">Modulo Avviso</span><span class="sxs-lookup"><span data-stu-id="e6889-170">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="e6889-171">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="e6889-171">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="e6889-172">Modulo Blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="e6889-172">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="e6889-173">Modulo Posizionamento contenuti</span><span class="sxs-lookup"><span data-stu-id="e6889-173">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="e6889-174">Modulo Funzionalità</span><span class="sxs-lookup"><span data-stu-id="e6889-174">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="e6889-175">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="e6889-175">Video player module</span></span>](add-video-player.md)
