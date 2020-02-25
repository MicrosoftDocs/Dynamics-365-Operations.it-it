---
title: Modulo Lettore video
description: In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025653"
---
# <a name="video-player-module"></a><span data-ttu-id="a477a-103">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="a477a-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a477a-104">In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a477a-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a477a-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a477a-105">Overview</span></span>

<span data-ttu-id="a477a-106">Il modulo Lettore video è utilizzato per supportare la riproduzione di video.</span><span class="sxs-lookup"><span data-stu-id="a477a-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="a477a-107">Può essere aggiunto a qualsiasi pagina, a condizione che il contenuto del video sia caricato e disponibile nel sistema di gestione dei contenuti (CMS).</span><span class="sxs-lookup"><span data-stu-id="a477a-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="a477a-108">Il modulo Lettore video supporta il tipo di file multimediale .mp4.</span><span class="sxs-lookup"><span data-stu-id="a477a-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="a477a-109">Modulo lettore video</span><span class="sxs-lookup"><span data-stu-id="a477a-109">Video player module</span></span>

<span data-ttu-id="a477a-110">Il modulo Lettore video può essere utilizzato per presentare video in un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a477a-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="a477a-111">Supporta tutte le funzionalità di riproduzione, ad esempio riproduci, pausa, modalità a schermo intero, descrizioni audio e sottotitoli.</span><span class="sxs-lookup"><span data-stu-id="a477a-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="a477a-112">Il modulo Lettore video supporta anche la personalizzazione dei sottotitoli per soddisfare gli standard di accessibilità di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a477a-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="a477a-113">Ad esempio, è possibile personalizzare la dimensione dei caratteri e il colore di sfondo.</span><span class="sxs-lookup"><span data-stu-id="a477a-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="a477a-114">Il modulo del lettore video supporta anche tracce audio secondarie.</span><span class="sxs-lookup"><span data-stu-id="a477a-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="a477a-115">Quando un video viene caricato in CMS, è anche possibile caricare una traccia audio secondaria.</span><span class="sxs-lookup"><span data-stu-id="a477a-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="a477a-116">Il modulo del lettore video può quindi riprodurre la traccia audio secondaria se un utente la seleziona.</span><span class="sxs-lookup"><span data-stu-id="a477a-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="a477a-117">Esempi di moduli Lettore video in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="a477a-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="a477a-118">Video di istruzioni in pagine dettagli prodotto o in pagine marketing</span><span class="sxs-lookup"><span data-stu-id="a477a-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="a477a-119">Video promozionali o video su policy in qualsiasi pagina marketing</span><span class="sxs-lookup"><span data-stu-id="a477a-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="a477a-120">Video marketing che presentano le caratteristiche dei prodotti nelle pagine dettagli prodotto o nelle pagine marketing</span><span class="sxs-lookup"><span data-stu-id="a477a-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

### <a name="video-player-module-properties"></a><span data-ttu-id="a477a-121">Proprietà del modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="a477a-121">Video player module properties</span></span>

| <span data-ttu-id="a477a-122">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="a477a-122">Property name</span></span>         | <span data-ttu-id="a477a-123">Valore</span><span class="sxs-lookup"><span data-stu-id="a477a-123">Value</span></span>                               | <span data-ttu-id="a477a-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a477a-124">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="a477a-125">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="a477a-125">Auto play</span></span>             | <span data-ttu-id="a477a-126">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a477a-126">**True** or **False**</span></span>               | <span data-ttu-id="a477a-127">Se il valore è impostato su **True**, il video viene automaticamente riprodotto.</span><span class="sxs-lookup"><span data-stu-id="a477a-127">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="a477a-128">Disattiva audio</span><span class="sxs-lookup"><span data-stu-id="a477a-128">Mute</span></span>                  | <span data-ttu-id="a477a-129">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a477a-129">**True** or **False**</span></span>               | <span data-ttu-id="a477a-130">Se il valore è impostato su **True**, l'audio è disattivato.</span><span class="sxs-lookup"><span data-stu-id="a477a-130">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="a477a-131">Per questo lettore, il valore predefinito è **False**.</span><span class="sxs-lookup"><span data-stu-id="a477a-131">For this player, the default value is **False**.</span></span> <span data-ttu-id="a477a-132">Nel browser Chrome, l'audio dei video riprodotti automaticamente è disattivato per impostazione predefinita e viene attivato solo se l'utente riproduce manualmente il video.</span><span class="sxs-lookup"><span data-stu-id="a477a-132">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="a477a-133">Ciclo</span><span class="sxs-lookup"><span data-stu-id="a477a-133">Loop</span></span>                  | <span data-ttu-id="a477a-134">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a477a-134">**True** or **False**</span></span>               | <span data-ttu-id="a477a-135">Se il valore è impostato su **True**, il video viene ripetuto continuamente.</span><span class="sxs-lookup"><span data-stu-id="a477a-135">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="a477a-136">Multimediale</span><span class="sxs-lookup"><span data-stu-id="a477a-136">Media</span></span>                 | <span data-ttu-id="a477a-137">Percorso e nome del file video</span><span class="sxs-lookup"><span data-stu-id="a477a-137">Video file path and name</span></span> | <span data-ttu-id="a477a-138">Il file video riprodotto dal lettore.</span><span class="sxs-lookup"><span data-stu-id="a477a-138">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="a477a-139">Riproduci a schermo intero</span><span class="sxs-lookup"><span data-stu-id="a477a-139">Play fullscreen</span></span>       | <span data-ttu-id="a477a-140">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a477a-140">**True** or **False**</span></span>               | <span data-ttu-id="a477a-141">Se il valore è impostato su **True**, il video viene riprodotto nella modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="a477a-141">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="a477a-142">Trigger riproduzione o pausa</span><span class="sxs-lookup"><span data-stu-id="a477a-142">Play pause trigger</span></span>    | <span data-ttu-id="a477a-143">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a477a-143">**True** or **False**</span></span>               | <span data-ttu-id="a477a-144">Se il valore è impostato su **True**, un pulsante Riproduci/Pausa è visualizzato nel video.</span><span class="sxs-lookup"><span data-stu-id="a477a-144">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="a477a-145">Controlli lettore video</span><span class="sxs-lookup"><span data-stu-id="a477a-145">Video player controls</span></span> | <span data-ttu-id="a477a-146">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a477a-146">**True** or **False**</span></span>               | <span data-ttu-id="a477a-147">Se il valore è impostato su **True**, tutti i controlli lettore video sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="a477a-147">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="a477a-148">Questi controlli includono i pulsanti Riproduci e Pausa, un indicatore di avanzamento e opzioni per sottotitoli.</span><span class="sxs-lookup"><span data-stu-id="a477a-148">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="a477a-149">Nascondi immagine poster</span><span class="sxs-lookup"><span data-stu-id="a477a-149">Hide poster image</span></span>     | <span data-ttu-id="a477a-150">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="a477a-150">**True** or **False**</span></span>               | <span data-ttu-id="a477a-151">Un video può avere un fotogramma di anteprima.</span><span class="sxs-lookup"><span data-stu-id="a477a-151">A video can have a poster frame.</span></span> <span data-ttu-id="a477a-152">Quando il valore di questa proprietà è **True**, il fotogramma di anteprima è nascosto.</span><span class="sxs-lookup"><span data-stu-id="a477a-152">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="a477a-153">Livello maschera</span><span class="sxs-lookup"><span data-stu-id="a477a-153">Mask level</span></span>            | <span data-ttu-id="a477a-154">Un numero da **0** a **100**</span><span class="sxs-lookup"><span data-stu-id="a477a-154">A number from **0** through **100**</span></span> | <span data-ttu-id="a477a-155">La maschera che viene applicata al video per la modifica dello stile.</span><span class="sxs-lookup"><span data-stu-id="a477a-155">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="a477a-156">Aggiungere un modulo Lettore video a una pagina</span><span class="sxs-lookup"><span data-stu-id="a477a-156">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="a477a-157">Prima di creare un modulo Lettore video, è necessario dapprima caricare un video nella libreria multimediale.</span><span class="sxs-lookup"><span data-stu-id="a477a-157">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="a477a-158">Per aggiungere un modulo Lettore video a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="a477a-158">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="a477a-159">Creare un modello di pagina denominato **Modello lettore video**.</span><span class="sxs-lookup"><span data-stu-id="a477a-159">Create a page template that is named **video player template**.</span></span>
1. <span data-ttu-id="a477a-160">Nello slot **Principale** della pagina predefinita, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="a477a-160">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="a477a-161">Nel modulo contenitore, aggiungere i moduli Lettore video e Lettore video ambiente.</span><span class="sxs-lookup"><span data-stu-id="a477a-161">In the container module, add video player and ambient video player modules.</span></span>
1. <span data-ttu-id="a477a-162">Completare la modifica del modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="a477a-162">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="a477a-163">Utilizzare il modello lettore video creato per creare una pagina denominata **Pagina lettore video**.</span><span class="sxs-lookup"><span data-stu-id="a477a-163">Use the video player template that you created to create a page that is named **video player page**.</span></span>
1. <span data-ttu-id="a477a-164">Nello slot **Principale** della nuova pagina, aggiungere un modulo Lettore video.</span><span class="sxs-lookup"><span data-stu-id="a477a-164">In the **Main** slot of the new page, add a video player module.</span></span>
1. <span data-ttu-id="a477a-165">Nel riquadro delle proprietà per il modulo Lettore video, selezionare **Aggiungi un video**.</span><span class="sxs-lookup"><span data-stu-id="a477a-165">In the property pane for the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="a477a-166">Nella finestra di dialogo **Selettore multimediale**, selezionare un video e quindi **Carica nuovo elemento multimediale**.</span><span class="sxs-lookup"><span data-stu-id="a477a-166">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="a477a-167">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="a477a-167">Save and preview the page.</span></span> <span data-ttu-id="a477a-168">Il modulo video dovrebbe essere visualizzato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="a477a-168">You should see the video module on the page.</span></span> <span data-ttu-id="a477a-169">È possibile modificare ulteriori impostazioni per personalizzare il comportamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="a477a-169">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="a477a-170">Completare la modifica della pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="a477a-170">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a477a-171">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a477a-171">Additional resources</span></span>

[<span data-ttu-id="a477a-172">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="a477a-172">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a477a-173">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="a477a-173">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="a477a-174">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="a477a-174">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="a477a-175">Modulo blocco di testo</span><span class="sxs-lookup"><span data-stu-id="a477a-175">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="a477a-176">Modulo blocco di contenuto</span><span class="sxs-lookup"><span data-stu-id="a477a-176">Content block module</span></span>](add-hero-module.md)
