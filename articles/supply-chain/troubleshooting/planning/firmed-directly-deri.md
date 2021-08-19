---
title: Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro in revisione
description: Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro il cui stato è In revisione.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d20f1c1d6e8fc83dd996b04bf0321a41f7b39290f306d1ac9f4fcd17514832e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721177"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro in revisione

Numero KB: 4612450

## <a name="symptoms"></a>Sintomi

Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro il cui stato è *In revisione*.

## <a name="resolution"></a>Risoluzione

Quando il rilevamento delle modifiche è attivato, lo stato *In revisione* viene assegnato agli ordini stabilizzati derivati (ordini fornitore in conto lavoro). Pertanto, se un ordine fornitore viene derivato (un ordine fornitore in conto lavoro), viene inviato solo a un flusso di lavoro. Se un ordine fornitore è un ordine fornitore pianificato stabilizzato, viene automaticamente approvato per garantire che il motore di pianificazione non crei nuovi ordini pianificati mentre lo stato dell'ordine fornitore è ancora *Bozza*.
