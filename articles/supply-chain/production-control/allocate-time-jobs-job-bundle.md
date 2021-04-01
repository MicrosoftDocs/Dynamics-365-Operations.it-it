---
title: Allocare tempo ai processi in un'aggregazione di processi
description: In Esecuzione produzione, è possibile aggregare i processi. È quindi possibile avviare più processi contemporaneamente nella pagina Elenco processi.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgBundleSlize, JmgProdParameters, JmgRegistration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55591
ms.assetid: 358efce7-73c8-4d2a-a7f7-cb99b88ab6ee
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88c75c67cadcde57f981f4e357b40855709d072d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246503"
---
# <a name="allocate-time-to-jobs-in-a-job-bundle"></a>Allocare tempo ai processi in un'aggregazione di processi

[!include [banner](../includes/banner.md)]

In Esecuzione produzione, è possibile aggregare i processi. È quindi possibile avviare più processi contemporaneamente nella pagina Elenco processi.

Se si aggregano processi, è necessario definire come il tempo totale registrato per tutti i processi deve essere allocato a ciascun processo. È possibile definire l'allocazione selezionando una delle seguenti opzioni nel campo **Tipo di aggregazione** nella pagina **Chiavi di allocazione**:

-   **Stima**: il tempo viene suddiviso tra i processi in base al tempo stimato per ogni processo.
-   **Processi**: il tempo viene suddiviso in base ai processi totali aggregati e al tempo impiegato per completare tutti i processi.
-   **Tempo netto**: il tempo viene suddiviso equamente tra i processi inclusi nell'aggregazione in qualsiasi momento.
-   **Tempo reale**: viene allocato il tempo effettivo per un processo. Il costo può essere calcolato sulla base del costo di retribuzione effettivo. **Nota:** la chiave di allocazione **Tempo reale** è disponibile solo se la società utilizza la funzionalità di retribuzione in Orario e presenze.

Negli esempi seguenti vengono illustrati i risultati delle diverse chiavi di allocazione.

## <a name="example-scenario"></a>Scenario di esempio
È necessario completare tre processi nella coda processi. Si inizia il primo processo e, mentre questo è in corso, si passa al secondo e al terzo. Di conseguenza, si tratta di un'aggregazione di tre processi. Nella seguente tabella viene visualizzato il tempo di produzione stimato per ciascun processo.

| Posizione lavorativa   | Tempo di produzione |
|-------|-----------------|
| Processo 1 | 1 ora          |
| Processo 2 | 3 ore         |
| Processo 3 | 4 ore         |
| Totale | 8 ore         |

Nella seguente tabella vengono illustrate le ore lavorative effettive impiegate per eseguire ciascun processo.

| Posizione lavorativa    | Ora di inizio | Ora di fine | Tempo di aggregazione |
|--------|------------|----------|-------------|
| Processo 1  | 09:00:00      | 11.00    | 2 ore     |
| Processo 2  | 10.00      | 13.00    | 3 ore     |
| Processo 3  | 10.00      | 15:00:00    | 5 ore     |
| Aggregazione | 09:00:00      | 15:00:00    | 6 ore     |

Nelle sezioni seguenti vengono descritti i risultati del tempo calcolato per ogni chiave di allocazione.

## <a name="estimation-allocation-key"></a>Chiave di allocazione Stima
Nella seguente tabella viene illustrata la formula per calcolare il tempo allocato, Formula: Tempo per processo = Tempo totale di aggregazione × (Tempo processo stimato ÷ Tempo stimato totale)

| Processo   | Formula           | Tempo allocato |
|-------|-------------------|----------------|
| Processo 1 | 6 × (1 ÷ 8) ore | 0,75 ore      |
| Processo 2 | 6 × (3 ÷ 8) ore | 2,25 ore     |
| Processo 3 | 6 × (4 ÷ 8) ore | 3,00 ore     |

## <a name="jobs-allocation-key"></a>Chiave di allocazione Processi
Nella seguente tabella viene illustrata la formula per calcolare il tempo allocato, Formula: Tempo per processo = Tempo totale di aggregazione ÷ Numero di processi

| Processo   | Formula | Tempo allocato |
|-------|---------|----------------|
| Processo 1 | 6 ÷ 3   | 2 ore        |
| Processo 2 | 6 ÷ 3   | 2 ore        |
| Processo 3 | 6 ÷ 3   | 2 ore        |

## <a name="net-time-allocation-key"></a>Chiave di allocazione Tempo netto
Nella seguente tabella viene illustrata la formula per calcolare il tempo allocato, Formula: Tempo calcolato per report = Tempo di aggregazione ÷ Numero di processi

|                              | 09.00–10.00 (1 ora) | 10.00–11.00 (1 ora) | 11.00–13.00 (2 ore) | 13.00–15.00 (2 ore) | Tempo allocato |
|------------------------------|----------------------|----------------------|-----------------------|-----------------------|----------------|
| Numero di processi inclusi nell'aggregazione | 1                    | 3                    | 2                     | 1                     | Non applicabile |
| Processo 1                        | 1 ÷ 1 = 1 ora       | 1 ÷ 3 = 0,33 ore    | Non applicabile        | Non applicabile        | 1,33 ore     |
| Processo 2                        | Non applicabile       | 1 ÷ 3 = 0,33 ore    | 2 ÷ 2 = 1 ora        | Non applicabile        | 1,33 ore     |
| Processo 3                        | Non applicabile       | 1 ÷ 3 = 0,33 ore    | 2 ÷ 2 = 1 ora        | 2 ÷ 1 = 2 ore       | 3,33 ore     |

## <a name="real-time-allocation-key"></a>Chiave di allocazione Tempo reale
Se si desidera che i costi di produzione vengano calcolati in base ai costi reali, è necessario deselezionare l'opzione **Categoria costi** nella pagina **Impostazioni predefinite ordini di produzione**. Nella seguente tabella viene illustrata la formula per calcolare il tempo allocato, Formula: Tempo effettivo per processo = Tempo effettivo in aggregazione

| Processo   | Ora effettiva |
|-------|-------------|
| Processo 1 | 2 ore     |
| Processo 2 | 3 ora     |
| Processo 3 | 5 ore     |

Si supponga che un lavoratore abbia eseguito tre processi con una retribuzione oraria di 12,00 USD e senza alcuno straordinario o premio per il tempo impiegato nei processi. Per questi tre processi aggregati sono state impiegate in totale sei ore. Il costo della paga sarà quindi pari a 6 × 12,00 USD = 72,00 USD. Quando si utilizza un'allocazione Tempo reale, il costo orario viene ricalcolato con il fattore ottenuto dalla formula tempo netto. Viene quindi trasferito il tempo effettivo impiegato per ciascun processo con il prezzo di costo orario corretto. Nell'esempio sono state allocate dieci ore, ma ne sono state impiegate sei. Nella seguente tabella viene illustrata la formula per calcolare il costo, Formula: Costo orario = (Tempo totale di aggregazione per processo (tempo netto) ÷ Tempo effettivo per processo) × Prezzo di costo orario standard

| Processo   | Calcolo del costo orario corretto | Costo orario corretto | Tempo allocato | Costo totale del processo |
|-------|----------------------------------------|-------------------------|----------------|-------------------|
| Processo 1 | (1,33 ÷ 2) × USD 12,00                 | USD 8,00                | 2 ore        | USD 16,00         |
| Processo 2 | (1,33 ÷ 3) × USD 12,00                 | USD 5,33                | 3 ora        | USD 16,00         |
| Processo 3 | (3,33 ÷ 5) × USD 12,00                 | USD 8,00                | 5 ore        | USD 40,00         |

Il costo orario corretto e il tempo necessario per il processo vengono registrati in un giornale di registrazione produzione. **Nota:** se si seleziona l'opzione **Categoria costi** nella scheda **Generale** della pagina **Impostazioni predefinite ordini di produzione**, l'ora effettiva per ciascun processo viene trasferita in un giornale di registrazione produzione, in cui il costo è applicato alla categoria di costi del processo specifico.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]