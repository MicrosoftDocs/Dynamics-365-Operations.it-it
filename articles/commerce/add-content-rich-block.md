---
title: Modulo blocco di testo
description: In questo argomento vengono descritti i moduli blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025599"
---
# <a name="text-block-module"></a>Modulo blocco di testo


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo blocco di testo è un modulo utilizzato per aggiungere contenuto testuale. Questo contenuto può essere informativo o promozionale.

I moduli blocco di testo sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina. Sono moduli autonomi che non dipendono dal contesto della pagina o da qualsiasi altro modulo.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Esempi di moduli blocco di testo in e-Commerce

I moduli blocco di testo possono essere utilizzati nei seguenti modi:

* Per visualizzare caratteristiche dei prodotti in una pagina dettagli prodotto.
* Per scopi informativi in qualsiasi pagina. Ad esempio, possono spiegare i vantaggi dei programmi fedeltà, descrivere le condizioni di spedizione e reso, rispondere alle domande frequenti oppure fornire contenuto "chi siamo".
* Per aggiungere messaggi personalizzati in una pagina dettagli prodotto (ad esempio, "Spedizione gratuita per ordini superiori a 50 €").
* Per le dichiarazioni di non responsabilità e le informazioni di contatto nelle pagine dettagli prodotto, carrello, checkout e altre pagine (ad esempio "Spedizioni e resi sono soggetti alle politiche del punto vendita").

## <a name="text-block-module-properties"></a>Proprietà dei moduli blocco di testo

| Nome proprietà     | Value                                            | Descrizione |
|-------------------|--------------------------------------------------|-------------|
| RTF         | RTF                                        | Testo di paragrafo. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo. |
| Nome classe personalizzato | Il nome di una classe Cascading Style Sheets (CSS)        | Il nome di una classe CSS personalizzata fornita da uno sviluppatore per formattare questo modulo. Il nome della classe deve essere definito nel pacchetto di temi. |
| Dimensione carattere         | **Piccolo**, **Medio**, **Grande** o **Grandissimo** | La dimensione del carattere del contenuto. |

## <a name="add-a-text-block-module-to-a-page"></a>Aggiungere un modulo blocco di testo a una pagina

Per aggiungere un modulo blocco di testo a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello di pagina denominato **Modello contenuto**. 
1. Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.
1. Completare la modifica del modello e pubblicarlo.
1. Utilizzare il modello di contenuto appena creato per creare una pagina denominata **Pagina contenuto**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.
1. Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.
1. Aggiungere un modulo blocco di testo al modulo contenitore. 
1. Nel riquadro delle proprietà del modulo blocco di testo, aggiungere testo al campo **RTF**.
1. Completare la modifica della pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo banner promozionale](add-alert.md)

[Modulo Sequenza](add-carousel.md)

[modulo blocco di contenuto](add-hero-module.md)

[Modulo lettore video](add-video-player.md)

