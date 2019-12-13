---
title: Modulo Lettore video
description: In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 32504351f712c83ba8f593c17d2e51c532374311
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785331"
---
# <a name="video-player-module"></a>Modulo Lettore video

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I moduli Lettore video vengono utilizzati per supportare la riproduzione di video. Due moduli Lettore video sono disponibili nello starter kit del punto vendita: il modulo Lettore video ambiente e il modulo Lettore video. Entrambi i lettori supportano il formato multimediale .mp4.

## <a name="ambient-video-player-module"></a>Modulo Lettore video ambiente

Il modulo Lettore video ambiente supporta video informativi brevi. Deve essere utilizzato per video la cui durata è inferiore a cinque secondi. Questo lettore supporta funzionalità di riproduzione di video limitate, ad esempio un pulsante Riproduci/Pausa.

### <a name="examples-of-ambient-video-player-modules-in-e-commerce"></a>Esempi di moduli Lettore video ambiente in e-Commerce

- Video informativi brevi che presentano nuovi prodotti nella home page
- Video informativi brevi che presentano le caratteristiche dei prodotti in una pagina dettagli prodotto

### <a name="ambient-video-player-module-properties"></a>Proprietà del modulo Lettore video ambiente

| Nome proprietà     | Valore                 | Descrizione |
|-------------------|-----------------------|-------------|
| Riproduzione automatica          | **True** o **False** | Se il valore è impostato su **True**, il video viene automaticamente riprodotto. |
| Disattiva audio              | **True** o **False** | Se il valore è impostato su **True**, l'audio è disattivato. Per questo lettore, il valore predefinito è **True**. Nel browser Google Crome, l'audio dei video riprodotti automaticamente viene disattivato per impostazione predefinita e viene attivato solo se l'utente riproduce manualmente il video. |
| Ciclo              | **True** o **False** | Se il valore è impostato su **True**, il video viene ripetuto continuamente. |
| Multimediale             |  Percorso e nome del file video | Il file video riprodotto dal lettore. |
| Comandi di riproduzione | **True** o **False** | Se il valore è impostato su **True**, un pulsante Riproduci/Pausa è visualizzato nel video. Se il valore è impostato su **False**, il pulsante Riproduci/Pausa non è visualizzato, ma gli utenti possono comunque sospendere e riprendere la riproduzione utilizzando la tastiera. |

## <a name="video-player-module"></a>Modulo Lettore video

Il modulo Lettore video può essere utilizzato per presentare video in un sito di e-Commerce. Supporta tutte le funzionalità di riproduzione, ad esempio riproduci, pausa, modalità a schermo intero e sottotitoli. Il modulo Lettore video supporta anche la personalizzazione dei sottotitoli per soddisfare gli standard di accessibilità di Microsoft. Ad esempio, è possibile personalizzare la dimensione dei caratteri e il colore di sfondo.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Esempi di moduli Lettore video in e-Commerce

- Video di istruzioni in pagine dettagli prodotto o in pagine marketing
- Video promozionali o video su policy in qualsiasi pagina marketing
- Video marketing che presentano le caratteristiche dei prodotti nelle pagine dettagli prodotto o nelle pagine marketing

### <a name="video-player-module-properties"></a>Proprietà del modulo Lettore video

| Nome proprietà         | Valore                               | Descrizione |
|-----------------------|-------------------------------------|-------------|
| Riproduzione automatica             | **True** o **False**               | Se il valore è impostato su **True**, il video viene automaticamente riprodotto. |
| Disattiva audio                  | **True** o **False**               | Se il valore è impostato su **True**, l'audio è disattivato. Per questo lettore, il valore predefinito è **False**. Nel browser Chrome, l'audio dei video riprodotti automaticamente è disattivato per impostazione predefinita e viene attivato solo se l'utente riproduce manualmente il video. |
| Ciclo                  | **True** o **False**               | Se il valore è impostato su **True**, il video viene ripetuto continuamente. |
| Multimediale                 | Percorso e nome del file video | Il file video riprodotto dal lettore. |
| Comandi di riproduzione     | **True** o **False**               | Se il valore è impostato su **True**, un pulsante Riproduci/Pausa è visualizzato nel video. Se il valore è impostato su **False**, il pulsante Riproduci/Pausa non è visualizzato, ma gli utenti possono comunque sospendere e riprendere la riproduzione utilizzando la tastiera. |
| Riproduci a schermo intero       | **True** o **False**               | Se il valore è impostato su **True**, il video viene riprodotto nella modalità a schermo intero. |
| Controlli              | **True** o **False**               | Se il valore è impostato su **True**, tutti i controlli sono visualizzati. Questi controlli includono i pulsanti Riproduci e Pausa, un indicatore di avanzamento e sottotitoli. |
| Nascondi fotogramma di anteprima     | **True** o **False**               | Un video può avere un fotogramma di anteprima. Quando il valore di questa proprietà è **True**, il fotogramma di anteprima è nascosto. |
| Livello maschera            | Un numero da **0** a **100** | La maschera che viene applicata al video per la modifica dello stile. |
| Stile icona schermo intero | **Quadrato** o **Freccia**             | Lo stile dell'icona della modalità a schermo intero visualizzata nel lettore video. |

## <a name="add-a-video-player-module-to-a-page"></a>Aggiungere un modulo Lettore video a una pagina

Per aggiungere un modulo Lettore video a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello di pagina denominato **Modello lettore video**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo contenitore.
1. Nel modulo contenitore, aggiungere i moduli Lettore video e Lettore video ambiente.
1. Archiviare il modello e pubblicarlo.
1. Utilizzare il modello lettore video appena creato per creare una pagina denominata **Pagina lettore video**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Lettore video ambiente.
1. Nelle impostazioni del modulo Lettore video ambiente, passare a **Multimedia** e caricare un file video. È possibile modificare **Riproduci automaticamente**, **Ciclo** e altre proprietà come necessario.
1. Salvare la pagina e visualizzarne l'anteprima.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Lettore video.
1. Nelle impostazioni del modulo Lettore video, passare a **Multimedia** e caricare un file video.
1. Salvare la pagina e visualizzarne l'anteprima. Entrambi i moduli video dovrebbero apparire nella pagina. È possibile modificare ulteriori impostazioni per personalizzare il comportamento di ciascun modulo.
1. Archiviare la pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Avviso](add-alert.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Blocco ricco di contenuti](add-content-rich-block.md)

[Modulo Posizionamento contenuti](add-content-placement-modules.md)

[Modulo Funzionalità](add-feature-module.md)

[Modulo Hero](add-hero-module.md)
