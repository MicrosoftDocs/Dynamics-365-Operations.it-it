---
title: Aggiornare lo stato del processo kanban
description: Quando un kanban viene svuotato per errore o un kanban ricevuto deve essere svuotato, è necessario aggiornare lo stato del kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a0e03da4671ffec4ecf4835b20a00ef87971c94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831819"
---
# <a name="update-kanban-status"></a>Aggiornare lo stato del processo kanban

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]