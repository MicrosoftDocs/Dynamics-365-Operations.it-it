---
title: Modulo Posizionamento contenuti
description: In questo argomento vengono descritti i moduli Posizionamento contenuti e i moduli Elemento posizionamento contenuti nonché la procedura per aggiungerli a pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1b64e930628c969334ff6e643ba23b77445e6e4c
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785302"
---
# <a name="content-placement-module"></a>Modulo Posizionamento contenuti

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Posizionamento contenuti e i moduli Elemento posizionamento contenuti nonché la procedura per aggiungerli a pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Posizionamento contenuti è un contenitore speciale in cui è possibile includere altri moduli in un layout specifico. I moduli Posizionamento contenuti supportano i seguenti tipi di moduli come moduli figlio: Elemento posizionamento contenuti, Elemento messaggio di benvenuto account, Elemento elenco preferenze account ed Elemento profilo account.

I moduli Posizionamento contenuti derivano i dati dai moduli figlio che supportano. Di conseguenza, i moduli Posizionamento contenuti possono essere utilizzati in vari modi, in base ai moduli che vengono aggiunti agli stessi.

I moduli Elemento posizionamento contenuti utilizzano immagini e testo per presentare promozioni, politiche e caratteristiche dei prodotti. Ad esempio, un modulo Elemento posizionamento contenuti può essere utilizzato in una home page per archiviare politiche o informazioni di spedizione del punto vendita. I moduli Elemento posizionamento contenuti sono basati sui dati del sistema di gestione dei contenuti (CMS) e possono essere utilizzati in qualsiasi pagina. Tuttavia, sono utilizzabili solo in un modulo Posizionamento contenuti.

## <a name="examples-of-content-placement-modules-in-e-commerce"></a>Esempi di moduli Posizionamento contenuti in e-Commerce

* I moduli Posizionamento contenuti che contengono moduli Elemento posizionamento contenuti possono essere utilizzati in una home page o in pagine marketing per presentare caratteristiche dei prodotti, promozioni, politiche del punto vendita, informazioni sulla spedizione e altre informazioni mediante immagini e testo.
* I moduli Posizionamento contenuti che contengono moduli Elemento posizionamento contenuti possono essere utilizzati nelle pagine dettagli prodotto per presentare le caratteristiche dei prodotti.
* I moduli Posizionamento contenuti che contengono moduli Elemento messaggio di benvenuto account o Elemento ordini account possono essere utilizzati nelle pagine di gestione account.

## <a name="content-placement-module-properties"></a>Proprietà del modulo Posizionamento contenuti

| Nome proprietà | Valore | Descrizione |
|---------------|-------|-------------|
| Larghezza         | **Adatta a contenitore** o **Riempi schermo** | Se il valore è **Adatta a contenitore**, gli elementi nel modulo Posizionamento contenuti sono limitati alla larghezza di quel modulo. Se il valore è **Riempi schermo**, gli elementi non sono limitati alla larghezza del modulo Posizionamento contenuti ma possono essere visualizzati in modalità a schermo intero. |

## <a name="content-placement-item-module-properties"></a>Proprietà del modulo Elemento posizionamento contenuti

| Nome proprietà | Valore | Descrizione |
|---------------|-------|-------------|
| Intestazione       | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Ogni modulo Elemento posizionamento contenuti può avere un'intestazione. La proprietà **Intestazione** supporta i tag di intestazione. Per impostazione predefinita, viene utilizzato il tag di intestazione **H2**, ma è possibile utilizzare un altro tag per soddisfare i requisiti di accessibilità. |
| Paragrafo     | Testo di paragrafo | I moduli Elemento posizionamento contenuti supportano testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo nonché collegamenti ipertestuali. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Immagine         | File di immagine | Un'immagine può essere associata al testo. |
| Collega          | URL e testo collegamento | Un collegamento può essere aggiunto al testo per reindirizzare gli utenti a una pagina specifica. |
| Dimensioni riquadro     | Un numero da **1** a **12** | Per ogni elemento posizionamento contenuti, questa proprietà definisce il numero di slot che l'elemento deve occupare nel modulo Posizionamento contenuti. La dimensione massima del modulo Posizionamento contenuti è 12 slot. Se la dimensione totale dei riquadri per i primi *n* elementi nel modulo Posizionamento contenuti supera i 12 slot, gli elementi vengono posizionati sulla riga successiva. |

## <a name="add-a-content-placement-module-that-contains-a-content-placement-item-module-to-a-page"></a>Aggiungere un modulo Posizionamento contenuti contenente un modulo Elemento posizionamento contenuti a una pagina

Per aggiungere un modulo Posizionamento contenuti contenente un modulo Elemento posizionamento contenuti a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello denominato **Modello posizionamento contenuti**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Posizionamento contenuti.
1. Nel modulo Posizionamento contenuti, aggiungere un modulo Elemento posizionamento contenuti.
1. Archiviare il modello e pubblicarlo.
1. Utilizzare il modello posizionamento contenuti appena creato per creare una pagina denominata **Pagina posizionamento contenuti**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Posizionamento contenuti.
1. Nel modulo Posizionamento contenuti, aggiungere un modulo Elemento posizionamento contenuti.
1. Nel riquadro delle proprietà del modulo Elemento posizionamento contenuti, selezionare un'immagine, aggiungere un'intestazione, un paragrafo e un collegamento, impostare l'URL collegamento e quindi impostare le dimensioni dei riquadri su **6**.
1. Ripetere i passaggi 7 e 8 per aggiungere un altro modulo Elemento posizionamento contenuti che ha le stesse dimensioni per i riquadri.
1. Salvare la pagina e visualizzarne l'anteprima. Dovrebbero essere visualizzati due elementi posizionamento contenuti visualizzati uno accanto all'altro. È possibile modificare la proprietà **Dimensioni riquadro** di ogni modulo Elemento posizionamento contenuti o aggiungere altri moduli per ottenere il layout desiderato.
1. Archiviare la pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Avviso](add-alert.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Blocco ricco di contenuti](add-content-rich-block.md)

[Modulo Funzionalità](add-feature-module.md)

[Modulo Hero](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)
