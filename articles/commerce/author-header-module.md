---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: cec138ebefbd2beb2f1cf6302ce58d8bbc5c4bbd
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261446"
---
# <a name="header-module"></a><span data-ttu-id="72939-103">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="72939-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="72939-104">In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="72939-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="72939-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="72939-105">Overview</span></span>

<span data-ttu-id="72939-106">In Dynamics 365 Commerce, un'intestazione di pagina comprende più moduli, come i moduli intestazione, menu di navigazione, ricerca, banner promozionale e consenso per i cookie.</span><span class="sxs-lookup"><span data-stu-id="72939-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="72939-107">Il modulo intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il simbolo del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="72939-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="72939-108">Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile).</span><span class="sxs-lookup"><span data-stu-id="72939-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="72939-109">Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="72939-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="72939-110">Proprietà di un modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="72939-110">Properties of a header module</span></span>

<span data-ttu-id="72939-111">Un modulo intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**.</span><span class="sxs-lookup"><span data-stu-id="72939-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="72939-112">Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina.</span><span class="sxs-lookup"><span data-stu-id="72939-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="72939-113">Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="72939-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="72939-114">La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="72939-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="72939-115">Moduli disponibili in un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="72939-115">Modules that are available in a header module</span></span>

<span data-ttu-id="72939-116">Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:</span><span class="sxs-lookup"><span data-stu-id="72939-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="72939-117">**Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici.</span><span class="sxs-lookup"><span data-stu-id="72939-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="72939-118">La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="72939-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="72939-119">Il menu di navigazione presenta una proprietà **Origine navigazione** utilizzata per specificare le voci di menu di navigazione di Retail Server e le voci di menu statico come origine.</span><span class="sxs-lookup"><span data-stu-id="72939-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="72939-120">Se le voci di menu statico vengono specificate come origine, è possibile fornire collegamenti relativi ad altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="72939-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="72939-121">Gli elementi configurati vengono quindi visualizzati come navigazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="72939-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="72939-122">**Cerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti.</span><span class="sxs-lookup"><span data-stu-id="72939-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="72939-123">L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="72939-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="72939-124">Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="72939-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="72939-125">Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.</span><span class="sxs-lookup"><span data-stu-id="72939-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>
- <span data-ttu-id="72939-126">**Icona del carrello** - Il modulo icona carrello rappresenta l'icona del carrello, che mostra in qualsiasi momento il numero di articoli presenti nel carrello.</span><span class="sxs-lookup"><span data-stu-id="72939-126">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="72939-127">Per ulteriori informazioni, vedere [Modulo icona carrello](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="72939-127">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="72939-128">Creare un modulo intestazione per una pagina</span><span class="sxs-lookup"><span data-stu-id="72939-128">Create a header module for a page</span></span>

<span data-ttu-id="72939-129">Per creare un modulo Intestazione, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="72939-129">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="72939-130">Creare un frammento denominato **Frammento intestazione** e aggiungervi un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="72939-130">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="72939-131">Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="72939-131">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="72939-132">Aggiungere un modulo banner promozionale e consenso per i cookie al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="72939-132">Add a promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="72939-133">Aggiungere un altro modulo contenitore al frammento e impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="72939-133">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="72939-134">Aggiungere un modulo intestazione al secondo modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="72939-134">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="72939-135">Nello slot **Menu di navigazione** del modulo intestazione, aggiungere un modulo menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="72939-135">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="72939-136">Nel riquadro delle proprietà per il modulo menu di navigazione, configurare le proprietà del modulo menu di navigazione.</span><span class="sxs-lookup"><span data-stu-id="72939-136">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="72939-137">Nello slot **Cerca** del modulo intestazione, aggiungere un modulo ricerca.</span><span class="sxs-lookup"><span data-stu-id="72939-137">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="72939-138">Nel riquadro delle proprietà per il modulo ricerca, configurare le proprietà del modulo ricerca.</span><span class="sxs-lookup"><span data-stu-id="72939-138">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="72939-139">Nello slot **Icona carrello** del modulo intestazione, aggiungere un modulo icona carrello.</span><span class="sxs-lookup"><span data-stu-id="72939-139">In the **Cart icon** slot of the header module, add a cart icon module.</span></span> 
1. <span data-ttu-id="72939-140">Nel riquadro delle proprietà per il modulo icona carrello, configurare le proprietà del modulo icona carrello.</span><span class="sxs-lookup"><span data-stu-id="72939-140">In the property pane for the cart icon module, configure the properties of the cart icon module.</span></span> <span data-ttu-id="72939-141">Se si desidera che l'icona del carrello faccia visualizzare un mini carrello quando si passa con il mouse sopra, selezionare **Vero** per **Mostra mini carrello**.</span><span class="sxs-lookup"><span data-stu-id="72939-141">If you want the cart icon to display a mini cart when hovered over, select **True** for **Show mini cart**.</span></span>
1. <span data-ttu-id="72939-142">Salvare il frammento di pagina, completare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="72939-142">Save the page fragment, finish editing, and publish it.</span></span> 


<span data-ttu-id="72939-143">Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="72939-143">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="72939-144">Nello slot **Principale** della pagina predefinita, aggiungere il frammento di pagina intestazione contenente il modulo Intestazione all'intestazione.</span><span class="sxs-lookup"><span data-stu-id="72939-144">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="72939-145">Salvare il modello, completare la modifica e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="72939-145">Save the template, finish editing, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72939-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="72939-146">Additional resources</span></span>

[<span data-ttu-id="72939-147">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="72939-147">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="72939-148">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="72939-148">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="72939-149">Modulo casella acquisti</span><span class="sxs-lookup"><span data-stu-id="72939-149">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="72939-150">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="72939-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="72939-151">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="72939-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="72939-152">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="72939-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="72939-153">Modulo conferma ordine</span><span class="sxs-lookup"><span data-stu-id="72939-153">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="72939-154">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="72939-154">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="72939-155">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="72939-155">Footer module</span></span>](author-footer-module.md)
