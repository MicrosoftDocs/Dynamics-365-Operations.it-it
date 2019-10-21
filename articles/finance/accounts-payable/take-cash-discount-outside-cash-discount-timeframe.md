---
title: Applicare uno sconto di cassa fuori del periodo dello sconto di cassa
description: Questo articolo fornisce due scenari che illustrano come applicare uno sconto di cassa anche se il pagamento viene effettuato al di fuori del periodo dello sconto di cassa.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4a166e9a0d43da80986dd63d6739b104745b115
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189478"
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
| Selezionata | Sempre            | Inv-10030 | 3052    | 28/6/2015          | 12/7/2015 | 10030   | -2.000,00                      | GBP      | -1.980,00        |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 12/7/2015 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Sempre    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Data da utilizzare per il calcolo degli sconti = Data selezionata
Se sono stati registrati sia la fattura che il pagamento, lo sconto di cassa può comunque essere applicato quando le transazioni vengono liquidate nella pagina **Liquida transazioni**. April modifica il valore del campo **Data da utilizzare per il calcolo degli sconti** in **Data selezionata**. Immette la data del 28 giugno, compresa nel periodo di sconto di cassa della fattura. Tale data viene utilizzata per calcolare lo sconto di cassa per la transazione. Nella pagina **Liquida transazioni aperte**, April vede che, per impostazione predefinita, viene indicato lo sconto completo di 20,00. La riga di fattura indica che l'importo da liquidare è 1.980,00.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data sconto di cassa | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato ed evidenziato | Normale            | Inv-10030 | 3052    | 28/6/2015          | 12/7/2015 | 10030   | -2.000,00                      | GBP      | -1.980,00        |
| Selezionato                 | Normale            | APP-10030 | 3052    | 15/7/2015          | 15/7/2015 |         | 500,00                         | GBP      | 500,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**. L'importo dello sconto da applicare è 20,00, poiché l'importo da liquidare per la fattura è l'importo predefinito, 1.980,00.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 12/7/2015 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -20,00    |

April aggiorna il valore nel campo **Importo da liquidare** in **500,00**. Il valore **Importo sconto di cassa da applicare** nel campo viene calcolato come **5,05**.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato ed evidenziato | Normale            | Inv-10030 | 3052    | 28/6/2015 | 12/7/2015 | 10030   | 2.000,00                       | GBP      | -500,00          |
| Selezionato                 | Normale            | APP-10030 | 3052    | 15/7/2015 | 15/7/2015 |         | 500,00                         | GBP      | 500,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**. Il valore nel campo **Importo sconto di cassa da applicare** è **5,05**, poiché l'importo da liquidare per la fattura è stato modificato nell'importo del pagamento, 500,00.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 12/7/2015 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -5,05     |





