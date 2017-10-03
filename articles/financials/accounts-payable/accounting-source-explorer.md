---
title: "Esplora origine contabilità"
description: "Questo articolo fornisce informazioni su Esplora origine contabilità, che è possibile utilizzare per analisi dettagliate delle informazioni di origine relative alle voci della contabilità generale."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: df97cad657164866b83fa0ca8f10091317f92a88
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="accounting-source-explorer"></a>Esplora origine contabilità

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni su Esplora origine contabilità, che è possibile utilizzare per analisi dettagliate delle informazioni di origine relative alle voci della contabilità generale.

Esplora origine contabilità è una nuova pagina contenente le informazioni relative all'origine. È possibile utilizzare Esplora origine contabilità come strumento autonomo oppure per analizzare i dettagli relativi alle voci contabili di contabilità generale. Ad esempio, è possibile eseguire Esplora  origine contabilità per ottenere informazioni più dettagliate sull'origine per un saldo in Bilancio di verifica o per una transazione giustificativo. È quindi possibile utilizzare la funzionalità Esporta in MS Excel per visualizzare le informazioni in modo ancora più dettagliato in Microsoft Excel (ad esempio, in una tabella Pivot o in un report di tabella pivot).

Esplora origine contabilità mostra sempre lo stesso importo totale per conto CoGe in base a quanto indicato in Contabilità generale (ad esempio, in Bilancio di verifica). Come in Bilancio di verifica, è possibile visualizzare segmenti in colonne separate. È sufficiente selezionare il set di dimensioni finanziarie appropriato. 

È possibile utilizzare i parametri per definire un intervallo di date per l'analisi. Anche questa funzionalità è simile a quella presente in Bilancio di verifica.

Per tutti i documenti che utilizzano il framework documento di origine, Esplora origine contabilità mostra informazioni aggiuntive, in base alle distribuzioni contabili e, se applicabile, alle distribuzioni contabili di progetto. Queste informazioni includono tipo di importo monetario, progetto, attività, categoria e proprietà riga. Di seguito sono riportati alcuni esempi dell'analisi che è possibile effettuare:

-   Scostamenti tra ordini di acquisto e fatture fornitore, poiché ogni scostamento viene rappresentato da un tipo di importo monetario, ad esempio lo scostamento addebiti
-   Ore e spese fatturabili rispetto a quelle non fatturabili per progetto, Business Unit e conto principale

Per i documenti di origine che utilizzano il concetto di identità di riferimento del documento di origine, Esplora origine contabilità mostra un numero maggiore di dettagli, ad esempio il cliente, il fornitore, il lavoratore, il prodotto, la quantità, il testo unità e le descrizioni. Di seguito sono riportati alcuni esempi dell'analisi che è possibile effettuare:

-   Spese di albergo per Business Unit e catena alberghiera per un periodo fiscale, in base alle note spese
-   Sconti per fornitore, prodotto, reparto

Per questi documenti, è possibile inoltre passare al documento di origine effettivo da Esplora origine contabilità.



