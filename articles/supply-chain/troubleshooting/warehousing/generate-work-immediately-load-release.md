---
title: Generare un lavoro di prelievo immediatamente quando il carico viene rilasciato
description: Se il lavoro deve essere generato immediatamente quando il carico viene rilasciato, è necessario configurare il modello di ciclo di conseguenza. Questa pagina illustra i passaggi della procedura.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fdeb0b27f4d2c1a2cc9f8e0c4ba537cdce604bd2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476786"
---
# <a name="picking-work-isnt-generated-immediately-when-outbound-load-is-released"></a>Un lavoro di prelievo non viene generato immediatamente quando il carico in uscita viene rilasciato

## <a name="symptoms"></a>Sintomi

È possibile creare un carico in uscita utilizzando un ordine di vendita o di trasferimento e rilasciare il carico al magazzino. Tuttavia, notare che è necessario ancora generare un lavoro di prelievo.

## <a name="resolution"></a>Risoluzione

Se il lavoro deve essere generato immediatamente quando il carico viene rilasciato, è necessario configurare il modello di ciclo di conseguenza. Sul modello di ciclo, impostare le seguenti opzioni su *Sì*:

- Automatizza creazione ondata
- Elabora ondata al rilascio in magazzino
- Automatizza rilascio ondata
