---
title: Impossibile trovare il profilo del cluster
description: Quando si utilizzano operazioni di magazzino in entrata, è possibile che venga visualizzato un errore che indica che non è possibile trovare il profilo del cluster. Assicurarsi che i profili del cluster siano impostati correttamente.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bbf9c5bc70c8f3ba1fa26db425249e65e82c0518
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476812"
---
# <a name="cluster-profile-cant-be-found"></a>Impossibile trovare il profilo del cluster

## <a name="symptoms"></a>Sintomi

Quando si utilizzano operazioni di magazzino in entrata, è possibile che venga visualizzato il seguente messaggio di errore:

> "L'ordine di controllo qualità %1 è stato generato. Impossibile trovare il profilo del cluster. Controllare la configurazione."

Questo messaggio di errore è correlato a un processo di ricezione in cui è attivata la gestione della qualità (QMS). A seconda delle configurazioni nel proprio ambiente, ulteriori dettagli sulla transazione che sta generando il messaggio di errore potrebbero aiutare a risolvere il problema.

## <a name="resolution"></a>Risoluzione

Innanzitutto, esaminare l'impostazione di prelievo cluster e assicurarsi che i profili del cluster siano impostati correttamente. Non è possibile utilizzare una voce di menu del dispositivo mobile per la selezione del cluster a meno che non siano stati configurati i profili del cluster. A seconda del proprio ambiente, potrebbe essere necessario rivedere anche altre configurazioni correlate.
