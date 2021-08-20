---
title: Monitorare un'esecuzione di pianificazione generale
description: Questo argomento spiega come il responsabile di pianificazione della produzione può vedere se è in corso un'esecuzione di pianificazione generale.
author: josaw1
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b59e8590bf700b77a5e8021f9518f6d0cc6929acc0d9ea2723cef8b7a1971fd4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757736"
---
# <a name="monitor-a-master-planning-run"></a>Monitorare un'esecuzione di pianificazione generale

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Utilizzare un diagramma di Gantt per visualizzare l'avanzamento della pianificazione generale

Nella pagina **Visualizza stato pianificazione generale**, è possibile visualizzare i dettagli delle esecuzioni storiche di pianificazione generale come diagramma di Gantt. Questa funzionalità può aiutare a comprendere il tempo impiegato nelle varie fasi della pianificazione generale. Per un lavoro di pianificazione attivo corrente, è possibile utilizzare la pagina **Visualizza stato pianificazione principale** per tenere traccia dell'avanzamento e visualizzare il tempo rimanente stimato.

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a>Attivare e utilizzare la funzione di visualizzazione dell'avanzamento del piano principale

Per utilizzare questa funzionalità, attenersi alla seguente procedura.

1. Nell'area di lavoro **Gestione funzionalità**, scheda **Nuovo**, selezionare **Visualizzazione stato pianificazione generale** nell'elenco. Se la funzionalità non è presente nella scheda **Nuovo**, considerare le schede **Tutto** e **Non abilitato**.
1. Selezionare **Abilita ora**. In alternativa, selezionare **Programmazione** e quindi selezionare l'ora in cui si desidera che la funzionalità sia abilitata.

Nella pagina **Visualizza stato pianificazione generale** possono essere visualizzati entrambi i processi della pianificazione storica e i processi di pianificazione attivi. 

Per visualizzare i processi della pianificazione storica, sono disponibili due opzioni. 

1. Andare a **Pianificazione generale \> Impostazione \> Piani \> Piani generali**, quindi nel riquadro azioni selezionare **Storico**. Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**
1. Passare a **Pianificazione generale \> Aree di lavoro \> Pianificazione generale** e nel riquadro della pianificazione generale selezionare **Storico**. Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**

Per visualizzare i processi della pianificazione attiva, sono disponibili due opzioni. 
1. Andare a **Pianificazione generale \> Aree di lavoro \> Pianificazione generale** e nel riquadro azioni selezionare **Processi di pianificazione non completati**. Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**.
1. Passare a **Pianificazione generale \> Aree di lavoro \> Pianificazione generale** e nel riquadro della pianificazione generale selezionare **Visualizza avanzamento**. Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**

Notare che è possibile visualizzare i processi attivi solo quando un processo di pianificazione è in elaborazione.

### <a name="analyze-a-master-planning-job"></a>Analizzare un processo di pianificazione generale

Nel diagramma di Gantt, è possibile espandere i seguenti processi di pianificazione per visualizzare ulteriori dettagli relativi al tempo impiegato:

- Inizializzazione
- Eliminazione e inserimento dati
- Pianificazione copertura
- Ritardi
- Messaggi d'azione
- Finalizzazione
- Stabilizzazione automatica

Il diagramma di Gantt è uno strumento utile se si desidera visualizzare l'impatto dei messaggi di azione.

#### <a name="navigation-in-the-gantt-chart"></a>Navigazione nel diagramma di Gantt

- Per espandere il gruppo selezionato e visualizzare i dettagli, selezionare il segno più (**+**) nella visualizzazione ad albero.
- Per comprimere il gruppo selezionato, selezionare il segno meno (**–**) nella visualizzazione ad albero.
- È possibile utilizzare la tastiera per la navigazione. Utilizzare i tasti **freccia su** e **freccia giù** per spostare tra le righe. Utilizzare i tasti **freccia a sinistra** e **freccia a destra** per espandere e comprimere gruppi.
- Per aprire o chiudere tutti i livelli nel diagramma di Gantt, selezionare **Espandi tutto** o **Comprimi tutto**.
- Per visualizzare il tempo di esecuzione correlato, passare il mouse su un'attività. Le attività sono il livello più basso nel diagramma di Gantt.

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>Visualizzare un'altra esecuzione della pianificazione generale per confrontare i processi

Se si seleziona il processo di pianificazione generale nel campo **Mostra esecuzione della pianificazione generale aggiuntiva**, è possibile visualizzare l'esecuzione di una pianificazione generale aggiuntiva nel diagramma di Gantt e confrontare i due processi.

#### <a name="bom-level-display"></a>Visualizzazione dei livelli DBA

I livelli della distinta base (DBA) vengono visualizzati in modo diverso per pianificazione di copertura, ritardi, azioni e stabilizzazione.

- **Pianificazione copertura** - I livelli DBA vengono visualizzati come previsto. Vengono calcolati dall'alto verso il basso.

    **Esempio:** livello DBA 0, 1, 2

- **Ritardi** - I livelli DBA vengono visualizzati come i livelli DBA della pianificazione copertura moltiplicati per -1. In altre parole con segno negativo.

    **Esempio:** livello DBA -2, -1, 0

- **Messaggio d'azione** - I livelli DBA vengono visualizzati come previsto. Vengono calcolati dall'alto verso il basso.

    **Esempio:** livello DBA 0, 1, 2

- **Stabilizzazione automatica** - I livelli DBA vengono visualizzati come 999 meno il livello DBA della pianificazione di copertura.

    **Esempio:** livello DBA 999, 998, 997

Nella seguente tabella viene illustrato il comportamento.

| Livello DBA mostrato | Prodotto finito | Sottocomponente | Materie prime |
|---|---|---|---|
| Pianificazione copertura | 0 | 1 | 2 |
| Ritardi | 0 | –1 | –2 |
| Messaggio d'azione | 0 | 1 | 2 |
| Stabilizzazione automatica | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>Visualizzare l'avanzamento

Se si visualizza un processo di pianificazione generale attualmente in esecuzione, l'avanzamento è indicato tramite i colori nel diagramma di Gantt. I seguenti colori si applicano al tema blu. Per altri temi i colori sono diversi.

- **Blu scuro** - Attività di pianificazione completate.
- **Arancione** L'attività che è attualmente in corso.
- **Blu chiaro** - La stima delle attività rimanenti.

Il colore viene visualizzato solo sul livello più basso nel diagramma di Gantt. Selezionare **Espandi tutto** per visualizzare tutte le attività nel processo di pianificazione generale. La stima delle attività rimanenti si basa sui processi storici della pianificazione generale.

## <a name="run-master-planning-and-track-processing-time"></a>Eseguire la pianificazione generale e tracciare il tempo di elaborazione

1. Nel dashboard predefinito, selezionare **Pianificazione generale**.
1. Nel campo **Piano** immettere o selezionare un valore.
1. Selezionare **Esegui**.
1. Impostare l'opzione **Traccia ora di elaborazione** su **Sì**.
1. Nel campo **Numero di thread** immettere un numero.
1. Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.
1. Nella griglia, selezionare la riga in cui il campo **Campo** è impostato su **Numero articolo**.
1. Nel campo **Criteri** immettere un valore.
1. Selezionare **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]