---
title: Diagramma di Gantt per la programmazione dei processi
description: I pianificatori di produzione possono monitorare e ottimizzare i piani di produzione utilizzando i diagrammi di Gantt.
author: johanhoffmann
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 301db69fce18c2ed32e201e7418e628ac57db543
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571842"
---
# <a name="gantt-chart-for-job-scheduling"></a>Diagramma di Gantt per la programmazione dei processi

[!include [banner](../includes/banner.md)]

Il diagramma di Gantt è progettato per mettere i pianificatori di produzione nelle condizioni di monitorare e ottimizzare il piano di produzione. Il diagramma di Gantt rende il flusso delle operazioni trasparente e semplifica la rettifica della programmazione della produzione, prendendo nel contempo in considerazione le carenze di risorse o materiale. In questo modo i pianificatori usano in modo ottimale le risorse disponibili, riducono il lavoro in corso e ottimizzano i tempi di elaborazione degli ordini di produzione.

Un diagramma di Gantt è la rappresentazione grafica delle attività previste in un determinato intervallo di tempo. Le attività sono programmate sulle risorse che hanno la capacità definita da un calendario di capacità. I seguenti tipi di attività possono essere visualizzati nel diagramma di Gantt.

-   Processi derivati da ordini di produzione che sono programmati come processi.
-   Processi derivati da ordini di produzione pianificati.
-   Attività di progetto programmate come processi del tipo Previsioni ore.

Il diagramma di Gantt può essere aperto in due diverse visualizzazioni, **Visualizzazione ordini** e **Visualizzazione risorse**[](https://authoring.help.dynamics.com/en/?post_type=incsub_wiki&p=1665154&preview=true). In **Visualizzazione ordini**, le attività vengono raggruppate negli ordini di produzione. Ciò può essere utile, ad esempio, se si desidera mantenere una panoramica di tutti i processi appartenenti agli stessi ordini. In **Visualizzazione risorse** tutti i processi vengono raggruppati in singole risorse. Questa visualizzazione risulta utile quando si ottimizza il piano a livello di risorsa, ad esempio, di computer o di gruppo di computer. I diagrammi di Gantt visualizzati nelle illustrazioni che seguono mostrano **Visualizzazione ordini** e **Visualizzazione risorse** con questi elementi principali:

1.  Attività del diagramma di Gantt
2.  Icona Carenza di materiale
3.  Icona Disponibilità di materiale
4.  Icona Data di consegna dell'ordine
5.  Barra della capacità

## <a name="order-view"></a>Visualizzazione ordini

[![Visualizzazione ordini](./media/orderview.png)](./media/orderview.png)

## <a name="resource-view"></a>Visualizzazione risorse
[![Visualizzazione risorse](./media/resview.png)](./media/resview.png)

## <a name="activities"></a>Attività
Le attività vengono visualizzate come barre e sono organizzate in una griglia della scala cronologica con una data di inizio e una data di fine programmate e la lunghezza delle barre è proporzionale al tempo necessario per completare l'attività. Le attività vengono visualizzate in base a una scala cronologica. È possibile modificare la scala cronologica nel menu in cui si seleziona una data di fine e un'unità di tempo, ad esempio, ore o giorni. Regolando la scala cronologica è possibile impostare l'elemento attivo su un intervallo di tempo in cui si desidera gestire le attività. 

Per ottenere una panoramica più dettagliata, sono presenti opzioni diverse per il controllo del colore delle attività. È possibile configurare un singolo colore per attività, utilizzare il colore del tema, ovvero il tema del colore generale utilizzato per la domanda, oppure impostare il colore da controllare attraverso il codice colore per gli ordini di produzione. 

L'intervallo di tempo per le attività ha uno sfondo ombreggiato. I periodi con ombreggiatura bianca indicano un intervallo di tempo con capacità definita della risorsa per l'attività, mentre i periodi con ombreggiatura grigia indicano gli intervalli di tempo senza capacità definita. 

Sul lato sinistro del diagramma sono disponibili ulteriori informazioni sull'attività, ad esempio, la risorsa in cui l'attività è programmata e numero di ordine di produzione. La connessione tra i processi appartenenti allo stesso ordine viene indicata con una freccia. 

È possibile ottenere ulteriori informazioni su un'attività nella finestra di dialogo Attività. Per aprire la finestra di dialogo, fare doppio clic sull'attività o selezionare il menu **informazioni**. Nella finestra di dialogo Attività è possibile visualizzare la data di inizio e la data di fine programmate e le informazioni temporali su quali sono i materiali che l'attività dovrà consumare. 

Le attività possono essere raggruppate in livelli di raggruppamento. I livelli di raggruppamento sono gerarchici e possono essere utilizzati per effettuare raggruppamenti logici di attività. Ad esempio, se si dispone di un layout in cui le attività di produzione vengono raggruppate per sito, unità di produzione, gruppi di risorse e risorse, è possibile utilizzare i livelli di raggruppamento per raggruppare le attività in base a tale layout. I livelli di raggruppamento possono essere estesi e compressi a livello di singolo raggruppamento o per tutti i livelli del diagramma utilizzando i pulsanti **Espandi tutto** e **Comprimi tutto** del menu. È inoltre possibile configurare l'espansione o la compressione di tutti i livelli di raggruppamento quando il grafico è aperto.

### <a name="material-availability"></a>Disponibilità di materiale

Il diagramma di Gantt può essere configurato in modo da fornire alla pianificazione informazioni dettagliate sullo stato del materiale per le singole attività. Ad esempio, questo può essere utile se il materiale subisce un ritardo che influisce sul piano di produzione. In questo caso, le uscite di materiale vengono evidenziate nel diagramma di Gantt per consentire alla pianificazione di comprendere le conseguenze e apportare le rettifiche necessarie. 

Un processo verrà visualizzato con un'icona di carenza di materiali se la data di inizio della programmazione del processo è successiva alla data di disponibilità dei materiali per i materiali utilizzati dal processo. La data di disponibilità dei materiali viene calcolata in base alle informazioni di pegging nel piano generale dinamico. L'icona di carenza di materiali verrà ad esempio visualizzata in un processo in cui viene utilizzato un materiale che è sottoposto a pegging rispetto a un ordine fornitore con un'entrata successiva alla data di inizio prevista per il processo.

### <a name="indicator-of-material-availability-date"></a>Indicatore della data di disponibilità del materiale

Quando si imposta il grafico per visualizzare processi con carenze di materiale, può essere visualizzata anche un'icona che mostri la data di disponibilità dei materiali per il processo. L'icona verrà visualizzata solo se la data di disponibilità dei materiali viene inclusa nell'intervallo di tempo definito del diagramma. Se la data di disponibilità del materiale si trova al di fuori dell'intervallo di tempo definito, informazioni più dettagliate sulla disponibilità del materiale possono essere recuperate dall'elenco del materiale nella finestra di dialogo del processo. Nell'elenco è presente anche un'icona che mostra i materiali recenti per il processo. È possibile riprogrammare un processo utilizzando la data di disponibilità del materiale come data di inizio.

### <a name="indicator-of-order-delivery-date"></a>Indicatore della data di consegna dell'ordine

Questa icona indica la data di consegna di un ordine di produzione. L'icona è visibile solo in Visualizzazione ordini.

### <a name="capacity-bar"></a>Barra della capacità

È possibile configurare il diagramma per visualizzare una barra di capacità della risorsa. Questa barra offre una panoramica della capacità della risorsa per un'attività nell'intervallo di tempo definito del diagramma. La barra di capacità non viene visualizzata per periodi di tempo in cui la risorsa non viene prenotata. Nei periodi in cui la capacità della risorsa è prenotata, la barra di capacità viene visualizzata come barra solida. Nei periodi in cui la risorsa è prenotata in eccesso, la barra sembrerà più spessa e sarà rossa. Ad esempio, se due processi si sovrappongono, la barra della capacità indicherà una prenotazione in eccesso nell'intervallo di tempo in cui è presente una sovrapposizione. La barra della capacità viene aggiornata in modo dinamico quando si programma un processo. Si abilita la barra della capacità nel menu **Mostra barra della capacità**. Può essere visualizzata solo in **Visualizzazione risorse**. Se si desidera ottenere una visualizzazione più dettagliata del carico di capacità per una risorsa, utilizzare il grafico **Carico di capacità**, che può essere aperto dal menu o dal menu di scelta rapida di un'attività selezionata.

## <a name="job-scheduling-in-the-gantt-chart"></a>Programmazione di processi nel diagramma di Gantt
Nel diagramma di Gantt sono disponibili diverse opzioni per rettificare il piano di produzione. Nel diagramma di Gantt è possibile riprogrammare le attività come interazione di trascinamento della selezione o in un menu di programmazione. Nel processo di pianificazione è possibile prendere in considerazione la capacità della risorsa, le capacità delle risorse e i vincoli del materiale.

### <a name="schedule-a-job-as-a-drag-and-drop-interaction"></a>Programmare un processo come interazione di trascinamento della selezione

È possibile riprogrammare il processo nell'intervallo di tempo definito come interazione di trascinamento della selezione. È possibile riprogrammare il processo solo nella stessa risorsa ed è possibile programmare solo un processo alla volta.

### <a name="schedule-a-job-from-the-menu"></a>Programmare un processo tramite il menu

Nel menu **Programma processi** è possibile programmare uno o più processi selezionati nel grafico in base a una direzione di programmazione e a un'ora nella data di programmazione. Sono disponibili tre tipi di direzioni della programmazione.

-   Avanti da data programmazione
-   Indietro da data programmazione
-   Avanti da data di disponibilità materiali

Non è possibile programmare un processo al di fuori dell'intervallo di tempo definito del diagramma di Gantt. Se si riesce, il processo verrà lasciato non programmato e verrà restituito un messaggio di errore "Impossibile programmare il processo durante il periodo di tempo caricato".

### <a name="schedule-previous-jobs"></a>Programma processi precedenti

In una rete di attività, ad esempio i processi appartenenti allo stesso ordine di produzione, è possibile utilizzare la funzione **Programma processi precedenti** per la programmazione dei processi precedenti rispetto a un processo selezionato nella rete. Nell'esempio che segue l'attività evidenziata è il processo selezionato. Il diagramma mostra il processo selezionato prima della programmazione di un processo precedente e dopo la programmazione di un processo precedente. 

[![Programma processi precedenti](./media/schprevjob3.png)](./media/schprevjob3.png)

### <a name="schedule-next-jobs"></a>Programma processi successivi

È possibile utilizzare la funzione **Programma processi successivi** per la programmazione dei processi successivi in relazione a un processo selezionato in una rete di attività. Nell'esempio che segue l'attività evidenziata è il processo selezionato. Il diagramma mostra il processo selezionato prima della programmazione del processo successivo e dopo la programmazione del processo successivo. 

[![Programma processi successivi](./media/schnxtjob.png)](./media/schnxtjob.png)

### <a name="schedule-around-job"></a>Programmazione su processo

È possibile utilizzare la funzione **Programmazione su processo** per la programmazione del processo successivo e del processo precedente correlati a un processo selezionato in una rete di attività. Nell'esempio che segue l'attività evidenziata è il processo selezionato. Il diagramma mostra il processo selezionato prima della programmazione di un processo e dopo la programmazione di un processo. 

[![Programmazione su processo](./media/scharoundjob1.png)](./media/scharoundjob1.png)

### <a name="arrange-jobs"></a>Disponi processi

È possibile utilizzare la funzione **Disponi** per disporre di attività selezionate nella stessa risorsa. Queste attività possono trovarsi nella stessa rete di attività, ma appartenere anche a reti diverse. Quando si utilizza la funzione di organizzazione, le interruzioni di tempo tra le attività selezionate verranno eliminate. È possibile utilizzare questa funzione per ottimizzare l'uso della capacità delle risorse. Il diagramma mostra il processo selezionato prima della programmazione di un processo e dopo la programmazione di un processo. 

[![Disponi processi](./media/arrangejobs1.png)](./media/arrangejobs1.png)

### <a name="reassign-activities-from-one-resource-to-another"></a>Riassegnare attività da una risorsa a un'altra

È possibile riassegnare un'attività da una risorsa a un'altra. Ciò può essere utile nelle situazioni in cui un computer è guasto o è prenotato in eccesso ed è necessario individuare un'altra risorsa disponibile a effettuare il processo.

### <a name="reassigning-an-activity-as-a-drag-and-drop-interaction"></a>Riassegnare un'attività come interazione di trascinamento della selezione

In visualizzazione **Risorsa** è possibile riassegnare un'attività a una risorsa diversa nel diagramma di Gantt come interazione di trascinamento della selezione. Ciò avviene selezionando la riga nella quale è programmata l'attività. Dopo che la riga viene selezionata, è possibile trascinarla nella risorsa del grafico raggruppato in un livello diverso di raggruppamento delle risorse.

### <a name="reassigning-an-activity-from-the-schedule-jobs-menu"></a>Riassegnare un'attività dal menu Programma processi

È possibile riassegnare un processo nella finestra di dialogo **Programma processo** aperta scegliendo il menu **Programma processo**. Dal questo menu è possibile riassegnare solo un processo a una risorsa già caricata nel diagramma di Gantt. Se si seleziona solo un processo, la casella di riepilogo a discesa della risorsa sarà ordinato in base alle risorse applicabili. Se si selezionano più processi, nell'elenco delle risorse non saranno disponibili informazioni sulle risorse applicabili.

## <a name="load-additional-resources-to-the-gantt-chart"></a>Caricare risorse aggiuntive sul diagramma di Gantt
In **Visualizzazione risorse** è disponibile un'opzione per caricare altre risorse sul diagramma di Gantt. Ciò può essere utile se si desidera trovare una risorsa alternativa per un processo programmato in un computer che viene prenotato in eccesso o che si guasta. Nella pagina **Carica risorse aggiuntive** verrà visualizzato un elenco di risorse valide partire dalla data in cui l'elenco sarà aperto. Le risorse applicabili, correlate a un processo selezionato nel diagramma di Gantt, verranno elencate per prime. Se sono stati selezionati più processi, prima di aprire l'elenco, non verrà visualizzata alcun indicazione delle risorse applicabili. Nella pagina **Carica risorse aggiuntive** è possibile selezionare una o più risorse, che verranno caricate nel diagramma di Gantt quando si conferma la selezione effettuata. Se non esistono processi programmati per la risorsa selezionata nell'intervallo di tempo del diagramma di Gantt, la risorsa verrà inserita con un livello di raggruppamento di risorse nella parte inferiore dell'elenco delle attività nel diagramma di Gantt.

### <a name="access-the-gantt-chart"></a>Accedere al diagramma di Gantt

Il diagramma di Gantt può essere aperto nelle pagine seguenti.


|                                                 <strong>Pagina</strong>                                                  |                                                                                                                                                                                                                                                            <strong>Descrizione</strong>                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   <strong>Elenco e dettagli degli ordini di produzione</strong>                                    | Nella pagina <strong>Elenco e dettagli degli ordini di produzione</strong> è possibile aprire il diagramma di Gantt da uno o più ordini selezionati. L'apertura del diagramma dalla voce di menu <strong>Diagramma di Gantt</strong> caricherà tutti i processi relativi agli ordini di produzione selezionati, ma anche i processi provenienti da altri ordini di produzione programmati nelle stesse risorse. L'apertura del diagramma dalla voce di menu <strong>Diagramma di Gantt - Visualizzazione rapida</strong> caricherà solo i processi relativi agli ordini di produzione selezionati. In questa visualizzazione non è possibile programmare i processi. |
|                                               <strong>Risorsa</strong>                                                |                                                                                                                                                        Nella pagina <strong>Risorsa</strong> è possibile aprire il diagramma di Gantt dalla voce di menu <strong>Diagramma di Gantt</strong>. Quando l'opzione è selezionata, tutti i processi programmati per la risorsa in un intervallo di tempo selezionato verranno caricati nel diagramma.                                                                                                                                                         |
|                                            <strong>Gruppo di risorse</strong>                                             |                                                                                                                                                 Nella pagina <strong>Gruppo di risorse</strong> è possibile aprire il diagramma di Gantt dalla voce di menu <strong>Diagramma di Gantt</strong>. Quando l'opzione è selezionata, tutti i processi programmati per la risorsa nel gruppo di risorse verranno visualizzati in un intervallo di tempo selezionato.                                                                                                                                                 |
|                                             <strong>Diagrammi di Gantt</strong>                                              |                                                                                 Nella pagina <strong>Diagrammi di Gantt</strong> è possibile configurare i diagrammi di Gantt in base alle risorse e ai gruppi di risorse. Ad esempio, se si desidera controllare le attività di produzione per set specifici di risorse o di gruppi di risorse, è possibile effettuare singole configurazioni dei suddetti nella pagina <strong>Diagrammi di Gantt</strong>. È quindi possibile aprire il diagramma di Gantt da ciascuna configurazione.                                                                                 |
|                                       <strong>Previsioni ore</strong> (progetto)                                        |                                                                                                                              Attività di progetto del tipo <strong>Previsioni ore</strong> possono essere programmate come processi nelle risorse. Nella pagina <strong>Previsione ore</strong> del menu <strong>Programmazione</strong> è possibile aprire il diagramma di Gantt in un ordine per visualizzare le attività di progetto programmate come processi di tipo previsione oraria.                                                                                                                               |
|           <strong>Processi da completare</strong> (Elenco nell'area di lavoro <strong>Gestione area di produzione</strong>)            |                                                                                               Nell'area di lavoro <strong>Elenco dei processi da completare in Gestione area di produzione</strong> vengono visualizzati i processi di produzione e gli ordini batch in corso sulle risorse selezionate per l'area di lavoro. Scegliendo la voce di menu <strong>Diagramma di Gantt</strong> è possibile aprire il diagramma di Gantt, nel quale verranno caricati tutti i processi selezionati nell'elenco.                                                                                               |
| <strong>Ordini di produzione da rilasciare</strong> (Aperto dall'area di lavoro <strong>Gestione del piano di produzione</strong> ) |                                                                                                                                         La pagina degli ordini di produzione da rilasciare viene aperta dall'area di lavoro <strong>Gestione del piano di produzione</strong>. In questa pagina viene visualizzata la versione in sospeso degli ordini batch e di produzione programmati. In questa pagina è possibile aprire il diagramma di Gantt per gli ordini di produzione selezionati.                                                                                                                                          |

## <a name="additional-resources"></a>Risorse aggiuntive  
[Programmazione visiva con il diagramma di Gantt per ordini batch e di produzione (video)](https://youtu.be/BtbuShkGj4I)

[Programmazione visiva per la produzione (script demo)](https://mbs.microsoft.com/customersource/northamerica/365Enterprise/learning/documentation/how-to-articles/365finoptvisschep)

