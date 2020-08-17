---
title: Modulo Sequenza
description: In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 10ff0cd566a1a8d89ccadce9571dafc5a592520b
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2020
ms.locfileid: "3620988"
---
# <a name="carousel-module"></a><span data-ttu-id="3c377-103">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="3c377-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3c377-104">In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3c377-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3c377-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="3c377-105">Overview</span></span>

<span data-ttu-id="3c377-106">Un modulo Sequenza viene utilizzato per inserire molteplici articoli promozionali (incluse immagini) in un banner sequenza rotante al quale i clienti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="3c377-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="3c377-107">Ad esempio, un rivenditore può utilizzare un modulo Sequenza in una home page per presentare molteplici nuovi prodotti o promozioni.</span><span class="sxs-lookup"><span data-stu-id="3c377-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="3c377-108">È possibile aggiungere moduli Blocco di contenuto a un modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="3c377-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="3c377-109">Le proprietà del modulo Sequenza definiscono quindi il modo in cui viene eseguito il rendering di tali moduli.</span><span class="sxs-lookup"><span data-stu-id="3c377-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="3c377-110">Esempi di moduli Sequenza in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="3c377-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="3c377-111">Una sequenza che include più moduli promozionali può essere utilizzata in una home page.</span><span class="sxs-lookup"><span data-stu-id="3c377-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="3c377-112">Una sequenza con più moduli promozionali può essere utilizzata in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="3c377-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="3c377-113">Una sequenza può essere utilizzata in qualsiasi pagina marketing per promuovere molteplici promozioni o prodotti.</span><span class="sxs-lookup"><span data-stu-id="3c377-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="3c377-114">L'immagine seguente mostra un esempio di modulo Sequenza utilizzato in una home page.</span><span class="sxs-lookup"><span data-stu-id="3c377-114">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="3c377-115">Questo modulo Sequenza contiene molteplici elementi del blocco di contenuto.</span><span class="sxs-lookup"><span data-stu-id="3c377-115">This carousel module contains multiple content block items.</span></span>

![Esempio di modulo Sequenza](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="3c377-117">Proprietà del modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="3c377-117">Carousel module properties</span></span>

| <span data-ttu-id="3c377-118">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="3c377-118">Property name</span></span>             | <span data-ttu-id="3c377-119">Valore</span><span class="sxs-lookup"><span data-stu-id="3c377-119">Value</span></span>                 | <span data-ttu-id="3c377-120">descrizione</span><span class="sxs-lookup"><span data-stu-id="3c377-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="3c377-121">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="3c377-121">Autoplay</span></span>                  | <span data-ttu-id="3c377-122">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="3c377-122">**True** or **False**</span></span> | <span data-ttu-id="3c377-123">Se il valore è impostato su **True**, la transizione tra gli articoli nella sequenza viene eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3c377-123">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="3c377-124">Se il valore è impostato su **False**, non viene eseguita alcuna transizione a meno che il cliente non utilizzi la tastiera o il mouse per passare da un articolo all'articolo successivo.</span><span class="sxs-lookup"><span data-stu-id="3c377-124">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="3c377-125">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="3c377-125">Slide transition interval</span></span> | <span data-ttu-id="3c377-126">Un valore in secondi</span><span class="sxs-lookup"><span data-stu-id="3c377-126">A value in seconds</span></span>    | <span data-ttu-id="3c377-127">L'intervallo delle transizioni tra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="3c377-127">The interval for transitions between items.</span></span> |
| <span data-ttu-id="3c377-128">Tipo di transizione</span><span class="sxs-lookup"><span data-stu-id="3c377-128">Transition type</span></span>           | <span data-ttu-id="3c377-129">**Diapositiva** o **Dissolvenza**</span><span class="sxs-lookup"><span data-stu-id="3c377-129">**Slide** or **Fade**</span></span> | <span data-ttu-id="3c377-130">L'effetto di transizione tra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="3c377-130">The transition effect between items.</span></span> |
| <span data-ttu-id="3c377-131">Nascondi flipper sequenza</span><span class="sxs-lookup"><span data-stu-id="3c377-131">Hide carousel flipper</span></span>     | <span data-ttu-id="3c377-132">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="3c377-132">**True** or **False**</span></span> | <span data-ttu-id="3c377-133">Se il valore è **True**, il flipper sequenza e l'indicatore di sequenza sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="3c377-133">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="3c377-134">Consenti chiusura sequenza</span><span class="sxs-lookup"><span data-stu-id="3c377-134">Allow carousel dismiss</span></span>    | <span data-ttu-id="3c377-135">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="3c377-135">**True** or **False**</span></span> | <span data-ttu-id="3c377-136">Se il valore è **True**, gli utenti possono chiudere la sequenza.</span><span class="sxs-lookup"><span data-stu-id="3c377-136">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="3c377-137">Aggiungere un modulo Sequenza a una pagina</span><span class="sxs-lookup"><span data-stu-id="3c377-137">Add a carousel module to a page</span></span>

<span data-ttu-id="3c377-138">Per aggiungere un modulo Sequenza a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="3c377-138">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3c377-139">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="3c377-139">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="3c377-140">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello sequenza**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c377-140">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="3c377-141">Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="3c377-141">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="3c377-142">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="3c377-142">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="3c377-143">Utilizzare il modello sequenza appena creato per creare una pagina denominata **Pagina sequenza**.</span><span class="sxs-lookup"><span data-stu-id="3c377-143">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="3c377-144">Nello slot **Principale** della nuova pagina, aggiungere un modulo Contenitore.</span><span class="sxs-lookup"><span data-stu-id="3c377-144">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="3c377-145">Nel riquadro a destra, impostare il **Larghezza** su **Riempi schermo**.</span><span class="sxs-lookup"><span data-stu-id="3c377-145">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="3c377-146">Sotto **Struttura pagina**, aggiungere un modulo Sequenza al modulo Contenitore.</span><span class="sxs-lookup"><span data-stu-id="3c377-146">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="3c377-147">Aggiungere un modulo Blocco di contenuto al modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="3c377-147">Add a content block module to the carousel module.</span></span> <span data-ttu-id="3c377-148">Impostare le proprietà del modulo Blocco di contenuto fornendo **Intestazione**, **Collegamento**, **Layout** e altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="3c377-148">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="3c377-149">Aggiungere e configurare un altro modulo Blocco di contenuto.</span><span class="sxs-lookup"><span data-stu-id="3c377-149">Add and configure another content block module.</span></span>
1. <span data-ttu-id="3c377-150">Impostare proprietà aggiuntive per il modulo Sequenza come necessario.</span><span class="sxs-lookup"><span data-stu-id="3c377-150">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="3c377-151">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="3c377-151">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="3c377-152">La pagina dovrebbe visualizzare una sequenza con due moduli (un modulo Hero e un modulo Funzionalità).</span><span class="sxs-lookup"><span data-stu-id="3c377-152">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="3c377-153">È possibile modificare ulteriori proprietà dei moduli Sequenza, Hero e Funzionalità per ottenere l'effetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="3c377-153">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="3c377-154">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="3c377-154">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3c377-155">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3c377-155">Additional resources</span></span>

[<span data-ttu-id="3c377-156">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="3c377-156">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3c377-157">Modulo Banner promozionale</span><span class="sxs-lookup"><span data-stu-id="3c377-157">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="3c377-158">Modulo Blocco di testo</span><span class="sxs-lookup"><span data-stu-id="3c377-158">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="3c377-159">modulo Blocco di contenuto</span><span class="sxs-lookup"><span data-stu-id="3c377-159">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="3c377-160">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="3c377-160">Video player module</span></span>](add-video-player.md)
