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
ms.openlocfilehash: d9626f33ced0433bc96ed58429e95d4f75af6508
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980384"
---
# <a name="gift-card-module"></a><span data-ttu-id="9d6a6-103">Modulo Gift card</span><span class="sxs-lookup"><span data-stu-id="9d6a6-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9d6a6-104">Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9d6a6-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9d6a6-105">Overview</span></span>

<span data-ttu-id="9d6a6-106">I moduli di gift card possono essere utilizzati nei moduli di pagamento per accettare gift card, una forma di pagamento comune utilizzata per le transazioni di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="9d6a6-107">Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="9d6a6-108">Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="9d6a6-109">Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="9d6a6-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9d6a6-110">Il supporto per il riscatto di gift card SVS e Givex durante il flusso di completamento della transazione è disponibile in Dynamics 365 Commerce versione 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-110">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="9d6a6-111">Sono disponibili due moduli di gift card:</span><span class="sxs-lookup"><span data-stu-id="9d6a6-111">There are two gift card modules available:</span></span>

- <span data-ttu-id="9d6a6-112">**Gift card** - Questo modulo può essere utilizzato in una pagina di checkout per riscattare una gift card come offerta.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-112">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="9d6a6-113">**Controllo del saldo della gift card** - Questo modulo può essere utilizzato in qualsiasi pagina per controllare il saldo di una gift card.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-113">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="9d6a6-114">Questo modulo è disponibile in Commerce versione 10.0.14 e successive.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-114">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="9d6a6-115">Il supporto per il modulo di controllo del saldo della gift card regalo è disponibile in Dynamics 365 Commerce versione 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-115">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="9d6a6-116">L'immagine seguente mostra un esempio di un moduli Gift card in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-116">The following image shows an example of a gift card module on a checkout page.</span></span>

![Esempio di moduli Gift card](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="9d6a6-118">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="9d6a6-118">Module properties</span></span>

- <span data-ttu-id="9d6a6-119">**Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-119">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="9d6a6-120">Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-120">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="9d6a6-121">In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-121">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="9d6a6-122">Valori supportati:</span><span class="sxs-lookup"><span data-stu-id="9d6a6-122">Supported values:</span></span>
-   <span data-ttu-id="9d6a6-123">PIN</span><span class="sxs-lookup"><span data-stu-id="9d6a6-123">PIN</span></span>
-   <span data-ttu-id="9d6a6-124">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="9d6a6-124">Expiration date</span></span>
-   <span data-ttu-id="9d6a6-125">PIN e Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="9d6a6-125">PIN and expiration date</span></span> 
-   <span data-ttu-id="9d6a6-126">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="9d6a6-126">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="9d6a6-127">Impostazioni del sito per i moduli Gift card</span><span class="sxs-lookup"><span data-stu-id="9d6a6-127">Site settings for gift card modules</span></span>

<span data-ttu-id="9d6a6-128">In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del moduli Gift card chiamata **Tipo di gift card supportato**.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-128">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="9d6a6-129">Questa impostazione supporta tre valori:</span><span class="sxs-lookup"><span data-stu-id="9d6a6-129">This setting supports three values:</span></span>
- <span data-ttu-id="9d6a6-130">**Gift card Dynamics 365** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-130">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="9d6a6-131">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-131">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="9d6a6-132">**Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-132">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="9d6a6-133">Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-133">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="9d6a6-134">**Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-134">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="9d6a6-135">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-135">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d6a6-136">Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.11 e sono richiesti solo se è necessario il supporto per le gift card SVS o Givex.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-136">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="9d6a6-137">Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="9d6a6-137">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="9d6a6-138">Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="9d6a6-138">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="9d6a6-139">Aggiungere un moduli Gift card a una pagina</span><span class="sxs-lookup"><span data-stu-id="9d6a6-139">Add a gift card module to a page</span></span>

<span data-ttu-id="9d6a6-140">Per istruzioni su come aggiungere un moduli Gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="9d6a6-140">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d6a6-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9d6a6-141">Additional resources</span></span>

[<span data-ttu-id="9d6a6-142">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="9d6a6-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="9d6a6-143">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="9d6a6-143">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="9d6a6-144">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="9d6a6-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="9d6a6-145">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="9d6a6-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="9d6a6-146">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="9d6a6-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="9d6a6-147">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="9d6a6-147">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="9d6a6-148">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="9d6a6-148">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="9d6a6-149">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="9d6a6-149">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="9d6a6-150">Supporto per gift card esterne</span><span class="sxs-lookup"><span data-stu-id="9d6a6-150">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="9d6a6-151">SDK e aggiornamenti libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="9d6a6-151">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
