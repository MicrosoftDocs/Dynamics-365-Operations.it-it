---
title: Modulo iFrame
description: In questo argomento viene descritto il modulo iFrame e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 4afd8f60938c99d1981be1625ef28f91d9e4bb4c
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665398"
---
# <a name="iframe-module"></a><span data-ttu-id="0fbe3-103">Modulo iFrame</span><span class="sxs-lookup"><span data-stu-id="0fbe3-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0fbe3-104">In questo argomento viene descritto il modulo iFrame e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0fbe3-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0fbe3-105">Overview</span></span>

<span data-ttu-id="0fbe3-106">Un modulo iFrame fornisce un iFrame (frame in linea) che ospita contenuti esterni su un sito.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="0fbe3-107">Ad esempio, può essere utilizzato per ospitare un video YouTube o un visualizzatore di file PDF in qualsiasi pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="0fbe3-108">Un modulo iFrame richiede un URL di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="0fbe3-109">Ospita quindi il contenuto della pagina di destinazione all'interno di un elemento **iFrame** HTML.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="0fbe3-110">Gli URL esterni devono essere presenti nell'elenco dei consentiti in base alle direttive sui criteri di sicurezza dei contenuti (CSP) del sito.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-110">External URLs must be on the allow list per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="0fbe3-111">Per i contenuti iFrame, gli URL dovrebbero essere consentiti utilizzando la direttiva **frame-ancestor**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="0fbe3-112">Per altre informazioni, vedere [Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="0fbe3-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0fbe3-113">Il modulo iFrame è disponibile in Dynamics 365 Commerce versione 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-113">The iframe module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="0fbe3-114">L'immagine seguente mostra esempi di moduli iFrame che presentano video esterni sulle pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-114">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Esempio di moduli iFrame che presentano video esterni](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="0fbe3-116">Proprietà del modulo iFrame</span><span class="sxs-lookup"><span data-stu-id="0fbe3-116">Iframe module properties</span></span>

| <span data-ttu-id="0fbe3-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="0fbe3-117">Property name</span></span>             | <span data-ttu-id="0fbe3-118">Valore</span><span class="sxs-lookup"><span data-stu-id="0fbe3-118">Value</span></span>                 | <span data-ttu-id="0fbe3-119">descrizione</span><span class="sxs-lookup"><span data-stu-id="0fbe3-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="0fbe3-120">Intestazione</span><span class="sxs-lookup"><span data-stu-id="0fbe3-120">Heading</span></span> | <span data-ttu-id="0fbe3-121">Testo</span><span class="sxs-lookup"><span data-stu-id="0fbe3-121">Text</span></span> | <span data-ttu-id="0fbe3-122">L'intestazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-122">The heading for the module.</span></span> |
| <span data-ttu-id="0fbe3-123">URL destinazione</span><span class="sxs-lookup"><span data-stu-id="0fbe3-123">Target URL</span></span> | <span data-ttu-id="0fbe3-124">URL</span><span class="sxs-lookup"><span data-stu-id="0fbe3-124">URL</span></span> | <span data-ttu-id="0fbe3-125">L'URL ospitato nel modulo.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-125">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="0fbe3-126">Altezza</span><span class="sxs-lookup"><span data-stu-id="0fbe3-126">Height</span></span> | <span data-ttu-id="0fbe3-127">Numero o percentuale</span><span class="sxs-lookup"><span data-stu-id="0fbe3-127">Number or percentage</span></span> | <span data-ttu-id="0fbe3-128">L'altezza del modulo, in pixel o in percentuale.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-128">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="0fbe3-129">Ad esempio, il valore **100** sarà trattato come un numero di pixel e il valore **100%** sarà trattato come una percentuale.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-129">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="0fbe3-130">Aria-label</span><span class="sxs-lookup"><span data-stu-id="0fbe3-130">Aria label</span></span> | <span data-ttu-id="0fbe3-131">Testo</span><span class="sxs-lookup"><span data-stu-id="0fbe3-131">Text</span></span> | <span data-ttu-id="0fbe3-132">Un'etichetta ARIA (Accessible Rich Internet Applications) può essere definita per scopi di accessibilità..</span><span class="sxs-lookup"><span data-stu-id="0fbe3-132">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="0fbe3-133">Aggiungere un modulo iFrame a una pagina</span><span class="sxs-lookup"><span data-stu-id="0fbe3-133">Add an iframe module to a page</span></span>

<span data-ttu-id="0fbe3-134">Per aggiungere un modulo iFrame a una pagina per mostrare un video esterno, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-134">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="0fbe3-135">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-135">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="0fbe3-136">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello di marketing**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-136">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="0fbe3-137">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-137">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="0fbe3-138">Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-138">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="0fbe3-139">Nella finestra di dialogo **Scegli un modello**, selezionare il modello **Modello di marketing**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-139">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="0fbe3-140">Sotto **Nome pagina**, immettere **Pagina di marketing** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-140">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="0fbe3-141">Nello slot **Principale** della nuova pagina, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-141">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0fbe3-142">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-142">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="0fbe3-143">Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-143">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="0fbe3-144">Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-144">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0fbe3-145">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **iFrame** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-145">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="0fbe3-146">Nel riquadro delle proprietà del modulo, impostare il valore **URL di destinazione** su un URL esterno per un video.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-146">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="0fbe3-147">Impostare altre proprietà, ad esempio **Intestazione** e **Altezza**, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-147">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="0fbe3-148">Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-148">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="0fbe3-149">Andare alla pagina di marketing sul sito.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-149">Go to the marketing page on your site.</span></span> <span data-ttu-id="0fbe3-150">Il rendering del video nel modulo iFrame dovrebbe essere visibile.</span><span class="sxs-lookup"><span data-stu-id="0fbe3-150">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="0fbe3-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0fbe3-151">Additional resources</span></span>

[<span data-ttu-id="0fbe3-152">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="0fbe3-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0fbe3-153">Gestire i criteri di sicurezza del contenuto (CSP)</span><span class="sxs-lookup"><span data-stu-id="0fbe3-153">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
