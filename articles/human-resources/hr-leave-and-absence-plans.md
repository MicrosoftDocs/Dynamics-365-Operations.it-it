---
title: Creare un piano di congedo e assenza
description: Questo argomento descrive come creare piani ferie in Dynamics 365 Human Resources per diverse tipologie di congedo.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 47a0db91a1c27e1c0b1117da79d9f8d2abc665cb
ms.sourcegitcommit: 67c4ed957e43d4d60bb609d93921a0be9619e675
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "8509586"
---
# <a name="create-a-leave-and-absence-plan"></a>Creare un piano di congedo e assenza

> [!Important]
> La funzionalità indicata in questo argomento è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Definire piani di congedo e assenza in Dynamics 365 Human Resources per ogni tipo di congedo offerto. I piani di congedo e assenza possono accumularsi a frequenze diverse, come annuale, mensile o semestrale. È anche possibile definire i piani come una concessione, dove un singolo accumulo avviene a una data specifica. Ad esempio, si potrebbe creare un piano che concede festività mobili ogni anno.

I piani di congedo a più livelli consentono ai dipendenti di ricevere benefit in base alla quantità di tempo trascorso in un'organizzazione. I piani a più livelli consentono l'iscrizione automatica in ulteriori ore benefit.

È possibile specificare limiti di riporto massimi o saldi minimi per garantire che i dipendenti utilizzino solo le ore benefit accumulate.

Ad esempio, con un piano a più livelli, si potrebbe concedere un benefit di 80 ore di permessi retribuiti ai nuovi dipendenti. Successivamente si potrebbe concedere 120 ore per 60 mesi di servizio.

È anche possibile creare benefit di congedo in base alla posizione, come ore benefit per soli dirigenti.

## <a name="create-a-leave-plan"></a>Creare un piano di congedo

1. Nella pagina **Piani di congedo e assenza** selezionare **Crea nuovo piano**.

2. Sotto **Dettagli**, immettere **Nome**, **Data d'inizio**, **Descrizione** e **Tipo di congedo** per il piano.

Se la funzionalità per **configurare più tipi di congedo per un singolo piano di congedo e assenza** è abilitata, i tipi di congedo sono configurati in **Programmazione dell'accumulo** anziché in **Dettagli**. Per ogni record nella tabella della programmazione dell'accumulo, è possibile definire un tipo di congedo. Inoltre, quando questa funzione è abilitata, è necessario usare nuove entità di dati per integrazioni o altri scenari in cui occorre usare le entità. 

Le nuove entità sono:

- Transazione bancaria per congedo e assenza V2
- Iscrizione per congedo e assenza V2
- Livello del piano di congedo e assenza V2
- Piano di congedo e assenza V2
- Richiesta di permesso di congedo V2

 > [!IMPORTANT]
   > Dopo aver abilitato questa funzionalità, non è possibile disattivarla.

3. Definire gli accumuli nella scheda **Accumuli**. Gli accumuli determinano quando e con quale frequenza viene concesso un permesso a un dipendente. In questa fase, si definiscono le politiche su quando gli accumuli devono essere assegnati e le politiche sulla ripartizione dei benefit di congedo.

   1. Seleziona un valore dalla casella a discesa **Frequenza accumulo**:

      - Ogni giorno
      - Ogni settimana
      - Bisettimanale
      - Quindicinale
      - Ogni mese
      - Trimestrale
      - Biennale
      - Annualmente
      - Nessuna

   2. Selezionare un'opzione dalla casella a discesa **Base periodo di accumulo** per determinare la data di inizio utilizzata per il calcolo dei periodi di accumulo:

      | Base del periodo di accumulo | Descrizione |
      | --- | --- |
      | **Data di inizio piano** | La data di inizio del periodo di accumulo è la data in cui il piano è disponibile. |
      | **Data specifica del dipendente** | La data di inizio del periodo di accumulo dipende da un evento del dipendente:</br><ul><li>Personalizzato (è necessario specificare una base per la data di accumulo per ogni singola iscrizione)</li><li>Data di ricorrenza annuale</li><li>Data di assunzione originale</li><li>Data di anzianità</li><li>Data di inizio rettificata del lavoratore</li><li>Data di inizio del lavoratore</li></ul> |

   3. Selezionare un'opzione dalla casella a discesa **Data concessione accumulo**:

      - **Fine del periodo di accumulo** - Al dipendente viene concesso un permesso l'ultimo giorno del periodo di premio. Per accumulare l'importo corretto, il processo di accumulo deve includere l'intero periodo. Ad esempio, se il periodo di accumulo è compreso tra il 1° gennaio 2020 e il 31 gennaio 2020, è necessario eseguire l'accumulo per il 1° febbraio 2020 per includere gennaio.

      - **Inizio del periodo di accumulo** - Al dipendente viene concesso un permesso il primo giorno del periodo di premio.

   4. Selezionare un'opzione dalla casella a discesa **Criteri di accumulo all'iscrizione**: Questo valore definisce il modo di calcolo dell'accumulo quando un dipendente si iscrive durante un periodo di accumulo.

      - **Ripartito** - L'intervallo di date tra la data di iscrizione e la data di inizio viene utilizzato per determinare la differenza in giorni. Tale differenza viene applicata quando si elaborano gli accumuli.

      - **Accumulo completo** - L'importo di accumulo completo, basato sul livello, viene concesso durante la prima elaborazione dell'accumulo.

      - **Nessun accumulo** - Non viene concesso alcun accumulo fino al periodo di accumulo successivo.

   5. Selezionare un'opzione dalla casella a discesa **Criteri di accumulo all'annullamento dell'iscrizione**: Questo valore definisce il modo di calcolo dell'accumulo quando un dipendente annulla l'iscrizione durante un periodo di accumulo.

      - **Ripartito** - L'intervallo di date tra la data di iscrizione e la data di inizio viene utilizzato per determinare la differenza in giorni. Tale differenza viene applicata quando si elaborano gli accumuli.

      - **Accumulo completo** - L'importo di accumulo completo, basato sul livello, viene concesso durante la prima elaborazione dell'accumulo.

      - **Nessun accumulo** - Non viene concesso alcun accumulo fino al periodo di accumulo successivo.

4. Definire la programmazione dell'accumulo nella scheda **Programmazione dell'accumulo**. La programmazione dell'accumulo determina:

   - Come un dipendente accumula i permessi
   - Gli importi accumulati dal dipendente
   - Gli importi che verranno riportati

   È possibile creare livelli per concedere permessi in base a livelli differenti.

   Le organizzazioni con dipendenti a ora possono assegnare permessi in base alle ore lavorate anziché in base alla durata del rapporto con l'organizzazione. I dati sulle ore lavorate vengono in genere archiviati in un sistema di gestione dell'orario e delle presenze. È possibile importare le ore regolari e di straordinario lavorate dal sistema di gestione dell'orario e delle presenze e utilizzarle come base per un premio al dipendente.
   
    1. Selezionare un'opzione dalla casella a discesa **Tipo di accumulo**:

      - **Mesi di servizio** - La programmazione dell'accumulo è basata sui mesi di servizio.

      - **Ore lavorate** - La programmazione dell'accumulo è basata sulle ore lavorate. Per ulteriori informazioni sugli accumuli per ore lavorate, consultare [Accumulare tempo libero in base alle ore di lavoro](hr-leave-and-absence-plans.md?accrue-time-off-based-on-hours-worked).

      Per ulteriori informazioni sui saldi di accumulo, consultare [Accumulare tempo libero in base alle ore di lavoro](hr-leave-and-absence-plans.md?enrollments-and-balances).

    2. Immettere i valori nella tabella della programmazione dell'accumulo:

      - **Mesi di servizio** - Il numero minimo di mesi che i dipendenti devono lavorare per avere diritto ad accumuli. Se non è richiesto un minimo, impostare il valore su 0.

      - **Ore lavorate** - Il numero minimo di ore che i dipendenti devono lavorare per periodo di accumulo per avere diritto ad accumuli. Se non è richiesto un minimo, impostare il valore su 0.

      - **Importo accumulo** - Il numero di ore o giorni che i dipendenti accumulano per periodo. Il periodo è basato sulla frequenza dell'accumulo.

      - **Saldo minimo** - È possibile essere utilizzare un valore negativo per il saldo minimo se i dipendenti possono richiedere più congedi di quelli disponibili.

      - **Riporto massimo** - Il processo di accumulo rettificherà i saldi congedo che superano il saldo riporto massimo alla ricorrenza della data di inizio.

      - **Importo concesso** - Il numero iniziale di ore o giorni concessi ai dipendenti quando si iscrivono per la prima volta al piano di congedo. Non si ha accumulo dell'importo per ogni periodo di accumulo.
      
Se la funzionalità per **configurare più tipi di congedo per un singolo piano di congedo e assenza** è abilitata, selezionare un'opzione dal **Tipo di congedo**. 

   > [!IMPORTANT]
   > Dopo aver abilitato questa funzionalità, non è possibile disattivarla.

Se la funzionalità per **utilizzare l'equivalenza a tempo pieno** è abilitata, Human Resources utilizza l'equivalenza a tempo pieno (FTE) definita per la posizione per ripartire l'accumulo di un dipendente. Ad esempio, se FTE è pari a 0,5 e l'importo dell'accumulo è 10, l'impiegato accumulerà 5. È possibile utilizzare questa funzionalità solo se si abilitano più tipi di congedo.  

5. Selezionare **Salva**.

## <a name="accrue-time-off-based-on-hours-worked"></a>Accumulare tempo libero in base alle ore di lavoro

Le organizzazioni con dipendenti a ora possono assegnare permessi in base alle ore lavorate anziché in base alla durata del rapporto con l'organizzazione. I dati sulle ore lavorate vengono in genere archiviati in un sistema di gestione dell'orario e delle presenze. È possibile importare le ore regolari e di straordinario lavorate dal sistema di gestione dell'orario e delle presenze e utilizzarle come base per un premio al dipendente.

Quando si selezionano le ore lavorate come tipo di accumulo, è possibile usare due tipi di ore per l'accumulo regolari e di straordinario. L'elaborazione dell'accumulo dei piani basati sulle ore lavorate utilizza la frequenza di accumulo, insieme alla base del periodo di accumulo, per determinare le ore da accumulare.

### <a name="annual-accrual-frequency"></a>Frequenza di accumulo annuale

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2000                | 0                 |


### <a name="monthly-accrual-frequency"></a>Frequenza di accumulo mensile

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 1/8/2018-31/8/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 1/8/2018-31/8/2018   | 184                 | 3                   |

### <a name="semi-monthly-accrual-frequency"></a>Frequenza di accumulo semestrale

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 75                  | 0                   |

### <a name="weekly-accrual-frequency"></a>Frequenza di accumulo settimanale

| Data concessione accumulo    | Livello ore lavorate    | Importo accumulo        | Date ore lavorate   | Ore lavorate effettive| Premio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 35                  | 0                   |

### <a name="employee-assigned-leave-plans"></a>Piani di congedo assegnati del dipendente

Nei piani di congedo assegnati del dipendente la base del livello e il tipo di ore sono visualizzati per i piani di ore lavorate. Anche le ore lavorate effettive per i periodi di accumulo a partire dalla data corrente vengono visualizzate per i piani attivi.

### <a name="loading-data"></a>Caricamento dati

È possibile importare le ore effettive utilizzando l'entità **Ore di assenza e di congedo lavorate** nella gestione dei dati. Se si utilizzano calendari orario di lavoro, l'importazione verifica che le ore di lavoro normali non superino le ore previste in un giorno definito dal calendario. L'importazione verifica anche che le ore lavorate in un determinato giorno non superino le 24 ore. 

Le seguenti informazioni sono necessarie per importare le ore effettive da utilizzare nel processo di accumulo per il congedo:

- Numero dipendente 
- Data lavorata
- Tipo
- Ore

Una singola data può avere solo uno di ogni tipo associato.

| Numero dipendente       | Data lavorata           | Tipo                  | Ore                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Orario regolare               | 8                    |       
| 000337                | 8/7/2018             | Orario regolare               | 8                    |
| 000337                | 8/7/2018             | Straordinario              | 3                    |
| 000337                | 8/8/2018             | Orario regolare               | 8                    |
| 000337                | 8/7/2018             | Orario regolare               | 8                    |
| 000337                | 8/9/2018             | Orario regolare               | 8                    |

## <a name="enrollments-and-balances"></a>Iscrizioni e saldi

### <a name="enrollment-date"></a>Data di iscrizione

La data di iscrizione determina quando un dipendente può iniziare ad accumulare permessi. Ad esempio, un dipendente iscritto a un piano di ferie il 15 giugno 2018, non può accumulare permessi prima del 15 giugno 2018.

### <a name="current-balance"></a>Saldo corrente

Il saldo corrente è l'importo di congedo disponibile per le richieste di permesso. Questo importo include accumuli, richieste approvate e rettifiche fino alla data corrente.

### <a name="current-balance-examples"></a>Esempi di saldo corrente

#### <a name="annual-plan"></a>Piano annuale

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuale            | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 1° gennaio 2019 (1/1/2019) in modo da includere l'intero periodo.

**Risultati**

| Importo accumulo | Saldo minimo | Riporto massimo | Importo richiesta | Saldo corrente (al 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Saldo corrente (160) = Importo accumulo (200) – Importo richiesta (40)

#### <a name="semimonthly-plan"></a>Piano quindicinale

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Quindicinale       | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 1° maggio 2018 (5/1/2018) in modo da includere l'intero periodo.

**Risultati**

| Importo accumulo | Saldo minimo | Riporto massimo | Importo richiesta | Saldo corrente (al 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Saldo corrente (22) = Importo accumulo (5 × 6) – Importo richiesta (8)

#### <a name="monthly-plan"></a>Piano mensile

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Quindicinale       | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 1° maggio 2018 (5/1/2018) in modo da includere l'intero periodo.

**Risultati**

| Importo accumulo | Saldo minimo | Riporto massimo | Importo richiesta | Saldo corrente (al 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Saldo corrente (7) = Importo accumulo (5 × 3) – Importo richiesta (8)

### <a name="forecasted-balance"></a>Saldo previsto

Il *saldo previsto* è l'importo di congedo disponibile in una data futura. Gli accumuli e le rettifiche di riporto sono previste fino a tale data.

Human Resources utilizza la seguente formula:

Saldo previsto lunedì = Saldo corrente – Richieste + Accumuli – Rettifica di riporto

### <a name="forecasted-balance-examples"></a>Esempi di saldo previsto

#### <a name="annual-plan"></a>Piano annuale

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuale            | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 15° febbraio 2019 (2/15/2019) in modo da includere l'intero periodo.

**Risultati**

| Importo accumulo | Saldo minimo | Riporto massimo | Saldo corrente | Saldo previsto (al 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Saldo previsto (40) = Saldo accumulo (20) + Saldo corrente (40) – Rettifica di riporto (20)

#### <a name="semimonthly-plan"></a>Piano quindicinale

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Quindicinale       | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 15° febbraio 2019 (2/15/2019) in modo da includere l'intero periodo.

**Risultati**

| Importo accumulo | Saldo minimo | Riporto massimo | Saldo corrente | Saldo previsto (al 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Saldo previsto (35) = Saldo accumulo (5 × 3) + Saldo corrente (40) – Rettifica di riporto (20)

#### <a name="monthly-plan"></a>Piano mensile

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Quindicinale       | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 15° febbraio 2019 (2/15/2019) in modo da includere l'intero periodo.

**Risultati**

| Importo accumulo | Saldo minimo | Riporto massimo | Saldo corrente | Saldo previsto (al 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Saldo previsto (30) = Saldo accumulo (10 × 1) + Saldo corrente (40) – Rettifica di riporto (20)

### <a name="proration-balance-examples"></a>Esempi di saldo ripartizione

#### <a name="prorated-monthly-plan"></a>Piano mensile ripartito

**Configurazione piano**

| Data di inizio piano | Frequenza accumulo | Base periodo di accumulo |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensile           | Data di inizio piano      |

**Risultati**

| Dipendente            | Mesi di servizio | Data di iscrizione | Data di inizio | Importo accumulo | Accumulo processo | Stato patrimoniale |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.53    |

#### <a name="full-accrual-monthly-plan"></a>Piano mensile accumulo completo

**Configurazione piano**

| Data di inizio piano | Frequenza accumulo | Base periodo di accumulo |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensile           | Data di inizio piano      |

**Risultati**

| Dipendente            | Mesi di servizio | Data di iscrizione | Data di inizio | Importo accumulo | Accumulo processo | Stato patrimoniale |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Piano mensile senza accumulo

**Configurazione piano**

| Data di inizio piano | Frequenza accumulo | Base periodo di accumulo |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensile           | Data di inizio piano      |

**Risultati**

| Dipendente            | Mesi di servizio | Data di iscrizione | Data di inizio | Importo accumulo | Accumulo processo | Stato patrimoniale |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3.00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 2.00    |

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md)
- [Accumulare piani di congedo e assenza](hr-leave-and-absence-accrue.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
