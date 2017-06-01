---
title: Panoramica sul lean manufacturing
description: "In questo articolo vengono fornite una panoramica e una descrizione delle funzionalità di lean manufacturing in Microsoft Dynamics AX."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19371
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: dd29e601cb78b6903e09e63182196427183f6dbe
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="lean-manufacturing-overview"></a>Panoramica sul lean manufacturing

[!include[banner](../includes/banner.md)]


In questo articolo vengono fornite una panoramica e una descrizione delle funzionalità di lean manufacturing in Microsoft Dynamics AX.

La funzionalità lean manufacturing mette a disposizione strumenti per la gestione di operazioni snelle. Questi strumenti supportano e promuovono i concetti e le attività commerciali seguenti:
-   Creare una base di lean manufacturing modellando i processi di logistica e di produzione come flussi di produzione.
-   Implementare un sistema pull snello utilizzando i kanban per segnalare i requisiti della domanda.
-   Monitorare e gestire i processi kanban.

L'architettura di lean manufacturing in Microsoft Dynamics AX 7 è costituita da flussi di produzione, attività e regole kanban. Queste strutture vengono interamente integrate con i processi di Microsoft Dynamics AX 7. La funzionalità lean manufacturing si adatta a un ambiente di produzione misto in cui si combinano varie strategie di fornitura, produzione e approvvigionamento. Queste strategie includono gli ordini di produzione, gli ordini batch per i settori della trasformazione, gli ordini fornitore e di trasferimento.
| **Importante**                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| È possibile utilizzare Microsoft Dynamics AX 7 per supportare l'implementazione di lean manufacturing con kanban. Tuttavia, il successo di un'implementazione dei principi di lean manufacturing dipende dai processi aziendali interni in uso e dall'ambiente e dalle condizioni di produzione effettivi. |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a>Modellizzazione dei processi di logistica e di produzione come flussi di produzione
Per creare una base di lean manufacturing, modellare i processi di logistica e di produzione come flussi di produzione. Questa attività consiste nelle seguenti mansioni:
1.  Identificare i processi per cui si desidera implementare una strategia di rifornimento lean, quindi modellarli come flussi di produzione. È possibile quindi analizzare e semplificare i processi. Uno degli obiettivi di un'implementazione snella è di ridurre lo spreco migliorando il flusso di materiale e informazioni.
2.  Definire un flusso di produzione come una sequenza di attività che descrive il flusso di materiale. Un'attività di trasferimento definisce il movimento di uno o più prodotti da una località a un'altra. Un'attività di processo definisce un'operazione a valore aggiunto che viene applicata a un prodotto.
3.  Creare una versione del flusso di produzione che definisca i requisiti per il tempo di produzione di un'unità. Questi requisiti vengono utilizzati per calcolare la durata di ciclo di ciascuna attività del flusso di produzione. È possibile creare più versioni dei flussi di produzione e utilizzarle per migliorare i processi.

## <a name="using-kanbans-to-signal-demand-requirements"></a>Utilizzo dei kanban per segnalare il fabbisogno della domanda
Il system pull è un sistema di produzione in base al quale le merci vengono prodotte solo su richiesta. Questa procedura abbrevia il lead time di consegna e riduce l'eccesso di scorte. Per pianificare, tenere traccia ed elaborare il fabbisogno basato sui flussi di produzione, è possibile utilizzare i kanban. Per creare un framework kanban, creare delle regole kanban che definiscano quando creare i kanban e come soddisfare il fabbisogno. È possibile creare due tipi di regole kanban: Le regole produzione creano i processi kanban e le regole kanban di prelievo creano i processi kanban di trasferimento. È possibile impostare le seguenti strategie di rifornimento:
-   Le regole kanban a **Quantità fissa** sono correlate a un numero di unità movimentazione fisso, pertanto i numeri di kanban attivi sono costanti. Ogni volta che tutti i prodotti da un kanban vengono consumati e le unità movimentazione vengono svuotate manualmente, un nuovo kanban dello stesso tipo viene creato. Quando si creano regole kanban a quantità fissa, è possibile calcolare le quantità kanban ottimali e le quantità di prodotto utilizzate. Il calcolo prende in considerazione la previsione, la domanda effettiva degli ordini aperti, il lead time per rifornire articoli e le richieste dello storico.
-   Le regole kanban **programmate** soddisfano il fabbisogno calcolato dalla pianificazione generale. La pianificazione generale genera kanban pianificati che possono essere consolidati a kanban.
-   Le regole kanban **evento** soddisfano il fabbisogno derivante dalle righe ordini clienti, dalle righe della DBA di produzione, dalle righe kanban e dalle impostazioni dei livelli minimi di scorte. I kanban evento generati vengono sottoposti a pegging in base al fabbisogno all'origine.

Con la creazione dei kanban, vengono generati uno o più processi kanban in base alle attività del flusso kanban che sono definite nelle regole kanban.

## <a name="monitoring-and-maintaining-kanban-jobs"></a> Monitorare e gestire i processi kanban
La funzionalità lean manufacturing è una finestra aperta sullo stato corrente delle attività di logistica e di produzione disciplinate dalle regole kanban. Di conseguenza, è possibile pianificare e assegnare priorità alle attività seguenti:

-   Ottenere una panoramica della programmazione corrente dei processi kanban.
-   Pianificare e riprogrammare i processi kanban.
-   Tenere traccia e registrare lo stato dei processi kanban.

Nel seguente elenco vengono descritte le bacheche kanban specifiche:
-   Programmazione dei processi kanban – Viene fornita una panoramica dei processi kanban. La bacheca visualizza i processi kanban e lo stato per una o più celle di lavoro. I processi sono elencati in base ai periodi di pianificazione (giorni o settimane) che sono definiti nel modello di flusso di produzione. Nella bacheca viene inoltre visualizzato il consumo di capacità per ogni periodo di pianificazione. In questo modo è possibile monitorare il carico programmato. È possibile modificare lo stato dei processi kanban, riprogrammarli in periodi di pianificazione diversi ed eseguire altre attività.
-   Bacheca kanban per i processi di trasferimento: in questa bacheca viene fornita una panoramica dei processi di trasferimento correnti. È possibile aggiornare e registrare le distinte di prelievo, avviare e completare i processi di trasferimento ed eseguire altre attività.
-   Bacheca kanban per i processi di lavorazione - Questa bacheca è progettata per supportare il flusso di produzione normale e per effettuare una panoramica della situazione corrente in una o più celle di lavoro. Da questa bacheca ai kanban può essere assegnata la priorità, possono prelevati o prodotti. La bacheca è inoltre progettata per supportare lo scansione del codice a barre per la registrazione di kanban.

## <a name="kanban-jobs-and-integration-with-microsoft-dynamics-ax-processes"></a>Processi kanban e integrazione con i processi di Microsoft Dynamics AX
I processi kanban sono pienamente integrati con i processi correnti per le operazioni di magazzino in Microsoft Dynamics AX.
-   È possibile eseguire attività di prelievo per rifornire il materiale utilizzato per i processi kanban.
-   È possibile stampare le schede kanban, le schede kanban circolanti e le distinte di prelievo a supporto dell'utilizzo dei kanban. Questi documenti vengono utilizzati per rappresentare, tenere traccia e registrare i processi kanban nel magazzino e nel reparto di produzione.
-   È possibile registrare le attività di prelievo e di trasferimento delle scorte eseguendo la scansione dei codici a barre.

Inoltre, la funzionalità lean manufacturing supporta i processi di acquisto e di fatturazione per i servizi ai quali fanno riferimento le attività in conto lavoro.
-   È possibile assegnare servizi e righe del contratto di acquisto alle attività in conto lavoro.
-   È possibile creare ordini fornitore e comunicazioni di ricevimento periodici a supporto dell'acquisto e della fatturazione dei servizi.






