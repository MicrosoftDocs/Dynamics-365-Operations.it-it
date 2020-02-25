---
title: Modulo Dettagli ordini
description: In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026019"
---
# <a name="order-details-module"></a><span data-ttu-id="8ec86-103">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="8ec86-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8ec86-104">In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8ec86-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8ec86-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8ec86-105">Overview</span></span>

<span data-ttu-id="8ec86-106">Il modulo Dettagli ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8ec86-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="8ec86-107">Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento e il metodo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="8ec86-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="8ec86-108">Proprietà del modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="8ec86-108">Order confirmation module properties</span></span>

| <span data-ttu-id="8ec86-109">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="8ec86-109">Property name</span></span>  | <span data-ttu-id="8ec86-110">Valori</span><span class="sxs-lookup"><span data-stu-id="8ec86-110">Values</span></span> | <span data-ttu-id="8ec86-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ec86-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="8ec86-112">Intestazione</span><span class="sxs-lookup"><span data-stu-id="8ec86-112">Heading</span></span>        | <span data-ttu-id="8ec86-113">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="8ec86-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="8ec86-114">Il modulo Conferma ordine può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8ec86-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="8ec86-115">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8ec86-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="8ec86-116">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="8ec86-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="8ec86-117">Numero contatto</span><span class="sxs-lookup"><span data-stu-id="8ec86-117">Contact number</span></span> | <span data-ttu-id="8ec86-118">Text</span><span class="sxs-lookup"><span data-stu-id="8ec86-118">Text</span></span> | <span data-ttu-id="8ec86-119">È possibile fornire un numero di contatto per domande relative all'ordine.</span><span class="sxs-lookup"><span data-stu-id="8ec86-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="8ec86-120">Moduli che possono essere utilizzati in una pagina Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="8ec86-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="8ec86-121">Quando si crea una pagina Dettagli ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Dettagli ordine.</span><span class="sxs-lookup"><span data-stu-id="8ec86-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="8ec86-122">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="8ec86-122">Here are some examples:</span></span>

- <span data-ttu-id="8ec86-123">**Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Dettagli ordine per suggerire altri prodotti al cliente.</span><span class="sxs-lookup"><span data-stu-id="8ec86-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="8ec86-124">**Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Dettagli ordine per visualizzare contenuti di marketing.</span><span class="sxs-lookup"><span data-stu-id="8ec86-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="create-an-order-details-page-module"></a><span data-ttu-id="8ec86-125">Creare un modulo per la pagina Dettagli ordine</span><span class="sxs-lookup"><span data-stu-id="8ec86-125">Create an order details page module</span></span>

1. <span data-ttu-id="8ec86-126">Creare un modello di pagina denominato **Modello Dettagli ordine**.</span><span class="sxs-lookup"><span data-stu-id="8ec86-126">Create a page template that is named **Order details template**.</span></span>
1. <span data-ttu-id="8ec86-127">Nello slot **Principale** della pagina predefinita, aggiungere un modulo Dettagli ordine.</span><span class="sxs-lookup"><span data-stu-id="8ec86-127">In the **Main** slot of the default page, add an order details module.</span></span>
1. <span data-ttu-id="8ec86-128">Nel modulo Dettagli ordine, aggiungere un modulo Suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="8ec86-128">In the order details module, add a recommendations module.</span></span>
1. <span data-ttu-id="8ec86-129">Salvare il modello e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="8ec86-129">Save and preview the template.</span></span> <span data-ttu-id="8ec86-130">Il rendering del modulo Dettagli ordine non verrà eseguito in quanto richiede il contesto del numero di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="8ec86-130">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="8ec86-131">Completare la modifica del modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="8ec86-131">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="8ec86-132">Utilizzare il modello Dettagli ordine appena creato per creare una pagina denominata **Pagina Dettagli ordine**.</span><span class="sxs-lookup"><span data-stu-id="8ec86-132">Use the order details template that you just created to create a page that is named **order details page**.</span></span>
1. <span data-ttu-id="8ec86-133">Aggiungere la pagina predefinita alla struttura delle pagine.</span><span class="sxs-lookup"><span data-stu-id="8ec86-133">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="8ec86-134">Nello slot **Intestazione**, aggiungere un frammento intestazione.</span><span class="sxs-lookup"><span data-stu-id="8ec86-134">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="8ec86-135">Nello slot **Piè di pagina**, aggiungere un frammento piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="8ec86-135">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="8ec86-136">Nello slot **Principale**, aggiungere un modulo Dettagli ordine.</span><span class="sxs-lookup"><span data-stu-id="8ec86-136">In the **Main** slot, add an order details module.</span></span>
1. <span data-ttu-id="8ec86-137">Nel riquadro delle proprietà del modulo Dettagli ordine, aggiungere l'intestazione **Dettagli ordine**.</span><span class="sxs-lookup"><span data-stu-id="8ec86-137">In the property pane for the order details module, add the heading **Order details**.</span></span>
1. <span data-ttu-id="8ec86-138">Sotto il modulo Dettagli ordine, aggiungere un modulo Suggerimenti e configurarlo di modo che utilizzi le impostazioni **Novità** e **Più venduti**.</span><span class="sxs-lookup"><span data-stu-id="8ec86-138">Below the order details module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="8ec86-139">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="8ec86-139">Save and preview the page.</span></span>
1. <span data-ttu-id="8ec86-140">Completare la modifica della pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="8ec86-140">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ec86-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8ec86-141">Additional resources</span></span>

[<span data-ttu-id="8ec86-142">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="8ec86-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8ec86-143">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="8ec86-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="8ec86-144">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="8ec86-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8ec86-145">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="8ec86-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8ec86-146">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="8ec86-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8ec86-147">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="8ec86-147">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="8ec86-148">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="8ec86-148">Footer module</span></span>](author-footer-module.md)
