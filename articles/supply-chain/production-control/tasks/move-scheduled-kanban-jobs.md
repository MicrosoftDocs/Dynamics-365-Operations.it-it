---
title: Spostare processi kanban programmati
description: Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso.
author: ChristianRytt
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b258512a81033dbceb61057e062eb041177b552413b6444497dade63d07f76d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754562"
---
# <a name="move-scheduled-kanban-jobs"></a>Spostare processi kanban programmati

[!include [banner](../../includes/banner.md)]

Questa procedura riguarda lo spostamento di processi kanban di lavorazione pianificati in periodo diverso. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La procedura è destinata al supervisore dello shop floor o al responsabile di pianificazione della produzione che utilizza i processi kanban.

## <a name="select-scheduled-kanban-jobs"></a>Selezionare processi kanban programmati. 

1. Andare a **Controllo produzione > Kanban > Programmazione processo kanban**. 

2. Nel campo **Cella di lavoro**, fare clic sul pulsante a discesa per aprire la ricerca. 

3. Nell'elenco contrassegnare la riga selezionata. 
   - Selezionare la cella di lavoro 1250. 
4. Fare clic su **Seleziona**. 

5. Nel campo **Visualizza stato processo** selezionare **Programmato**. Viene filtrato l'elenco dei processi per visualizzare solo i processi kanban programmati. 

## <a name="move-kanban-jobs-to-a-different-period"></a>Spostare processi kanban in un periodo diverso. 

1. Nell'elenco trovare e selezionare il record desiderato. Selezionare un processo con stato **processo Pianificato**, ad esempio un processo programmato il 20 dicembre 2012 nel campo **Periodo pianificato**, quindi spostare il processo al periodo precedente. 

2. Fare clic su **Periodo precedente**. 

3. Fare clic su **Fine** per spostare il processo alla fine dell'elenco di processi come l'ultimo processo nel periodo precedente. 

4. Nell'elenco trovare e selezionare il record desiderato. Selezionare un processo con stato **processo Pianificato**, ad esempio un processo programmato il 18 dicembre 2012 nel campo **Periodo pianificato**, quindi spostare il processo al periodo successivo. 

5. Fare clic su **Periodo successivo**. 

6. Fare clic su **Inizio** per spostare il processo all'inizio dell'elenco di processi come primo processo nel periodo precedente. 

## <a name="move-a-job-within-a-period"></a>Spostare un processo all'interno di un periodo. 

1. Nell'elenco trovare e selezionare il record desiderato. Selezionare un processo con stato Processo pianificato, ad esempio il secondo processo programmato il 19 dicembre 2012 nel campo **Periodo pianificato**, quindi spostare il processo nel periodo pianificato. 

2. Fare clic su **Avanti**. Si noti che il processo viene spostato una riga verso il basso nell'elenco. 

3. Fare clic su **Indietro**. Si noti che il processo viene spostato una riga verso l'alto nell'elenco.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]