---
title: Programmazione processi kanban
description: Questa procedura riguarda la programmazione dei processi kanban di lavorazione per una cella di lavoro specifica.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c8c088e7f70303aae9f106f627778108062a073f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811016"
---
# <a name="schedule-kanban-jobs"></a>Programmazione processi kanban

[!include [banner](../../includes/banner.md)]

Questa procedura riguarda la programmazione dei processi kanban di lavorazione per una cella di lavoro specifica. La procedura "Preparare un processo kanban quando non sono disponibili materiali per la cella di lavoro" è un prerequisito per creare questa procedura. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa attività è destinata al supervisore dello shop floor e al responsabile di pianificazione della produzione che utilizzano i processi kanban.


## <a name="select-kanban-jobs-for-a-work-cell"></a>Selezionare processi kanban per una cella di lavoro
1. Andare a Controllo produzione > Kanban > Programmazione processo kanban.
2. Espandere il riquadro Dettaglio informazioni della capacità periodo
    * Espandere il riquadro Dettaglio informazioni kanban.  
3. Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare la cella di lavoro 1250. In questo modo verrà filtrata la visualizzazione per mostrare solo i processi per la cella di lavoro 1250.  
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su Seleziona.

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>Programmare un processo kanban nel primo periodo disponibile
1. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare la prima riga nell'elenco con lo stato Non pianificato. L'icona punteggiata nel campo Stato del processo indica uno stato non pianificato.  
2. Fare clic su Programma.
    * In questo modo il processo kanban verrà programmato nel primo periodo disponibile.  
    * Si noti che il processo kanban viene spostato alla fine dell'elenco perché è stato aggiunto al periodo a partire dalla data odierna.  
    * Se il periodo a partire dalla data odierna è completamente prenotato, il processo verrà spostato nel primo periodo disponibile.  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>Programmare due processi kanban per un giorno specifico
1. Nell'elenco selezionare la riga 1.
    * Nel campo Stato del processo alla prima riga è associato lo stato Non pianificato.  
2. Nell'elenco selezionare la riga 2.
    * Nel campo Stato del processo alla seconda riga è associato lo stato Non pianificato. Ora i primi due processi sono selezionati.  
3. Fare clic su Data di inizio programmazione per aprire la finestra di dialogo a discesa.
4. Selezionare o deselezionare la casella Ignora reazione alla carenza di capacità.
    * Questa opzione consente di sostituire la reazione alla carenza di capacità predefinita.  
5. Nel campo Reazione alla carenza di capacità selezionare Aggiungi al periodo richiesto.
    * Questa opzione assicura che il processo viene aggiunto al periodo di tempo richiesto se la cella di lavoro risultasse sovraccarica.  
6. Fare clic su Programma.
    * Si noti che entrambi i processi vengono aggiunti al periodo desiderato.  
    * Nella sezione Capacità periodo, è possibile visualizzare il carico per ogni periodo. Il campo Consumo mostra il consumo previsto in questo periodo. Se il consumo programmato è superiore alla capacità disponibile di questo periodo, verrà selezionato il consumo di overload.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]