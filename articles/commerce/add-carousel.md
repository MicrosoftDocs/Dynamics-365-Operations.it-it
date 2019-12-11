---
title: Modulo Sequenza
description: In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785239"
---
# <a name="carousel-module"></a><span data-ttu-id="f96ff-103">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="f96ff-103">Carousel module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f96ff-104">In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f96ff-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f96ff-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f96ff-105">Overview</span></span>

<span data-ttu-id="f96ff-106">Un modulo Sequenza viene utilizzato per inserire molteplici articoli promozionali in una sequenza che i clienti possono vedere.</span><span class="sxs-lookup"><span data-stu-id="f96ff-106">A carousel module is used to put multiple promotional items in a carousel that customers can browse.</span></span> <span data-ttu-id="f96ff-107">Si tratta di un modulo contenitore speciale che ospita altri moduli.</span><span class="sxs-lookup"><span data-stu-id="f96ff-107">It's a special container module that hosts other modules.</span></span> <span data-ttu-id="f96ff-108">Ad esempio, un rivenditore può utilizzare un modulo Sequenza in una home page per presentare molteplici nuovi prodotti o promozioni.</span><span class="sxs-lookup"><span data-stu-id="f96ff-108">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="f96ff-109">È possibile aggiungere moduli Hero e Funzionalità a un modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-109">You can add hero and feature modules inside a carousel module.</span></span> <span data-ttu-id="f96ff-110">Le proprietà del modulo Sequenza definiscono quindi il modo in cui viene eseguito il rendering di tali moduli.</span><span class="sxs-lookup"><span data-stu-id="f96ff-110">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="f96ff-111">Esempi di moduli Sequenza in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="f96ff-111">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="f96ff-112">Una sequenza che include più moduli promozionali può essere utilizzata in una home page.</span><span class="sxs-lookup"><span data-stu-id="f96ff-112">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="f96ff-113">Una sequenza con più moduli promozionali può essere utilizzata in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="f96ff-113">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="f96ff-114">Una sequenza può essere utilizzata in qualsiasi pagina marketing per promuovere molteplici promozioni o prodotti.</span><span class="sxs-lookup"><span data-stu-id="f96ff-114">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="f96ff-115">Proprietà del modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="f96ff-115">Carousel module properties</span></span>

| <span data-ttu-id="f96ff-116">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="f96ff-116">Property name</span></span>             | <span data-ttu-id="f96ff-117">Valore</span><span class="sxs-lookup"><span data-stu-id="f96ff-117">Value</span></span>                                | <span data-ttu-id="f96ff-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f96ff-118">Description</span></span> |
|---------------------------|--------------------------------------|-------------|
| <span data-ttu-id="f96ff-119">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="f96ff-119">Autoplay</span></span>                  | <span data-ttu-id="f96ff-120">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="f96ff-120">**True** or **False**</span></span>                | <span data-ttu-id="f96ff-121">Se il valore è impostato su **True**, la transizione tra gli articoli nella sequenza viene eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f96ff-121">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="f96ff-122">Se il valore è impostato su **False**, non viene eseguita alcuna transizione a meno che il cliente non utilizzi la tastiera o il mouse per passare da un articolo all'articolo successivo.</span><span class="sxs-lookup"><span data-stu-id="f96ff-122">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="f96ff-123">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="f96ff-123">Slide transition interval</span></span> | <span data-ttu-id="f96ff-124">Un valore in secondi</span><span class="sxs-lookup"><span data-stu-id="f96ff-124">A value in seconds</span></span>                   | <span data-ttu-id="f96ff-125">L'intervallo delle transizioni tra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="f96ff-125">The interval for transitions between items.</span></span> |
| <span data-ttu-id="f96ff-126">Animazione transizione</span><span class="sxs-lookup"><span data-stu-id="f96ff-126">Transition animation</span></span>      | <span data-ttu-id="f96ff-127">**Diapositiva** o **Dissolvenza**</span><span class="sxs-lookup"><span data-stu-id="f96ff-127">**Slide** or **Fade**</span></span>                | <span data-ttu-id="f96ff-128">L'effetto di transizione.</span><span class="sxs-lookup"><span data-stu-id="f96ff-128">The transition effect.</span></span> |
| <span data-ttu-id="f96ff-129">Larghezza</span><span class="sxs-lookup"><span data-stu-id="f96ff-129">Width</span></span>                     | <span data-ttu-id="f96ff-130">**Adatta a contenitore** o **Riempi schermo**</span><span class="sxs-lookup"><span data-stu-id="f96ff-130">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="f96ff-131">Se il valore è **Adatta a contenitore**, gli elementi nella sequenza sono limitati alla larghezza della sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-131">If the value is set to **Fit container**, the items inside the carousel are restricted to the width of the carousel.</span></span> <span data-ttu-id="f96ff-132">Se il valore impostato è **Riempi schermo**, gli elementi non sono limitati alla larghezza della sequenza ma possono essere visualizzati in modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="f96ff-132">If the value is set to **Fill screen**, the items aren't restricted to the carousel width but can go into full-screen mode.</span></span> <span data-ttu-id="f96ff-133">È possibile modificare il valore per ottenere il layout desiderato.</span><span class="sxs-lookup"><span data-stu-id="f96ff-133">You can change the value to achieve the desired layout.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="f96ff-134">Aggiungere un modulo Sequenza a una pagina</span><span class="sxs-lookup"><span data-stu-id="f96ff-134">Add a carousel module to a page</span></span>

<span data-ttu-id="f96ff-135">Per aggiungere un modulo Sequenza a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f96ff-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="f96ff-136">Creare un modello di pagina denominato **Modello sequenza**.</span><span class="sxs-lookup"><span data-stu-id="f96ff-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="f96ff-137">Nello slot **Principale** della pagina predefinita, aggiungere un modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-137">In the **Main** slot of the default page, add a carousel module.</span></span>
1. <span data-ttu-id="f96ff-138">Aggiungere un modulo Hero al modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-138">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="f96ff-139">Aggiungere un modulo Funzionalità al modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-139">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="f96ff-140">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="f96ff-140">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="f96ff-141">Utilizzare il modello sequenza appena creato per creare una pagina denominata **Pagina sequenza**.</span><span class="sxs-lookup"><span data-stu-id="f96ff-141">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="f96ff-142">Nello slot **Principale** della nuova pagina, aggiungere un modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-142">In the **Main** slot of the new page, add a carousel module.</span></span>
1. <span data-ttu-id="f96ff-143">Impostare la proprietà **Larghezza** del modulo Sequenza su **Riempi schermo**.</span><span class="sxs-lookup"><span data-stu-id="f96ff-143">Set the **Width** property of the carousel module to **Fill screen**.</span></span> 
1. <span data-ttu-id="f96ff-144">Impostare la proprietà **Animazione transizione** su **Diapositiva**.</span><span class="sxs-lookup"><span data-stu-id="f96ff-144">Set the **Transition animation** property to **Slide**.</span></span>
1. <span data-ttu-id="f96ff-145">Aggiungere un modulo Hero al modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-145">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="f96ff-146">Nel modulo Hero, aggiungere un'immagine e un'intestazione, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f96ff-146">In the hero module, add an image and a heading, and then select **Save**.</span></span>
1. <span data-ttu-id="f96ff-147">Aggiungere un modulo Funzionalità al modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="f96ff-147">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="f96ff-148">Nel modulo Funzionalità, aggiungere un'immagine, un'intestazione e un paragrafo di testo.</span><span class="sxs-lookup"><span data-stu-id="f96ff-148">In the feature module, add an image, a heading, and a paragraph of text.</span></span>
1. <span data-ttu-id="f96ff-149">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="f96ff-149">Save and preview the page.</span></span> <span data-ttu-id="f96ff-150">La pagina dovrebbe visualizzare una sequenza con due moduli (un modulo Hero e un modulo Funzionalità).</span><span class="sxs-lookup"><span data-stu-id="f96ff-150">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="f96ff-151">È possibile modificare ulteriori proprietà dei moduli Sequenza, Hero e Funzionalità per ottenere l'effetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="f96ff-151">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="f96ff-152">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="f96ff-152">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f96ff-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f96ff-153">Additional resources</span></span>

[<span data-ttu-id="f96ff-154">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="f96ff-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f96ff-155">Modulo Avviso</span><span class="sxs-lookup"><span data-stu-id="f96ff-155">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="f96ff-156">Modulo Blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="f96ff-156">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="f96ff-157">Modulo Posizionamento contenuti</span><span class="sxs-lookup"><span data-stu-id="f96ff-157">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="f96ff-158">Modulo Funzionalità</span><span class="sxs-lookup"><span data-stu-id="f96ff-158">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="f96ff-159">Modulo Hero</span><span class="sxs-lookup"><span data-stu-id="f96ff-159">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="f96ff-160">Modulo Lettore video</span><span class="sxs-lookup"><span data-stu-id="f96ff-160">Video player module</span></span>](add-video-player.md)
