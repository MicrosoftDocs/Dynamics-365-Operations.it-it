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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2ec629d9fd027be01652351ab1c99001e063e30
ms.sourcegitcommit: 49656661c89c864e8e067259a601c3bbceb8bef4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "3464932"
---
# <a name="order-details-module"></a><span data-ttu-id="02b14-103">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="02b14-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="02b14-104">In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="02b14-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="02b14-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="02b14-105">Overview</span></span>

<span data-ttu-id="02b14-106">Il modulo Dettagli ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="02b14-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="02b14-107">Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento e il metodo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="02b14-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="02b14-108">Proprietà del modulo Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="02b14-108">Order details module properties</span></span>

| <span data-ttu-id="02b14-109">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="02b14-109">Property name</span></span>  | <span data-ttu-id="02b14-110">Valori</span><span class="sxs-lookup"><span data-stu-id="02b14-110">Values</span></span> | <span data-ttu-id="02b14-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="02b14-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="02b14-112">Intestazione</span><span class="sxs-lookup"><span data-stu-id="02b14-112">Heading</span></span>        | <span data-ttu-id="02b14-113">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="02b14-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="02b14-114">Il modulo Dettagli ordine può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="02b14-114">The order details module can have a heading.</span></span> <span data-ttu-id="02b14-115">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="02b14-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="02b14-116">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="02b14-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="02b14-117">Numero contatto</span><span class="sxs-lookup"><span data-stu-id="02b14-117">Contact number</span></span> | <span data-ttu-id="02b14-118">Text</span><span class="sxs-lookup"><span data-stu-id="02b14-118">Text</span></span> | <span data-ttu-id="02b14-119">È possibile fornire un numero di contatto per domande relative all'ordine.</span><span class="sxs-lookup"><span data-stu-id="02b14-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="02b14-120">Moduli che possono essere utilizzati in una pagina Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="02b14-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="02b14-121">Quando si crea una pagina Dettagli ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Dettagli ordine.</span><span class="sxs-lookup"><span data-stu-id="02b14-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="02b14-122">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="02b14-122">Here are some examples:</span></span>

- <span data-ttu-id="02b14-123">**Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Dettagli ordine per suggerire altri prodotti al cliente.</span><span class="sxs-lookup"><span data-stu-id="02b14-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="02b14-124">**Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Dettagli ordine per visualizzare contenuti di marketing.</span><span class="sxs-lookup"><span data-stu-id="02b14-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="02b14-125">Aggiungi un un modulo Dettagli ordine a una pagina</span><span class="sxs-lookup"><span data-stu-id="02b14-125">Add an order details module to a page</span></span>

<span data-ttu-id="02b14-126">Per aggiungere un modulo Dettagli ordine a una nuova pagina e impostare le proprietà necessarie, effettua le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="02b14-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="02b14-127">Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="02b14-127">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="02b14-128">Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immetti un nome per **Modello Dettagli ordine**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b14-128">In the **New Template** dialog box, under **Template name**, enter the name **Order details template**, and then select **OK**.</span></span>
1. <span data-ttu-id="02b14-129">Nello slot **Corpo** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="02b14-129">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="02b14-130">Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b14-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="02b14-131">Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="02b14-131">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="02b14-132">Nella finestra di dialogo **Aggiungi modulo**, seleziona il modulo **Dettagli ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b14-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="02b14-133">Seleziona **Salva**, quindi **Anteprima** per visualizzare l'anteprima del modello.</span><span class="sxs-lookup"><span data-stu-id="02b14-133">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="02b14-134">Il rendering del modulo Dettagli ordine non verrà eseguito in quanto richiede il contesto del numero di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="02b14-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="02b14-135">Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="02b14-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="02b14-136">Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="02b14-136">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="02b14-137">Nella finestra di dialogo **Scegli un modello**, seleziona **Modello dettagli ordine**.</span><span class="sxs-lookup"><span data-stu-id="02b14-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="02b14-138">Sotto **Nome pagina**, immetti **Pagina dettagli ordine** e seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b14-138">Under **Page name**, enter **Order details page**, and then select **OK**.</span></span>
1. <span data-ttu-id="02b14-139">Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.</span><span class="sxs-lookup"><span data-stu-id="02b14-139">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="02b14-140">Nella finestra di dialogo **Aggiungi modulo**, seleziona il modulo **Dettagli ordine** quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b14-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="02b14-141">Nel riquadro delle proprietà del modulo Dettagli ordine, seleziona **Intestazione** accanto al simbolo della matita.</span><span class="sxs-lookup"><span data-stu-id="02b14-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="02b14-142">Nel campo **Titolo dell'intestazione** della finestra di dialogo **Intestazione**, immetti il testo dell'intestazione **Dettagli ordine**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b14-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details**, and then select **OK**.</span></span>
1. <span data-ttu-id="02b14-143">Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.</span><span class="sxs-lookup"><span data-stu-id="02b14-143">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="02b14-144">Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="02b14-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02b14-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="02b14-145">Additional resources</span></span>

[<span data-ttu-id="02b14-146">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="02b14-146">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="02b14-147">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="02b14-147">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="02b14-148">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="02b14-148">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="02b14-149">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="02b14-149">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="02b14-150">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="02b14-150">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="02b14-151">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="02b14-151">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="02b14-152">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="02b14-152">Footer module</span></span>](author-footer-module.md)
