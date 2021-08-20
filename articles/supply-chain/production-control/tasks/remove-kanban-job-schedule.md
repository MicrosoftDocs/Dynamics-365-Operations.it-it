---
title: Rimuovere un processo kanban dalla programmazione
description: Questa procedura riguarda la rimozione di un processo kanban di lavorazione pianificato dalla programmazione ripristinando lo stato del processo su Non pianificato.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eeedfad5f294f73097fc1b6a973d63125df72209227fc06470663665961af2d4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756921"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Rimuovere un processo kanban dalla programmazione

[!include [banner](../../includes/banner.md)]

Questa procedura riguarda la rimozione di un processo kanban di lavorazione pianificato dalla programmazione ripristinando lo stato del processo su Non pianificato. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La procedura è destinata al supervisore dello shop floor o al responsabile di pianificazione della produzione.


## <a name="find-a-planned-kanban-job"></a>Trovare un processo kanban pianificato
1. Andare a Controllo produzione > Kanban > Programmazione processo kanban.
2. Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare la cella di lavoro 1250.  
4. Fare clic su Seleziona.
5. Nel campo Visualizza stato processo selezionare "Programmato".

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>Rimuovere il processo kanban pianificato dalla programmazione
1. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare un processo con stato Pianificato, ad esempio un processo del 19 dicembre 2012.  
2. Nel riquadro azioni fare clic su Piano.
3. Fare clic su Ripristina stato del processo.
4. Fare clic su OK.
    * In questo modo lo stato del processo corrente verrà ripristinato da Pianificato a Non pianificato e il processo verrà rimosso dalla bacheca dei processi.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]