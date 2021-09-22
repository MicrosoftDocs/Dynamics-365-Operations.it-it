---
title: Gli ordini pianificati richiedono molto tempo per l'aggiornamento
description: Quando si aggiorna la quantità richiesta e/o la data di consegna di un ordine pianificato, in genere sono necessari almeno 30 secondi per ordine per salvare l'aggiornamento.
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ccf3305cc18ea0ccf2ac3e9ca0dd507fd12a9da7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476781"
---
# <a name="planned-orders-take-a-long-time-to-update"></a>Gli ordini pianificati richiedono molto tempo per l'aggiornamento

## <a name="symptoms"></a>Sintomi

Quando si aggiorna la quantità richiesta e/o la data di consegna di un ordine pianificato, in genere sono necessari almeno 30 secondi per ordine per salvare l'aggiornamento.

## <a name="resolution"></a>Risoluzione

Si tratta di un problema noto con il motore di pianificazione generale integrato. È causato dall'auto esplosione sottostante attraverso la struttura della distinta base durante le modifiche. Questo problema viene risolto in Ottimizzazione pianificazione, in cui un pianificatore può aggiornare e approvare gli ordini pertinenti e, se desiderato, attivare un'esecuzione della pianificazione per aggiornare gli ordini pianificati per la struttura della distinta base sottostante.

Un modo per migliorare le prestazioni con il motore di pianificazione generale integrato consiste nell'effettuare le operazioni seguenti:

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare un piano.
1. Espandere la scheda dettaglio **Intervalli temporali in giorni**.
1. Impostare **Esplosione** su *Sì* e impostare il campo sotto questa impostazione su 0 (zero).

> [!NOTE]
> Ciò limiterà il periodo per le esplosioni eseguite per questo piano generale a un solo giorno.
