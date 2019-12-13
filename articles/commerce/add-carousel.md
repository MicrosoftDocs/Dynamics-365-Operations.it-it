---
title: Modulo Sequenza
description: In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785239"
---
# <a name="carousel-module"></a>Modulo Sequenza

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Sequenza viene utilizzato per inserire molteplici articoli promozionali in una sequenza che i clienti possono vedere. Si tratta di un modulo contenitore speciale che ospita altri moduli. Ad esempio, un rivenditore può utilizzare un modulo Sequenza in una home page per presentare molteplici nuovi prodotti o promozioni.

È possibile aggiungere moduli Hero e Funzionalità a un modulo Sequenza. Le proprietà del modulo Sequenza definiscono quindi il modo in cui viene eseguito il rendering di tali moduli.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Esempi di moduli Sequenza in e-Commerce

- Una sequenza che include più moduli promozionali può essere utilizzata in una home page.
- Una sequenza con più moduli promozionali può essere utilizzata in una pagina dettagli prodotto.
- Una sequenza può essere utilizzata in qualsiasi pagina marketing per promuovere molteplici promozioni o prodotti.

## <a name="carousel-module-properties"></a>Proprietà del modulo Sequenza

| Nome proprietà             | Valore                                | Descrizione |
|---------------------------|--------------------------------------|-------------|
| Riproduzione automatica                  | **True** o **False**                | Se il valore è impostato su **True**, la transizione tra gli articoli nella sequenza viene eseguita automaticamente. Se il valore è impostato su **False**, non viene eseguita alcuna transizione a meno che il cliente non utilizzi la tastiera o il mouse per passare da un articolo all'articolo successivo. |
| Intervallo di transizione diapositiva | Un valore in secondi                   | L'intervallo delle transizioni tra gli articoli. |
| Animazione transizione      | **Diapositiva** o **Dissolvenza**                | L'effetto di transizione. |
| Larghezza                     | **Adatta a contenitore** o **Riempi schermo** | Se il valore è **Adatta a contenitore**, gli elementi nella sequenza sono limitati alla larghezza della sequenza. Se il valore impostato è **Riempi schermo**, gli elementi non sono limitati alla larghezza della sequenza ma possono essere visualizzati in modalità a schermo intero. È possibile modificare il valore per ottenere il layout desiderato. |

## <a name="add-a-carousel-module-to-a-page"></a>Aggiungere un modulo Sequenza a una pagina

Per aggiungere un modulo Sequenza a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello di pagina denominato **Modello sequenza**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Sequenza.
1. Aggiungere un modulo Hero al modulo Sequenza.
1. Aggiungere un modulo Funzionalità al modulo Sequenza.
1. Archiviare il modello e pubblicarlo. 
1. Utilizzare il modello sequenza appena creato per creare una pagina denominata **Pagina sequenza**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Sequenza.
1. Impostare la proprietà **Larghezza** del modulo Sequenza su **Riempi schermo**. 
1. Impostare la proprietà **Animazione transizione** su **Diapositiva**.
1. Aggiungere un modulo Hero al modulo Sequenza.
1. Nel modulo Hero, aggiungere un'immagine e un'intestazione, quindi selezionare **Salva**.
1. Aggiungere un modulo Funzionalità al modulo Sequenza.
1. Nel modulo Funzionalità, aggiungere un'immagine, un'intestazione e un paragrafo di testo.
1. Salvare la pagina e visualizzarne l'anteprima. La pagina dovrebbe visualizzare una sequenza con due moduli (un modulo Hero e un modulo Funzionalità). È possibile modificare ulteriori proprietà dei moduli Sequenza, Hero e Funzionalità per ottenere l'effetto desiderato.
1. Archiviare la pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Avviso](add-alert.md)

[Modulo Blocco ricco di contenuti](add-content-rich-block.md)

[Modulo Posizionamento contenuti](add-content-placement-modules.md)

[Modulo Funzionalità](add-feature-module.md)

[Modulo Hero](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)
