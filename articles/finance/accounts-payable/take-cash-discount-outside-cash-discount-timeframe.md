---
title: Applicare uno sconto di cassa fuori del periodo dello sconto di cassa
description: Questo articolo fornisce due scenari che illustrano come applicare uno sconto di cassa anche se il pagamento viene effettuato al di fuori del periodo dello sconto di cassa.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b1eb5e542acf7496d1a0cf7196716a5de75e4e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780531"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Applicare uno sconto di cassa fuori del periodo dello sconto di cassa

[!include [banner](../includes/banner.md)]

Questo articolo fornisce due scenari che illustrano come applicare uno sconto di cassa anche se il pagamento viene effettuato al di fuori del periodo dello sconto di cassa.

Il 28 giugno April crea una fattura per 2.000,00 per il fornitore 3052. La fattura ha uno sconto di cassa dell'1% se la fattura viene pagata entro 14 giorni.

## <a name="use-cash-discount-option--always"></a>Utilizzare le opzioni dello sconto di cassa = Sempre
April crea un pagamento il 1° luglio, ovvero dopo la data dello sconto. April apre il modulo **Liquida transazioni** per visualizzare le transazioni che possono essere liquidate. 

April contrassegna la fattura per il pagamento. Non viene applicato alcuno sconto di cassa, poiché il pagamento è successivo alla data dello sconto. Tuttavia, il fornitore ha concesso ad April l'approvazione per applicare comunque lo sconto di cassa. Di conseguenza, April cambia il valore del campo **Utilizzare lo sconto di cassa** in **Sempre**.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data sconto di cassa | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato | Sempre            | Inv-10030 | 3052    | 6/28/2020          | 7/12/2020 | 10030   | -2.000,00                      | USD      | -1.980,00        |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/12/2020 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Sempre    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Data da utilizzare per il calcolo degli sconti = Data selezionata
Se sono stati registrati sia la fattura che il pagamento, lo sconto di cassa può comunque essere applicato quando le transazioni vengono liquidate nella pagina **Liquida transazioni**. April modifica il valore del campo **Data da utilizzare per il calcolo degli sconti** in **Data selezionata**. Immette la data del 28 giugno, compresa nel periodo di sconto di cassa della fattura. Tale data viene utilizzata per calcolare lo sconto di cassa per la transazione. Nella pagina **Liquida transazioni aperte**, April vede che, per impostazione predefinita, viene indicato lo sconto completo di 20,00. La riga di fattura indica che l'importo da liquidare è 1.980,00.

| Contrassegna          | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data sconto di cassa | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|--------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato ed evidenziato | Normale    | Inv-10030 | 3052    | 6/28/2020         | 7/12/2020 | 10030   | -2.000,00                      | USD      | -1.980,00        |
| Selezionato                 | Normale    | APP-10030 | 3052    | 7/15/2020          | 7/15/2020 |         | 500.00                         | USD      | 500.00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**. L'importo dello sconto da applicare è 20,00, poiché l'importo da liquidare per la fattura è l'importo predefinito, 1.980,00.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/12/2020 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -20,00    |

April aggiorna il valore nel campo **Importo da liquidare** in **500,00**. Il valore **Importo sconto di cassa da applicare** nel campo viene calcolato come **5,05**.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato ed evidenziato | Normale            | Inv-10030 | 3052    | 6/28/2020 | 7/12/2020 | 10030   | 2,000.00                       | USD      | -500,00          |
| Selezionato                 | Normale            | APP-10030 | 3052    | 7/15/2020 | 7/15/2020 |         | 500.00                         | USD      | 500.00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**. Il valore nel campo **Importo sconto di cassa da applicare** è **5,05**, poiché l'importo da liquidare per la fattura è stato modificato nell'importo del pagamento, 500,00.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/12/2020 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -5,05     |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
