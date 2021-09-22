---
title: L'annullamento di una rimanenza di consegna modifica lo stato dell'ordine fornitore in Confermato
description: Se una rimanenza di consegna viene annullata su un ordine fornitore in cui è attivata la gestione delle modifiche, l'ordine fornitore passa allo stato Confermato
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1d8b331bc5699487dff3491d65daa36293f3212f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476780"
---
# <a name="cancelling-delivery-remainder-moves-purchase-order-to-a-confirmed-state"></a>L'annullamento di una rimanenza di consegna modifica lo stato dell'ordine fornitore in Confermato

## <a name="symptoms"></a>Sintomi

Per un ordine fornitore soggetto a gestione delle modifiche, se l'unica modifica richiesta è l'annullamento di una rimanenza di consegna su una o più righe, l'ordine fornitore passerà direttamente sullo stato *Confermato* quando è approvato e non verrà creato alcun giornale di registrazione.

## <a name="resolution"></a>Risoluzione

L'annullamento di una rimanenza di consegna non influisce sul contenuto del giornale di registrazione delle conferme. Questa funzionalità deve essere utilizzata quando la riga è stata ricevuta parzialmente e la qualità rimanente deve essere annullata nel passaggio di processo dopo che l'ordine fornitore è stato confermato con il fornitore.

Se ciò si riflette sulla conferma dell'ordine fornitore, la quantità deve essere rettificata nella riga dell'ordine fornitore in modo che venga richiesta la conferma. In alternativa, se non è stato ricevuto nulla sulla riga, la quantità può essere rimossa. In questo caso, sarà richiesta la riconferma.
