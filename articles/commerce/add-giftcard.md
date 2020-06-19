---
title: Modulo Gift card
description: Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: a8428963e105e422dcd048863c17df0926a409ac
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411114"
---
# <a name="gift-card-module"></a><span data-ttu-id="015c2-103">Modulo Gift card</span><span class="sxs-lookup"><span data-stu-id="015c2-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="015c2-104">Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="015c2-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="015c2-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="015c2-105">Overview</span></span>

<span data-ttu-id="015c2-106">Le gift card sono una forma di pagamento comune e il moduli Gift card può essere utilizzato in un modulo di pagamento per accettare gift card.</span><span class="sxs-lookup"><span data-stu-id="015c2-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="015c2-107">Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="015c2-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="015c2-108">Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen.</span><span class="sxs-lookup"><span data-stu-id="015c2-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="015c2-109">Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="015c2-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

<span data-ttu-id="015c2-110">L'immagine seguente mostra un esempio di un moduli Gift card in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="015c2-110">The following image shows an example of a gift card module on a checkout page.</span></span>

![Esempio di moduli Gift card](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="015c2-112">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="015c2-112">Module properties</span></span>

- <span data-ttu-id="015c2-113">**Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="015c2-113">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="015c2-114">Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="015c2-114">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="015c2-115">In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="015c2-115">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="015c2-116">Valori supportati:</span><span class="sxs-lookup"><span data-stu-id="015c2-116">Supported values:</span></span>
-   <span data-ttu-id="015c2-117">PIN</span><span class="sxs-lookup"><span data-stu-id="015c2-117">PIN</span></span>
-   <span data-ttu-id="015c2-118">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="015c2-118">Expiration date</span></span>
-   <span data-ttu-id="015c2-119">PIN e Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="015c2-119">PIN and expiration date</span></span> 
-   <span data-ttu-id="015c2-120">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="015c2-120">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="015c2-121">Impostazioni del sito per i moduli Gift card</span><span class="sxs-lookup"><span data-stu-id="015c2-121">Site settings for gift card modules</span></span>

<span data-ttu-id="015c2-122">In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del moduli Gift card chiamata **Tipo di gift card supportato**.</span><span class="sxs-lookup"><span data-stu-id="015c2-122">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="015c2-123">Questa impostazione supporta tre valori:</span><span class="sxs-lookup"><span data-stu-id="015c2-123">This setting supports three values:</span></span>
- <span data-ttu-id="015c2-124">**Gift card Dynamics 365** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="015c2-124">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="015c2-125">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="015c2-125">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="015c2-126">**Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="015c2-126">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="015c2-127">Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="015c2-127">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="015c2-128">**Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="015c2-128">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="015c2-129">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="015c2-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="015c2-130">Aggiungere un moduli Gift card a una pagina</span><span class="sxs-lookup"><span data-stu-id="015c2-130">Add a gift card module to a page</span></span>

<span data-ttu-id="015c2-131">Per istruzioni su come aggiungere un moduli Gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="015c2-131">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="015c2-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="015c2-132">Additional resources</span></span>

[<span data-ttu-id="015c2-133">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="015c2-133">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="015c2-134">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="015c2-134">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="015c2-135">Supporto per gift card esterne</span><span class="sxs-lookup"><span data-stu-id="015c2-135">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
