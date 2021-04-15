---
title: Modulo Icona carrello
description: In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5ff514f07e8b31abe79775e5011bd3f1b24b2935
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793083"
---
# <a name="cart-icon-module"></a><span data-ttu-id="c8303-103">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="c8303-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c8303-104">In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c8303-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c8303-105">Il modulo Icona carrello rappresenta il carrello nel modulo Intestazione della pagina e mostra in qualsiasi momento il numero di articoli presenti nel carrello.</span><span class="sxs-lookup"><span data-stu-id="c8303-105">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="c8303-106">Il modulo Icona carrello mostra anche un riepilogo del carrello (noto anche come mini carrello) quando si passa con il mouse sull'icona del carrello.</span><span class="sxs-lookup"><span data-stu-id="c8303-106">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="c8303-107">Il mini carrello fornisce all'utente un riepilogo degli articoli nel carrello senza dover accedere alla pagina del carrello.</span><span class="sxs-lookup"><span data-stu-id="c8303-107">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="c8303-108">Inoltre, consente all'utente di accedere direttamente alla pagina di pagamento se è soddisfatto del riepilogo.</span><span class="sxs-lookup"><span data-stu-id="c8303-108">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="c8303-109">Ciò riduce il numero di navigazioni della pagina e velocizza il checkout.</span><span class="sxs-lookup"><span data-stu-id="c8303-109">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8303-110">Il supporto per l'utilizzo del modulo dell'icona del carrello è disponibile in Dynamics 365 Commerce versione 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="c8303-110">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="c8303-111">L'immagine seguente mostra un esempio di un modulo Icona carrello che visualizza un mini carrello nell'intestazione Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="c8303-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Esempio di modulo Icona carrello](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="c8303-113">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="c8303-113">Module properties</span></span>

- <span data-ttu-id="c8303-114">**Mostra mini carrello** - Se impostata su vero, questa proprietà consente di visualizzare un riepilogo del carrello (mini carrello) quando si passa con il mouse sull'icona del carrello.</span><span class="sxs-lookup"><span data-stu-id="c8303-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="c8303-115">Questa funzionalità è supportata solo per le porte di visualizzazione desktop.</span><span class="sxs-lookup"><span data-stu-id="c8303-115">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="c8303-116">Aggiungere un modulo Icona carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="c8303-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="c8303-117">Per aggiungere un modulo Icona carrello, vedere [Modulo Intestazione](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="c8303-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c8303-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c8303-118">Additional resources</span></span>

[<span data-ttu-id="c8303-119">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="c8303-119">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c8303-120">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="c8303-120">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c8303-121">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="c8303-121">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="c8303-122">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="c8303-122">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="c8303-123">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="c8303-123">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="c8303-124">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="c8303-124">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="c8303-125">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="c8303-125">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c8303-126">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="c8303-126">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]