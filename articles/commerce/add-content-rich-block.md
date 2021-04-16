---
title: Modulo Blocco di testo
description: In questo argomento vengono descritti i moduli Blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7dbeb8785641960cc2680335436aea10775759d3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797769"
---
# <a name="text-block-module"></a><span data-ttu-id="73729-103">Modulo blocco testo</span><span class="sxs-lookup"><span data-stu-id="73729-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="73729-104">In questo argomento vengono descritti i moduli Blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="73729-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="73729-105">Un modulo Blocco di testo è un modulo utilizzato per aggiungere contenuto testuale.</span><span class="sxs-lookup"><span data-stu-id="73729-105">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="73729-106">Questo contenuto può essere informativo o promozionale.</span><span class="sxs-lookup"><span data-stu-id="73729-106">This content can be informational or promotional.</span></span>

<span data-ttu-id="73729-107">I moduli Blocco di testo sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="73729-107">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="73729-108">Sono moduli autonomi che non dipendono dal contesto della pagina o da qualsiasi altro modulo.</span><span class="sxs-lookup"><span data-stu-id="73729-108">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="73729-109">Esempi di moduli Blocco di testo in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="73729-109">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="73729-110">I moduli Blocco di testo possono essere utilizzati nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="73729-110">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="73729-111">Per visualizzare caratteristiche dei prodotti in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="73729-111">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="73729-112">Per scopi informativi in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="73729-112">For informational purposes on any page.</span></span> <span data-ttu-id="73729-113">Ad esempio, possono spiegare i vantaggi dei programmi fedeltà, descrivere le condizioni di spedizione e reso, rispondere alle domande frequenti oppure fornire contenuto "chi siamo".</span><span class="sxs-lookup"><span data-stu-id="73729-113">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="73729-114">Per aggiungere messaggi personalizzati in una pagina dettagli prodotto</span><span class="sxs-lookup"><span data-stu-id="73729-114">To add custom messages on a product details page.</span></span> <span data-ttu-id="73729-115">(ad esempio, "Spedizione gratuita per ordini superiori a 50 €").</span><span class="sxs-lookup"><span data-stu-id="73729-115">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="73729-116">Per le dichiarazioni di non responsabilità e le informazioni di contatto nelle pagine dettagli prodotto, carrello, checkout e altre pagine (ad esempio "Spedizioni e resi sono soggetti alle politiche del punto vendita").</span><span class="sxs-lookup"><span data-stu-id="73729-116">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="73729-117">L'immagine seguente mostra un esempio di modulo Blocco di testo utilizzato in una home page.</span><span class="sxs-lookup"><span data-stu-id="73729-117">The following image shows an example of a text block module that is used on a home page.</span></span>

![Esempio di un modulo Blocco di testo](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="73729-119">Proprietà dei moduli Blocco di testo</span><span class="sxs-lookup"><span data-stu-id="73729-119">Text block module properties</span></span>

| <span data-ttu-id="73729-120">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="73729-120">Property name</span></span>     | <span data-ttu-id="73729-121">Valore</span><span class="sxs-lookup"><span data-stu-id="73729-121">Value</span></span>                                            | <span data-ttu-id="73729-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73729-122">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="73729-123">RTF</span><span class="sxs-lookup"><span data-stu-id="73729-123">Rich text</span></span>         | <span data-ttu-id="73729-124">RTF</span><span class="sxs-lookup"><span data-stu-id="73729-124">Rich text</span></span>                                        | <span data-ttu-id="73729-125">Testo di paragrafo.</span><span class="sxs-lookup"><span data-stu-id="73729-125">Paragraph text.</span></span> <span data-ttu-id="73729-126">Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo.</span><span class="sxs-lookup"><span data-stu-id="73729-126">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="73729-127">Nome classe personalizzato</span><span class="sxs-lookup"><span data-stu-id="73729-127">Custom class name</span></span> | <span data-ttu-id="73729-128">Il nome di una classe Cascading Style Sheets (CSS)</span><span class="sxs-lookup"><span data-stu-id="73729-128">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="73729-129">Il nome di una classe CSS personalizzata fornita da uno sviluppatore per formattare questo modulo.</span><span class="sxs-lookup"><span data-stu-id="73729-129">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="73729-130">Il nome della classe deve essere definito nel pacchetto di temi.</span><span class="sxs-lookup"><span data-stu-id="73729-130">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="73729-131">Dimensione carattere</span><span class="sxs-lookup"><span data-stu-id="73729-131">Font size</span></span>         | <span data-ttu-id="73729-132">**Piccolo**, **Medio**, **Grande** o **Grandissimo**</span><span class="sxs-lookup"><span data-stu-id="73729-132">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="73729-133">La dimensione del carattere del contenuto.</span><span class="sxs-lookup"><span data-stu-id="73729-133">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="73729-134">Aggiungere un modulo Blocco di testo a una pagina</span><span class="sxs-lookup"><span data-stu-id="73729-134">Add a text block module to a page</span></span>

<span data-ttu-id="73729-135">Per aggiungere un modulo Blocco di testo a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="73729-135">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="73729-136">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="73729-136">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="73729-137">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello contenuto**.</span><span class="sxs-lookup"><span data-stu-id="73729-137">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="73729-138">Nello slot **Corpo** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="73729-138">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73729-139">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="73729-139">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="73729-140">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="73729-140">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="73729-141">Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="73729-141">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="73729-142">Nella finestra di dialogo **Scegli un modello**, selezionare **Modello contenuto**.</span><span class="sxs-lookup"><span data-stu-id="73729-142">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="73729-143">Sotto **Nome pagina**, Immettere **Pagina contenuto** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="73729-143">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="73729-144">Nello slot **Principale** della nuova pagina, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="73729-144">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73729-145">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="73729-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="73729-146">Nel riquadro delle proprietà del modulo Contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="73729-146">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="73729-147">Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="73729-147">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="73729-148">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Blocco di testo** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="73729-148">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="73729-149">Nel riquadro delle proprietà del modulo Blocco di testo, aggiungere testo al campo **RTF**.</span><span class="sxs-lookup"><span data-stu-id="73729-149">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="73729-150">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="73729-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="73729-151">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="73729-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73729-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="73729-152">Additional resources</span></span>

[<span data-ttu-id="73729-153">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="73729-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="73729-154">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="73729-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="73729-155">Modulo sequenza</span><span class="sxs-lookup"><span data-stu-id="73729-155">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="73729-156">Modulo blocco contenuto</span><span class="sxs-lookup"><span data-stu-id="73729-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="73729-157">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="73729-157">Video player module</span></span>](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]