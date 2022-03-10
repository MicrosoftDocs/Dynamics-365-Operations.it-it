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
ms.openlocfilehash: 0f1f49a7da2f015d90987587fc251a36cfe82d49
ms.sourcegitcommit: cd7f1c63f48542a8ebcace7b3d512eb810d4b56e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903252"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Insuccesso della pubblicazione del giornale a causa dello squilibrio

[!include [banner](../includes/banner.md)]

Questo argomento spiega perché gli addebiti e gli accrediti potrebbero non essere bilanciati nelle transazioni dei buoni, così che le transazioni non possono essere registrate. L'argomento include anche i passi per risolvere il problema.

## <a name="symptom"></a>Sintomo

In alcuni casi, un diario non può essere pubblicato e viene mostrato il seguente messaggio: "Le transazioni su un voucher specifico non si equilibrano a partire da una certa data (valuta contabile: 0.01 - valuta di segnalazione: 0.06)." Perché il diario non può essere pubblicato?

## <a name="resolution"></a>Risoluzione

Durante la registrazione in Contabilità generale, ogni giustificativo deve essere bilanciato nella valuta della transazione, nella valuta contabile e nella valuta di segnalazione, se queste valute sono definite nella pagina **di impostazione del Ledger** . (I buoni sono bilanciati quando il totale dei debiti è uguale al totale dei crediti)

In fondo alla pagina delle righe del giornale, i totali sono mostrati nella valuta contabile e nella valuta di segnalazione.  **Non** sono mostrati nella valuta della transazione per le transazioni in valuta estera. Inoltre, il messaggio di errore che gli utenti ricevono durante la simulazione o la registrazione mostra le differenze solo nella valuta contabile e nella valuta di segnalazione. Non li mostra nella valuta della transazione, perché un singolo giustificativo può avere più di una valuta di transazione, e il giornale può includere buoni in diverse valute di transazione. Pertanto, è importante verificare manualmente che gli importi in valuta di transazione per ogni giustificativo con una sola valuta di transazione siano bilanciati.

### <a name="transaction-currency"></a>Valuta transazione

Durante la simulazione e la registrazione, il sistema verifica che ogni giustificativo che ha una sola valuta di transazione sia bilanciato nella valuta della transazione. Per ogni giustificativo che viene inserito, ci possono essere una o più valute per la valuta della transazione. Per esempio, un giustificativo inserito nel giornale generale potrebbe avere due valute di transazione quando il contante viene trasferito da un conto bancario che usa euro (EUR) a un conto bancario che usa dollari canadesi (CAD).

Se un giustificativo ha solo una valuta di transazione, il totale degli addebiti deve essere uguale al totale degli accrediti nella valuta della transazione per quel giustificativo. I clienti hanno incontrato i seguenti scenari in cui la registrazione è fallita correttamente perché gli importi della valuta della transazione non erano bilanciati:

- Il totale dei debiti e il totale dei crediti **non** erano bilanciati nella valuta della transazione, ma erano bilanciati per la valuta contabile e la valuta di segnalazione. Un cliente ha dato per scontato che il giustificativo sarebbe stato comunque inviato. Tuttavia, questa supposizione era sbagliata. **Gli importi in valuta della transazione su un giustificativo devono sempre essere bilanciati quando tutte le righe del giustificativo hanno la stessa transazione.**
- Il giustificativo è stato importato con un'entità dati tramite Data Management Framework (DMF) e l'utente ha ritenuto che gli importi in valuta della transazione fossero bilanciati. In un file di importazione, alcuni importi avevano più di due cifre decimali e più di due cifre decimali sono state incluse quando gli importi sono stati importati. Pertanto, gli addebiti non erano uguali agli accrediti, perché erano fuori di una frazione di centesimo. Il giornale non rifletteva questa differenza sulle righe del giustificativo, perché gli importi indicati hanno solo due cifre decimali.
- Il giustificativo è stato importato con un'entità di dati attraverso DMF e l'utente pensava che gli importi della valuta della transazione fossero bilanciati. Anche se il **giustificativo** era bilanciato, alcune righe del giustificativo avevano date di transazione diverse. Se sono stati sommati gli addebiti totali e gli accrediti totali nella valuta della transazione per **giustificativo e data della transazione**, non erano bilanciati. Questo requisito viene applicato quando si inserisce un giustificativo attraverso il giornale generale nel sistema. Tuttavia, questo non viene applicato quando un giustificativo viene importato con un'entità di dati tramite DMF.

In uno scenario supportato, un giustificativo può avere più di una valuta di transazione. In questo caso, il sistema **non** verifica che gli addebiti siano uguali agli accrediti nella valuta della transazione, perché le valute non corrispondono. Il sistema verifica invece che gli importi della valuta contabile e della valuta di dichiarazione siano bilanciati.

### <a name="accounting-currency"></a>Valuta di contabilizzazione

Se tutte le righe di un giustificativo hanno la stessa valuta di transazione, e se gli importi della valuta di transazione sono bilanciati, il sistema verifica che gli importi della valuta contabile siano bilanciati. Se il giustificativo è inserito in una valuta estera, il tasso di cambio sulle righe del giustificativo è usato per tradurre gli importi della valuta della transazione nella valuta contabile. Innanzitutto, ogni riga del voucher viene tradotta e arrotondata a due cifre decimali. Poi le linee vengono sommate per determinare il totale dei debiti e il totale dei crediti. Poiché ogni riga è tradotta, il totale dei debiti e il totale dei crediti potrebbero non essere bilanciati. Tuttavia, se il valore assoluto della differenza è all'interno del valore **massimo di differenza di centesimo** che è definito nella pagina dei **parametri della contabilità generale** , il giustificativo sarà inviato e la differenza sarà automaticamente inviata al conto differenza di penny.

Se il giustificativo ha più di una valuta di transazione, ogni riga del giustificativo viene tradotta nella valuta contabile e arrotondato di due posizioni decimali e poi le righe vengono sommate per determinare i debiti totali e i crediti totali. Per essere considerati bilanciati, i debiti e i crediti devono essere bilanciati nella valuta di contabilizzazione.  Un conto con differenza in centesimi non viene mai aggiunto al giustificativo nella valuta contabile per portare in pareggio gli addebiti e gli accrediti. 

### <a name="reporting-currency"></a>Valuta dichiarazione

Se tutte le righe di un giustificativo hanno la stessa valuta della transazione e se gli importi della valuta della transazione sono bilanciati, il sistema verifica che gli importi della valuta di segnalazione siano bilanciati. Se il giustificativo è inserito in una valuta estera, il tasso di cambio sulle righe del giustificativo è usato per tradurre gli importi della valuta della transazione nella valuta di segnalazione. Innanzitutto, ogni riga del voucher viene tradotta e arrotondata a due cifre decimali. Poi le linee vengono sommate per determinare il totale dei debiti e il totale dei crediti. Poiché ogni riga è tradotta, il totale dei debiti e il totale dei crediti potrebbero non essere bilanciati. Tuttavia, se la differenza è all'interno del valore **massimo di penny-rounding nella valuta di segnalazione** che è definito nella pagina dei **parametri di contabilità generale** , il giustificativo sarà inviato, e la differenza sarà automaticamente inviata al conto della differenza di penny.

Se il giustificativo ha più di una valuta di transazione, ogni riga del giustificativo viene tradotta nella valuta dichiarazione e arrotondato di due posizioni decimali e poi le righe vengono sommate per determinare i debiti totali e i crediti totali. Per essere considerati bilanciati, i debiti e i crediti devono essere bilanciati nella valuta di dichiarazione.  Un conto con differenza in centesimi non viene mai aggiunto al giustificativo nella valuta di dichiarazione per portare in pareggio gli addebiti e gli accrediti.

### <a name="example-for-an-accounting-currency-imbalance"></a>Esempio per uno squilibrio valutario contabile

> [!NOTE]
> L'importo in valuta di dichiarazione viene calcolato dall'importo in valuta di transazione allo stesso modo dell'importo in valuta contabile.

Tasso di cambio: 1,5

| Riga | Giustificativo | Conto | Valuta | Dare (Transazione) | Avere (Transazione) | Dare (Contabilità) | Avere (Contabilità) |
|---|---|---|---|---|---|---|---|
| 1 | 001 | 1101-01 | EUR | 3.33 | | 5 (4.995) | |
| 2 | 001 | 1101-02 | EUR | 3.33 | | 5 (4.995) | |
| 3 | 001 | 1101-03 | EUR | 3.34 | | 5.01 | |
| 4 | 001 | 4101- | EUR | | 10.00 | | 15.00 |
| **Totale** | | | | **10.00** | **10.00** | **15.01** | **15.00** |

La valuta contabile è sbilanciata di 0,01. Tuttavia, se l'arrotondamento massimo in centesimi nella valuta contabile è almeno 0,01, la differenza verrà automaticamente registrata nel conto differenza in centesimi e il giustificativo verrà registrato correttamente.
