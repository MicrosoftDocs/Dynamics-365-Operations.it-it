---
title: Modulo Conferma ordine
description: In questo argomento vengono descritti i moduli Conferma ordine e la procedura per usarli in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bf33ebf9c0c5136f40fcd7e1012988d186c4169b
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2020
ms.locfileid: "4413619"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="c4a6e-103">Modulo conferma ordine</span><span class="sxs-lookup"><span data-stu-id="c4a6e-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c4a6e-104">In questo argomento vengono descritti i moduli Conferma ordine e la procedura per usarli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c4a6e-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c4a6e-105">Overview</span></span>

<span data-ttu-id="c4a6e-106">Il modulo Conferma ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-106">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="c4a6e-107">Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento, le opzioni di ritiro e il metodo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="c4a6e-108">Proprietà del modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="c4a6e-108">Order confirmation module properties</span></span>

| <span data-ttu-id="c4a6e-109">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="c4a6e-109">Property name</span></span>  | <span data-ttu-id="c4a6e-110">Valori</span><span class="sxs-lookup"><span data-stu-id="c4a6e-110">Values</span></span> | <span data-ttu-id="c4a6e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4a6e-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="c4a6e-112">Intestazione</span><span class="sxs-lookup"><span data-stu-id="c4a6e-112">Heading</span></span>        | <span data-ttu-id="c4a6e-113">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="c4a6e-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="c4a6e-114">Il modulo Conferma ordine può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="c4a6e-115">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="c4a6e-116">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="c4a6e-117">Numero contatto</span><span class="sxs-lookup"><span data-stu-id="c4a6e-117">Contact number</span></span> | <span data-ttu-id="c4a6e-118">Text</span><span class="sxs-lookup"><span data-stu-id="c4a6e-118">Text</span></span> | <span data-ttu-id="c4a6e-119">È possibile fornire un numero di contatto per domande relative all'ordine.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-119">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="c4a6e-120">Mostrare le informazioni sulla fascia oraria per il ritiro</span><span class="sxs-lookup"><span data-stu-id="c4a6e-120">Show pickup timeslot information</span></span> | <span data-ttu-id="c4a6e-121">True o false</span><span class="sxs-lookup"><span data-stu-id="c4a6e-121">True or False</span></span> | <span data-ttu-id="c4a6e-122">Questa proprietà è disponibile in Dynamics 365 Commerce 10.0.15 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-122">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="c4a6e-123">Quando è impostata su vero, visualizza le informazioni sulla fascia oraria per il ritiro se fornite per un articolo da ritirare</span><span class="sxs-lookup"><span data-stu-id="c4a6e-123">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="c4a6e-124">Moduli che possono essere utilizzati in una pagina Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="c4a6e-124">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="c4a6e-125">Quando si crea una pagina Conferma ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-125">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="c4a6e-126">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-126">Here are some examples:</span></span>

- <span data-ttu-id="c4a6e-127">**Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Conferma ordine per suggerire altri prodotti al cliente.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-127">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="c4a6e-128">**Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Conferma ordine per visualizzare contenuti di marketing.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-128">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="c4a6e-129">Aggiungere un un modulo Conferma ordine a una pagina</span><span class="sxs-lookup"><span data-stu-id="c4a6e-129">Add an order confirmation module to a page</span></span>

<span data-ttu-id="c4a6e-130">Per aggiungere un modulo Conferma ordine a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-130">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c4a6e-131">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-131">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="c4a6e-132">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per **Modello Conferma ordine**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-132">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="c4a6e-133">Nello slot **Corpo** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-133">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c4a6e-134">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-134">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c4a6e-135">Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-135">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c4a6e-136">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Conferma ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-136">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c4a6e-137">Seleziona **Salva**, quindi **Anteprima** per visualizzare l'anteprima del modello.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-137">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="c4a6e-138">Non si deve eseguire il rendering del modulo Conferma ordine in quanto richiede il contesto del numero di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-138">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="c4a6e-139">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="c4a6e-140">Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-140">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="c4a6e-141">Nella finestra di dialogo **Scegli un modello**, selezionare **Modello Conferma ordine**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-141">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="c4a6e-142">Sotto **Nome pagina**, immettere **Pagina Conferma ordine** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-142">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="c4a6e-143">Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-143">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c4a6e-144">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Conferma ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-144">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c4a6e-145">Nel riquadro delle proprietà del modulo Conferma ordine, selezionare **Intestazione** accanto al simbolo della matita.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-145">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="c4a6e-146">Nel campo **Titolo dell'intestazione** della finestra di dialogo **Intestazione**, immettere il testo dell'intestazione **Conferma ordine**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-146">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="c4a6e-147">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-147">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="c4a6e-148">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="c4a6e-148">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4a6e-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c4a6e-149">Additional resources</span></span>

[<span data-ttu-id="c4a6e-150">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="c4a6e-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c4a6e-151">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="c4a6e-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="c4a6e-152">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="c4a6e-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c4a6e-153">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="c4a6e-153">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="c4a6e-154">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="c4a6e-154">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="c4a6e-155">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="c4a6e-155">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="c4a6e-156">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="c4a6e-156">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="c4a6e-157">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="c4a6e-157">Gift card module</span></span>](add-giftcard.md)
