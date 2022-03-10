---
title: Aliquote IVA basate su Imponibile marginale e Metodo di calcolo
description: In questo argomento viene illustrato come i valori nei campi Imponibile marginale e Metodo di calcolo determinano le aliquote IVA nelle transazioni di vendita e di acquisto.
author: kailiang
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 55fc5416bafe63d8c32bc19359b4e8ba75b372de
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2021
ms.locfileid: "7727042"
---
# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>Aliquote IVA basate su Imponibile marginale e Metodo di calcolo

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come i valori nei campi Imponibile marginale e Metodo di calcolo determinano le aliquote IVA nelle transazioni di vendita e di acquisto.

Il calcolo dell'imponibile marginale nella scheda dettaglio della pagina dei codici IVA determina quale importo viene utilizzato per prelevare le aliquote appropriate nella pagina dei valori del codice IVA. Il tipo di importo nel campo Imponibile marginale congiuntamente al metodo nel campo Metodo di calcolo determina la logica per cercare le aliquote corrette per una transazione. 

Le varie combinazioni dei valori di questi campi determinano l'esecuzione di calcoli dell'IVA differenti, come illustrato negli esempi riportati di seguito. Negli esempi vengono utilizzati gli stessi valori di intervallo di imposta, che sono impostati per ogni codice IVA nella pagina dei valori del codice IVA. Per aprire la pagina, fare clic su Codice IVA &gt; Valori nella pagina Codici IVA.

> [!Important]                                                                                                                  
> Se l'imponibile marginale relativo a uno o più codici IVA è basato su importi riga o unità, il valore del campo Metodo di calcolo nella pagima Parametri contabilità generale deve essere impostato su Riga. |

## <a name="net-amount-per-line"></a> Importo netto per riga
Selezionare questa opzione per determinare le aliquote IVA in base all'importo netto delle righe di fattura, escluse eventuali altre imposte.

### <a name="example"></a>Esempio

Vengono impostati i seguenti intervalli per le aliquote IVA:

| Intervallo importi    | Aliquota imposta |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

> [!NOTE]                                                                                                             
> Il limite superiore 0 (zero) nell'ultimo intervallo indica che sono inclusi tutti gli importi maggiori di 100.

Imponibile marginale: **Importo netto per riga** 

Metodo di calcolo: **Intervallo** 

Si acquistano 8 lampade al costo di 25,00 l'una. 

L'importo netto della riga di fattura è pari a EUR 200. 

L'IVA viene calcolata nel seguente modo: 

IVA totale = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = EUR 35,00 

Importo fattura totale = 200,00 + 35,00 = EUR 235,00 

**Variazione** 

Se la fattura ha due righe con 4 articoli ciascuna, l'importo netto per ogni riga sarà pari a 100,00 e l'IVA verrà calcolata nel seguente modo: 

IVA riga 1 = 50 x 30% + 50 x 20% = 15 + 10 = EUR 25,00 

IVA riga 2 = 50 x 30% + 50 x 20% = 15 + 10 = EUR 25,00 

Totale IVA = 25 + 25 = 50,00 

Importo fattura totale = 200,00 + 50,00 = EUR 250,00

## <a name="net-amount-per-unit"></a> Importo netto unitario
Selezionare questa opzione per determinare l'aliquota IVA in base al valore di ogni unità, escluse eventuali altre imposte. Quando un Imponibile marginale basato su unità viene selezionato, anche un'unità deve essere specificata per il codice IVA.

### <a name="example"></a>Esempio

Vengono impostati i seguenti intervalli per le aliquote IVA:

| Importo             | Aliquota imposta |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Imponibile marginale: **Importo netto per unità** 

Metodo di calcolo  **Importo totale:** 

Si acquistano 8 lampade al costo di 25,00 l'una. 

L'importo netto della riga di fattura è pari a EUR 200. 

L'IVA viene calcolata nel seguente modo: IVA per unità = 25,00 x 30% = 7,50 IVA totale = 7,50 x 8 unità = 60,00 Importo della fattura totale = 200,00 + 60,00 = 260,00

## <a name="net-amount-of-invoice-balance"></a> Importo netto del saldo fattura

Selezionare questa opzione per determinare l'aliquota IVA in base all'importo totale delle righe di fattura, escluse eventuali altre imposte.

### <a name="example"></a>Esempio

Vengono impostati i seguenti intervalli per le aliquote IVA:

| Importo            | Aliquota imposta |
|-------------------|----------|
| 0 - 50            | 30%      |
| 50 - 100          | 20%      |
| 100 -0 (&gt; 100) | 10%      |

Imponibile marginale: **Importo netto del saldo fattura** 

Metodo di calcolo: **Intervallo** Una fattura di vendita ha 2 righe con 4 lampade per ogni riga per 25,00 ciascuna. L'importo del saldo netto della fattura è 4 x 25,00 + 4 x 25,00 = 200,00. L'IVA viene calcolata nel seguente modo: IVA totale = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Importo della fattura totale = 200,00 + 35,00 = 235,00

## <a name="gross-amount-per-line"></a> Importo lordo per riga

Selezionare questa opzione per determinare l'aliquota IVA in base al valore della riga incluse tutte le altre imposte per tale riga.

> [!NOTE]
> In una fascia IVA può essere presente un solo codice IVA con questo valore selezionato nel campo Imponibile marginale.

### <a name="example"></a>Esempio

Vengono impostati i seguenti intervalli per le aliquote IVA:

| Importo             | Aliquota imposta |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Imponibile marginale: **Importo lordo per riga** Metodo di calcolo: **Intervallo** È inoltre presente un altro codice IVA calcolato per un diritto speciale di 5,00 in ciascuna lampada. Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA. Si acquistano 8 lampade al costo di 25,00 l'una. L'importo netto della riga di fattura è pari a EUR 200. L'importo lordo della riga di fattura è pari a 8 x 25,00 + 8 x 5,00 = 240,00. L'IVA viene calcolata nel seguente modo: IVA totale = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 = 5,00 x 8 = 40,00 Importi della fattura totale = 200,00 + 39,00 + 40,00 = 279,00

**Variazione** 

Se la fattura viene creata utilizzando due righe con 4 articoli ciascuna, l'importo netto per riga di fattura sarà pari a 100,00. Importo lordo (imposta incluso di 4 x 5,00) di per riga di fattura sarà 120,00 e l'vat verrà creato come segue: Riga fattura 2 = di VAT riga fattura 1 = 50 VAT x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 totale VAT 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 imposta totale = 27,00 + 27,00 = 54,00 = 5,00 x 8 = 40,00 importi della fattura totale = 200,00 + 54,00 + 40,00 = 294,00

## <a name="gross-amount-per-unit"></a> Importo lordo unitario

Selezionare questa opzione per determinare l'aliquota IVA in base al valore di ogni unità, incluse eventuali altre imposte.

> [!NOTE]
> In una fascia IVA può essere presente un solo codice IVA con questo valore selezionato nel campo Imponibile marginale.

### <a name="example"></a>Esempio

Vengono impostati i seguenti intervalli per le aliquote IVA:

| Importo             | Aliquota imposta |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Imponibile marginale: **Importo lordo unitario** È presente un diritto speciale di 5,00 in ciascuna lampada. Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA. Si acquistano 8 lampade al costo di 25,00 l'una. L'importo lordo unitario è pari a EUR 30,00. L'IVA viene calcolata nel seguente modo: IVA per unità = 30 x 30% = 9,00 Iva totale = 9,00 x 8 = 72,00 Diritto totale = 5.00 x 8 = 40.00 Importo della fattura totale = 200,00 + 72,00 + 40,00 = 312,00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a> Totale fattura inclusi altri importi IVA

Selezionare questa opzione per determinare l'aliquota IVA in base all'importo totale delle righe di fattura, incluse eventuali altre imposte.
> [!NOTE]
> In una fascia IVA può essere presente un solo codice IVA con questo valore selezionato nel campo Imponibile marginale.

### <a name="example"></a>Esempio

Vengono impostati i seguenti intervalli per le aliquote IVA:

| Importo             | Aliquota imposta |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Imponibile marginale: **Totale fattura inclusi altri importi IVA** Metodo di calcolo: **Intervallo**   
Su ciascuna lampada viene applicata un'imposta speciale di EUR 5,00. Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA. Si acquistano 8 lampade al costo di 25,00 l'una. L'importo netto della fattura è pari a EUR 200. L'importo lordo della fattura è pari a EUR 200 + (8 x 5,00) = EUR 240,00. L'IVA viene calcolata nel seguente modo: IVA totale = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 = 5,00 x 8 = 40,00 Importi della fattura totale = 200,00 + 39,00 + 40,00 = 279,00

Per ulteriori informazioni, vedere [Opzioni Importo totale e Intervallo per i codici IVA](whole-amount-interval-options-sales-tax-codes.md) e [Metodi di calcolo IVA nel campo Origine](sales-tax-calculation-methods-origin-field.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
