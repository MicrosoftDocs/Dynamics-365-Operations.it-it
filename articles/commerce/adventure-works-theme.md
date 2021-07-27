---
title: Panoramica del tema Adventure Works
description: Questo argomento offre una panoramica del tema Adventure Works e descrive come applicarlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7557a36a948de5ae877d74bbbdea78821099b82
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479481"
---
# <a name="adventure-works-theme-overview"></a>Panoramica del tema Adventure Works

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento offre una panoramica del tema Adventure Works e descrive come applicarlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce ha un tema per l'e-commerce chiamato Adventure Works. Il tema Adventure Works mette in mostra prodotti sportivi e ricreativi ed è ottimizzato per un'esperienza di narrazione ricca e migliorata. Fornisce un aspetto moderno, nuovi layout ed effetti di animazione per creare un'esperienza di acquisto online immersiva e coinvolgente per i clienti di e-commerce.

Il tema Adventure Works fornisce i seguenti nuovi flussi di lavoro:

- Il modulo del lettore video ora supporta la funzionalità di intestazione, paragrafo e collegamenti per una narrazione aggiuntiva.
- L'azione Aggiungi al carrello richiama il mini carrello invece di fornire una notifica.
- Il modulo di visualizzazione rapida è un riquadro che scorre sia nei riquadri di visualizzazione dei desktop che in quelli dei dispositivi mobili.
- Un carrello vuoto ora può mostrare le promozioni.

Il tema Adventure Works include i seguenti moduli di narrazione nella libreria del modulo Commerce:

- Modulo elenco riquadro
- Modulo funzionalità interattiva
- Modulo di iscrizione
- Modulo dell'immagine attiva
- Modulo elenco immagini

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

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo elenco riquadro](tile-list-module.md)

[Modulo funzionalità interattiva](interactive-feature-module.md)

[Modulo dell'immagine attiva](active-image-module.md)

[Modulo di iscrizione](subscribe-module.md)

[Modulo elenco immagini](image-list-module.md)

[Estensioni del tema](e-commerce-extensibility/theme-module-extensions.md)

[Modulo icona carrello](cart-icon-module.md)

[Creare un sito di e-commerce B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
