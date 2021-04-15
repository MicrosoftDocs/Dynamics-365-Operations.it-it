---
title: Modulo indirizzo di spedizione
description: In questo argomento viene descritto il modulo di indirizzo di spedizione e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: fd48a04612159cbe29a2cc7cafea1c9c4c8745b4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795431"
---
# <a name="shipping-address-module"></a><span data-ttu-id="df3c1-103">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="df3c1-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="df3c1-104">In questo argomento viene descritto il modulo di indirizzo di spedizione e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df3c1-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="df3c1-105">Il modulo dell'indirizzo di spedizione consente ai clienti di aggiungere o selezionare l'indirizzo di spedizione per un ordine durante il flusso di check out.</span><span class="sxs-lookup"><span data-stu-id="df3c1-105">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="df3c1-106">Se un cliente è connesso, sono visualizzati tutti gli indirizzi salvati in precedenza per tale cliente e il cliente può scegliere tra di essi.</span><span class="sxs-lookup"><span data-stu-id="df3c1-106">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="df3c1-107">Il cliente può anche aggiungere un nuovo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="df3c1-107">The customer can also add a new address.</span></span> <span data-ttu-id="df3c1-108">Il modulo dell'indirizzo di spedizione viene utilizzato per tutti gli articoli in un ordine che devono essere spediti.</span><span class="sxs-lookup"><span data-stu-id="df3c1-108">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="df3c1-109">I formati degli indirizzi di spedizione possono essere definiti in Commerce headquarters per ogni paese o regione e il modulo dell'indirizzo di spedizione applica le regole specifiche del paese.</span><span class="sxs-lookup"><span data-stu-id="df3c1-109">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="df3c1-110">Quando i clienti immettono un indirizzo di spedizione durante il flusso di check out, hanno la possibilità di salvare l'indirizzo come indirizzo principale.</span><span class="sxs-lookup"><span data-stu-id="df3c1-110">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="df3c1-111">Questa opzione viene visualizzata solo se un cliente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="df3c1-111">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="df3c1-112">Sebbene il modulo dell'indirizzo di spedizione non fornisca la convalida dell'indirizzo, questa funzionalità può essere implementata mediante la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="df3c1-112">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="df3c1-113">L'immagine seguente mostra un esempio di un nuovo modulo Indirizzo di spedizione in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="df3c1-113">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Esempio di un modulo dell'indirizzo di spedizione su una pagina Checkout](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="df3c1-115">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="df3c1-115">Module properties</span></span>

| <span data-ttu-id="df3c1-116">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="df3c1-116">Property name</span></span> | <span data-ttu-id="df3c1-117">Valori</span><span class="sxs-lookup"><span data-stu-id="df3c1-117">Values</span></span> | <span data-ttu-id="df3c1-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df3c1-118">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="df3c1-119">Intestazione</span><span class="sxs-lookup"><span data-stu-id="df3c1-119">Heading</span></span> | <span data-ttu-id="df3c1-120">Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="df3c1-120">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="df3c1-121">Un'intestazione facoltativa per il modulo dell'indirizzo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="df3c1-121">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="df3c1-122">Mostra tipo di indirizzo</span><span class="sxs-lookup"><span data-stu-id="df3c1-122">Show address type</span></span> | <span data-ttu-id="df3c1-123">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="df3c1-123">**True** or **False**</span></span> | <span data-ttu-id="df3c1-124">Se questa proprietà facoltativa è impostata su **True** verrà visualizzato un tipo di indirizzo, ad esempio **Casa** o **Attività commerciale**.</span><span class="sxs-lookup"><span data-stu-id="df3c1-124">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="df3c1-125">Se non viene specificato alcun tipo di indirizzo, l'indirizzo verrà automaticamente salvato come **Tipo**=**Altro**.</span><span class="sxs-lookup"><span data-stu-id="df3c1-125">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |
| <span data-ttu-id="df3c1-126">Abilita suggerimento automatico</span><span class="sxs-lookup"><span data-stu-id="df3c1-126">Enable auto suggestion</span></span>| <span data-ttu-id="df3c1-127">**True** o **False**</span><span class="sxs-lookup"><span data-stu-id="df3c1-127">**True** or **False**</span></span> | <span data-ttu-id="df3c1-128">Se questa proprietà facoltativa è impostata su **True**, verranno forniti suggerimenti di indirizzo automatici.</span><span class="sxs-lookup"><span data-stu-id="df3c1-128">If this optional property is set to **True**, automatic address suggestions will be provided.</span></span> <span data-ttu-id="df3c1-129">Questi suggerimenti sono forniti da Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="df3c1-129">These suggestions are powered by Bing Maps.</span></span> <span data-ttu-id="df3c1-130">Per informazioni su come configurare l'integrazione di Bing Maps per il proprio sito, vedere [Modulo Selettore punto vendita](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="df3c1-130">For information about how to set up Bing Maps integration for your site, see [Store selector module](store-selector.md).</span></span> <span data-ttu-id="df3c1-131">Questa funzionalità è disponibile a partire da Commerce versione 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="df3c1-131">This feature is available as of the Commerce version 10.0.15 release.</span></span>|
|<span data-ttu-id="df3c1-132">Opzioni di suggerimento automatico</span><span class="sxs-lookup"><span data-stu-id="df3c1-132">Auto suggest options</span></span>| <span data-ttu-id="df3c1-133">Un numero</span><span class="sxs-lookup"><span data-stu-id="df3c1-133">A number</span></span>| <span data-ttu-id="df3c1-134">Se i suggerimenti di indirizzo automatici sono abilitati, è possibile specificare opzioni aggiuntive, come il numero massimo di suggerimenti da fornire.</span><span class="sxs-lookup"><span data-stu-id="df3c1-134">If automatic address suggestions are enabled, you can specify additional options, such as the maximum number of suggestions that should be provided.</span></span>|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="df3c1-135">Aggiungere un modulo di indirizzi di spedizione a una pagina Checkout e impostare le proprietà necessarie</span><span class="sxs-lookup"><span data-stu-id="df3c1-135">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="df3c1-136">Un modulo di indirizzi di spedizione può essere aggiunto solo a un modulo checkout.</span><span class="sxs-lookup"><span data-stu-id="df3c1-136">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="df3c1-137">Per ulteriori informazioni su come configurare il modulo di indirizzi di spedizione e aggiungerlo a una pagina di checkout, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="df3c1-137">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df3c1-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="df3c1-138">Additional resources</span></span>

[<span data-ttu-id="df3c1-139">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="df3c1-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="df3c1-140">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="df3c1-140">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="df3c1-141">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="df3c1-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="df3c1-142">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="df3c1-142">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="df3c1-143">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="df3c1-143">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="df3c1-144">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="df3c1-144">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="df3c1-145">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="df3c1-145">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="df3c1-146">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="df3c1-146">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="df3c1-147">Memorizzare il modulo di selezione</span><span class="sxs-lookup"><span data-stu-id="df3c1-147">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]