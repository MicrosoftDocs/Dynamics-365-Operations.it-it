---
title: Liquidare un pagamento fornitore parziale con sconti sulle note di accredito fornitore
description: Questo articolo descrive uno scenario in cui una nota di credito viene liquidata a fronte di una fattura.
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
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 923ab0305ac75c1156984c7a6d051f036479a16d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834513"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-vendor-credit-notes"></a>Liquidare un pagamento fornitore parziale con sconti sulle note di accredito fornitore

[!include [banner](../includes/banner.md)]

Questo articolo descrive uno scenario in cui una nota di credito viene liquidata a fronte di una fattura.

I fornitori di Fabrikam offrono sconti di cassa sulle note di accredito. Il fornitore 3050 consente a Fabrikam di eseguire uno sconto di cassa dell'1% se una fattura viene pagata in 14 giorni.

## <a name="invoice-and-credit-memo"></a>Fattura e nota di accredito
Il 29 giugno April crea una fattura per 1.000,00 per il fornitore 3050. Il 2 luglio, crea una nota di accredito per 200,00. Nella pagina **Fornitori** April apre la pagina **Liquida transazioni**. Può utilizzare la pagina **Liquida transazioni** per contrassegnare sia la nota di accredito che la fattura per la liquidazione. Uno sconto del 2,00 viene calcolato sulla nota di accredito. Di conseguenza, il valore totale della nota di accredito viene ridotto a 198,00.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata                 | Normale            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070   | -1.000,00                      | GBP      | -990,00          |
| Selezionato ed evidenziato | Normale            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 |         | 200,00                         | GBP      | 198,00           |

Le informazioni di sconto per la nota di accredito vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 13/7/2015 |
| Importo sconto di cassa         | 2,00      |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 2,00      |

April fa clic su **Registra**. Quindi rivede la liquidazione completata. April vede che 198,00 della nota di accredito sono stati applicati ed è stato eseguito uno sconto di 2,00. Di conseguenza, il totale è 200,00.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura  | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Selezionato ed evidenziato | Normale            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070    | -1.000,00                      | GBP      | -200,00          |
| Selezionato                 | Normale            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 | CR-10070 | 200,00                         | GBP      | 198,00           |

April può verificare le transazioni del fornitore nella pagina **Transazioni fornitore** selezionando un fornitore nella pagina **Tutti i fornitori**, quindi nel Riquadro azioni facendo clic su **Transazioni**. In questa pagina April vede che la fattura ha un saldo pari a -800,00. Vede anche una nota di accredito per 198,00 e uno sconto di 2,00.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | Fattura          | 29/6/2015 | 10070   |                                      | 1.000,00                              | -800,00 | GBP      |
| Inv-10071  |                  | 2/7/2015  | CR10071 | 200,00                               |                                       | 0,00    | GBP      |
| DISC-10071 |  Sconto di cassa   | 2/7/2015  |         | 2,00                                 |                                       | 0,00    | GBP      |
| DISC-10071 |  Sconto di cassa   | 2/7/2015  |         |                                      | 2,00                                  | 0,00    | GBP      |





