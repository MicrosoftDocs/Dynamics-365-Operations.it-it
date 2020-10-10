---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 99457b2c98eae0ddd898f852630d690140a5a4c5
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817012"
---
# <a name="header-module"></a><span data-ttu-id="10b48-103">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="10b48-103">Header module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="10b48-104">In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="10b48-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="10b48-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10b48-105">Overview</span></span>

<span data-ttu-id="10b48-106">In Dynamics 365 Commerce, un'intestazione di pagina è configurata come un frammento di pagina che include l'intestazione, il banner promozionale e i moduli di consenso dei cookie.</span><span class="sxs-lookup"><span data-stu-id="10b48-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="10b48-107">Il modulo intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il modulo dell'icona del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="10b48-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="10b48-108">Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile).</span><span class="sxs-lookup"><span data-stu-id="10b48-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="10b48-109">Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="10b48-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="10b48-110">L'immagine seguente mostra un esempio di modulo Intestazione in una home page.</span><span class="sxs-lookup"><span data-stu-id="10b48-110">The following image shows an example of a header module on a home page.</span></span>

![Esempio di modulo Intestazione](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="10b48-112">Proprietà di un modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="10b48-112">Properties of a header module</span></span>

<span data-ttu-id="10b48-113">Un modulo Intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**.</span><span class="sxs-lookup"><span data-stu-id="10b48-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="10b48-114">Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina.</span><span class="sxs-lookup"><span data-stu-id="10b48-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="10b48-115">Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="10b48-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="10b48-116">La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="10b48-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="10b48-117">Moduli disponibili in un modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="10b48-117">Modules that are available within a header module</span></span>

<span data-ttu-id="10b48-118">Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:</span><span class="sxs-lookup"><span data-stu-id="10b48-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="10b48-119">**Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici.</span><span class="sxs-lookup"><span data-stu-id="10b48-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="10b48-120">Per ulteriori informazioni, vedere [Modulo menu di spostamento](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="10b48-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="10b48-121">**Ricerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti.</span><span class="sxs-lookup"><span data-stu-id="10b48-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="10b48-122">L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="10b48-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="10b48-123">Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="10b48-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="10b48-124">Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.</span><span class="sxs-lookup"><span data-stu-id="10b48-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="10b48-125">**Icona del carrello** - Il modulo Icona carrello rappresenta l'icona del carrello, che mostra in qualsiasi momento il numero di articoli presenti nel carrello.</span><span class="sxs-lookup"><span data-stu-id="10b48-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="10b48-126">Per ulteriori informazioni, vedere [Modulo Icona carrello](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="10b48-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="10b48-127">Creare un frammento Intestazione per una pagina</span><span class="sxs-lookup"><span data-stu-id="10b48-127">Create a header fragment for a page</span></span>

<span data-ttu-id="10b48-128">Per creare un frammento Intestazione, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="10b48-128">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="10b48-129">Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="10b48-129">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="10b48-130">Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-130">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="10b48-131">Selezionare lo slot **Contenitore predefinito** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi schermo**.</span><span class="sxs-lookup"><span data-stu-id="10b48-131">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="10b48-132">Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="10b48-132">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="10b48-133">Nella finestra di dialogo **Aggiungi modulo** selezionare i moduli **Consenso per i cookie**, **Intestazione** e **Banner promozionale**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-133">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="10b48-134">Nel riquadro delle proprietà del modulo **Banner promozionale** selezionare **Aggiungi messaggio** e quindi **Messaggio** .</span><span class="sxs-lookup"><span data-stu-id="10b48-134">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="10b48-135">Nella finestra di dialogo **Messaggio**, aggiungere il testo e i collegamenti per il contenuto promozionale e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-135">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="10b48-136">Nel riquadro delle proprietà del modulo **Consenso per i cookie** aggiungere e configurare il testo e un collegamento alla pagina della privacy del sito.</span><span class="sxs-lookup"><span data-stu-id="10b48-136">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="10b48-137">Nello slot **Menu di navigazione** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="10b48-137">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="10b48-138">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Menu di navigazione** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-138">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="10b48-139">Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Origine menu di spostamento**, selezionare **Retail Server** .</span><span class="sxs-lookup"><span data-stu-id="10b48-139">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="10b48-140">Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Voci di menu statiche** selezionare **Aggiungi voce di menu** e quindi selezionare **Voce di menu** .</span><span class="sxs-lookup"><span data-stu-id="10b48-140">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="10b48-141">Nella finestra di dialogo **Voce di menu**, sotto **Testo voce di menu** inserire "Contatto".</span><span class="sxs-lookup"><span data-stu-id="10b48-141">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="10b48-142">Nella finestra di dialogo **Voce di menu**, sotto **Destinazione collegamento voce di menu** selezionare **Aggiungi un collegamento** .</span><span class="sxs-lookup"><span data-stu-id="10b48-142">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="10b48-143">Nella finestra di dialogo **Aggiungi un collegamento**, selezionare l'URL per la pagina "Contatti" del sito, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-143">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="10b48-144">Nella finestra di dialogo **Voce di menu** selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-144">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="10b48-145">Nello slot **Ricerca** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="10b48-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="10b48-146">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Ricerca** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="10b48-147">Nel riquadro delle proprietà per il modulo Ricerca, configurare le proprietà come necessario.</span><span class="sxs-lookup"><span data-stu-id="10b48-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="10b48-148">Nello slot **Icona carrello** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="10b48-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="10b48-149">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Icona carrello** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="10b48-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="10b48-150">Nel riquadro delle proprietà per il modulo Icona carrello, configurare le proprietà come necessario.</span><span class="sxs-lookup"><span data-stu-id="10b48-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="10b48-151">Se l'icona del carrello deve visualizzare un riepilogo del carrello (noto anche come mini carrello) quando il puntatore del mouse si trova sull'icona, selezionare **Mostra mini carrello**.</span><span class="sxs-lookup"><span data-stu-id="10b48-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="10b48-152">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="10b48-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="10b48-153">Per assicurare che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.</span><span class="sxs-lookup"><span data-stu-id="10b48-153">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="10b48-154">Nello slot **Intestazione** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.</span><span class="sxs-lookup"><span data-stu-id="10b48-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="10b48-155">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="10b48-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="10b48-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="10b48-156">Additional resources</span></span>

[<span data-ttu-id="10b48-157">Panoramica della libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="10b48-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="10b48-158">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="10b48-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="10b48-159">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="10b48-159">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="10b48-160">Modulo banner promozionale</span><span class="sxs-lookup"><span data-stu-id="10b48-160">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="10b48-161">Modulo menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="10b48-161">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="10b48-162">Consenso cookie</span><span class="sxs-lookup"><span data-stu-id="10b48-162">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="10b48-163">Modulo piè di pagina</span><span class="sxs-lookup"><span data-stu-id="10b48-163">Footer module</span></span>](author-footer-module.md)
