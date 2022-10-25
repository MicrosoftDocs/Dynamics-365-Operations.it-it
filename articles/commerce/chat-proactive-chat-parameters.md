---
title: Parametri della chat proattiva del modulo di chat di Commerce
description: Questo articolo descrive i parametri della chat proattiva dei moduli di chat di Commerce in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: f3cff89a25ff84414e7fdd32cbb26404c2080187
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691072"
---
# <a name="commerce-chat-module-proactive-chat-parameters"></a>Parametri della chat proattiva del modulo di chat di Commerce

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i parametri della chat proattiva della chat di Commerce con Multicanale per Customer Service e della chat di Commerce con i moduli chat di Power Virtual Agents in Microsoft Dynamics 365 Commerce.

## <a name="proactive-chat-properties"></a>Proprietà della chat proattiva

Le proprietà della chat proattiva si trovano nel riquadro delle proprietà della chat di Commerce con Multicanale per Customer Service e della chat di Commerce con i moduli Power Virtual Agents in Creazione di siti di Commerce.

> [!NOTE]
> Per impostazione predefinita, tutte le proprietà della chat proattiva elencate qui sono vuote. È consigliabile saperne di più su queste proprietà e di impostarle solo quando sono obbligatorie. Questo approccio aiuterà a ridurre l'attivazione delle chat proattive errate.

### <a name="proactive-chat"></a>Chat proattiva

| Nome descrittivo | Description | Valore predefinito |
|---------------|-------------|---------------|
| Attivato | Interagisci con i clienti in modo proattivo, in base a diversi trigger. | Disabilitate |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. | Vuoto |

### <a name="wait-time-proactive-chat"></a>Tempo di attesa (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Tempo di attesa (sec) | Il tempo (in secondi) che gli utenti del sito trascorrono su una pagina del sito prima che venga attivata una chat proattiva. |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="number-of-page-visits-proactive-chat"></a>Numero di visite alla pagina (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Numero di visite alla pagina | Il numero di visite alla pagina prima dell'attivazione di una chat proattiva. Gli utenti del sito devono prima accettare la richiesta nel banner di consenso ai cookie. |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="specific-pages-proactive-chat"></a>Pagine specifiche (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Pagina(e) | Un elenco delle pagine che attiveranno una chat proattiva quando vengono visitate. |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="from-specific-pages-proactive-chat"></a>Da pagine specifiche (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Pagina(e) | Un elenco delle pagine che attiveranno una chat proattiva quando gli utenti abbandonano le pagine. |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="specific-countryregion-proactive-chat"></a>Paese/area geografica specifico (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Codice paese | Gli utenti che visitano da paesi o aree geografiche specificati attiveranno una chat proattiva. I codici paese/area geografica devono essere due lettere maiuscole (ad esempio **IT**). |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="date-range-proactive-chat"></a>Intervallo di date (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Data di inizio (gg/mm/aaaa) | La data in cui o dopo la quale verrà attivata una chat proattiva. |
| Data di fine (gg/mm/aaaa) | La data in cui o prima della quale verrà attivata una chat proattiva. |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="total-amount-in-cart-proactive-chat"></a>Importo totale nel carrello (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Minimo | L'importo monetario minimo (incluso) nel carrello degli acquisti che attiverà una chat proattiva quando gli utenti visitano la pagina del carrello. |
| Massimo | L'importo monetario massimo (incluso) nel carrello degli acquisti che attiverà una chat proattiva quando gli utenti visitano la pagina del carrello. |
|Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="total-number-of-items-in-cart-proactive-chat"></a>Numero totale di articoli nel carrello (chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| Minimo | Il numero minimo di articoli (inclusivo) nel carrello degli acquisti che attiverà una chat proattiva quando gli utenti visitano la pagina del carrello. |
| Massimo | Il numero massimo di articoli (inclusivo) nel carrello degli acquisti che attiverà una chat proattiva quando gli utenti visitano la pagina del carrello. |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

### <a name="specific-products-in-cart-proactive-chat"></a>Prodotti specifici nel carrello (Chat proattiva)

| Nome descrittivo | Description |
|---------------|-------------|
| ID/SKU prodotto(i) | Un elenco degli ID/unità di stockkeeping (SKU) del prodotto che attiveranno una chat proattiva quando gli utenti visitano la pagina del carrello. |
| Formula di saluto della chat | Il messaggio della formula di saluto utilizzato quando è stata attivata una chat proattiva. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica delle funzionalità della chat di Commerce](commerce-chat-overview.md)

[Modulo Chat di Commerce con Multicanale per Customer Service](commerce-chat-module.md)

[Modulo chat di Commerce con Power Virtual Agents](chat-module-pva.md)
