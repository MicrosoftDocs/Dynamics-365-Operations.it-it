---
title: Concetti di congedo e assenza
description: In questo argomento vengono descritti i concetti di congedo e assenza e il modo in cui sono determinati i saldi permesso.
author: jcart
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: a388e0efe6c19a3aabe04e7fff039ce11ae023c4
ms.openlocfilehash: 563593d6c93b0488c681f5b43004f5c0d22cc004
ms.contentlocale: it-it
ms.lasthandoff: 01/07/2019

---

# <a name="leave-and-absence-concepts"></a>Concetti di congedo e assenza

[!include[banner](../includes/banner.md)]

I concetti e termini descritti in questo argomento consentono di determinare il modo in cui vengono concessi permessi a un dipendente e il modo in cui vengono calcolati i saldi permesso di quel dipendente. Per ulteriori informazioni sulla gestione di congedi e assenze, vedere [Gestione di congedo e assenza](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).

## <a name="leave-plan-details"></a>Dettagli del piano di congedo

### <a name="start-date"></a>Data di inizio

La data di inizio è la data in cui ha inizio l'elaborazione degli accumuli. La data di inizio funge anche da data di ricorrenza utilizzata per calcolare gli importi riportabili in avanti.

## <a name="accruals"></a>Ratei

Gli accumuli determinano quando e con quale frequenza vengono concessi permessi a un dipendente. I criteri relativi a quando gli accumuli devono essere concessi e quelli relativi alla ripartizione sono definiti nella sezione **Accumuli** quando si configura il piano di congedo e assenza.

### <a name="accrual-frequency"></a>Frequenza dell'accumulo

La frequenza dell'accumulo definisce la frequenza di accumulo o concessione di congedi. Sono disponibili le opzioni seguenti:

- Giornaliera
- Settimanale
- Bisettimanale
- Quindicinale
- Mensile
- Trimestrale
- Biennale
- Annualmente
- Nessuna priorità

### <a name="accrual-period-basis"></a>Base del periodo di accumulo

La base del periodo di accumulo determina la data che viene utilizzata per calcolare i periodi di accumulo. Sono disponibili le opzioni seguenti:

- **Data di inizio piano**
- **Data specifica dipendente** - Quando questa opzione è selezionata, il valore determina l'origine del valore di data iniziale utilizzato per calcolare i periodi di accumulo. Sono disponibili le opzioni seguenti:

    - Personalizzata
    - Data di ricorrenza annuale
    - Data di assunzione originale
    - Data di anzianità
    - Data di inizio rettificata del lavoratore
    - Data di inizio del lavoratore

### <a name="accrual-award-date"></a>Data concessione accumulo

La data di concessione accumulo determina quando a un dipendente viene concesso un permesso. Sono disponibili le opzioni seguenti:

- **Fine del periodo di accumulo** - Al dipendente verrà concesso un permesso l'ultimo giorno del periodo di premio.

    Per accumulare l'importo corretto, il processo di accumulo deve includere l'intero periodo. Ad esempio, il periodo di accumulo va dal 1° gennaio 2018 al 31 gennaio 2018. In questo caso, affinché gennaio sia incluso, l'accumulo deve essere eseguito per il 1° febbraio 2018.

- **Inizio del periodo di accumulo** - Al dipendente verrà concesso un permesso il primo giorno del periodo di premio.

### <a name="accrual-policy-on-enrollment"></a>Criteri di accumulo all'iscrizione

I criteri di accumulo all'iscrizione definiscono il modo di calcolo dell'accumulo quando un dipendente viene iscritto a metà di un periodo di accumulo. Sono disponibili le opzioni seguenti:

- **Ripartito** - L'intervallo di date tra la data di iscrizione e la data di inizio viene utilizzato per determinare la differenza in giorni. Tale differenza viene applicata quando si elaborano gli accumuli.
- **Accumulo completo** - L'importo di accumulo completo, basato sul livello, viene concesso durante la prima elaborazione dell'accumulo.
- **Nessun accumulo** - Non viene concesso alcun accumulo fino al periodo di accumulo successivo.

### <a name="accrual-policy-on-unenrollment"></a>Criteri di accumulo all'annullamento dell'iscrizione

I criteri di accumulo all'annullamento dell'iscrizione definiscono il modo di calcolo dell'accumulo quando l'iscrizione di un dipendente viene annullata a metà di un periodo di accumulo. Sono disponibili le opzioni seguenti:

- **Ripartito** - L'intervallo di date tra la data di iscrizione e la data di inizio viene utilizzato per determinare la differenza in giorni. Tale differenza viene applicata quando si elaborano gli accumuli.
- **Accumulo completo** - L'importo di accumulo completo, basato sul livello, viene concesso durante la prima elaborazione dell'accumulo.
- **Nessun accumulo** - Non viene concesso alcun accumulo fino al periodo di accumulo successivo.

## <a name="accrual-schedule"></a>Programmazione dell'accumulo

La programmazione dell'accumulo determina il modo in cui un dipendente accumula permessi e gli importi che il dipendente accumulerà e riporterà. È possibile creare livelli di modo che i permessi siano concessi in base a livelli differenti.

### <a name="months-of-service"></a>Mesi di servizio

Il valore **Mesi di servizio** definisce il numero minimo di mesi che i dipendenti devono lavorare per avere diritto ad accumuli. Se non è richiesto un minimo per i dipendenti, impostare il valore su **0**.

### <a name="hours-worked"></a>Ore lavorate

Il valore **Ore lavorate** definisce il numero minimo di ore che i dipendenti devono lavorare per periodo di accumulo per avere diritto ad accumuli. Se non è richiesto un minimo per i dipendenti, impostare il valore su **0**.

### <a name="accrual-amount"></a>Importo accumulo

L'importo di accumulo è il numero di ore o giorni che i dipendenti accumuleranno per periodo. Il periodo è basato sulla frequenza dell'accumulo.

### <a name="minimum-balance"></a>Saldo minimo

Un valore negativo può essere utilizzato per il saldo minimo se i dipendenti possono richiedere più congedi di quelli disponibili.

### <a name="maximum-carry-forward"></a>Riporto massimo

Il processo di accumulo rettificherà i saldi congedo che superano il saldo riporto massimo alla ricorrenza della data di inizio.

### <a name="grant-amount"></a>Importo concesso

L'importo concesso è il numero iniziale di ore o giorni concessi ai dipendenti quando si iscrivono per la prima volta al piano di congedo. Non si ha accumulo dell'importo per ogni periodo di accumulo.

## <a name="enrollments-and-balances"></a>Iscrizioni e saldi

### <a name="enrollment-date"></a>Data di iscrizione

La data di iscrizione determina quando un dipendente può iniziare ad accumulare permessi. Ad esempio, se un dipendente viene iscritto a un piano di ferie il 15 giugno 2018, non può accumulare permessi prima del 15 giugno 2018.

### <a name="current-balance"></a>Saldo corrente

Il saldo corrente è l'importo di congedo disponibile per le richieste di permesso. Questo importo include accumuli, richieste approvate e rettifiche fino alla data corrente.

### <a name="current-balance-examples"></a>Esempi di saldo corrente

#### <a name="annual-plan"></a>Piano annuale

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuale            | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 1° gennaio 2019 (1/1/2019), di modo che sia incluso l'intero periodo.

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

Gli accumuli sono elaborati il 1° maggio 2018 (1/5/2018), di modo che sia incluso l'intero periodo.

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

Gli accumuli sono elaborati il 1° maggio 2018 (1/5/2018), di modo che sia incluso l'intero periodo.

**Risultati**

| Importo accumulo | Saldo minimo | Riporto massimo | Importo richiesta | Saldo corrente (al 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Saldo corrente (7) = Importo accumulo (5 × 3) – Importo richiesta (8)

### <a name="forecasted-balance"></a>Saldo previsto

Il *saldo previsto* è l'importo di congedo disponibile in una data futura. Gli accumuli e le rettifiche di riporto sono previste fino a tale data.

Viene utilizzata la seguente formula:

Saldo previsto lunedì = Saldo corrente – Richieste + Accumuli – Rettifica di riporto

### <a name="forecasted-balance-examples"></a>Esempi di saldo previsto

#### <a name="annual-plan"></a>Piano annuale

**Configurazione piano**

| Data di inizio piano | Data di iscrizione | Frequenza accumulo | Base periodo di accumulo | Data concessione accumulo    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuale            | Data di inizio piano      | Fine del periodo di accumulo |

Gli accumuli sono elaborati il 15 febbraio 2019 (15/2/2019), di modo che sia incluso l'intero periodo.

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

Gli accumuli sono elaborati il 15 febbraio 2019 (15/2/2019), di modo che sia incluso l'intero periodo.

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

Gli accumuli sono elaborati il 15 febbraio 2019 (15/2/2019), di modo che sia incluso l'intero periodo.

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
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.00    |

