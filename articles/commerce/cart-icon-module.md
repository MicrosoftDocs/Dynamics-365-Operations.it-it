---
title: Modulo Icona carrello
description: In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9e3850d98e716d1bbea2017f6e8c9d75f19adc9
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638003"
---
# <a name="cart-icon-module"></a>Modulo icona carrello

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

Il modulo Icona carrello rappresenta il carrello nel modulo Intestazione della pagina e mostra in qualsiasi momento il numero di articoli presenti nel carrello. Il modulo Icona carrello mostra anche un riepilogo del carrello (noto anche come mini carrello) quando si passa con il mouse sull'icona del carrello. Il mini carrello fornisce all'utente un riepilogo degli articoli nel carrello senza dover accedere alla pagina del carrello. Inoltre, consente all'utente di accedere direttamente alla pagina di pagamento se è soddisfatto del riepilogo. Ciò riduce il numero di navigazioni della pagina e velocizza il checkout. 

L'immagine seguente mostra un esempio di un modulo Icona carrello che visualizza un mini carrello nell'intestazione Fabrikam.

![Esempio di modulo Icona carrello.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Proprietà del modulo

- **Mostra mini carrello** - Se impostata su vero, questa proprietà consente di visualizzare un riepilogo del carrello (mini carrello) quando si passa con il mouse sull'icona del carrello. Questa funzionalità è supportata solo per le porte di visualizzazione desktop.

## <a name="module-properties-in-the-adventure-works-theme"></a>Proprietà del modulo nel tema Adventure Works

Nel tema Adventure Works il modulo Icona carrello include due slot aggiuntivi per il mini carrello. Questi slot sono inclusi come estensione della definizione del modulo.

- **Promozioni carrello vuoto** - Questo slot accetta un modulo di blocco del contenuto. Quando il carrello è vuoto, viene mostrato il modulo di blocco del contenuto specificato. Il modulo di blocco del contenuto può essere utilizzato per promozioni, contenuti di marketing e collegamenti a pagine di categoria, per aiutare i clienti a continuare il loro percorso di acquisto.
- **Contenuti promozionali** - Questo slot può essere utilizzato per mostrare promozioni, come "Spedizione gratuita per ordini superiori a $100". I moduli di blocco del contenuto, blocco di testo ed elenco di immagini possono essere utilizzati nello slot dei contenuti promozionali.

L'immagine seguente mostra un esempio di modulo Icona carrello nel tema Adventure Works che mostra il contenuto promozionale sul mini carrello.

![Esempio di un modulo Icona carrello nel tema Adventure Works](./media/AW_minicart.PNG)

> [!IMPORTANT]
> Gli slot del tema Adventure Works sono disponibili a partire dalla versione 10.0.20 di Dynamics 365 Commerce.

## <a name="add-a-cart-icon-module-to-a-page"></a>Aggiungere un modulo Icona carrello a una pagina

Per aggiungere un modulo Icona carrello, vedere [Modulo Intestazione](author-header-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
