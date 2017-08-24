--- 
title: Modificare regole kanban di un processo di lavorazione
description: La procedura consente di modificare la regola kanban utilizzata per un kanban specifico.
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: e8355a94322e6489fe64f22a049a34b7ecfe65b9
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="change-kanban-rules-for-a-process-job"></a>Modificare regole kanban di un processo di lavorazione

[!include[task guide banner](../../includes/task-guide-banner.md)]

La procedura consente di modificare la regola kanban utilizzata per un kanban specifico. Ciò è utile per livellare le risorse di carico o in caso di scomposizione. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al responsabile pianificazione che lavora presso una società di produzione snella, responsabile del flusso del valore.


## <a name="copy-kanban-rule"></a>Copiare la regola kanban
1. Passare a Regole kanban.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la regola kanban di evento 000022 per L0001.  
3. Fare clic su Duplica regola kanban.
4. Fare clic su OK.

## <a name="change-kanban-rule"></a>Modificare la regola kanban
1. Chiudere la pagina.
2. Passare a Programmazione processo kanban.
3. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare la riga con il kanban 000177.  
4. Fare clic su Utilizza regola kanban alternativa.
5. Scegliere Avanti.
6. Nel campo Regola kanban immettere o selezionare un valore.
    * Selezionare la regola kanban creata in precedenza. Si tratta della regola kanban con il numero più elevato.  
7. Scegliere Fine.
    * A questo punto il processo kanban utilizza un'altra regola kanban. Può essere utile per livellare il carico delle celle di lavoro.  


