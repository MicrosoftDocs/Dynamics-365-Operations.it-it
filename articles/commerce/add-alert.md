---
title: Modulo Avviso
description: In questo argomento vengono descritti i moduli Avviso e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785354"
---
# <a name="alert-module"></a>Modulo Avviso

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Avviso e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Avviso è utilizzato per visualizzare messaggi informativi in una pagina. I moduli Avviso supportano un messaggio di testo e un collegamento. Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce. 

I moduli Avviso sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.

## <a name="examples-of-alert-modules-in-e-commerce"></a>Esempi di moduli Avviso in e-Commerce

I moduli Avviso possono essere utilizzati nell'intestazione del sito per indicare promozioni o messaggi a livello di sito. Di seguito sono riportati alcuni esempi.

"La vendita annuale termina tra 10 giorni"

"Grandi risparmi con la vendita di articoli scolastici. Acquista ora".

## <a name="alert-module-properties"></a>Proprietà del modulo Avviso

| Nome proprietà  | Valore                              | Descrizione |
|----------------|------------------------------------|-------------|
| Testo           | Testo                               | Il messaggio di testo visualizzato nel modulo Avviso. |
| Allineamento testo | **A destra**, **A sinistra** o **Al centro** | Un valore che definisce il modo in cui il testo è allineato nel modulo Avviso. |
| Chiudi avviso  | **True** o **False**              | Se il valore è impostato su **True**, il cliente può chiudere l'avviso. |
| Collega           | URL                                | L'URL di un collegamento facoltativo. |

## <a name="add-an-alert-module-to-a-page"></a>Aggiungere un modulo Avviso a una pagina 

Per aggiungere un modulo Avviso a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello di pagina denominato **Modello avviso**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Avviso.
1. Archiviare il modello e pubblicarlo. 
1. Utilizzare il modello di avviso appena creato per creare una pagina denominata **Pagina avviso**. 
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Avviso.
1. Nelle impostazioni del modulo Avviso, immettere il testo dell'avviso. È possibile modificare le altre proprietà se si desidera personalizzare ulteriormente il modulo Avviso.
1. Salvare la pagina e visualizzarne l'anteprima. Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso con il testo aggiunto.
1. Archiviare la pagina e pubblicarla. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Blocco ricco di contenuti](add-content-rich-block.md)

[Modulo Posizionamento contenuti](add-content-placement-modules.md)

[Modulo Funzionalità](add-feature-module.md)

[Modulo Hero](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)
