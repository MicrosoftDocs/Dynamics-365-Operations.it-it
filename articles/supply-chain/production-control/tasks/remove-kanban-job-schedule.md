--- 
title: Rimuovere un processo kanban dalla programmazione
description: Questa procedura riguarda la rimozione di un processo kanban di lavorazione pianificato dalla programmazione ripristinando lo stato del processo su Non pianificato.
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
ms.openlocfilehash: 9a0f246bfe42dde0befdf5c4f01d2ad1e1200b12
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Rimuovere un processo kanban dalla programmazione

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

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


