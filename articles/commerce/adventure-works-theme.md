---
title: Panoramica del tema Adventure Works
description: Questo articolo offre una panoramica del tema Adventure Works e descrive come applicarlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: ae2af73a17e03ca216665e515ac4739e02944b8c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278680"
---
# <a name="adventure-works-theme-overview"></a>Panoramica del tema Adventure Works

[!include [banner](includes/banner.md)]

Questo articolo offre una panoramica del tema Adventure Works e descrive come applicarlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce ha un tema per l'e-commerce chiamato Adventure Works. Il tema Adventure Works mette in mostra prodotti sportivi e ricreativi ed è ottimizzato per un'esperienza di narrazione ricca e migliorata. Fornisce un aspetto moderno, nuovi layout ed effetti di animazione per creare un'esperienza di acquisto online immersiva e coinvolgente per i clienti di e-commerce.

## <a name="trial-environments-in-commerce"></a>Ambienti di prova in Commerce

Per vedere come appare il tema Adventure Works quando viene distribuito per i siti business-to-consumer (B2C) e business-to-business (B2B), visita i seguenti siti di prova:

- [Sito Adventure Works B2C](https://www.adventure-works.com/)
- [Sito Adventure Works B2B](https://www.adventure-works.com/business)

## <a name="theme-capabilities"></a>Funzionalità di tema

Il tema Adventure Works fornisce le seguenti nuove funzionalità:

- Il modulo del lettore video ora supporta la funzionalità di intestazione, paragrafo e collegamento per una narrazione aggiuntiva.
- Ci sono migliori transizioni di contenuto per l'animazione.
- L'azione "Aggiungi al carrello" richiama il mini carrello invece di fornire una notifica.
- Il modulo di visualizzazione rapida è un riquadro che scorre sia nei riquadri di visualizzazione dei desktop che in quelli dei dispositivi mobili.
- Ci sono nuovi layout per le pagine del sito. 
- I contenuti di marketing possono essere configurati per il carrello e il mini carrello quando sono vuoti.
- Il mini carrello può mostrare messaggi promozionali, come "Spedizione gratuita per ordini superiori a $50".
- Le schede descrittive vengono visualizzate nelle pagine di ricerca e di categoria.

Il tema Adventure Works ora include i seguenti moduli di narrazione nella libreria del modulo Commerce:

- [Modulo Elenco riquadri](tile-list-module.md)
- [Modulo funzionalità interattiva](interactive-feature-module.md)
- [Modulo Immagine attiva](active-image-module.md)
- [Modulo di iscrizione](subscribe-module.md)
- [Modulo Elenco immagini](image-list-module.md)

Il tema Adventure Works è completamente reattivo e offre un'esperienza ottimizzata per i riquadri di visualizzazione dei desktop, dei dispositivi mobili e dei tablet.

> [!IMPORTANT]
> Il tema Adventure Works e i nuovi moduli sono disponibili a partire dalla versione 10.0.20 di Dynamics 365 Commerce.

L'illustrazione seguente mostra un esempio di una home page che utilizza il tema Adventure Works.

![Esempio di una home page che utilizza il tema Adventure Works](./media/aw_b2c.PNG)

L'illustrazione seguente mostra un esempio di una pagina elenco che utilizza il tema Adventure Works.

![Esempio di una pagina elenco che utilizza il tema Adventure Works](./media/Aw_list.PNG)

L'illustrazione seguente mostra un esempio di una pagina dettagli prodotto (PDP) che utilizza il tema Adventure Works.

![Esempio di una pagina dettagli prodotto (PDP) che utilizza il tema Adventure Works](./media/aw_pdp.PNG)

## <a name="use-the-adventure-works-theme-for-b2b-sites"></a>Usare il tema Adventure Works per i siti B2B

Il tema Adventure Works è anche un tema di riferimento per i siti business-to-business (B2B). Tutti i moduli e i flussi di lavoro B2B sono presentati nel tema Adventure Works. Per informazioni su come impostare un sito B2B, vedere [Impostare un sito B2B](./b2b/set-up-b2b-site.md).

L'illustrazione seguente mostra un esempio di una home page B2B che utilizza il tema Adventure Works.

![Esempio di una home page B2B che utilizza il tema Adventure Works](./media/aw_b2b.PNG)

## <a name="theme-extensions"></a>Estensioni del tema

Il tema Adventure Works include diverse estensioni del tema, come le estensioni **Estensioni della visualizzazione** e **Definizione del modulo**. Il tema Adventure Works può essere utilizzato come tema di riferimento per creare estensioni simili. Ad esempio, la pagina elenco nel tema Adventure Works viene implementata come estensione della visualizzazione con un criterio di affinamento orizzontale. (Al contrario, nel tema Fabrikam viene utilizzato un criterio di affinamento del riquadro sinistro).

Allo stesso modo, altri moduli includono estensioni di definizione del modulo. Ad esempio, il [modulo icona carrello](cart-icon-module.md) include due slot aggiuntivi **Carrello vuoto** e **Contenuti promozionali** implementati utilizzando estensioni di definizione del modulo. Inoltre, una nuova proprietà **Logo mobile** è stata aggiunta al modulo di intestazione per supportare un logo nei riquadri di visualizzazione dei dispositivi mobili. Questa proprietà è implementata come estensione della definizione del modulo di intestazione.

Per ulteriori informazioni sulle estensioni dei temi, vedere [Estensioni del tema](e-commerce-extensibility/theme-module-extensions.md).

## <a name="install-the-adventure-works-theme"></a>Installare il tema Adventure Works

Per informazioni su come installare il tema Adventure Works, vedi [Installare il tema Adventure Works](install-adventure-works.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo Elenco riquadri](tile-list-module.md)

[Modulo funzionalità interattiva](interactive-feature-module.md)

[Modulo dell'immagine attiva](active-image-module.md)

[Modulo di iscrizione](subscribe-module.md)

[Modulo elenco immagini](image-list-module.md)

[Estensioni del tema](e-commerce-extensibility/theme-module-extensions.md)

[Modulo icona carrello](cart-icon-module.md)

[Creare un sito di e-commerce B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
