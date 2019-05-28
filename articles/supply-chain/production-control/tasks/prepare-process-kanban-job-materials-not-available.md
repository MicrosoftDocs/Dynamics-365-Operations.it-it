---
title: Preparare un processo kanban quando non sono disponibili materiali per la cella di lavoro
description: Questa procedura riguarda la preparazione del processo kanban di lavorazione quando alcuni materiali non sono disponibili per la cella di lavoro ed è pertanto necessario prelevarvi dal magazzino.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7e7eb46bda13ef7e72189f921686a9889a8773c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559073"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>Preparare un processo kanban quando non sono disponibili materiali per la cella di lavoro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura riguarda la preparazione del processo kanban di lavorazione quando alcuni materiali non sono disponibili per la cella di lavoro ed è pertanto necessario prelevarvi dal magazzino. La procedura Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro" è un prerequisito per creare questa procedura. Questa procedura è destinata all'operatore. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a Controllo produzione > Kanban > Bacheca kanban per i processi di lavorazione.
2. Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare la cella di lavoro 1250.  
4. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare Kanban 000356  
5. Nell'elenco trovare e selezionare il record desiderato.
    * Nell'elenco deselezionare la riga 4. Selezionarla se non è stata completata l'attività "Preparare un processo kanban quando sono disponibili materiali".  
6. Attivare/disattivare l'espansione della sezione Distinta di prelievo.
    * L'icona che indica nessuna voce nello stato fornitura mostra che 48 unità dell'articolo P0002 sono mancanti per la cella di lavoro.  

## <a name="transfer-materials-to-work-cell"></a>Trasferire materiali nella cella di lavoro
1. Attivare/disattivare l'espansione della sezione Processi di trasferimento.
2. Utilizzare il filtro rapido per filtrare il campo Numero articolo in base al valore "P0002".
3. Nell'elenco trovare e selezionare il record desiderato.
4. Fare clic su Inizia.
    * Trasferimento in corso.  
5. Fare clic su Completa.
    * L'articolo P0002 ora è disponibile nella distinta di prelievo per il processo kanban. Ciò significa che è possibile preparare il processo kanban con tutti i materiali necessari.  
6. Fare clic su Prepara.
    * Si noti che un'icona nello stato del processo indica che il processo ora è pronto.  

