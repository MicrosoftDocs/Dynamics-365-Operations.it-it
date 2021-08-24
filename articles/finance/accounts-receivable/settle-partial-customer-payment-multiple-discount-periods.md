---
title: Liquidare un pagamento cliente parziale che ha più periodi di sconto
description: Questo articolo illustra come vengono liquidati i pagamenti cliente se sono presenti più periodi di sconto.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d0d517524add5e18b1f0795b2ee2fd7f5b7686b26919a7e8f2e20ac1d243fe9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740124"
---
# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>Liquidare un pagamento cliente parziale che ha più periodi di sconto

[!include [banner](../includes/banner.md)]

Questo articolo illustra come vengono liquidati i pagamenti cliente se sono presenti più periodi di sconto.

Fabrikam offre al cliente 4031 due periodi di sconto di cassa. Il cliente riceve uno sconto di cassa del 2% se salda la fattura entro cinque giorni e uno sconto di cassa dell'1% se salda la fattura entro 14 giorni. Fabrikam offre inoltre sconti di cassa su pagamenti parziali. I parametri di liquidazione si trovano nella pagina **Parametri contabilità clienti**.

## <a name="invoice"></a>Fattura
Il 25 giugno, Arnie immette e registra una fattura di 1.000,00 per il cliente 4031. Quando rivede gli sconti di cassa per la fattura, Arnie vede che il cliente 4031 otterrà uno sconto di 20,00 se la fattura viene pagata entro il 30 giugno. Se la fattura viene pagata entro il 9 luglio, il cliente otterrà uno sconto di 10,00.

| Data sconto di cassa | Importo sconto di cassa | Importo nella valuta della transazione |
|--------------------|----------------------|--------------------------------|
| 30/6/2015          | 20,00                | 980,00                         |
| 9/7/2015           | 10,00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

Arnie può visualizzare la transazione nella pagina **Transazioni cliente**.

| Giustificativo   | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo  | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | Fattura          | 25/6/2015 | 10030   | 1.000,00                             |                                       | 1.000,00 | GBP      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Pagamento parziale prima della data dello sconto di cassa
Il 28 giugno, il cliente 4031 effettua un pagamento parziale di 294,00. Poiché il 28 giugno rientra nel primo periodo di sconto di cassa, il cliente riceverà lo sconto di 6,00. Nella pagina **Liquida transazioni**, il valore di **Importo sconto di cassa** è di 20,00 e il valore di **Importo sconto di cassa da applicare** è pari a 6,00.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata | Normale            | FTI-10030 | 4031    | 25/6/2015 | 25/7/2015 | 10030   | 1.000,00                       | GBP      | 294,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**. Se non si modifica il valore di **Importo da liquidare** in **294,00**, i valori di **Importo sconto di cassa** visualizzati saranno differenti. Tuttavia, quando viene registrato il pagamento, verrà applicato lo sconto di cassa pari a 6,00 poiché la liquidazione rettifica automaticamente il valore di **Importo da liquidare**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Data sconto di cassa           | 30/6/2015 |
| Importo sconto di cassa         | 20,00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 6,00      |

Una volta che Arnie ha registrato il pagamento, il saldo della fattura è di 700,00.

## <a name="partial-payment-before-the-second-cash-discount-date"></a>Pagamento parziale prima della seconda data dello sconto di cassa
L'8 luglio, il cliente salda la parte restante dell'importo della fattura. Lo sconto ottenuto è di 7,00, ovvero dell'1%, perché il pagamento è stato effettuato entro il secondo periodo di sconto di cassa.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selezionata | Normale            | FTI-10030 | 4031    | 25/6/2015 | 25/7/2015 | 10030   | 700,00                               |                                       | GBP      | 693,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Data sconto di cassa           | 9/07/2015 |
| Importo sconto di cassa         | 30,00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 6,00      |
| Importo sconto di cassa da applicare | 7,00      |

Il saldo della fattura ora è pari a 0,00. Arnie visualizza le informazioni nella pagina **Transazioni cliente**.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | Fattura          | 25/6/2015 | 10030   | 1.000,00                             |                                       | 0,00    | GBP      |
| ARP-10030  |  Pagamento         | 28/6/2015 |         |                                      | 294,00                                | 0,00    | GBP      |
| DISC-10030 |  Sconto di cassa   | 28/6/2015 |         |                                      | 6,00                                  | 0,00    | GBP      |
| ARP-10031  |  Pagamento         | 8/7/2015  |         |                                      | 693,00                                | 0,00    | GBP      |
| DISC-1031  |  Sconto di cassa   | 8/7/2015  |         |                                      | 7,00                                  | 0,00    | GBP      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]