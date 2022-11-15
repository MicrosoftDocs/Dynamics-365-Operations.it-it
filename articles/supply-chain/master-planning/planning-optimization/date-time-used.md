---
title: Parametri di data e ora utilizzati da Ottimizzazione pianificazione
description: Questo articolo fornisce informazioni sui parametri di data e ora utilizzati da Ottimizzazione pianificazione durante il suo funzionamento.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2ef78c73a1c7033735f9586229ff7ba21daaa5ef
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740906"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>Parametri di data e ora utilizzati da Ottimizzazione pianificazione

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce informazioni sui parametri di data e ora utilizzati da Ottimizzazione pianificazione durante il suo funzionamento.

Mentre il motore di pianificazione generale deprecato utilizza le date delle transazioni in tutti i calcoli, Ottimizzazione pianificazione funziona con i valori di data e ora che vengono convertiti in date. Questa differenza di comportamento può portare a situazioni in cui, ad esempio, le transazioni di previsione create a mezzanotte del giorno in cui viene eseguita la pianificazione generale non vengono incluse perché Ottimizzazione pianificazione ritiene che siano state create prima della data corrente.

## <a name="parameters-for-issue-and-demand-transactions"></a>Parametri per le transazioni della domanda e in uscita

Nella tabella seguente sono elencati i parametri utilizzati da Ottimizzazione pianificazione quando elabora le transazioni della domanda e in uscita.

| Parametro | Nome del parametro in Ottimizzazione pianificazione | Descrizione | Campo equivalente in Microsoft Dynamics 365 Supply Chain Management (nella tabella ReqTrans) |
|---|---|---|---|
| Ora di emissione pianificata | `PlannedIssueTime` | Data pianificata per l'emissione. | **Data finale** (`FuturesDate`) e **Ritardato a ora** (`FuturesTime`) |
| Ora di emissione richiesta | `RequestedIssueTime` | La data di emissione richiesta dall'utente e impostata in Supply Chain Management. Questo parametro è applicabile solo per ordini pianificati rilasciati o approvati. Per gli ordini pianificati, è vuoto per impostazione predefinita. | **Data richiesta** (`ReqDateDlvOrig`) |
| Ora di emissione richiesta | `RequiredIssueTime` | La data di emissione richiesta che viene modificata da Ottimizzazione pianificazione. Se l'ora di emissione richiesta è nel passato quando viene eseguita Ottimizzazione pianificazione, l'ora di emissione richiesta verrà adattata al primo giorno di apertura che non è precedente alla data odierna. Se l'ora di emissione richiesta è contrassegnata come bloccata nel calendario, l'ora di emissione richiesta verrà adeguata al primo giorno di apertura prima di tale data. | **Data fabbisogno** (`ReqDate`) e **Ora fabbisogno** (`ReqTime`) |
| Ritardo ora di emissione | `IssueTimeDelay` | La differenza di tempo tra l'ora di emissione pianificata e l'ora di emissione richiesta per gli ordini approvati e rilasciati o l'ora di emissione richiesta. | **Ritardo (in giorni)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>Parametri per le operazioni di fornitura e ricevuta

Nella tabella seguente sono elencati i parametri utilizzati da Ottimizzazione pianificazione quando elabora le transazioni di fornitura e di ricevuta.

| Parametro | Nome del parametro in Ottimizzazione pianificazione | Descrizione | Campo equivalente in Supply Chain Management (nella tabella ReqTrans o ReqPO) |
|---|---|---|---|
| Ora di disponibilità pianificata | `PlannedAvailabilityTime` | Data pianificata in cui la ricevuta diventerà disponibile. | **Data fabbisogno** (`ReqDate`) e **Ora fabbisogno** (`ReqTime`) |
| Ora di ricevuta pianificata | `PlannedReceiptTime` | La data in cui la ricevuta arriverà in sede. | **Data finale** (`FuturesDate`), **Ritardato a ora** (`FuturesTime`) e **Data di consegna** (`ReqDateDlv`) o **Data richiesta** (`ReqDateDlvOrig`) se l'ordine non è ancora stato rilasciato. |
| Ora disponibilità richiesta | `RequiredAvailabilityTime` | La data di disponibilità richiesta che viene modificata da Ottimizzazione pianificazione. | **Data fabbisogno** (`ReqDate`) e **Ora fabbisogno** (`ReqTime`) |
| Ora di ricezione prevista | `ExpectedReceiptTime` | La data di ricezione prevista per una ricevuta rilasciata. Il valore viene impostato dall'utente in Supply Chain Management e non viene modificato da Ottimizzazione pianificazione. Questo parametro si applica solo alle ricevute rilasciate. | **Data richiesta** (`ReqDateDlvOrig`) |
| Ora di ricezione richiesta | `RequiredReceiptTime` | La data di ricezione richiesta che viene modificata da Ottimizzazione pianificazione. | **Data fabbisogno** (`ReqDate`) e **Ora fabbisogno** (`ReqTime`) |
| Ora di ordine pianificata | `PlannedOrderingTime` | La data di ordine richiesta che viene calcolata da Ottimizzazione pianificazione. | **Data ordine** (`ReqDateOrder`) e **Ora ordine** (`ReqTimeOrder`) |
| Ora di inizio attività pianificata | `PlannedActivityStartTime` | La data in cui dovrebbe iniziare l'attività per questa ricevuta. | **Data di inizio** (`SchedFromDate`) |
| Ritardo ora ricezione | `ReceiptTimeDelay` | La differenza di tempo tra l'ora di ricevuta pianificata e l'ora di ricevuta richiesta. | **Ritardo (giorni)** (`FuturesDays`) e **Ritardato nel tempo** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Esempi di uso dei parametri della data da parte di Ottimizzazione pianificazione

I piani nelle illustrazioni seguenti sono a livello di giorno, ma Ottimizzazione pianificazione viene eseguita a un livello più dettagliato. Ad esempio, poiché i margini possono essere espressi in ore, l'orario di ordine della pianificazione può essere il 22 gennaio 2021, alle 11:35 e così via.

### <a name="example-1-simple-scenario"></a>Esempio 1: scenario semplice

Un ordine cliente con un'ora di emissione richiesta il 22 gennaio è coperto da un ordine fornitore. Vengono usate le seguenti impostazioni:

- Nessun lead time
- Nessun calendario (tutti i giorni sono aperti.)
- Nessun margine

Nella figura seguente viene illustrato questo scenario. Seleziona l'illustrazione per aprire una versione più grande.

[![Scenario semplice.](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>Esempio 2: scenario lead time

Un ordine cliente con un'ora di emissione richiesta il 22 gennaio è coperto da un ordine fornitore. Vengono usate le seguenti impostazioni:

- Tre giorni di lead time
- Nessun calendario (tutti i giorni sono aperti.)
- Nessun margine

Nella figura seguente viene illustrato questo scenario. Seleziona l'illustrazione per aprire una versione più grande.

[![Scenario lead time.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>Esempio 3: scenario di margine

Un ordine cliente con un'ora di emissione richiesta il 22 gennaio è coperto da un ordine fornitore. Vengono usate le seguenti impostazioni:

- Tre giorni di lead time
- Margine di ordine di quattro giorni
- Margine di disponibilità di cinque giorni
- Nessun calendario (tutti i giorni sono aperti.)

Nella figura seguente viene illustrato questo scenario. Seleziona l'illustrazione per aprire una versione più grande.

[![Scenario di margine.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>Esempio 4: scenario di ritardo

Un ordine cliente con un'ora di emissione richiesta il 22 gennaio è coperto da un ordine fornitore. Questo esempio utilizza le stesse impostazioni dell'esempio 3, ma la data di pianificazione è stata spostata al 15 gennaio. La pianificazione a ritroso (marcatori rossi) non riesce perché l'ora di ordinazione pianificata dovrebbe essere precedente alla data odierna. Pertanto, la pianificazione generale deve essere pianificata in avanti e si verificano ritardi.

Nella figura seguente viene illustrato questo scenario. Seleziona l'illustrazione per aprire una versione più grande.

[![Scenario di ritardo.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>Esempio 5: scenario di trasferimento

Un ordine cliente dal magazzino 1 con un ora di prelievo richiesta il 22 gennaio è coperto da un ordine di trasferimento dal magazzino 2 coperto da un ordine fornitore pianificato. Vengono usate le seguenti impostazioni:

- Tre giorni di lead time di trasferimento (magazzino 1)
- Due giorni di lead time di acquisto (magazzino 2)
- Nessun calendario (tutti i giorni sono aperti.)

Nella figura seguente viene illustrato questo scenario. Seleziona l'illustrazione per aprire una versione più grande.

[![Scenario di trasferimento.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>Esempio 6: scenario lead time con calendari

Un ordine cliente con un'ora di emissione richiesta il 22 gennaio è coperto da un ordine fornitore. Vengono usate le seguenti impostazioni:

- Tre giorni di lead time
- Calendario delle emissioni (chiuso il venerdì)
- Calendario delle disponibilità (chiuso giovedì e venerdì)
- Calendario delle ricevute (chiuso martedì, mercoledì e domenica)
- Calendario lead time (chiuso giovedì e venerdì)
- Calendario ordini (aperto lunedì e sabato)

Nella figura seguente viene illustrato questo scenario. Seleziona l'illustrazione per aprire una versione più grande.

[![Scenario lead time con calendari.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>Esempio 7: scenario di ritardo con calendari

Un ordine cliente con un'ora di emissione richiesta il 22 gennaio è coperto da un ordine fornitore. Questo esempio utilizza le stesse impostazioni dell'esempio 6, ma la data di pianificazione è stata spostata al 13 gennaio. La pianificazione a ritroso (marcatori rossi) non riesce perché l'ora di ordinazione pianificata dovrebbe essere precedente alla data odierna. Pertanto, la pianificazione generale deve essere pianificata in avanti e si verificano ritardi.

Nella figura seguente viene illustrato questo scenario. Seleziona l'illustrazione per aprire una versione più grande.

[![Scenario di ritardo con calendari.](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
