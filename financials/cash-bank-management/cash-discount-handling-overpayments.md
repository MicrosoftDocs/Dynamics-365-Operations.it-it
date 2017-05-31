---
title: Gestione degli sconti di cassa per le eccedenze di pagamento
description: Questo articolo fornisce gli scenari che mostrano come un pagamento viene gestito quando il cliente ha uno sconto di cassa ma paga anche un importo superiore al dovuto.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f5d75794146eada9b9f439d99ad272f5af8db53b
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="handling-cash-discounts-for-overpayments"></a>Gestione degli sconti di cassa per le eccedenze di pagamento

[!include[banner](../includes/banner.md)]


Questo articolo fornisce gli scenari che mostrano come un pagamento viene gestito quando il cliente ha uno sconto di cassa ma paga anche un importo superiore al dovuto. 

Una fattura viene considerata con eccedenza di pagamento quando l'importo del pagamento è maggiore dell'importo della fattura meno lo sconto di cassa. Per specificare come la differenza di uno sconto di cassa viene gestito in caso di eccedenza del pagamento di una fattura, utilizzare i campi **Applicazione sconto di cassa** e **Massima eccedenza/insufficienza pagamento** nella pagina **Parametri contabilità clienti**. Nel seguente esempio, il cliente ha pagato 0,50 in più sulla fattura.

| Totale fattura | Sconto di cassa disponibile | Importo da pagare, incluso lo sconto di cassa | Importo effettivamente pagato dal cliente |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| 105,00        | 10,50                   | 94,50                                               | 95,00                             |

## <a name="cash-discount-administration--specific"></a>Amministrazione dello sconto di cassa = Specifico
Quando si seleziona **Specifico** nel campo **Applicazione sconto di cassa** della pagina **Conti per transazioni automatiche**, l'intero sconto di cassa viene prelevato. L'importo dell'eccedenza di pagamento viene registrato in un conto CoGe relativo alle differenze di sconto di cassa o rimane un saldo del conto cliente. Il comportamento varia a seconda che l'importo dell'eccedenza di pagamento sia compreso tra 0,00 e l'importo immesso nel campo **Massima eccedenza/insufficienza pagamento** o che sia superiore all'importo indicato in **Massima eccedenza/insufficienza pagamento**.

### <a name="scenario-1"></a>Scenario 1

In questo scenario, l'importo dell'eccedenza di pagamento è compreso tra 0,00 e l'importo massimo per eccedenza o insufficienza di pagamento. Viene immessa una fattura di 105,00 con la possibilità di usufruire di uno sconto di cassa se la fattura viene pagata entro sette giorni.

| Totale fattura | Sconto di cassa disponibile | Importo da pagare, incluso lo sconto di cassa |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Il cliente invia un pagamento di 95,00 entro il periodo dello sconto di cassa. Il pagamento viene liquidato rispetto alla fattura di 105,00. Successivamente alla liquidazione della fattura e del pagamento, nella Contabilità clienti vengono create le seguenti transazioni per il cliente.

| Transazione   | Importo | Saldo |
|---------------|--------|---------|
| Fattura       | 105,00 | 0,00    |
| Pagamento       | -95,00 | 0,00    |
| Sconto di cassa | -10,50 | 0,00    |

Le seguenti voci contabili vengono generate per il pagamento e la liquidazione. **Pagamento**

| Conto             | Importo in Dare | Importo in Avere |
|---------------------|--------------|---------------|
| Contante                | 95,00        |               |
| Contabilità clienti |              | 95,00         |

**Liquidazione**

| Conto                                                                                                          | Importo in Dare | Importo in Avere |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| Sconto di cassa (il campo **Conto principale per sconti cliente** nella pagina **Sconti di cassa**)                 | 10,50        |               |
| Contabilità clienti                                                                                              |              | 10,50         |
| Sconto di cassa cliente (il campo **Sconto di cassa cliente** nella pagina **Conti per transazioni automatiche**) |              | 0,50          |
| Contabilità clienti                                                                                              | 0,50         |               |

### <a name="scenario-2"></a>Scenario 2

In questo scenario, l'importo di eccedenza di pagamento supera l'importo massimo per eccedenza o insufficienza di pagamento. Viene immessa una fattura di 105,00 con la possibilità di usufruire di uno sconto di cassa se la fattura viene pagata entro sette giorni.

| Totale fattura | Sconto di cassa disponibile | Importo da pagare, incluso lo sconto di cassa |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Il cliente invia un pagamento di 95,00 entro il periodo dello sconto di cassa. Il pagamento viene liquidato rispetto alla fattura di 105,00. Successivamente alla liquidazione della fattura e del pagamento, nella Contabilità clienti vengono create le seguenti transazioni per il cliente.

| Transazione   | Importo | Saldo |
|---------------|--------|---------|
| Fattura       | 105,00 | 0,00    |
| Pagamento       | -95,00 | -0,50   |
| Sconto di cassa | -10,50 | 0,00    |

L'importo dell'eccedenza di pagamento di 0,50 rimarrà come saldo aperto nel pagamento e può essere liquidato in un'altra fattura. Le seguenti voci contabili vengono generate per il pagamento e la liquidazione. **Pagamento**

| Conto             | Importo in Dare | Importo in Avere |
|---------------------|--------------|---------------|
| Contante                | 95,00        |               |
| Contabilità clienti |              | 95,00         |

**Liquidazione**

| Conto                                                                                          | Importo in Dare | Importo in Avere |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Sconto di cassa (il campo **Conto principale per sconti cliente** nella pagina **Sconti di cassa**) | 10,50        |               |
| Contabilità clienti                                                                              |              | 10,50         |

## <a name="cash-discount-administration--unspecific"></a>Amministrazione dello sconto di cassa = Non specifico
Quando si seleziona **Non specifico** nel campo **Applicazione sconto di cassa** della pagina **Conti per transazioni automatiche**, l'importo dello sconto di cassa viene ridotto dell'importo di eccedenza di pagamento. Questo comportamento viene applicato sempre, indipendentemente dal fatto che l'importo dell'eccedenza di pagamento sia superiore o inferiore all'importo immesso nel campo **Massima eccedenza/insufficienza pagamento**.

### <a name="scenario-3"></a>Scenario 3

In questo scenario, viene immessa una fattura di 105,00 con la possibilità di usufruire di uno sconto di cassa se la fattura viene pagata entro sette giorni.

| Totale fattura | Sconto di cassa disponibile | Importo da pagare, incluso lo sconto di cassa |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

Il cliente invia un pagamento di 95,00 entro la data dello sconto di cassa. Il pagamento viene liquidato rispetto alla fattura di 105,00. Successivamente alla liquidazione della fattura e del pagamento, nella Contabilità clienti vengono create le seguenti transazioni per il cliente.

| Transazione   | Importo | Saldo |
|---------------|--------|---------|
| Fattura       | 105,00 | 0,00    |
| Pagamento       | -95,00 | -0,00   |
| Sconto di cassa | -10.00 | 0,00    |

L'importo dello sconto di cassa viene ridotto da 10,50 a 10,00. Il pagamento e la fattura vengono considerati liquidati. **Pagamento**

| Conto             | Importo in Dare | Importo in Avere |
|---------------------|--------------|---------------|
| Contante                | 95,00        |               |
| Contabilità clienti |              | 95,00         |

**Liquidazione**

| Conto                                                                                          | Importo in Dare | Importo in Avere |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Sconto di cassa (il campo **Conto principale per sconti cliente** nella pagina **Sconti di cassa**) | 10,50        |               |
| Contabilità clienti                                                                              |              | 10,50         |






