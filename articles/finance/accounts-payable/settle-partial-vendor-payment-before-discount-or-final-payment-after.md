---
title: Liquidare un pagamento parziale prima della data dello sconto e del pagamento finale dopo la data dello sconto
description: In questo argomento viene descritto uno scenario in cui vengono eseguiti più pagamenti parziali, alcuni nel periodo dello sconto di cassa e altri fuori dello stesso periodo.
author: abruer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7331b4b2ad48cfa380497336d4ac22c8723568b5
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716749"
---
# <a name="settle-partial-payment-before-discount-date-and-final-payment-after-discount-date"></a>Liquidare un pagamento parziale prima della data dello sconto e del pagamento finale dopo la data dello sconto

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto uno scenario in cui vengono eseguiti più pagamenti parziali, alcuni nel periodo dello sconto di cassa e altri fuori dello stesso periodo.

Fabrikam acquista merci dal fornitore 3057. Fabrikam riceve uno sconto di cassa dell'1% se la fattura viene pagata entro 14 giorni. Le fatture devono essere pagate in 30 giorni. Il fornitore consente inoltre a Fabrikam di applicare sconti di cassa su pagamenti parziali. I parametri di liquidazione si trovano nella pagina **Parametri contabilità fornitori**.

## <a name="invoice-on-june-25"></a>Fatturare il 25 giugno
Il 25 giugno April immette e registra una fattura per 1.000,00 per il fornitore 3057. April può visualizzare la transazione nella pagina **Transazioni fornitore**.

| Giustificativo   | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo   | Valuta |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Fattura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | -1.000,00 | GBP      |

## <a name="partial-payment-on-july-2"></a>Pagamento parziale il 2 luglio
Il 2 luglio, April desidera liquidare 300,00 della fattura. Il pagamento è idoneo per uno sconto, poiché Fabrikam applica sconti sui pagamenti parziali. Di conseguenza, April paga 297,00 e applica uno sconto di 3,00. Crea un giornale di registrazione pagamenti e immette una riga per il fornitore 3057. Apre quindi la pagina **Liquida transazioni**, in modo che sia possibile contrassegnare la fattura per la liquidazione.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata | Normale            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | -1.000,00                      | GBP      | -297,00          |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2015 |
| Importo sconto di cassa         | -10.00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -3,00     |

April, quindi, registra il pagamento. La fattura ora ha un saldo pari a 700,00. April può visualizzare la transazione nella pagina **Transazioni fornitore**.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fattura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | -700,00 | GBP      |
| APP-10020  | Pagamento          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | GBP      |
| DISC-10020 | Sconto di cassa    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | GBP      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Pagamento rimanente il 15 luglio, Utilizzare lo sconto di cassa = normale
April paga il resto della fattura il 15 luglio, che è dopo il periodo di sconto. Nella pagina **Liquida transazioni aperte** nessun importo di sconto viene visualizzato nel campo **Sconto di cassa stimato** e il valore nel campo **Importo sconto di cassa** è **0,00**. Quando April paga i 700,00 rimanenti, nessuno sconto aggiuntivo verrà applicato.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata | Normale            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | -700,00                        | GBP      | -700,00          |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**. April può visualizzare che ha già applicato uno sconto di 3,00.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2015 |
| Importo sconto di cassa         | 0,00      |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | -3,00     |
| Importo sconto di cassa da applicare | 0,00      |

April, quindi, registra il pagamento. Quando April apre la pagina **Transazioni fornitore**, vede che la fattura ha un saldo pari a 0,00. Inoltre vede che sono disponibili due pagamenti. Un pagamento è di 297,00 e ha uno sconto di 3,00, e l'altro pagamento è di 700,00.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fattura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | 0,00    | GBP      |
| APP-10020  | Pagamento          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | GBP      |
| DISC-10020 | Sconto di cassa    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | GBP      |
| APP-10021  | Pagamento          | 15/7/2015 |         | 700,00                               |                                       | 0,00    | GBP      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Pagamento rimanente il 15 luglio, Utilizzare lo sconto di cassa = Sempre
Se il fornitore consente ad April di applicare uno sconto anche se paga dopo la data dello sconto, può modificare il valore nel campo **Utilizzare lo sconto di cassa** in **Sempre**. L'impostazione **Calcola sconti di cassa per pagamenti parziali** verrà ignorata e lo sconto viene applicato. L'importo del pagamento è 693,00 e lo sconto è di 7,00 rimanenti.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selezionata | Sempre            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | 700,00                               |                                       | GBP      | -693,00          |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.

| Campo                        | Valore     |
|------------------------------|-----------|
| Data sconto di cassa           | 7/09/2015 |
| Importo sconto di cassa         | 7.00      |
| Utilizzare lo sconto di cassa            | Sempre    |
| Sconto di cassa applicato          | -3,00     |
| Importo sconto di cassa da applicare | -7,00     |

April, quindi, registra il pagamento. Quando April apre la pagina **Transazioni fornitore**, vede che la fattura ha un saldo pari a 0,00. Inoltre vede che sono disponibili due pagamenti. Un pagamento è di 297,00 e ha uno sconto di 3,00, e l'altro pagamento è di 693,00 e ha uno sconto di 7,00.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fattura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | 0,00    | GBP      |
| APP-10020  | Pagamento          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | GBP      |
| DISC-10020 | Sconto di cassa    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | GBP      |
| APP-10021  | Pagamento          | 15/7/2015 |         | 693,00                               |                                       | 0,00    | GBP      |
| DISC-10021 | Sconto di cassa    | 15/7/2015 |         | 7,00                                 |                                       | 0,00    | GBP      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
