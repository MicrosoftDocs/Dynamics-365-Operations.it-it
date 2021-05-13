---
title: Modulo Gift card
description: Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8db7e597241f1fd552f6b960c2b57b0ba83da949
ms.sourcegitcommit: efde05c758b2e02960760d875569d780d77d5550
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "5962765"
---
# <a name="gift-card-module"></a><span data-ttu-id="a3ba1-103">Modulo gift card</span><span class="sxs-lookup"><span data-stu-id="a3ba1-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a3ba1-104">Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a3ba1-105">I moduli di gift card possono essere utilizzati nei moduli di pagamento per accettare gift card, una forma di pagamento comune utilizzata per le transazioni di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="a3ba1-106">Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="a3ba1-107">Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="a3ba1-108">Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="a3ba1-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3ba1-109">Il supporto per il riscatto di gift card SVS e Givex durante il flusso di completamento della transazione è disponibile in Dynamics 365 Commerce versione 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="a3ba1-110">Sono disponibili due moduli di gift card:</span><span class="sxs-lookup"><span data-stu-id="a3ba1-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="a3ba1-111">**Gift card** - Questo modulo può essere utilizzato in una pagina di checkout per riscattare una gift card come offerta.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-111">**Gift card** – This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="a3ba1-112">**Controllo del saldo della gift card** - Questo modulo può essere utilizzato in qualsiasi pagina per controllare il saldo di una gift card.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-112">**Gift card balance check** – This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="a3ba1-113">Questo modulo è disponibile in Commerce versione 10.0.14 e successive.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="a3ba1-114">Il supporto per il modulo di controllo del saldo della gift card regalo è disponibile in Dynamics 365 Commerce versione 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="a3ba1-115">L'immagine seguente mostra un esempio di un moduli Gift card in una pagina checkout.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Esempio di moduli Gift card](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="a3ba1-117">Proprietà del modulo</span><span class="sxs-lookup"><span data-stu-id="a3ba1-117">Module properties</span></span>

- <span data-ttu-id="a3ba1-118">**Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-118">**Show additional fields** – This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="a3ba1-119">Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="a3ba1-120">In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="a3ba1-121">Valori supportati:</span><span class="sxs-lookup"><span data-stu-id="a3ba1-121">Supported values:</span></span>
-   <span data-ttu-id="a3ba1-122">PIN</span><span class="sxs-lookup"><span data-stu-id="a3ba1-122">PIN</span></span>
-   <span data-ttu-id="a3ba1-123">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="a3ba1-123">Expiration date</span></span>
-   <span data-ttu-id="a3ba1-124">PIN e Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="a3ba1-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="a3ba1-125">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="a3ba1-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="a3ba1-126">Impostazioni del sito per i moduli Gift card</span><span class="sxs-lookup"><span data-stu-id="a3ba1-126">Site settings for gift card modules</span></span>

<span data-ttu-id="a3ba1-127">In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del moduli Gift card chiamata **Tipo di gift card supportato**.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="a3ba1-128">Questa impostazione supporta tre valori:</span><span class="sxs-lookup"><span data-stu-id="a3ba1-128">This setting supports three values:</span></span>
- <span data-ttu-id="a3ba1-129">**Gift card Dynamics 365** - Quando si applica questa impostazione, il modulo Gift card consente solo il riscatto di gift card Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-129">**Dynamics 365 gift card** – When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="a3ba1-130">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="a3ba1-131">**Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il modulo Gift card consente solo il riscatto di gift card Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-131">**SVS and Givex gift cards** – When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="a3ba1-132">Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="a3ba1-133">**Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il modulo Gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-133">**Dynamics 365, SVS, and Givex gift cards** – When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="a3ba1-134">Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3ba1-135">Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.11 e sono richiesti solo se è necessario il supporto per le gift card SVS o Givex.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="a3ba1-136">Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="a3ba1-137">Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="a3ba1-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a><span data-ttu-id="a3ba1-138">Estendere le gift card interne per l'uso in punti vendita e-commerce</span><span class="sxs-lookup"><span data-stu-id="a3ba1-138">Extend internal gift cards for use in e-commerce storefronts</span></span>

<span data-ttu-id="a3ba1-139">Per impostazione predefinita, le gift card interni non sono ottimizzati per l'utilizzo in punti vendita di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-139">By default, internal gift cards aren't optimized for use in e-commerce storefronts.</span></span> <span data-ttu-id="a3ba1-140">Pertanto, prima di consentire l'utilizzo delle gift card interne per il pagamento, è necessario configurarle con estensioni che contribuiscano a renderle più sicure.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-140">Therefore, before you allow internal gift cards to be used for payment, you should configure them with extensions that help make them more secure.</span></span> <span data-ttu-id="a3ba1-141">Di seguito sono riportate le aree delle  gift card che dovresti estendere prima di consentire l'utilizzo delle  gift card interne nella produzione:</span><span class="sxs-lookup"><span data-stu-id="a3ba1-141">Here are the gift card areas that you should extend before you allow internal gift cards to be used in production:</span></span>

- <span data-ttu-id="a3ba1-142">**Numero della  gift card** - Le sequenze numeriche vengono utilizzate per generare numeri di  gift card per  gift card interne.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-142">**Gift card number** – Number sequences are used to generate gift card numbers for internal gift cards.</span></span> <span data-ttu-id="a3ba1-143">Poiché le sequenze numeriche possono essere facilmente previste, è necessario estendere la generazione di numeri di gift card in modo che vengano utilizzate stringhe casuali e crittograficamente sicure per i numeri di  gift card emesse.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-143">Because number sequences can easily be predicted, you should extend the generation of gift card numbers so that random, cryptographically secure strings are used for the gift card numbers that are issued.</span></span>
- <span data-ttu-id="a3ba1-144">**GetBalance** - L'API **GetBalance** viene utilizzata per cercare i saldi delle  gift card.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-144">**GetBalance** – The **GetBalance** API is used to look up gift card balances.</span></span> <span data-ttu-id="a3ba1-145">Per impostazione predefinita, l'API è pubblica.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-145">By default, this API public.</span></span> <span data-ttu-id="a3ba1-146">Se non è necessario un PIN per cercare i saldi delle gift card, c'è il rischio che attacchi di forza bruta possano utilizzare l'API **GetBalance** per tentare di cercare i numeri delle gift card che hanno saldi.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-146">If a PIN isn't required to look up gift card balances, there is a risk that brute force attacks could use the **GetBalance** API to try to look up gift card numbers that have balances.</span></span> <span data-ttu-id="a3ba1-147">Implementando sia i requisiti del PIN per  gift card interni sia la limitazione dell'API, puoi contribuire a mitigare il rischio.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-147">By implementing both PIN requirements for internal gift cards and API throttling, you can help mitigate the risk.</span></span>
- <span data-ttu-id="a3ba1-148">**PIN** - Per impostazione predefinita, le  gift card interne non supportano i PIN.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-148">**PIN** – By default, internal gift cards don't support PINs.</span></span> <span data-ttu-id="a3ba1-149">È necessario estendere le gift card interni in modo che sia necessario un PIN per cercare i saldi.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-149">You should extend internal gift cards so that a PIN is required to look up balances.</span></span> <span data-ttu-id="a3ba1-150">Questa funzionalità può essere utilizzata anche per bloccare le gift card dopo tentativi errati consecutivi di inserire il PIN.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-150">This functionality can also be used to lock gift cards after consecutive incorrect attempts to enter the PIN.</span></span>

## <a name="enable-gift-card-payments-for-guest-checkout"></a><span data-ttu-id="a3ba1-151">Abilitare i pagamenti con gift card per il checkout come guest</span><span class="sxs-lookup"><span data-stu-id="a3ba1-151">Enable gift card payments for guest checkout</span></span>

<span data-ttu-id="a3ba1-152">Per impostazione predefinita, i pagamenti con gift card non sono abilitati per il checkout come guest (anonimo).</span><span class="sxs-lookup"><span data-stu-id="a3ba1-152">By default, gift card payments aren't enabled for guest (anonymous) checkout.</span></span> <span data-ttu-id="a3ba1-153">Per abilitarli, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-153">To enable them, follow these steps.</span></span>

1. <span data-ttu-id="a3ba1-154">In Commerce Headquarters vai a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> POS \> Operazioni POS**.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-154">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS Operations**.</span></span>
1. <span data-ttu-id="a3ba1-155">Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) l'intestazione della griglia, quindi seleziona **Inserisci colonne**.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-155">Select and hold (or right-click) the header of the grid, and then select **Insert columns**.</span></span>
1. <span data-ttu-id="a3ba1-156">Nella finestra di dialogo **Inserisci colonne** selezionare la casella di controllo **AllowAnonymousAccess**.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-156">In the **Insert columns** dialog box, select the **AllowAnonymousAccess** check box.</span></span>
1. <span data-ttu-id="a3ba1-157">Selezionare **Aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-157">Select **Update**.</span></span>
1. <span data-ttu-id="a3ba1-158">Per le operazioni **520** (Saldo goft card) e **214**, impostare il valore **AllowAnonymousAccess** su **1**.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-158">For operations **520** (Gift card balance) and **214**, set the **AllowAnonymousAccess** value to **1**.</span></span>
1. <span data-ttu-id="a3ba1-159">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-159">Select **Save**.</span></span>
1. <span data-ttu-id="a3ba1-160">Eseguire il processo Retail Scheduler **1090** per sincronizzare le modifiche nel database del canale.</span><span class="sxs-lookup"><span data-stu-id="a3ba1-160">Run the **1090** scheduler job to sync changes to the channel database.</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="a3ba1-161">Aggiungere un moduli Gift card a una pagina</span><span class="sxs-lookup"><span data-stu-id="a3ba1-161">Add a gift card module to a page</span></span>

<span data-ttu-id="a3ba1-162">Per istruzioni su come aggiungere un moduli Gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="a3ba1-162">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3ba1-163">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a3ba1-163">Additional resources</span></span>

[<span data-ttu-id="a3ba1-164">Modulo carrello</span><span class="sxs-lookup"><span data-stu-id="a3ba1-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a3ba1-165">Modulo icona carrello</span><span class="sxs-lookup"><span data-stu-id="a3ba1-165">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="a3ba1-166">Modulo checkout</span><span class="sxs-lookup"><span data-stu-id="a3ba1-166">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a3ba1-167">Modulo pagamento</span><span class="sxs-lookup"><span data-stu-id="a3ba1-167">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="a3ba1-168">Modulo indirizzo di spedizione</span><span class="sxs-lookup"><span data-stu-id="a3ba1-168">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="a3ba1-169">Modulo opzioni di consegna</span><span class="sxs-lookup"><span data-stu-id="a3ba1-169">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="a3ba1-170">Modulo di informazioni sul ritiro</span><span class="sxs-lookup"><span data-stu-id="a3ba1-170">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="a3ba1-171">Modulo Dettagli ordini</span><span class="sxs-lookup"><span data-stu-id="a3ba1-171">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a3ba1-172">Supporto per gift card esterne</span><span class="sxs-lookup"><span data-stu-id="a3ba1-172">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="a3ba1-173">SDK e aggiornamenti libreria dei moduli</span><span class="sxs-lookup"><span data-stu-id="a3ba1-173">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
