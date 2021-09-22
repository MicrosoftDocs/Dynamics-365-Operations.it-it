---
title: Le condizioni del flusso di lavoro del giornale di registrazione dell'inventario si applicano a livello di giornale di registrazione, non a livello di riga
description: Le condizioni del flusso di lavoro del giornale di registrazione dell'inventario si applicano solo a livello di giornale di registrazione, non a livello di riga.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 46bdde7f09c639fbefd46162431762b056d521ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476767"
---
# <a name="inventory-journal-workflow-conditions-apply-at-the-journal-level-not-line-level"></a>Le condizioni del flusso di lavoro del giornale di registrazione dell'inventario si applicano a livello di giornale di registrazione, non a livello di riga

## <a name="symptoms"></a>Sintomi

È possibile che si verifichi questo problema se, ad esempio, si tenta di configurare una condizione del flusso di lavoro del giornale di registrazione magazzini sull'importo del costo. Si configura la condizione in modo che il passaggio 1 venga eseguito solo quando l'importo del costo è inferiore a 100. Quindi si configura un'altra condizione in modo che il passaggio 2 venga eseguito solo quando l'importo del costo è maggiore o uguale a 100. Quindi, quando viene eseguito il flusso di lavoro, la cronologia del flusso di lavoro mostra solo una riga e la prima condizione viene sempre valutata come *vero*, indipendentemente dal valore inviato.

## <a name="workaround"></a>Soluzione alternativa

Nella versione attuale, le condizioni del flusso di lavoro del giornale di registrazione magazzino si applicano solo a livello di giornale di registrazione, non a livello di riga. Questo comportamento è predefinito. È consigliabile impostare i criteri della condizione solo sugli attributi a livello di giornale di registrazione.
