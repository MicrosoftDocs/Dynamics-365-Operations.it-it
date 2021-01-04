---
title: Ripristina stato del processo kanban
description: La procedura riguarda il ripristino di uno stato non di processo kanban non corretto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cca5ea3a4c33c7f36acd18a8af7034466b3b580
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431110"
---
# <a name="revert-kanban-job-status"></a>Ripristina stato del processo kanban

[!include [banner](../../includes/banner.md)]

La procedura riguarda il ripristino di uno stato non di processo kanban non corretto. Questa opzione è utile nel caso dell'operatore che aggiorna il processo sbagliato o imposta lo stato non corretto per errore. In questa procedura, un processo kanban viene registrato come preparato per errore e lo stato viene ripristinato. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al supervisore o all'operatore che opera in una società di produzione snella.


## <a name="open-process-board-for-the-work-cell"></a>Aprire la bacheca processo per la cella di lavoro
1. Andare a Bacheca kanban per i processi lavorazione.
2. Nel campo Cella di lavoro immettere o selezionare un valore.
    * Selezionare la cella di lavoro 1260.  

## <a name="prepare-kanban-job"></a>Preparare il processo kanban
1. Fare clic su Prepara.
    * Se non è possibile fare clic su Prepara perché è in grigio, assicurarsi che il processo kanban selezionato abbia lo stato Pianificato, indicato dall'icona kanban vuota. Se Prepara ha esito negativo, assicurarsi che tutti i materiali nella distinta di prelievo siano disponibili.  
2. Selezionare il processo preparato nell'elenco.
    * Selezionare il primo processo appena preparato.  
    * Si noti che lo stato del processo è Preparato, indicato con un triangolo all'interno dell'icona kanban.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>Reimpostare lo stato del processo kanban preparato
1. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare il primo processo che era stato preparato.  
2. Nel riquadro azioni, fare clic su Produzione.
3. Fare clic su Ripristina stato.
    * È possibile utilizzare una regola kanban alternativa se vengono soddisfatte le seguenti condizioni: - La strategia di rifornimento è uguale per entrambe le regole.  - La versione del flusso di produzione è uguale per entrambe le regole.  - Il prodotto che viene fornito è uguale per entrambe le regole.  - Tutte le attività downstream configurate per l'ultima attività delle regole kanban devono essere uguali per entrambe le regole.  - Le stesse dimensioni inventariali fornite devono essere configurate per entrambe le regole.  - Lo stato dell'unità movimentazione deve essere Non assegnato.  - La configurazione per i kanban evento deve essere uguale.  
    * Assicurarsi che il nuovo stato sia Pianificato.  
4. Fare clic su OK.
5. Nell'elenco deselezionare la riga selezionata.
    * Selezionare lo stesso processo.  
    * Si noti che lo stato del processo kanban viene reimpostato su Pianificato, indicato da un'icona kanban vuota.  

