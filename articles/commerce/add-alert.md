---
title: Modulo banner promozionale
description: In questo argomento vengono descritti i moduli banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025622"
---
# <a name="promo-banner-module"></a><span data-ttu-id="d60db-103">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="d60db-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d60db-104">In questo argomento vengono descritti i moduli banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d60db-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d60db-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d60db-105">Overview</span></span>

<span data-ttu-id="d60db-106">I moduli banner promozionale sono utilizzati per visualizzare messaggi informativi incorporati in una pagina.</span><span class="sxs-lookup"><span data-stu-id="d60db-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="d60db-107">Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="d60db-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="d60db-108">I moduli banner promozionale supportano un messaggio di testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="d60db-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="d60db-109">Se vengono aggiunti più messaggi a un modulo banner promozionale, questo diventa un banner sequenza rotante che consente ai clienti di scorrere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="d60db-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="d60db-110">I moduli banner promozionale sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="d60db-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="d60db-111">Esempi di utilizzo di banner promozionali in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="d60db-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="d60db-112">I banner promozionali possono essere utilizzati nell'intestazione del sito per mostrare promozioni o messaggi in tutto il sito, come negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d60db-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="d60db-113">"La vendita annuale termina tra 10 giorni"</span><span class="sxs-lookup"><span data-stu-id="d60db-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="d60db-114">"Grandi risparmi con la vendita di articoli scolastici.</span><span class="sxs-lookup"><span data-stu-id="d60db-114">"Save big with back to school sale.</span></span> <span data-ttu-id="d60db-115">Acquista ora".</span><span class="sxs-lookup"><span data-stu-id="d60db-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="d60db-116">Proprietà dei moduli banner promozionale</span><span class="sxs-lookup"><span data-stu-id="d60db-116">Promo banner module properties</span></span>

| <span data-ttu-id="d60db-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="d60db-117">Property name</span></span>             | <span data-ttu-id="d60db-118">Value</span><span class="sxs-lookup"><span data-stu-id="d60db-118">Value</span></span>                              | <span data-ttu-id="d60db-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d60db-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="d60db-120">Messaggi banner</span><span class="sxs-lookup"><span data-stu-id="d60db-120">Banner messages</span></span>           | <span data-ttu-id="d60db-121">Testo e collegamenti</span><span class="sxs-lookup"><span data-stu-id="d60db-121">Text and links</span></span>                     | <span data-ttu-id="d60db-122">Una matrice di testo e collegamenti.</span><span class="sxs-lookup"><span data-stu-id="d60db-122">An array of text and links.</span></span> |
| <span data-ttu-id="d60db-123">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="d60db-123">Autoplay</span></span>                  | <span data-ttu-id="d60db-124">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="d60db-124">**True** or **False**</span></span>              | <span data-ttu-id="d60db-125">Un valore che indica se i messaggi vengono automaticamente passati in rassegna, se sono configurati più messaggi.</span><span class="sxs-lookup"><span data-stu-id="d60db-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="d60db-126">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="d60db-126">Slide transition interval</span></span> | <span data-ttu-id="d60db-127">Un numero di millisecondi (ms)</span><span class="sxs-lookup"><span data-stu-id="d60db-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="d60db-128">L'intervallo utilizzato per scorrere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="d60db-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="d60db-129">Consenti chiusura</span><span class="sxs-lookup"><span data-stu-id="d60db-129">Allow dismiss</span></span>             | <span data-ttu-id="d60db-130">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="d60db-130">**True** or **False**</span></span>              | <span data-ttu-id="d60db-131">Se il valore è impostato su **True**, i clienti possono chiudere l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d60db-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="d60db-132">Mostra flipper sequenza</span><span class="sxs-lookup"><span data-stu-id="d60db-132">Show carousel flipper</span></span>     | <span data-ttu-id="d60db-133">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="d60db-133">**True** or **False**</span></span>              | <span data-ttu-id="d60db-134">Un valore che indica se i flipper della sequenza devono essere visualizzati, di modo che i clienti possano scorrere manualmente più elementi del banner.</span><span class="sxs-lookup"><span data-stu-id="d60db-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="d60db-135">Allineamento testo</span><span class="sxs-lookup"><span data-stu-id="d60db-135">Text alignment</span></span>            | <span data-ttu-id="d60db-136">**A destra**, **A sinistra** o **Al centro**</span><span class="sxs-lookup"><span data-stu-id="d60db-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="d60db-137">L'allineamento del testo nel modulo banner promozionale.</span><span class="sxs-lookup"><span data-stu-id="d60db-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="d60db-138">Collega</span><span class="sxs-lookup"><span data-stu-id="d60db-138">Link</span></span>                      | <span data-ttu-id="d60db-139">URL A</span><span class="sxs-lookup"><span data-stu-id="d60db-139">A URL</span></span>                              | <span data-ttu-id="d60db-140">L'URL di un collegamento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d60db-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="d60db-141">Aggiungere un modulo banner promozionale a una pagina</span><span class="sxs-lookup"><span data-stu-id="d60db-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="d60db-142">Per aggiungere un modulo banner promozionale a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d60db-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="d60db-143">Creare un modello pagina denominato **Modello banner promozionale**.</span><span class="sxs-lookup"><span data-stu-id="d60db-143">Create a page template that is named **Promo banner template**.</span></span>
1. <span data-ttu-id="d60db-144">Sotto **Struttura pagina** , aggiungere un modulo **Pagina predefinita** allo slot **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="d60db-144">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="d60db-145">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="d60db-145">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="d60db-146">Utilizzare il modello appena creato per creare una pagina denominata **Pagina banner promozionale**.</span><span class="sxs-lookup"><span data-stu-id="d60db-146">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="d60db-147">Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d60db-147">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="d60db-148">Nel riquadro a destra, impostare il valore **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="d60db-148">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="d60db-149">Sotto **Struttura pagina**, aggiungere un modulo banner promozionale al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d60db-149">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="d60db-150">Nelle impostazioni per il modulo banner, aggiungere uno o più messaggi banner.</span><span class="sxs-lookup"><span data-stu-id="d60db-150">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="d60db-151">Ogni messaggio può avere del testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="d60db-151">Each message can have text together with a link.</span></span> <span data-ttu-id="d60db-152">È possibile modificare le altre proprietà per personalizzare ulteriormente il modulo.</span><span class="sxs-lookup"><span data-stu-id="d60db-152">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="d60db-153">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="d60db-153">Save and preview the page.</span></span> <span data-ttu-id="d60db-154">Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso che mostra il testo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="d60db-154">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="d60db-155">Completare la modifica della pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="d60db-155">Finish editing the page, and publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="d60db-156">Un banner promozionale viene in genere utilizzato nello slot dell'intestazione di pagina o in uno slot del sottotitolo.</span><span class="sxs-lookup"><span data-stu-id="d60db-156">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="d60db-157">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d60db-157">Additional resources</span></span>

[<span data-ttu-id="d60db-158">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="d60db-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d60db-159">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="d60db-159">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="d60db-160">Modulo blocco di testo</span><span class="sxs-lookup"><span data-stu-id="d60db-160">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="d60db-161">modulo blocco di contenuto</span><span class="sxs-lookup"><span data-stu-id="d60db-161">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="d60db-162">Modulo lettore video</span><span class="sxs-lookup"><span data-stu-id="d60db-162">Video player module</span></span>](add-video-player.md)
