---
title: Aggiungere un messaggio di benvenuto
description: In questo argomento viene descritto come aggiungere un messaggio di benvenuto al sito Web di Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5910ab85b1b0b2df992a24ad3cf7a032e7b98ea9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980134"
---
# <a name="add-a-welcome-message"></a>Aggiungere un messaggio di benvenuto


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un messaggio di benvenuto al sito Web di Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un messaggio di benvenuto nel sito Web di e-Commerce può informare i visitatori sulle vendite in corso, gli aggiornamenti del sito o la disponibilità delle collezioni stagionali. Il messaggio di benvenuto viene impostato mediante il modulo Avviso.

Il modulo Avviso non deve essere aggiunto allo slot **Messaggi informativi/di errore** del frammento intestazione. Il modulo Avviso consente di specificare il testo visualizzato, il colore del testo e l'allineamento. Consente inoltre di specificare se i visitatori del sito possono chiudere il messaggio.

Quando un messaggio di benvenuto viene aggiunto a un frammento intestazione condiviso, viene visualizzato in ogni pagina che utilizza il modello in cui è utilizzato il frammento intestazione condiviso.

Per aggiungere un messaggio di benvenuto al sito, effettuare le seguenti operazioni.

1. In Creazione di siti Web di Commerce, accedere al sito.
1. Selezionare **Frammenti**.
1. Selezionare il frammento intestazione a cui aggiungere il messaggio.
1. Nell'albero, espandere **Messaggi informativi/di errore**.
1. Selezionare il modulo Avviso e quindi **OK**. Se un modulo Avviso non esiste, selezionare prima il pulsante con i puntini di sospensione (**...**) accanto a **Messaggi informativi/di errore** e quindi selezionare **Aggiungi modulo**.
1. Nel riquadro delle proprietà a destra, nella scheda **Dati** selezionare **Aggiungi origine dati** e quindi **Contenuto**.
1. Nel campo **Inserisci testo**, immettere il testo del messaggio di benvenuto.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento di intestazione, quindi selezionare **Pubblica** per pubblicarlo. 

Il messaggio di benvenuto viene visualizzato nella parte superiore di ogni pagina del sito che utilizza il frammento intestazione selezionato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

