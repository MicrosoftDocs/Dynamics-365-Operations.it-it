---
title: Modulo banner promozionale
description: In questo argomento vengono descritti i moduli banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 12cabbf0b8d9f337f15a8cd6cb1f2a85100b75f7
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269776"
---
# <a name="promo-banner-module"></a><span data-ttu-id="8a27e-103">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="8a27e-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8a27e-104">In questo argomento vengono descritti i moduli banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a27e-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8a27e-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8a27e-105">Overview</span></span>

<span data-ttu-id="8a27e-106">I moduli banner promozionale sono utilizzati per visualizzare messaggi informativi incorporati in una pagina.</span><span class="sxs-lookup"><span data-stu-id="8a27e-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="8a27e-107">Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a27e-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="8a27e-108">I moduli banner promozionale supportano un messaggio di testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="8a27e-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="8a27e-109">Se vengono aggiunti più messaggi a un modulo banner promozionale, questo diventa un banner sequenza rotante che consente ai clienti di scorrere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8a27e-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="8a27e-110">I moduli banner promozionale sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="8a27e-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="8a27e-111">Esempi di utilizzo di banner promozionali in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="8a27e-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="8a27e-112">I banner promozionali possono essere utilizzati nell'intestazione del sito per mostrare promozioni o messaggi in tutto il sito, come negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a27e-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="8a27e-113">"La vendita annuale termina tra 10 giorni"</span><span class="sxs-lookup"><span data-stu-id="8a27e-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="8a27e-114">"Grandi risparmi con la vendita di articoli scolastici.</span><span class="sxs-lookup"><span data-stu-id="8a27e-114">"Save big with back to school sale.</span></span> <span data-ttu-id="8a27e-115">Acquista ora".</span><span class="sxs-lookup"><span data-stu-id="8a27e-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="8a27e-116">Proprietà dei moduli banner promozionale</span><span class="sxs-lookup"><span data-stu-id="8a27e-116">Promo banner module properties</span></span>

| <span data-ttu-id="8a27e-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="8a27e-117">Property name</span></span>             | <span data-ttu-id="8a27e-118">Value</span><span class="sxs-lookup"><span data-stu-id="8a27e-118">Value</span></span>                              | <span data-ttu-id="8a27e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a27e-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="8a27e-120">Messaggi banner</span><span class="sxs-lookup"><span data-stu-id="8a27e-120">Banner messages</span></span>           | <span data-ttu-id="8a27e-121">Testo e collegamenti</span><span class="sxs-lookup"><span data-stu-id="8a27e-121">Text and links</span></span>                     | <span data-ttu-id="8a27e-122">Una matrice di testo e collegamenti.</span><span class="sxs-lookup"><span data-stu-id="8a27e-122">An array of text and links.</span></span> |
| <span data-ttu-id="8a27e-123">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="8a27e-123">Autoplay</span></span>                  | <span data-ttu-id="8a27e-124">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="8a27e-124">**True** or **False**</span></span>              | <span data-ttu-id="8a27e-125">Un valore che indica se i messaggi vengono automaticamente passati in rassegna, se sono configurati più messaggi.</span><span class="sxs-lookup"><span data-stu-id="8a27e-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="8a27e-126">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="8a27e-126">Slide transition interval</span></span> | <span data-ttu-id="8a27e-127">Un numero di millisecondi (ms)</span><span class="sxs-lookup"><span data-stu-id="8a27e-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="8a27e-128">L'intervallo utilizzato per scorrere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8a27e-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="8a27e-129">Consenti chiusura</span><span class="sxs-lookup"><span data-stu-id="8a27e-129">Allow dismiss</span></span>             | <span data-ttu-id="8a27e-130">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="8a27e-130">**True** or **False**</span></span>              | <span data-ttu-id="8a27e-131">Se il valore è impostato su **True**, i clienti possono chiudere l'avviso.</span><span class="sxs-lookup"><span data-stu-id="8a27e-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="8a27e-132">Mostra flipper sequenza</span><span class="sxs-lookup"><span data-stu-id="8a27e-132">Show carousel flipper</span></span>     | <span data-ttu-id="8a27e-133">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="8a27e-133">**True** or **False**</span></span>              | <span data-ttu-id="8a27e-134">Un valore che indica se i flipper della sequenza devono essere visualizzati, di modo che i clienti possano scorrere manualmente più elementi del banner.</span><span class="sxs-lookup"><span data-stu-id="8a27e-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="8a27e-135">Allineamento testo</span><span class="sxs-lookup"><span data-stu-id="8a27e-135">Text alignment</span></span>            | <span data-ttu-id="8a27e-136">**A destra**, **A sinistra** o **Al centro**</span><span class="sxs-lookup"><span data-stu-id="8a27e-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="8a27e-137">L'allineamento del testo nel modulo banner promozionale.</span><span class="sxs-lookup"><span data-stu-id="8a27e-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="8a27e-138">Collega</span><span class="sxs-lookup"><span data-stu-id="8a27e-138">Link</span></span>                      | <span data-ttu-id="8a27e-139">URL A</span><span class="sxs-lookup"><span data-stu-id="8a27e-139">A URL</span></span>                              | <span data-ttu-id="8a27e-140">L'URL di un collegamento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8a27e-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="8a27e-141">Aggiungere un modulo banner promozionale a una pagina</span><span class="sxs-lookup"><span data-stu-id="8a27e-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="8a27e-142">Per aggiungere un modulo banner promozionale a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8a27e-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="8a27e-143">Selezionare **Nuovo** per creare un modello di pagina.</span><span class="sxs-lookup"><span data-stu-id="8a27e-143">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="8a27e-144">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello banner promozionale**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a27e-144">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="8a27e-145">Sotto **Struttura pagina** , aggiungere un modulo **Pagina predefinita** allo slot **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="8a27e-145">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="8a27e-146">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="8a27e-146">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="8a27e-147">Utilizzare il modello appena creato per creare una pagina denominata **Pagina banner promozionale**.</span><span class="sxs-lookup"><span data-stu-id="8a27e-147">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="8a27e-148">Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="8a27e-148">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="8a27e-149">Nel riquadro a destra, impostare il valore **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="8a27e-149">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="8a27e-150">Sotto **Struttura pagina**, aggiungere un modulo banner promozionale al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="8a27e-150">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="8a27e-151">Nelle impostazioni per il modulo banner, aggiungere uno o più messaggi banner.</span><span class="sxs-lookup"><span data-stu-id="8a27e-151">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="8a27e-152">Ogni messaggio può avere del testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="8a27e-152">Each message can have text together with a link.</span></span> <span data-ttu-id="8a27e-153">È possibile modificare le altre proprietà per personalizzare ulteriormente il modulo.</span><span class="sxs-lookup"><span data-stu-id="8a27e-153">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="8a27e-154">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="8a27e-154">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="8a27e-155">Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso che mostra il testo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="8a27e-155">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="8a27e-156">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="8a27e-156">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="8a27e-157">Un banner promozionale viene in genere utilizzato nello slot dell'intestazione di pagina o in uno slot del sottotitolo.</span><span class="sxs-lookup"><span data-stu-id="8a27e-157">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="8a27e-158">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8a27e-158">Additional resources</span></span>

[<span data-ttu-id="8a27e-159">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="8a27e-159">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8a27e-160">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="8a27e-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="8a27e-161">Modulo blocco di testo</span><span class="sxs-lookup"><span data-stu-id="8a27e-161">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="8a27e-162">modulo blocco di contenuto</span><span class="sxs-lookup"><span data-stu-id="8a27e-162">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="8a27e-163">Modulo lettore video</span><span class="sxs-lookup"><span data-stu-id="8a27e-163">Video player module</span></span>](add-video-player.md)
