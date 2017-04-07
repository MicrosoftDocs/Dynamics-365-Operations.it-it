---
title: Opzioni Importo totale e Intervallo per i codici IVA
description: Questo articolo illustra le opzioni del campo Metodo di calcolo sui codici IVA e come si calcola l&quot;IVA per intervalli e interi importi.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: d417019ab7e47a180d45d45abbde4e358a904721
ms.lasthandoff: 03/31/2017


---

# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Opzioni Importo totale e Intervallo per i codici IVA

Questo articolo illustra le opzioni del campo Metodo di calcolo sui codici IVA e come si calcola l'IVA per intervalli e interi importi.

È possibile impostare un codice IVA da calcolare in base a un importo totale o a un importo di intervallo. Nella pagina Codici IVA utilizzare il campo Metodo di calcolo nella Scheda dettaglio Calcolo per selezionare la modalità di calcolo di un codice IVA.
-   Importo totale - L'aliquota IVA si applica all'intero importo tassabile.
-   Intervallo - L'importo tassabile è diviso in parti, ognuna delle quali rientra in un intervallo con un'aliquota IVA specifica. La parte dell'importo che rientra in un determinato intervallo viene tassata in base all'aliquota IVA per tale intervallo. L'IVA è la somma degli importi delle imposte calcolati per ciascun intervallo di importi.
> [!NOTE]                                                                                                                              
> L'opzione di intervallo è disponibile solo quando si seleziona la riga nel campo del metodo di calcolo nell'area IVA della pagina dei parametri di contabilità generale. 

Gli intervalli vengono impostati nella pagina di valori di codice IVA immettendo gli importi limiti minimi e massimi per aliquota. Per calcolare le imposte per tutti gli importi tassabili, indipendentemente dal metodo selezionato, è necessario che gli intervalli siano conformi alle seguenti regole:
-   Il primo intervallo deve avere un limite minimo pari a zero.
-   L'ultimo intervallo deve avere un limite massimo pari a zero, che indica l'infinito.
-   Il limite massimo di un intervallo deve corrispondere al limite minimo dell'intervallo successivo.

Se un importo corrisponde al limite massimo dell'intervallo precedente e al limite minimo dell'intervallo successivo, all'importo viene applicata l'aliquota IVA del primo intervallo. Se un importo non è compreso negli intervalli definiti dai limiti superiore e inferiore, viene applicata un'aliquota IVA pari a 0.

## <a name="example-whole-amount-method-of-calculation"></a>Esempio: metodo di calcolo dell'importo totale
Nella pagina dei valori del codice IVA vengono impostati i seguenti intervalli per le aliquote IVA:
|                   |                   |              |
|-------------------|-------------------|--------------|
| **Limite minimo** | **Limite massimo** | **Aliquota IVA** |
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

L'IVA viene calcolata sull'intero importo tassabile.

| Importo tassabile (prezzo) | Calcolo    | IVA |
|------------------------|----------------|-----------|
| 35,00                  | 35.00 \* 0.30  | 10,50     |
| 50,00                  | 50.00 \* 0.30  | 15,00     |
| 85,00                  | 85.00 \* 0.20  | 17,00     |
| 305,00                 | 305.00 \* 0.10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a>Esempio: metodo di calcolo dell'intervallo
Nella pagina Valori vengono impostati i seguenti intervalli per le aliquote IVA:

|                   |                   |              |
|-------------------|-------------------|--------------|
| **Limite minimo** | **Limite massimo** | **Aliquota IVA** |
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

L'IVA è la somma degli importi delle imposte calcolati per ciascun intervallo di importi.

| Importo tassabile (prezzo) | Calcolo                                                               | IVA |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35.00 \* 0.30                                                             | 10,50     |
| 50,00                  | 50.00 \* 0.30                                                             | 15,00     |
| 85,00                  | (50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)                          | 22,00     |
| 305,00                 | (50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50) | 45,50     |

 

Per ulteriori informazioni, vedere [controlla le aliquote di vendita in base ai campi marginali] del metodo di calcolo e di base (marginal-base-field.md).




