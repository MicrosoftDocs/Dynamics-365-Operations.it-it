---
title: Funzione ER ROUND
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ROUND della creazione di report elettronici (ER).
author: kfend
ms.date: 10/21/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 57d41ed92a5577fdc5fffeccef2834e9b6fb5197
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286061"
---
# <a name="round-er-function"></a>Funzione ER ROUND

[!include [banner](../includes/banner.md)]

La funzione `ROUND` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato al numero di posizioni decimali specificato.

## <a name="syntax"></a>Sintassi

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>Argomenti

`number`: *Reale*

Un valore numerico che deve essere arrotondato.

`decimals`: *Intero*

Un valore numerico che rappresenta il numero di posizioni decimali.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Se il valore dell'argomento `decimals` è maggiore di 0 (zero), il numero specificato viene arrotondato al numero di posizioni decimali specificato.

Se il valore dell'argomento `decimals` è **0** (zero), il numero specificato viene arrotondato all'intero pari più vicino.

Se il valore dell'argomento `decimals` è minore di 0 (zero), il numero specificato viene arrotondato a sinistra del separatore decimale.

## <a name="example-1"></a>Esempio 1

`ROUND (1200.767, 2)` arrotonda a due posti decimali e restituisce **1200.77**.

## <a name="example-2"></a>Esempio 2

`ROUND (1200.767, -3)` arrotonda al più vicino multiplo di 1000 e restituisce **1000**.

## <a name="example-3"></a>Esempio 3

`ROUND (1200.5, 0)` arrotonda al numero intero pari più vicino e restituisce **1200**, mentre `ROUND (1201.5, 0)` fa lo stesso e restituisce **1202**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni matematiche](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
