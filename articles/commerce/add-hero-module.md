---
title: Modulo blocco contenuto
description: In questo articolo vengono descritti i moduli blocco di contenuto e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: dc6d728f49befd0c156340379dba05f592ca7919
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277002"
---
# <a name="content-block-module"></a>Modulo blocco contenuto

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli blocco di contenuto e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Un modulo blocco di contenuto è utilizzato per commercializzare prodotti o promozioni mediante una combinazione di immagini e testo. Ad esempio, un rivenditore può aggiungere un modulo blocco di contenuto alla home page di un sito di e-Commerce per promuovere un nuovo prodotto e attirare l'attenzione dei clienti.

Un modulo blocco di contenuto è basato sui dati del sistema di gestione dei contenuti (CMS). È un modulo autonomo che non dipende da alcun altro modulo nella pagina. Un modulo blocco di contenuto può essere utilizzato in qualsiasi pagina del sito in cui un rivenditore desidera commercializzare o promuovere qualcosa (ad esempio prodotti, vendite o caratteristiche).

## <a name="examples-of-content-block-module-in-e-commerce"></a>Esempi di modulo blocco di contenuto in e-Commerce

- Un modulo blocco di contenuto può essere utilizzato nella home page di un sito di e-Commerce per mettere in evidenza promozioni e nuovi prodotti.
- Un modulo blocco di contenuto può essere utilizzato in una pagina dettagli prodotto per visualizzare informazioni sul prodotto.
- Molteplici moduli blocco di contenuto possono essere utilizzati in un modulo Sequenza per mettere in evidenza più prodotti o promozioni.

## <a name="content-block-modules-and-themes"></a>Moduli blocco di contenuto e temi

I moduli blocco di contenuto possono supportare vari layout e stili in base a un tema. Ad esempio, il tema Fabrikam supporta tre varianti di layout di un modulo blocco di contenuto: hero, funzionalità e riquadro. Il layout hero mostra un'immagine in background con sovrapposizione di testo. Il layout funzionalità mostra un'immagine e testo affiancati. Il layout riquadro consente più blocchi di contenuto in un formato riquadro.

Inoltre, il tema può esporre proprietà differenti per ciascun layout. Uno sviluppatore di temi può creare più layout con più stili utilizzando il modulo blocco di contenuto.

L'immagine seguente mostra un esempio di modulo blocco di contenuto con un layout hero.

![Esempio di un modulo Hero.](./media/Hero.PNG)

L'immagine seguente mostra un esempio di modulo blocco di contenuto con un layout funzionalità.

![Esempi di moduli Funzionalità.](./media/Feature.PNG)

## <a name="content-block-module-properties"></a>Proprietà dei moduli blocco di contenuto

| Nome proprietà  | Valori | descrizione |
|----------------|--------|-------------|
| Immagine          | File di immagine | Un'immagine può essere utilizzata per presentare un prodotto o una promozione. Un'immagine può essere caricata nella raccolta di immagini o è possibile utilizzare un'immagine esistente. |
| Intestazione        | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Ogni modulo Hero può avere un'intestazione. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |
| Paragrafo      | Testo di paragrafo | I moduli Hero supportano testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo nonché collegamenti ipertestuali. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Collega           | Testo del collegamento, URL del collegamento, etichetta ARIA e **Apri collegamento in una nuova scheda** | I moduli Hero supportano uno o più collegamenti "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda. |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a>Proprietà dei moduli blocco di contenuto esposte dal tema Fabrikam 

| Nome proprietà  | Valori | Descrizione |
|----------------|--------|-------------|
| Posizionamento del testo | **Sinistra**, **Destra**, **Centro** | Questa proprietà definisce la posizione del testo nell'immagine. Si applica solo al layout hero. |
| Tema testo     | **Chiaro** o **Scuro** | Una combinazione di colori può essere definita per il testo, in base all'immagine di sfondo. Ad esempio, se l'immagine ha uno sfondo scuro, un tema chiaro può essere utilizzato per rendere il testo più visibile e per soddisfare i rapporti di contrasto dei colori per scopi di accessibilità. Si applica solo al layout hero.|
| Posizionamento immagine       | **Sinistra**, **Destra** | Questa proprietà specifica se l'immagine deve essere a sinistra o a destra del testo. Si applica solo al layout funzionalità.  |

## <a name="add-a-content-block-module-to-a-new-page"></a>Aggiungere un modulo blocco di contenuto a una nuova pagina

Per aggiungere un modulo Hero a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e creare un modello di pagina denominato **Modello blocco di contenuto**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Hero.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Utilizzare il modello hero appena creato per creare una pagina denominata **Pagina blocco di contenuto**.
1. Nello slot **Principale** della pagina predefinita, seleziona il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo banner e quindi **OK**.
1. Nell'albero a sinistra, selezionare il modulo blocco di contenuto.
1. Nel riquadro delle proprietà a destra, selezionare **Aggiungi immagine**. Quindi selezionare un'immagine esistente o caricare una nuova immagine.
1. Selezionare **Intestazione**.
1. Nella finestra di dialogo **Intestazione**, aggiungere il testo dell'intestazione, selezionare il livello di intestazione e quindi **OK**.
1. Sotto **RTF**, aggiungere testo come necessario.
1. Selezionare **Aggiungi collegamento**.
1. Nella finestra di dialogo **Collegamento**, aggiungere il testo, un URL e un'etichetta ARIA per il collegamento e selezionare **OK**.
1. Selezionare il layout **Hero**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo banner promozionale](add-alert.md)

[Modulo sequenza](add-carousel.md)

[Modulo blocco testo](add-content-rich-block.md)

[Modulo lettore video](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
