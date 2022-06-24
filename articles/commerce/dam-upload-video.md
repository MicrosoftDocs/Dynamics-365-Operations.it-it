---
title: Caricare i video
description: In questo articolo viene descritto come caricare i video in Creazione di siti Web Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a48c6cbdd5898a2156f60dada40e94cd402df9c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890543"
---
# <a name="upload-videos"></a>Caricare i video

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come caricare i video in Creazione di siti Web Microsoft Dynamics 365 Commerce.

La libreria multimediale Creazione di siti Web Commerce consente di caricare i video. È sempre necessario caricare la versione di un video con il bitrate e la risoluzione più alti, perché il video verrà automaticamente convertito per essere adatto a diversi riquadri di visualizzazione e ai punti di interruzione.

### <a name="video-information-specified-during-upload"></a>Informazioni sul video specificate durante il caricamento

Quando si carica un video, è possibile specificare le seguenti informazioni.

- **Titolo, Descrizione, parole chiave**: i metadati del video.
- **Genera automaticamente sottotitoli**: specifica se i sottotitoli devono essere generati automaticamente per il video (è supportata solo la lingua inglese). 
- **Sottotitolo**: specifica i sottotitoli da utilizzare.
- **Audio normale**: specifica la traccia audio normale da utilizzare.
- **Anteprima**: specifica l'anteprima per il video. Se non specificata, verrà generata automaticamente.
- **Audio descrittivo**: specifica la traccia audio descrittivo da utilizzare.

## <a name="upload-a-video"></a>Caricare un video

Per caricare un video in Creazione di siti Web, attenersi alla seguente procedura.

1. Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.
1. Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.
1. Nella finestra Esplora file, individuare e selezionare uno o più file video da caricare, quindi selezionare **Apri**.
1. Nella finestra di dialogo **Carica elemento multimediale**, immettere il titolo e il testo alternativo richiesti.
1. Immettere una descrizione e le parole chiave facoltative e selezionare una categoria, se lo si desidera. 
1. Se si desidera pubblicare le immagini immediatamente dopo averle caricate, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**
1. Selezionare **OK**.

Se si stanno caricando più tipi di risorse contemporaneamente (ad esempio, immagini e video), nella finestra di dialogo **Carica elemento multimediale** sarà possibile specificare solo parole chiave, se i file devono essere pubblicati immediatamente dopo il caricamento e se i sottotitoli devono essere generati automaticamente per i file video. Tutte le risorse condivideranno le stesse parole chiave.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della gestione risorse digitali](dam-overview.md)

[Caricare immagini](dam-upload-images.md)

[Caricare file](dam-upload-files.md)

[Tagliare immagini](dam-crop-images.md)

[Personalizzare punti focali immagine](dam-custom-focal-point.md)

[Caricare e fornire file statici](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
