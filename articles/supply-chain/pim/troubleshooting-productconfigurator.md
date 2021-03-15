---
title: Risolvere i problemi del configuratore di prodotto
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza il configuratore di prodotto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e6cfeb6a2b4166dfa9a5a5cc1b7d3d913b865ce2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999608"
---
# <a name="troubleshoot-the-product-configurator"></a>Risolvere i problemi del configuratore di prodotto

Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizza il configuratore di prodotto.

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a>Il testo dell'articolo viene sovrascritto quando si configura un prodotto in una riga dell'ordine cliente.

### <a name="issue-description"></a>Descrizione del problema

Questo problema si verifica quando si crea una riga di ordine cliente per un articolo configurabile e quindi si modifica il testo dell'articolo. Quando si configura l'articolo e quindi si seleziona **OK**, il testo viene sovrascritto con il testo standard.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è previsto. Il campo di testo include il nome della variante, che viene compilato solo dopo aver configurato la riga. Pertanto, è necessario modificare il testo dopo aver configurato la riga, non prima.

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Gli attributi interi vengono arrotondati in modo errato quando vengono calcolati i modelli di configurazione del prodotto.

### <a name="issue-description"></a>Descrizione del problema

Questo problema può verificarsi quando si eseguono le seguenti serie di azioni:

1. Impostare i seguenti attributi su un modello di configurazione di produzione:

    - Input (numero intero)
    - Percentuale (decimale)
    - Risultato (numero intero)

2. Crea un calcolo con la seguente espressione:

    *Risultato* = *Input* × *Percentuale* ÷ 100

In questo caso, il risultato intero non è sempre arrotondato correttamente. Ad esempio, l'input è 1.000 e la percentuale è 2,40. Pertanto, ci si aspetta che il risultato intero sia 24, perché il 2,40% di 1.000 è 24 (o 24,00 in formato decimale). Il risultato viene invece mostrato come 23. Tuttavia, quando la percentuale è 2,39, il calcolo viene arrotondato a 24 anziché a 23. Quando la percentuale è 2,50, il calcolo viene arrotondato a 25 come previsto.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo problema si verifica a causa del modo in cui Microsoft Solver Foundation internamente rappresenta i numeri utilizzando le frazioni. Per l'esempio precedente, il risultato del calcolo in cui la percentuale è 2,40 è rappresentato come 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Quando .NET esegue il cast di questo valore come numero intero, restituirà 23.

Questo comportamento non verrà modificato, perché altri scenari dipendono da esso. Per l'esempio precedente, è possibile risolvere il problema introducendo un attributo decimale aggiuntivo e un calcolo.

Ad esempio è possibile impostare i seguenti attributi su un modello di configurazione di produzione:

- Input (numero intero)
- Percentuale (decimale)
- Risultato decimale (decimale)
- Resultato intero (numero intero)

Sarà quindi possibile aggiunger i calcoli riportati di seguito:

- *Risultato decimale* = *Input* × *Percentuale* ÷ 100
- *Risultato intero* = *Risultato decimale*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]