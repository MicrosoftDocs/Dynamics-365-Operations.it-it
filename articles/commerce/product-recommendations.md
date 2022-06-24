---
title: Panoramica suggerimenti sul prodotto
description: Questo articolo fornisce informazioni generali sui suggerimenti sul prodotto. I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati e persino i prodotti che originariamente non intendevano acquistare.
author: Moonma
ms.date: 05/26/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2cb62638e89dd9cd7c01739244d808f664b3f3b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867734"
---
# <a name="product-recommendations-overview"></a>Panoramica suggerimenti sul prodotto

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce può essere utilizzato per visualizzare suggerimenti sul prodotto nel sito Web di e-Commerce e nel dispositivo POS. I suggerimenti sul prodotto sono articoli a cui un cliente potrebbe essere interessato. I suggerimenti si basano sulle tendenze di acquisto di altri clienti in punti vendita online e fisici.

I suggerimenti sul prodotto consentono ai clienti di individuare facilmente e rapidamente i prodotti desiderati durante un'esperienza ottimale. Il cross-selling e l'up-selling possono inoltre essere utilizzati per consentire ai clienti di individuare ulteriori prodotti che originariamente non intendevano acquistare. Quando i suggerimenti sono utilizzati per aumentare l'individuazione di prodotti, possono creare più opportunità di conversione, aumentare i ricavi da vendite e persino amplificare la soddisfazione e la conservazione dei clienti.

In e-Commerce, i suggerimenti sul prodotto sono generati mediante tecnologie di machine learning del servizio Suggerimenti di Microsoft su vasta scala.

Questo servizio è un componente aggiuntivo per Dynamics 365 Commerce. Per ulteriori informazioni, scaricare l'ultima [guida alle licenze di Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).


## <a name="recommendation-service"></a>Servizio Suggerimenti

Il servizio di suggerimenti sui prodotti utilizza le tecnologie di intelligenza artificiale e machine learning (AI-ML) nel modo seguente:

- I dati nel formato richiesto dal servizio Suggerimenti vengono estratti dal database operativo di Commerce e sono inviati a Azure Data Lake Storage o all'Archivio entità.
- Il servizio Suggerimenti utilizza i dati memorizzati per preparare i modelli di suggerimenti per gli elenchi **Alle persone piace anche**, **Spesso acquistati insieme**, **Novità**, **Più venduti** e **Di tendenza**.

## <a name="scenarios"></a>Scenari

I suggerimenti sul prodotto sono disponibili per i seguenti scenari:

- **In qualsiasi pagina di esplorazione del punto vendita o nella pagina di destinazione di e-Commerce:** se i clienti o gli addetti alle vendite visitano una pagina del punto vendita, il motore dei suggerimenti può suggerire prodotti negli elenchi **Novità**, **Più venduti** e **Di tendenza**.
- **Nella pagina dettagli prodotto:** se i clienti o gli addetti alle vendite visitano una pagina **Dettagli prodotto**, il motore dei suggerimenti suggerisce altri articoli il cui acquisto è probabile. Questi articoli sono visualizzati nell'elenco **Alle persone piace anche**.
- **Nella pagina Transazione o checkout:** il motore dei suggerimenti suggerisce articoli in base all'intero elenco di articoli nel carrello. Questi articoli sono visualizzati nell'elenco **Spesso acquistati insieme**.
- **Suggerimenti personalizzati:** i merchandiser possono offrire ai clienti che hanno effettuato l'accesso un elenco **Selezioni personalizzate**, oltre alle nuove funzionalità che consentono di personalizzare scenari di elenco esistenti in base a quel cliente. Per ulteriori informazioni, vedere [Abilitare i suggerimenti personalizzati.](personalized-recommendations.md).

### <a name="types-of-product-recommendations"></a>Tipi di suggerimenti sul prodotto

La tabella seguente descrive vari tipi di suggerimenti sul prodotto automatizzati disponibili per i rivenditori da implementare nella soluzione Dynamics 365 Commerce tramite il [modulo Raccolta prodotti](product-collection-module-overview.md). I rivenditori possono anche mostrare risultati personalizzati per un utente che ha effettuato l'accesso se l'autore del sito sceglie tale opzione.

| Modulo Raccolta prodotti  | Tipo | Descrizione |
|----------------------------|------|-------------|
| Nuove                        | Algoritmico | Questo modulo mostra un elenco dei prodotti più recenti che sono stati assortiti di recente in canali e cataloghi. |
| Più venduti               | Algoritmico | Questo modulo mostra un elenco di prodotti classificati in base al più alto numero di vendite. |
| Di tendenza                   | Algoritmico | Questo modulo presenta un elenco dei prodotti di maggior successo in un determinato periodo, classificati per numero più alto di vendite.  |
| Spesso acquistati insieme | AI-ML | Questo modulo offre suggerimenti per un elenco di prodotti che vengono comunemente acquistati insieme al contenuto del carrello attuale dei consumatori. |
| Alle persone piace anche           | AI-ML | Questo modulo offre suggerimenti per i prodotti per un determinato prodotto iniziale in base ai modelli di acquisto dei consumatori. |
| Selezioni personalizzate              | AI-ML | Questo modulo offre suggerimenti per un elenco personalizzato di prodotti basato sui modelli di acquisto dell'utente che ha effettuato l'accesso. Per un utente guest, questo elenco verrà compresso. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Aggiungere suggerimenti sul prodotto nel POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
