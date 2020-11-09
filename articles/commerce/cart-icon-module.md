---
title: Modulo Icona carrello
description: In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4ab1609d332b96c0588b06aa086dd4fee944e5d9
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055762"
---
# <a name="cart-icon-module"></a><span data-ttu-id="acfed-103">Modulo Icona carrello</span><span class="sxs-lookup"><span data-stu-id="acfed-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="acfed-104">In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="acfed-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="acfed-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="acfed-105">Overview</span></span>

<span data-ttu-id="acfed-106">Il modulo Icona carrello rappresenta il carrello nel modulo Intestazione della pagina e mostra in qualsiasi momento il numero di articoli presenti nel carrello.</span><span class="sxs-lookup"><span data-stu-id="acfed-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="acfed-107">Il modulo Icona carrello mostra anche un riepilogo del carrello (noto anche come mini carrello) quando si passa con il mouse sull'icona del carrello.</span><span class="sxs-lookup"><span data-stu-id="acfed-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="acfed-108">Il mini carrello fornisce all'utente un riepilogo degli articoli nel carrello senza dover accedere alla pagina del carrello.</span><span class="sxs-lookup"><span data-stu-id="acfed-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="acfed-109">Inoltre, consente all'utente di accedere direttamente alla pagina di pagamento se è soddisfatto del riepilogo.</span><span class="sxs-lookup"><span data-stu-id="acfed-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="acfed-110">Ciò riduce il numero di navigazioni della pagina e velocizza il checkout.</span><span class="sxs-lookup"><span data-stu-id="acfed-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="acfed-111">Il supporto per l'utilizzo del modulo dell'icona del carrello è disponibile in Dynamics 365 Commerce versione 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="acfed-111">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="acfed-112">L'immagine seguente mostra un esempio di un modulo Icona carrello che visualizza un mini carrello nell'intestazione Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="acfed-112">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Esempio di modulo Icona carrello](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="acfed-114">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="acfed-114">Module properties</span></span>

- <span data-ttu-id="acfed-115">**Mostra mini carrello** - Se impostata su vero, questa proprietà consente di visualizzare un riepilogo del carrello (mini carrello) quando si passa con il mouse sull'icona del carrello.</span><span class="sxs-lookup"><span data-stu-id="acfed-115">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="acfed-116">Questa funzionalità è supportata solo per le porte di visualizzazione desktop.</span><span class="sxs-lookup"><span data-stu-id="acfed-116">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="acfed-117">Aggiungere un modulo Icona carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="acfed-117">Add a cart icon module to a page</span></span>

<span data-ttu-id="acfed-118">Per aggiungere un modulo Icona carrello, vedere [Modulo Intestazione](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="acfed-118">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="acfed-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="acfed-119">Additional resources</span></span>

[<span data-ttu-id="acfed-120">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="acfed-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="acfed-121">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="acfed-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="acfed-122">Modulo Pagamento</span><span class="sxs-lookup"><span data-stu-id="acfed-122">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="acfed-123">Modulo Indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="acfed-123">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="acfed-124">Modulo Opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="acfed-124">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="acfed-125">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="acfed-125">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="acfed-126">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="acfed-126">Gift card module</span></span>](add-giftcard.md)
