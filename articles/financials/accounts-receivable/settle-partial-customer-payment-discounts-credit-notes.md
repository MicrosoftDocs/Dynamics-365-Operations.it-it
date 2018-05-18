---
title: Liquidare un pagamento cliente parziale con sconti sulle note di accredito
description: Questo articolo descrive uno scenario in cui uno sconto di cassa viene applicato su una nota di accredito quando anche la fattura originale ha uno sconto di cassa.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5402aa886d7194c4dcfad329aa30eb19bae3bc84
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Liquidare un pagamento cliente parziale con sconti sulle note di accredito

[!include [banner](../includes/banner.md)]

Questo articolo descrive uno scenario in cui uno sconto di cassa viene applicato su una nota di accredito quando anche la fattura originale ha uno sconto di cassa. 

Fabrikam consente ai clienti di applicare sconti di cassa a pagamenti parziali e anche a note di accredito (note di credito). Uno sconto di cassa può essere applicato a una nota di accredito quando la nota di accredito viene emessa per una fattura di un cliente alla quale è stato applicato uno sconto di cassa. Anziché accordare crediti per l'intero importo, è possibile accordare un credito al saldo cliente per un importo che escluda le percentuali di sconto di cassa applicate al cliente. I parametri di liquidazione si trovano nella pagina **Parametri contabilità clienti**.

## <a name="invoice-and-credit-note"></a>Fattura e nota di accredito
Il cliente 4035 ha una fattura di 1.000,00 e una nota di accredito di 100,00. Ciascun documento ha uno sconto dell'1% se viene pagata in 14 giorni. Arnie può visualizzare questa informazione nella pagina **Transazioni cliente**.

| Giustificativo    | Tipo di transazione | Data      | Fattura  | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo  | Valuta |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Fattura          | 28/6/2015 | 10050    | 1.000,00                             |                                       | 1.000,00 | GBP      |
| CCRN-10050 | Nota di accredito      | 28/6/2015 | CR-10050 |                                      | 100,00                                | -100,00  | GBP      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Consente di liquidare una nota di accredito con una fattura.
Nella pagina **Transazioni cliente** Arnie apre la pagina **Liquida transazioni**. Può utilizzare la pagina **Liquida transazioni** per liquidare la fattura e la nota di accredito. Durante il processo di liquidazione visualizza le date e gli importi dello sconto di cassa. Contrassegna i due documenti e quindi fa clic su **Registra** per liquidare le transazioni. È presente uno sconto del -1,00 sulla nota di accredito, perché Fabrikam consente sconti sulle note di accredito.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo    | Conto | Data      | Data di scadenza  | Fattura  | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Selezionata | Normale            | FTI-10050  | 4035    | 28/6/2015 | 28/7/2015 | 10050    | 1.000,00                       | GBP      | 990,00           |
| Selezionato | Normale            | CCRN-10050 | 4035    | 28/6/2015 | 28/7/2015 | CR-10050 | -100,00                        | GBP      | -99,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 12/7/2015 |
| Importo sconto di cassa         | -1,00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -1,00     |

La liquidazione sarà di 100,00 e includerà un pagamento di 99,00 e uno sconto di 1,00.




