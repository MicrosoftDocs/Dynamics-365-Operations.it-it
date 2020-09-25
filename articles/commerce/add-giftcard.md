---
title: Modulo Gift card
description: Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4cc947b9d6f3cfa51bce2155170c49e9529d0f7d
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761083"
---
# <a name="gift-card-module"></a><span data-ttu-id="83687-103">Modulo Gift card</span><span class="sxs-lookup"><span data-stu-id="83687-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="83687-104">Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="83687-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="83687-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="83687-105">Overview</span></span>

<span data-ttu-id="83687-106">I moduli di gift card possono essere utilizzati nei moduli di pagamento per accettare gift card, una forma di pagamento comune utilizzata per le transazioni di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="83687-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="83687-107">Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="83687-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="83687-108">Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen.</span><span class="sxs-lookup"><span data-stu-id="83687-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="83687-109">Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="83687-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

<span data-ttu-id="83687-110">Sono disponibili due moduli di gift card:</span><span class="sxs-lookup"><span data-stu-id="83687-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="83687-111">**Gift card** - Questo modulo può essere utilizzato in una pagina di checkout per riscattare una gift card come offerta.</span><span class="sxs-lookup"><span data-stu-id="83687-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="83687-112">**Controllo del saldo della gift card** - Questo modulo può essere utilizzato in qualsiasi pagina per controllare il saldo di una gift card.</span><span class="sxs-lookup"><span data-stu-id="83687-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="83687-113">Questo modulo è disponibile in Commerce versione 10.0.14 e successive.</span><span class="sxs-lookup"><span data-stu-id="83687-113">This module is available in Commerce release 10.0.14 and later.</span></span>

<span data-ttu-id="83687-114">L'immagine seguente mostra un esempio di un moduli Gift card in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="83687-114">The following image shows an example of a gift card module on a checkout page.</span></span>

![Esempio di moduli Gift card](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="83687-116">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="83687-116">Module properties</span></span>

- <span data-ttu-id="83687-117">**Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="83687-117">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="83687-118">Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="83687-118">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="83687-119">In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="83687-119">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="83687-120">Valori supportati:</span><span class="sxs-lookup"><span data-stu-id="83687-120">Supported values:</span></span>
-   <span data-ttu-id="83687-121">PIN</span><span class="sxs-lookup"><span data-stu-id="83687-121">PIN</span></span>
-   <span data-ttu-id="83687-122">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="83687-122">Expiration date</span></span>
-   <span data-ttu-id="83687-123">PIN e Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="83687-123">PIN and expiration date</span></span> 
-   <span data-ttu-id="83687-124">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="83687-124">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="83687-125">Impostazioni del sito per i moduli Gift card</span><span class="sxs-lookup"><span data-stu-id="83687-125">Site settings for gift card modules</span></span>

<span data-ttu-id="83687-126">In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del moduli Gift card chiamata **Tipo di gift card supportato**.</span><span class="sxs-lookup"><span data-stu-id="83687-126">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="83687-127">Questa impostazione supporta tre valori:</span><span class="sxs-lookup"><span data-stu-id="83687-127">This setting supports three values:</span></span>
- <span data-ttu-id="83687-128">**Gift card Dynamics 365** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="83687-128">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="83687-129">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="83687-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="83687-130">**Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="83687-130">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="83687-131">Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="83687-131">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="83687-132">**Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="83687-132">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="83687-133">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="83687-133">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="83687-134">Aggiungere un moduli Gift card a una pagina</span><span class="sxs-lookup"><span data-stu-id="83687-134">Add a gift card module to a page</span></span>

<span data-ttu-id="83687-135">Per istruzioni su come aggiungere un moduli Gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="83687-135">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83687-136">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="83687-136">Additional resources</span></span>

[<span data-ttu-id="83687-137">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="83687-137">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="83687-138">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="83687-138">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="83687-139">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="83687-139">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="83687-140">Modulo Pagamento</span><span class="sxs-lookup"><span data-stu-id="83687-140">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="83687-141">Modulo Indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="83687-141">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="83687-142">Modulo Opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="83687-142">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="83687-143">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="83687-143">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="83687-144">Supporto per gift card esterne</span><span class="sxs-lookup"><span data-stu-id="83687-144">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
