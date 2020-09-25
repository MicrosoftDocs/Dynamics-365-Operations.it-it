---
title: Modulo Carrello
description: In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 07d121d5a68970dd29f0e77babda735de12871ca
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761131"
---
# <a name="cart-module"></a><span data-ttu-id="8a37a-103">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="8a37a-103">Cart module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="8a37a-104">In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a37a-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8a37a-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8a37a-105">Overview</span></span>

<span data-ttu-id="8a37a-106">Un modulo Carrello mostra gli articoli che sono stati aggiunti al carrello prima che il cliente proceda al checkout.</span><span class="sxs-lookup"><span data-stu-id="8a37a-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="8a37a-107">Il modulo mostra anche un riepilogo dell'ordine e consente al cliente di applicare o rimuovere codici promozionali.</span><span class="sxs-lookup"><span data-stu-id="8a37a-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="8a37a-108">Il modulo Carrello supporta il checkout come utente connesso e il checkout come guest.</span><span class="sxs-lookup"><span data-stu-id="8a37a-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="8a37a-109">Supporta inoltre il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="8a37a-110">È possibile configurare la route per questo collegamento in **Impostazioni sito \> Estensioni \> Route**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="8a37a-111">Il modulo Carrello visualizza i dati in base all'ID carrello, che è un cookie del browser disponibile in tutto il sito.</span><span class="sxs-lookup"><span data-stu-id="8a37a-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="8a37a-112">L'immagine seguente mostra un esempio di una pagina del carrello sul sito Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="8a37a-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Esempio di modulo Carrello](./media/cart2.PNG)

<span data-ttu-id="8a37a-114">L'immagine seguente mostra un esempio di una pagina del carrello sul sito Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="8a37a-114">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="8a37a-115">In questo esempio, è prevista una commissione di gestione per una voce.</span><span class="sxs-lookup"><span data-stu-id="8a37a-115">In this example, there is a handling fee for a line item.</span></span>

![Esempio di modulo Carrello](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="8a37a-117">Proprietà e slot del modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="8a37a-117">Cart module properties and slots</span></span>

| <span data-ttu-id="8a37a-118">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8a37a-118">Property</span></span> | <span data-ttu-id="8a37a-119">Valori</span><span class="sxs-lookup"><span data-stu-id="8a37a-119">Values</span></span> | <span data-ttu-id="8a37a-120">descrizione</span><span class="sxs-lookup"><span data-stu-id="8a37a-120">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="8a37a-121">Intestazione</span><span class="sxs-lookup"><span data-stu-id="8a37a-121">Heading</span></span> | <span data-ttu-id="8a37a-122">Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="8a37a-122">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="8a37a-123">Un'intestazione per il carrello, ad esempio "Carrello della spesa" o "Articoli nel carrello".</span><span class="sxs-lookup"><span data-stu-id="8a37a-123">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="8a37a-124">Mostra errori scorte esaurite</span><span class="sxs-lookup"><span data-stu-id="8a37a-124">Show out of stock errors</span></span> | <span data-ttu-id="8a37a-125">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="8a37a-125">**True** or **False**</span></span> | <span data-ttu-id="8a37a-126">Se questa proprietà è impostata su **True**, la pagina del carrello mostrerà errori relativi alle scorte.</span><span class="sxs-lookup"><span data-stu-id="8a37a-126">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="8a37a-127">Ti consigliamo di impostare questa proprietà su **True** se le verifiche delle scorte disponibili vengono applicate sul sito.</span><span class="sxs-lookup"><span data-stu-id="8a37a-127">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="8a37a-128">Mostra spese di spedizione per voci</span><span class="sxs-lookup"><span data-stu-id="8a37a-128">Show shipping charges for line items</span></span> | <span data-ttu-id="8a37a-129">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="8a37a-129">**True** or **False**</span></span> | <span data-ttu-id="8a37a-130">Se questa proprietà è impostata su **True**, le voci del carrello mostreranno le spese di spedizione, se queste informazioni sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="8a37a-130">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="8a37a-131">Questa funzione non è supportata nel tema Fabrikam, perché gli utenti selezionano la spedizione solo nel flusso di checkout.</span><span class="sxs-lookup"><span data-stu-id="8a37a-131">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="8a37a-132">Tuttavia, questa funzione può essere abililtata in altri flussi di lavoro, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="8a37a-132">However, this feature can be turned on in other workflows if it's applicable.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="8a37a-133">Moduli che è possibile utilizzare in un modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="8a37a-133">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="8a37a-134">**Blocco di testo** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello.</span><span class="sxs-lookup"><span data-stu-id="8a37a-134">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="8a37a-135">I messaggi sono gestiti dal sistema di gestione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="8a37a-135">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="8a37a-136">È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="8a37a-136">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="8a37a-137">**Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="8a37a-137">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="8a37a-138">Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze.</span><span class="sxs-lookup"><span data-stu-id="8a37a-138">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="8a37a-139">Per ulteriori informazioni su questo modulo, vedere [Modulo Selettore punto vendita](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="8a37a-139">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="8a37a-140">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="8a37a-140">Module properties</span></span>

<span data-ttu-id="8a37a-141">Le seguenti impostazioni del modulo Carrello possono essere configurate in **Impostazioni sito \> Estensioni**:</span><span class="sxs-lookup"><span data-stu-id="8a37a-141">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="8a37a-142">**Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello.</span><span class="sxs-lookup"><span data-stu-id="8a37a-142">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="8a37a-143">Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="8a37a-143">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="8a37a-144">**Scorte** - Per informazioni su come applicare le impostazioni relative alle scorte, vedere [Applicare le impostazioni relative alle scorte](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8a37a-144">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="8a37a-145">**Continua gli acquisti** - Questa proprietà viene utilizzata per specificare la route per il collegamento **Continua gli acquisti**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-145">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="8a37a-146">Il ciclo di lavorazione può essere configurato a livello di sito, consentendo ai rivenditori al dettaglio di riportare il cliente sulla home page o su qualsiasi altra pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="8a37a-146">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="8a37a-147">Interazione con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="8a37a-147">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="8a37a-148">Il modulo Carrello recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="8a37a-148">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="8a37a-149">L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="8a37a-149">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="8a37a-150">Aggiungere un modulo Carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="8a37a-150">Add a cart module to a page</span></span>

<span data-ttu-id="8a37a-151">Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="8a37a-151">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="8a37a-152">Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.</span><span class="sxs-lookup"><span data-stu-id="8a37a-152">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="8a37a-153">Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Carrello**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-153">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="8a37a-154">In **Nome frammento**, inserire il nome **Frammento carrello**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-154">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="8a37a-155">Selezionare lo slot **Carrello**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-155">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="8a37a-156">Nel riquadro delle proprietà a destra, selezionare il simbolo della matita, immettere il testo dell'intestazione nel campo, quindi selezionare il simbolo del segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="8a37a-156">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="8a37a-157">Nello slot **Carrello** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-157">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8a37a-158">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Selettore punto vendita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-158">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8a37a-159">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="8a37a-159">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8a37a-160">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="8a37a-160">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="8a37a-161">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="8a37a-161">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="8a37a-162">Nell'albero, selezionare lo slot **Corpo**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi frammento**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-162">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="8a37a-163">Nella finestra di dialogo **Seleziona frammento** selezionare il frammento **Frammento carrello** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-163">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8a37a-164">Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="8a37a-164">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8a37a-165">Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="8a37a-165">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="8a37a-166">Nella finestra di dialogo **Scegli un modello**, selezionare il modello creato, quindi immettere un nome di pagina e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a37a-166">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="8a37a-167">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="8a37a-167">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="8a37a-168">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="8a37a-168">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a37a-169">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8a37a-169">Additional resources</span></span>

[<span data-ttu-id="8a37a-170">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="8a37a-170">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="8a37a-171">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="8a37a-171">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8a37a-172">Modulo Pagamento</span><span class="sxs-lookup"><span data-stu-id="8a37a-172">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="8a37a-173">Modulo Indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="8a37a-173">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="8a37a-174">Modulo Opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="8a37a-174">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="8a37a-175">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="8a37a-175">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="8a37a-176">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="8a37a-176">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="8a37a-177">Calcolare la disponibilità scorte per i canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="8a37a-177">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
