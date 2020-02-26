---
title: Modulo banner promozionale
description: In questo argomento vengono descritti i moduli banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025622"
---
# <a name="promo-banner-module"></a>Modulo banner promozionale


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I moduli banner promozionale sono utilizzati per visualizzare messaggi informativi incorporati in una pagina. Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce. 

I moduli banner promozionale supportano un messaggio di testo e un collegamento. Se vengono aggiunti più messaggi a un modulo banner promozionale, questo diventa un banner sequenza rotante che consente ai clienti di scorrere tutti i messaggi. 

I moduli banner promozionale sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Esempi di utilizzo di banner promozionali in e-Commerce

I banner promozionali possono essere utilizzati nell'intestazione del sito per mostrare promozioni o messaggi in tutto il sito, come negli esempi seguenti.

"La vendita annuale termina tra 10 giorni"

"Grandi risparmi con la vendita di articoli scolastici. Acquista ora".

## <a name="promo-banner-module-properties"></a>Proprietà dei moduli banner promozionale

| Nome proprietà             | Value                              | Descrizione |
|---------------------------|------------------------------------|-------------|
| Messaggi banner           | Testo e collegamenti                     | Una matrice di testo e collegamenti. |
| Riproduzione automatica                  | **True** o **False**              | Un valore che indica se i messaggi vengono automaticamente passati in rassegna, se sono configurati più messaggi. |
| Intervallo di transizione diapositiva | Un numero di millisecondi (ms)      | L'intervallo utilizzato per scorrere i messaggi. |
| Consenti chiusura             | **True** o **False**              | Se il valore è impostato su **True**, i clienti possono chiudere l'avviso. |
| Mostra flipper sequenza     | **True** o **False**              | Un valore che indica se i flipper della sequenza devono essere visualizzati, di modo che i clienti possano scorrere manualmente più elementi del banner. |
| Allineamento testo            | **A destra**, **A sinistra** o **Al centro** | L'allineamento del testo nel modulo banner promozionale. |
| Collega                      | URL A                              | L'URL di un collegamento facoltativo. |

## <a name="add-a-promo-banner-module-to-a-page"></a>Aggiungere un modulo banner promozionale a una pagina 

Per aggiungere un modulo banner promozionale a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello pagina denominato **Modello banner promozionale**.
1. Sotto **Struttura pagina** , aggiungere un modulo **Pagina predefinita** allo slot **Corpo**. 
1. Archiviare il modello e pubblicarlo. 
1. Utilizzare il modello appena creato per creare una pagina denominata **Pagina banner promozionale**. 
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore. 
1. Nel riquadro a destra, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Sotto **Struttura pagina**, aggiungere un modulo banner promozionale al modulo contenitore.
1. Nelle impostazioni per il modulo banner, aggiungere uno o più messaggi banner. Ogni messaggio può avere del testo e un collegamento. È possibile modificare le altre proprietà per personalizzare ulteriormente il modulo.
1. Salvare la pagina e visualizzarne l'anteprima. Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso che mostra il testo aggiunto.
1. Completare la modifica della pagina e pubblicarla. 

> [!NOTE]
> Un banner promozionale viene in genere utilizzato nello slot dell'intestazione di pagina o in uno slot del sottotitolo.


## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Sequenza](add-carousel.md)

[Modulo blocco di testo](add-content-rich-block.md)

[modulo blocco di contenuto](add-hero-module.md)

[Modulo lettore video](add-video-player.md)
