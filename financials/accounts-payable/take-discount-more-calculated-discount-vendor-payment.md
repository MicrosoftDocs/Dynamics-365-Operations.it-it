---
title: Prendere uno sconto precedente a quella dello sconto calcolato per un pagamento fornitore
description: Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura. Questo scenario potrebbe verificarsi se un&quot;organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 22ba73681faa509a5144517163cc173a1267a534
ms.lasthandoff: 03/31/2017


---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a>Prendere uno sconto precedente a quella dello sconto calcolato per un pagamento fornitore

Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura. Questo scenario potrebbe verificarsi se un'organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura. 

Il fornitore 3051 concede a Fabrikam uno sconto di cassa del 4% se una fattura viene pagata in sette giorni. April immette una fattura il 29 giugno per 1.000,00. Il fornitore consente ad April di applicare uno sconto del 60,00 anziché lo sconto predefinito di 40,00 disponibile per la fattura. April registra un pagamento occasionale utilizzando il giornale di registrazione pagamenti della contabilità fornitori. Registra il fornitore per il pagamento e quindi apre ** transazioni liquidati ** la pagina. Segna la fattura e modifica il valore ** importo dello sconto di cassa ** nel campo a ** ** 60.00.
| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata | Normale            | Inv-10040 | 3051    | 29/6/2015 | 29/7/2015 | 10040   | 1.000,00                       | GBP      | 940,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.
|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 12/7/2015 |
| Importo sconto di cassa         | 60,00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 60,00     |

April registra il giornale di registrazione pagamenti. La fattura è completamente liquidata con un pagamento di 940,00 e uno sconto di 60,00.


