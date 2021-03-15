---
title: Caricare e fornire file statici
description: Questo argomento descrive come caricare un file statico nel generatore di siti di Microsoft Dynamics 365 Commerce e come creare un URL e un nome file personalizzati che possono essere utilizzati per richiedere quel file.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1d709d99737ad05af1fb19d9f3ef7b87a8db80d3
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031822"
---
# <a name="upload-and-serve-static-files"></a>Caricare e fornire file statici

[!include [banner](includes/banner.md)]

Questo argomento descrive come caricare un file statico nel generatore di siti di Microsoft Dynamics 365 Commerce e come creare un URL e un nome file personalizzati che possono essere utilizzati per richiedere quel file.

Alcuni connettori di terze parti richiedono che un file sia ospitato e servito dal sito di e-commerce. Questi connettori prevedono che il file venga restituito dalle richieste in un percorso URL di callback e un nome file specifici. Pertanto, questo argomento spiega come caricare e servire un file statico con un URL e un nome file definibili dall'utente in un sito di e-commerce di Dynamics 365 Commerce.

## <a name="create-a-site-url-that-returns-a-static-file"></a>Crea un URL del sito che restituisca un file statico

Per creare un URL del sito che restituisce un file statico nel generatore di siti di Commerce, attenersi alla seguente procedura.

1. Andare alla libreria multimediale del sito e caricare il file che deve essere servito dalle richieste all'URL che verrà definito. Se è già stato caricato il file, è possibile saltare questo passaggio.
1. Andare a **URL** per il sito.
1. Selezionare **Nuovo \> Nuovo URL**.
1. Nella finestra di dialogo **Nuovo URL**, selezionare **Risorsa libreria multimediale**.
1. Nel campo **Percorso URL** inserire il percorso dell'URL. Includere il nome del file nel percorso.
1. Selezionare **Avanti**. La libreria multimediale viene aperta e mostra tutte le risorse multimediali di tipo **documento** che sono state caricate.
1. Seleziona il file che deve essere servito per le richieste all'URL definito nel passaggio 5.
1. Selezionare **Salva**.

A questo punto, l'URL creato è in stato bozza. Il file a cui punta l'URL non verrà restituito finché non si pubblica l'URL. Prima di pubblicare l'URL, è possibile verificare che restituisca i dati corretti.

## <a name="validate-and-publish-a-url"></a>Convalidare e pubblicare un URL

Per convalidare un URL prima di pubblicarlo, attenersi alla seguente procedura.

1. Andare a **URL** per il sito e selezionare l'URL da visualizzare in anteprima.
2. Nel riquadro delle proprietà a destra, sotto il pulsante **Modifica** selezionare il collegamento URL corretto. Si apre una nuova finestra del browser e viene visualizzato un errore 404.
3. Aggiungere la stringa di query **?preview=inprogress** all'URL (ad esempio, `https://yoursite.com/callback.html?preview=inprogress`) e ricaricare la pagina. Il file caricato nella libreria multimediale viene restituito nella risposta.

Dopo aver convalidato l'URL, è possibile pubblicarlo.

1. Andare a **URL** per il sito e selezionare l'URL.
2. Nella barra dei comandi selezionare **Pubblica**.

## <a name="update-the-file-that-a-url-points-to"></a>Aggiornare il file a cui punta un URL

Dopo che un URL è stato pubblicato, è possibile aggiornarlo in modo che punti a un file diverso. In alternativa, è possibile aggiornare l'URL in modo che punti a un diverso tipo di risorsa, come descritto nella sezione successiva. Ad esempio, è possibile puntare l'URL a una pagina interna o a un reindirizzamento.

Per aggiornare il file a cui punta un URL, seguire questi passaggi.

1. Andare a **URL** per il sito e selezionare l'URL da aggiornare.
1. Nel riquadro delle proprietà a destra, selezionare **Modifica**.
1. Sotto **Assegnazione URL**, selezionare la casella **Passaggio 2** quindi selezionare un nuovo documento dalla libreria multimediale.
1. Selezionare **Applica**.

## <a name="update-the-asset-type-that-a-url-points-to"></a>Aggiornare il tipo di risorsa a cui punta un URL

È anche possibile aggiornare un URL in modo che punti a un diverso tipo di risorsa (asset), come una pagina interna o un reindirizzamento.

Per aggiornare il tipo di risorsa a cui punta un URL, seguire questi passaggi.

1. Andare a **URL** per il sito e selezionare l'URL da aggiornare.
1. Nel riquadro delle proprietà a destra, selezionare **Modifica**.
1. Sotto **Assegnazione URL**, sotto **Passaggio 1**, selezionare un altro tipo di risorsa.
1. Selezionare la casella **Passaggio 2** quindi selezionare la nuova risorsa.
1. Selezionare **Applica**.

## <a name="change-the-url-path"></a>Modificare il percorso dell'URL

Dopo aver creato un URL, il suo percorso non può essere modificato. Se è necessario modificare il percorso dell'URL che serve un file o qualsiasi altro tipo di risorsa, è necessario creare un nuovo URL, mapparlo al file esistente o un'altra risorsa, quindi annullare la pubblicazione ed eliminare il vecchio URL.

Per modificare il percorso dell'URL, eseguire le operazioni indicate di seguito.

1. Per creare un nuovo URL e mapparlo al file esistente o a un'altra risorsa, seguire le istruzioni nella precedente sezione [Creare un URL del sito che restituisca un file statico](#create-a-site-url-that-returns-a-static-file) in questo argomento.
1. Selezionare il nuovo URL e selezionare **Pubblica** sulla barra dei comandi. Il nuovo URL viene pubblicato.
1. Per annullare la pubblicazione del vecchio URL, selezionalo, quindi selezionare **Annulla pubblicazione** sulla barra dei comandi. È possibile ora eliminare il vecchio URL se si desidera.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della gestione cespiti digitali](dam-overview.md)

[Caricare immagini](dam-upload-images.md)

[Caricare i video](dam-upload-video.md)

[Caricare file diversi da immagini e video](dam-upload-files.md)

[Tagliare immagini](dam-crop-images.md)

[Personalizzare punti focali immagine](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]