---
title: Programmazione dei processi kanban per lean manufacturing
description: "Questo articolo fornisce informazioni su controllo visivo sulla programmazione dei processi kanban e le modalità varie per la programmazione dei processi kanban."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 27db57170ccc23c2ea18a49c1a3e5950c870fa13
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017

---

# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Programmazione dei processi kanban per lean manufacturing

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni su controllo visivo sulla programmazione dei processi kanban e le modalità varie per la programmazione dei processi kanban.  

La pagina **Programmazione processi kanban** fornisce il controllo visivo sulle programmazioni di celle di lavoro lean manufacturing. Fornisce una panoramica di tutti i processi kanban e fornisce molteplici funzionalità di filtro. Da questa pagina è possibile spostare tutte le altre pagine che sono correlate alla configurazione e all'esecuzione kanban.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Programmazione automatica dei processi kanban
La programmazione può essere attivata automaticamente se si imposta il parametro **Quantità di pianificazione automatica** sulla regola kanban. Se si imposta **Quantità di pianificazione automatica** su **1**, ogni processo kanban è pianificato immediatamente quando viene creato. Il risultato è una serie di operazioni "first pull, first serve". Se si imposta **Quantità di pianificazione automatica** su un valore superiore a 1, i processi kanban vengono raggruppati prima di essere pianificati. 

Questo concetto consente di ridurre le dimensioni kanban sotto le dimensioni batch economiche effettive. Ad esempio, la dimensione batch economica per un articolo specifico (o famiglia di articoli) è 30. Anziché creare kanban che utilizzano la quantità di prodotto, 30, è possibile configurare la regola kanban in modo che abbia una quantità di prodotto pari a 10 e un valore di **Quantità di pianificazione automatica** di **3**. Sebbene la pianificazione automatica consenta di programmare i processi kanban per la cella di lavoro solo in presenza di tre processi non pianificati, è chiarissimo a chi pianifica e al supervisore dello shop floor che vi sono due processi non pianificati in attesa di esecuzione. I responsabili della pianificazione e dello shop floor possono integrare i due processi nella produzione pianificandoli manualmente o creando kanban aggiuntivi.

## <a name="manual-scheduling"></a>Programmazione manuale
Per la programmazione manuale in Microsoft Dynamics AX 2012 è stata introdotta la bacheca di programmazione kanban. La programmazione manuale può essere combinata con la programmazione automatica. La bacheca di programmazione kanban consente di pianificare i processi, e di annullarne la pianificazione, di spostarli in sequenza o da un periodo all'altro. I processi che sono basati su una regola kanban in cui il valore di **Pianificazione automatica** è superiore a **0** possono essere eliminati dalla pianificazione manualmente. Tuttavia, questi processi saranno ripianificati quando si verifica il successivo evento di pianificazione automatica, vale a dire quando viene creato un nuovo kanban). Sono disponibili le seguenti opzioni per la programmazione manuale:

-   **Programma**: programma i processi selezionati in base alla data di scadenza. Questa opzione è simile alla pianificazione automatica.
-   **Programma in avanti a partire dalla data specifica**: tenta di programmare i processi selezionati in base alla data di scadenza ma limita il risultato utilizzando la data meno recente specificata.
-   **Indietro**: sposta i processi programmati selezionati indietro nella sequenza all'interno del periodo.
-   **Avanti**: sposta i processi programmati selezionati avanti nella sequenza all'interno del periodo.
-   **Periodo precedente**: sposta i processi programmati selezionati all'inizio o alla fine del periodo precedente.
-   **Periodo successivo**: sposta i processi programmati selezionati all'inizio o alla fine del periodo successivo.
-   **Pianifica** &gt; **Ripristina stato del processo** consente di eliminare dalla programmazione un processo programmato.

## <a name="lean-scheduling-groups"></a>Gruppi di programmazione snella
Ogni colore per un gruppo di programmazione snella. I gruppi di programmazione snella possono essere liberamente definiti come gruppi generici o come gruppi che appartengono a una singola cella di lavoro. Gli articoli e le dimensioni possono essere liberamente assegnati ai gruppi di programmazione. Ad esempio, in una cella Verniciatura, un gruppo di programmazione può rappresentare il colore del prodotto. Nel lavoro che è determinato dai requisiti specifici di lavorazione con utensili, gli articoli possono essere raggruppati in base ai requisiti degli utensili e una cella di lavoro di imballaggio può raggruppare gli articoli in base al modello di imballaggio. L'utilizzo di colori per i gruppi di programmazione snella è facoltativo ma consigliato. Migliora la visibilità dello stato del piano. Ad esempio, è molto semplice vedere quali colori vengono prodotti in quale giorno ed è possibile capire immediatamente in che modo sia possibile ottimizzare il lavoro.

## <a name="work-cell-capacity-and-period-capacity"></a>Capacità della cella di lavoro e capacità di periodo
La capacità di una cella di lavoro snella è sempre capacità simultanea. In altre parole, più processi possono essere attivi in una cella di lavoro contemporaneamente. La capacità può essere monitorata in due modi: per produttività e per ore.

### <a name="throughput"></a>Produttività

La capacità di una cella di lavoro è definita dalla quantità di produttività media del periodo di riferimento (giorno lavorativo, settimana o mese standard). La capacità effettiva al giorno o alla settima viene quindi calcolata in base alle ore di lavoro del calendario che è assegnato alla cella di lavoro. La capacità che viene caricata dal processo è la quantità del processo, rettificata dal rapporto di produttività dell'articolo nella cella di lavoro.

### <a name="hours"></a>Ore

La capacità disponibile al giorno o alla settimana è definita dal calendario assegnato alla cella di lavoro. La capacità che viene caricata dal processo è la durata ciclo dell'attività, rettificata dalla quantità (quantità attività predefinita contro quantità processo effettiva) e dal rapporto di produttività dell'articolo nella cella di lavoro.

#### <a name="period-capacity-factbox"></a>Dettaglio informazioni Capacità periodo

Nella pagina elenco **Programmazione processo kanban** è incluso un riquadro Dettagli informazioni che mostra la capacità di periodo disponibile e prenotata per la cella di lavoro selezionata. A seconda dei periodi di programmazione selezionati nel modello di flusso di produzione, i periodi mostrano i giorni o le settimane.

<a name="see-also"></a>Vedere anche
--------




