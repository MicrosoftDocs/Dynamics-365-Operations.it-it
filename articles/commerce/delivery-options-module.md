---
title: Modulo Opzioni di consegna
description: In questo argomento vengono descritte le opzioni di consegna e la procedura per configurarle in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 60449e9492c8e831b4ec6b2896f1ab471ef9d499
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661210"
---
# <a name="delivery-options-module"></a><span data-ttu-id="f76ca-103">Modulo Opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="f76ca-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="f76ca-104">In questo argomento vengono descritte le opzioni di consegna e la procedura per configurarle in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f76ca-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f76ca-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f76ca-105">Overview</span></span>

<span data-ttu-id="f76ca-106">I moduli delle opzioni di consegna consentono ai clienti di selezionare una modalità di consegna come la spedizione o il ritiro per il proprio ordine online.</span><span class="sxs-lookup"><span data-stu-id="f76ca-106">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="f76ca-107">È necessario un indirizzo di spedizione per determinare la modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="f76ca-107">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="f76ca-108">Se l'indirizzo di spedizione viene modificato, le opzioni di consegna devono essere recuperate di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f76ca-108">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="f76ca-109">Se un ordine include solo articoli che verranno prelevati in un punto vendita, questo modulo viene automaticamente nascosto.</span><span class="sxs-lookup"><span data-stu-id="f76ca-109">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="f76ca-110">Per informazioni su come configurare le modalità di consegna, vedere [Configurazione del canale online](channel-setup-online.md)e [Imposta la modalità di consegna](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="f76ca-110">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="f76ca-111">Ciascuna modalità di consegna può avere un addebito associato.</span><span class="sxs-lookup"><span data-stu-id="f76ca-111">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="f76ca-112">Per ulteriori informazioni su come attivare configurare le spese di consegna per un punto vendita online, vedere [Addebiti automatici avanzati omnicanale](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="f76ca-112">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="f76ca-113">Nella versione 10.0.13 di Commerce, il modulo delle opzioni di consegna è stato aggiornato per supportare le funzioni **Spese di intestazione senza ripartizione proporzionale** e **Spedizione come spese riga**.</span><span class="sxs-lookup"><span data-stu-id="f76ca-113">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="f76ca-114">Se la ripartizione è disattivata, l'aspettativa è che il flusso di lavoro dell'e-commerce non consentirà una modalità di consegna mista per gli articoli nel carrello (ovvero, alcuni articoli sono selezionati per la spedizione, ma altri sono selezionati per il ritiro).</span><span class="sxs-lookup"><span data-stu-id="f76ca-114">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="f76ca-115">La funzione **Spese di intestazione senza ripartizione proporzionale** richiede che il flag **Abilita la gestione della modalità di consegna coerente nel canale** sia abilitato in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="f76ca-115">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="f76ca-116">Quando questo flag è abilitato, le spese di spedizione verranno applicate a livello di intestazione o a livello di riga, a seconda della configurazione in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="f76ca-116">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="f76ca-117">Il tema Fabrikam supporta una modalità di consegna mista, in cui alcuni articoli vengono selezionati per la spedizione ma altri vengono selezionati per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="f76ca-117">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="f76ca-118">In questa modalità, le spese di spedizione verranno ripartite proporzionalmente per tutti gli articoli selezionati per la modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="f76ca-118">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="f76ca-119">Affinché una modalità di consegna mista funzioni, è necessario prima configurare la funzione **Spese di intestazione senza ripartizione proporzionale** in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="f76ca-119">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="f76ca-120">Per ulteriori informazioni su questa configurazione, vedere [Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="f76ca-120">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="f76ca-121">Se le spese di spedizione si applicano agli articoli, possono essere visualizzate nella riga del carrello per ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="f76ca-121">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="f76ca-122">Questa funzionalità richiede che la proprietà **Mostra le spese di spedizione su una voce** sia abilitata sia per il modulo carrello che per il modulo checkout.</span><span class="sxs-lookup"><span data-stu-id="f76ca-122">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="f76ca-123">Per ulteriori informazioni, vedere [Modulo Carrello](add-cart-module.md) e [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="f76ca-123">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="f76ca-124">L'immagine seguente mostra un esempio di modulo Opzioni di consegna in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="f76ca-124">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Esempio di un modulo Opzioni di consegna su una pagina Checkout](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="f76ca-126">Proprietà del modulo Opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="f76ca-126">Delivery options module properties</span></span>

| <span data-ttu-id="f76ca-127">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f76ca-127">Property</span></span> | <span data-ttu-id="f76ca-128">Valori</span><span class="sxs-lookup"><span data-stu-id="f76ca-128">Values</span></span> | <span data-ttu-id="f76ca-129">descrizione</span><span class="sxs-lookup"><span data-stu-id="f76ca-129">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="f76ca-130">Intestazione</span><span class="sxs-lookup"><span data-stu-id="f76ca-130">Heading</span></span> | <span data-ttu-id="f76ca-131">Testo e tag dell'intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="f76ca-131">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="f76ca-132">Un'intestazione facoltativa per il modulo delle opzioni di consegna.</span><span class="sxs-lookup"><span data-stu-id="f76ca-132">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="f76ca-133">Nome classe CSS personalizzato</span><span class="sxs-lookup"><span data-stu-id="f76ca-133">Custom CSS class name</span></span> | <span data-ttu-id="f76ca-134">Testo</span><span class="sxs-lookup"><span data-stu-id="f76ca-134">Text</span></span> | <span data-ttu-id="f76ca-135">Un nome della classe Cascading Style Sheets ( CSS) che verrà utilizzato per eseguire il rendering di questo modulo, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="f76ca-135">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="f76ca-136">Filtra opzione modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="f76ca-136">Filter Delivery Mode Option</span></span> | <span data-ttu-id="f76ca-137">**Non filtrare** o **Modalità non di spedizione**</span><span class="sxs-lookup"><span data-stu-id="f76ca-137">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="f76ca-138">Un valore che specifica se il modulo Opzioni di consegna deve filtrare tutte le modalità di consegna non di spedizione.</span><span class="sxs-lookup"><span data-stu-id="f76ca-138">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="f76ca-139">Aggiungere un modulo Opzioni di consegna a una pagina Checkout e impostare le proprietà necessarie</span><span class="sxs-lookup"><span data-stu-id="f76ca-139">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="f76ca-140">Un modulo delle opzioni di consegna può essere aggiunto solo a un modulo checkout.</span><span class="sxs-lookup"><span data-stu-id="f76ca-140">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="f76ca-141">Per ulteriori informazioni su come configurare il modulo delle opzioni di consegna e aggiungerlo a una pagina di checkout, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="f76ca-141">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f76ca-142">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f76ca-142">Additional resources</span></span>

[<span data-ttu-id="f76ca-143">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="f76ca-143">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="f76ca-144">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="f76ca-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f76ca-145">Modulo Pagamento</span><span class="sxs-lookup"><span data-stu-id="f76ca-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="f76ca-146">Modulo Indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="f76ca-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="f76ca-147">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="f76ca-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f76ca-148">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="f76ca-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="f76ca-149">Configurazione del canale online</span><span class="sxs-lookup"><span data-stu-id="f76ca-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="f76ca-150">Addebiti automatici avanzati omnicanale</span><span class="sxs-lookup"><span data-stu-id="f76ca-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="f76ca-151">Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti</span><span class="sxs-lookup"><span data-stu-id="f76ca-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="f76ca-152">Imposta la modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="f76ca-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
