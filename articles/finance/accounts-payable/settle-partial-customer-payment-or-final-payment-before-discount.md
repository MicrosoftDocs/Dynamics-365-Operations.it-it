---
title: Liquidare pagamenti parziali e finali completamente prima della data dello sconto
description: Questo articolo fornisce scenari che illustrano come registrare pagamenti parziali per un cliente e applicare sconti di cassa all'interno del periodo dello sconto di cassa.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
ms.openlocfilehash: a8da366b1e770ea649603ae85d4acc5e377ed9fb
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780498"
---
# <a name="settle-partial-and-final-payments-in-full-before-the-discount-date"></a>Liquidare pagamenti parziali e finali completamente prima della data dello sconto

[!include [banner](../includes/banner.md)]

Questo articolo fornisce scenari che illustrano come registrare pagamenti parziali per un cliente e applicare sconti di cassa all'interno del periodo dello sconto di cassa.

Fabrikam vende merci al cliente 4028. Fabrikam offre uno sconto di cassa dell'1% se la fattura viene pagata entro 14 giorni. Le fatture devono essere pagate in 30 giorni. Fabrikam offre inoltre sconti di cassa su pagamenti parziali. I parametri di liquidazione si trovano nella pagina **Parametri contabilità clienti**.

## <a name="customer-invoice"></a>Fattura cliente
Il 25 giugno, Arnie immette e registra una fattura di 1.000,00 per il cliente 4028. Arnie può visualizzare la transazione nella pagina **Transazioni cliente**.

| Giustificativo   | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo  | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | Fattura          | 6/25/2020 | 10010   | 1,000.00                             |                                       | 1,000.00 | USD      |

Nella pagina **Cliente** o **Transazioni cliente** Arnie potrà aprire la pagina **Liquida transazioni** per visualizzare le date e gli importi degli sconti di cassa disponibili per la fattura. La data di scadenza è il 25 luglio ed è disponibile uno sconto di cassa di 10,00 se la fattura viene pagata entro il 9 luglio.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato | Normale            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 990.00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni** per la fattura contrassegnata.

|    &nbsp;                    |  &nbsp;   |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2020 |
| Importo sconto di cassa         | 10.00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 10,00     |

Arnie fa clic sulla scheda **Sconto di cassa** per visualizzare l'importo dello sconto.

| Data sconto di cassa | Importo sconto di cassa | Importo nella valuta della transazione |
|--------------------|----------------------|--------------------------------|
| 7/9/2020           | 10.00                | 990.00                         |
| 7/25/2020          | 0,00                 | 1,000.00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>Pagamento parziale utilizzando la pagina Pagamenti cliente
Il cliente 4028 invia un pagamento di 500,00 il 1° luglio. Per immettere il pagamento, Arnie non fa clic su **Righe**. Invece, registra il pagamento creando un nuovo giornale di registrazione pagamenti e quindi aprendo la pagina **Pagamenti cliente**. Immette le informazioni sul pagamento e contrassegna la fattura immessa. Quando Arnie immette **500,00** come importo, immette anche **500,00** nel campo **Importo da pagare** nella griglia. Poiché Fabrikam consente uno sconto di cassa sui pagamenti parziali, Arnie vede che verrà applicato uno sconto di cassa parziale di 5,05. Il calcolo di questo sconto è 500,00/0,99 × 0,01 = 5,05. Nel calcolo, 500,00 viene diviso per 0,99 poiché è presente uno sconto dell'1%. Di conseguenza, il cliente paga il 99% della fattura. Il risultato viene quindi moltiplicato per la percentuale di sconto, che è pari all'1% o 0,01. Se il cliente prende lo sconto totale di 10,00, l'importo che deve essere liquidato sarà 990,00. Informazioni sullo sconto appaiono nella griglia nella parte inferiore della pagina **Pagamenti cliente**.

| Importo sconto di cassa da applicare | Sconto di cassa applicato | Importo da pagare |
|------------------------------|---------------------|---------------|
| 5,05                         | 0,00                | 500,00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>Pagamento parziale tramite le righe del giornale di registrazione
Anziché aprire la pagina **Pagamenti cliente** nel giornale di registrazione pagamenti, Arnie può fare clic su **Righe** per immettere un pagamento. Il giornale di registrazione pagamenti viene visualizzato in cui Arnie può immettere una riga per il cliente 4028. Arnie apre quindi la pagina **Liquida transazioni**, in modo che possa contrassegnare la fattura per la liquidazione. Arnie contrassegna la fattura e modifica il valore nel campo **Importo da liquidare** su **-500,00**. Vede che il valore nel campo **Importo sconto di cassa** è **10,00** per l'intera fattura e che il valore nel campo **Importo sconto di cassa da applicare** è **5,05**. Di conseguenza, Arnie sta liquidando 505,05 della fattura.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato | Normale            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 500.00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|        &nbsp;                | &nbsp;    |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2020 |
| Importo sconto di cassa         | 10.00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 5,05      |

Se il cliente desidera liquidare esattamente metà della fattura, deve inviare un pagamento di 495,00. In questo caso Arnie immette **495,00** nel campo **Importo da liquidare**. Lo sconto di cassa per 5,00 verrà comunque applicato, in modo che l'importo liquidato totale sia 500,00.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato | Normale            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 495,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|     &nbsp;                   | &nbsp;    |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2020 |
| Importo sconto di cassa         | 10.00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | 5,00      |

Arnie chiude la pagina **Transazioni di liquidare**. Nel giornale di registrazione viene creata una riga di pagamento di 495,00 e Arnie registra il giornale di registrazione. Arnie può visualizzare le transazioni nella pagina **Transazioni cliente**. In questa pagina Arnie vede che la fattura ha un saldo pari a 500,00. Vede inoltre un pagamento di 495,00 e uno sconto di 5,00.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Fattura          | 6/25/2020 | 10010   | 1,000.00                             |                                       | 500.00  | USD      |
| ARP-10010  |  Pagamento         | 2020/1/7  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10010 |  Sconto di cassa   | 2020/1/7  |         |                                      | 5.00                                  | 0,00    | USD      |

## <a name="payment-for-the-remaining-amount"></a>Pagamento per l'importo rimanente
Il cliente 4028 paga l'importo rimanente di 495,00 l'8 luglio, che rientra nel periodo dello sconto di cassa. Arnie crea il giornale di registrazione pagamenti l'8 luglio e contrassegna la transazione per la liquidazione. Vede che l'importo da liquidare è di 495,00. Il valore nel campo **Sconto di cassa stimato** è **5,00**, in quanto è stato prelevato in precedenza lo sconto di 5,00.

|   &nbsp;                | &nbsp; |
|-------------------------|--------|
| Totale contrassegnato            | 495,00 |
| Sconto di cassa stimato | 5,00   |

Le informazioni sulla transazione contrassegnata vengono visualizzate nella griglia nella pagina **Liquida transazioni aperte**.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionato | Normale            | FTI-10010 | 4028    | 6/25/2020 | 7/25/2020 | 10010   | 1,000.00                       | USD      | 495,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2020 |
| Importo sconto di cassa         | 10.00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 5,00      |
| Importo sconto di cassa da applicare | 5,00      |

Arnie registra questo giornale e rivede le transazioni nella pagina **Transazioni cliente**. Il saldo della fattura è ora pari a 0,00 e Arnie vede i due pagamenti e i due sconti di cassa.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Fattura          | 6/25/2020 | 10010   | 1,000.00                             |                                       | 0,00    | USD      |
| ARP-10010  | Pagamento          | 2020/1/7  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10010 | Sconto di cassa    | 2020/1/7  |         |                                      | 5.00                                  | 0,00    | USD      |
| ARP-10011  | Pagamento          | 7/8/2020  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10011 | Sconto di cassa    | 7/8/2020  |         |                                      | 5.00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
