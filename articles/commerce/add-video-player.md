---
title: Modulo Lettore video
description: In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025653"
---
# <a name="video-player-module"></a>Modulo Lettore video


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il modulo Lettore video è utilizzato per supportare la riproduzione di video. Può essere aggiunto a qualsiasi pagina, a condizione che il contenuto del video sia caricato e disponibile nel sistema di gestione dei contenuti (CMS). Il modulo Lettore video supporta il tipo di file multimediale .mp4.

## <a name="video-player-module"></a>Modulo lettore video

Il modulo Lettore video può essere utilizzato per presentare video in un sito di e-Commerce. Supporta tutte le funzionalità di riproduzione, ad esempio riproduci, pausa, modalità a schermo intero, descrizioni audio e sottotitoli. Il modulo Lettore video supporta anche la personalizzazione dei sottotitoli per soddisfare gli standard di accessibilità di Microsoft. Ad esempio, è possibile personalizzare la dimensione dei caratteri e il colore di sfondo.

Il modulo del lettore video supporta anche tracce audio secondarie. Quando un video viene caricato in CMS, è anche possibile caricare una traccia audio secondaria. Il modulo del lettore video può quindi riprodurre la traccia audio secondaria se un utente la seleziona.

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
| Riproduci a schermo intero       | **True** o **False**               | Se il valore è impostato su **True**, il video viene riprodotto nella modalità a schermo intero. |
| Trigger riproduzione o pausa    | **True** o **False**               | Se il valore è impostato su **True**, un pulsante Riproduci/Pausa è visualizzato nel video. |
| Controlli lettore video | **True** o **False**               | Se il valore è impostato su **True**, tutti i controlli lettore video sono visualizzati. Questi controlli includono i pulsanti Riproduci e Pausa, un indicatore di avanzamento e opzioni per sottotitoli. |
| Nascondi immagine poster     | **True** o **False**               | Un video può avere un fotogramma di anteprima. Quando il valore di questa proprietà è **True**, il fotogramma di anteprima è nascosto. |
| Livello maschera            | Un numero da **0** a **100** | La maschera che viene applicata al video per la modifica dello stile. |

## <a name="add-a-video-player-module-to-a-page"></a>Aggiungere un modulo Lettore video a una pagina

> [!NOTE] 
> Prima di creare un modulo Lettore video, è necessario dapprima caricare un video nella libreria multimediale.

Per aggiungere un modulo Lettore video a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello di pagina denominato **Modello lettore video**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo contenitore.
1. Nel modulo contenitore, aggiungere i moduli Lettore video e Lettore video ambiente.
1. Completare la modifica del modello e pubblicarlo.
1. Utilizzare il modello lettore video creato per creare una pagina denominata **Pagina lettore video**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Lettore video.
1. Nel riquadro delle proprietà per il modulo Lettore video, selezionare **Aggiungi un video**.
1. Nella finestra di dialogo **Selettore multimediale**, selezionare un video e quindi **Carica nuovo elemento multimediale**.
1. Salvare la pagina e visualizzarne l'anteprima. Il modulo video dovrebbe essere visualizzato nella pagina. È possibile modificare ulteriori impostazioni per personalizzare il comportamento del modulo.
1. Completare la modifica della pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo banner promozionale](add-alert.md)

[Modulo Sequenza](add-carousel.md)

[Modulo blocco di testo](add-content-rich-block.md)

[Modulo blocco di contenuto](add-hero-module.md)
