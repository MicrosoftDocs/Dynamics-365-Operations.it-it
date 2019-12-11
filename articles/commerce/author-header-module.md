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
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697277"
---
# <a name="header-module"></a><span data-ttu-id="0d899-103">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="0d899-103">Header module</span></span>

<span data-ttu-id="0d899-104">[!include [banner](includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span><span class="sxs-lookup"><span data-stu-id="0d899-104">[!include [banner]includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span></span>

<span data-ttu-id="0d899-105">In questo argomento vengono descritti i moduli Intestazione e la procedura per crearli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d899-105">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0d899-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0d899-106">Overview</span></span>

<span data-ttu-id="0d899-107">Un modulo Intestazione è un contenitore speciale utilizzato per l'hosting di tutti i moduli che verranno visualizzati nell'intestazione di una pagina.</span><span class="sxs-lookup"><span data-stu-id="0d899-107">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="0d899-108">Ad esempio, può includere il logo del sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito e la barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0d899-108">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="0d899-109">Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (ovvero un dispositivo desktop o un dispositivo mobile).</span><span class="sxs-lookup"><span data-stu-id="0d899-109">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="0d899-110">Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="0d899-110">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="0d899-111">Proprietà di un'intestazione</span><span class="sxs-lookup"><span data-stu-id="0d899-111">Properties of a header</span></span>

<span data-ttu-id="0d899-112">Come i contenitori generici, un modulo Intestazione supporta le proprietà **intestazione** e **larghezza**.</span><span class="sxs-lookup"><span data-stu-id="0d899-112">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="0d899-113">Un modulo Intestazione ha molteplici slot.</span><span class="sxs-lookup"><span data-stu-id="0d899-113">A header module has multiple slots.</span></span> <span data-ttu-id="0d899-114">Ad esempio, sono presenti slot per un messaggio informativo, un menu di navigazione, il logo, una barra di ricerca, l'icona del carrello, l'icona dell'elenco preferenze e informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="0d899-114">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="0d899-115">Ogni slot supporta uno specifico set di moduli.</span><span class="sxs-lookup"><span data-stu-id="0d899-115">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="0d899-116">Moduli disponibili in un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="0d899-116">Modules that are available in a header module</span></span>

<span data-ttu-id="0d899-117">Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:</span><span class="sxs-lookup"><span data-stu-id="0d899-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="0d899-118">**Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici.</span><span class="sxs-lookup"><span data-stu-id="0d899-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="0d899-119">La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="0d899-119">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="0d899-120">Gli elementi configurati vengono quindi visualizzati come navigazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="0d899-120">Configured items then appear as header navigation.</span></span> <span data-ttu-id="0d899-121">Inoltre, è possibile configurare i collegamenti di navigazione statici e possono essere forniti i collegamenti ad altre pagine nel sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d899-121">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="0d899-122">L'intestazione stessa può essere allineata a sinistra, a destra o al centro.</span><span class="sxs-lookup"><span data-stu-id="0d899-122">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="0d899-123">**Icona del carrello** - L'icona del carrello è un'icona speciale che rappresenta il carrello.</span><span class="sxs-lookup"><span data-stu-id="0d899-123">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="0d899-124">È visualizzata nell'intestazione e indica il numero di articoli nel carrello.</span><span class="sxs-lookup"><span data-stu-id="0d899-124">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="0d899-125">Un collegamento alla pagina carrello deve accompagnare l'icona del carrello, di modo che i clienti possano essere reindirizzati alla pagina carrello quando interagiscono con l'icona.</span><span class="sxs-lookup"><span data-stu-id="0d899-125">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="0d899-126">**Icona dell'elenco preferenze** - L'icona dell'elenco preferenze è visualizzata nell'intestazione e indica il numero di articoli aggiunti all'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="0d899-126">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="0d899-127">Un collegamento alla pagina dell'elenco preferenze deve accompagnare questa icona, di modo che i clienti possano essere reindirizzati alla pagina dell'elenco preferenze quando interagiscono con l'icona.</span><span class="sxs-lookup"><span data-stu-id="0d899-127">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="0d899-128">**Modulo Accesso** - Il modulo Accesso è visualizzato nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="0d899-128">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="0d899-129">Consente ai clienti di accedere al proprio account o di registrarsi per averne uno.</span><span class="sxs-lookup"><span data-stu-id="0d899-129">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="0d899-130">Se il cliente è già registrato, il modulo può essere configurato per visualizzare collegamenti alla pagina dell'account, alla pagina dello storico ordini o a un'altra pagina.</span><span class="sxs-lookup"><span data-stu-id="0d899-130">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="0d899-131">**Modulo Logo** - Questo modulo mostra il logo che rappresenta il rivenditore e il marchio.</span><span class="sxs-lookup"><span data-stu-id="0d899-131">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="0d899-132">È un'immagine con un collegamento.</span><span class="sxs-lookup"><span data-stu-id="0d899-132">It's an image that has a link.</span></span> <span data-ttu-id="0d899-133">Il collegamento è in genere configurato di modo che reindirizzi alla home page. Di conseguenza, i clienti possono tornare rapidamente alla home page da qualsiasi pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="0d899-133">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="0d899-134">**Avviso** - Un avviso viene visualizzato nell'intestazione ed è utilizzato per visualizzare un messaggio inline valido per tutte le pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="0d899-134">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="0d899-135">Ad esempio, un avviso può visualizzare un messaggio come "La vendita annuale termina tra 2 giorni".</span><span class="sxs-lookup"><span data-stu-id="0d899-135">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="0d899-136">**Barra di ricerca** - La barra di ricerca consente agli utenti di immettere i termini di ricerca per cercare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="0d899-136">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="0d899-137">Il modulo deve essere configurato con l'URL della pagina dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="0d899-137">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="0d899-138">Il parametro della stringa di query può essere configurato (il valore predefinito è **"q"**).</span><span class="sxs-lookup"><span data-stu-id="0d899-138">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="0d899-139">La barra di ricerca ha uno slot di suggerimento automatico in cui deve essere aggiunto il modulo Suggerimento automatico.</span><span class="sxs-lookup"><span data-stu-id="0d899-139">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="0d899-140">**Suggerimento automatico** - Il modulo Suggerimento automatico visualizza i risultati suggeriti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d899-140">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="0d899-141">Questi risultati possono essere parole chiave, prodotti o categorie in cui viene trovato il termine di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0d899-141">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="0d899-142">Creare un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="0d899-142">Create a header module</span></span>

<span data-ttu-id="0d899-143">Per creare un modulo Intestazione, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="0d899-143">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="0d899-144">Creare un frammento pagina che include un modulo Intestazione.</span><span class="sxs-lookup"><span data-stu-id="0d899-144">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="0d899-145">Aggiungere moduli agli slot nel modulo Intestazione.</span><span class="sxs-lookup"><span data-stu-id="0d899-145">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="0d899-146">Aggiornare le impostazioni di ciascun modulo.</span><span class="sxs-lookup"><span data-stu-id="0d899-146">Update the settings for each module.</span></span>
1. <span data-ttu-id="0d899-147">Salvare il frammento pagina.</span><span class="sxs-lookup"><span data-stu-id="0d899-147">Save the page fragment.</span></span> 
1. <span data-ttu-id="0d899-148">Archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="0d899-148">Check in the page, and publish it.</span></span>

<span data-ttu-id="0d899-149">Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="0d899-149">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="0d899-150">Nella pagina predefinita, aggiungere il frammento pagina contenente il modulo Intestazione all'intestazione nello slot principale.</span><span class="sxs-lookup"><span data-stu-id="0d899-150">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="0d899-151">Salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="0d899-151">Save the template.</span></span> 
1. <span data-ttu-id="0d899-152">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="0d899-152">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d899-153">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0d899-153">Additional resources</span></span>

[<span data-ttu-id="0d899-154">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="0d899-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0d899-155">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="0d899-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="0d899-156">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="0d899-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0d899-157">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="0d899-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0d899-158">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="0d899-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0d899-159">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="0d899-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="0d899-160">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="0d899-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="0d899-161">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="0d899-161">Footer module</span></span>](author-footer-module.md)
