---
title: Creare una programmazione per un sito
description: Questa procedura mostra come programmare gli ordini di produzione non ancora iniziati per un sito.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146531217f7f596a5cb98e271b0356ffeb3d5547
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567249"
---
# <a name="create-a-schedule-for-a-site"></a>Creare una programmazione per un sito

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]