---
title: Modulo Lettore video
description: In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 0612682d310362c7523bf08db40faf51c80ea2e3
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411161"
---
# <a name="video-player-module"></a>Modulo Lettore video


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Lettore video e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il modulo Lettore video è utilizzato per supportare la riproduzione di video. Può essere aggiunto a qualsiasi pagina, a condizione che il contenuto del video sia caricato e disponibile nel sistema di gestione dei contenuti (CMS). Il modulo Lettore video supporta il tipo di file multimediale .mp4.

## <a name="video-player-module"></a>Modulo Lettore video

Il modulo Lettore video può essere utilizzato per presentare video in un sito di e-Commerce. Supporta tutte le funzionalità di riproduzione, ad esempio riproduci, pausa, modalità a schermo intero, descrizioni audio e sottotitoli. Il modulo Lettore video supporta anche la personalizzazione dei sottotitoli per soddisfare gli standard di accessibilità di Microsoft. Ad esempio, è possibile personalizzare la dimensione dei caratteri e il colore di sfondo.

Il modulo Lettore video supporta anche tracce audio secondarie. Quando un video viene caricato in CMS, è anche possibile caricare una traccia audio secondaria. Il modulo Lettore video può quindi riprodurre la traccia audio secondaria se un utente la seleziona.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Esempi di moduli Lettore video in e-Commerce

- Video di istruzioni in pagine dettagli prodotto o in pagine marketing
- Video promozionali o video su policy in qualsiasi pagina marketing
- Video marketing che presentano le caratteristiche dei prodotti nelle pagine dettagli prodotto o nelle pagine marketing

L'immagine seguente mostra un esempio di modulo Lettore video in una home page.

![Esempio di modulo Lettore video](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Proprietà del modulo Lettore video

| Nome proprietà         | Valore                               | descrizione |
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

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello lettore video**, quindi selezionare **OK**.
1. Nello slot **Corpo** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Lettore video** e quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo. 
1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, selezionare il modello di lettore video creato. Sotto **Nome pagina**, Immettere **Pagina lettore video** e selezionare **OK**.
1. Nello slot **Principale** della nuova pagina, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Lettore video** e quindi selezionare **OK**.
1. Nel riquadro delle proprietà del modulo Lettore video, selezionare **Aggiungi un video**.
1. Nella finestra di dialogo **Selettore multimediale**, selezionare un video e quindi **Carica nuovo elemento multimediale**.
1. In Esplora file, selezionare un file video, quindi selezionare **Apri**.
1. Nella finestra di dialogo **Carica elemento multimediale**, immettere un titolo e altre informazioni come necessario e quindi selezionare **OK**.
1. Nella finestra di dialogo **Selettore multimediale** selezionare **Chiudi**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. Il modulo Video dovrebbe essere visualizzato nella pagina. È possibile modificare ulteriori impostazioni per personalizzare il comportamento del modulo.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Banner promozionale](add-alert.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Blocco di testo](add-content-rich-block.md)

[Modulo Blocco di contenuto](add-hero-module.md)
