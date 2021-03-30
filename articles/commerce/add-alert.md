---
title: Modulo Banner promozionale
description: In questo argomento vengono descritti i moduli Banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0b9325ef31fc61d451584930b09c2039156c0c05
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206585"
---
# <a name="promo-banner-module"></a><span data-ttu-id="739cd-103">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="739cd-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="739cd-104">In questo argomento vengono descritti i moduli Banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="739cd-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="739cd-105">I moduli Banner promozionale sono utilizzati per visualizzare messaggi informativi incorporati in una pagina.</span><span class="sxs-lookup"><span data-stu-id="739cd-105">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="739cd-106">Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="739cd-106">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="739cd-107">I moduli Banner promozionale supportano un messaggio di testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="739cd-107">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="739cd-108">Se vengono aggiunti più messaggi a un modulo banner promozionale, questo diventa un banner sequenza rotante che consente ai clienti di scorrere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="739cd-108">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="739cd-109">I moduli Banner promozionale sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="739cd-109">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="739cd-110">Esempi di utilizzo di banner promozionali in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="739cd-110">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="739cd-111">I banner promozionali possono essere utilizzati nell'intestazione del sito per mostrare promozioni o messaggi in tutto il sito, come negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="739cd-111">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="739cd-112">"La vendita annuale termina tra 10 giorni"</span><span class="sxs-lookup"><span data-stu-id="739cd-112">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="739cd-113">"Grandi risparmi con la vendita di articoli scolastici.</span><span class="sxs-lookup"><span data-stu-id="739cd-113">"Save big with back to school sale.</span></span> <span data-ttu-id="739cd-114">Acquista ora".</span><span class="sxs-lookup"><span data-stu-id="739cd-114">Shop Now."</span></span>

<span data-ttu-id="739cd-115">"SALDI del Giorno del ringraziamento"</span><span class="sxs-lookup"><span data-stu-id="739cd-115">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="739cd-116">L'immagine seguente mostra un esempio di banner promozionale.</span><span class="sxs-lookup"><span data-stu-id="739cd-116">The following image shows an example of a promo banner.</span></span>

![Esempio di modulo banner promozionale](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="739cd-118">Proprietà dei moduli Banner promozionale</span><span class="sxs-lookup"><span data-stu-id="739cd-118">Promo banner module properties</span></span>

| <span data-ttu-id="739cd-119">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="739cd-119">Property name</span></span>             | <span data-ttu-id="739cd-120">Valore</span><span class="sxs-lookup"><span data-stu-id="739cd-120">Value</span></span>                              | <span data-ttu-id="739cd-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="739cd-121">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="739cd-122">Messaggi banner</span><span class="sxs-lookup"><span data-stu-id="739cd-122">Banner messages</span></span>           | <span data-ttu-id="739cd-123">Testo e collegamenti</span><span class="sxs-lookup"><span data-stu-id="739cd-123">Text and links</span></span>                     | <span data-ttu-id="739cd-124">Una matrice di testo e collegamenti.</span><span class="sxs-lookup"><span data-stu-id="739cd-124">An array of text and links.</span></span> |
| <span data-ttu-id="739cd-125">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="739cd-125">Autoplay</span></span>                  | <span data-ttu-id="739cd-126">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="739cd-126">**True** or **False**</span></span>              | <span data-ttu-id="739cd-127">Un valore che indica se i messaggi vengono automaticamente passati in rassegna, se sono configurati più messaggi.</span><span class="sxs-lookup"><span data-stu-id="739cd-127">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="739cd-128">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="739cd-128">Slide transition interval</span></span> | <span data-ttu-id="739cd-129">Un numero di millisecondi (ms)</span><span class="sxs-lookup"><span data-stu-id="739cd-129">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="739cd-130">L'intervallo utilizzato per scorrere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="739cd-130">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="739cd-131">Consenti chiusura</span><span class="sxs-lookup"><span data-stu-id="739cd-131">Allow dismiss</span></span>             | <span data-ttu-id="739cd-132">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="739cd-132">**True** or **False**</span></span>              | <span data-ttu-id="739cd-133">Se il valore è impostato su **True**, i clienti possono chiudere l'avviso.</span><span class="sxs-lookup"><span data-stu-id="739cd-133">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="739cd-134">Mostra flipper sequenza</span><span class="sxs-lookup"><span data-stu-id="739cd-134">Show carousel flipper</span></span>     | <span data-ttu-id="739cd-135">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="739cd-135">**True** or **False**</span></span>              | <span data-ttu-id="739cd-136">Un valore che indica se i flipper della sequenza devono essere visualizzati, di modo che i clienti possano scorrere manualmente più elementi del banner.</span><span class="sxs-lookup"><span data-stu-id="739cd-136">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="739cd-137">Allineamento testo</span><span class="sxs-lookup"><span data-stu-id="739cd-137">Text alignment</span></span>            | <span data-ttu-id="739cd-138">**A destra**, **A sinistra** o **Al centro**</span><span class="sxs-lookup"><span data-stu-id="739cd-138">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="739cd-139">L'allineamento del testo nel modulo banner promozionale.</span><span class="sxs-lookup"><span data-stu-id="739cd-139">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="739cd-140">Collega</span><span class="sxs-lookup"><span data-stu-id="739cd-140">Link</span></span>                      | <span data-ttu-id="739cd-141">URL A</span><span class="sxs-lookup"><span data-stu-id="739cd-141">A URL</span></span>                              | <span data-ttu-id="739cd-142">L'URL di un collegamento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="739cd-142">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="739cd-143">Aggiungere un modulo banner promozionale a una pagina</span><span class="sxs-lookup"><span data-stu-id="739cd-143">Add a promo banner module to a page</span></span> 

<span data-ttu-id="739cd-144">Per aggiungere un modulo banner promozionale a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="739cd-144">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="739cd-145">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="739cd-145">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="739cd-146">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello banner promozionale**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="739cd-146">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="739cd-147">Sotto **Struttura pagina** , aggiungere un modulo **Pagina predefinita** allo slot **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="739cd-147">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="739cd-148">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="739cd-148">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="739cd-149">Utilizzare il modello appena creato per creare una pagina denominata **Pagina banner promozionale**.</span><span class="sxs-lookup"><span data-stu-id="739cd-149">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="739cd-150">Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="739cd-150">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="739cd-151">Nel riquadro a destra, impostare il valore **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="739cd-151">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="739cd-152">Sotto **Struttura pagina**, aggiungere un modulo banner promozionale al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="739cd-152">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="739cd-153">Nelle impostazioni per il modulo banner, aggiungere uno o più messaggi banner.</span><span class="sxs-lookup"><span data-stu-id="739cd-153">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="739cd-154">Ogni messaggio può avere del testo e un collegamento.</span><span class="sxs-lookup"><span data-stu-id="739cd-154">Each message can have text together with a link.</span></span> <span data-ttu-id="739cd-155">È possibile modificare le altre proprietà per personalizzare ulteriormente il modulo.</span><span class="sxs-lookup"><span data-stu-id="739cd-155">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="739cd-156">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="739cd-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="739cd-157">Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso che mostra il testo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="739cd-157">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="739cd-158">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="739cd-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="739cd-159">Un banner promozionale viene in genere utilizzato nello slot dell'intestazione di pagina o in uno slot del sottotitolo.</span><span class="sxs-lookup"><span data-stu-id="739cd-159">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="739cd-160">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="739cd-160">Additional resources</span></span>

[<span data-ttu-id="739cd-161">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="739cd-161">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="739cd-162">Modulo sequenza</span><span class="sxs-lookup"><span data-stu-id="739cd-162">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="739cd-163">Modulo blocco testo</span><span class="sxs-lookup"><span data-stu-id="739cd-163">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="739cd-164">Modulo blocco contenuto</span><span class="sxs-lookup"><span data-stu-id="739cd-164">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="739cd-165">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="739cd-165">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]