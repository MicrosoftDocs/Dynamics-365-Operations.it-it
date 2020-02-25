---
title: Panoramica suggerimenti sul prodotto
description: Questo argomento fornisce informazioni generali sui suggerimenti sul prodotto. I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati e persino i prodotti che originariamente non intendevano acquistare.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e249c7d450510a3a9a33158e9e1c33f832a1f91c
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024981"
---
# <a name="product-recommendations-overview"></a>Panoramica suggerimenti sul prodotto

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce può essere utilizzato per visualizzare suggerimenti sul prodotto nel sito Web di e-Commerce e nel dispositivo POS. I suggerimenti sul prodotto sono articoli a cui un cliente potrebbe essere interessato. I suggerimenti si basano sulle tendenze di acquisto di altri clienti in punti vendita online e fisici.

I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati durante un'esperienza ottimale. Il cross-selling e l'up-selling possono inoltre essere utilizzati per consentire ai clienti di individuare ulteriori prodotti che originariamente non intendevano acquistare. Quando i suggerimenti sono utilizzati per consentire l'individuazione di prodotti, possono creare più opportunità di conversione, aumentare i ricavi da vendite e persino migliorare la soddisfazione e la conservazione dei clienti.

In Commerce, i suggerimenti sul prodotto sono generati mediante tecnologie di machine learning del servizio Suggerimenti di Microsoft su vasta scala.


## <a name="scenarios"></a>Scenari

I suggerimenti sul prodotto sono disponibili per i seguenti scenari:

- **In qualsiasi pagina di esplorazione del punto vendita o nella pagina di destinazione di e-Commerce:** se i clienti o gli addetti alle vendite visitano una pagina del punto vendita, il motore dei suggerimenti può suggerire prodotti negli elenchi **Novità**, **Più venduti** e **Di tendenza**.
- **Nella pagina dettagli prodotto:** se i clienti o gli addetti alle vendite visitano una pagina **Dettagli prodotto**, il motore dei suggerimenti suggerisce altri articoli il cui acquisto è probabile. Questi articoli sono visualizzati nell'elenco **Alle persone piace anche**.
- **Nella pagina Transazione o checkout:** il motore dei suggerimenti suggerisce articoli in base all'intero elenco di articoli nel carrello. Questi articoli sono visualizzati nell'elenco **Spesso acquistati insieme**.
- **Suggerimenti personalizzati:** i merchandiser possono offrire ai clienti che hanno effettuato l'accesso un elenco **Selezioni personalizzate**, oltre alle nuove funzionalità che consentono di personalizzare scenari di elenco esistenti in base a quel cliente. Per saperne di più, consultare la documentazione relativa alle funzionalità: [Abilitare suggerimenti personalizzati.](personalized-recommendations.md)

## <a name="recommendation-service"></a>Servizio Suggerimenti

I suggerimenti sul prodotto utilizzano le tecnologie di machine learning del servizio Suggerimenti come segue:

- I dati nel formato richiesto dal servizio Suggerimenti vengono estratti dal database operativo di Commerce e sono inviati all'Archivio entità.
- Il servizio Suggerimenti utilizza i dati per preparare i modelli di suggerimenti per gli elenchi **Alle persone piace anche**, **Spesso acquistati insieme**, **Novità**, **Più venduti** e **Di tendenza**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Abilitare suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare suggerimenti personalizzati](personalized-recommendations.md)

[Panoramica del modulo di raccolta prodotti](product-collection-module-overview.md)

[Creare elenchi dettagliati di suggerimenti sul prodotto](create-editorial-recommendation-lists.md)

[Gestire i risultati dei suggerimenti sul prodotto basati su AI-ML](modify-product-recommendation-results.md)

[Aggiungere elenchi di suggerimenti sul prodotto alle pagine](add-reco-list-to-page.md)
