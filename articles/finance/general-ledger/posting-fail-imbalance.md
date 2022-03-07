---
title: Insuccesso della pubblicazione del giornale a causa dello squilibrio
description: Questo argomento spiega perché gli addebiti e gli accrediti potrebbero non essere bilanciati nelle transazioni dei buoni, così che le transazioni non possono essere registrate. L'argomento include anche i passi per risolvere il problema.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a59724ff698b6ad0e84b0642240da5f8953ab3d1
ms.sourcegitcommit: 9642494da87c0d237f9fcbe15df14315d9e88fa2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2021
ms.locfileid: "7385725"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Insuccesso della pubblicazione del giornale a causa dello squilibrio

[!include [banner](../includes/banner.md)]

Questo argomento spiega perché gli addebiti e gli accrediti potrebbero non essere bilanciati nelle transazioni dei buoni, così che le transazioni non possono essere registrate. L'argomento include anche i passi per risolvere il problema.

## <a name="symptom"></a>Sintomo

In alcuni casi, un diario non può essere pubblicato e viene mostrato il seguente messaggio: "Le transazioni su un voucher specifico non si equilibrano a partire da una certa data (valuta contabile: 0.01 - valuta di segnalazione: 0.06)." Perché il diario non può essere pubblicato?

## <a name="resolution"></a>Risoluzione

Durante la registrazione in Contabilità generale, ogni buono deve essere bilanciato nella valuta della transazione, nella valuta contabile e nella valuta di segnalazione, se queste valute sono definite nella pagina **di impostazione del Ledger** . (I buoni sono bilanciati quando il totale dei debiti è uguale al totale dei crediti)

In fondo alla pagina delle righe del giornale, i totali sono mostrati nella valuta contabile e nella valuta di segnalazione.  **Non** sono mostrati nella valuta della transazione per le transazioni in valuta estera. Inoltre, il messaggio di errore che gli utenti ricevono durante la simulazione o la registrazione mostra le differenze solo nella valuta contabile e nella valuta di segnalazione. Non li mostra nella valuta della transazione, perché un singolo buono può avere più di una valuta di transazione, e il giornale può includere buoni in diverse valute di transazione. Pertanto, è importante verificare che gli importi della valuta della transazione per ogni buono siano bilanciati.

### <a name="transaction-currency"></a>Valuta transazione

Durante la simulazione e la registrazione, il sistema verifica che ogni buono sia bilanciato nella valuta della transazione. Per ogni buono che viene inserito, ci possono essere una o più valute per la valuta della transazione. Per esempio, un buono inserito nel giornale generale potrebbe avere due valute di transazione quando il contante viene trasferito da un conto bancario che usa euro (EUR) a un conto bancario che usa dollari canadesi (CAD).

Se un buono ha solo una valuta di transazione, il totale degli addebiti deve essere uguale al totale degli accrediti per quel buono. I clienti hanno incontrato i seguenti scenari in cui la registrazione è fallita correttamente perché gli importi della valuta della transazione non erano bilanciati:

- Il totale dei debiti e il totale dei crediti **non** erano bilanciati nella valuta della transazione, ma erano bilanciati per la valuta contabile e la valuta di segnalazione. Un cliente ha dato per scontato che il buono sarebbe stato comunque inviato. Tuttavia, questa supposizione era sbagliata. **Gli importi in valuta della transazione su un buono devono sempre essere bilanciati quando tutte le righe del buono hanno la stessa valuta.**
- Il buono è stato importato attraverso Microsoft Excel, e l'utente pensava che gli importi della valuta della transazione fossero bilanciati. Nella cartella di lavoro Excel, gli importi importati erano impostati come valori **numerici** , non come valori di **valuta** . In questo scenario, gli importi numerici nella cartella di lavoro avevano più di due cifre decimali, e più di due cifre decimali sono state incluse quando gli importi sono stati importati. Pertanto, gli addebiti non erano uguali agli accrediti, perché erano fuori di una frazione di centesimo. Il giornale non rifletteva questa differenza sulle righe del buono, perché gli importi indicati hanno solo due cifre decimali.
- Il buono è stato importato tramite Excel, e l'utente pensava che gli importi della valuta della transazione fossero bilanciati. Anche se il buono era bilanciato, alcune righe del buono avevano date di transazione diverse. Se si sommano gli addebiti totali e gli accrediti totali per buono e data della transazione, non sono bilanciati. Il sistema ora impedisce questo scenario. Un buono può avere solo una data di transazione. Questo requisito viene applicato quando si inserisce un buono attraverso il giornale generale nel sistema. Tuttavia, non era originariamente applicato quando un buono veniva importato attraverso Excel.

In uno scenario supportato, un buono può avere più di una valuta di transazione. In questo caso, il sistema **non** verifica che gli addebiti siano uguali agli accrediti nella valuta della transazione, perché le valute non corrispondono. Invece, il sistema verifica che gli importi della valuta contabile siano bilanciati.

### <a name="accounting-currency"></a>Valuta di contabilizzazione

Se tutte le righe di un buono hanno la stessa valuta di transazione, e se gli importi della valuta di transazione sono bilanciati, il sistema verifica che gli importi della valuta contabile siano bilanciati. Se il buono è inserito in una valuta estera, il tasso di cambio sulle righe del buono è usato per tradurre gli importi della valuta della transazione nella valuta contabile. In primo luogo, ogni riga del buono viene tradotta. Poi le linee vengono sommate per determinare il totale dei debiti e il totale dei crediti. Poiché ogni riga è tradotta, il totale dei debiti e il totale dei crediti potrebbero non essere bilanciati. Tuttavia, se la differenza è all'interno del valore **massimo di differenza di penny** che è definito nella pagina dei **parametri della contabilità generale** , il buono sarà inviato, e la differenza sarà automaticamente inviata al conto differenza di penny.

Se il buono ha più di una valuta di transazione, ogni riga del buono viene tradotta nella valuta contabile, e poi le righe vengono sommate per determinare i debiti totali e i crediti totali. Per essere considerati bilanciati, i debiti e i crediti devono essere bilanciati, e non ci deve essere nessuna differenza di arrotondamento del centesimo.

### <a name="reporting-currency"></a>Valuta dichiarazione

Se tutte le righe di un buono hanno la stessa valuta della transazione e se gli importi della valuta della transazione sono bilanciati, il sistema verifica che gli importi della valuta di segnalazione siano bilanciati. Se il buono è inserito in una valuta estera, il tasso di cambio sulle righe del buono è usato per tradurre gli importi della valuta della transazione nella valuta di segnalazione. In primo luogo, ogni riga del buono viene tradotta. Poi le linee vengono sommate per determinare il totale dei debiti e il totale dei crediti. Poiché ogni riga è tradotta, il totale dei debiti e il totale dei crediti potrebbero non essere bilanciati. Tuttavia, se la differenza è all'interno del valore **massimo di penny-rounding nella valuta di segnalazione** che è definito nella pagina dei **parametri di contabilità generale** , il buono sarà inviato, e la differenza sarà automaticamente inviata al conto della differenza di penny.

Se il buono ha più di una valuta di transazione, ogni riga del buono viene tradotta nella valuta di riferimento, e poi le righe vengono sommate per determinare il totale dei debiti e il totale dei crediti. Per essere considerati bilanciati, i debiti e i crediti devono essere bilanciati, e non ci deve essere nessuna differenza di arrotondamento del centesimo.
