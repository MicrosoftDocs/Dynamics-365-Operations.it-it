---
title: Il sistema non riesce a trovare un ordine pianificato durante le operazioni su più ordini
description: L'errore "Ordine pianificato non esiste" si verifica quando si eseguono operazioni su più ordini pianificati e almeno due ordini appartengono allo stesso ID articolo.
author: t-benebo
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo_ReqTransPoMarkChangeType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ece4a331b63b86e896c5b337a58185ed3ea1049
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920805"
---
# <a name="the-system-cant-find-a-planned-order-during-operations-on-multiple-orders"></a>Il sistema non riesce a trovare un ordine pianificato durante le operazioni su più ordini

Codice errore: SYS24774

## <a name="symptoms"></a>Sintomi

Viene visualizzato il seguente messaggio di errore quando si tenta di eseguire un'operazione su più ordini pianificati contemporaneamente e almeno due degli ordini appartengono allo stesso ID articolo. Ad esempio, l'errore potrebbe verificarsi quando gli ordini vengono stabilizzati o il tipo di ordine viene modificato.

> L'ordine pianificato %1 non esiste.

## <a name="cause"></a>Causa

Quando il sistema stabilizza o modifica il tipo di un ordine, deve riconsiderare gli ordini pianificati esistenti per l'articolo, per assicurarsi che la fornitura pianificata corrisponda alla domanda e alla fornitura esistenti. Come parte di questo processo, il sistema ricrea gli ordini pianificati per l'articolo. Pertanto, il secondo ordine pianificato che il sistema prevede di elaborare non esiste più.

## <a name="workaround"></a>Soluzione alternativa

Approva gli ordini prima di elaborarli. In questo modo, gli ordini non verranno eliminati quando il sistema elabora il primo ordine per l'articolo.
