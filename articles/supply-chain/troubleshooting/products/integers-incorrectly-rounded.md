---
title: I numeri interi vengono arrotondati in calcoli di modelli di configurazione del prodotto
description: I risultati di numeri interi non vengono sempre arrotondati correttamente quando vengono calcolati i modelli di configurazione del prodotto. Risolvi il problema con un attributo decimale aggiuntivo e un calcolo.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b17145d7d17cb784fe11b3fbf65ddf5aa5530f27
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476787"
---
# <a name="integers-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>I numeri interi vengono arrotondati in modo errato quando vengono calcolati i modelli di configurazione del prodotto

## <a name="symptoms"></a>Sintomi

Questo problema può verificarsi quando si eseguono le seguenti serie di azioni:

1. Impostare questi attributi su un modello di configurazione di produzione:

    - Input (numero intero)
    - Percentuale (decimale)
    - Risultato (numero intero)

2. Crea un calcolo con la seguente espressione:

    *Risultato* = *Input* × *Percentuale* ÷ 100

In questo caso, il risultato intero non è sempre arrotondato correttamente. Ad esempio, se l'input è 1.000 e la percentuale è 2,40, si prevede che il risultato intero sia 24 perché il 2,40 percento di 1.000 è 24 (o 24,00 in formato decimale). Il risultato viene invece mostrato come 23. Tuttavia, quando la percentuale è 2,39, il calcolo viene arrotondato a 24 anziché a 23. Quando la percentuale è 2,50, il calcolo viene arrotondato a 25 come previsto.

## <a name="cause"></a>Causa

Questo problema si verifica a causa del modo in cui Microsoft Solver Foundation internamente rappresenta i numeri utilizzando le frazioni. Per l'esempio precedente, il risultato del calcolo in cui la percentuale è 2,40 è rappresentato come 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Quando .NET esegue il cast di questo valore come numero intero, restituirà 23.

## <a name="resolution"></a>Risoluzione

Questo comportamento non verrà modificato perché altri scenari dipendono da esso. Per l'esempio precedente, è possibile risolvere il problema introducendo un attributo decimale aggiuntivo e calcoli.

Ad esempio, impostare i seguenti attributi su un modello di configurazione di produzione:

- Input (numero intero)
- Percentuale (decimale)
- Risultato decimale (decimale)
- Resultato intero (numero intero)

Sarà quindi possibile aggiunger i calcoli riportati di seguito:

- *Risultato decimale* = *Input* × *Percentuale* ÷ 100
- *Risultato intero* = *Risultato decimale*
