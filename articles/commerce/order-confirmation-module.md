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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 407fc2724d4b589ef5f611974f9358e879dba7ed
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257149"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="edbc9-103">Modulo conferma ordine</span><span class="sxs-lookup"><span data-stu-id="edbc9-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="edbc9-104">In questo argomento vengono descritti i moduli Conferma ordine e la procedura per usarli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="edbc9-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="edbc9-105">Il modulo Conferma ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="edbc9-105">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="edbc9-106">Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento, le opzioni di ritiro e il metodo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="edbc9-106">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="edbc9-107">Proprietà del modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="edbc9-107">Order confirmation module properties</span></span>

| <span data-ttu-id="edbc9-108">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="edbc9-108">Property name</span></span>  | <span data-ttu-id="edbc9-109">Valori</span><span class="sxs-lookup"><span data-stu-id="edbc9-109">Values</span></span> | <span data-ttu-id="edbc9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edbc9-110">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="edbc9-111">Intestazione</span><span class="sxs-lookup"><span data-stu-id="edbc9-111">Heading</span></span>        | <span data-ttu-id="edbc9-112">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="edbc9-112">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="edbc9-113">Il modulo Conferma ordine può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="edbc9-113">The order confirmation module can have a heading.</span></span> <span data-ttu-id="edbc9-114">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="edbc9-114">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="edbc9-115">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="edbc9-115">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="edbc9-116">Numero contatto</span><span class="sxs-lookup"><span data-stu-id="edbc9-116">Contact number</span></span> | <span data-ttu-id="edbc9-117">Text</span><span class="sxs-lookup"><span data-stu-id="edbc9-117">Text</span></span> | <span data-ttu-id="edbc9-118">È possibile fornire un numero di contatto per domande relative all'ordine.</span><span class="sxs-lookup"><span data-stu-id="edbc9-118">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="edbc9-119">Mostrare le informazioni sulla fascia oraria per il ritiro</span><span class="sxs-lookup"><span data-stu-id="edbc9-119">Show pickup timeslot information</span></span> | <span data-ttu-id="edbc9-120">True o false</span><span class="sxs-lookup"><span data-stu-id="edbc9-120">True or False</span></span> | <span data-ttu-id="edbc9-121">Questa proprietà è disponibile in Dynamics 365 Commerce 10.0.15 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="edbc9-121">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="edbc9-122">Quando è impostata su vero, visualizza le informazioni sulla fascia oraria per il ritiro se fornite per un articolo da ritirare</span><span class="sxs-lookup"><span data-stu-id="edbc9-122">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="edbc9-123">Moduli che possono essere utilizzati in una pagina Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="edbc9-123">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="edbc9-124">Quando si crea una pagina Conferma ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="edbc9-124">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="edbc9-125">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="edbc9-125">Here are some examples:</span></span>

- <span data-ttu-id="edbc9-126">**Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Conferma ordine per suggerire altri prodotti al cliente.</span><span class="sxs-lookup"><span data-stu-id="edbc9-126">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="edbc9-127">**Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Conferma ordine per visualizzare contenuti di marketing.</span><span class="sxs-lookup"><span data-stu-id="edbc9-127">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="edbc9-128">Aggiungere un un modulo Conferma ordine a una pagina</span><span class="sxs-lookup"><span data-stu-id="edbc9-128">Add an order confirmation module to a page</span></span>

<span data-ttu-id="edbc9-129">Per aggiungere un modulo Conferma ordine a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="edbc9-129">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="edbc9-130">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="edbc9-130">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="edbc9-131">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per **Modello Conferma ordine**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-131">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="edbc9-132">Nello slot **Corpo** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-132">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="edbc9-133">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-133">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="edbc9-134">Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-134">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="edbc9-135">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Conferma ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-135">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="edbc9-136">Seleziona **Salva**, quindi **Anteprima** per visualizzare l'anteprima del modello.</span><span class="sxs-lookup"><span data-stu-id="edbc9-136">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="edbc9-137">Non si deve eseguire il rendering del modulo Conferma ordine in quanto richiede il contesto del numero di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="edbc9-137">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="edbc9-138">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="edbc9-138">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="edbc9-139">Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="edbc9-139">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="edbc9-140">Nella finestra di dialogo **Scegli un modello**, selezionare **Modello Conferma ordine**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-140">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="edbc9-141">Sotto **Nome pagina**, immettere **Pagina Conferma ordine** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-141">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="edbc9-142">Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-142">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="edbc9-143">Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Conferma ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-143">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="edbc9-144">Nel riquadro delle proprietà del modulo Conferma ordine, selezionare **Intestazione** accanto al simbolo della matita.</span><span class="sxs-lookup"><span data-stu-id="edbc9-144">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="edbc9-145">Nel campo **Titolo dell'intestazione** della finestra di dialogo **Intestazione**, immettere il testo dell'intestazione **Conferma ordine**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbc9-145">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="edbc9-146">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="edbc9-146">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="edbc9-147">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="edbc9-147">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="edbc9-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="edbc9-148">Additional resources</span></span>

[<span data-ttu-id="edbc9-149">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="edbc9-149">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="edbc9-150">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="edbc9-150">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="edbc9-151">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="edbc9-151">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="edbc9-152">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="edbc9-152">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="edbc9-153">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="edbc9-153">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="edbc9-154">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="edbc9-154">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="edbc9-155">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="edbc9-155">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="edbc9-156">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="edbc9-156">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]