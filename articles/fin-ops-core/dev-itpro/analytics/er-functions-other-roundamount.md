---
title: Funzione ER ROUNDAMOUNT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUNDAMOUNT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a80587236d17160a996d701ca4ae38be21c818c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563296"
---
# <a name="roundamount-er-function"></a>Funzione ER ROUNDAMOUNT

[!include [banner](../includes/banner.md)]

La funzione `ROUNDAMOUNT` restituisce un valore *Reale* come risultato dell'arrotondamento del numero specificato al multiplo più vicino di un altro numero in base alla regola di arrotondamento specificata.

## <a name="syntax"></a>Sintassi

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Argomenti

`number`: *Int* o *Reale*

Un valore numerico che deve essere arrotondato.

`decimals`: *Int* o *Reale*

Il numero al cui multiplo deve essere arrotondato il valore del parametro `number`.

`round rule`: *Valore enumerazione*

Un valore di enumerazione dell'enumerazione **RoundOffType** che definisce la regola di arrotondamento. Questa enumerazione offre i seguenti valori:

- Normale (Ordinary)
- Arrotondamento per difetto (RoundDown)
- Arrotondamento per eccesso (RoundUp)

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante è un multiplo del valore specificato dal parametro `decimals` ed è il più vicino al valore specificato dal parametro `number`.

## <a name="usage-notes"></a>Note sull'utilizzo

Quando il parametro `number` è zero, questa funzione restituisce sempre zero.

Quando il parametro `decimals` è zero, questa funzione arrotonda al valore di arrotondamento predefinito. Quando il parametro `round rule` è impostato su **RoundOffType.Ordinary**, il valore di arrotondamento predefinito è **0,01**. In caso contrario, il valore di arrotondamento predefinito è **1,0**.

Quando il parametro `round rule` è impostato su **RoundOffType.Ordinary**, questa funzione arrotonda all'importo di arrotondamento più vicino.

Quando il parametro `round rule` è impostato su **RoundOffType.RoundDown**, questa funzione arrotonda verso lo zero all'importo di arrotondamento più vicino.

Quando il parametro `round rule` è impostato su **RoundOffType.RoundUp**, questa funzione arrotonda lontano da zero all'importo di arrotondamento più vicino.

Quando il parametro `round rule` è impostato su **RoundOffType.Ordinary**, questa funzione si comporta come la funzione [ARROTONDA.MULTIPLO](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) di Excel e la funzione [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) di X++.

## <a name="remarks"></a>Note

Per arrotondare un valore numerico a un numero specificato di posizioni decimali, utilizzare la funzione [ROUND](er-functions-mathematical-round.md).

## <a name="example"></a>Esempio

Se il parametro **model.RoundOff** è impostato su **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` restituisce 7,35. 

Se il parametro **model.RoundOff** è impostato su **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` restituisce 7,35. 

Se il parametro **model.RoundOff** è impostato su **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` restituisce 8,4.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)

[Funzioni matematiche](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]