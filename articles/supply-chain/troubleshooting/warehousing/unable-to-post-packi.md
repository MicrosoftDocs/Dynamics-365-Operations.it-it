---
title: Impossibile inviare il documento di trasporto per una riga dell'ordine cliente interrotta
description: Non è possibile inviare il documento di trasporto per una riga dell'ordine cliente interrotta
author: smithanataraj
ms.date: 03/07/2022
ms.topic: article
ms.search.form: WHSLoadTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2022-03-07
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 115cfe79e075eb36f73203818acdbb5e31fc0bad
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462852"
---
# <a name="cant-post-packing-slip-for-a-stopped-a-sales-order-line"></a>Impossibile inviare il documento di trasporto per una riga dell'ordine cliente interrotta

Codice errore: SYS13203

## <a name="symptoms"></a>Sintomi

Quando si tenta di registrare un documento di trasporto per un carico, il sistema visualizza il seguente messaggio di errore:

> Impossibile registrare il documento di trasporto quando si interrompe una riga dell'ordine cliente dopo aver confermato la spedizione in uscita. Impossibile prelevare una quantità.

## <a name="cause"></a>Causa

Una o più delle righe dell'ordine cliente correlate potrebbero essere interrotte, il che significa che il sistema impedisce l'ulteriore elaborazione di tale ordine cliente. Tra le altre cose, ciò significa che il sistema non invierà un documento di trasporto per l'ordine.

Ad esempio, un utente potrebbe aver deciso di interrompere una o più righe d'ordine perché il cliente ha richiamato e annullato l'ordine. Tuttavia, se la spedizione in uscita era già stata confermata, la spedizione contenente l'ordine cliente avrebbe già lasciato fisicamente il magazzino, il che significa che l'interruzione delle righe dell'ordine cliente non avrà alcun effetto. Poiché non è più possibile interrompere fisicamente la spedizione, puoi anche interrompere le righe in modo da poter registrare il documento di trasporto. Dovrai quindi gestire l'ordine annullato come reso.

## <a name="resolution"></a>Risoluzione

Per poter registrare il documento di trasporto, accertati che nessuna delle righe dell'ordine cliente pertinenti venga interrotta eseguendo i passaggi seguenti.

1. Vai a **Tutti gli ordini cliente \> Vendite e marketing \> Tutti gli ordini cliente**.
1. Trova e apri l'ordine cliente con cui hai problemi.
1. Nella scheda dettaglio **Righe ordine cliente**, seleziona una riga dell'ordine cliente.
1. Nella scheda dettaglio **Dettagli riga** apri la scheda **Generale** e assicurati che il campo **Arrestato** sia impostato su *No*.
1. Continua a lavorare fino a quando tutte le righe di vendita pertinenti non sono più interrotte.
1. Riprova a registrare il documento di trasporto per il carico o l'ordine cliente.
