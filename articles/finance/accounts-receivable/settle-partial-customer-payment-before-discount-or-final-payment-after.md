---
title: Liquidare un pagamento parziale prima della data dello sconto con un pagamento finale dopo la data dello sconto
description: Questo articolo illustra l'effetto della liquidazione dei pagamenti delle fatture per i clienti. Lo scenario si concentra sugli effetti della contabilità secondaria, non della contabilità generale.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f6b4527a9f176857e0cc6ba4665688dc8721ac1
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780485"
---
# <a name="settle-partial-payment-before-discount-date-with-final-payment-after-discount-date"></a>Liquidare un pagamento parziale prima della data dello sconto con un pagamento finale dopo la data dello sconto

[!include [banner](../includes/banner.md)]

Questo articolo illustra l'effetto della liquidazione dei pagamenti delle fatture per i clienti. Lo scenario si concentra sugli effetti della contabilità secondaria, non della contabilità generale.

Fabrikam vende merci al cliente 4027. Fabrikam offre uno sconto di cassa dell'1% se la fattura viene pagata entro 14 giorni. Le fatture devono essere pagate in 30 giorni. Fabrikam offre inoltre sconti di cassa su pagamenti parziali. I parametri di liquidazione si trovano nella pagina **Parametri contabilità clienti**.

## <a name="invoice"></a>Fattura
Il 25 giugno, Arnie immette e registra una fattura di 1.000,00 per il cliente 4027. Arnie può visualizzare la fattura utilizzando il pulsante **Transazioni** nella pagina **Clienti**.

| Giustificativo   | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo  | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Fattura          | 6/25/2020 | 10020   | 1,000.00                             |                                       | 1,000.00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Pagamento parziale prima della data dello sconto di cassa
Il 2 luglio il cliente 4027 effettua un pagamento parziale di 297,00 per la fattura. Il pagamento è idoneo per uno sconto di cassa, poiché Fabrikam offre gli sconti di cassa su pagamenti parziali e il pagamento parziale viene effettuato prima della data dello sconto di cassa. Di conseguenza, il cliente 4027 ottiene uno sconto di cassa di 3,00. Arnie registra il pagamento per il cliente 4027 utilizzando il giornale di registrazione pagamenti. Arnie apre quindi la pagina **Liquida transazioni**, in modo che possa contrassegnare la fattura per la liquidazione.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Selezionato | Normale            | FTI-10020 | 4027    | 6/25/2020 | 7/25/2020 | 10020   | 1,000.00                             | USD      | 297,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**. Se non si modifica il valore di **Importo da liquidare** in 297,00, i valori di **Importo sconto di cassa** visualizzati saranno differenti. Tuttavia, quando viene registrato il pagamento, verrà applicato lo sconto di cassa pari a 3,00, poiché la liquidazione rettifica automaticamente il valore di **Importo da liquidare**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2020 |
| Importo sconto di cassa         | 10.00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 3,00      |

Arnie registra il pagamento. La fattura ora ha un saldo pari a 700,00. Le seguenti transazioni possono essere considerate per il cliente.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Fattura          | 6/25/2020 | 10020   | 1,000.00                             |                                       | 700.00  | USD      |
| ARP-10020  |  Pagamento         | 2020/1/7  |         |                                      | 297,00                                | 0,00    | USD      |
| DISC-10020 |  Sconto di cassa   | 2020/1/7  |         |                                      | 3.00                                  | 0,00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>Pagamento residuo dopo la data dello sconto di cassa
L'11 luglio, che è dopo il periodo di sconto, il cliente 4027 paga il resto della fattura. Nella pagina **Liquida transazioni** nessun importo di sconto viene visualizzato nel campo **Sconto di cassa stimato** e il valore nel campo **Importo sconto di cassa** è **0,00**. Quando il cliente 4027 paga i 700,00 rimanenti, non viene applicato alcuno sconto aggiuntivo.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Selezionato | Normale            | FTI-10020 | 4027    | 6/25/2020 | 7/25/2020 | 10020   | 700.00                               | USD      | 700.00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2020 |
| Importo sconto di cassa         | 0,00      |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 3,00      |
| Importo sconto di cassa da applicare | 0,00      |

Se Arnie cambia il valore nel campo **Utilizzare lo sconto di cassa** su **Sempre**, l'impostazione **Calcola sconti di cassa per pagamenti parziali** viene ignorato e lo sconto di cassa viene applicato. L'importo del pagamento diventa 693,00 e lo sconto di cassa sono i 7,00 rimanenti.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|---------------|---------------------|----------|------------------|
| Selezionato | Sempre            | FTI-10020 | 4027    | 6/25/2020 | 7/25/2020 | 10020   | 700.00        |                        | USD      | 693,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2020 |
| Importo sconto di cassa         | 7.00      |
| Utilizzare lo sconto di cassa            | Sempre    |
| Sconto di cassa applicato          | 3,00      |
| Importo sconto di cassa da applicare | 7,00      |

Arnie imposta il valore nel campo **Utilizzare lo sconto di cassa** di nuovo su **Normale**, poiché non ha intenzione di applicare per il cliente lo sconto di cassa rimanente di 7,00. Arnie, quindi, registra il pagamento. Quando Arnie apre la pagina **Transazioni cliente**, vede che la fattura ha un saldo pari a 0,00. Sono disponibili due pagamenti: Un pagamento è di 297,00 e ha uno sconto di cassa di 3,00 e l'altro pagamento è di 700,00.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Fattura          | 6/25/2020 | 10020   | 1,000.00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 2020/1/7  |         |                                      | 297,00                                | 0,00    | USD      |
| DISC-10020 |                  | 2020/1/7  |         |                                      | 3.00                                  | 0,00    | USD      |
| ARP-10021  |                  | 7/11/2020 |         |                                      | 700.00                                | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
