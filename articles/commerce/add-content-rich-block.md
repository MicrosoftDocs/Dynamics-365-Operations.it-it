---
title: Modulo Blocco ricco di contenuti
description: In questo argomento vengono descritti i moduli Blocco ricco di contenuti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785423"
---
# <a name="content-rich-block-module"></a>Modulo Blocco ricco di contenuti

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Blocco ricco di contenuti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Blocco ricco di contenuti è un contenitore speciale in cui è possibile inserire uno o più elementi blocco ricco di contenuti. I moduli Blocco ricco di contenuti sono utilizzati per contenuto testuale in una pagina. Questo contenuto può essere informativo o promozionale.

I moduli Blocco ricco di contenuti sono basati sui dati del sistema di gestione dei contenuti (CMS) e possono essere utilizzati in qualsiasi pagina. Sono moduli autonomi che non dipendono dal contesto della pagina o da qualsiasi altro modulo.

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a>Esempi di moduli Blocco ricco di contenuti in e-Commerce

I moduli Blocco ricco di contenuti possono essere utilizzati nei seguenti modi:

* Per visualizzare caratteristiche dei prodotti in una pagina dettagli prodotto.
* Per scopi informativi in qualsiasi pagina. Ad esempio, possono spiegare i vantaggi dei programmi fedeltà, descrivere le condizioni di spedizione e reso, rispondere alle domande frequenti oppure fornire contenuto "chi siamo".
* Per aggiungere messaggi personalizzati in una pagina dettagli prodotto (ad esempio, "Spedizione gratuita per ordini superiori a 50 €").
* Per le dichiarazioni di non responsabilità e le informazioni di contatto nelle pagine dettagli prodotto, carrello, checkout e altre pagine (ad esempio "Spedizioni e resi sono soggetti alle politiche del punto vendita").

## <a name="content-rich-block-module-properties"></a>Proprietà del modulo Blocco ricco di contenuti

| Nome proprietà     | Valore                                 | Proprietà |
|-------------------|---------------------------------------|----------|
| Numero di colonne | Un numero da **1** a **4**     | Il numero di colonne nel blocco ricco di contenuti. È possibile avere fino a quattro colonne. |
| Larghezza             | **Riempi contenitore** o **Riempi schermo** | Se il valore è **Riempi contenitore**, gli elementi nel contenitore sono limitati alla larghezza del contenitore. Se il valore impostato è **Riempi schermo**, gli elementi non sono limitati alla larghezza del contenitore ma possono essere visualizzati in modalità a schermo intero. È possibile modificare il valore per ottenere il layout desiderato. |

## <a name="content-rich-block-item-module-properties"></a>Proprietà del modulo Elemento blocco ricco di contenuti

| Nome proprietà | Valore          | Descrizione |
|---------------|----------------|-------------|
| Paragrafo     | Testo di paragrafo | Il testo che accompagna ogni elemento blocco ricco di contenuti. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo. |

## <a name="add-a-content-rich-block-module-to-a-page"></a>Aggiungere un modulo Blocco ricco di contenuti a una pagina

Per aggiungere un modulo Blocco ricco di contenuti a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello di pagina denominato **Modello contenuto**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Blocco ricco di contenuti.
1. Archiviare il modello e pubblicarlo.
1. Utilizzare il modello di contenuto appena creato per creare una pagina denominata **Pagina contenuto**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Blocco ricco di contenuti.
1. Nelle proprietà del modulo Blocco ricco di contenuti, impostare il numero di colonne su **2**.
1. Nel modulo Blocco ricco di contenuti, selezionare **Aggiungi un modulo** e aggiungere un elemento blocco ricco di contenuti (ad esempio **item1**).
1. Nel nuovo elemento blocco ricco di contenuti, aggiungere il testo di paragrafo.
1. Nel modulo Blocco ricco di contenuti, selezionare **Aggiungi un modulo** e aggiungere un elemento blocco ricco di contenuti (ad esempio **item2**).
1. Nel nuovo elemento blocco ricco di contenuti, aggiungere il testo di paragrafo.
1. Salvare la pagina e visualizzare un'anteprima delle modifiche Dovrebbero essere visualizzati due blocchi ricchi di contenuti in una visualizzazione a due colonne.
1. Archiviare la pagina e pubblicarla.

> [!NOTE]
> Se si aggiunge un terzo elemento blocco ricco di contenuti, verrà impilato sotto i due elementi aggiunti in precedenza. Modificando il numero di colonne ed elementi nel contenitore, è possibile ottenere differenti layout per contenuto testuale.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Avviso](add-alert.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Posizionamento contenuti](add-content-placement-modules.md)

[Modulo Funzionalità](add-feature-module.md)

[Modulo Hero](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)

