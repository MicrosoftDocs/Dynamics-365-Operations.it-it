---
title: Differenze tra la pianificazione generale integrata e l'ottimizzazione della pianificazione
description: Questo argomento elenca le caratteristiche che Planning Optimization non supporta ancora e che non sono elencate nella pagina di analisi dell'adattamento di Planning Optimization.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: e271ddd3331d7b5de78f00a02b60a0479879c172
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700007"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>Differenze tra la pianificazione generale integrata e l'ottimizzazione della pianificazione

[!include [banner](../../includes/banner.md)]

I risultati di Planning Optimization potrebbero differire dai risultati del motore di pianificazione principale incorporato. Le differenze possono essere causate da caratteristiche pendenti. Questo argomento elenca le caratteristiche che Planning Optimization non supporta ancora e che non sono elencate nella **[Analisi dell'adattamento di Planning Optimization](planning-optimization-fit-analysis.md)** pagina].

| Funzionalità | Comportamento attuale nell'ottimizzazione della pianificazione |
|---|---|
| Prodotti di peso di cattura | I prodotti a peso di cattura sono considerati prodotti usuali.|
| Dimensioni estensibili | Le dimensioni estensibili sono vuote sugli ordini pianificati, anche quando la casella di controllo **Piano di copertura per dimensione** è selezionata nella pagina **Gruppi di dimensioni di stoccaggio** o **Gruppi di dimensioni di monitoraggio** . |
| Corse di produzione filtrate | Per i dettagli, vedere [Pianificazione della produzione - Filtri](production-planning.md#filters). |
| Pianificazione previsionale | La pianificazione delle previsioni non è supportata. Si consiglia di utilizzare la pianificazione principale in cui un modello di previsione è assegnato al piano principale. |
| Sequenze di numeri per ordini pianificati | Le sequenze di numeri per gli ordini pianificati non sono supportate. I numeri d'ordine pianificati sono generati sul lato servizio. Il numero dell'ordine pianificato viene normalmente visualizzato con 10 cifre, ma la sequenza è in realtà costituita da 20 caratteri, con 10 cifre allocate per il conteggio dell'esecuzione della pianificazione e le altre 10 cifre per il conteggio degli ordini pianificati. |
| Copia del piano, cancellazione del piano e pulizia della versione del piano | <p>I seguenti elementi sono disabilitati sotto **Pianificazione principale \> Pianificazione principale \> Mantenere i piani** nel pannello di navigazione:</p><ul><li>Copia del piano</li><li>Elimina piano</li><li>Pulitura versione piano</li></ul> |
| Ordini di reso | Gli ordini di ritorno non sono considerati. |
| Caratteristiche relative alla programmazione | Per i dettagli, vedere [Programmazione con capacità infinita](infinite-capacity-planning.md#limitations). |
| Garanzia scorte di sicurezza | Ottimizzazione pianificazione utilizza sempre l'opzione *Data odierna + tempo di approvvigionamento* per il campo **Soddisfa minimo** della pagina **Copertura articolo**. Consente di impedire ordini pianificati indesiderati e altri problemi perché se il tempo di approvvigionamento non è incluso per la scorta di sicurezza, gli ordini pianificati creati per le scorte a disponibilità ridotta saranno sempre posticipati a causa dei tempi di consegna. |
| Pegging delle scorte di sicurezza e fabbisogni netti | Il tipo di requisito *Scorta di sicurezza* non è incluso e non viene visualizzato nella pagina **fabbisogni netti**. Le scorte di sicurezza non rappresentano la domanda e non sono associate a una data di fabbisogno. Imposta invece un vincolo sulla quantità di scorte che deve essere sempre presente. In ogni caso, il valore del campo **Minimo** viene ancora preso in considerazione durante il calcolo degli ordini pianificati durante la pianificazione generale. Ti consigliamo di ispezionare la colonna **Quantità accumulata** nella pagina **fabbisogni netti** per controllare che questo valore sia stato considerato. |
| Calendari di trasporto | Il valore nella colonna **Calendario di trasporto** nella pagina **Modalità di consegna** è ignorato. |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Analisi corrispondenza Ottimizzazione pianificazione](planning-optimization-fit-analysis.md)
- [Parametri non utilizzati da Ottimizzazione pianificazione](not-used-parameters.md)
- [Parametri di data e ora utilizzati da Ottimizzazione pianificazione](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
