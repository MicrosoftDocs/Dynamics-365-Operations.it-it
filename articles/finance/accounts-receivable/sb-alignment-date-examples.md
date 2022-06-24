---
title: Scenari di date di allineamento
description: Questo articolo fornisce esempi che mostrano come funzionano le date di allineamento nella fatturazione abbonamento.
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
ms.openlocfilehash: 102e3a104be5be287f914172160e95aff65d0b18
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872617"
---
# <a name="alignment-date-scenarios"></a>Scenari di date di allineamento

Questo articolo fornisce esempi che mostrano come funzionano le date di allineamento nella fatturazione abbonamento.

Per questi esempi, un dettaglio di fatturazione per un programma di fatturazione ha una data di allineamento del 31 ottobre 2019. Il primo dettaglio di fatturazione per la riga scade il 31 ottobre 2019 e viene ripartito proporzionalmente. La riga si rinnova automaticamente utilizzando una data di inizio rinnovo dell'11 novembre.

> [!NOTE]
> L'anno è rilevante perché può far sì che la data di allineamento sia maggiore o minore di un anno. Per questi esempi, il metodo per la ripartizione è impostato su **Mensile** nella pagina **Parametri di fatturazione contratto ricorrente**. Se fosse impostato su **Giornaliero**, alcuni importi parziali differirebbero.

## <a name="scenario-1-no-alignment"></a>Scenario 1: Nessun allineamento

Il programma di fatturazione è impostato con i seguenti dati:

- **Data di inizio:** 1 maggio 2019
- **Data di fine:** 31 dicembre 2024
- **Importo:** $1.000

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 30/4/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 2020/1/5 | 2021/30/4 | | | 1.00 | | 1.00 | 1,000.00 |
| 2021/1/5 | 2022/30/4 | | | 1.00 | | 1.00 | 1,000.00 |
| 2022/1/5 | 2023/30/4 | | | 1.00 | | 1.00 | 1,000.00 |
| 2023/1/5 | 2024/30/4 | | | 1.00 | | 1.00 | 1,000.00 |
| 2024/1/5 | 2024/31/12 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-2-shortened-alignment"></a>Scenario 2: Allineamento accorciato

Il programma di fatturazione è impostato con i seguenti dati:

- **Data di inizio:** 1 maggio 2019
- **Data di fine:** 31 dicembre 2024
- **Importo:** $1.000
- **Data di allineamento:** 31 dicembre 2019

Il primo importo di rinnovo è inferiore a un anno.

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2019/31/12 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 2021/1/1 | 2021/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2022 | 2022/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 2023/1/1 | 2023/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 2024/1/1 | 2024/31/12 | | | 1.00 | | 1.00 | 1,000.00 |

## <a name="scenario-3-extended-alignment"></a>Scenario 3: Allineamento esteso

Il programma di fatturazione è impostato con i seguenti dati:

- **Data di inizio:** 1 maggio 2019
- **Data di fine:** 31 dicembre 2024
- **Importo:** $1.000
- **Data di allineamento:** 31 dicembre 2020

Il primo importo di rinnovo è superiore a un anno.

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 31/12/2020 | | | 1.00 | | 1.00 | 1,666.67 |
| 2021/1/1 | 2021/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2022 | 2022/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 2023/1/1 | 2023/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 2024/1/1 | 2024/31/12 | | | 1.00 | | 1.00 | 1,000.00 |

## <a name="scenario-4-alignment-with-a-different-end-month"></a>Scenario 4: Allineamento con un mese di fine diverso

Il programma di fatturazione è impostato con i seguenti dati:

- **Data di inizio:** 1 maggio 2019
- **Data di fine:** 31 ottobre 2024
- **Importo:** $1.000
- **Data di allineamento:** 31 dicembre 2019

> [!NOTE]
> Questo scenario non è comune.

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2019/31/12 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 2021/1/1 | 2021/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2022 | 2022/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 2023/1/1 | 2023/31/12 | | | 1.00 | | 1.00 | 1,000.00 |
| 2024/1/1 | 2024/31/10 | | | 1.00 | | 1.00 | 833.33 |

## <a name="scenario-5-single-partial-year"></a>Scenario 5: Singolo anno parziale

Il programma di fatturazione è impostato con i seguenti dati:

- **Data di inizio:** 1 maggio 2019
- **Data di fine:** 31 dicembre 2019
- **Importo:** $1.000
- **Data di allineamento:** 31 dicembre 2019

In questo scenario, la data di allineamento non è necessaria. Questo scenario è comune per i rinnovi automatici.

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2019/31/12 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-6-calculated-dates"></a>Scenario 6: Date calcolate

Il supporto e rinnovo sono impostati con i seguenti dati:

- **Data di inizio sostituzione:** No
- **Date di inizio supporto e rinnovo:** Inizio del prossimo mese
- **Data di registrazione fattura:** 22 giugno 2019
- **Data di allineamento:** 31 dicembre 2020

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/1/7 | 2019/31/7 | | | 1.00 | | 1.00 | 297.60 |
| 2019/1/8 | 31/12/2020 | | | 1.00 | | 1.00 | 6,936.00 |

## <a name="scenario-7-calculated-dates-and-future-posting"></a>Scenario 7: Date calcolate e registrazione futura

Il supporto e rinnovo sono impostati con i seguenti dati:

- **Data di inizio sostituzione:** No
- **Date di inizio supporto e rinnovo:** Inizio del prossimo mese
- **Data di registrazione fattura:** 22 giugno 2019
- **Data di allineamento:** 31 dicembre 2020

Per questo scenario, la data di allineamento viene modificata al 31 dicembre 2021.

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/22/6 | 2019/22/6 | | | 1.00 | | 1.00 | 0,00 |
| 2019/1/8 | 31/12/2020 | | | 1.00 | | 1.00 | 4,250.00 |

## <a name="scenario-8-manual-dates-and-multiple-years"></a>Scenario 8: Date manuali e più anni

Il supporto e rinnovo sono impostati con i seguenti dati:

- **Data di inizio sostituzione:** Sì
- **Data di inizio rinnovo:** 1 luglio 2020
- **Data di fine rinnovo:** 31 dicembre 2024
- **Data di allineamento:** 31 dicembre 2021

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/22/6 | 2019/22/6 | | | 1.00 | | 1.00 | 0,00 |
| 2020/1/7 | 2021/31/12 | | | 1.00 | | 1.00 | 375.00 |
| 1/1/2022 | 2022/31/12 | | | 1.00 | | 1.00 | 250,00 |
| 2023/1/1 | 2023/31/12 | | | 1.00 | | 1.00 | 250,00 |
| 2024/1/1 | 2024/31/12 | | | 1.00 | | 1.00 | 250,00 |

## <a name="scenario-9-manual-dates-multiple-years-and-a-different-end-month"></a>Scenario 9: Date manuali, più anni e un mese di fine diverso

Il supporto e rinnovo sono impostati con i seguenti dati:

- **Data di inizio sostituzione:** Sì
- **Data di inizio rinnovo:** 1 luglio 2020
- **Data di fine rinnovo:** 31 ottobre 2024
- **Data di allineamento:** 31 dicembre 2021

| Data di inizio fatturazione | Data di fine fatturazione | Lettura precedente | Lettura corrente | Quantità immessa | Quantità disponibile | Quantità fatturabile | Prezzo unitario |
|---|---|---|---|---|---|---|---|
| 2019/22/6 | 2019/22/6 | | | 1.00 | | 1.00 | 0,00 |
| 2020/1/7 | 2021/31/12 | | | 1.00 | | 1.00 | 375.00 |
| 1/1/2022 | 2022/31/12 | | | 1.00 | | 1.00 | 250,00 |
| 2023/1/1 | 2023/31/12 | | | 1.00 | | 1.00 | 250,00 |
| 2024/1/1 | 2024/31/10 | | | 1.00 | | 1.00 | 208.33 |

## <a name="scenario-10-alignment-without-proration"></a>Scenario 10: Allineamento senza ripartizione

Il supporto e rinnovo sono impostati con i seguenti dati:

- **Data di inizio sostituzione:** No
- **Data di registrazione fattura:** 22 giugno 2019
- **Data di allineamento:** 31 dicembre 2019

La data di inizio del rinnovo e le date di allineamento vengono modificate in modo che entrambe le date di inizio siano successive alla data di registrazione.

- **Data di inizio rinnovo:** 1 gennaio 2020
- **Data di fine rinnovo:** 31 dicembre 2020
