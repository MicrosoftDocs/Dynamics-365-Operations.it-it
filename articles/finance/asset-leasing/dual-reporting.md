---
title: Doppio reporting
description: In questo argomento viene illustrato un esempio che mostra come soddisfare i requisiti sia per la creazione di report International Financial Reporting Standard (IFRS) sia per il reporting statutario nel leasing di cespiti.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d6daa43178625316a40427728e7e4186691cc13c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229552"
---
# <a name="dual-reporting"></a>Doppio reporting

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato un esempio che mostra come soddisfare i requisiti sia per la creazione di report International Financial Reporting Standard (IFRS) sia per il reporting statutario nel leasing di cespiti. La conoscenza dei livelli di registrazione in Microsoft Dynamics 365 Finance è obbligatoria e renderà l'esempio più facile da capire.

## <a name="example"></a>Esempio

Il seguente esempio utilizza un leasing ai sensi del reporting statutario italiano utilizzando sia il metodo di cassa sia i metodi di reporting IFRS. L'azienda deve stabilire tre libri contabili per tenere conto sia dei requisiti legali italiani che dei requisiti IFRS 16. Un libro è richiesto per l'IFRS 16, un libro è richiesto per i requisiti legali e un libro è richiesto per stornare automaticamente le registrazioni statutarie. I libri sono configurati come mostrato nelle tabelle seguenti.

**Libro IFRS 16**

Il libro IFRS 16 è configurato in modo da essere conforme al principio contabile IFRS 16. Tutte le voci registrate in questo libro verranno registrate su un livello personalizzato.

| Nome                                    | Descrizione    |
|-----------------------------------------|----------------|
| Tipo libro                               | IFRS 16        |
| Descrizione del libro                        | IFRS 16        |
| Livello di registrazione                           | Livello personalizzato 1 |
| Tipo di leasing                              | Finance        |
| Framework di contabilità                    | IFRS 16        |
| Configurazione termine del leasing/vita utile         | 0,00           |
| Configurazione valore corrente/valore equo cespite | 0,00           |
| Soglia a breve termine                    | 12             |
| Soglia valore basso                     | 5,000.00       |
| Pagamento al fornitore                           | Nessuno             |

**Libro statutario**

Il libro statutario è un libro di cassa in cui la società contabilizzerà le spese di leasing come l'importo in contanti che viene pagato ogni mese per l'affitto. Questo libro non produrrà un Asset Right of use un'obbligazione sul leasing.

| Nome                                    | Descrizione |
|-----------------------------------------|-------------|
| Tipo libro                               | Statutario   |
| Descrizione del libro                        | GAAP locale  |
| Livello di registrazione                           | Correnti     |
| Tipo di leasing                              | Automatica   |
| Framework di contabilità                    | Cassa  |
| Configurazione termine del leasing/vita utile         | 0,00        |
| Configurazione valore corrente/valore equo cespite | 0,00        |
| Soglia a breve termine                    | 0           |
| Soglia valore basso                     | 0           |
| Pagamento al fornitore                           | Nessuno          |

**Libro storno statutario**

Il libro di storno statutario è configurato allo stesso modo del libro statutario.

| Nome                                    | Descrizione                    |
|-----------------------------------------|--------------------------------|
| Tipo libro                               | Statutario - Storno           |
| Descrizione del libro                        | Libro per stornare libro statutario |
| Livello di registrazione                           | Livello personalizzato 1                 |
| Tipo di leasing                              | Automatica                      |
| Framework di contabilità                    | Cassa                     |
| Configurazione termine del leasing/vita utile         | 0,00                           |
| Configurazione valore corrente/valore equo cespite | 0,00                           |
| Soglia a breve termine                    | 0                              |
| Soglia valore basso                     | 0                              |
| Pagamento al fornitore                           | Nessuno                             |

Per questo esempio, è stato creato un contratto di leasing con le seguenti impostazioni nelle schede **Generale** e **Righe scadenzario pagamenti**.

**Scheda Generale**

| Campo                      | Valore            |
|----------------------------|------------------|
| Tasso incrementale di prestito | 5%               |
| Data di inizio          | 1/1/2020         |
| Gruppo di leasing                | Edifici        |
| Fornitore                     | 1001             |
| Valore equo del cespite    | 245,000          |
| Vita utile del cespite          | 120              |
| Tipo di rendita finanziaria               | Rendita finanziaria posticipata |
| Intervallo interessi composti       | Ogni mese          |

**Scheda Righe scadenzario pagamenti**

| Campo             | Valore      |
|-------------------|------------|
| Data di inizio        | 1/1/2020   |
| Intervallo periodico   | Mesi     |
| Periodi           | 24         |
| Data di fine          | 31/12/2020 |
| Frequenza pagamenti | Ogni mese    |
| Importo pagamento    | 1.000      |

Per contabilizzare questo leasing in due framework, utilizza un livello di registrazione corrente e un livello di registrazione personalizzato. La tabella seguente mostra un esempio di ogni registrazione a giornale il cui obbligo era di rappresentare equamente i dati finanziari in ogni standard di reporting. Successivamente viene fornita una descrizione dettagliata di ciascuna registrazione a giornale per il primo mese del contratto di leasing.

<table>
<thead>
<tr>
<th rowspan='3'>Numero conto</th>
<th rowspan='3'>Descrizione</th>
<th colspan='3'>Libro statutario (livello attuale)</th>
<th rowspan='3'>Totale livello corrente</th>
<th>Libro di storno (livello personalizzato)</th>
<th colspan='4'>Libro IFRS 16 (livello personalizzato)</th>
<th rowspan='3'>Totale livello corrente + livello personalizzato</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
<th>JE-130</th>
<th>JE-140</th>
<th>JE-150</th>
<th>JE-160</th>
<th>JE-170</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Spesa di leasing</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
<td>-1.000,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>2</td>
<td>Commissione bancaria</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Spesa IVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Conto di compensazione</td>
<td>-1.000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
<td>1,000.00</td>
<td></td>
<td>-1.000,00</td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Contabilità fornitori</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Asset ROU</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>22,794.00</td>
<td></td>
<td></td>
<td></td>
<td>22,793.90</td>
</tr>
<tr>
<td>7</td>
<td>Obbligo di leasing finanziario</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>-22.794,00</td>
<td>1,000.00</td>
<td>-94,97</td>
<td></td>
<td>-21.888,87</td>
</tr>
<tr>
<td>8</td>
<td>Interessi passivi</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td>94.97</td>
<td></td>
<td>94.97</td>
</tr>
<tr>
<td>9</td>
<td>Cassa</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Spesa di ammortamento</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>949.75</td>
<td>949.75</td>
</tr>
<tr>
<td>11</td>
<td>Fondo di ammortamento</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-949,75</td>
<td>-949,75</td>
</tr>
</tbody>
</table>

Come mostra la tabella precedente, sono obbligatori tre libri per la rendicontazione ai sensi sia del reporting statutario che del reporting IFRS.

- Il libro legale registra il canone di leasing secondo le regole per la contabilità di cassa nel livello corrente.
- Il libro di storno statutario storna le registrazioni di scrittura contabile.
- Il libro IFRS 16 crea le registrazioni di scrittura contabile obbligatorie ai sensi di IFRS 16.

Devi inserire un leasing solo una volta. È quindi possibile aprire la pagina **Libri** per vedere tutti i libri associati al leasing.

> [!NOTE]
> Quando crei i libri, tutti e tre devono essere associati allo stesso record di leasing.

La prima registrazione a giornale registra le spese di leasing nel libro statutario. È possibile creare i pagamenti in batch o selezionando lo scadenzario pagamenti nel libro statutario.

Per questo esempio, la seguente scrittura contabile viene prodotta per il libro legale dallo scadenzario pagamenti.

### <a name="lease-payment--1312020--je-100"></a>Canone di leasing - 31/01/2020 - JE 100

| Tipo di account | Numero conto | Livello   | Descrizione conto | Dare    | Avere   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 1              | Correnti | Spesa di leasing       | 1,000.00 |          |
| Ledger       | 4              | Correnti | Conto di compensazione    |          | 1,000.00 |

Un addetto alla contabilità fornitori utilizza la funzionalità standard di Dynamics 365 per creare una fattura per pagare il leasing al di fuori del leasing di cespiti. Tuttavia, invece di selezionare **Spese di leasing** come conto in Dare, l'addetto alla contabilità fornitori seleziona un conto di compensazione per generare la seguente voce.

### <a name="ap-process--1312020--je-110"></a>Processo contabilità fornitori - 31/1/2020 - JE 110

| Tipo di account | Numero conto | Livello   | Descrizione conto | Dare    | Avere   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 4              | Correnti | Conto di compensazione    | 1,000.00 |          |
| Ledger       | 2              | Correnti | Commissione bancaria            | 3.00     |          |
| Ledger       | 3              | Correnti | Spesa IVA         | 5.00     |          |
| Fornitore       | 5              | Correnti | Contabilità fornitori    |          | 1,008.00 |

Quando la dichiarazione viene rilasciata al fornitore, segui il normale processo di pagamento. Durante questo processo, viene generata la seguente scrittura contabile.

### <a name="cash-payment--1312020--je-120"></a>Pagamento in contanti - 31/01/2020 - JE 120

| Tipo di account | Numero conto | Livello   | Descrizione conto | Dare    | Avere   |
|--------------|----------------|---------|---------------------|----------|----------|
| Fornitore       | 5              | Correnti | Contabilità fornitori    | 1,008.00 |          |
| Banca         | 9              | Correnti | Cassa                |          | 1,008.00 |

A questo punto, hai contabilizzato completamente questo leasing in base ai requisiti di reporting legali e puoi generare un bilancio di verifica utilizzando il livello corrente. Il sistema restituisce un bilancio di verifica con le seguenti cifre.

<table>
<thead>
<tr>
<th rowspan='3'>Numero conto</th>
<th rowspan='3'>Descrizione</th>
<th colspan='3'>Libro statutario (livello attuale)</th>
<th rowspan='3'>Totale livello corrente</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Spesa di leasing</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
</tr>
<tr>
<td>2</td>
<td>Commissione bancaria</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Spesa IVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Conto di compensazione</td>
<td>-1.000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Contabilità fornitori</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Asset ROU</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>7</td>
<td>Obbligo di leasing finanziario</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>8</td>
<td>Interessi passivi</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>9</td>
<td>Cassa</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Spesa di ammortamento</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>11</td>
<td>Fondo di ammortamento</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
</tbody>
</table>

Se vuoi utilizzare i dati IFRS 16 per eseguire lo stesso bilancio di verifica, le registrazioni a giornale contabili legali devono essere stornate e le registrazioni contabili IFRS 16 devono essere registrate. Per stornare le registrazioni a giornale legali, questo esempio include un libro di storno legale che ha la stessa configurazione del libro legale ma un profilo di registrazione opposto. Ad esempio, il libro statutario ha *addebitato* un conto spese di leasing, ma il libro di storno *accredita* questo account. Queste relazioni sono facilmente definibili nei conti di registrazione del leasing di asset nella pagina **Parametri del leasing di cespiti** (**Leasing di cespiti\> Imposta \> Parametri del leasing di cespiti**).

Quando lo stesso processo utilizzato per il libro legale viene utilizzato per il libro di storno, viene prodotta la seguente registrazione a giornale. La differenza è che il libro di storno registra le registrazioni di storno dal libro statutario. Le voci di storno vengono apportate anche al livello personalizzato. Quando un bilancio di verifica viene eseguito al livello corrente, le registrazioni a giornale di storno non vengono incluse.

### <a name="lease-payment--1312020--je-130"></a>Canone di leasing - 31/01/2020 - JE 130

| Tipo di account | Numero conto | Livello  | Descrizione conto | Dare    | Avere   |
|--------------|----------------|--------|---------------------|----------|----------|
| Ledger       | 4              | Personalizzazione | Conto di compensazione    | 1,000.00 |          |
| Ledger       | 1              | Personalizzazione | Spesa di leasing       |          | 1,000.00 |

Dopo aver eliminato le registrazioni contabili statutarie, registrerai tutte le scritture contabili richieste dall'IFRS 16 nel libro IFRS 16. Queste voci includono la rilevazione iniziale dell'Asset ROU e della passività e la registrazione di interessi e ammortamenti.

### <a name="initial-recognition--112020--je-140"></a>Rilevazione iniziale – 1/1/2020 – JE 140

| Tipo di account | Numero conto | Livello  | Descrizione conto      | Dare     | Avere    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| Ledger       | 6              | Personalizzazione | Asset ROU                | 22,793.90 |           |
| Ledger       | 7              | Personalizzazione | Obbligo di leasing finanziario |           | 22,793.90 |

Il canone di leasing viene registrato come gli altri canoni di leasing. Il motivo per utilizzare il conto di compensazione è garantire che il contante venga accreditato solo una volta.

### <a name="lease-payment--1312020--je-150"></a>Canone di leasing - 31/01/2020 - JE 150

| Tipo di account | Numero conto | Livello  | Descrizione conto      | Dare    | Avere   |
|--------------|----------------|--------|--------------------------|----------|----------|
| Ledger       | 7              | Personalizzazione | Obbligo di leasing finanziario | 1,000.00 |          |
| Ledger       | 4              | Personalizzazione | Conto di compensazione         |          | 1,000.00 |

La scrittura contabile degli interessi passivi viene generata dal piano di ammortamento della passività.

### <a name="interest-expense--1312020--je-160"></a>Interessi passivi – 31/1/2020 – JE 160

| Tipo di account | Numero conto | Livello  | Descrizione conto      | Dare | Avere |
|--------------|----------------|--------|--------------------------|-------|--------|
| Ledger       | 8              | Personalizzazione | Interessi passivi         | 94.97 |        |
| Ledger       | 7              | Personalizzazione | Obbligo di leasing finanziario |       | 94.97  |

La scrittura contabile della spesa di ammortamento viene generata dal piano di ammortamento dei cespiti.

### <a name="depreciation-expense--1312020--je-170"></a>Spesa di ammortamento – 31/1/2020 – JE 170

| Tipo di account | Numero conto | Livello  | Descrizione conto      | Dare  | Avere |
|--------------|----------------|--------|--------------------------|--------|--------|
| Ledger       | 10             | Personalizzazione | Spesa di ammortamento     | 949.75 |        |
| Ledger       | 11             | Personalizzazione | Fondo di ammortamento |        | 949.75 |

Dopo che tutte queste registrazioni contabili sono state create e registrate, vedrai i seguenti valori di "livello personalizzato 1". Nota che l'ultima colonna include la commissione bancaria, la spesa per l'imposta sul valore aggiunto (IVA) e la riduzione del contante dal livello precedente, ma non include le registrazioni contabili del reporting statutario. Pertanto, si ottengono vere funzionalità di doppio reporting. A questo punto, la società deve solo eseguire il bilancio di verifica e combinare il livello corrente e il livello personalizzato per creare un bilancio di verifica IFRS.

| Numero di conto | Descrizione              | Libro statutario\-Livello corrente\-JE\-100\-Dr \(Cr\) | Libro statutario\-Livello corrente\-JE\-110\-Dr \(Cr\) | Libro statutario\-Livello corrente\-JE\-120\-Dr \(Cr\) | Livello corrente \- Totali | - | Libro di storno\-Livello personalizzato\-JE\-130\-Dr \(Cr\) | Libro IFRS 16\-Livello personalizzato\-JE\-140\-Dr \(Cr\) | Libro IFRS 16\-Livello personalizzato\-JE\-150\-Dr \(Cr\) | Libro IFRS 16\-Livello personalizzato\-JE\-160\-Dr \(Cr\) | Libro IFRS 16\-Livello personalizzato\-JE\-170\-Dr \(Cr\) | Livello personalizzato \+ Livello corrente \- Totali |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| 1          | Spesa di leasing            | 1,000\.00                                         |                                                   |                                                   | 1,000\.00               |   | \-1.000                                         |                                                |                                                |                                                |                                                | 0\.00                                   |
| 2          | Commissione bancaria                 |                                                   | 3\.00                                             |                                                   | 3\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 3\.00                                   |
| 3          | Spesa IVA              |                                                   | 5\.00                                             |                                                   | 5\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 5\.00                                   |
| 4          | Conto di compensazione         | \-1.000\.00                                       | 1,000\.00                                         |                                                   | 0\.00                   |   | 1.000                                           |                                                | \-1.000                                        |                                                |                                                | 0\.00                                   |
| 5          | Contabilità fornitori         |                                                   | \-1.008\.00                                       | 1,008\.00                                         | 0\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 0\.00                                   |
| 6          | Asset ROU                |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | 22,794                                         |                                                |                                                |                                                | 22,793\.90                              |
| 7          | Obbligo di leasing finanziario |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | \-22.794                                       | 1.000                                          | \-94\.97                                       |                                                | \-21,888\.87                            |
| 8          | Interessi passivi         |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                | 94\.97                                         |                                                | 94\.97                                  |
| 9          | Cassa                     |                                                   |                                                   | \-1.008\.00                                       | \-1.008\.00             |   |                                                 |                                                |                                                |                                                |                                                | \-1.008\.00                             |
| 10         | Spesa di ammortamento     |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | 949\.75                                        | 949\.75                                 |
| 11         | Fondo di ammortamento |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | \-949\.75                                      | \-949\.75                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]