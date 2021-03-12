---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1373397c4499ed65835bcc71c6fc628ff356e4e7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991517"
---
# <a name="header-module"></a><span data-ttu-id="b56da-103">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="b56da-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b56da-104">In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b56da-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b56da-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b56da-105">Overview</span></span>

<span data-ttu-id="b56da-106">In Dynamics 365 Commerce, un'intestazione di pagina è configurata come un frammento di pagina che include l'intestazione, il banner promozionale e i moduli di consenso dei cookie.</span><span class="sxs-lookup"><span data-stu-id="b56da-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="b56da-107">Il modulo intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il modulo dell'icona del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b56da-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="b56da-108">Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile).</span><span class="sxs-lookup"><span data-stu-id="b56da-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="b56da-109">Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="b56da-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="b56da-110">L'immagine seguente mostra un esempio di modulo Intestazione in una home page.</span><span class="sxs-lookup"><span data-stu-id="b56da-110">The following image shows an example of a header module on a home page.</span></span>

![Esempio di modulo Intestazione](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="b56da-112">Proprietà di un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="b56da-112">Properties of a header module</span></span>

<span data-ttu-id="b56da-113">Un modulo Intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**.</span><span class="sxs-lookup"><span data-stu-id="b56da-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="b56da-114">Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina.</span><span class="sxs-lookup"><span data-stu-id="b56da-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="b56da-115">Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="b56da-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="b56da-116">La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="b56da-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="b56da-117">Moduli disponibili in un modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="b56da-117">Modules that are available within a header module</span></span>

<span data-ttu-id="b56da-118">Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:</span><span class="sxs-lookup"><span data-stu-id="b56da-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="b56da-119">**Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici.</span><span class="sxs-lookup"><span data-stu-id="b56da-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="b56da-120">Per ulteriori informazioni, vedere [Modulo menu di spostamento](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="b56da-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="b56da-121">**Ricerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti.</span><span class="sxs-lookup"><span data-stu-id="b56da-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="b56da-122">L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="b56da-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="b56da-123">Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b56da-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="b56da-124">Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.</span><span class="sxs-lookup"><span data-stu-id="b56da-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="b56da-125">**Icona del carrello** - Il modulo Icona carrello rappresenta l'icona del carrello, che mostra in qualsiasi momento il numero di articoli presenti nel carrello.</span><span class="sxs-lookup"><span data-stu-id="b56da-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="b56da-126">Per ulteriori informazioni, vedere [Modulo Icona carrello](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="b56da-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="b56da-127">**Selettore sito** - Il modulo di selezione sito consente agli utenti di spostarsi in diversi siti predefiniti, in base al mercato, alle regioni e alle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="b56da-127">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="b56da-128">Per ulteriori informazioni, vedere [Modulo Selettore sito](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="b56da-128">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="b56da-129">**Selettore punto vendita** - Il modulo di selezione punto vendita può essere incluso nello slot di selezione del punto vendita del modulo di intestazione.</span><span class="sxs-lookup"><span data-stu-id="b56da-129">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="b56da-130">Consente agli utenti di spostarsi e trovare i punti vendita nelle vicinanze.</span><span class="sxs-lookup"><span data-stu-id="b56da-130">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="b56da-131">Gli utenti possono anche specificare un punto vendita preferito.</span><span class="sxs-lookup"><span data-stu-id="b56da-131">Users can also specify a preferred store.</span></span> <span data-ttu-id="b56da-132">Quel punto vendita verrà quindi mostrato nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="b56da-132">That store will then be shown in the header.</span></span> <span data-ttu-id="b56da-133">Quando il modulo di selezione punto vendita è incluso nel modulo di intestazione, la proprietà **Modalità** deve essere impostata su **Trova punti vendita**.</span><span class="sxs-lookup"><span data-stu-id="b56da-133">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="b56da-134">Per ulteriori informazioni, vedere [Modulo Selettore punto vendita](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="b56da-134">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="b56da-135">Il supporto per l'utilizzo del modulo dell'icona del carrello nei moduli di intestazione è disponibile in Dynamics 365 Commerce versione 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="b56da-135">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="b56da-136">Il supporto per l'utilizzo del modulo di selezione sito nei moduli di intestazione è disponibile in Dynamics 365 Commerce versione 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="b56da-136">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="b56da-137">Il supporto per l'utilizzo del modulo di selezione punto vendita nei moduli di intestazione è disponibile in Dynamics 365 Commerce versione 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="b56da-137">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="b56da-138">Creare un frammento Intestazione per una pagina</span><span class="sxs-lookup"><span data-stu-id="b56da-138">Create a header fragment for a page</span></span>

<span data-ttu-id="b56da-139">Per creare un frammento Intestazione, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="b56da-139">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="b56da-140">Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="b56da-140">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="b56da-141">Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-141">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="b56da-142">Selezionare lo slot **Contenitore predefinito** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi schermo**.</span><span class="sxs-lookup"><span data-stu-id="b56da-142">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="b56da-143">Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="b56da-143">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b56da-144">Nella finestra di dialogo **Aggiungi modulo** selezionare i moduli **Consenso per i cookie**, **Intestazione** e **Banner promozionale**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-144">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="b56da-145">Nel riquadro delle proprietà del modulo **Banner promozionale** selezionare **Aggiungi messaggio** e quindi **Messaggio** .</span><span class="sxs-lookup"><span data-stu-id="b56da-145">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="b56da-146">Nella finestra di dialogo **Messaggio**, aggiungere il testo e i collegamenti per il contenuto promozionale e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-146">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="b56da-147">Nel riquadro delle proprietà del modulo **Consenso per i cookie** aggiungere e configurare il testo e un collegamento alla pagina della privacy del sito.</span><span class="sxs-lookup"><span data-stu-id="b56da-147">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="b56da-148">Nello slot **Menu di navigazione** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="b56da-148">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b56da-149">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Menu di navigazione** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-149">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b56da-150">Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Origine menu di spostamento**, selezionare **Retail Server** .</span><span class="sxs-lookup"><span data-stu-id="b56da-150">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="b56da-151">Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Voci di menu statiche** selezionare **Aggiungi voce di menu** e quindi selezionare **Voce di menu** .</span><span class="sxs-lookup"><span data-stu-id="b56da-151">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="b56da-152">Nella finestra di dialogo **Voce di menu**, sotto **Testo voce di menu** inserire "Contatto".</span><span class="sxs-lookup"><span data-stu-id="b56da-152">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="b56da-153">Nella finestra di dialogo **Voce di menu**, sotto **Destinazione collegamento voce di menu** selezionare **Aggiungi un collegamento** .</span><span class="sxs-lookup"><span data-stu-id="b56da-153">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="b56da-154">Nella finestra di dialogo **Aggiungi un collegamento**, selezionare l'URL per la pagina "Contatti" del sito, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-154">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="b56da-155">Nella finestra di dialogo **Voce di menu** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-155">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="b56da-156">Nello slot **Ricerca** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="b56da-156">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b56da-157">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Ricerca** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-157">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b56da-158">Nel riquadro delle proprietà per il modulo Ricerca, configurare le proprietà come necessario.</span><span class="sxs-lookup"><span data-stu-id="b56da-158">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="b56da-159">Nello slot **Icona carrello** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="b56da-159">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b56da-160">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Icona carrello** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56da-160">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b56da-161">Nel riquadro delle proprietà per il modulo Icona carrello, configurare le proprietà come necessario.</span><span class="sxs-lookup"><span data-stu-id="b56da-161">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="b56da-162">Se l'icona del carrello deve visualizzare un riepilogo del carrello (noto anche come mini carrello) quando il puntatore del mouse si trova sull'icona, selezionare **Mostra mini carrello**.</span><span class="sxs-lookup"><span data-stu-id="b56da-162">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="b56da-163">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="b56da-163">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="b56da-164">Per assicurare che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="b56da-164">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="b56da-165">Nello slot **Intestazione** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.</span><span class="sxs-lookup"><span data-stu-id="b56da-165">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="b56da-166">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="b56da-166">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b56da-167">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b56da-167">Additional resources</span></span>

[<span data-ttu-id="b56da-168">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="b56da-168">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b56da-169">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="b56da-169">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="b56da-170">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="b56da-170">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="b56da-171">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="b56da-171">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="b56da-172">Modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="b56da-172">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="b56da-173">Consenso cookie</span><span class="sxs-lookup"><span data-stu-id="b56da-173">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="b56da-174">Modulo piè di pagina</span><span class="sxs-lookup"><span data-stu-id="b56da-174">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="b56da-175">Modulo di selezione sito</span><span class="sxs-lookup"><span data-stu-id="b56da-175">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="b56da-176">Memorizzare il modulo di selezione</span><span class="sxs-lookup"><span data-stu-id="b56da-176">Store selector module</span></span>](store-selector.md)
