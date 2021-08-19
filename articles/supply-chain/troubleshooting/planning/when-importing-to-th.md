---
title: Ti viene chiesto di salvare le impostazioni di copertura degli articoli anche se non hai apportato modifiche
description: Ti viene chiesto di salvare le impostazioni di copertura degli articoli anche se non hai apportato modifiche.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 29ee23164430f219ff3d0c94216a8be43f480ce309f6cdac3dac6ed5b6d030af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730084"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a>Ti viene chiesto di salvare le impostazioni di copertura degli articoli anche se non hai apportato modifiche

Numero KB: 4615588

## <a name="symptoms"></a>Sintomi

In alcuni scenari, potresti ricevere il seguente messaggio quando apri la pagina **Copertura dell'articolo** dopo aver importato gli elementi tramite l'entità *Copertura articolo V2*:

> Salvare le modifiche apportate prima di chiudere?

Riceverai questo messaggio anche se non hai apportato modifiche.

## <a name="resolution"></a>Risoluzione

La pagina **Copertura dell'articolo** include una logica di default complessa che potrebbe causare la visualizzazione del messaggio dopo che sono state apportate di recente modifiche dirette al database, ad esempio tramite l'importazione di entità. Ad esempio, il campo entità `AREGENERALSETTINGSOVERRIDDEN` è impostato su *No*, ma importi un file che fornisce valori nuovi o modificati per campi come `PRODUCTCOVERAGEGROUPID` e/o `VENDORACCOUNTNUMBER`. In questo caso, poiché il campo `AREGENERALSETTINGSOVERRIDDEN` è impostato su *No*, i valori vengono automaticamente cancellati dai campi quando si apre la pagina **Copertura dell'articolo** per la prima volta dopo l'importazione. Se si salvano le modifiche come richiesto dalla finestra di messaggio, vengono archiviate nel database. In caso contrario, riceverai lo stesso messaggio la prossima volta che aprirai la pagina.

Per evitare questo comportamento, ma includere anche valori per campi come `PRODUCTCOVERAGEGROUPID` tramite l'importazione di entità, imposta `AREGENERALSETTINGSOVERRIDDEN` su *Sì* quando importi.
