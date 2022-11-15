---
title: Differenze tra Ottimizzazione pianificazione e il motore di pianificazione generale deprecato
description: Questo articolo elenca le caratteristiche che Planning Optimization non supporta ancora e che non sono elencate nella pagina di analisi dell'adattamento di Planning Optimization.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6e1671a508b85a94ac9687af15e898d885ea94c1
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745363"
---
# <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Differenze tra Ottimizzazione pianificazione e il motore di pianificazione generale deprecato

[!include [banner](../../includes/banner.md)]

I risultati di Planning Optimization potrebbero differire dai risultati del motore di pianificazione principale deprecato. Le differenze possono essere causate da caratteristiche pendenti. Questo articolo elenca le caratteristiche che Planning Optimization non supporta ancora e che non sono elencate nella **[Analisi dell'adattamento di Planning Optimization](planning-optimization-fit-analysis.md)** pagina].

| Funzionalità | Comportamento attuale nell'ottimizzazione della pianificazione |
|---|---|
| Prodotti di peso di cattura | I prodotti a peso di cattura sono considerati prodotti usuali.|
| Dimensioni estensibili | Le dimensioni estensibili non sono supportate da Ottimizzazione pianificazione. Quando usi Ottimizzazione pianificazione, le dimensioni estensibili sono vuote sugli ordini pianificati, anche quando la casella di controllo **Piano di copertura per dimensione** è selezionata nella pagina **Gruppi di dimensioni di stoccaggio** o **Gruppi di dimensioni di monitoraggio** . |
| Corse di produzione filtrate | Per i dettagli, vedere [Pianificazione della produzione - Filtri](production-planning.md#filters). |
| Pianificazione previsionale | La pianificazione delle previsioni non è supportata. Si consiglia di utilizzare la pianificazione principale in cui un modello di previsione è assegnato al piano principale. |
| Sequenze di numeri per ordini pianificati | Le sequenze di numeri per gli ordini pianificati non sono supportate. I numeri d'ordine pianificati sono generati sul lato servizio. Il numero dell'ordine pianificato viene normalmente visualizzato con 10 cifre, ma la sequenza è in realtà costituita da 20 caratteri, con 10 cifre allocate per il conteggio dell'esecuzione della pianificazione e le altre 10 cifre per il conteggio degli ordini pianificati. |
| Copia del piano, cancellazione del piano e pulizia della versione del piano | <p>I seguenti elementi sono disabilitati sotto **Pianificazione principale \> Pianificazione principale \> Mantenere i piani** nel pannello di navigazione:</p><ul><li>Copia del piano</li><li>Elimina piano</li><li>Pulitura versione piano</li></ul> |
| Ordini di reso | Gli ordini di ritorno non sono considerati. |
| Caratteristiche relative alla programmazione | Per i dettagli, vedere [Programmazione con capacità infinita](infinite-capacity-planning.md#limitations). |
| Garanzia scorte di sicurezza | Ottimizzazione pianificazione utilizza sempre l'opzione *Data odierna + tempo di approvvigionamento* per il campo **Soddisfa minimo** della pagina **Copertura articolo**. Consente di impedire ordini pianificati indesiderati e altri problemi perché se il tempo di approvvigionamento non è incluso per la scorta di sicurezza, gli ordini pianificati creati per le scorte a disponibilità ridotta saranno sempre posticipati a causa dei tempi di consegna. |
| Pegging delle scorte di sicurezza e fabbisogni netti | Il tipo di requisito *Scorta di sicurezza* non è incluso e non viene visualizzato nella pagina **fabbisogni netti**. Le scorte di sicurezza non rappresentano la domanda e non sono associate a una data di fabbisogno. Imposta invece un vincolo sulla quantità di scorte che deve essere sempre presente. In ogni caso, il valore del campo **Minimo** viene ancora preso in considerazione durante il calcolo degli ordini pianificati durante la pianificazione generale. Ti consigliamo di ispezionare la colonna **Quantità accumulata** nella pagina **fabbisogni netti** per controllare che questo valore sia stato considerato. Poiché il pegging è diverso, possono essere suggerite diverse azioni. |
| Calendari di trasporto | Il valore nella colonna **Calendario di trasporto** nella pagina **Modalità di consegna** è ignorato. |
| Codice di copertura minimo/massimo senza valori| Con il motore di pianificazione generale deprecato, quando usi un codice di copertura min/max in cui nessun valore minimo o massimo è impostato, il motore di pianificazione tratta il codice di copertura come requisito e crea un ordine per ciascun requisito. Con Ottimizzazione pianificazione, il sistema creerà un ordine per giorno per coprire l'importo completo di tale giorno.  |
| Fabbisogno netto e ordini pianificati creati manualmente | Con il motore di pianificazione generale deprecato, gli ordini di fornitura creati manualmente per un articolo vengono visualizzati automaticamente tra i fabbisogni netti dell'articolo. Ad esempio, quando si crea un ordine fornitore da un ordine cliente, l'ordine fornitore viene visualizzato nella pagina **Fabbisogno netto** senza richiedere alcuna azione preventiva. Ciò avviene perché il motore di pianificazione generale deprecato registra le transazioni di magazzino nella tabella `inventLogTTS` e mostra le modifiche nella pagina **Fabbisogno netto** per i piani dinamici. Tuttavia, con Ottimizzazione pianificazione, gli ordini creati manualmente non verranno visualizzati tra i fabbisogni netti di un articolo finché non viene eseguita l'Ottimizzazione pianificazione (utilizzando un piano che include l'articolo) o finché non si seleziona **Aggiorna \> Pianificazione principale** nel riquadro azioni della pagina **Fabbisogno netto** che eseguirà la pianificazione generale per l'articolo. Per ulteriori informazioni su come lavorare con la pagina **Fabbisogni netti**, vedi [Fabbisogni netti e informazioni di pegging](net-requirements.md). |
| Assegnazione di risorsa | Quando si lavora con capacità infinita, il motore di pianificazione generale deprecato assegna tutti gli ordini pianificati alla stessa risorsa in un determinato gruppo di risorse. Ottimizzazione pianificazione migliora questo aspetto selezionando le risorse in modo casuale in modo che ordini di produzione diversi possano utilizzare risorse diverse. Se desideri utilizzare la stessa risorsa per tutti gli ordini pianificati, devi specificare tale risorsa nel ciclo. |
| Extended data types (EDT) | Ottimizzazione pianificazione non supporta le modifiche alla precisione degli EDT. Ciò significa che questo processo non è ufficialmente supportato e non è garantito che funzioni. |
| Garanzia scorte di sicurezza | L'ottimizzazione della pianificazione utilizza sempre un **Soddisfa minimo** di *Data odierna + tempo di approvvigionamento*. Questo prepara il sistema a utilizzare una configurazione di pianificazione semplificata in futuro e fornisce un risultato utile. Se il tempo di approvvigionamento non è incluso per la scorta di sicurezza, gli ordini pianificati creati per le scorte a disponibilità ridotta saranno sempre posticipati a causa dei tempi di consegna. Questo comportamento può causare disturbi significativi e ordini pianificati indesiderati. Come procedura consigliata cambiare l'impostazione in modo da utilizzare *Data odierna + tempo di approvvigionamento*. Aggiorna i dati master per evitare avvisi. |
| Copia piano statico in piano dinamico | L'ottimizzazione della pianificazione non copia i piani statici nei piani dinamici, indipendentemente dall'impostazione della pagina **Parametri di pianificazione generale**. In generale, questa operazione è meno rilevante a causa della velocità e della rigenerazione completa fornita dall'ottimizzazione della pianificazione. Se vengono utilizzati due o più piani, è necessario attivare la pianificazione generale per ciascun piano. |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Analisi corrispondenza Ottimizzazione pianificazione](planning-optimization-fit-analysis.md)
- [Parametri non utilizzati da Ottimizzazione pianificazione](not-used-parameters.md)
- [Parametri di data e ora utilizzati da Ottimizzazione pianificazione](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
