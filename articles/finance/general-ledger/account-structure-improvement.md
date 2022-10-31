---
title: Miglioramento delle prestazioni di attivazione della struttura dei conti
description: Questo articolo illustra il nuovo miglioramento delle prestazioni per il processo di attivazione della struttura dei conti.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2022
ms.locfileid: "9714001"
---
# <a name="account-structure-activation-performance-enhancement"></a>Miglioramento delle prestazioni di attivazione della struttura dei conti

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Questo miglioramento delle prestazioni consente di attivare le strutture dei conti più rapidamente eseguendo più aggiornamenti delle transazioni contemporaneamente. Inoltre, la struttura stessa viene contrassegnata come attiva dopo la convalida e l'elaborazione della transazione può continuare mentre le transazioni non registrate esistenti vengono aggiornate alla nuova struttura. Poiché gli aggiornamenti delle transazioni potrebbero richiedere del tempo, è possibile tener traccia dello stato dell'attivazione selezionando **Visualizza stato di attivazione** sopra la griglia nella pagina **Strutture dei conti**. È possibile inoltre visualizzare lo stato di attivazione selezionando **Visualizza** nel riquadro azioni e quindi selezionando **Stato di attivazione** nel menu a discesa.

[![Pagine delle strutture dei conti.](./media/AccountStructure1.png)](./media/AccountStructure1.png)

Dopo aver selezionato **Visualizza stato di attivazione**, viene visualizzata una finestra di dialogo che mostra le singole attività in esecuzione come parte del processo di attivazione. Per ogni attività è possibile visualizzare lo stato e, al termine dell'attività, la data e l'ora di completamento.

[![Cronologia di attivazione della struttura dei conti.](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>Suggerimenti sull'attivazione della struttura dei conti

La finestra di dialogo di attivazione della struttura dei conti visualizzata quando si seleziona **Attiva** per una struttura di conti provvisoria ha una sezione scheda denominata **Aggiorna transazioni non registrate**. Questa sezione include un'opzione denominata **Forza aggiornamento**. È possibile selezionare questa opzione per aggiornare tutte le transazioni non registrate alla struttura corrente. Tuttavia, è consigliabile utilizzare questa opzione solo quando si è verificato un errore o il supporto tecnico ne ha consigliato l'utilizzo.

Di seguito sono riportati alcuni dei fattori che possono influenzare le prestazioni del processo di attivazione:

- Un gran numero di record del giornale di registrazione non registrati
- Un gran numero di record di documenti open source come fatture a testo libero, fatture fornitore e documenti correlati che utilizzano il framework del documento di origine e hanno distribuzioni contabili aperte
- La quantità di dati in TaxUncommitted
- Importo di dati di budget aperti
- Importazione dei dati del giornale di registrazione mentre le attività di attivazione sono ancora in esecuzione

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
