---
title: Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro
description: Questa attività riguarda la preparazione di un processo kanban di lavorazione quando tutti i materiali sono disponibili per la cella di lavoro.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a12773cc6d94a34197084c8fe12c90167d4dca62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977765"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a>Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]