---
title: Modulo Carrello
description: In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f21268ed4cffed1d5c789f722796cdf05e965819
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621038"
---
# <a name="cart-module"></a><span data-ttu-id="8080c-103">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="8080c-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8080c-104">In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8080c-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8080c-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8080c-105">Overview</span></span>

<span data-ttu-id="8080c-106">Un modulo Carrello mostra gli articoli che sono stati aggiunti al carrello prima che il cliente proceda al checkout.</span><span class="sxs-lookup"><span data-stu-id="8080c-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="8080c-107">Il modulo mostra anche un riepilogo dell'ordine e consente al cliente di applicare o rimuovere codici promozionali.</span><span class="sxs-lookup"><span data-stu-id="8080c-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="8080c-108">Il modulo Carrello supporta il checkout come utente connesso e il checkout come guest.</span><span class="sxs-lookup"><span data-stu-id="8080c-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="8080c-109">Supporta inoltre il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="8080c-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="8080c-110">È possibile configurare la route per questo collegamento in **Impostazioni sito \> Estensioni \> Route**.</span><span class="sxs-lookup"><span data-stu-id="8080c-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="8080c-111">Il modulo Carrello visualizza i dati in base all'ID carrello, che è un cookie del browser disponibile in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="8080c-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="8080c-112">L'immagine seguente mostra un esempio di una pagina del carrello sul sito Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="8080c-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Esempio di modulo Carrello](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="8080c-114">Proprietà e slot del modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="8080c-114">Cart module properties and slots</span></span>

<span data-ttu-id="8080c-115">Il modulo Carrello ha una proprietà **Intestazione** che può essere impostata su valori come **Carrello della spesa** e **Articoli nel carrello**.</span><span class="sxs-lookup"><span data-stu-id="8080c-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="8080c-116">Moduli che è possibile utilizzare in un modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="8080c-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="8080c-117">**Blocco di testo** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="8080c-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="8080c-118">I messaggi sono gestiti dal sistema di gestione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="8080c-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="8080c-119">È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="8080c-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="8080c-120">**Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="8080c-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="8080c-121">Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze.</span><span class="sxs-lookup"><span data-stu-id="8080c-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="8080c-122">Per ulteriori informazioni su questo modulo, vedere [Modulo Selettore punto vendita](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="8080c-122">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="8080c-123">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="8080c-123">Module properties</span></span>

<span data-ttu-id="8080c-124">Le seguenti impostazioni del modulo Carrello possono essere configurate in **Impostazioni sito \> Estensioni**:</span><span class="sxs-lookup"><span data-stu-id="8080c-124">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="8080c-125">**Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello.</span><span class="sxs-lookup"><span data-stu-id="8080c-125">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="8080c-126">Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="8080c-126">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="8080c-127">**Scorte** - Per informazioni su come applicare le impostazioni relative alle scorte, vedere [Applicare le impostazioni relative alle scorte](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8080c-127">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="8080c-128">**Continua gli acquisti** - Questa proprietà viene utilizzata per specificare la route per il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="8080c-128">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="8080c-129">Il ciclo di lavorazione può essere configurato a livello di sito, consentendo ai rivenditori al dettaglio di riportare il cliente sulla home page o su qualsiasi altra pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="8080c-129">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="8080c-130">Interazione con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="8080c-130">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="8080c-131">Il modulo Carrello recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="8080c-131">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="8080c-132">L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="8080c-132">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="8080c-133">Aggiungere un modulo Carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="8080c-133">Add a cart module to a page</span></span>

<span data-ttu-id="8080c-134">Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8080c-134">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="8080c-135">Andare a **Frammenti pagina** e selezionare **Nuovo** per creare un nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="8080c-135">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="8080c-136">Nella finestra di dialogo **Nuovo frammento pagina**, selezionare il modulo **Carrello**.</span><span class="sxs-lookup"><span data-stu-id="8080c-136">In the **New Page Fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="8080c-137">Sotto **Nome frammento pagina**, inserire il nome **Frammento carrello**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8080c-137">Under **Page Fragment Name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="8080c-138">Selezionare lo slot **Carrello**.</span><span class="sxs-lookup"><span data-stu-id="8080c-138">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="8080c-139">Nel riquadro delle proprietà a destra, selezionare il simbolo della matita, immettere il testo dell'intestazione nel campo, quindi selezionare il simbolo del segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="8080c-139">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="8080c-140">Nello slot **Carrello** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="8080c-140">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8080c-141">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Selettore punto vendita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8080c-141">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8080c-142">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="8080c-142">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8080c-143">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="8080c-143">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="8080c-144">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="8080c-144">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="8080c-145">Nell'albero, selezionare lo slot **Corpo**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="8080c-145">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="8080c-146">Nella finestra di dialogo **Seleziona frammento pagina** selezionare il frammento **Frammento carrello** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8080c-146">In the **Select Page Fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8080c-147">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="8080c-147">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8080c-148">Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="8080c-148">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="8080c-149">Nella finestra di dialogo **Scegli un modello**, selezionare il modello creato, quindi immettere un nome di pagina e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8080c-149">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="8080c-150">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="8080c-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="8080c-151">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="8080c-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8080c-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8080c-152">Additional resources</span></span>

[<span data-ttu-id="8080c-153">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="8080c-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8080c-154">Modulo Contenitore</span><span class="sxs-lookup"><span data-stu-id="8080c-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="8080c-155">Modulo Selettore punto vendita</span><span class="sxs-lookup"><span data-stu-id="8080c-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="8080c-156">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="8080c-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8080c-157">Modulo Icona carrello</span><span class="sxs-lookup"><span data-stu-id="8080c-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="8080c-158">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="8080c-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8080c-159">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="8080c-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="8080c-160">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="8080c-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="8080c-161">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="8080c-161">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="8080c-162">Calcolare la disponibilità scorte per i canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="8080c-162">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
