---
title: Definire i modelli di flusso di produzione
description: I modelli di flusso di produzione descrivono come la capacità delle celle di lavoro di produzione snella viene calcolata e gestita.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlowModel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8267b18ea85b7a6ba7a1333b586f36ea8b6e8e30
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257221"
---
# <a name="define-production-flow-models"></a>Definire i modelli di flusso di produzione

[!include [banner](../../includes/banner.md)]

I modelli di flusso di produzione descrivono come la capacità delle celle di lavoro di produzione snella viene calcolata e gestita. Pertanto la definizione di un modello di flusso di produzione è un prerequisito della definizione delle celle di lavoro. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="define-a-production-flow-model"></a>Definire un modello di flusso di produzione. 
1. Passare a Controllo produzione > Impostazione > Flusso di produzione snella > Modelli di flusso di produzione.
2. Fare clic su Nuovo.
3. Nel campo Modello di flusso di produzione, immettere un ID per il modello di flusso di produzione.
4. Nel campo Tipo di modello selezionare un'opzione.
    * Sono disponibili due tipi di modello: il tipo Produttività e il tipo Ore. Per il tipo Produttività, la capacità delle celle di lavoro che utilizzano questo modello di flusso di produzione verrà calcolata e espressa in quantità di prodotto. Per il tipo Ore, la capacità delle celle di lavoro che utilizzano questo modello di flusso di produzione verrà calcolata e espressa in ore. Si noti che la proprietà non può essere modificata per un modello di flusso di produzione esistente. Dopo che una cella di lavoro dispone di prenotazioni di capacità, il tipo di modello di flusso di produzione non può essere modificato.  
5. Immettere il numero di giorni nel campo Ciclo EPE.
    * L'intervallo descrive il periodo in cui ogni parte prodotta da un flusso di produzione o da una cella di lavoro verrà prodotta almeno una volta. Più breve è il ciclo EPE, più flessibile è il processo di produzione. Se Ciclo EPE = 0, qualsiasi richiesta può essere prodotta nello stesso giorno. Il ciclo EPE viene utilizzato per la programmazione dei processi di lavorazione di produzione snella. Nella programmazione di un processo per una cella di lavoro con il ciclo EPE = 5, il processo di programmazione cerca la capacità della cella di lavoro alla data di scadenza del ciclo EPE (5 giorni prima della data di scadenza) per verificare che il prodotto possa essere prodotto in quel ciclo. Il lead time di magazzino di un prodotto è in genere uguale o maggiore del ciclo EPE del processo di produzione correlato.  
6. Nel campo Tipo di pianificazione del periodo selezionare un'opzione.
    * Dopo che una cella di lavoro dispone di prenotazioni di capacità, il tipo di periodo di pianificazione non può essere modificato. È possibile selezionare solo i modelli di flusso di produzione con lo stesso tipo di periodo di questa cella di lavoro specifica.  
7. Nel campo Intervallo temporale pianificazione immettere un numero.
    * L'intervallo temporale di pianificazione descrive il numero di giorni in cui le prenotazioni di capacità possono essere effettuate per le celle di lavoro correlate. Nell'intervallo temporale di pianificazione, immettere il numero di giorni.   I processi di lavorazione kanban che non rientrano in questo periodo non vengono pianificati con la pianificazione automatica. L'intervallo temporale di pianificazione è in genere il doppio del lead time di magazzino medio dei prodotti creati in un flusso di produzione o una cella di lavoro. Il ciclo EPE non deve essere maggiore della metà dell'intervallo temporale di pianificazione.     
8. Selezionare un'opzione nel campo Reazione alla carenza di capacità.
    * Le opzioni sono: Posticipa, per posticipare la domanda completa dell'evento di programmazione al successivo giorno di produzione disponibile con produttività disponibile. Annulla, per terminare la pianificazione automatica per l'evento di programmazione e lascia i processi correlati non pianificati.   Aggiungi al giorno richiesto, per pianificare i processi necessari per il periodo richiesto. Ciò determina un overload della cella per questo giorno e richiede al responsabile della pianificazione di rivedere e interagire manualmente.   Distribuire i diversi processi di evento di programmazione a tutti i giorni di produzione disponibili, a partire dal primo giorno disponibile. La quantità di distribuzione minima è la quantità del processo kanban. La distribuzione assegna la quantità di pianificazione minima (quantità kanban) per ogni giorno con sufficiente produttività disponibile.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]