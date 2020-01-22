---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per crearli in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885480"
---
# <a name="header-module"></a><span data-ttu-id="a7023-103">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="a7023-103">Header module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a7023-104">In questo argomento vengono descritti i moduli Intestazione e la procedura per crearli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a7023-104">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a7023-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a7023-105">Overview</span></span>

<span data-ttu-id="a7023-106">Un modulo Intestazione è un contenitore speciale utilizzato per l'hosting di tutti i moduli che verranno visualizzati nell'intestazione di una pagina.</span><span class="sxs-lookup"><span data-stu-id="a7023-106">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="a7023-107">Ad esempio, può includere il logo del sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito e la barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a7023-107">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="a7023-108">Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (ovvero un dispositivo desktop o un dispositivo mobile).</span><span class="sxs-lookup"><span data-stu-id="a7023-108">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="a7023-109">Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="a7023-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="a7023-110">Proprietà di un'intestazione</span><span class="sxs-lookup"><span data-stu-id="a7023-110">Properties of a header</span></span>

<span data-ttu-id="a7023-111">Come i contenitori generici, un modulo Intestazione supporta le proprietà **intestazione** e **larghezza**.</span><span class="sxs-lookup"><span data-stu-id="a7023-111">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="a7023-112">Un modulo Intestazione ha molteplici slot.</span><span class="sxs-lookup"><span data-stu-id="a7023-112">A header module has multiple slots.</span></span> <span data-ttu-id="a7023-113">Ad esempio, sono presenti slot per un messaggio informativo, un menu di navigazione, il logo, una barra di ricerca, l'icona del carrello, l'icona dell'elenco preferenze e informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="a7023-113">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="a7023-114">Ogni slot supporta uno specifico set di moduli.</span><span class="sxs-lookup"><span data-stu-id="a7023-114">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="a7023-115">Moduli disponibili in un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="a7023-115">Modules that are available in a header module</span></span>

<span data-ttu-id="a7023-116">Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:</span><span class="sxs-lookup"><span data-stu-id="a7023-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="a7023-117">**Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici.</span><span class="sxs-lookup"><span data-stu-id="a7023-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="a7023-118">La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="a7023-118">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="a7023-119">Gli elementi configurati vengono quindi visualizzati come navigazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="a7023-119">Configured items then appear as header navigation.</span></span> <span data-ttu-id="a7023-120">Inoltre, è possibile configurare i collegamenti di navigazione statici e possono essere forniti i collegamenti ad altre pagine nel sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a7023-120">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="a7023-121">L'intestazione stessa può essere allineata a sinistra, a destra o al centro.</span><span class="sxs-lookup"><span data-stu-id="a7023-121">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="a7023-122">**Icona del carrello** - L'icona del carrello è un'icona speciale che rappresenta il carrello.</span><span class="sxs-lookup"><span data-stu-id="a7023-122">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="a7023-123">È visualizzata nell'intestazione e indica il numero di articoli nel carrello.</span><span class="sxs-lookup"><span data-stu-id="a7023-123">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="a7023-124">Un collegamento alla pagina carrello deve accompagnare l'icona del carrello, di modo che i clienti possano essere reindirizzati alla pagina carrello quando interagiscono con l'icona.</span><span class="sxs-lookup"><span data-stu-id="a7023-124">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="a7023-125">**Icona dell'elenco preferenze** - L'icona dell'elenco preferenze è visualizzata nell'intestazione e indica il numero di articoli aggiunti all'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="a7023-125">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="a7023-126">Un collegamento alla pagina dell'elenco preferenze deve accompagnare questa icona, di modo che i clienti possano essere reindirizzati alla pagina dell'elenco preferenze quando interagiscono con l'icona.</span><span class="sxs-lookup"><span data-stu-id="a7023-126">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="a7023-127">**Modulo Accesso** - Il modulo Accesso è visualizzato nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="a7023-127">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="a7023-128">Consente ai clienti di accedere al proprio account o di registrarsi per averne uno.</span><span class="sxs-lookup"><span data-stu-id="a7023-128">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="a7023-129">Se il cliente è già registrato, il modulo può essere configurato per visualizzare collegamenti alla pagina dell'account, alla pagina dello storico ordini o a un'altra pagina.</span><span class="sxs-lookup"><span data-stu-id="a7023-129">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="a7023-130">**Modulo Logo** - Questo modulo mostra il logo che rappresenta il rivenditore e il marchio.</span><span class="sxs-lookup"><span data-stu-id="a7023-130">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="a7023-131">È un'immagine con un collegamento.</span><span class="sxs-lookup"><span data-stu-id="a7023-131">It's an image that has a link.</span></span> <span data-ttu-id="a7023-132">Il collegamento è in genere configurato di modo che reindirizzi alla home page. Di conseguenza, i clienti possono tornare rapidamente alla home page da qualsiasi pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="a7023-132">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="a7023-133">**Avviso** - Un avviso viene visualizzato nell'intestazione ed è utilizzato per visualizzare un messaggio inline valido per tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="a7023-133">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="a7023-134">Ad esempio, un avviso può visualizzare un messaggio come "La vendita annuale termina tra 2 giorni".</span><span class="sxs-lookup"><span data-stu-id="a7023-134">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="a7023-135">**Barra di ricerca** - La barra di ricerca consente agli utenti di immettere i termini di ricerca per cercare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="a7023-135">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="a7023-136">Il modulo deve essere configurato con l'URL della pagina dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="a7023-136">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="a7023-137">Il parametro della stringa di query può essere configurato (il valore predefinito è **"q"**).</span><span class="sxs-lookup"><span data-stu-id="a7023-137">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="a7023-138">La barra di ricerca ha uno slot di suggerimento automatico in cui deve essere aggiunto il modulo Suggerimento automatico.</span><span class="sxs-lookup"><span data-stu-id="a7023-138">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="a7023-139">**Suggerimento automatico** - Il modulo Suggerimento automatico visualizza i risultati suggeriti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a7023-139">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="a7023-140">Questi risultati possono essere parole chiave, prodotti o categorie in cui viene trovato il termine di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a7023-140">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="a7023-141">Creare un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="a7023-141">Create a header module</span></span>

<span data-ttu-id="a7023-142">Per creare un modulo Intestazione, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="a7023-142">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="a7023-143">Creare un frammento pagina che include un modulo Intestazione.</span><span class="sxs-lookup"><span data-stu-id="a7023-143">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="a7023-144">Aggiungere moduli agli slot nel modulo Intestazione.</span><span class="sxs-lookup"><span data-stu-id="a7023-144">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="a7023-145">Aggiornare le impostazioni di ciascun modulo.</span><span class="sxs-lookup"><span data-stu-id="a7023-145">Update the settings for each module.</span></span>
1. <span data-ttu-id="a7023-146">Salvare il frammento pagina.</span><span class="sxs-lookup"><span data-stu-id="a7023-146">Save the page fragment.</span></span> 
1. <span data-ttu-id="a7023-147">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="a7023-147">Check in the page, and publish it.</span></span>

<span data-ttu-id="a7023-148">Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="a7023-148">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="a7023-149">Nella pagina predefinita, aggiungere il frammento pagina contenente il modulo Intestazione all'intestazione nello slot principale.</span><span class="sxs-lookup"><span data-stu-id="a7023-149">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="a7023-150">Salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="a7023-150">Save the template.</span></span> 
1. <span data-ttu-id="a7023-151">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="a7023-151">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a7023-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a7023-152">Additional resources</span></span>

[<span data-ttu-id="a7023-153">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="a7023-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a7023-154">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="a7023-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="a7023-155">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="a7023-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="a7023-156">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="a7023-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a7023-157">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="a7023-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a7023-158">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="a7023-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a7023-159">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="a7023-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="a7023-160">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="a7023-160">Footer module</span></span>](author-footer-module.md)
