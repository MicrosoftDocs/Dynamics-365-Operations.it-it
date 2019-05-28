---
title: Trasferire materiali con processi kanban
description: Questa procedura riguarda l'esecuzione del processo kanban di prelievo per trasferire i materiali.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2db7b9fb960beb5b4a851aabb9f28a0f9e3d3da
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571452"
---
# <a name="transfer-materials-with-kanban-jobs"></a>Trasferire materiali con processi kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura riguarda l'esecuzione del processo kanban di prelievo per trasferire i materiali. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata all'addetto al magazzino.


## <a name="display-transfer-jobs"></a>Visualizza processi di trasferimento
1. Andare a Controllo produzione > Kanban > Bacheca kanban per processi di trasferimento.
2. Espandere o comprimere la sezione Filtri.
    * Nella sezione Filtri è possibile specificare i processi che si desidera visualizzare filtrando per flusso di produzione, nome dell'attività, il magazzino e ubicazione di origine e magazzino e ubicazione di destinazione.  
3. Nel campo Magazzino origine digitare "11".
4. Nel campo Ubicazione destinazione digitare "12".

## <a name="start-a-transfer-job"></a>Avvia un processo di trasferimento
1. Nell'elenco deselezionare la riga selezionata, se presente.
2. Nell'elenco selezionare la riga 4.
    * Selezionare il primo processo con lo stato Non pianificato. Assicurarsi che questo sia l'unico processo selezionato.  
3. Fare clic su Inizia.
    * Si noti che un'icona indica che il processo è avviato.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>Selezionare un secondo processo di trasferimento e modificare la quantità
1. Nell'elenco trovare e selezionare il record desiderato.
    * È possibile selezionare più processi, ma per adesso selezionare solo la riga 5.  
2. Nell'elenco trovare e selezionare il record desiderato.
    * Verificare che il processo nel passaggio precedente sia l'unico selezionato. Deselezionare tutti gli altri processi.  
3. Annotare il valore nel campo Quantità processo per farvi riferimento in seguito
4. Impostare la quantità processo su "30".
    * Si noti l'avviso. Non è possibile trasferire una quantità pari a 30. In base all'impostazione della regola kanban, è possibile trasferire solo la quantità originale.  
5. Utilizzare il valore annotato in precedenza nel campo Quantità processo
    * Impostare la quantità del processo sul valore precedente.  

## <a name="start-the-second-transfer-job"></a>Avviare il secondo processo di trasferimento
1. Fare clic su Inizia.
    * Verrà iniziato il trasferimento del processo nella riga. 5.  

## <a name="complete-both-transfer-jobs"></a>Completare entrambi i processi di trasferimento
1. Nell'elenco selezionare la riga 4.
    * Ora due processi di trasferimento sono selezionati nella riga 4 e nella riga. 5.  
2. Fare clic su Completa.
    * In questo modo verrà completato il trasferimento di entrambi i processi.  

