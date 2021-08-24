---
title: Funzionalità di intervallo composto
description: Questo argomento fornisce informazioni che ti aiuteranno a scegliere tra intervalli composti mensili, trimestrali, semestrali e annuali.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d0f01748d370dfa5351ceb007a630564ca5d3a76c142830f32ce11951db9088
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716695"
---
# <a name="compounding-interval-functionality"></a>Funzionalità di intervallo composto

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento fornisce informazioni che ti aiuteranno a scegliere tra intervalli composti mensili, trimestrali, semestrali e annuali. La funzionalità dell'intervallo composto viene utilizzata per determinare il numero di periodi composti all'anno nello scadenziario di pagamento di un leasing. Ciascuno dei quattro esempi in questo argomento mostra come apparirà lo scadenziario del pagamento di un leasing per un intervallo diverso.

Non è possibile selezionare un intervallo composto meno frequente della frequenza di pagamento del leasing. Ad esempio, un intervallo composto trimestrale non può essere utilizzato con una frequenza di pagamento mensile e un intervallo di composizione annuale non può essere utilizzato con una frequenza di pagamento semestrale. Se tenti di selezionare un intervallo composto meno frequente della frequenza di pagamento del leasing, ricevi un messaggio di errore.

> [!NOTE]
> In tutti e quattro gli esempi in questo argomento, l'intervallo composto corrisponde alla frequenza di pagamento.

## <a name="examples"></a>Esempi

### <a name="setup-for-all-four-leases"></a>Configurazione per tutti e quattro i leasing

Le tabelle seguenti mostrano i valori impostati nelle schede **Generale** e **Righe scadenzario pagamenti** per i quattro contratti leasing utilizzati negli esempi.

**Scheda Generale**

| Campo                      | Valore                        |
|----------------------------|------------------------------|
| Tasso incrementale di prestito | **5%**                       |
| Tipo di rendita finanziaria               | **Rendita finanziaria posticipata**         |
| Intervallo interessi composti       | Vedi i singoli esempi. |
| Frequenza pagamenti          | **Ogni mese**                  |
| Data di inizio          | **1/1/2020**                 |

**Scheda Righe scadenzario pagamenti**

| Campo             | Valore                        |
|-------------------|------------------------------|
| Data di inizio        | **1/1/2020**                 |
| Periodi           | **120**                      |
| Intervallo periodico   | **Mesi**                   |
| Data di fine          | **12/31/2029**               |
| Frequenza pagamenti | Vedi i singoli esempi. |
| Importo pagamento    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>Leasing 1: intervallo composto mensile e frequenza di pagamento mensile

La tabella seguente elenca i primi 12 mesi dello scadenziario pagamenti. Considerare i seguenti dettagli:

- Il valore nella colonna "Periodo" aumenta di 1 ogni mese, poiché ogni mese è un nuovo intervallo composto.
- Nella formula nella colonna "Valore attuale", il tasso è diviso per 12, perché ci sono 12 periodi composti all'anno. L'esponente (ovvero il numero in apice) è uguale al valore nella colonna "Periodo".

| Periodo | Mese | Data       | Importo pagamento | Valore corrente                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 31/1/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>1</sup> = 49.792,53  |
| 2      | 2     | 29/2/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>2</sup> = 49.585,92  |
| 3      | 3     | 31/3/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>3</sup> = 49.380,17  |
| 4      | 4     | 30/4/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>4</sup> = 49.175,28  |
| 5      | 5     | 31/5/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>5</sup> = 48.971,23  |
| 6      | 6     | 30/6/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>6</sup> = 48.768,03  |
| 7      | 7     | 31/7/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>7</sup> = 48.565,67  |
| 8      | 8     | 31/8/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>8</sup> = 48.364,15  |
| 9      | 9     | 30/9/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>9</sup> = 48.163,47  |
| 10     | 10    | 31/10/2020 | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>10</sup> = 47.963,62 |
| 11     | 11    | 30/11/2020 | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>11</sup> = 47.764,61 |
| 12     | 12    | 31/12/2020 | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>12</sup> = 47.566,41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>Leasing 2: intervallo composto mensile e frequenza di pagamento mensile

La tabella seguente elenca i primi 12 mesi dello scadenziario pagamenti. Considerare i seguenti dettagli:

- Il valore nella colonna "Periodo" aumenta di 1 ogni tre mesi (ovvero ogni trimestre), poiché ogni trimestre è un nuovo intervallo composto.
- Nella formula nella colonna "Valore attuale", il tasso è diviso per 4, perché ci sono 4 periodi composti all'anno. L'esponente è uguale al valore nella colonna "Periodo".

| Periodo | Mese | Data       | Importo pagamento | Valore corrente                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 49.382,72 |
| 2      | 4     | 30/4/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 31/5/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 30/6/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 48.773,05 |
| 3      | 7     | 31/7/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 31/8/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 30/9/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 48.170,92 |
| 4      | 10    | 31/10/2020 | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 30/11/2020 | 0,00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 31/12/2020 | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 47.576,21 |

> [!NOTE]
> Se il tipo di rendita viene modificato in **Rendita dovuta**, il pagamento avverrà all'inizio del trimestre anziché alla fine del trimestre.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>Leasing 3: intervallo composto bimestrale e frequenza di pagamento bimestrale

La tabella seguente elenca i primi 12 mesi dello scadenziario pagamenti. Considerare i seguenti dettagli:

- Il valore nella colonna "Periodo" aumenta di 1 ogni sei mesi (ovvero ogni semestre), poiché ogni semestre è un nuovo intervallo composto.
- Nella formula nella colonna "Valore attuale", il tasso è diviso per 2, perché ci sono due periodi composti all'anno. L'esponente è uguale al valore nella colonna "Periodo".

| Periodo | Mese | Data       | Importo pagamento | Valore corrente                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 30/4/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 31/5/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 30/6/2020  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 48.780,49 |
| 2      | 7     | 31/7/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 31/8/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 30/9/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 31/10/2020 | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 30/11/2020 | 0,00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 31/12/2020 | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 47.590,72 |

> [!NOTE]
> Se il tipo di rendita viene modificato in **Rendita dovuta**, il pagamento avverrà a gennaio e luglio anziché a giugno e dicembre.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>Leasing 4: intervallo composto annuale e frequenza di pagamento annuale

La tabella seguente elenca i primi 12 mesi dello scadenziario pagamenti. Considerare i seguenti dettagli:

- Il valore nella colonna "Periodo" aumenta di 1 ogni 12 mesi (ovvero ogni anno), poiché ogni semestre è un nuovo intervallo composto.
- Nella formula nella colonna "Valore attuale", il tasso è diviso per 1, perché c'è un periodo composti all'anno. L'esponente è uguale al valore nella colonna "Periodo".

| Periodo | Mese | Data       | Importo pagamento | Valore corrente                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 30/4/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 31/5/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 30/6/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 31/7/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 31/8/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 30/9/2020  | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 31/10/2020 | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 30/11/2020 | 0,00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 31/12/2020 | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 47.619,05 |

> [!NOTE]
> Se il tipo di rendita viene modificato in **Rendita dovuta**, il pagamento avverrà a gennaio anziché a dicembre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
