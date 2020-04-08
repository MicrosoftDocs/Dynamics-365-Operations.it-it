---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025669"
---
# <a name="header-module"></a><span data-ttu-id="410d1-103">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="410d1-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="410d1-104">In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="410d1-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="410d1-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="410d1-105">Overview</span></span>

<span data-ttu-id="410d1-106">In Dynamics 365 Commerce, un'intestazione di pagina comprende più moduli, come i moduli intestazione, menu di navigazione, ricerca, banner promozionale e consenso per i cookie.</span><span class="sxs-lookup"><span data-stu-id="410d1-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="410d1-107">Il modulo intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il simbolo del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="410d1-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="410d1-108">Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile).</span><span class="sxs-lookup"><span data-stu-id="410d1-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="410d1-109">Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="410d1-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="410d1-110">Proprietà di un modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="410d1-110">Properties of a header module</span></span>

<span data-ttu-id="410d1-111">Un modulo intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**.</span><span class="sxs-lookup"><span data-stu-id="410d1-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="410d1-112">Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina.</span><span class="sxs-lookup"><span data-stu-id="410d1-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="410d1-113">Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="410d1-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="410d1-114">La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="410d1-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="410d1-115">Moduli disponibili in un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="410d1-115">Modules that are available in a header module</span></span>

<span data-ttu-id="410d1-116">Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:</span><span class="sxs-lookup"><span data-stu-id="410d1-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="410d1-117">**Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici.</span><span class="sxs-lookup"><span data-stu-id="410d1-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="410d1-118">La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="410d1-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="410d1-119">Il menu di navigazione presenta una proprietà **Origine navigazione** utilizzata per specificare le voci di menu di navigazione di Retail Server e le voci di menu statico come origine.</span><span class="sxs-lookup"><span data-stu-id="410d1-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="410d1-120">Se le voci di menu statico vengono specificate come origine, è possibile fornire collegamenti relativi ad altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="410d1-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="410d1-121">Gli elementi configurati vengono quindi visualizzati come navigazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="410d1-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="410d1-122">**Cerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti.</span><span class="sxs-lookup"><span data-stu-id="410d1-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="410d1-123">L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="410d1-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="410d1-124">Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="410d1-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="410d1-125">Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.</span><span class="sxs-lookup"><span data-stu-id="410d1-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="410d1-126">Creare un modulo intestazione per una pagina</span><span class="sxs-lookup"><span data-stu-id="410d1-126">Create a header module for a page</span></span>

<span data-ttu-id="410d1-127">Per creare un modulo Intestazione, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="410d1-127">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="410d1-128">Creare un frammento denominato **Frammento intestazione** e aggiungervi un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="410d1-128">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="410d1-129">Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="410d1-129">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="410d1-130">Aggiungere i moduli banner e consenso per i cookie al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="410d1-130">Add promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="410d1-131">Aggiungere un altro modulo contenitore al frammento e impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="410d1-131">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="410d1-132">Aggiungere un modulo intestazione al secondo modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="410d1-132">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="410d1-133">Nello slot **Menu di navigazione** del modulo intestazione, aggiungere un modulo menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="410d1-133">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="410d1-134">Nel riquadro delle proprietà per il modulo menu di navigazione, configurare le proprietà del modulo menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="410d1-134">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="410d1-135">Nello slot **Cerca** del modulo intestazione, aggiungere un modulo ricerca.</span><span class="sxs-lookup"><span data-stu-id="410d1-135">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="410d1-136">Nel riquadro delle proprietà per il modulo ricerca, configurare le proprietà del modulo ricerca.</span><span class="sxs-lookup"><span data-stu-id="410d1-136">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="410d1-137">Salvare il frammento di pagina, finalizzare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="410d1-137">Save the page fragment, finish editing it, and publish it.</span></span> 

<span data-ttu-id="410d1-138">Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="410d1-138">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="410d1-139">Nello slot **Principale** della pagina predefinita, aggiungere il frammento di pagina intestazione contenente il modulo Intestazione all'intestazione.</span><span class="sxs-lookup"><span data-stu-id="410d1-139">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="410d1-140">Salvare il modello, finalizzare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="410d1-140">Save the template, finish editing it, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="410d1-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="410d1-141">Additional resources</span></span>

[<span data-ttu-id="410d1-142">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="410d1-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="410d1-143">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="410d1-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="410d1-144">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="410d1-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="410d1-145">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="410d1-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="410d1-146">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="410d1-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="410d1-147">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="410d1-147">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="410d1-148">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="410d1-148">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="410d1-149">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="410d1-149">Footer module</span></span>](author-footer-module.md)
