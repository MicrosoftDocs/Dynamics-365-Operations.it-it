---
title: Modulo Funzionalità
description: In questo argomento vengono descritti i moduli Funzionalità e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785286"
---
# <a name="feature-module"></a>Modulo Funzionalità 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Funzionalità e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Funzionalità è utilizzato per commercializzare prodotti o promozioni mediante una combinazione di immagini e testo. Ad esempio, un rivenditore può aggiungere un modulo Funzionalità a una pagina dettagli prodotto per evidenziare le caratteristiche del prodotto.

Un modulo Funzionalità è basato sui dati del sistema di gestione dei contenuti (CMS). È un modulo autonomo che non dipende da alcun altro modulo nella pagina. Un modulo Funzionalità può essere utilizzato in qualsiasi pagina del sito in cui un rivenditore desidera commercializzare o promuovere qualcosa (ad esempio prodotti, vendite o caratteristiche).

## <a name="examples-of-feature-modules-in-e-commerce"></a>Esempi di moduli Funzionalità in e-Commerce

Un modulo Funzionalità può essere utilizzato nelle pagine seguenti:

- Una pagina dettagli prodotto, per presentare le caratteristiche del prodotto.
- La home page, per promuovere prodotti.
- Una pagina categoria, per evidenziare una categoria di prodotti.

## <a name="feature-module-properties"></a>Proprietà del modulo Funzionalità

| Nome proprietà     | Valori | Descrizione |
|-------------------|--------|-------------|
| Immagine             | File di immagine | Un'immagine può essere utilizzata per commercializzare il prodotto o una promozione. Un'immagine può essere caricata nella raccolta di immagini o è possibile utilizzare un'immagine esistente. |
| Intestazione           | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Ogni modulo Funzionalità può avere un'intestazione. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |
| Paragrafo         | Testo di paragrafo | I moduli Funzionalità supportano testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo nonché collegamenti ipertestuali. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Collega              | Testo del collegamento, URL del collegamento, etichetta ARIA e **Apri collegamento in una nuova scheda** | I moduli Funzionalità supportano uno o più collegamenti "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda. |
| Posizionamento immagine   | **A destra**, **A sinistra**, **In alto** o **In basso** | Questa proprietà definisce la posizione dell'immagine rispetto al testo. Ad esempio, se l'opzione **A destra** è selezionata, l'immagine viene visualizzata a destra del testo. |
| Dimensioni colonna immagine | Un valore da **1** a **12** | Questa proprietà definisce la dimensione dell'immagine rispetto al testo. La dimensione è espressa come numero di colonne nella pagina. Vi sono 12 colonne in una pagina. Per impostazione predefinita, l'immagine e il testo hanno la stessa dimensione (sei colonne ciascuno). Tuttavia, la dimensione può essere modificata secondo le esigenze. |

## <a name="add-a-feature-module-to-a-new-page"></a>Aggiungere un modulo Funzionalità a una nuova pagina 

Per aggiungere un modulo Funzionalità a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e creare un modello di pagina denominato **Modello funzionalità**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Funzionalità.
1. Archiviare il modello e pubblicarlo.
1. Utilizzare il modello funzionalità appena creato per creare una pagina denominata **Pagina funzionalità**.
1. Nello slot **Principale** della pagina predefinita, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** sotto **Seleziona moduli**, selezionare un modulo Funzionalità e quindi **OK**.
1. Nell'albero a sinistra, selezionare il modulo Funzionalità.
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

[Modulo Hero](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)
