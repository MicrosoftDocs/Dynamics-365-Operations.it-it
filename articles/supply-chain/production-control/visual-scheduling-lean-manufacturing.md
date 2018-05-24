---
title: Programmazione visiva per lean manufacturing
description: "In questo argomento vengono fornite informazioni sulla bacheca della programmazione kanban, che la pianificazione di produzione può utilizzare per controllare e ottimizzare il piano di produzione per i processi kanban."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d2ead061fe39c3dcb54d697f246c2c826339b699
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="visual-scheduling-for-lean-manufacturing"></a>Programmazione visiva per lean manufacturing

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sulla bacheca della programmazione kanban, che la pianificazione di produzione può utilizzare per controllare e ottimizzare il piano di produzione per i processi kanban.

In questo argomento vengono fornite informazioni sulla bacheca della programmazione kanban, che la pianificazione di produzione può utilizzare per controllare e ottimizzare il piano di produzione per i processi kanban.

La bacheca della programmazione kanban consente alla pianificazione di produzione di monitorare e ottimizzare il piano di produzione per i processi kanban. Rende il flusso dei processi kanban chiaro e assegna alla pianificazione della produzione uno strumento che ottimizza e registra il piano di produzione per ottenere la cella di lavoro lean manufacturing.

## <a name="visual-scheduling-of-kanban-jobs"></a>Programmazione visiva dei processi kanban
Un processo kanban può essere costituito da uno o più processi kanban. Sono disponibili due tipi di processi kanban:

-   Processo
-   Trasferimenti

È possibile programmare solo i processi del tipo **Processo**. Il processo kanban e le relative proprietà, ad esempio l'orario attività, vengono definiti nel flusso kanban di produzione. Nel flusso kanban di produzione il processo kanban viene assegnato anche a una cella di lavoro. La capacità giornaliera della cella di lavoro viene calcolata in base alla capacità della cella di lavoro definita nel gruppo di risorse. Viene rettificata in base all'orario di lavoro giornaliero nel calendario correlato. Quando un processo kanban viene programmato, il processo carica la capacità della cella di lavoro. Nella bacheca della programmazione kanban sono disponibili le seguenti funzionalità principali:

-   Una rappresentazione grafica del piano di produzione in una cella di lavoro lean manufacturing. In questa panoramica vengono mostrati i processi di lavorazione kanban pianificati nei periodi definiti.
-   Uno strumento che consente di definire la programmazione dei processi kanban non pianificati e riprogrammare i processi programmati in precedenza.

## <a name="kanban-schedule-board"></a>Bacheca programmazione kanban
La pagina **Bacheca programmazione kanban** contiene sette elementi principali, come illustrato nella figura seguente. 

![Bacheca programmazione kanban](./media/kanban-schedule-board-1024x554.png)
1.  Riquadro azioni
2.  Campi filtro
3.  Pulsante per i processi non pianificati
4.  Nodo periodo
5.  Processo kanban
6.  Barra della capacità
7.  Scala cronologica

### <a name="view-the-time-scale"></a>Consente di visualizzare la scala cronologica

La bacheca è suddivisa in periodi, ognuno dei quali è rappresentato da un nodo (4). I nodi del periodo sono elencati sull'asse verticale e l'accesso orizzontale rappresenta una scala cronologica (7) che mostra la durata del periodo. Un periodo ha una durata di un giorno o una settimana. La durata del periodo viene determinata dalla configurazione della cella di lavoro selezionata nella bacheca della programmazione kanban (2). Per ogni nodo di periodo, la bacheca della programmazione kanban indica quanto i processi kanban programmati stanno caricando nel periodo. Esiste inoltre un'indicazione di produttività massima per il periodo. Se la produttività programmata supera la produttività massima, nel periodo viene considerato sovraccaricato e un simbolo di avviso rosso verrà visualizzato. Un processo kanban programmato è incluso in un periodo con inizio e ore di scadenza (5) programmati. La durata del processo corrisponde al tempo di attività. I processi kanban vengono visualizzati come sovrapposti in un periodo se i relativi tempi di attività superano il tempo di produzione di un'unità della cella di lavoro.

### <a name="view-job-status"></a>Visualizzazione dello stato del processo

Ulteriori informazioni su un processo kanban sono disponibili nella descrizione comandi visualizzata quando si passa il puntatore sul processo. Un simbolo fornisce informazioni sullo stato del processo. Ad esempio, un simbolo dell'orologio indica che il processo kanban è scaduto.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>Utilizzare i colori per visualizzare la bacheca della programmazione kanban

Per aumentare la panoramica fornita dalla bacheca della programmazione kanban, è possibile utilizzare i colori per distinguere i processi kanban. Il colore di un processo kanban viene configurato nel gruppo di produzione snella, in cui è possibile aggregare i prodotti che devono essere prodotti nello stesso ordine. Il pulsante **Utilizza colori tema** nella scheda **Bacheca** del riquadro azioni consente di passare dai colori dei temi dell'applicazione e i colori configurati nel gruppo di produzione snella e viceversa. Per ciascun periodo, una barra di capacità (6) indica quante delle ore disponibili per il periodo sono state caricate con i processi kanban. Se il periodo è sovraccarico, la barra di capacità diviene più spessa e rossa. Tutte le funzioni sono disponibili nella scheda **Bacheca** del riquadro azioni (1) nella parte superiore della pagina **Bacheca programmazione kanban**.

## <a name="plan-unplanned-jobs"></a>Pianifica processi non pianificati
È possibile programmare i processi kanban non pianificati nella finestra di dialogo **Pianifica processi non pianificati**. Per aprire la finestra di dialogo, fare clic sul pulsante **Processi non pianificati** contenente il numero corrente di processi non pianificati. In alternativa, fare clic su **Pianifica processi non pianificati** nella scheda **Bacheca** del riquadro azioni. Nella finestra di dialogo viene visualizzato un elenco di processi kanban non pianificati per la cella di lavoro. È possibile utilizzare il campo **Filtro** per filtrare tutti i campi nella griglia. Ad esempio, è possibile filtrare i processi kanban relativi a un prodotto specifico. Quando si dispone di un elenco filtrato dei processi che si desidera programmare, selezionarli nell'elenco e fare clic su **OK**. Per utilizzare la pianificazione automatica per la programmazione dei processi, impostare l'opzione **Pianificazione automatica** su **Sì**. In questo caso, i processi vengono programmati in un periodo in base alla relativa data di scadenza. È inoltre possibile definire la programmazione dei processi per periodo. Basta selezionare un periodo nel campo **Periodo**. Nella figura seguente è illustrato un esempio della finestra dialogo **Pianifica processi non pianificati**. 

![Finestra di dialogo Pianifica processi non pianificati](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>Processi kanban in sequenza durante lo stesso periodo
È possibile modificare la sequenza di uno o più processi selezionati in un determinato periodo. Questa funzione può risultare utile se si desidera assegnare la priorità ai processi durante il periodo. In alternativa, è possibile ordinare i processi con gli stessi attributi del prodotto per ottimizzare l'esecuzione del processo. È possibile modificare la sequenza con un'operazione di trascinamento della selezione o utilizzando le voci di menu **Indietro** e **Avanti** della scheda **Bacheca** del riquadro azioni.

## <a name="reassign-kanban-jobs-across-periods"></a>Riassegnare i processi kanban tra più periodi
I processi possono essere riassegnati da un periodo a un altro. Questa funzione può essere utile se un periodo è sovraccarico e si desidera livellare il carico sui periodi che hanno capacità. È possibile riassegnare processi con un'operazione di trascinamento della selezione o utilizzando le voci di menu **Periodo successivo** e **Periodo precedente** della scheda **Bacheca** del riquadro azioni.

## <a name="open-the-kanban-schedule-board"></a>Aprire la bacheca della programmazione kanban
È possibile aprire la bacheca della programmazione kanban utilizzando la voce di menu nelle pagine seguenti:

-   pagina **Area di produzione**
-   pagina **Programmazione dei processi kanban**
-   pagina **Visualizzazione flusso di produzione**


<a name="additional-resources"></a>Risorse aggiuntive
--------

[Lean manufacturing: programmazione dei processi kanban](lean-manufacturing-kanban-job-scheduling.md)


