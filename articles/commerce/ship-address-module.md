---
title: Modulo indirizzo di spedizione
description: In questo argomento viene descritto il modulo di indirizzo di spedizione e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 380d268ec0ba64367f090c31408eac1c54d0ff17
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661443"
---
# <a name="shipping-address-module"></a><span data-ttu-id="07593-103">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="07593-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="07593-104">In questo argomento viene descritto il modulo di indirizzo di spedizione e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="07593-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="07593-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="07593-105">Overview</span></span>

<span data-ttu-id="07593-106">Il modulo dell'indirizzo di spedizione consente ai clienti di aggiungere o selezionare l'indirizzo di spedizione per un ordine durante il flusso di check out.</span><span class="sxs-lookup"><span data-stu-id="07593-106">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="07593-107">Se un cliente è connesso, sono visualizzati tutti gli indirizzi salvati in precedenza per tale cliente e il cliente può scegliere tra di essi.</span><span class="sxs-lookup"><span data-stu-id="07593-107">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="07593-108">Il cliente può anche aggiungere un nuovo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="07593-108">The customer can also add a new address.</span></span> <span data-ttu-id="07593-109">Il modulo dell'indirizzo di spedizione viene utilizzato per tutti gli articoli in un ordine che devono essere spediti.</span><span class="sxs-lookup"><span data-stu-id="07593-109">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="07593-110">I formati degli indirizzi di spedizione possono essere definiti in Commerce headquarters per ogni paese o regione e il modulo dell'indirizzo di spedizione applica le regole specifiche del paese.</span><span class="sxs-lookup"><span data-stu-id="07593-110">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="07593-111">Quando i clienti immettono un indirizzo di spedizione durante il flusso di check out, hanno la possibilità di salvare l'indirizzo come indirizzo principale.</span><span class="sxs-lookup"><span data-stu-id="07593-111">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="07593-112">Questa opzione viene visualizzata solo se un cliente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="07593-112">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="07593-113">Sebbene il modulo dell'indirizzo di spedizione non fornisca la convalida dell'indirizzo, questa funzionalità può essere implementata mediante la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="07593-113">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="07593-114">L'immagine seguente mostra un esempio di un nuovo modulo Indirizzo di spedizione in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="07593-114">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Esempio di un modulo dell'indirizzo di spedizione su una pagina Checkout](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="07593-116">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="07593-116">Module properties</span></span>

| <span data-ttu-id="07593-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="07593-117">Property name</span></span> | <span data-ttu-id="07593-118">Valori</span><span class="sxs-lookup"><span data-stu-id="07593-118">Values</span></span> | <span data-ttu-id="07593-119">descrizione</span><span class="sxs-lookup"><span data-stu-id="07593-119">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="07593-120">Intestazione</span><span class="sxs-lookup"><span data-stu-id="07593-120">Heading</span></span> | <span data-ttu-id="07593-121">Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="07593-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="07593-122">Un'intestazione facoltativa per il modulo dell'indirizzo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="07593-122">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="07593-123">Mostra tipo di indirizzo</span><span class="sxs-lookup"><span data-stu-id="07593-123">Show address type</span></span> | <span data-ttu-id="07593-124">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="07593-124">**True** or **False**</span></span> | <span data-ttu-id="07593-125">Se questa proprietà facoltativa è impostata su **True** verrà visualizzato un tipo di indirizzo, ad esempio **Casa** o **Attività commerciale**.</span><span class="sxs-lookup"><span data-stu-id="07593-125">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="07593-126">Se non viene specificato alcun tipo di indirizzo, l'indirizzo verrà automaticamente salvato come **Tipo**=**Altro**.</span><span class="sxs-lookup"><span data-stu-id="07593-126">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="07593-127">Aggiungere un modulo di indirizzi di spedizione a una pagina Checkout e impostare le proprietà necessarie</span><span class="sxs-lookup"><span data-stu-id="07593-127">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="07593-128">Un modulo di indirizzi di spedizione può essere aggiunto solo a un modulo checkout.</span><span class="sxs-lookup"><span data-stu-id="07593-128">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="07593-129">Per ulteriori informazioni su come configurare il modulo di indirizzi di spedizione e aggiungerlo a una pagina di checkout, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="07593-129">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="07593-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="07593-130">Additional resources</span></span>

[<span data-ttu-id="07593-131">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="07593-131">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="07593-132">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="07593-132">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="07593-133">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="07593-133">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="07593-134">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="07593-134">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="07593-135">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="07593-135">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="07593-136">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="07593-136">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="07593-137">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="07593-137">Gift card module</span></span>](add-giftcard.md)
