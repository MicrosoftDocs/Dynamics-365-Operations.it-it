---
title: Aggiungere una favicon
description: In questo argomento viene descritto come aggiungere un favicon al sito.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 262e478d426fd913130b21a3434331c7d27b54b2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413390"
---
# <a name="add-a-favicon"></a>Aggiungere una favicon

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un favicon al sito.

## <a name="overview"></a>Panoramica

Un favicon è un piccolo file di grafica che viene visualizzato, tra l'altro, in una scheda del browser Web, nella barra degli indirizzi, nella cronologia delle esplorazioni e in segnalibri o preferiti. È consigliabile aggiungere un favicon al sito, poiché rappresenta e rinforza il marchio e consente di differenziare il proprio sito da altri siti visitati dai clienti.

Sebbene sia possibile aggiungere più favicon di varie dimensioni e tipi di file al sito, in questo argomento viene descritto coma aggiungere un singolo favicon. Tuttavia, lo stesso processo e la stessa posizione sono utilizzati per aggiungere più favicon.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Caricare un favicon nella raccolta di asset del sito

Per caricare un favicon nella raccolta di asset del sito, procedere come segue.

1. Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.
1. Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.
1. Nella finestra Esplora file andare al file di immagine del favicon da caricare, selezionarlo, quindi selezionare **Apri**.
1. Nella finestra di dialogo **Carica elemento multimediale**, immettere il titolo e il testo alternativo richiesti.
1. Per pubblicare l'immagine subito dopo il caricamento, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.

    > [!NOTE]
    > Se non si seleziona la casella di controllo **Pubblica elementi multimediali dopo il caricamento**, è necessario tornare alla pagina **Elementi multimediali** e pubblicare manualmente il favicon in un secondo momento.

1. Selezionare **OK**.
1. Nel riquadro delle proprietà a destra, copiare l'URL pubblico del favicon. L'URL verrà utilizzato in seguito.

## <a name="create-the-html-for-your-favicon"></a>Creare l'HTML per il favicon

Per creare l'HTML per il favicon, usare la stringa HTML seguente. Per l'attributo **href**, sostituire **Public\_URL\_for\_your\_favicon** con l'URL pubblico copiato in precedenza.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a>Creare un frammento contenente un metatag per il favicon

Per creare un frammento contenente un metatag per il favicon, effettuare le seguenti operazioni.

1. Andare a **Frammenti** e selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo frammento** selezionare **Metatag** come modulo su cui basare il frammento.
1. Immettere un nome per il frammento, quindi selezionare **OK**.
1. Nell'albero della gerarchia di frammenti, selezionare l'elemento figlio **Metatag predefiniti**.
1. Nel riquadro destro, sotto **Metatag**, selezionare **Aggiungi**, quindi immettere la stringa HTML creata in precedenza per il favicon. 
1. Selezionare **Fine modifica**, quindi selezionare **Pubblica** per pubblicare il frammento.

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a>Aggiungere il frammento dei metatag alla sezione di intestazione HTML delle pagine

Per aggiungere il frammento dei metatag alla sezione **head** di intestazione HTML delle pagine, effettuare le seguenti operazioni:

1. Andare a **Modelli**, aprire il modello per le pagine a cui aggiungere il favicon, quindi selezionare **Modifica**.
1. Nell'albero della gerarchia dei modelli, selezionare i puntini di sospensione (**...**) a destra del contenitore **Intestazione HTML**, quindi selezionare **Aggiungi frammento**.
1. Nella finestra di dialogo **Seleziona frammento**, selezionare il frammento dei metatag creato in precedenza, quindi selezionare **OK**.
1. Selezionare **Fine modifica**, quindi selezionare **Pubblica** per pubblicare il modello.

> [!NOTE]
> Se il tuo sito utilizza più di un modello, è necessario aggiungere il frammento dei metatag a ognuno di essi.

Quando si visualizzano in anteprima le pagine basate sul modello a cui è stato aggiunto il frammento dei metatag, si dovrebbe ora vedere il favicon nella scheda del browser.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

