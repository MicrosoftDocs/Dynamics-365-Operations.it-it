---
title: Liquidare un pagamento parziale fornitore e il pagamento totale finale prima della data dello sconto
description: Questo articolo descrive uno scenario in cui vengono effettuati pagamenti parziali per una fattura fornitore e viene preso uno sconto di cassa.
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
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 6cd87dc1b34d1d689d5417359e1ec3a34d53afb4
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Liquidare un pagamento parziale fornitore e il pagamento totale finale prima della data dello sconto

Questo articolo descrive uno scenario in cui vengono effettuati pagamenti parziali per una fattura fornitore e viene preso uno sconto di cassa.

Fabrikam acquista merci dal fornitore 3064. Il fornitore Fabrikam assegnare a uno sconto di cassa del 1 se la fattura viene pagata in 14 giorni. Le fatture devono essere pagate in 30 giorni. Il fornitore consente inoltre a Fabrikam di applicare sconti di cassa su pagamenti parziali. I parametri di liquidazione si trovano ** parametri di contabilità fornitori ** nella pagina. Il 25 giugno April immette una fattura per 1.000,00 per il fornitore 3064.

## <a name="vendor-invoice-on-june-25"></a>Fattura fornitore del 25 giugno
Il 25 giugno aprile, immette e registra una fattura di 1,000.00 per il fornitore 3064. April può visualizzare la transazione nella pagina **Transazioni fornitore**.

| Giustificativo   | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo   | Valuta |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10010 | 25/6/2015 | 10010   |                                      | 1.000,00                              | -1.000,00 | GBP      |

Nella pagina **Fornitori** April apre la pagina **Liquida transazioni**. April può utilizzare la pagina **Liquida transazioni** per visualizzare le date e gli importi degli sconti di cassa. La data di scadenza è il 25 luglio ed è disponibile uno sconto di cassa di 10,00 se la fattura viene pagata entro il 9 luglio.

| Contrassegna | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normale            | Inv-10010 | 3064    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | GBP      | 990,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 9/07/2015 |
| Importo sconto di cassa         | -10.00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -10.00    |

April fa clic sulla scheda **Sconto di cassa** per visualizzare l'importo dello sconto.

| Data sconto di cassa | Importo sconto di cassa | Importo nella valuta della transazione |
|--------------------|----------------------|--------------------------------|
| 9/7/2015           | 10,00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>Pagamento parziale effettuato il 1° luglio utilizzando la pagina Liquida transazioni
April può creare un giornale di registrazione pagamenti per il pagamento aprendo la pagina **Giornale di registrazione pagamenti** nella contabilità fornitori. Crea un nuovo giornale di registrazione e immette una riga per il fornitore 3064. Quindi aperto ** transazioni liquidati ** la pagina, in modo da poter collegare la fattura per la liquidazione. April contrassegna la fattura e modifica il valore nel campo **Importo da liquidare** in **-500,00**. Vede che il valore nel campo **Importo sconto di cassa** è **-10,00** per l'intera fattura e che il valore nel campo **Importo sconto di cassa da applicare** è **-5,05**. Di conseguenza, April sta liquidando -505,05 della fattura.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata | Normale            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | GBP      | -500,00          |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 9/07/2015 |
| Importo sconto di cassa         | -10.00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -5,05     |

April desidera liquidare esattamente metà della fattura. Di conseguenza, modifica il valore nel campo **Importo da liquidare** in **-495,00**. L'importo totale che viene liquidato ora è 500,00. Questo importo include lo sconto di cassa di -5,00.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata | Normale            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | GBP      | -495,00          |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 9/07/2015 |
| Importo sconto di cassa         | -10.00    |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 0,00      |
| Importo sconto di cassa da applicare | -5,00     |

April chiude la pagina **Transazioni di liquidare**. Nel giornale di registrazione viene creata una riga di pagamento di 495,00 e April registra il giornale di registrazione. April può verificare le transazioni fornitore ** ** transazioni fornitore nella pagina. Nota che le fatture con un saldo pari a -500.00. Vede inoltre un pagamento di 495,00 e uno sconto di cassa di 5,00.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Fattura          | 25/6/2015 | 10010   |                                      | 1.000,00                              | -500,00 | GBP      |
| APP-10010  | Pagamento          | 1/7/2015  |         | 495,00                               |                                       | 0,00    | GBP      |
| DISC-10010 | Sconto di cassa    | 1/7/2015  |         | 5,00                                 |                                       | 0,00    | GBP      |

## <a name="remaining-amount-paid-on-july-8"></a>L'importo rimanente viene pagato l'8 luglio
April liquida la parte restante della fattura per il fornitore 3064 l'8 luglio, compreso nel periodo dello sconto di cassa. April crea il giornale di registrazione pagamenti l'8 luglio e contrassegna la transazione per la liquidazione. Vede che l'importo da liquidare è di 495,00. Il valore nel campo **Sconto di cassa stimato** è **-5,00**, in quanto è stato prelevato in precedenza lo sconto di 5,00.

|                         |        |
|-------------------------|--------|
| Totale contrassegnato            | 495,00 |
| Sconto di cassa stimato | -5,00  |

Le informazioni sulla transazione contrassegnata vengono visualizzate nella griglia nella pagina **Liquida transazioni aperte**.

| Contrassegna     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo nella valuta della transazione | Valuta | Importo da liquidare |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selezionata | Normale            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | GBP      | 495,00           |

Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni aperte**.

|                              |           |
|------------------------------|-----------|
| Data sconto di cassa           | 9/07/2015 |
| Importo sconto di cassa         | 10,00     |
| Utilizzare lo sconto di cassa            | Normale    |
| Sconto di cassa applicato          | 5,00      |
| Importo sconto di cassa da applicare | 5,00      |

April registra il giornale di registrazione pagamenti e rivede le transazioni nella pagina **Transazioni fornitore**. Il saldo della fattura è ora pari a 0,00 e April vede i due pagamenti e i due sconti di cassa.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Fattura          | 25/6/2015 | 10010   |                                      | 1.000,00                              | 0,00    | GBP      |
| APP-10010  |  Pagamento         | 1/7/2015  |         | 495,00                               |                                       | 0,00    | GBP      |
| DISC-10010 | Sconto di cassa    | 1/7/2015  |         | 5,00                                 |                                       | 0,00    | GBP      |
| APP-10011  | Pagamento          | 8/7/2015  |         | 495,00                               |                                       | 0,00    | GBP      |
| DISC-10011 | Sconto di cassa    | 8/7/2015  |         | 5,00                                 |                                       | 0,00    | GBP      |



