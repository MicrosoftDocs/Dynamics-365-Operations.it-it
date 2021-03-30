---
title: Modulo Sequenza
description: Questo argomento tratta i moduli Sequenza e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5333ecd7a1fe4f60684fa5f5bb3ac9f98efde6d7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206513"
---
# <a name="carousel-module"></a><span data-ttu-id="ee447-103">Modulo sequenza</span><span class="sxs-lookup"><span data-stu-id="ee447-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ee447-104">Questo argomento tratta i moduli Sequenza e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee447-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ee447-105">Un modulo Sequenza viene utilizzato per inserire molteplici articoli promozionali (incluse immagini) in un banner sequenza rotante al quale i clienti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="ee447-105">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="ee447-106">Ad esempio, un rivenditore può utilizzare un modulo Sequenza in una home page per presentare molteplici nuovi prodotti o promozioni.</span><span class="sxs-lookup"><span data-stu-id="ee447-106">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="ee447-107">È possibile aggiungere moduli Blocco di contenuto a un modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="ee447-107">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="ee447-108">Le proprietà del modulo Sequenza definiscono quindi il modo in cui viene eseguito il rendering di tali moduli.</span><span class="sxs-lookup"><span data-stu-id="ee447-108">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="ee447-109">Esempi di moduli Sequenza in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="ee447-109">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="ee447-110">Una sequenza che include più moduli promozionali può essere utilizzata in una home page.</span><span class="sxs-lookup"><span data-stu-id="ee447-110">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="ee447-111">Una sequenza con più moduli promozionali può essere utilizzata in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="ee447-111">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="ee447-112">Una sequenza può essere utilizzata in qualsiasi pagina marketing per promuovere molteplici promozioni o prodotti.</span><span class="sxs-lookup"><span data-stu-id="ee447-112">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="ee447-113">L'immagine seguente mostra un esempio di modulo Sequenza utilizzato in una home page.</span><span class="sxs-lookup"><span data-stu-id="ee447-113">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="ee447-114">Questo modulo Sequenza contiene molteplici elementi del blocco di contenuto.</span><span class="sxs-lookup"><span data-stu-id="ee447-114">This carousel module contains multiple content block items.</span></span>

![Esempio di modulo Sequenza](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="ee447-116">Proprietà del modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="ee447-116">Carousel module properties</span></span>

| <span data-ttu-id="ee447-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="ee447-117">Property name</span></span>             | <span data-ttu-id="ee447-118">Valore</span><span class="sxs-lookup"><span data-stu-id="ee447-118">Value</span></span>                 | <span data-ttu-id="ee447-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee447-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="ee447-120">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="ee447-120">Autoplay</span></span>                  | <span data-ttu-id="ee447-121">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="ee447-121">**True** or **False**</span></span> | <span data-ttu-id="ee447-122">Se il valore è impostato su **True**, la transizione tra gli articoli nella sequenza viene eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ee447-122">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="ee447-123">Se il valore è impostato su **False**, non viene eseguita alcuna transizione a meno che il cliente non utilizzi la tastiera o il mouse per passare da un articolo all'articolo successivo.</span><span class="sxs-lookup"><span data-stu-id="ee447-123">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="ee447-124">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="ee447-124">Slide transition interval</span></span> | <span data-ttu-id="ee447-125">Un valore in secondi</span><span class="sxs-lookup"><span data-stu-id="ee447-125">A value in seconds</span></span>    | <span data-ttu-id="ee447-126">L'intervallo delle transizioni tra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="ee447-126">The interval for transitions between items.</span></span> |
| <span data-ttu-id="ee447-127">Tipo di transizione</span><span class="sxs-lookup"><span data-stu-id="ee447-127">Transition type</span></span>           | <span data-ttu-id="ee447-128">**Diapositiva** o **Dissolvenza**</span><span class="sxs-lookup"><span data-stu-id="ee447-128">**Slide** or **Fade**</span></span> | <span data-ttu-id="ee447-129">L'effetto di transizione tra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="ee447-129">The transition effect between items.</span></span> |
| <span data-ttu-id="ee447-130">Nascondi flipper sequenza</span><span class="sxs-lookup"><span data-stu-id="ee447-130">Hide carousel flipper</span></span>     | <span data-ttu-id="ee447-131">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="ee447-131">**True** or **False**</span></span> | <span data-ttu-id="ee447-132">Se il valore è **True**, il flipper sequenza e l'indicatore di sequenza sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="ee447-132">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="ee447-133">Consenti chiusura sequenza</span><span class="sxs-lookup"><span data-stu-id="ee447-133">Allow carousel dismiss</span></span>    | <span data-ttu-id="ee447-134">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="ee447-134">**True** or **False**</span></span> | <span data-ttu-id="ee447-135">Se il valore è **True**, gli utenti possono chiudere la sequenza.</span><span class="sxs-lookup"><span data-stu-id="ee447-135">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="ee447-136">Aggiungere un modulo Sequenza a una pagina</span><span class="sxs-lookup"><span data-stu-id="ee447-136">Add a carousel module to a page</span></span>

<span data-ttu-id="ee447-137">Per aggiungere un modulo Sequenza a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ee447-137">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ee447-138">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="ee447-138">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="ee447-139">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello sequenza**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee447-139">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="ee447-140">Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="ee447-140">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="ee447-141">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="ee447-141">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="ee447-142">Utilizzare il modello sequenza appena creato per creare una pagina denominata **Pagina sequenza**.</span><span class="sxs-lookup"><span data-stu-id="ee447-142">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="ee447-143">Nello slot **Principale** della nuova pagina, aggiungere un modulo Contenitore.</span><span class="sxs-lookup"><span data-stu-id="ee447-143">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="ee447-144">Nel riquadro a destra, impostare il **Larghezza** su **Riempi schermo**.</span><span class="sxs-lookup"><span data-stu-id="ee447-144">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="ee447-145">Sotto **Struttura pagina**, aggiungere un modulo Sequenza al modulo Contenitore.</span><span class="sxs-lookup"><span data-stu-id="ee447-145">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="ee447-146">Aggiungere un modulo Blocco di contenuto al modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="ee447-146">Add a content block module to the carousel module.</span></span> <span data-ttu-id="ee447-147">Impostare le proprietà del modulo Blocco di contenuto fornendo **Intestazione**, **Collegamento**, **Layout** e altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="ee447-147">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="ee447-148">Aggiungere e configurare un altro modulo Blocco di contenuto.</span><span class="sxs-lookup"><span data-stu-id="ee447-148">Add and configure another content block module.</span></span>
1. <span data-ttu-id="ee447-149">Impostare proprietà aggiuntive per il modulo Sequenza come necessario.</span><span class="sxs-lookup"><span data-stu-id="ee447-149">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="ee447-150">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="ee447-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="ee447-151">La pagina dovrebbe visualizzare una sequenza con due moduli (un modulo Hero e un modulo Funzionalità).</span><span class="sxs-lookup"><span data-stu-id="ee447-151">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="ee447-152">È possibile modificare ulteriori proprietà dei moduli Sequenza, Hero e Funzionalità per ottenere l'effetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee447-152">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="ee447-153">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="ee447-153">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee447-154">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ee447-154">Additional resources</span></span>

[<span data-ttu-id="ee447-155">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="ee447-155">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ee447-156">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="ee447-156">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="ee447-157">Modulo blocco testo</span><span class="sxs-lookup"><span data-stu-id="ee447-157">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="ee447-158">Modulo blocco contenuto</span><span class="sxs-lookup"><span data-stu-id="ee447-158">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="ee447-159">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="ee447-159">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]