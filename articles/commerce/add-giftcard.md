---
title: Modulo Gift card
description: Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c024cc1b16ca60b2277eba2d7045020c2e67c3a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206297"
---
# <a name="gift-card-module"></a><span data-ttu-id="4e9b3-103">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="4e9b3-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4e9b3-104">Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4e9b3-105">I moduli di gift card possono essere utilizzati nei moduli di pagamento per accettare gift card, una forma di pagamento comune utilizzata per le transazioni di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="4e9b3-106">Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="4e9b3-107">Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="4e9b3-108">Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="4e9b3-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4e9b3-109">Il supporto per il riscatto di gift card SVS e Givex durante il flusso di completamento della transazione è disponibile in Dynamics 365 Commerce versione 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="4e9b3-110">Sono disponibili due moduli di gift card:</span><span class="sxs-lookup"><span data-stu-id="4e9b3-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="4e9b3-111">**Gift card** - Questo modulo può essere utilizzato in una pagina di checkout per riscattare una gift card come offerta.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="4e9b3-112">**Controllo del saldo della gift card** - Questo modulo può essere utilizzato in qualsiasi pagina per controllare il saldo di una gift card.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="4e9b3-113">Questo modulo è disponibile in Commerce versione 10.0.14 e successive.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="4e9b3-114">Il supporto per il modulo di controllo del saldo della gift card regalo è disponibile in Dynamics 365 Commerce versione 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="4e9b3-115">L'immagine seguente mostra un esempio di un moduli Gift card in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Esempio di moduli Gift card](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="4e9b3-117">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="4e9b3-117">Module properties</span></span>

- <span data-ttu-id="4e9b3-118">**Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-118">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="4e9b3-119">Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="4e9b3-120">In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="4e9b3-121">Valori supportati:</span><span class="sxs-lookup"><span data-stu-id="4e9b3-121">Supported values:</span></span>
-   <span data-ttu-id="4e9b3-122">PIN</span><span class="sxs-lookup"><span data-stu-id="4e9b3-122">PIN</span></span>
-   <span data-ttu-id="4e9b3-123">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="4e9b3-123">Expiration date</span></span>
-   <span data-ttu-id="4e9b3-124">PIN e Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="4e9b3-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="4e9b3-125">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="4e9b3-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="4e9b3-126">Impostazioni del sito per i moduli Gift card</span><span class="sxs-lookup"><span data-stu-id="4e9b3-126">Site settings for gift card modules</span></span>

<span data-ttu-id="4e9b3-127">In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del moduli Gift card chiamata **Tipo di gift card supportato**.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="4e9b3-128">Questa impostazione supporta tre valori:</span><span class="sxs-lookup"><span data-stu-id="4e9b3-128">This setting supports three values:</span></span>
- <span data-ttu-id="4e9b3-129">**Gift card Dynamics 365** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-129">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="4e9b3-130">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="4e9b3-131">**Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-131">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="4e9b3-132">Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="4e9b3-133">**Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-133">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="4e9b3-134">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e9b3-135">Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.11 e sono richiesti solo se è necessario il supporto per le gift card SVS o Givex.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="4e9b3-136">Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="4e9b3-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="4e9b3-137">Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="4e9b3-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="4e9b3-138">Aggiungere un moduli Gift card a una pagina</span><span class="sxs-lookup"><span data-stu-id="4e9b3-138">Add a gift card module to a page</span></span>

<span data-ttu-id="4e9b3-139">Per istruzioni su come aggiungere un moduli Gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="4e9b3-139">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e9b3-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4e9b3-140">Additional resources</span></span>

[<span data-ttu-id="4e9b3-141">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="4e9b3-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="4e9b3-142">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="4e9b3-142">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="4e9b3-143">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="4e9b3-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="4e9b3-144">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="4e9b3-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="4e9b3-145">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="4e9b3-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="4e9b3-146">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="4e9b3-146">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="4e9b3-147">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="4e9b3-147">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="4e9b3-148">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="4e9b3-148">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="4e9b3-149">Supporto per gift card esterne</span><span class="sxs-lookup"><span data-stu-id="4e9b3-149">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="4e9b3-150">SDK e aggiornamenti libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="4e9b3-150">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]