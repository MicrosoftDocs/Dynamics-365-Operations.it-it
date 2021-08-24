---
title: Panoramica delle pagine dei dettagli del prodotto
description: Questo argomento fornisce una panoramica delle pagine dettagli prodotto in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: eb8535a0c03029c347d5fc6e3fe49ca556c6f7bdd22d2baa7815ced1db21a13a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760178"
---
# <a name="product-details-pages-overview"></a>Panoramica delle pagine dei dettagli del prodotto

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica delle pagine dettagli prodotto in Microsoft Dynamics 365 Commerce.

Una pagina dettagli prodotto (PDP) fornisce informazioni dettagliate su un prodotto e consente ai clienti di selezionare le opzioni relative al prodotto come dimensione, stile e colore. Una pagina dettagli prodotto include tutte le informazioni sul prodotto che un cliente necessita per decidere se effettuare l'acquisto.

Nella figura seguente viene illustrato un esempio di pagina dettagli prodotto.

![Esempio di una pagina dettagli prodotto.](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Moduli intestazione e piè di pagina

La parte superiore di una pagina dettagli prodotto include un'intestazione che mostra tutte le categorie di prodotti e altre pagine che il rivenditore vuole siano visitate dai clienti. La parte inferiore della pagina include un piè di pagina che contiene collegamenti rapidi a vari argomenti che possono interessare i clienti.

## <a name="buy-box-module"></a>Modulo Casella acquisti

Il modulo più importante in una pagina dettagli prodotto è il modulo Casella acquisti visualizzato come primo elemento nella sezione principale della pagina. Un modulo Casella acquisti mostra importanti informazioni sul prodotto, come il nome del prodotto, la descrizione del prodotto, il prezzo del prodotto, le immagini del prodotto e le valutazioni del prodotto.

Il modulo Casella acquisti consente al cliente di selezionare opzioni relative al prodotto (ad esempio, una dimensione, uno stile e un colore) e di aggiungere il prodotto al carrello. Consente inoltre al cliente di acquistare il prodotto online e di ritirarlo in un punto vendita. Il modulo Acquista online e preleva nel punto vendita utilizza l'integrazione con le API di Bing Maps per trovare punti vendita vicini o punti vendita in un'altra ubicazione specificata dal cliente.

Un modulo Casella acquisti richiede un ID prodotto. Questo ID è derivato dal contesto della pagina. Se un modulo Casella acquisti viene aggiunto a una pagina in cui il contesto non include un ID prodotto, eseguirà un rendering non corretto delle informazioni.

## <a name="product-specifications-module"></a>Modulo Specifiche prodotto

Il modulo Specifiche prodotto può essere utilizzato per presentare ulteriori dettagli sul prodotto. Tali dettagli vengono ottenuti dagli attributi del prodotto in Commerce. Il modulo Specifiche prodotto mostra ogni attributo in cui la proprietà **visibile** è impostata su **true**. Richiede un ID prodotto per recuperare gli attributi del prodotto.

## <a name="recommendations-module"></a>Modulo Suggerimenti

Il modulo Suggerimenti è un modulo importante in una pagina dettagli prodotto. Quando i clienti cercano dei prodotti, è importante che siano visualizzate altri articoli, di modo che possano trovare il prodotto appropriato ed effettuare un acquisto. I suggerimenti aiutano i clienti a individuare facilmente il contenuto correlato e a continuare ad acquistare.

Sono disponibili diversi tipi di elenchi di suggerimenti:

- L'elenco **Alle persone piace anche** è basato sul machine learning. Utilizza lo storico transazioni di altri clienti per fornire suggerimenti. Questo elenco viene generato dal servizio Suggerimenti ed è simile agli elenchi "Chi ha acquistato questo articolo ha acquistato anche...". Un ID prodotto è necessario per generare questo elenco.
- Un elenco **Correlato** può essere configurato per un prodotto in Commerce. Ad esempio, per una borsa da viaggio in pelle marrone, altre borse in pelle o da viaggio possono essere configurate per l'elenco correlato. Altri tipi di elenchi correlati, come **Accessori** e **Prodotti simili**, possono anche essere configurati in Commerce. Un ID prodotto è necessario per generare questo elenco. Di conseguenza, se è aggiunto a una home page, dove il contesto della pagina non include un ID prodotto, l'elenco sarà vuoto.
- Gli elenchi di suggerimenti generati con algoritmi, ad esempio **Di tendenza**, **Più venduti** e **Novità**, possono essere utilizzati nelle pagine dettagli prodotto. Benché tali elenchi possano non essere direttamente correlati al prodotto nella pagina dettagli prodotto, sono un altro modo per consentire agli utenti di trovare i prodotti a cui potrebbero essere interessati. Questi tipi di elenchi non richiedono un ID prodotto. Sono elenchi generici generati in base ai criteri di acquisto nel sito.
- Gli elenchi editoriali sono elenchi curati manualmente. Ad esempio, un rivenditore potrebbe decidere di curare manualmente gli elenchi di prodotti che desidera presentare.

## <a name="ratings-and-reviews-modules"></a>Moduli Valutazioni e recensioni

Tre moduli possono essere utilizzati per visualizzare e aggiungere recensioni:

- **Recensioni** - Questo modulo elenca valutazioni e recensioni fornite da altri clienti. I clienti possono ordinare e filtrare le recensioni. Questo modulo consente inoltre ai clienti di apprezzare o non apprezzare le recensioni e di segnalare problemi.
- **Scrivi recensione** - Questo modulo consente ai clienti di scrivere le proprie recensioni su un prodotto.
- **Istogramma delle valutazioni** - Questo modulo include un istogramma che mostra il trend delle valutazioni per un prodotto.

Per ulteriori informazioni, vedere [Panoramica valutazioni e recensioni](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Moduli Marketing

Se il contenuto marketing è univoco a uno specifico prodotto, qualsiasi modulo Marketing può essere aggiunto a una pagina dettagli prodotto. È possibile aggiungere moduli Marketing a una pagina dettagli prodotto "migliorando" la pagina. Per maggiori dettagli, vedere [Migliorare una pagina prodotto](enrich-product-page.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della home page](quick-tour-home-page.md)

[Panoramica delle pagine del checkout e del carrello](quick-tour-cart-checkout.md)

[Panoramica delle pagine della gestione del conto](quick-tour-account-management.md)

[Migliorare una pagina prodotto](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
