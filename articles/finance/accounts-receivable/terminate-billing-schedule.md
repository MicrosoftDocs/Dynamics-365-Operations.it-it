---
title: Terminare i programmi di fatturazione
description: Questo articolo spiega come terminare i programmi di fatturazione e le righe programma di fatturazione nella fatturazione abbonamento.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 4fce23f3cf35ef8c388ce13fc422f268a2bd8e32
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872559"
---
# <a name="terminate-billing-schedules"></a>Terminare i programmi di fatturazione

[!include [banner](../includes/banner.md)]

Questo articolo spiega come terminare i programmi di fatturazione e le righe programma di fatturazione nella fatturazione abbonamento. Quando termini un programma di fatturazione, deve avere lo stato **Attivo**. Non può avere uno stato **In attesa**. Analogamente, quando termini una riga programma di fatturazione, deve avere lo stato **Attivo**. La sezione dell'intestazione del programma di fatturazione non è interessata quando si termina una riga programma di fatturazione.

Per terminare un programma di fatturazione o una riga del programma di fatturazione, vai in una delle seguenti pagine:

- La pagina elenco **Tutti i programmi di fatturazione o Programmi di fatturazione attivi**
- Un programma di fatturazione specifico nella pagina **Tutti i programmi di fatturazione**
- Una riga del programma di fatturazione specifica nella pagina **Tutti i programmi di fatturazione**

> [!NOTE]
> Se desideri terminare più programmi di fatturazione contemporaneamente, utilizza la pagina **Elaborazione terminazione di massa**.

## <a name="terminate-a-billing-schedule-or-line"></a>Terminare un programma di fatturazione o una riga

Per terminare un programma di fatturazione o una riga del programma di fatturazione, effettua i seguenti passaggi.

1. Seleziona un programma di fatturazione o una riga del programma di fatturazione, quindi seleziona **Termina**. 
2. Imposta i campi **Data terminazione**, **Tipo di terminazione**, e **Codice motivo**.
3. Imposta il campo **Opzione di credito** su **Emetti credito**.
4. Seleziona **Termina**.

Lo stato del programma di fatturazione cambia, in base al tipo di terminazione selezionato. Se hai selezionato **Fattura rimanente** come tipo di terminazione, lo stato di tutte le righe nel programma di fatturazione è **Ultima fatturazione**. Lo stato del programma di fatturazione rimane **Attivo** fino all'elaborazione dell'ultima fattura. Dopo l'elaborazione dell'ultima fattura, lo stato viene aggiornato a **Terminato**. Se hai selezionato **Rettifica programma** come tipo di terminazione, lo stato del programma di fatturazione viene immediatamente aggiornato a **Terminato**.

## <a name="terminate-a-billing-schedule-or-line-and-apply-a-refund"></a>Terminare un programma o una riga di fatturazione e applicare un rimborso

Per terminare un programma di fatturazione o una riga del programma di fatturazione e applicare un rimborso, effettua i seguenti passaggi.

1. Seleziona un programma di fatturazione o una riga del programma di fatturazione, quindi seleziona **Termina**.
2. Imposta i campi **Data terminazione**, **Tipo di terminazione**, **Codice motivo**, e **Opzione di credito**.
3. Seleziona **Termina con rimborso**. La pagina **Elaborazione di terminazione di massa** viene visualizzata e viene filtrata in modo da mostrare il programma di fatturazione.
4. Seleziona **Visualizza anteprima** per visualizzare le righe del programma di fatturazione, quindi seleziona **Processo**.

Dopo che il credito è stato elaborato, apri la pagina **Visualizza dettagli fatturazione** per rivedere il credito che è stato applicato al programma di fatturazione. Se l'importo del credito è maggiore di 0 (zero), tutte le righe non fatturate future vengono eliminate e sostituite con le righe dei dettagli di fatturazione che mostrano gli importi negativi per il credito applicato al programma di fatturazione.

### <a name="view-example"></a>Visualizza esempio

Un programma di fatturazione contiene le seguenti informazioni:

- La data di inizio è il 1 gennaio 2020.
- La data di fine è il 31 dicembre 2020.
- L'importo del periodo di fatturazione è di 100,00 al mese.
- Le fatture sono state create per periodi di fatturazione da gennaio a luglio.
- La data di scadenza del contratto è il 15 giugno 2020.

Quando la rettifica del credito viene elaborata, tutti i periodi di fatturazione futuri (da agosto a dicembre) vengono rimossi dalla pagina **Visualizza dettagli di fatturazione**. Dopo il periodo di fatturazione di luglio viene aggiunta una riga di rettifica del credito:

- 16 giugno – 31 luglio, con un credito di 150,00

Se viene utilizzata la funzione ricavi non fatturati, la pagina **Controllo scrittura contabile ricavi non fatturati** viene aggiornata con la voce di terminazione.

## <a name="terminate-a-billing-schedule-or-line-without-applying-a-credit"></a>Terminare un programma o una riga di fatturazione senza applicare un credito

Per terminare un programma di fatturazione o una riga del programma di fatturazione senza applicare un credito, effettua i seguenti passaggi.

1. Seleziona un programma di fatturazione o una riga del programma di fatturazione, quindi seleziona **Termina**.
2. Imposta il campo **Data terminazione**.
3. Imposta il campo **Tipo di terminazione** su **Nessuna rettifica**. Il campo **Opzione di credito** viene automaticamente impostato su **Nessun credito**.
3. Imposta il campo **Codice motivo**.
4. Nel campo **Note di terminazione**, immetti le note necessarie.
5. Seleziona **Termina**. 

Quando la terminazione viene elaborata, tutte le righe dei dettagli di fatturazione successive alla data di risoluzione vengono rimosse. Queste righe includono la riga che contiene la data di terminazione. Non è possibile creare fatture per le righe terminate. Se la terminazione viene rimossa, tutte le righe terminate vengono aggiunte nuovamente alla pagina **Visualizza dettagli di fatturazione** e diventano disponibili per la fatturazione.

## <a name="fields"></a>Campi

La pagina **Visualizza dettagli di fatturazione** contiene i seguenti campi.

| Campo | Description |
|-------|-------------| 
| Data fine rapporto | Seleziona la data di terminazione di un programma di fatturazione o una riga del programma di fatturazione. |
| Tipo di terminazione | <p>Seleziona il tipo di terminazione:</p><ul><li>**Rettifica programma** – Tagliare i periodi di fatturazione per la riga alla data di terminazione e modificare lo stato della riga in **Ultima fatturazione**. Se esiste un programma di differimento per la voce, viene rettificato stornando l'importo che non deve più essere rilevato. Se la data di inizio della fatturazione è successiva alla data di terminazione, i periodi di fatturazione rimanenti vengono rimossi.</li><li>**Fattura rimanente** – Aggiungi l'eventuale importo residuo per il periodo di fatturazione al periodo di terminazione e modifica lo stato della riga in **Ultima fatturazione**. Se esiste un programma di differimento per la voce, la data di fine differimento viene aggiornata. Se la data di inizio della fatturazione è successiva alla data di terminazione, l'importo totale di tutti i periodi di fatturazione rimanenti viene aggiunto al periodo di fatturazione e i periodi di fatturazione rimanenti vengono rimossi.</li><li>**Nessuna rettifica** – Termina i periodi di fatturazione per la riga alla data di scadenza specificata. Non vengono apportate rettifiche. Quando viene selezionato questo tipo di terminazione, il campo **Opzione credito** è impostato su **Nessun credito**, e il campo **Ripartizione giornaliera** è impostato su **No**. Entrambi questi campi diventano quindi di sola lettura e non possono essere modificati.</li></ul> |
| Opzione di credito | <p>Seleziona come viene applicato il credito quando termini una riga del programma di fatturazione:</p><ul><li>**Rettifica credito** – Crea una rettifica del credito per un programma di fatturazione quando una riga viene terminata. La rettifica del credito viene visualizzato in un periodo di fatturazione futuro per il programma di fatturazione. La rettifica modifica automaticamente anche l'importo della fattura per il periodo di fatturazione successivo fino al termine dell'applicazione del credito al programma di fatturazione.</li><li>**Emetti credito** – Crea una nota di credito quando un programma di fatturazione o una riga del programma di fatturazione viene terminato.</li><li>**Nessun credito** – Non viene creata una rettifica di credito o una nota di credito quando un programma di fatturazione o una riga del programma di fatturazione viene terminato. Questa opzione è disponibile solo quando si utilizza una terminazione di tipo **Nessuna rettifica** per terminare un programma di fatturazione.</li></ul><p>L'opzione predefinita è nella pagina **Parametri di fatturazione ricorrente di contratti**.</p> |
| Codice motivo | Seleziona il codice motivo per la terminazione. |
| Descrizione motivo | Descrizione del codice motivo. |
| Note terminazione | Immetti le eventuali note relative alla terminazione. |

<!--## Additional information-->
