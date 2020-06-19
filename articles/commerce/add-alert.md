---
title: Modulo Banner promozionale
description: In questo argomento vengono descritti i moduli Banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: dae824cdbaaf56f85f125c5f36aaa56171bbd6bc
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411367"
---
# <a name="promo-banner-module"></a><span data-ttu-id="5ecb2-103">Modulo Banner promozionale</span><span class="sxs-lookup"><span data-stu-id="5ecb2-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5ecb2-104">In questo argomento vengono descritti i moduli Banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5ecb2-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5ecb2-105">Overview</span></span>

<span data-ttu-id="5ecb2-106">I moduli Banner promozionale sono utilizzati per visualizzare messaggi informativi incorporati in una pagina.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="5ecb2-107">Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="5ecb2-108">I moduli Banner promozionale supportano un messaggio di testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="5ecb2-109">Se vengono aggiunti più messaggi a un modulo banner promozionale, questo diventa un banner sequenza rotante che consente ai clienti di scorrere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="5ecb2-110">I moduli Banner promozionale sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="5ecb2-111">Esempi di utilizzo di banner promozionali in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="5ecb2-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="5ecb2-112">I banner promozionali possono essere utilizzati nell'intestazione del sito per mostrare promozioni o messaggi in tutto il sito, come negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="5ecb2-113">"La vendita annuale termina tra 10 giorni"</span><span class="sxs-lookup"><span data-stu-id="5ecb2-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="5ecb2-114">"Grandi risparmi con la vendita di articoli scolastici.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-114">"Save big with back to school sale.</span></span> <span data-ttu-id="5ecb2-115">Acquista ora".</span><span class="sxs-lookup"><span data-stu-id="5ecb2-115">Shop Now."</span></span>

<span data-ttu-id="5ecb2-116">"SALDI del Giorno del ringraziamento"</span><span class="sxs-lookup"><span data-stu-id="5ecb2-116">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="5ecb2-117">L'immagine seguente mostra un esempio di banner promozionale.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-117">The following image shows an example of a promo banner.</span></span>

![Esempio di modulo banner promozionale](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="5ecb2-119">Proprietà dei moduli Banner promozionale</span><span class="sxs-lookup"><span data-stu-id="5ecb2-119">Promo banner module properties</span></span>

| <span data-ttu-id="5ecb2-120">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="5ecb2-120">Property name</span></span>             | <span data-ttu-id="5ecb2-121">Valore</span><span class="sxs-lookup"><span data-stu-id="5ecb2-121">Value</span></span>                              | <span data-ttu-id="5ecb2-122">descrizione</span><span class="sxs-lookup"><span data-stu-id="5ecb2-122">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="5ecb2-123">Messaggi banner</span><span class="sxs-lookup"><span data-stu-id="5ecb2-123">Banner messages</span></span>           | <span data-ttu-id="5ecb2-124">Testo e collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ecb2-124">Text and links</span></span>                     | <span data-ttu-id="5ecb2-125">Una matrice di testo e collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-125">An array of text and links.</span></span> |
| <span data-ttu-id="5ecb2-126">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="5ecb2-126">Autoplay</span></span>                  | <span data-ttu-id="5ecb2-127">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="5ecb2-127">**True** or **False**</span></span>              | <span data-ttu-id="5ecb2-128">Un valore che indica se i messaggi vengono automaticamente passati in rassegna, se sono configurati più messaggi.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-128">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="5ecb2-129">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="5ecb2-129">Slide transition interval</span></span> | <span data-ttu-id="5ecb2-130">Un numero di millisecondi (ms)</span><span class="sxs-lookup"><span data-stu-id="5ecb2-130">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="5ecb2-131">L'intervallo utilizzato per scorrere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-131">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="5ecb2-132">Consenti chiusura</span><span class="sxs-lookup"><span data-stu-id="5ecb2-132">Allow dismiss</span></span>             | <span data-ttu-id="5ecb2-133">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="5ecb2-133">**True** or **False**</span></span>              | <span data-ttu-id="5ecb2-134">Se il valore è impostato su **True**, i clienti possono chiudere l'avviso.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-134">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="5ecb2-135">Mostra flipper sequenza</span><span class="sxs-lookup"><span data-stu-id="5ecb2-135">Show carousel flipper</span></span>     | <span data-ttu-id="5ecb2-136">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="5ecb2-136">**True** or **False**</span></span>              | <span data-ttu-id="5ecb2-137">Un valore che indica se i flipper della sequenza devono essere visualizzati, di modo che i clienti possano scorrere manualmente più elementi del banner.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-137">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="5ecb2-138">Allineamento testo</span><span class="sxs-lookup"><span data-stu-id="5ecb2-138">Text alignment</span></span>            | <span data-ttu-id="5ecb2-139">**A destra**, **A sinistra** o **Al centro**</span><span class="sxs-lookup"><span data-stu-id="5ecb2-139">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="5ecb2-140">L'allineamento del testo nel modulo banner promozionale.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-140">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="5ecb2-141">Collega</span><span class="sxs-lookup"><span data-stu-id="5ecb2-141">Link</span></span>                      | <span data-ttu-id="5ecb2-142">URL A</span><span class="sxs-lookup"><span data-stu-id="5ecb2-142">A URL</span></span>                              | <span data-ttu-id="5ecb2-143">L'URL di un collegamento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-143">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="5ecb2-144">Aggiungere un modulo banner promozionale a una pagina</span><span class="sxs-lookup"><span data-stu-id="5ecb2-144">Add a promo banner module to a page</span></span> 

<span data-ttu-id="5ecb2-145">Per aggiungere un modulo banner promozionale a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-145">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="5ecb2-146">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-146">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="5ecb2-147">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello banner promozionale**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-147">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="5ecb2-148">Sotto **Struttura pagina** , aggiungere un modulo **Pagina predefinita** allo slot **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-148">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="5ecb2-149">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-149">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="5ecb2-150">Utilizzare il modello appena creato per creare una pagina denominata **Pagina banner promozionale**.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-150">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="5ecb2-151">Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-151">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="5ecb2-152">Nel riquadro a destra, impostare il valore **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-152">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="5ecb2-153">Sotto **Struttura pagina**, aggiungere un modulo banner promozionale al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-153">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="5ecb2-154">Nelle impostazioni per il modulo banner, aggiungere uno o più messaggi banner.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-154">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="5ecb2-155">Ogni messaggio può avere del testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-155">Each message can have text together with a link.</span></span> <span data-ttu-id="5ecb2-156">È possibile modificare le altre proprietà per personalizzare ulteriormente il modulo.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-156">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="5ecb2-157">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-157">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="5ecb2-158">Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso che mostra il testo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-158">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="5ecb2-159">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-159">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="5ecb2-160">Un banner promozionale viene in genere utilizzato nello slot dell'intestazione di pagina o in uno slot del sottotitolo.</span><span class="sxs-lookup"><span data-stu-id="5ecb2-160">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="5ecb2-161">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5ecb2-161">Additional resources</span></span>

[<span data-ttu-id="5ecb2-162">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="5ecb2-162">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="5ecb2-163">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="5ecb2-163">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="5ecb2-164">Modulo Blocco di testo</span><span class="sxs-lookup"><span data-stu-id="5ecb2-164">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="5ecb2-165">modulo blocco di contenuto</span><span class="sxs-lookup"><span data-stu-id="5ecb2-165">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="5ecb2-166">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="5ecb2-166">Video player module</span></span>](add-video-player.md)
