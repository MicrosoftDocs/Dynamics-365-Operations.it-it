---
title: Modulo Conferma ordine
description: In questo argomento vengono descritti i moduli Conferma ordine e la procedura per crearli in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698328"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="17265-103">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="17265-103">Order confirmation module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="17265-104">In questo argomento vengono descritti i moduli Conferma ordine e la procedura per crearli in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="17265-104">This topic covers order confirmation modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="17265-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="17265-105">Overview</span></span>

<span data-ttu-id="17265-106">Un modulo Conferma ordine viene utilizzato per visualizzare un messaggio di conferma in una pagina di conferma ordine dopo che l'ordine è stato piazzato.</span><span class="sxs-lookup"><span data-stu-id="17265-106">An order confirmation module is used to show a confirmation message on an order confirmation page after an order is placed.</span></span> <span data-ttu-id="17265-107">Il modulo Conferma ordine mostra il numero di conferma ordine e l'indirizzo di posta elettronica del cliente fornito durante il checkout.</span><span class="sxs-lookup"><span data-stu-id="17265-107">The order confirmation module shows the order confirmation number and the customer email address that was provided during checkout.</span></span>

<span data-ttu-id="17265-108">Quando si effettua un ordine durante il checkout, il numero di conferma ordine e l'indirizzo di posta elettronica del cliente vengono passati alla pagina di conferma ordine come stringa di query nell'URL della pagina.</span><span class="sxs-lookup"><span data-stu-id="17265-108">When an order is placed during checkout, the order confirmation number and customer email address are passed to the order confirmation page as a query string in the page's URL.</span></span> <span data-ttu-id="17265-109">Il modulo Conferma ordine riceve queste informazioni ed esegue il rendering dello stato dell'ordine nella pagina di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="17265-109">The order confirmation module receives this information and renders the order status on the order confirmation page.</span></span> <span data-ttu-id="17265-110">Il modulo Conferma ordine richiede questo contesto di pagina per fornire lo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="17265-110">The order confirmation module requires this page context to provide the status of the order.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="17265-111">Proprietà del modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="17265-111">Order confirmation module properties</span></span>

| <span data-ttu-id="17265-112">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="17265-112">Property name</span></span> | <span data-ttu-id="17265-113">Valori</span><span class="sxs-lookup"><span data-stu-id="17265-113">Values</span></span> | <span data-ttu-id="17265-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17265-114">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="17265-115">Intestazione</span><span class="sxs-lookup"><span data-stu-id="17265-115">Heading</span></span>       | <span data-ttu-id="17265-116">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="17265-116">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="17265-117">Il modulo Conferma ordine può avere un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="17265-117">The order confirmation module can have a heading.</span></span> <span data-ttu-id="17265-118">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="17265-118">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="17265-119">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="17265-119">However, the tag can be changed to meet accessibility requirements.</span></span> |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a><span data-ttu-id="17265-120">Moduli che possono essere utilizzati in un modulo Pagina di conferma ordine</span><span class="sxs-lookup"><span data-stu-id="17265-120">Modules that can be used in an order confirmation page module</span></span> 

- <span data-ttu-id="17265-121">**Suggerimenti** - Il modulo Suggerimenti può essere inserito nella pagina di conferma ordine per suggerire altri prodotti al cliente.</span><span class="sxs-lookup"><span data-stu-id="17265-121">**Recommendations** – The recommendations module can be put on the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="17265-122">**Marketing** - Il modulo Marketing può aggiungere contenuto marketing alla pagina di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="17265-122">**Marketing** – The marketing module can add marketing content to the order confirmation page.</span></span>

## <a name="create-an-order-confirmation-page-module"></a><span data-ttu-id="17265-123">Creare un modulo Pagina di conferma ordine</span><span class="sxs-lookup"><span data-stu-id="17265-123">Create an order confirmation page module</span></span>

1. <span data-ttu-id="17265-124">Creare un modello di pagina denominato **Modello conferma ordine**.</span><span class="sxs-lookup"><span data-stu-id="17265-124">Create a page template that is named **order confirmation template**.</span></span>
1. <span data-ttu-id="17265-125">Nello slot **Principale** della pagina predefinita, aggiungere un modulo Conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="17265-125">In the **Main** slot of the default page, add an order confirmation module.</span></span>
1. <span data-ttu-id="17265-126">Nel modulo Conferma ordine, aggiungere un modulo Suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="17265-126">In the order confirmation module, add a recommendations module.</span></span>
1. <span data-ttu-id="17265-127">Salvare il modello e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="17265-127">Save and preview the template.</span></span> <span data-ttu-id="17265-128">Non si deve eseguire il rendering del modulo Conferma ordine in quanto richiede il contesto del numero di conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="17265-128">The order confirmation module should not be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="17265-129">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="17265-129">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="17265-130">Utilizzare il modello di conferma ordine appena creato per creare una pagina denominata **Pagina conferma ordine**.</span><span class="sxs-lookup"><span data-stu-id="17265-130">Use the order confirmation template that you just created to create a page that is named **order confirmation page**.</span></span>
1. <span data-ttu-id="17265-131">Aggiungere la pagina predefinita alla struttura delle pagine.</span><span class="sxs-lookup"><span data-stu-id="17265-131">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="17265-132">Nello slot **Intestazione**, aggiungere un frammento intestazione.</span><span class="sxs-lookup"><span data-stu-id="17265-132">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="17265-133">Nello slot **Piè di pagina**, aggiungere un frammento piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="17265-133">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="17265-134">Nello slot **Principale**, aggiungere un modulo Conferma ordine.</span><span class="sxs-lookup"><span data-stu-id="17265-134">In the **Main** slot, add an order confirmation module.</span></span>
1. <span data-ttu-id="17265-135">Nel riquadro delle proprietà del modulo Conferma ordine, aggiungere l'intestazione **Conferma ordine**.</span><span class="sxs-lookup"><span data-stu-id="17265-135">In the property pane of the order confirmation module, add the heading **Order confirmation**.</span></span>
1. <span data-ttu-id="17265-136">Sotto il modulo Conferma ordine, aggiungere un modulo Suggerimenti e configurarlo di modo che utilizzi le impostazioni **Novità** e **Più venduti**.</span><span class="sxs-lookup"><span data-stu-id="17265-136">Below the order confirmation module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="17265-137">Salvare la pagina e visualizzarne l'anteprima, quindi archiviare e pubblicare la pagina.</span><span class="sxs-lookup"><span data-stu-id="17265-137">Save and preview the page, check it in, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="17265-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="17265-138">Additional resources</span></span>

[<span data-ttu-id="17265-139">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="17265-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="17265-140">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="17265-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="17265-141">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="17265-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="17265-142">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="17265-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="17265-143">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="17265-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="17265-144">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="17265-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="17265-145">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="17265-145">Footer module</span></span>](author-footer-module.md)
