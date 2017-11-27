---
title: "Rivalutazione della valuta in una società di consolidamento"
description: "In questo argomento viene descritto come rivalutare la valuta in una società di consolidamento."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 27059b0d2a781453a7594bdc430005df6ea5c167
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a>Rivalutazione della valuta in una società di consolidamento

[!include[banner](../includes/banner.md)]




Quando si consolidano i dati da una valuta di contabilizzazione a un'altra, è necessario eseguire la rivalutazione della valuta in presenza di una variazione nei tassi di cambio, affinché i saldi dei conti vengano rivalutati correttamente. Quando si consolidano i dati, utilizzare la scheda **Conversione valuta** per selezionare i tassi di cambio iniziali per la conversione durante il processo di consolidamento. Dopo che si è inserito un nuovo tasso di cambio (ad esempio nel mese successivo), è necessario rivalutare i saldi dei conti. I profitti non realizzati o le perdite non realizzate vengono aggiornati di conseguenza, in base al nuovo tasso di cambio e alla data. Nell'esempio riportato di seguito vengono mostrare le registrazioni contabili che vengono create durante il processo.

## <a name="company-setup"></a>Impostazione società
-   **Società operative/di origine (USMF)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.
-   **Società consolidata (CON)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.
    -   **Profitto realizzato** - Conto CoGe 801500
    -   **Perdita realizzata** - Conto CoGe 801600
    -   **Profitto realizzato**- - Conto CoGe 801600
    -   **Perdita realizzata** - Conto CoGe 801400

## <a name="original-transactions"></a>Conversioni originali
### <a name="cash-receipt-transactions-in-usmf"></a>Transazioni di ricevuta in USMF

| Data       | Conto CoGe               | Valuta | Importo |
|------------|------------------------------|----------|--------|
| 11/10/2015 | 110110 – Contanti                | GBP      | 500    |
| 11/10/2015 | 130100 – Contabilità clienti | GBP      | -500   |

## <a name="exchange-rates"></a>Tassi di cambio
| Dalla valuta | Alla valuta | Data di inizio | Tasso di cambio |
|---------------|-------------|------------|---------------|
| EUR           | GBP         | 1/10/2015  | 200           |
| EUR           | GBP         | 1/11/2015  | 150           |
| EUR           | GBP         | 1/12/2012  | 100           |

## <a name="perform-the-consolidation-for-october-2015"></a>Eseguire il consolidamento per ottobre 2015
### <a name="balances-in-the-consolidation-company"></a>Saldi della società di consolidamento

| Conto CoGe | Valuta | Importo | Calcolo    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | 500 EUR × 50%  |
| 130100         | EUR      | -250   | -500 EUR × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a>Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 30 novembre 2015
### <a name="balances-in-the-consolidation-company"></a>Saldi della società di consolidamento

| Conto CoGe | Valuta | Importo  | Calcolo                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333,33  | Importo originale di 500 × 66,6667%  |
| 130100         | EUR      | -333,33 | Importo originale di -500 × 66,6667% |
| 801400         | EUR      | 83,33   | 333,33 – 250                       |
| 801600         | EUR      | -83,33  | -333,33 – (-250)                   |

Verranno visualizzate transazioni aggiuntive per gli importi in valuta di dichiarazione.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a>Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2015 fino al 31 dicembre 2015
### <a name="balances-in-the-consolidation-company"></a>Saldi della società di consolidamento

| Conto CoGe | Valuta | Importo  | Calcolo                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500,00  | Importo originale di 500 × 1                           |
| 130100         | EUR      | -500,00 | Importo originale di -500 × 1                          |
| 801400         | EUR      | 250     | 500 – 333.33 = 166,67 166,67 + 83,33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |






