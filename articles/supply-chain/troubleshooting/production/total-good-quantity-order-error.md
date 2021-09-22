---
title: Errore quantità idonea totale quando si tenta di terminare un ordine
description: Quando si tenta di terminare un ordine di produzione e di dichiararlo finito, è possibile che venga visualizzato un errore di quantità idonea totale. Questa pagina spiega perché e come risolvere il problema.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5f0c2c2ca64ada9d72c0ebd04e7de561aaa52039
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476758"
---
# <a name="total-good-quantity-error-when-trying-to-end-a-production-order"></a>Errore quantità idonea totale quando si tenta di terminare un ordine di produzione

## <a name="symptoms"></a>Sintomi

Quando si tenta di registrare un report come giornale di registrazione finito in un ordine di produzione, viene visualizzato il seguente messaggio di errore:

> La quantità idonea totale dichiarata finita per la produzione sarà pari a %1. Il riscontro complessivo per l'ultima operazione è pari a 0,00.

## <a name="cause"></a>Causa

Questo problema si verifica se le quantità registrate nelle ultime operazioni non erano corrette. Ad esempio, se la produzione viene avviata, ma la quantità che deve essere avviata non viene allocata, il giornale di registrazione scheda ciclo di lavorazione verrà registrato senza righe. Per confermare la situazione, aprire l'ordine di produzione, quindi, nel riquadro Azioni, nella scheda **Visualizza** selezionare **Scheda ciclo di lavorazione**.

## <a name="resolution"></a>Risoluzione

È possibile risolvere questo problema registrando giornali aggiuntivi per le operazioni per le quali i giornali non sono stati registrati correttamente. Riavviare l'ordine di produzione e selezionare per registrare i giornali di registrazione aggiuntivi. Questa azione non avvierà l'ordine di produzione, ma registrerà i giornali. La scheda ciclo mostra quindi le quantità che sono state registrate ed è possibile terminare correttamente gli ordini di produzione.
