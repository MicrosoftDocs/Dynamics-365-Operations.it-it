--- 
title: Eseguire processi di lavorazione kanban
description: Questa procedura illustra come eseguire i processi di lavorazione kanban.
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
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 752eab976f740606154d416678ba2381641697df
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="execute-kanban-process-jobs"></a>Eseguire processi di lavorazione kanban

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura illustra come eseguire i processi di lavorazione kanban. Il primo processo è stato completato con la quantità prevista e non presenta errori. Il secondo lavoro è stato completato con errori. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata all'operatore.


## <a name="select-a-kanban-job"></a>Selezionare un processo kanban
1. Andare a Controllo produzione > Kanban > Bacheca kanban per i processi di lavorazione.
2. Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.
3. Fare clic sulla riga con il gruppo di risorse 1250. In questo modo verrà filtrato l'elenco dei processi per mostrare solo i processi per la cella di lavoro 1250.
    * Contrassegnare la riga con stato del processo pianificato.  

## <a name="complete-a-job-with-expected-quantity"></a>Completare un processo con la quantità prevista
1. Espandere o comprimere la sezione Dettagli.
    * In questa sezione vengono visualizzate le informazioni principali sul numero di carta, il numero di articolo, la quantità ordinata e il nome dell'attività.  
2. Espandere o comprimere la sezione Istruzioni produzione.
    * In questa sezione vengono visualizzate le istruzioni di produzione per l'attività. Le istruzioni possono essere testo, immagini, disegni e altri documenti.  
3. Fare clic su Inizia.
    * Selezionare un processo che non è stato completato. Utilizzare le icone di stato nel campo Stato del processo per visualizzare lo stato del processo.      
4. Fare clic su Completa.
    * Il processo è stato completato con la qualità prevista.  

## <a name="complete-a-job-with-errors"></a>Completare un processo con errori
1. Fare clic su Inizia.
    * Quando un processo è completato, il processo successivo nell'elenco viene selezionato automaticamente. Per questo motivo non è necessario selezionare un processo prima di fare clic su Start.  
2. Nel riquadro azioni, fare clic su Produzione.
3. Fare clic su Completa (dettagli).
4. Nell'elenco contrassegnare la riga selezionata.
5. Nel campo Quantità difettosa immettere un numero.
6. Nel campo Quantità idonea immettere un numero.
7. Fare clic su OK.


