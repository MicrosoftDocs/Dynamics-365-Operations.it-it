---
title: Differenze tra la pianificazione generale integrata e l'ottimizzazione della pianificazione
description: Questo argomento elenca le caratteristiche che Planning Optimization non supporta ancora e che non sono elencate nella pagina di analisi dell'adattamento di Planning Optimization.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a102f1d77362f650c060ce5d0aee5b62d2102532
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344956"
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
| Sequenze di numeri per ordini pianificati | Le sequenze di numeri per gli ordini pianificati non sono supportate. I numeri d'ordine pianificati sono generati sul lato servizio. |
| Copia del piano, cancellazione del piano e pulizia della versione del piano | <p>I seguenti elementi sono disabilitati sotto **Pianificazione principale \> Pianificazione principale \> Mantenere i piani** nel pannello di navigazione:</p><ul><li>Copia del piano</li><li>Elimina piano</li><li>Pulitura versione piano</li></ul> |
| Ordini di reso | Gli ordini di ritorno non sono considerati. |
| Caratteristiche relative alla programmazione | Per i dettagli, vedere [Programmazione con capacità infinita](infinite-capacity-planning.md#limitations). |
| Calendari di trasporto | Il valore nella colonna **Calendario di trasporto** nella pagina **Modalità di consegna** è ignorato. |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Analisi corrispondenza Ottimizzazione pianificazione](planning-optimization-fit-analysis.md)
- [Parametri non utilizzati da Ottimizzazione pianificazione](not-used-parameters.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
