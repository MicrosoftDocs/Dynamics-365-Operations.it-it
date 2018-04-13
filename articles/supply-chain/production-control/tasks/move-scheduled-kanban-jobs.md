--- 
title: Spostare processi kanban programmati
description: Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso.
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a>Spostare processi kanban programmati

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La procedura è destinata al supervisore dello shop floor o al responsabile di pianificazione della produzione che utilizza i processi kanban.


## <a name="select-scheduled-kanban-jobs"></a>Selezionare processi kanban programmati
1. Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.
2. !MtCMR!Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca. áçêìõý !
3. Markér den valgte række på listen.
    * Selezionare la cella di lavoro 1250.  
4. Klik på Select.
5. Vælg 'Planlagt' i feltet Display job status.
    * Viene filtrato l'elenco dei processi per visualizzare solo i processi kanban programmati.  

## <a name="move-kanban-jobs-to-a-different-period"></a>Spostare processi kanban in un periodo diverso
1. Find og vælg den ønskede post på listen.
    * Selezionare un processo con stato del processo Pianificato, ad esempio un processo programmato il 20 dicembre 2012 nel campo Periodo pianificato, quindi spostare il processo al periodo precedente.  
2. Klik på Previous period.
3. Klik på End.
    * In questo modo il processo verrà spostato alla fine dell'elenco di processi come l'ultimo processo nel periodo precedente.  
4. Find og vælg den ønskede post på listen.
    * Selezionare un processo con stato del processo Pianificato, ad esempio un processo programmato il 18 dicembre 2012 nel campo Periodo pianificato, quindi spostare il processo al periodo successivo.  
5. Klik på Next period.
6. Klik på Start.
    * In questo modo il processo verrà spostato all'inizio dell'elenco di processi come il primo processo nel periodo precedente.  

## <a name="task-move-a-job-within-a-period"></a>Attività: spostare un processo all'interno di un periodo
1. Find og vælg den ønskede post på listen.
    * Selezionare un processo con stato del processo Pianificato, ad esempio il secondo processo programmato il 19 dicembre 2012 nel campo Periodo pianificato, quindi spostare il processo nel periodo pianificato.  
2. Klik på Forward.
    * Si noti che il processo viene spostato una riga verso il basso nell'elenco.  
3. Klik på Backward.
    * Si noti che il processo viene spostato una riga verso l'alto nell'elenco.  


