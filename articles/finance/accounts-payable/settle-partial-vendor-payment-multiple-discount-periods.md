---
title: Liquidare un pagamento fornitore parziale che ha più periodi di sconto
description: Questo articolo descrive uno scenario in cui vengono effettuati più pagamenti parziali a un fornitore che offre più sconti di cassa.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da69d61c657ddc168a27a97fe16909d5f60eb4fd
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778039"
---
# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Liquidare un pagamento fornitore parziale che ha più periodi di sconto

[!include [banner](../includes/banner.md)]

Questo articolo descrive uno scenario in cui vengono effettuati più pagamenti parziali a un fornitore che offre più sconti di cassa. 

Il fornitore 3054 offre a Fabrikam uno sconto di cassa del 2% se la fattura viene pagata in cinque giorni e uno sconto di cassa dell'1% se la fattura viene pagata in 14 giorni.

## <a name="invoice"></a>Fattura
Il 28 giugno April crea una fattura per 1.000,00 per il fornitore 3054. April può visualizzare la transazione nella pagina **Transazioni fornitore**.

| Giustificativo   | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo   | Valuta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 6/28/2020 | 10060   |                                      | 1,000.00                              | -1.000,00 | USD      |

Per la fattura sono disponibili le date e gli importi di sconto di cassa seguenti:

| Data sconto di cassa | Importo sconto di cassa | Importo nella valuta della transazione |
|--------------------|----------------------|--------------------------------|
| 7/3/2020           | 20.00                | 980.00                         |
| 7/12/2020          | 10.00                | 990.00                         |
| 7/25/2020          | 0,00                 | 1,000.00                       |

## <a name="payment-on-july-2"></a>Pagamento il 2 luglio
Il 2 luglio, April desidera pagare 300,00 sulla fattura. Crea un pagamento occasionale utilizzando la pagina **Giornale di registrazione pagamenti** in Contabilità fornitori. Aggiunge una riga per il fornitore 3054 e immette un importo di pagamento di **300,00**. April apre quindi la pagina **Liquida transazioni** per contrassegnare la fattura per la liquidazione. Aggiorna il valore nel campo **Importo da liquidare** su **300,00** e nota che il valore del campo **Importo sconto di cassa da applicare** è cambiato in **6,12**. Poiché il pagamento viene effettuato nel primo periodo di sconto, viene applicato uno sconto del 2%.

| Contrassegna | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normale            | Inv-10060 | 3054    | 6/28/2020 | 7/28/2020 | 10060   | 1,000.00                       | USD      | 300,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/02/2020 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -6,12     |

Poiché uno sconto di cassa è disponibile, April desidera modificare l'importo del pagamento in modo che l'importo totale liquidato sia 300,00 sia per il pagamento che per lo sconto di cassa. Modifica il valore nel campo **Importo da liquidare** su **294,00** e nota che il valore del campo **Importo sconto di cassa da applicare** è cambiato in **6,00**.

| Contrassegna | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normale            | Inv-10060 | 3054    | 6/28/2020 | 7/28/2020 | 10060   | 1,000.00                       | USD      | 294,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/02/2020 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -6,00     |

April registra il pagamento. April può visualizzare le transazioni nella pagina **Transazioni fornitore**. Vede che alla fattura è stato applicato il valore di 300,00. Questo importo include uno sconto del 6,00. Di conseguenza, il saldo residuo è 700,00.

| Giustificativo    | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2020 | 10060   |                                      | 1,000.00                              | -700,00 | USD      |
| APP-10060  | 7/2/2020  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2020  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Pagamento l'8 luglio
L'8 luglio, April effettua un pagamento aggiuntivo per la fattura. Per immettere l'importo, apre la pagina **Liquida transazioni** e fa clic sulla scheda **Sconto di cassa**. Vede le date e gli importi per i due sconti di cassa disponibili. Poiché il pagamento è stato effettuato nel secondo periodo di sconto, viene applicato uno sconto dell'1% o pari a 5,00. L'importo viene calcolato come metà dello sconto dell'1% su 1.000,00, ovvero metà di 10,00.

| Data sconto di cassa | Importo sconto di cassa | Importo nella valuta della transazione |
|--------------------|----------------------|--------------------------------|
| 7/3/2020           | 20.00                | 680,00                         |
| 7/12/2020          | 10.00                | 690,00                         |
| 7/25/2020          | 0,00                 | 700.00                         |

April decide di pagare 495,00 e di applicare lo sconto di cassa pari a 5,00. L'importo totale che viene liquidato ora è 500,00.

| Contrassegna | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normale            | Inv-10060 | 3054    | 6/28/2020 | 7/28/2020 | 10060   | 1,000.00                       | USD      | 495,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/12/2020 |
| Importo sconto di cassa         | -10.00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | -6,00     |
| Importo sconto di cassa da applicare | -5,00     |

Nella pagina **Transazioni fornitore** April vede che il nuovo saldo è 200,00.

| Giustificativo    | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2020 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 7/2/2020  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2020  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2020 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 7/12/2020 |         | 5.00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Pagamento il 20 luglio
Il 20 luglio April crea un pagamento finale di 200,00 per la fattura. Non viene applicato alcuno sconto di cassa, poiché il pagamento è successivo ai periodi di sconto. Il saldo della fattura è pari a 0,00.

| Giustificativo    | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 6/28/2020 | 10060   |                                      | 1,000.00                              | -200,00 | USD      |
| APP-10060  | 7/2/2020  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 7/2/2020  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 7/12/2020 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 7/12/2020 |         | 5.00                                 |                                       | 0,00    | USD      |
| APP-10062  | 7/20/2020 |         | 200.00                               |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
