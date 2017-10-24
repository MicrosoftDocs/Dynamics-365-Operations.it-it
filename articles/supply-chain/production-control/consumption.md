---
title: Calcolare il consumo di materiali
description: Questo articolo fornisce informazioni sulle varie opzioni correlate al calcolo del consumo materiali.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8defe5735726e877f37d8595a6aaa7c3d14d226b
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="calculate-material-consumption"></a>Calcolare il consumo di materiali

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni sulle varie opzioni correlate al calcolo del consumo materiali. 

Le seguenti opzioni correlate al calcolo del consumo di materiali sono disponibili nelle schede **Impostazioni** e **Consumo fase** della scheda dettaglio **Dettagli riga** nella pagina **Distinta base**.

## <a name="variable-and-constant-consumption"></a>Consumo variabile e costante
Nel campo **Il consumo è** è possibile scegliere se il consumo deve essere calcolato come una quantità costante o variabile. Selezionare **Costante** se per la produzione è necessario utilizzare una quantità o un volume fisso, indipendentemente dalla quantità prodotta. Selezionare **la variabile**, ovvero l'impostazione predefinita, se la quantità di materiale richiesta i prodotti finiti è proporzionale al numero di prodotti finiti che vengono prodotti.

## <a name="calculating-consumption-from-a-formula"></a>Calcolo del consumo tramite una formula
Nel campo **Formula** è possibile impostare diverse formule per il calcolo dl consumo di materiali. Se si utilizza il valore predefinito **Standard**, il consumo non viene calcolato da una formula. Le formule seguenti utilizzano i campi **Altezza**, **Larghezza**, **Profondità**, **Densità** e **Costante**:

-   Altezza \* Costante
-   Altezza \* Larghezza \* Costante
-   Altezza \* Larghezza \* Profondità \* Costante
-   (Altezza \* Larghezza \* Profondità / Densità) \* Costante

## <a name="rounding-up-and-multiples"></a>Arrotondamento per eccesso e multipli
I campi **Arrotondamento per eccesso** e **Multipli** consentono di arrotondare il valore del consumo materiali. Ad esempio, è possibile arrotondare il valore in base all'unità movimentazione in cui le materie prime vengono prelevate per la produzione. Nel campo **Arrotondamento per eccesso** sono disponibili le seguenti opzioni: **Quantità**, **Misurazione** e **Consumo**.

### <a name="quantity"></a>Quantità

Se si seleziona **Quantità** come meccanismo di arrotondamento per eccesso, la quantità deve essere un multiplo della quantità specificata. Se ad esempio sono necessari numeri interi, selezionare **1** nel campo **Multipli**. I numeri vengono arrotondati per eccesso a una quantità divisibile per 1.

### <a name="measurement"></a>Misurazione

In genere, si seleziona **Misurazione** come meccanismo di arrotondamento per eccesso quando le materie prime provengono in dimensioni specifiche. Ad esempio, un pezzo di tubo di metallo di 2 metri è necessario per un prodotto finito e il tubo di metallo viene immagazzinato in lunghezze di 4,5 metri. In questo caso, il meccanismo di arrotondamento per eccesso **Misurazione** può essere utilizzato per calcolare il numero tubi di metallo necessari per produrre un numero specifico di pezzi del prodotto finito. Per questo esempio, il campo **Formula** è impostato su **Altezza \* Costante**. Il campo **Altezza** è impostato su **2** per indicatore la lunghezza del tubo necessario per il prodotto finito. Il campo **Multiplo** è impostato su **4,5** per indicare che il tubo viene prelevato in lunghezze di 4,5 metri. Questo è il calcolo:

1.  Numero di multipli necessari per 10 pezzi del prodotto finito: 10 ÷ 2 = 5 pezzi
2.  Consumo totale: metri 4,5 × 5 = 22,5 di tubo di metallo

Si presume che 0,5 metri di tubo vengano scartati per ogni cinque pezzi di tubo utilizzati.

### <a name="consumption"></a>Consumo

In genere, si seleziona**Consumo** come meccanismo di arrotondamento per eccesso quando le materie prime devono essere prelevate nelle quantità intere di unità movimentazione specifica del prodotto. Ad esempio, 2 litri di vernice vengono utilizzati per produrre un pezzo di un prodotto finito e la vernice viene prelevata in latte da 25 litri. In questo caso, il meccanismo di arrotondamento per eccesso **Consumo** può essere utilizzato per arrotondare per eccesso il consumo ai numeri interi di latte da 25 litri. Questo è il calcolo della quantità di vernice necessaria se devono essere prodotti 180 pezzi del prodotto finito:

1.  Vernice necessaria, esclusi scarti: 180 × 2 = 360 litri
2.  Numero di latte: 360 ÷ 25 = 14,4, che viene arrotondato per eccesso a 15
3.  Vernice necessaria, inclusi scarti: 15 × 25 = 375 litri

## <a name="step-consumption"></a>Consumo fase
Il consumo per fasi viene utilizzato per calcolare il consumo costante in intervalli di quantità. Se si seleziona **Consumo fase** nel campo **Formula** della scheda **Impostazioni**, è possibile aggiungere le informazioni sulle fasi nella scheda **Consumo fase**. La quantità utilizzata fissa può essere impostata in intervalli della quantità prodotta. Ad esempio, il consumo per fasi è impostato come illustrato nella seguente tabella.

| Da serie | Quantità |
|-------------|----------|
| 0,00        | 10,0000  |
| 100,00      | 20,0000  |
| 200,00      | 40,0000  |

La quantità nella distinta base (DBA) è 1 e la quantità di produzione è 110. La formula per il calcolo del consumo è  Da serie (Quantità) = Consumo. Poiché la quantità di produzione è 110, rientra nella formula "Da 100 serie". Pertanto la quantità è 20.




