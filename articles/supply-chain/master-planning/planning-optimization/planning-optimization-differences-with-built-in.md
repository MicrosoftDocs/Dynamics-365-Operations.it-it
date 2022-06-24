---
title: Differenze tra la pianificazione generale integrata e l'ottimizzazione della pianificazione
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
ms.openlocfilehash: cf39166dce860dbd796cb4749175628252ed96ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897576"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>Differenze tra la pianificazione generale integrata e l'ottimizzazione della pianificazione

[!include [banner](../../includes/banner.md)]

I risultati di Planning Optimization potrebbero differire dai risultati del motore di pianificazione principale incorporato. Le differenze possono essere causate da caratteristiche pendenti. Questo articolo elenca le caratteristiche che Planning Optimization non supporta ancora e che non sono elencate nella **[Analisi dell'adattamento di Planning Optimization](planning-optimization-fit-analysis.md)** pagina].

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
| Codice di copertura minimo/massimo senza valori| Con il motore di pianificazione integrato, quando usi un codice di copertura min/max in cui nessun valore minimo o massimo è impostato, il motore di pianificazione tratta il codice di copertura come requisito e crea un ordine per ciascun requisito. Con Ottimizzazione pianificazione, il sistema creerà un ordine per giorno per coprire l'importo completo di tale giorno.  |
| Fabbisogno netto e ordini pianificati creati manualmente | Con il motore di pianificazione integrato, gli ordini di fornitura creati manualmente per un articolo vengono visualizzati automaticamente tra i fabbisogni netti dell'articolo. Ad esempio, quando si crea un ordine fornitore da un ordine cliente, l'ordine fornitore viene visualizzato nella pagina **Fabbisogno netto** senza richiedere alcuna azione preventiva. Ciò avviene perché il motore di pianificazione integrato registra le transazioni di magazzino nella tabella `inventLogTTS` e mostra le modifiche nella pagina **Fabbisogno netto** per i piani dinamici. Tuttavia, con Ottimizzazione pianificazione, gli ordini creati manualmente non verranno visualizzati tra i fabbisogni netti di un articolo finché non viene eseguita l'Ottimizzazione pianificazione (utilizzando un piano che include l'articolo) o finché non si seleziona **Aggiorna \> Pianificazione principale** nel riquadro azioni della pagina **Fabbisogno netto** che eseguirà la pianificazione generale per l'articolo. Per ulteriori informazioni su come lavorare con la pagina **Fabbisogni netti**, vedi [Fabbisogni netti e informazioni di pegging con Ottimizzazione pianificazione](net-requirements.md). |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Analisi corrispondenza Ottimizzazione pianificazione](planning-optimization-fit-analysis.md)
- [Parametri non utilizzati da Ottimizzazione pianificazione](not-used-parameters.md)
- [Parametri di data e ora utilizzati da Ottimizzazione pianificazione](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
