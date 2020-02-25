---
title: Modulo Sequenza
description: In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025783"
---
# <a name="carousel-module"></a><span data-ttu-id="56170-103">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="56170-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="56170-104">In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="56170-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="56170-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="56170-105">Overview</span></span>

<span data-ttu-id="56170-106">Un modulo Sequenza viene utilizzato per inserire molteplici articoli promozionali (incluse immagini) in un banner sequenza rotante al quale i clienti possono accedere.</span><span class="sxs-lookup"><span data-stu-id="56170-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="56170-107">Ad esempio, un rivenditore può utilizzare un modulo Sequenza in una home page per presentare molteplici nuovi prodotti o promozioni.</span><span class="sxs-lookup"><span data-stu-id="56170-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="56170-108">È possibile aggiungere modulo blocco di contenuto in un modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="56170-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="56170-109">Le proprietà del modulo Sequenza definiscono quindi il modo in cui viene eseguito il rendering di tali moduli.</span><span class="sxs-lookup"><span data-stu-id="56170-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="56170-110">Esempi di moduli Sequenza in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="56170-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="56170-111">Una sequenza che include più moduli promozionali può essere utilizzata in una home page.</span><span class="sxs-lookup"><span data-stu-id="56170-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="56170-112">Una sequenza con più moduli promozionali può essere utilizzata in una pagina dettagli prodotto.</span><span class="sxs-lookup"><span data-stu-id="56170-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="56170-113">Una sequenza può essere utilizzata in qualsiasi pagina marketing per promuovere molteplici promozioni o prodotti.</span><span class="sxs-lookup"><span data-stu-id="56170-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="56170-114">Proprietà del modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="56170-114">Carousel module properties</span></span>

| <span data-ttu-id="56170-115">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="56170-115">Property name</span></span>             | <span data-ttu-id="56170-116">Valore</span><span class="sxs-lookup"><span data-stu-id="56170-116">Value</span></span>                 | <span data-ttu-id="56170-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56170-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="56170-118">Riproduzione automatica</span><span class="sxs-lookup"><span data-stu-id="56170-118">Autoplay</span></span>                  | <span data-ttu-id="56170-119">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="56170-119">**True** or **False**</span></span> | <span data-ttu-id="56170-120">Se il valore è impostato su **True**, la transizione tra gli articoli nella sequenza viene eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="56170-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="56170-121">Se il valore è impostato su **False**, non viene eseguita alcuna transizione a meno che il cliente non utilizzi la tastiera o il mouse per passare da un articolo all'articolo successivo.</span><span class="sxs-lookup"><span data-stu-id="56170-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="56170-122">Intervallo di transizione diapositiva</span><span class="sxs-lookup"><span data-stu-id="56170-122">Slide transition interval</span></span> | <span data-ttu-id="56170-123">Un valore in secondi</span><span class="sxs-lookup"><span data-stu-id="56170-123">A value in seconds</span></span>    | <span data-ttu-id="56170-124">L'intervallo delle transizioni tra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="56170-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="56170-125">Tipo di transizione</span><span class="sxs-lookup"><span data-stu-id="56170-125">Transition type</span></span>           | <span data-ttu-id="56170-126">**Diapositiva** o **Dissolvenza**</span><span class="sxs-lookup"><span data-stu-id="56170-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="56170-127">L'effetto di transizione tra gli articoli.</span><span class="sxs-lookup"><span data-stu-id="56170-127">The transition effect between items.</span></span> |
| <span data-ttu-id="56170-128">Nascondi flipper sequenza</span><span class="sxs-lookup"><span data-stu-id="56170-128">Hide carousel flipper</span></span>     | <span data-ttu-id="56170-129">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="56170-129">**True** or **False**</span></span> | <span data-ttu-id="56170-130">Se il valore è **True**, il flipper sequenza e l'indicatore di sequenza sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="56170-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="56170-131">Consenti chiusura sequenza</span><span class="sxs-lookup"><span data-stu-id="56170-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="56170-132">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="56170-132">**True** or **False**</span></span> | <span data-ttu-id="56170-133">Se il valore è **True**, gli utenti possono chiudere la sequenza.</span><span class="sxs-lookup"><span data-stu-id="56170-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="56170-134">Aggiungere un modulo Sequenza a una pagina</span><span class="sxs-lookup"><span data-stu-id="56170-134">Add a carousel module to a page</span></span>

<span data-ttu-id="56170-135">Per aggiungere un modulo Sequenza a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="56170-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="56170-136">Creare un modello di pagina denominato **Modello sequenza**.</span><span class="sxs-lookup"><span data-stu-id="56170-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="56170-137">Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.</span><span class="sxs-lookup"><span data-stu-id="56170-137">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="56170-138">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="56170-138">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="56170-139">Utilizzare il modello sequenza appena creato per creare una pagina denominata **Pagina sequenza**.</span><span class="sxs-lookup"><span data-stu-id="56170-139">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="56170-140">Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="56170-140">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="56170-141">Nel riquadro a destra, impostare il **Larghezza** su **Riempi schermo**.</span><span class="sxs-lookup"><span data-stu-id="56170-141">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="56170-142">Sotto **Struttura pagina**, aggiungere un modulo Sequenza al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="56170-142">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="56170-143">Aggiungere un modulo blocco di contenuto al modulo Sequenza.</span><span class="sxs-lookup"><span data-stu-id="56170-143">Add a content block module to the carousel module.</span></span> <span data-ttu-id="56170-144">Impostare le proprietà del modulo blocco di contenuto fornendo **Intestazione**, **Collegamento**, **Layout** e altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="56170-144">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="56170-145">Aggiungere e configurare un altro modulo blocco di contenuto.</span><span class="sxs-lookup"><span data-stu-id="56170-145">Add and configure another content block module.</span></span>
1. <span data-ttu-id="56170-146">Impostare proprietà aggiuntive per il modulo Sequenza come necessario.</span><span class="sxs-lookup"><span data-stu-id="56170-146">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="56170-147">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="56170-147">Save and preview the page.</span></span> <span data-ttu-id="56170-148">La pagina dovrebbe visualizzare una sequenza con due moduli (un modulo Hero e un modulo Funzionalità).</span><span class="sxs-lookup"><span data-stu-id="56170-148">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="56170-149">È possibile modificare ulteriori proprietà dei moduli Sequenza, Hero e Funzionalità per ottenere l'effetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="56170-149">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="56170-150">Completare la modifica della pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="56170-150">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56170-151">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="56170-151">Additional resources</span></span>

[<span data-ttu-id="56170-152">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="56170-152">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="56170-153">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="56170-153">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="56170-154">Modulo blocco di testo</span><span class="sxs-lookup"><span data-stu-id="56170-154">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="56170-155">modulo blocco di contenuto</span><span class="sxs-lookup"><span data-stu-id="56170-155">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="56170-156">Modulo lettore video</span><span class="sxs-lookup"><span data-stu-id="56170-156">Video player module</span></span>](add-video-player.md)
