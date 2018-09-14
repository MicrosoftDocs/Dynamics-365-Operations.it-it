--- 
title: Programmare un ordine di produzione con programmazione di operazioni e processi
description: Questa procedura si concentra sulla programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d4aac437876862e9f776264fc81f246c820bdf45
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Programmare un ordine di produzione con programmazione di operazioni e processi

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura si concentra sulla programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi. Nessun processo viene creato con la programmazione delle operazioni, mentre i processi vengono creati con la programmazione dei processi. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa procedura è destinata al responsabile di produzione, al responsabile della pianificazione della produzione o al supervisore di reparto in un ambiente di produzione discreta.


## <a name="create-a-production-order"></a>Creare un ordine di produzione
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
2. Fare clic su Nuovo ordine di produzione.
3. Nel campo Numero di articoli immettere o selezionare un valore.
    * Selezionare il numero articolo D0001.  
4. Fare clic su Crea.

## <a name="schedule-operations-for-the-production-order"></a>Programmare operazioni per l'ordine di produzione
1. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare l'ordine di produzione appena creato. Dovrebbe essere nella parte superiore dell'elenco.      
2. Nel riquadro azioni fare clic su Programmazione.
3. Fare clic su Programma operazioni.
4. Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.
5. Immettere una data nel campo Data di programmazione.
    * Selezionare una data futura, ad esempio, oggi più una settimana. Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.  
6. Fare clic su OK.
7. Nell'elenco contrassegnare la riga selezionata.
    * Notare che lo stato viene modificato in Programmato.  
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Fare clic su Tutti i processi.
    * Si noti che nessun processo viene creato con la programmazione delle operazioni.  
10. Chiudere la pagina.

## <a name="schedule-jobs-for-the-production-order"></a>Programmare processi per l'ordine di produzione
1. Nel riquadro azioni fare clic su Programmazione.
2. Fare clic su Programma processi.
3. Nel campo Direzione programmazione, selezionare 'Avanti da data programmazione'.
4. Immettere una data nel campo Data di programmazione.
    * Selezionare una data futura, ad esempio, oggi più una settimana. Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.  
5. Fare clic su OK.
6. Nel riquadro azioni fare clic su Ordine di produzione.
7. Fare clic su Tutti i processi.
    * Si noti che in base al ciclo di lavorazione attivo, 5 processi vengono creati con la programmazione dei processi.  


