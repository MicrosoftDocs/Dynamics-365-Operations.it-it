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
# <a name="gift-card-module"></a>Modulo Gift card

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I moduli di gift card possono essere utilizzati nei moduli di pagamento per accettare gift card, una forma di pagamento comune utilizzata per le transazioni di e-commerce. Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex. Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen. Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md).

Sono disponibili due moduli di gift card:

- **Gift card** - Questo modulo può essere utilizzato in una pagina di checkout per riscattare una gift card come offerta. 
- **Controllo del saldo della gift card** - Questo modulo può essere utilizzato in qualsiasi pagina per controllare il saldo di una gift card. Questo modulo è disponibile in Commerce versione 10.0.14 e successive.

L'immagine seguente mostra un esempio di un moduli Gift card in una pagina checkout.

![Esempio di moduli Gift card](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Proprietà del modulo

- **Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita. Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza. In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.

Valori supportati:
-   PIN
-   Data di scadenza
-   PIN e Data di scadenza 
-   Nessuna priorità

## <a name="site-settings-for-gift-card-modules"></a>Impostazioni del sito per i moduli Gift card

In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del moduli Gift card chiamata **Tipo di gift card supportato**. Questa impostazione supporta tre valori:
- **Gift card Dynamics 365** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365. Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.
- **Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Givex e SVS. Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.
- **Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il moduli Gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex. Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.

## <a name="add-a-gift-card-module-to-a-page"></a>Aggiungere un moduli Gift card a una pagina

Per istruzioni su come aggiungere un moduli Gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo Pagamento](payment-module.md)

[Modulo Indirizzo di spedizione](ship-address-module.md)

[Modulo Opzioni di consegna](delivery-options-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Supporto per gift card esterne](./dev-itpro/gift-card.md)
