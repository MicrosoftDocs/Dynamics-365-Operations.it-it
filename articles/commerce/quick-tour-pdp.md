---
title: Panoramica delle pagine dettagli prodotto
description: Questo argomento fornisce una panoramica delle pagine dettagli prodotto in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 3b02d50adbfcda27d590bcb87fd9669d67d4a01c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697867"
---
# <a name="overview-of-product-details-pages"></a>Panoramica delle pagine dettagli prodotto

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica delle pagine dettagli prodotto in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Una pagina dettagli prodotto (PDP) fornisce informazioni dettagliate su un prodotto e consente ai clienti di selezionare le opzioni relative al prodotto come dimensione, stile e colore. Una pagina dettagli prodotto include tutte le informazioni sul prodotto che un cliente necessita per decidere se effettuare l'acquisto.

Nella figura seguente viene illustrato un esempio di pagina dettagli prodotto.

![Esempio di una pagina dettagli prodotto](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Moduli Intestazione e Piè di pagina

La parte superiore di una pagina dettagli prodotto include un'intestazione che mostra tutte le categorie di prodotti e altre pagine che il rivenditore vuole siano visitate dai clienti. La parte inferiore della pagina include un piè di pagina che contiene collegamenti rapidi a vari argomenti che possono interessare i clienti.

## <a name="buy-box-module"></a>Modulo Casella acquisti

Il modulo più importante in una pagina dettagli prodotto è il modulo Casella acquisti. Di conseguenza, è il primo elemento nella sezione principale della pagina. Un modulo Casella acquisti è un modulo contenitore che include vari moduli contenenti le informazioni più importanti sul prodotto. Queste informazioni includono il nome, le immagini, la descrizione, il prezzo e le recensioni del prodotto.

Il modulo Casella acquisti consente al cliente di selezionare opzioni relative al prodotto (ad esempio, una dimensione, uno stile e un colore) e di aggiungere il prodotto al carrello. Consente inoltre al cliente di acquistare il prodotto online e di ritirarlo in un punto vendita. Il modulo Acquista online e preleva nel punto vendita utilizza l'integrazione con le API di Bing Maps per trovare punti vendita vicini o punti vendita in un'altra ubicazione specificata dal cliente.

Un modulo Casella acquisti richiede un ID prodotto. Questo ID è derivato dal contesto della pagina. Se un modulo Casella acquisti viene aggiunto a una pagina in cui il contesto non include un ID prodotto, eseguirà un rendering non corretto delle informazioni.

## <a name="product-specifications-module"></a>Modulo Specifiche prodotto

Il modulo Specifiche prodotto può essere utilizzato per presentare ulteriori dettagli sul prodotto. Tali dettagli vengono ottenuti dagli attributi del prodotto in Dynamics 365 Retail. Il modulo Specifiche prodotto mostra ogni attributo in cui la proprietà **visibile** è impostata su **true**. Richiede un ID prodotto per recuperare gli attributi del prodotto.

## <a name="recommendations-module"></a>Modulo Suggerimenti

Il modulo Suggerimenti è un modulo importante in una pagina dettagli prodotto. Quando i clienti cercano dei prodotti, è importante che siano visualizzate altri articoli, di modo che possano trovare il prodotto appropriato ed effettuare un acquisto. I suggerimenti aiutano i clienti a individuare facilmente il contenuto correlato e a continuare ad acquistare.

Sono disponibili diversi tipi di elenchi di suggerimenti:

- L'elenco **Alle persone piace anche** è basato sul machine learning. Utilizza lo storico transazioni di altri clienti per fornire suggerimenti. Questo elenco viene generato dal servizio Suggerimenti ed è simile agli elenchi "Chi ha acquistato questo articolo ha acquistato anche...". Un ID prodotto è necessario per generare questo elenco.
- Un elenco **Correlato** può essere configurato per un prodotto in Retail. Ad esempio, per una borsa da viaggio in pelle marrone, altre borse in pelle o da viaggio possono essere configurate per l'elenco correlato. Altri tipi di elenchi correlati, come **Accessori** e **Prodotti simili**, possono anche essere configurati in Retail. Un ID prodotto è necessario per generare questo elenco. Di conseguenza, se è aggiunto a una home page, dove il contesto della pagina non include un ID prodotto, l'elenco sarà vuoto.
- Gli elenchi di suggerimenti generati con algoritmi, ad esempio **Di tendenza**, **Più venduti** e **Novità**, possono essere utilizzati nelle pagine dettagli prodotto. Benché tali elenchi possano non essere direttamente correlati al prodotto nella pagina dettagli prodotto, sono un altro modo per consentire agli utenti di trovare i prodotti a cui potrebbero essere interessati. Questi tipi di elenchi non richiedono un ID prodotto. Sono elenchi generici generati in base ai criteri di acquisto nel sito.
- Gli elenchi editoriali sono elenchi curati manualmente. Ad esempio, un rivenditore potrebbe decidere di curare manualmente gli elenchi di prodotti che desidera presentare.

## <a name="ratings-and-reviews-module"></a>Modulo Valutazioni e recensioni

Il modulo Valutazioni e recensioni mostra le valutazioni e le recensioni fornite da altri clienti. Consente inoltre a un cliente di scrivere una recensione sul prodotto. Inoltre, include un istogramma che mostra il trend delle valutazioni per il prodotto. Per ulteriori informazioni, vedere [Panoramica valutazioni e recensioni](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Moduli Marketing

Se il contenuto marketing è univoco a uno specifico prodotto, qualsiasi modulo Marketing può essere aggiunto a una pagina dettagli prodotto. È possibile aggiungere moduli Marketing a una pagina dettagli prodotto "migliorando" la pagina. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della home page](quick-tour-home-page.md)

[Panoramica della pagina di destinazione di categoria e della pagina dei risultati della ricerca predefinite](category-search-page-overview.md)

[Panoramica delle pagine carrello e checkout](quick-tour-cart-checkout.md)

[Panoramica delle pagine di gestione account](quick-tour-account-management.md)
