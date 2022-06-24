---
title: Modulo lettore video
description: In questo articolo vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 20d516c58bf619065d57b27bc5a614eb7bd4cea9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873438"
---
# <a name="video-player-module"></a>Modulo lettore video

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Il modulo Lettore video è utilizzato per supportare la riproduzione di video. Può essere aggiunto a qualsiasi pagina, a condizione che il contenuto del video sia caricato e disponibile nel sistema di gestione dei contenuti (CMS). Il modulo Lettore video supporta il tipo di file multimediale .mp4.

## <a name="video-player-module"></a>Modulo Lettore video

Il modulo Lettore video può essere utilizzato per presentare video in un sito di e-Commerce. Supporta tutte le funzionalità di riproduzione, ad esempio riproduci, pausa, modalità a schermo intero, descrizioni audio e sottotitoli. Il modulo Lettore video supporta anche la personalizzazione dei sottotitoli per soddisfare gli standard di accessibilità di Microsoft. Ad esempio, è possibile personalizzare la dimensione dei caratteri e il colore di sfondo.

Il modulo Lettore video supporta anche tracce audio secondarie. Quando un video viene caricato in CMS, è anche possibile caricare una traccia audio secondaria. Il modulo Lettore video può quindi riprodurre la traccia audio secondaria se un utente la seleziona.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Esempi di moduli Lettore video in e-Commerce

- Video di istruzioni in pagine dettagli prodotto o in pagine marketing
- Video promozionali o video su policy in qualsiasi pagina marketing
- Video marketing che presentano le caratteristiche dei prodotti nelle pagine dettagli prodotto o nelle pagine marketing

L'immagine seguente mostra un esempio di modulo Lettore video in una home page.

![Esempio di un modulo Lettore video.](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Proprietà del modulo Lettore video

| Nome proprietà         | Valore                               | descrizione |
|-----------------------|-------------------------------------|-------------|
| Intestazione               | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Per impostazione predefinita, viene utilizzato il tag di intestazione **H2**, ma è possibile utilizzare un altro tag per soddisfare i requisiti di accessibilità. |
| RTF             | Testo paragrafo | Il modulo supporta testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio collegamenti ipertestuali e testo in grassetto, sottolineato e in corsivo. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Collega                  | Testo del collegamento, URL del collegamento, etichetta ARIA e selettore **Apri collegamento in una nuova scheda** | Il modulo supporta uno o più collegamenti "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda. |
| Sottotesto              | Intestazione, testo o collegamenti | È possibile aggiungere un contesto aggiuntivo per il modulo Lettore video, ad esempio un nome di autore o designer o collegamenti a blog personali. |
| Riproduzione automatica             | **True** o **False**               | Se il valore è impostato su **True**, il video viene automaticamente riprodotto. |
| Disattiva audio                  | **True** o **False**               | Se il valore è impostato su **True**, l'audio è disattivato. Per questo lettore, il valore predefinito è **False**. Nel browser Chrome, l'audio dei video riprodotti automaticamente è disattivato per impostazione predefinita e viene attivato solo se l'utente riproduce manualmente il video. |
| Ciclo                  | **True** o **False**               | Se il valore è impostato su **True**, il video viene ripetuto continuamente. |
| Multimediale                 | Percorso e nome del file video | Il file video riprodotto dal lettore. |
| Riproduci a schermo intero       | **True** o **False**               | Se il valore è impostato su **True**, il video viene riprodotto nella modalità a schermo intero. |
| Trigger riproduzione o pausa    | **True** o **False**               | Se il valore è impostato su **True**, un pulsante Riproduci/Pausa è visualizzato nel video. |
| Controlli lettore video | **True** o **False**               | Se il valore è impostato su **True**, tutti i controlli lettore video sono visualizzati. Questi controlli includono i pulsanti Riproduci e Pausa, un indicatore di avanzamento e opzioni per sottotitoli. |
| Nascondi immagine poster     | **True** o **False**               | Un video può avere un fotogramma di anteprima. Quando il valore di questa proprietà è **True**, il fotogramma di anteprima è nascosto. |
| Livello maschera            | Un numero da **0** a **100** | La maschera che viene applicata al video per la modifica dello stile. |

> [!IMPORTANT]
> Le proprietà **Intestazione**, **RTF**, **Collegamento** e **Sottotesto** sono disponibili a partire da Dynamics 365 Commerce, versione 10.0.20.

## <a name="add-a-video-player-module-to-a-page"></a>Aggiungere un modulo Lettore video a una pagina

> [!NOTE] 
> Prima di creare un modulo Lettore video, è necessario dapprima caricare un video nella libreria multimediale.

Per aggiungere un modulo Lettore video a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immetti **Modello lettore video**, quindi seleziona **OK**.
1. Nello slot **Corpo** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Pagina predefinita** e quindi seleziona **OK**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Lettore video** e quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo. 
1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, sotto **Nome pagina**, immetti **Pagina lettore video**, quindi seleziona **Avanti**.
1. Sotto **Scegli un modello**, seleziona il **modello di lettore video** creato e seleziona **Avanti**.
1. Sotto **Scegli un layout**, seleziona un layout di pagina (ad esempio, **Layout flessibile**), quindi seleziona **Avanti**.
1. Sotto **Verifica e termina**, rivedi la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, seleziona **Indietro**. Se le informazioni sulla pagina sono corrette, seleziona **Crea pagina**.
1. Nello slot **Principale** della nuova pagina, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Lettore video** e quindi seleziona **OK**.
1. Nel riquadro delle proprietà del modulo Lettore video, selezionare **Aggiungi un video**.
1. Nella finestra di dialogo **Selettore multimediale**, selezionare un video e quindi **Carica nuovo elemento multimediale**.
1. In Esplora file, selezionare un file video, quindi selezionare **Apri**.
1. Nella finestra di dialogo **Carica elemento multimediale**, immettere un titolo e altre informazioni come necessario e quindi selezionare **OK**.
1. Nella finestra di dialogo **Selettore multimediale** selezionare **Chiudi**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. Il modulo Video dovrebbe essere visualizzato nella pagina. È possibile modificare ulteriori impostazioni per personalizzare il comportamento del modulo.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo banner promozionale](add-alert.md)

[Modulo sequenza](add-carousel.md)

[Modulo blocco testo](add-content-rich-block.md)

[Modulo Blocco di contenuto](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
