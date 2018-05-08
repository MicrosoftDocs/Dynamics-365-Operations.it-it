---
title: Prezzo di costo medio corrente
description: Il processo di chiusura dell'inventario  consente di compensare le transazioni in uscita a fronte delle transazioni in entrata in base al metodo di valutazione del magazzino selezionato nel gruppo di modelli di articoli dell'articolo. Prima di eseguire la chiusura dell'inventario, tuttavia, il sistema calcola un prezzo di costo medio corrente che viene in genere utilizzato per la registrazione delle transazioni in uscita.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: aeb23f78d9bec93cf92214470e9ace3cd88b92c3
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="running-average-cost-price"></a>Prezzo di costo medio corrente

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Il processo di chiusura dell'inventario  consente di compensare le transazioni in uscita a fronte delle transazioni in entrata in base al metodo di valutazione del magazzino selezionato nel gruppo di modelli di articoli dell'articolo. Prima di eseguire la chiusura dell'inventario, tuttavia, il sistema calcola un prezzo di costo medio corrente che viene in genere utilizzato per la registrazione delle transazioni in uscita.

Viene effettuata una stima del prezzo di costo medio corrente di un articolo applicando la seguente formula: 

Prezzo stimato = (importo fisico + importo finanziario) ÷ (quantità fisica + quantità finanziaria)

## <a name="using-the-running-average-cost-price"></a>Utilizzo del prezzo di costo medio corrente
Nella tabella riportata di seguito viene illustrato quando il sistema registra le operazioni di magazzino utilizzando il prezzo di costo medio corrente e quando invece utilizza il prezzo di costo definito nel record principale dell'articolo.

| Condizione                                               | Il sistema utilizza il prezzo di costo medio corrente stimato | Il sistema utilizza il prezzo di costo definito nel record principale dell'articolo |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Il numeratore\* e il denominatore\*\* sono entrambi positivi.  | Sì                                                      | No                                                                |
| Il numeratore\*, il denominatore\*\* o entrambi sono negativi. | No                                                       | Sì                                                               |
| Il denominatore\*\* è 0 (zero).                        | No                                                       | Sì                                                               |

\* Numeratore = (importo fisico + importo finanziario) \*\* Denominatore = (quantità fisica + quantità finanziaria) 

**Nota:** se l'opzione **Includi valore fisico** non è selezionata per un articolo, viene utilizzato 0 (zero) sia per l'importo fisico sia per la quantità fisica. Per informazioni su questa opzione, vedere [Includi valore fisico](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Evitare l'amplificazione dei prezzi
In rare occasioni, il sistema determina il prezzo di diverse uscite prima di disporre di sufficienti entrate su cui basare un prezzo. In questo scenario le stime del prezzo di costo medio corrente possono risultare eccessivamente gonfiate. È tuttavia possibile effettuare alcuni passaggi per evitare l'amplificazione dei prezzi o per attenuarne l'impatto. **Scenario** Le seguenti transazioni si verificano per un articolo per il quale è stata selezionata l'opzione **Includi valore fisico**:

1.  Si riceve finanziariamente una quantità pari a 100 a 100,00 EUR.
2.  Si rilascia finanziariamente una quantità pari a 200.
3.  Si riceve fisicamente una quantità pari a 101 a 202,00 EUR.

Quando viene esaminato il prezzo di costo medio corrente stimato dell'articolo, si prevede un prezzo di costo di 1,51 EUR, Invece si scopre una media corrente stimata di 102,00 EUR basata sulla seguente formula: Prezzo stimato = \[202 + (-100)\] ÷ \[101 + (-100))\] = 102 ÷ 1 = 102. Questa amplificazione dei prezzi si verifica perché quando nel passaggio 2 si registra l'uscita finanziaria di 200 articoli, il sistema deve determinare il prezzo di 100 di questi articoli prima di disporre delle entrate corrispondenti. Questa situazione causa le scorte negative. Il sistema quindi stima un prezzo unitario di 1,00 EUR, come si potrebbe prevedere. Quando, tuttavia, arrivano le 100 entrate corrispondenti, il loro prezzo unitario è di 2,00 EUR. 

**Nota:** anche se le uscite determinano una situazione di scorte negative, queste sono comunque positive nel momento in cui viene calcolato il prezzo di uscita. Per questo motivo viene utilizzato il prezzo di costo medio corrente anziché il prezzo del record generale dell'articolo. A questo punto, è presente un offset del valore di magazzino pari a 100,00 EUR. Nonostante tale valore sia stato generato da 100 pezzi, con un offset pari a 1,00 EUR ciascuno, in magazzino è attualmente disponibile un solo pezzo, al quale viene allocato l'intero offset di 100,00 EUR. Questa situazione determina un prezzo di costo stimato eccessivamente gonfiato. 

**Nota:** per fare un confronto, invertendo i passaggi 2 e 3 nello scenario, si registrerebbe l'uscita di 200 articoli al prezzo unitario di 1,51 EUR, mentre un unico pezzo rimarrebbe al prezzo unitario di 1,51 EUR. Poiché lo scenario di amplificazione dei prezzi si può verificare in presenza di scorte negative, risulta difficilmente evitabile nei seguenti casi:

-   È necessario stimare i prezzi di uscita sulla quantità e il valore delle disponibilità.
-   È necessario rettificare la quantità e il valore delle disponibilità su entrate e uscite.
-   Il modello aziendale consente l'invio o la determinazione del prezzo di un numero di pezzi superiore alle disponibilità.
-   È necessario accettare qualsiasi quantità e valore delle entrate ricevute.

Se tuttavia il modello aziendale lo consente, attenendosi alle seguenti procedure è possibile evitare le quantità negative che rendono possibile lo scenario di amplificazione dei prezzi:

-   Se si seleziona l'opzione **Includi valore fisico** per un articolo, deselezionare la casella di controllo **Scorte fisiche negative** nella pagina **Gruppi di modelli di articoli**.
-   Se *non* si seleziona l'opzione **Includi valore fisico** per un articolo, deselezionare l'opzione **Scorte finanziarie negative** nella pagina **Gruppi di modelli di articoli**.

È inoltre importante tenere presente che l'offset massimo nel valore dell'inventario fisico è limitato dal numero di transazioni fisiche e dalla differenza tra i prezzi fisici e i prezzi finanziari. Se tutte le transazioni fisiche vengono regolarmente aggiornate finanziariamente, il valore fisico non può salire a livelli estremi. Si noti infine che l'effetto di amplificazione tende ad attenuarsi significativamente quando l'offset accumulato viene ripartito su diversi pezzi disponibili anziché su un unico pezzo.




