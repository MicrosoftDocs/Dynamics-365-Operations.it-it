--- 
title: Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro
description: "Questa attività riguarda la preparazione di un processo kanban di lavorazione quando tutti i materiali sono disponibili per la cella di lavoro."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 4c52a2f226b079b404eab53e01b3025647633d04
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a>Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa attività riguarda la preparazione di un processo kanban di lavorazione quando tutti i materiali sono disponibili per la cella di lavoro. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa attività è destinata all'operatore.

1. Andare a Bacheca kanban per i processi lavorazione.
2. Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare la cella di lavoro 1250 e fare clic su OK.  
4. Nell'elenco selezionare la riga 4.
    * Nella società dimostrativa senza dati, il processo kanban 000329 nella riga 4 è il primo processo non ancora completato.  
5. Attivare/disattivare l'espansione della sezione Distinta di prelievo.
    * Verificare che lo stato della fornitura sia disponibile per tutti gli articoli nella distinta di prelievo.  
    * Se più processi vengono selezionati, la distinta di prelievo indicherà somma di tutti gli articoli necessari per i processi selezionati.  
6. Fare clic su Prepara.
    * Il processo di preparazione è ora completato. La casella di controllo selezionata per tutte le righe della distinta di prelievo indica che lo stato della fornitura è Prelevato.  

