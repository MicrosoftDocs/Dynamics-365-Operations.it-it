---
title: Modulo Dettagli ordini
description: In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
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
ms.openlocfilehash: 6610d2abe0a1b03ddd763f9a65fc1dab42f1da1b
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015182"
---
# <a name="order-details-module"></a><span data-ttu-id="5eb52-103">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="5eb52-103">Order details module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5eb52-104">In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5eb52-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5eb52-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5eb52-105">Overview</span></span>

<span data-ttu-id="5eb52-106">Il modulo Dettagli ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="5eb52-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="5eb52-107">Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento e il metodo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="5eb52-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="5eb52-108">Proprietà del modulo Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="5eb52-108">Order details module properties</span></span>

| <span data-ttu-id="5eb52-109">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="5eb52-109">Property name</span></span>  | <span data-ttu-id="5eb52-110">Valori</span><span class="sxs-lookup"><span data-stu-id="5eb52-110">Values</span></span> | <span data-ttu-id="5eb52-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="5eb52-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="5eb52-112">Intestazione</span><span class="sxs-lookup"><span data-stu-id="5eb52-112">Heading</span></span>        | <span data-ttu-id="5eb52-113">Testo e tag di intestazione ( **H1** , **H2** , **H3** , **H4** , **H5** o **H6** )</span><span class="sxs-lookup"><span data-stu-id="5eb52-113">Heading text and heading tag ( **H1** , **H2** , **H3** , **H4** , **H5** , or **H6** )</span></span> | <span data-ttu-id="5eb52-114">Il modulo Dettagli ordine può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="5eb52-114">The order details module can have a heading.</span></span> <span data-ttu-id="5eb52-115">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="5eb52-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="5eb52-116">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="5eb52-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="5eb52-117">Numero contatto</span><span class="sxs-lookup"><span data-stu-id="5eb52-117">Contact number</span></span> | <span data-ttu-id="5eb52-118">Text</span><span class="sxs-lookup"><span data-stu-id="5eb52-118">Text</span></span> | <span data-ttu-id="5eb52-119">È possibile fornire un numero di contatto per domande relative all'ordine.</span><span class="sxs-lookup"><span data-stu-id="5eb52-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="5eb52-120">Moduli che possono essere utilizzati in una pagina Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="5eb52-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="5eb52-121">Quando si crea una pagina Dettagli ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Dettagli ordine.</span><span class="sxs-lookup"><span data-stu-id="5eb52-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="5eb52-122">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="5eb52-122">Here are some examples:</span></span>

- <span data-ttu-id="5eb52-123">**Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Dettagli ordine per suggerire altri prodotti al cliente.</span><span class="sxs-lookup"><span data-stu-id="5eb52-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="5eb52-124">**Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Dettagli ordine per visualizzare contenuti di marketing.</span><span class="sxs-lookup"><span data-stu-id="5eb52-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="5eb52-125">Aggiungi un un modulo Dettagli ordine a una pagina</span><span class="sxs-lookup"><span data-stu-id="5eb52-125">Add an order details module to a page</span></span>

<span data-ttu-id="5eb52-126">Per aggiungere un modulo Dettagli ordine a una nuova pagina e impostare le proprietà necessarie, effettua le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="5eb52-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="5eb52-127">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="5eb52-127">Go to **Templates** , and select **New** to create a new template.</span></span>
1. <span data-ttu-id="5eb52-128">Nella finestra di dialogo **Nuovo modello** , sotto **Nome modello** , immetti un nome per **Modello Dettagli ordine** , quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-128">In the **New Template** dialog box, under **Template name** , enter the name **Order details template** , and then select **OK**.</span></span>
1. <span data-ttu-id="5eb52-129">Nello slot **Corpo** selezionare i puntini di sospensione ( **...** ) quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-129">In the **Body** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5eb52-130">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5eb52-131">Nello slot **Principale** del modulo **Pagina predefinita** , selezionare i puntini di sospensione ( **...** ) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-131">In the **Main** slot of the **Default Page** module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5eb52-132">Nella finestra di dialogo **Aggiungi modulo** , seleziona il modulo **Dettagli ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5eb52-133">Seleziona **Salva** , quindi **Anteprima** per visualizzare l'anteprima del modello.</span><span class="sxs-lookup"><span data-stu-id="5eb52-133">Select **Save** , and then select **Preview** to preview the template.</span></span> <span data-ttu-id="5eb52-134">Il rendering del modulo Dettagli ordine non verrà eseguito in quanto richiede il contesto del numero di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="5eb52-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="5eb52-135">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="5eb52-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="5eb52-136">Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="5eb52-136">Go to **Pages** , and select **New** to create a new page.</span></span>
1. <span data-ttu-id="5eb52-137">Nella finestra di dialogo **Scegli un modello** , seleziona **Modello dettagli ordine**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="5eb52-138">Sotto **Nome pagina** , immetti **Pagina dettagli ordine** e seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-138">Under **Page name** , enter **Order details page** , and then select **OK**.</span></span>
1. <span data-ttu-id="5eb52-139">Nello slot **Principale** del modulo **Pagina predefinita** , selezionare i puntini di sospensione ( **...** ) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-139">In the **Main** slot of the **Default Page** module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="5eb52-140">Nella finestra di dialogo **Aggiungi modulo** , seleziona il modulo **Dettagli ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="5eb52-141">Nel riquadro delle proprietà del modulo Dettagli ordine, seleziona **Intestazione** accanto al simbolo della matita.</span><span class="sxs-lookup"><span data-stu-id="5eb52-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="5eb52-142">Nel campo **Titolo dell'intestazione** della finestra di dialogo **Intestazione** , immetti il testo dell'intestazione **Dettagli ordine** , quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="5eb52-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details** , and then select **OK**.</span></span>
1. <span data-ttu-id="5eb52-143">Selezionare **Salva** , quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="5eb52-143">Select **Save** , and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="5eb52-144">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="5eb52-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5eb52-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5eb52-145">Additional resources</span></span>

[<span data-ttu-id="5eb52-146">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="5eb52-146">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="5eb52-147">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="5eb52-147">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="5eb52-148">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="5eb52-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5eb52-149">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="5eb52-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="5eb52-150">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="5eb52-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="5eb52-151">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="5eb52-151">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="5eb52-152">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="5eb52-152">Gift card module</span></span>](add-giftcard.md)
