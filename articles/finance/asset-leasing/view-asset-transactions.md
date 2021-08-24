---
title: Visualizzare le transazioni relative a passività, attività e spese
description: Questo argomento spiega come visualizzare le transazioni per un asset in leasing. Queste transazioni includono transazioni di obbligazione sul leasing e transazioni di spese di esecuzione che sono state registrate.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 58a57b2a1237b41c99e44cf40c57d80257fc9b5b77188586aab6735a8a3f4984
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765742"
---
# <a name="view-liability-asset-and-expense-transactions"></a>Visualizzare le transazioni relative a passività, attività e spese

[!include [banner](../includes/banner.md)]

Questo argomento spiega come visualizzare le transazioni per un asset in leasing. Queste transazioni includono transazioni di obbligazione sul leasing e transazioni di spese di esecuzione che sono state registrate. I valori contabili dell'passività e dell'asset ROU sono utilizzati in diversi report. Sono anche utilizzati per calcolare i valori di rettifica.

## <a name="liability-transactions"></a>Transazioni di passività

Per visualizzare le transazioni di obbligazione sul leasing, seleziona un leasing nella pagina **Riepilogo leasing**, quindi seleziona **Libri** per aprire i libri allegati al record di leasing. Dopo aver registrato un riconoscimento iniziale, una fattura o un giornale di registrazione interessi, seleziona **Transazioni di passività**.

La pagina **Transazioni di passività** mostra le transazioni che aumentano o diminuiscono l'obbligazione sul leasing. Gli importi negativi in questa pagina rappresentano le transazioni di credito nell'applicazione standard. Eventuali ratei di interessi sono indicati come valori negativi e aumentano l'obbligazione sul leasing totale. Eventuali rettifiche di leasing sono indicate come valori positivi o negativi, a seconda della natura e dell'impatto del libro di leasing. L'attuale saldo netto totale dell'obbligazione sul leasing per il leasing selezionato è mostrato in basso a sinistra nella pagina.

## <a name="asset-transactions"></a>Transazioni di cespite

Per visualizzare le transazioni di cespite del leasing, seleziona un leasing nella pagina **Riepilogo leasing**, quindi seleziona **Libri** per aprire i libri cespite allegati al record di leasing. Seleziona quindi **Transazioni cespiti**.

La pagina **Transazione cespiti** mostra le transazioni che aumentano o diminuiscono il cespite del leasing e i conti di ammortamento accumulato. Gli addebiti vengono visualizzati come valori positivi e gli accrediti come valori negativi, come nella pagina **Transazioni di passività**. Il riconoscimento iniziale registrato e il successivo ammortamento accumulato vengono visualizzati in basso a sinistra nella pagina come saldo del cespite. 

## <a name="expenses-transactions"></a>Transazioni di spesa

Per visualizzare le transazioni di spesa del leasing, seleziona un leasing nella pagina **Riepilogo leasing**, quindi seleziona **Libri** per aprire i libri cespite allegati al record di leasing. Quindi, seleziona **Transazioni di spesa**.

La pagina **Transazioni di spesa** mostra tutte le spese che sono state registrate a fronte del leasing, come gli interessi passivi, le spese di ammortamento e gli eventuali costi di esecuzione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
