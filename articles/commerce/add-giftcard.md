---
title: Modulo gift card
description: Questo argomento tratta i moduli per gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261575"
---
# <a name="gift-card-module"></a>Modulo gift card

[!include [banner](includes/banner.md)]

Questo argomento tratta i moduli per gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Le gift card sono una forma di pagamento comune e il modulo gift card può essere utilizzato in un modulo di pagamento per accettare gift card. Il modulo gift card supporta gift card Dynamics 365, SVS e Givex. Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen.

Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md)

## <a name="module-properties"></a>Proprietà del modulo

- **Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita. Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza. In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.

Valori supportati:
-   PIN
-   Data di scadenza
-   PIN e Data di scadenza 
-   Nessuna priorità

## <a name="site-settings-for-gift-card-modules"></a>Impostazioni del sito per i moduli gift card

In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del modulo gift card chiamata **Tipo di gift card supportato**. Questa impostazione supporta tre valori:
- **Gift card Dynamics 365** - Quando si applica questa impostazione, il modulo gift card consente solo il riscatto di gift card Dynamics 365. Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.
- **Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il modulo gift card consente solo il riscatto di gift card Givex e SVS. Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.
- **Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il modulo gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex. Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.

## <a name="add-a-gift-card-module-to-a-page"></a>Aggiungere un modulo gift card a una pagina

Per istruzioni su come aggiungere un modulo gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo checkout](add-checkout-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo checkout](add-checkout-module.md)

[Supporto per gift card esterne](./dev-itpro/gift-card.md)
