---
title: Modulo Icona carrello
description: In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 6771a84118504cd5c8e44302380eb970e4658902
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411091"
---
# <a name="cart-icon-module"></a><span data-ttu-id="19d6b-103">Modulo Icona carrello</span><span class="sxs-lookup"><span data-stu-id="19d6b-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="19d6b-104">In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="19d6b-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="19d6b-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="19d6b-105">Overview</span></span>

<span data-ttu-id="19d6b-106">Il modulo Icona carrello rappresenta il carrello nel modulo Intestazione della pagina e mostra in qualsiasi momento il numero di articoli presenti nel carrello.</span><span class="sxs-lookup"><span data-stu-id="19d6b-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="19d6b-107">Il modulo Icona carrello mostra anche un riepilogo del carrello (noto anche come mini carrello) quando si passa con il mouse sull'icona del carrello.</span><span class="sxs-lookup"><span data-stu-id="19d6b-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="19d6b-108">Il mini carrello fornisce all'utente un riepilogo degli articoli nel carrello senza dover accedere alla pagina del carrello.</span><span class="sxs-lookup"><span data-stu-id="19d6b-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="19d6b-109">Inoltre, consente all'utente di accedere direttamente alla pagina di pagamento se è soddisfatto del riepilogo.</span><span class="sxs-lookup"><span data-stu-id="19d6b-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="19d6b-110">Ciò riduce il numero di navigazioni della pagina e velocizza il checkout.</span><span class="sxs-lookup"><span data-stu-id="19d6b-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

<span data-ttu-id="19d6b-111">L'immagine seguente mostra un esempio di un modulo Icona carrello che visualizza un mini carrello nell'intestazione Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="19d6b-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Esempio di modulo Icona carrello](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="19d6b-113">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="19d6b-113">Module properties</span></span>

- <span data-ttu-id="19d6b-114">**Mostra mini carrello** - Se impostata su vero, questa proprietà consente di visualizzare un riepilogo del carrello (mini carrello) quando si passa con il mouse sull'icona del carrello.</span><span class="sxs-lookup"><span data-stu-id="19d6b-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="19d6b-115">Questa funzionalità è supportata solo per le porte di visualizzazione desktop.</span><span class="sxs-lookup"><span data-stu-id="19d6b-115">This functionality is only supported for desktop view ports.</span></span>


## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="19d6b-116">Aggiungere un modulo Icona carrello a una pagina</span><span class="sxs-lookup"><span data-stu-id="19d6b-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="19d6b-117">Per aggiungere un modulo Icona carrello, vedere [Modulo Intestazione](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="19d6b-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="19d6b-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="19d6b-118">Additional resources</span></span>

[<span data-ttu-id="19d6b-119">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="19d6b-119">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="19d6b-120">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="19d6b-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="19d6b-121">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="19d6b-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="19d6b-122">Modulo Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="19d6b-122">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="19d6b-123">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="19d6b-123">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="19d6b-124">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="19d6b-124">Footer module</span></span>](author-footer-module.md)
