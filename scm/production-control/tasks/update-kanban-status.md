--- 
title: Aggiornare lo stato del processo kanban
description: "Quando un kanban viene svuotato per errore o un kanban ricevuto deve essere svuotato, è necessario aggiornare lo stato del kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: caf7dead2da14e1ff76e205e7477b1eb11a2ca52
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="update-kanban-status"></a>Aggiornare lo stato del processo kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Quando un kanban viene svuotato per errore o un kanban ricevuto deve essere svuotato, è necessario aggiornare lo stato del kanban. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al supervisore.


## <a name="find-the-kanban"></a>Individuare il kanban.
1. Andare a Controllo produzione > Kanban > Kanban.
2. Aprire il filtro della colonna Stato unità movimentazione.
3. Fare clic su Cancella.
    * Vengono reimpostati i filtri.  
4. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Numero carta in base a un valore "000149".

## <a name="change-emptied-status-to-received-status"></a>Modificare da stato svuotato in stato ricevuto
1. Fare clic su Ripristina unità movimentazione vuota.
2. Fare clic su OK.
    * Lo stato dell'unità movimentazione è Ricevuto.  

## <a name="change-received-status-to-emptied-status"></a>Modificare da stato ricevuto in stato svuotato
1. Fare clic su Svuota kanban.
2. Nell'elenco contrassegnare la riga selezionata.
    * Lo stato dell'unità movimentazione è Svuotato.  


