---
title: Esplora origine contabilità
description: Questo articolo fornisce informazioni sulla pagina Esplora origine contabilità, che è possibile utilizzare per analisi dettagliate delle informazioni di origine relative alle voci della contabilità generale.
author: RyanCCarlson2
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: kfend
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd5580dc0be37ec89e6c7934b47c7d5593d8716
ms.sourcegitcommit: 5f8f042f3f7c3aee1a7303652ea66e40d34216e3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/29/2022
ms.locfileid: "9806435"
---
# <a name="accounting-source-explorer"></a>Esplora origine contabilità

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulla pagina **Esplora origine contabilità**, che è possibile utilizzare per analisi dettagliate delle informazioni di origine relative alle voci della contabilità generale.

La pagina **Esplora origine contabilità** visualizza le informazioni relative all'origine. È possibile utilizzarla come strumento autonomo oppure per analizzare i dettagli relativi alle voci contabili di contabilità generale. Ad esempio, è possibile utilizzare la pagina per ottenere informazioni più dettagliate sull'origine per un saldo di bilancio di verifica o per una transazione giustificativo. È quindi possibile utilizzare la funzionalità **Esporta in MS Excel** per visualizzare le informazioni in modo ancora più dettagliato in Microsoft Excel (ad esempio, in una tabella Pivot o in un report di tabella pivot).

La pagina **Esplora origine contabilità** mostra sempre lo stesso importo totale per conto CoGe in base a quanto indicato in Contabilità generale (ad esempio, in Bilancio di verifica). Come in Bilancio di verifica, è possibile visualizzare segmenti in colonne separate. È sufficiente selezionare il set di dimensioni finanziarie appropriato. 

È possibile utilizzare i parametri per definire un intervallo di date per l'analisi. Anche questa funzionalità è simile a quella presente in Bilancio di verifica.

Per tutti i documenti che utilizzano il framework documento di origine, la pagina **Esplora origine contabilità** mostra informazioni aggiuntive, in base alle distribuzioni contabili e, se applicabile, alle distribuzioni contabili di progetto. Queste informazioni includono i valori **Tipo di importo monetario**, **Progetto**, **Attività**, **Categoria** e **Proprietà riga**. Di seguito sono riportati alcuni esempi dell'analisi che è possibile effettuare:

- Scostamenti tra ordini di acquisto e fatture fornitore, poiché ogni scostamento viene rappresentato da un tipo di importo monetario, ad esempio lo scostamento addebiti
- Ore e spese fatturabili rispetto a quelle non fatturabili per progetto, Business Unit e conto principale

Per i documenti di origine che utilizzano il concetto di identità di riferimento del documento di origine, la pagina **Esplora origine contabilità** visualizza anche altri dettagli, ad esempio i valori **Cliente**, **Fornitore**, **Lavoratore**, **Prodotto**, **Quantità**, **Testo unità** e **Descrizione**. Di seguito sono riportati alcuni esempi dell'analisi che è possibile effettuare:

- Spese di albergo per Business Unit e catena alberghiera per un periodo fiscale, in base alle note spese
- Sconti per fornitore, prodotto, reparto

Per questi documenti, è possibile inoltre passare al documento di origine effettivo dalla pagina **Esplora origine contabilità**.

> [!NOTE]
> A partire dalla versione 10.0.31, una nuova funzione **Filtro avanzato di Esplora origine contabilità** è disponibile in Gestione funzioni. Questa funzione sostituisce il pulsante **Aggiorna** per fornire un'esperienza di query avanzata più solida che assomiglia a ciò che è disponibile nella pagina **Transazioni giustificativo**. Il filtro avanzato ti consentirà di filtrare in base a campi simili a quelli che trovi nella pagina **Query transazioni giustificativo**, ad esempio **Conto CoGe.**, **Business unit**, **Centro di costo** e **Reparto**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
