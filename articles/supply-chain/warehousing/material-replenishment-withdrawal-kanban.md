---
title: Rifornimento con kanban di prelievo
description: Questo argomento descrive come viene utilizzato il kanban di prelievo per il rifornimento di materiale per le attività di produzione.
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanFlow, KanbanRules, WHSKanbanWaveTable, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edc6da8a54de98696322ace67ada5dfe97af2024
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189946"
---
# <a name="replenishment-with-withdrawal-kanbans"></a>Rifornimento con kanban di prelievo

[!include [banner](../includes/banner.md)]

Questo argomento descrive come viene utilizzato il kanban di prelievo per il rifornimento di materiale per le attività di produzione.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>Flusso di lavoro per il rifornimento di materiale che utilizza il kanban di prelievo

Il kanban di prelievo può essere utilizzato per spostare un kanban di un singolo articolo tra magazzini e le ubicazioni di produzione in cui il materiale viene consumato. Il kanban di prelievo supporta a una soluzione basata su pull per il rifornimento di materiale, in cui un segnale pull è necessario per attivare l'offerta per una domanda specifica. 

Lo scenario seguente mostra un sistema di rifornimento basato su pull in cui un segnale pull attiva la creazione di un kanban per il rifornimento del materiale per un processo di produzione. 

[![Segnale pull che attiva la creazione di un kanban per il rifornimento di materiale per un processo di produzione](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  Kanban di prelievo
2.  Ubicazione "da" e di stoccaggio finale del kanban per lavoro magazzino
3.  Ubicazione "a" e di entrata produzione kanban
4.  Processo di produzione
5.  Lavoro di magazzino per il prelievo kanban
6.  Ubicazioni di magazzino per materie prime
7.  Magazzino materiale
8.  Magazzino di produzione

In questo scenario, un processo di produzione (4) utilizza il materiale da un'ubicazione di entrata produzione (3) nel magazzino di produzione (8). Se un'unità movimentazione del materiale (kanban) viene utilizzata, viene registrata come vuota. Un segnale di rifornimento viene creato per l'origine articolo e un nuovo kanban (1) viene creato. In questo caso, l'origine dell'articoloo è costituita dalle ubicazioni del magazzino materiale (7). Il materiale per il kanban viene prelevato e stoccato in un'ubicazione (2) nello stesso magazzino. Quando il materiale viene prelevato, è pronto per essere trasferito dall'ubicazione 2 nell'ubicazione di entrata produzione (3) nel magazzino di produzione (8).

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>Configurare il lavoro del magazzino per il prelievo del kanban per il kanban di prelievo

Per abilitare il prelievo di materie prime per il kanban di prelievo, configurare modelli di ondata, modelli di lavoro e direttive di ubicazione per il tipo di ordine di lavoro **Prelievo kanban**. Questo tipo di ordine di lavoro non supporta solo il processo di prelievo per il kanban di prelievo. Supporta anche il processo di prelievo per il kanban di produzione. Tuttavia, è possibile configurare un processo separato di prelievo per ciascun tipo di kanban separando i modelli di ondata, i modelli di lavoro e le direttive di posizione. Per separare i modelli ondata, i modelli di lavoro e le direttive di posizione, impostare i criteri per il tipo di attività (**Processo** o **Trasferimento**) nelle query per tali entità.

## <a name="configure-the-withdrawal-kanban"></a>Configurare il kanban di prelievo

L'attività di trasferimento utilizzata per il kanban di prelievo è configurata come parte di un piano delle attività attivato in un flusso di produzione snella. Durante la configurazione dell'attività di trasferimento, specificare le ubicazioni "da" e "a" per il trasferimento. Dopo aver configurato le attività di trasferimento, è possibile assegnarle a una regola kanban del tipo **Prelievo**. La regola kanban imposta i criteri e le configurazioni per il kanban di prelievo. La quantità del kanban determina il numero di unità movimentazione trasportate dal kanban durante il processo di trasferimento. La quantità kanban fissa viene utilizzata quando la strategia di rifornimento fissa è selezionata. Questa quantità definisce il numero di kanban richiesti per impedire l'esaurimento di scorte o inventario all'origine della domanda. La quantità fissa può essere calcolata in base alla domanda effettiva, la domanda storica e i livelli di servizio. I due scenari seguenti descrivono come è possibile gestire il rifornimento di materiale che utilizza il kanban di prelievo.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>Scenario 1: effettuare il rifornimento di un'ubicazione di entrata produzione mediante un kanban di prelievo fisso

Un processo di produzione utilizza materie prime acquistate da da un'ubicazione di entrata produzione che si trova nel magazzino di produzione. Quando le materie prime vengono ricevute dal fornitore, vengono conservate nelle ubicazioni del magazzino materiale. Poiché la domanda di materiali viene considerata stabile per un periodo, è impostata in modo da garantire la produzione in un flusso kanban a quantità fissa. Quando un kanban viene utilizzato nell'ubicazione entrata produzione, un segnale vuoto viene registrato e un nuovo kanban dello stesso tipo viene aggiunto al flusso. 

Il segnale vuoto può essere configurato per essere emesso automaticamente quando un kanban viene completato. In alternativa, il segnale vuoto può essere impostato come interazione manuale specificata dalla scheda di trasferimento kanban o dal menu di un dispositivo portatile. La scheda di trasferimento kanban è l'area di lavoro in cui tutte le attività nel ciclo di vita di kanban vengono gestite. 

Quando il kanban viene creato, una riga di ondata per le materie prime viene aggiunta a un'ondata kanban per il magazzino del materiale. Nella sezione delle distinte di prelievo della scheda di trasferimento kanban, lo stato del materiale e i processi di magazzino correlati possono essere controllati dalla creazione dell'onda alla creazione lavoro, fino a che il materiale non sia disponibile nell'ubicazione "trasferimento da" ed è pronto per essere trasferito nelle ubicazioni di entrata produzione. Il kanban può essere completato dalla scheda di trasferimento kanban o dal menu di un dispositivo portatile. 

In questo esempio, il lavoro di prelievo nel magazzino materiale viene elaborato come un'attività. L'attività di trasferimento tra il magazzino materiali e il magazzino di produzione viene elaborata come attività separata. Questo approccio può essere utile se, ad esempio, la distanza fisica tra i due magazzini è grande. In questo caso, l'attività di trasferimento kanban può rappresentare un carico su camion. 

Se la distanza tra ubicazioni di magazzino e l'ubicazione di entrata produzione è piccola, potrebbe essere più efficiente includere l'attività di trasferimento nel processo di prelievo. Quindi, dopo che il materiale è stato prelevato, può essere collocato direttamente nell'ubicazione di entrata produzione. Per supportare questo processo, configurare l'attività di trasferimento in modo da completarla automaticamente quando il lavoro di prelievo del kanban di prelievo viene elaborato.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>Scenario 2: completare automaticamente l'attività di trasferimento quando il lavoro di prelievo kanban viene elaborato

Nel seguente scenario, l'attività di trasferimento del kanban di prelievo viene configurata per il trasferimento tra due ubicazioni nello stesso magazzino. L'attività di trasferimento del kanban di prelievo viene impostata in modo che venga completata automaticamente. 

[![L'attività di trasferimento viene completata automaticamente quando il lavoro di prelievo del kanban viene elaborato](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  Magazzino condiviso per materie prime e produzione
2.  Ubicazioni di magazzino per materie prime
3.  Ubicazione "da" e di stoccaggio finale del kanban per lavoro magazzino
4.  Kanban di prelievo
5.  Ubicazione entrata produzione
6.  Processo di produzione

Dopo che un kanban è stato utilizzato nell'ubicazione entrata produzione, viene segnalato come vuoto e un nuovo kanban viene aggiunto al flusso. Quando il kanban viene creato, una riga di ondata viene aggiunta a un'ondata kanban. Quando l'ondata kanban viene elaborata, il lavoro di magazzino per il prelievo di kanban viene creato. Il lavoratore di magazzino elabora il lavoro per il prelievo di kanban e viene indirizzato dal lavoro per prelevate il materiale per il kanban in un'ubicazione di magazzino. Non appena il lavoratore di magazzino conferma il prelievo, il kanban viene automaticamente completato e il lavoratore del magazzino viene indirizzato a  collocare il materiale nell'ubicazione di entrata produzione.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]