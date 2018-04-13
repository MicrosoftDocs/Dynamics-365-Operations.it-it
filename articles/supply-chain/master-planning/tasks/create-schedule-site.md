--- 
title: Creare una programmazione per un sito
description: Questa procedura mostra come programmare gli ordini di produzione non ancora iniziati per un sito.
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 775428bf84a752c03c492e764fa9ed576ab64fb8
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-schedule-for-a-site"></a>Creare una programmazione per un sito

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come programmare gli ordini di produzione non ancora iniziati per un sito.  Per completare questa procedura viene utilizzata la società di dati dimostrativi USMF.


## <a name="identify-production-orders-that-are-not-started"></a>Individuare gli ordini di produzione non ancora avviati
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro nel campo Sito con un valore "1".
    * 1 rappresenta un sito in USMF. Se non si utilizza USMF, selezionare un sito della propria società.  
3. Aprire il filtro della colonna Stato.
4. Applicare un filtro nel campo "Stato", con un valore di "Programmato", utilizzando l'operatore "è esattamente".

## <a name="create-a-schedule"></a>Creare una programmazione
1. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
2. Nel riquadro azioni fare clic su Programmazione.
3. Fare clic su Programma processi.
4. Nel campo di direzione di programmazione, selezionare "Indietro da data di consegna".
5. Selezionare No nel campo Capacità limitata.
6. Selezionare No nel campo Materiale limitato.
7. Fare clic su OK.
    * Questa operazione potrebbe richiedere tempo.  

## <a name="view-the-result-of-scheduled-production-orders"></a>Visualizzare il risultato degli ordini di produzione programmati
1. Nell'elenco contrassegnare la riga selezionata.
    * È possibile contrassegnare qualsiasi riga.  
2. Nel riquadro azioni fare clic su Ordine di produzione.
3. Fare clic su Tutti i processi.
    * In questa pagina è possibile visualizzare l'elenco dei processi. Nella scheda di programmazione è possibile visualizzare la data di inizio e di fine di un processo.  
4. Fare clic su Materiali.
    * In questa pagina è possibile visualizzare il consumo stimato dei materiali per le operazioni presenti nell'ordine di produzione e le scorte correnti disponibili.  


