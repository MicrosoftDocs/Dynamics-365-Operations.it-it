---
title: Aggiungere una favicon
description: In questo argomento viene descritto come aggiungere un favicon al sito.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.openlocfilehash: 287663817232e7ce86e8fdb1fb5c2fcfeed33d20
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001541"
---
# <a name="add-a-favicon"></a>Aggiungere una favicon


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un favicon al sito.

## <a name="overview"></a>Panoramica

Un favicon è un piccolo file di grafica che viene visualizzato, tra l'altro, in una scheda del browser Web, nella barra degli indirizzi, nella cronologia delle esplorazioni e in segnalibri o preferiti. È consigliabile aggiungere un favicon al sito, poiché rappresenta e rinforza il marchio e consente di differenziare il proprio sito da altri siti visitati dai clienti.

Sebbene sia possibile aggiungere più favicon di varie dimensioni e tipi di file al sito, in questo argomento viene descritto coma aggiungere un singolo favicon. Tuttavia, lo stesso processo e la stessa posizione sono utilizzati per aggiungere più favicon.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Caricare un favicon nella raccolta di asset del sito

Per caricare un favicon nella raccolta di asset del sito, procedere come segue.

1. Scegliere **Asset \> Carica \> Carica asset**.
1. Trovare e selezionare il favicon nel file system locale.
1. Immettere un titolo e selezionare **OK**. 
1. Nel riquadro delle proprietà a destra, copiare l'URL pubblico del favicon.

> [!NOTE]
> Se non si seleziona l'opzione **Pubblica asset dopo caricamento**, è necessario tornare alla pagina **Cespiti** e pubblicare manualmente il favicon in un momento successivo.

## <a name="create-the-html-for-the-favicon"></a>Creare il codice HTML per il favicon

Per creare il codice HTML per il favicon, utilizzare il seguente frammento HTML. Per l'attributo **href**, sostituire **"URL\_pubblico\_per\_il\_favicon"** con l'URL pubblico copiato in precedenza.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a>Aggiungere il codice HTML per il favicon all'elemento \<intestazione\> delle pagine

Per aggiungere un favicon al sito, utilizzare la stessa procedura utilizzata per aggiungere qualsiasi tipo di codice HTML o script all'elemento **\<intestazione\>** delle pagine del sito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

