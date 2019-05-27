---
title: Liquidare un pagamento fornitore parziale che ha più periodi di sconto
description: Questo articolo descrive uno scenario in cui vengono effettuati più pagamenti parziali a un fornitore che offre più sconti di cassa.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84f8721c3bea232b7930e174eaf43ad550dd8ab6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1512247"
---
# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Liquidare un pagamento fornitore parziale che ha più periodi di sconto

[!include [banner](../includes/banner.md)]

Questo articolo descrive uno scenario in cui vengono effettuati più pagamenti parziali a un fornitore che offre più sconti di cassa. 

Il fornitore 3054 offre a Fabrikam uno sconto di cassa del 2% se la fattura viene pagata in cinque giorni e uno sconto di cassa dell'1% se la fattura viene pagata in 14 giorni.

## <a name="invoice"></a>Fattura
Il 28 giugno April crea una fattura per 1.000,00 per il fornitore 3054. April può visualizzare la transazione nella pagina **Transazioni fornitore**.

| Giustificativo   | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo   | Valuta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 28/6/2015 | 10060   |                                      | 1.000,00                              | -1.000,00 | GBP      |

Per la fattura sono disponibili le date e gli importi di sconto di cassa seguenti:

| Data sconto di cassa | Importo sconto di cassa | Importo nella valuta della transazione |
|--------------------|----------------------|--------------------------------|
| 3/7/2015           | 20,00                | 980,00                         |
| 12/7/2015          | 10,00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

## <a name="payment-on-july-2"></a>Pagamento il 2 luglio
Il 2 luglio, April desidera pagare 300,00 sulla fattura. Crea un pagamento occasionale utilizzando la pagina **Giornale di registrazione pagamenti** in Contabilità fornitori. Aggiunge una riga per il fornitore 3054 e immette un importo di pagamento di **300,00**. April apre quindi la pagina **Liquida transazioni** per contrassegnare la fattura per la liquidazione. Aggiorna il valore nel campo **Importo da liquidare** su **300,00** e nota che il valore del campo **Importo sconto di cassa da applicare** è cambiato in **6,12**. Poiché il pagamento viene effettuato nel primo periodo di sconto, viene applicato uno sconto del 2%.

| Contrassegna | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normale            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | GBP      | 300,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 2/07/2015 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -6,12     |

Poiché uno sconto di cassa è disponibile, April desidera modificare l'importo del pagamento in modo che l'importo totale liquidato sia 300,00 sia per il pagamento che per lo sconto di cassa. Modifica il valore nel campo **Importo da liquidare** su **294,00** e nota che il valore del campo **Importo sconto di cassa da applicare** è cambiato in **6,00**.

| Contrassegna | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normale            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | GBP      | 294,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 2/07/2015 |
| Importo sconto di cassa         | -20,00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -6,00     |

April registra il pagamento. April può visualizzare le transazioni nella pagina **Transazioni fornitore**. Vede che alla fattura è stato applicato il valore di 300,00. Questo importo include uno sconto del 6,00. Di conseguenza, il saldo residuo è 700,00.

| Giustificativo    | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -700,00 | GBP      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | GBP      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | GBP      |

## <a name="payment-on-july-8"></a>Pagamento l'8 luglio
L'8 luglio, April effettua un pagamento aggiuntivo per la fattura. Per immettere l'importo, apre la pagina **Liquida transazioni** e fa clic sulla scheda **Sconto di cassa**. Vede le date e gli importi per i due sconti di cassa disponibili. Poiché il pagamento è stato effettuato nel secondo periodo di sconto, viene applicato uno sconto dell'1% o pari a 5,00. L'importo viene calcolato come metà dello sconto dell'1% su 1.000,00, ovvero metà di 10,00.

| Data sconto di cassa | Importo sconto di cassa | Importo nella valuta della transazione |
|--------------------|----------------------|--------------------------------|
| 3/7/2015           | 20,00                | 680,00                         |
| 12/7/2015          | 10,00                | 690,00                         |
| 25/7/2015          | 0,00                 | 700,00                         |

April decide di pagare 495,00 e di applicare lo sconto di cassa pari a 5,00. L'importo totale che viene liquidato ora è 500,00.

| Contrassegna | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normale            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | GBP      | 495,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 12/7/2015 |
| Importo sconto di cassa         | -10.00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | -6,00     |
| Importo sconto di cassa da applicare | -5,00     |

Nella pagina **Transazioni fornitore** April vede che il nuovo saldo è 200,00.

| Giustificativo    | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -200,00 | GBP      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | GBP      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | GBP      |
| APP-10061  | 12/7/2015 |         | 495,00                               |                                       | 0,00    | GBP      |
| DISC-10061 | 12/7/2015 |         | 5,00                                 |                                       | 0,00    | GBP      |

## <a name="payment-on-july-20"></a>Pagamento il 20 luglio
Il 20 luglio April crea un pagamento finale di 200,00 per la fattura. Non viene applicato alcuno sconto di cassa, poiché il pagamento è successivo ai periodi di sconto. Il saldo della fattura è pari a 0,00.

| Giustificativo    | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -200,00 | GBP      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | GBP      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | GBP      |
| APP-10061  | 12/7/2015 |         | 495,00                               |                                       | 0,00    | GBP      |
| DISC-10061 | 12/7/2015 |         | 5,00                                 |                                       | 0,00    | GBP      |
| APP-10062  | 20/7/2015 |         | 200,00                               |                                       | 0,00    | GBP      |





