---
title: Funzionalità di vendita del servizio clienti
description: Questo argomento fornisce una panoramica delle funzionalità di vendita del servizio clienti in Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2e44770af4a30f539e56d38b21c897cacd2707e7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812341"
---
# <a name="call-center-sales-functionality"></a>Funzionalità di vendita del servizio clienti

[!include [banner](includes/banner.md)]


In Dynamics 365 Retail, un servizio clienti è un tipo di canale di vendita al dettaglio che può essere definito nell'applicazione. La definizione di uno specifico canale per le entità del servizio clienti consente al sistema di associare specifici valori predefiniti di dati e di elaborazione di ordini a ordini cliente creati da un utente del canale del servizio clienti.

Le funzionalità del servizio clienti includono prezzi di vendita al dettaglio e promozioni, cataloghi, gift card e buoni sconto. Gli ordini del servizio clienti sono utilizzati dall'applicazione POS per supportare scenari di adempimento ordini multicanale.

È importante notare che sebbene il modulo servizio clienti possa essere utilizzato da altri settori oltre a quello della vendita al dettaglio, la versione corrente dell'applicazione servizio clienti di Retail non è stata ottimizzata per l'utilizzo in scenari di elaborazione ordini B2B o scenari in cui gli ordini hanno un gran numero di righe di vendita. Si consiglia agli utenti che desiderano utilizzare le funzionalità del servizio clienti per l'elaborazione di ordini al di fuori di una tipica elaborazione di transazioni direct-to-consumer di verificare attentamente che l'attivazione della funzionalità di servizio clienti soddisferà le esigenze prestazionali e funzionali.

Oltre a supportare la creazione di ordini, il modulo servizio clienti fornisce un'applicazione servizio clienti intuitiva che semplifica la ricerca di conti cliente e la verifica di tutti i dati e gli attributi di ordini cliente correlati. La schermata del servizio clienti è progettata per consentire a un utente di accedere rapidamente ai dati relativi agli ordini che gli consentiranno di rispondere alle domande sugli ordini più comuni ricevute dai clienti.

In questa pagina vengono forniti collegamenti alla documentazione su impostazione, configurazione e utilizzo delle funzionalità di servizio clienti in Retail.


## <a name="configure-the-call-center"></a>Configurazione del servizio clienti

[Impostare canali del servizio clienti](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a>Configurazione dell'elaborazione degli ordini

[Impostazione e utilizzo degli avvisi di frode del servizio clienti](set-up-fraud-alerts.md)

[Configurare e utilizzare le sospensioni degli ordini del servizio clienti](work-with-order-holds.md)

## <a name="configure-payment-processing"></a>Configurazione dell'elaborazione dei pagamenti

[Metodi di pagamento nei servizi clienti](work-with-payments.md)

## <a name="configure-delivery-modes"></a>Configurare le modalità di consegna

[Configurare le modalità e le spese di consegna del servizio clienti](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a>Configurazione del direct marketing

[Cataloghi del servizio clienti](call-center-catalogs.md)

[Impostare l'analisi Recency, Frequency and Monetary (RFM)](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a>Configurazione di programmi di continuità

[Impostare programmi di continuità per i servizi clienti](set-up-continuity-program.md)
