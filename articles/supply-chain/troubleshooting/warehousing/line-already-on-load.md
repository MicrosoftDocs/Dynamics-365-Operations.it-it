---
title: Una delle righe è già presente su un carico
description: Questa pagina spiega perché potrebbe venire visualizzato l'errore "Una delle righe è già presente su un carico. Impossibile rilasciare al magazzino" e come risolvere il problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0bdfaed005b9c58f7bd5f87dd6dffe648de47261
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476818"
---
# <a name="one-of-the-lines-is-already-on-a-load"></a>Una delle righe è già presente su un carico

## <a name="symptoms"></a>Sintomi

Quando si eseguono operazioni di allestimento del carico e spedizioni, è possibile che venga visualizzato il seguente messaggio di errore:

> Una delle righe è già presente su un carico. Impossibile rilasciare al magazzino.

Se si creano manualmente i carichi o se si imposta il processo in modo che i carichi siano già creati prima che avvenga l'immissione della riga dell'ordine cliente, si presume che il rilascio successivo verrà eseguito manualmente e che verranno utilizzati il percorso e la classificazione dal carico.

In un altro possibile scenario, si tenta di eseguire un rilascio automatico al magazzino, ma il processo del ciclo non è riuscito a creare lavoro. Pertanto, viene comunque creata una spedizione o un carico aperto. Questa spedizione o carico aperto blocca quindi i tentativi successivi di rilasciare automaticamente l'ordine fino a quando non si elimina la spedizione o il carico aperto oppure si rielabora manualmente il ciclo.

## <a name="resolution"></a>Risoluzione

È possibile rilasciare dalla pagina dell'ordine cliente oppure è possibile eseguire un rilascio automatico dalla pagina di rilascio dell'ordine cliente, solo se non esiste alcun carico prima del rilascio al magazzino. Il carico verrà creato automaticamente dopo l'elaborazione del ciclo.
