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
# <a name="gift-card-module"></a>Modulo Gift card

[!include [banner](includes/banner.md)]

Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Le gift card sono una forma di pagamento comune e il moduli Gift card può essere utilizzato in un modulo di pagamento per accettare gift card. Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex. Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen.

Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md)

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

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Checkout](add-checkout-module.md)

[Supporto per gift card esterne](./dev-itpro/gift-card.md)
