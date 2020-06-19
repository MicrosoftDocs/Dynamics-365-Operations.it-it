---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: a5f7ad7d9c5ff63c3c3a8fe38275eec0d138891d
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411214"
---
# <a name="header-module"></a><span data-ttu-id="12017-103">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="12017-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="12017-104">In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="12017-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="12017-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="12017-105">Overview</span></span>

<span data-ttu-id="12017-106">In Dynamics 365 Commerce, un'intestazione di pagina comprende più moduli, come i moduli Intestazione, Menu di navigazione, Ricerca, Banner promozionale e Consenso per i cookie.</span><span class="sxs-lookup"><span data-stu-id="12017-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="12017-107">Il modulo Intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il simbolo del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="12017-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="12017-108">Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile).</span><span class="sxs-lookup"><span data-stu-id="12017-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="12017-109">Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="12017-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="12017-110">L'immagine seguente mostra un esempio di modulo Intestazione in una home page.</span><span class="sxs-lookup"><span data-stu-id="12017-110">The following image shows an example of a header module on a home page.</span></span>

![Esempio di modulo Intestazione](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="12017-112">Proprietà di un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="12017-112">Properties of a header module</span></span>

<span data-ttu-id="12017-113">Un modulo Intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**.</span><span class="sxs-lookup"><span data-stu-id="12017-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="12017-114">Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina.</span><span class="sxs-lookup"><span data-stu-id="12017-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="12017-115">Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="12017-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="12017-116">La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="12017-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="12017-117">Moduli disponibili in un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="12017-117">Modules that are available in a header module</span></span>

<span data-ttu-id="12017-118">Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:</span><span class="sxs-lookup"><span data-stu-id="12017-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="12017-119">**Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici.</span><span class="sxs-lookup"><span data-stu-id="12017-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="12017-120">La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="12017-120">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="12017-121">Il menu di navigazione presenta una proprietà **Origine navigazione** utilizzata per specificare le voci di menu di navigazione di Retail Server e le voci di menu statico come origine.</span><span class="sxs-lookup"><span data-stu-id="12017-121">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="12017-122">Se le voci di menu statico vengono specificate come origine, è possibile fornire collegamenti relativi ad altre pagine del sito.</span><span class="sxs-lookup"><span data-stu-id="12017-122">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="12017-123">Gli elementi configurati vengono quindi visualizzati come navigazione intestazione.</span><span class="sxs-lookup"><span data-stu-id="12017-123">Configured items then appear as header navigation.</span></span> 

- <span data-ttu-id="12017-124">**Ricerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti.</span><span class="sxs-lookup"><span data-stu-id="12017-124">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="12017-125">L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="12017-125">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="12017-126">Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="12017-126">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="12017-127">Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.</span><span class="sxs-lookup"><span data-stu-id="12017-127">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="12017-128">**Icona del carrello** - Il modulo Icona carrello rappresenta l'icona del carrello, che mostra in qualsiasi momento il numero di articoli presenti nel carrello.</span><span class="sxs-lookup"><span data-stu-id="12017-128">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="12017-129">Per ulteriori informazioni, vedere [Modulo Icona carrello](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="12017-129">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="12017-130">Creare un modulo Intestazione per una pagina</span><span class="sxs-lookup"><span data-stu-id="12017-130">Create a header module for a page</span></span>

<span data-ttu-id="12017-131">Per creare un modulo Intestazione, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="12017-131">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="12017-132">Andare a **Frammenti pagina** e selezionare **Nuovo** per creare un nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="12017-132">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="12017-133">Nella finestra di dialogo **Nuovo frammento pagina**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="12017-133">In the **New Page Fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="12017-134">Selezionare lo slot **Contenitore predefinito** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="12017-134">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="12017-135">Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="12017-135">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="12017-136">Nella finestra di dialogo **Aggiungi modulo** selezionare i moduli **Banner promozionale** e **Consenso per i cookie**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="12017-136">In the **Add Module** dialog box, select the **Promo banner** and **Cookie consent** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="12017-137">Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="12017-137">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="12017-138">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="12017-138">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="12017-139">Selezionare lo slot **Contenitore** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi contenitore**.</span><span class="sxs-lookup"><span data-stu-id="12017-139">Select the **Container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="12017-140">Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="12017-140">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="12017-141">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Intestazione** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="12017-141">In the **Add Module** dialog box, select the **Header** module, and then select **OK**.</span></span>
1. <span data-ttu-id="12017-142">Nello slot **Menu di navigazione** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="12017-142">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="12017-143">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Menu di navigazione** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="12017-143">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="12017-144">Nel riquadro delle proprietà per il modulo Menu di navigazione, configurare le proprietà come necessario.</span><span class="sxs-lookup"><span data-stu-id="12017-144">In the property pane for the navigation menu module, configure the properties as needed.</span></span>
1. <span data-ttu-id="12017-145">Nello slot **Ricerca** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="12017-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="12017-146">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Ricerca** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="12017-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="12017-147">Nel riquadro delle proprietà per il modulo Ricerca, configurare le proprietà come necessario.</span><span class="sxs-lookup"><span data-stu-id="12017-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="12017-148">Nello slot **Icona carrello** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="12017-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="12017-149">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Icona carrello** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="12017-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="12017-150">Nel riquadro delle proprietà per il modulo Icona carrello, configurare le proprietà come necessario.</span><span class="sxs-lookup"><span data-stu-id="12017-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="12017-151">Se l'icona del carrello deve visualizzare un riepilogo del carrello (noto anche come mini carrello) quando il puntatore del mouse si trova sull'icona, selezionare **Mostra mini carrello**.</span><span class="sxs-lookup"><span data-stu-id="12017-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="12017-152">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="12017-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="12017-153">Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="12017-153">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="12017-154">Nello slot **Intestazione** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.</span><span class="sxs-lookup"><span data-stu-id="12017-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="12017-155">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="12017-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="12017-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="12017-156">Additional resources</span></span>

[<span data-ttu-id="12017-157">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="12017-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="12017-158">Modulo Contenitore</span><span class="sxs-lookup"><span data-stu-id="12017-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="12017-159">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="12017-159">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="12017-160">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="12017-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="12017-161">Modulo Icona carrello</span><span class="sxs-lookup"><span data-stu-id="12017-161">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="12017-162">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="12017-162">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="12017-163">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="12017-163">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="12017-164">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="12017-164">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="12017-165">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="12017-165">Footer module</span></span>](author-footer-module.md)
