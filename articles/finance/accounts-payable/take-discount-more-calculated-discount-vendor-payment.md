---
title: Applicare uno sconto maggiore dello sconto calcolato per un pagamento fornitore
description: Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura. Questo scenario potrebbe verificarsi se un'organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd74c6677f80a9075449908411350f1c81b95b02
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778359"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a>Applicare uno sconto maggiore dello sconto calcolato per un pagamento fornitore

[!include [banner](../includes/banner.md)]

Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura. Questo scenario potrebbe verificarsi se un'organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura. 

Il fornitore 3051 concede a Fabrikam uno sconto di cassa del 4% se una fattura viene pagata in sette giorni. April immette una fattura il 29 giugno per 1.000,00. Il fornitore consente ad April di applicare uno sconto del 60,00 anziché lo sconto predefinito di 40,00 disponibile per la fattura. April registra un pagamento occasionale utilizzando il giornale di registrazione pagamenti della contabilità fornitori. Registra il fornitore per il pagamento e quindi apre la pagina **Liquida transazioni**. Contrassegna la fattura e modifica il valore nel campo **Importo sconto di cassa** in **60,00**.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato | Normale            | Inv-10040 | 3051    | 6/29/2020 | 7/29/2020 | 10040   | 1,000.00                       | USD      | 940,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/12/2020 |
| Importo sconto di cassa         | 60.00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 60,00     |

April registra il giornale di registrazione pagamenti. La fattura è completamente liquidata con un pagamento di 940,00 e uno sconto di 60,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
