---
title: Termini per registrazione ordine
description: "Questo articolo fornisce informazioni sulle scadenze di registrazione ordine. Una scadenza di registrazione ordine è un tempo limite che determina se un ordine cliente è considerato (ed evaso) come ricevuto il giorno corrente o il giorno successivo."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventOrderEntryDeadlineGroup, InventOrderEntryDeadlineParameters, InventOrderEntryDeadlineTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7151
ms.assetid: bbc4f9a2-df4b-4d92-9f18-25282a85541f
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d865260679dac6196a69f3182f937df7f9fd8200
ms.lasthandoff: 03/31/2017


---

# <a name="order-entry-deadlines"></a>Termini per registrazione ordine

Questo articolo fornisce informazioni sulle scadenze di registrazione ordine. Una scadenza di registrazione ordine è un tempo limite che determina se un ordine cliente è considerato (ed evaso) come ricevuto il giorno corrente o il giorno successivo.

In molte società vige una regola secondo cui solo gli ordini cliente pervenuti entro una certa ora del giorno vengono considerati come ricevuti in quel giorno. Tutti gli ordini ricevuti dopo tale scadenza vengono trattati come se ricevuti il giorno lavorativo successivo. Questo tempo limite per gli ordini è conosciuto come termine per la registrazione degli ordini.  

I termini per la registrazione degli ordini vengono utilizzati come input per le promesse di ordine. Di conseguenza, consentono di gestire le aspettative cliente sulle consegne di ordini. Ad esempio, i clienti possono vedere che, se effettuano un ordine prima di un ora specifica, vi impegnerete a spedire le merci lo stesso giorno. Tuttavia, se mancano il termine, possono prevedere la spedizione solo nel day business successivo. È possibile impostare i termini per l'inserimento di ordini basati sulle capacità di magazzino e programmazioni di gestione delle spedizioni.  

Gli orari dei termini di registrazione degli ordini per tutti i giorni della settimana vengono impostati nella pagina **Termini per registrazione ordine.** Se gli ordini vengono ricevuti dopo gli orari specificati, vengono trattati come se ricevuti il giorno lavorativo successivo. Per impostazione predefinita, questi orari sono impostati su 23.59, ovvero un minuto prima della mezzanotte del giorno pertinente. L'ora predefinita può essere modificata in modo che coincida con l'ora di scadenza di spedizione o di entrata effettiva.  

È possibile definire i termini per la registrazione ordine per un gruppo specifico di clienti. Ad esempio, si potrebbero impostare per un gruppo specifico di clienti termini per la registrazione ordine successivi a quelli definiti per altri clienti. In questo caso, è necessario definire prima i gruppi per i termini per la registrazione ordine nella pagina **Gruppi di termini per la registrazione ordine**. Si assegnano quindi i gruppi ai clienti nella pagina **Clienti**.  

Nel caso ad esempio di una società presente in più siti, è possibile impostare termini per la registrazione ordine specifici per ogni sito. Se i siti sono posizionati in fusi orari diversi, l'impostazione dei termini per la registrazione ordine verrà effettuata in base al fuso orario del sito specifico. Quando tuttavia si utilizzano ordini cliente e offerte di vendita, il termine per la registrazione ordine verrà convertito in base al proprio fuso orario nella pagina **Date di spedizione e di ricevimento disponibili**.  

Nella pagina **Attiva combinazioni di termini per la registrazione ordine** si definiscono le combinazioni di siti e gruppi di termini per la registrazione ordine consentite.

## <a name="example-order-entry-deadline"></a>Esempio: termine per la registrazione ordine
Il termine per la registrazione ordine del martedì è stato impostato su 16.00. Un determinato martedì, alle 17.00, si tenta di impostare la data corrente come data di spedizione. Nota (non è presente alcun lead time per questo esempio). ** Se controllo della data di consegna ** la casella di controllo è selezionata, viene visualizzato un avviso indicante che la data non è valida. Questo avviso viene visualizzato nella pagina **Date di spedizione e di ricevimento disponibili**, in cui è possibile selezionare le date alternative.

## <a name="example-different-order-entry-deadlines-per-site"></a>Esempio: termini per la registrazione ordine diversi in base al sito
La società è presente in due siti I siti si trovano in fusi orari diversi, come illustrato nella seguente tabella.

| Sito A                      | Sito B                      |
|-----------------------------|-----------------------------|
| California                  | Florida                     |
| Ora solare Pacifico | Ora solare fuso orientale |

Nei siti A e B sono stati definiti i seguenti termini per la registrazione ordine.

| Giorno della settimana             | A: Termini per inserimento ordini (Ora solare Pacifico) | B: Termini per inserimento ordini (Ora solare fuso orientale) |
|-----------------------------|--------------------------------|--------------------------------|
| Lunedì                      | 13.00                          | 14:00:00                          |
| Martedì                     | 13.00                          | 14:00:00                          |
| Mercoledì                   | 13.00                          | 14:00:00                          |
| Giovedì                    | 13.00                          | 14:00:00                          |
| Venerdì                      | 13.00                          | 14:00:00                          |

L'addetto all'elaborazione degli ordini si trova nello Utah dove è in vigore l'ora solare del fuso occidentale. Se pertanto gli ordini vengono effettuati entro le 14.00 (ora solare fuso occidentale) per il sito A e entro le 12.00 (ora solare fuso occidentale) per il sito B, vengono rispettati i termini per la registrazione ordine per entrambi i siti.  

Nella seguente tabella viene illustrato in che modo i termini per la registrazione ordine per i siti A e B vengono convertiti in base all'ora solare del fuso occidentale.

| Sito A: Ora solare Pacifico         | Sito A: A        | Sito B: Ora solare fuso orientale           | Sito B: A        |
|---------------------|--------------------|-----------------------|--------------------|
| 13.00               | 14:00:00              | 14:00:00                 | 12.00              |

**Nota:** Se è in vigore l'ora legale, i termini per la registrazione ordine verranno adattati di conseguenza.

## <a name="example-same-order-entry-deadline-per-site"></a>Esempio: termine per la registrazione ordine uguale per tutti i siti
La società è presente in due siti I siti si trovano in fusi orari diversi, come illustrato nella seguente tabella.

| Sito A                      | Sito B                      |
|-----------------------------|-----------------------------|
| California                  | Florida                     |
| Ora solare Pacifico | Ora solare fuso orientale |

Nei siti A e B sono stati definiti i seguenti termini per la registrazione ordine.

| Giorno della settimana | Ora solare Pacifico e ora solare fuso orientale |
|-----------------|-------------|
| lunedì          | 13.00       |
| martedì         | 13.00       |
| mercoledì       | 13.00       |
| giovedì        | 13.00       |
| venerdì          | 13.00       |

L'addetto all'elaborazione degli ordini si trova nello Utah dove è in vigore l'ora solare del fuso occidentale. Se pertanto gli ordini vengono effettuati entro le 14.00 (ora solare fuso occidentale) per il sito A e entro le 11.00 (ora solare fuso occidentale) per il sito B, vengono rispettati i termini per la registrazione ordine per entrambi i siti. 

Nella seguente tabella viene illustrato in che modo i termini per la registrazione ordine per i siti A e B vengono convertiti in base all'ora solare del fuso occidentale.

| Sito A: Ora solare Pacifico         | Sito A: A        | Sito B: Ora solare fuso orientale           | Sito B: A        |
|---------------------|--------------------|-----------------------|--------------------|
| 13.00               | 14:00:00              | 13.00                 | 11.00              |

**Nota:** Se è in vigore l'ora legale, i termini per la registrazione ordine verranno adattati di conseguenza.

<a name="see-also"></a>Vedere anche
--------

[Delivery schedules](delivery-schedules.md)

