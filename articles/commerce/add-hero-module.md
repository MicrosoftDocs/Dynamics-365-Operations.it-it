---
title: Modulo Hero
description: In questo argomento vengono descritti i moduli Hero e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785394"
---
# <a name="hero-module"></a>Modulo Hero

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Hero e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Hero è utilizzato per commercializzare prodotti o promozioni mediante una combinazione di immagini e testo. Ad esempio, un rivenditore può aggiungere un modulo Hero alla home page di un sito di e-Commerce per promuovere un nuovo prodotto e attirare l'attenzione dei clienti.

Un modulo Hero è basato sui dati del sistema di gestione dei contenuti (CMS). È un modulo autonomo che non dipende da alcun altro modulo nella pagina. Un modulo Hero può essere utilizzato in qualsiasi pagina del sito in cui un rivenditore desidera commercializzare o promuovere qualcosa (ad esempio prodotti, vendite o caratteristiche).

## <a name="examples-of-hero-module-in-e-commerce"></a>Esempi di modulo Hero in e-Commerce

- Un modulo Hero può essere utilizzato nella home page di un sito di e-Commerce per mettere in evidenza promozioni e nuovi prodotti.
- Un modulo Hero può essere utilizzato in una pagina dettagli prodotto per visualizzare informazioni sul prodotto.
- Molteplici moduli Hero possono essere utilizzati in un modulo Sequenza per mettere in evidenza più prodotti o promozioni.

## <a name="hero-module-properties"></a>Proprietà del modulo Hero

| Nome proprietà  | Valori | Descrizione |
|----------------|--------|-------------|
| Immagine          | File di immagine | Un'immagine può essere utilizzata per presentare un prodotto o una promozione. Un'immagine può essere caricata nella raccolta di immagini o è possibile utilizzare un'immagine esistente. |
| Intestazione        | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Ogni modulo Hero può avere un'intestazione. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |
| Paragrafo      | Testo di paragrafo | I moduli Hero supportano testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo nonché collegamenti ipertestuali. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Collega           | Testo del collegamento, URL del collegamento, etichetta ARIA e **Apri collegamento in una nuova scheda** | I moduli Hero supportano uno o più collegamenti "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda. |
| Posizionamento del testo | **Sinistra in alto**, **Destra in alto**, **Centro in alto**, **Sinistra in basso**, **Destra in basso**, **Centro in basso**, **Centro a sinistra**, **Centro a destra**, **Al centro**. | Questa proprietà definisce la posizione dell'immagine rispetto al testo. Ad esempio, se l'opzione **A destra** è selezionata, l'immagine viene visualizzata a destra del testo. |
| Tema testo     | **Chiaro** o **Scuro** | Una combinazione di colori può essere definita per il testo, in base all'immagine di sfondo. Ad esempio, se l'immagine ha uno sfondo scuro, un tema chiaro può essere utilizzato per rendere il testo più visibile e per soddisfare i rapporti di contrasto dei colori per scopi di accessibilità. |
| Gradiente       | **True** o **False** | Un gradiente può essere applicato all'immagine per soddisfare i rapporti di contrasto dei colori per scopi di accessibilità. |

## <a name="add-a-hero-module-to-a-new-page"></a>Aggiungere un modulo Hero a una nuova pagina

Per aggiungere un modulo Hero a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e creare un modello di pagina denominato **Modello hero**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Hero.
1. Archiviare il modello e pubblicarlo.
1. Utilizzare il modello hero appena creato per creare una pagina denominata **Pagina hero**.
1. Nello slot **Principale** della pagina predefinita, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** sotto **Seleziona moduli**, selezionare il modulo Hero e selezionare **OK**.
1. Nell'albero a sinistra, selezionare il modulo Hero.
1. Nel riquadro delle proprietà a destra, selezionare **Aggiungi immagine**. Quindi selezionare un'immagine esistente o caricare una nuova immagine.
1. Selezionare **Intestazione**.
1. Nella finestra di dialogo **Intestazione**, aggiungere il testo dell'intestazione, selezionare il livello di intestazione e quindi **OK**.
1. Sotto **RTF**, aggiungere testo come necessario.
1. Selezionare **Aggiungi collegamento azione**.
1. Nella finestra di dialogo **Collegamento azione**, aggiungere il testo, un URL e un'etichetta ARIA per il collegamento e selezionare **OK**.
1. Salvare la pagina e visualizzare un'anteprima delle modifiche.
1. Archiviare la pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Avviso](add-alert.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Blocco ricco di contenuti](add-content-rich-block.md)

[Modulo Posizionamento contenuti](add-content-placement-modules.md)

[Modulo Funzionalità](add-feature-module.md)

[Modulo Lettore video](add-video-player.md)
