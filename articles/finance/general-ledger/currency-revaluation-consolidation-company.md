---
title: Rivalutazione della valuta in una società di consolidamento
description: In questo articolo viene descritto come rivalutare la valuta in una società di consolidamento.
author: aprilolson
ms.date: 10/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: twheeloc
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c05ef0d4d05d5113d3b858dafe49ee9c1c7211d9
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779664"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>Rivalutazione della valuta in una società di consolidamento

[!include [banner](../includes/banner.md)]

Quando si consolidano i dati da una valuta di contabilizzazione a un'altra, è necessario eseguire la rivalutazione della valuta in presenza di una variazione nei tassi di cambio, affinché i saldi dei conti vengano rivalutati correttamente. Quando si consolidano i dati, utilizzare la scheda **Conversione valuta** per selezionare i tassi di cambio iniziali per la conversione durante il processo di consolidamento. Dopo che si è inserito un nuovo tasso di cambio (ad esempio nel mese successivo), è necessario rivalutare i saldi dei conti. I profitti non realizzati o le perdite non realizzate vengono aggiornati di conseguenza, in base al nuovo tasso di cambio e alla data. Nell'esempio riportato di seguito vengono mostrare le registrazioni contabili che vengono create durante il processo.

## <a name="company-setup"></a>Impostazione società
-   **Società operative/di origine (USMF)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.
-   **Società consolidata (CON)** - Vengono utilizzati gli euro (EUR) come valuta di contabilità e di dichiarazione.
    -   **Profitto realizzato** - Conto CoGe 801500
    -   **Perdita realizzata** - Conto CoGe 801600
    -   **Profitto realizzato**- - Conto CoGe 801600
    -   **Perdita realizzata** - Conto CoGe 801400

## <a name="original-transactions"></a>Conversioni originali
### <a name="cash-receipt-transactions-in-usmf"></a>Transazioni di ricevuta in USMF

| Data       | Conto CoGe               | Valuta | Importo |
|------------|------------------------------|----------|--------|
| 10/11/2020 | 110110 – Contanti                | USD      | 500    |
| 10/11/2020 | 130100 – Contabilità clienti | USD      | -500   |

## <a name="exchange-rates"></a>Tassi di cambio

| Dalla valuta | Alla valuta | Data di inizio | Tasso di cambio |
|---------------|-------------|------------|---------------|
| EUR           | USD         | 10/1/2020  | 200           |
| EUR           | USD         | 11/1/2020  | 150           |
| EUR           | USD         | 12/1/2017  | 100           |

## <a name="perform-the-consolidation-for-october-2020"></a>Eseguire il consolidamento per ottobre 2020
### <a name="balances-in-the-consolidation-company"></a>Saldi della società di consolidamento

| Conto CoGe | Valuta | Importo | Calcolo    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | 500 EUR × 50%  |
| 130100         | EUR      | -250   | -500 EUR × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-november-30-2020"></a>Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2020 fino al 30 novembre 2020
### <a name="balances-in-the-consolidation-company"></a>Saldi della società di consolidamento

| Conto CoGe | Valuta | Importo  | Calcolo                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333,33  | Importo originale di 500 × 66,6667%  |
| 130100         | EUR      | -333,33 | Importo originale di -500 × 66,6667% |
| 801400         | EUR      | 83,33   | 333,33 – 250                       |
| 801600         | EUR      | -83,33  | -333,33 – (-250)                   |

Verranno visualizzate transazioni aggiuntive per gli importi in valuta di dichiarazione.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-december-31-2020"></a>Eseguire la rivalutazione della valuta per i conti dal 1° ottobre 2020 fino al 31 dicembre 2020
### <a name="balances-in-the-consolidation-company"></a>Saldi della società di consolidamento

| Conto CoGe | Valuta | Importo  | Calcolo                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500,00  | Importo originale di 500 × 1                           |
| 130100         | EUR      | -500,00 | Importo originale di -500 × 1                          |
| 801400         | EUR      | 250     | 500 – 333.33 = 166,67 166,67 + 83,33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
