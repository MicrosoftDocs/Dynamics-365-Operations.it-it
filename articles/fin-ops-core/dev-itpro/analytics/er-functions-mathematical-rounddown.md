---
title: Funzione ER ROUNDDOWN
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUNDDOWN della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 77186dc4d607f419149e4001a7404afba9e80fc7ec2528b840261a329a1e7872
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747299"
---
# <a name="rounddown-er-function"></a>Funzione ER ROUNDDOWN

[!include [banner](../includes/banner.md)]

La funzione `ROUNDDOWN` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato per difetto al numero di posizioni decimali specificato.

## <a name="syntax"></a>Sintassi

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argomenti

`number`: *Reale*

Un valore numerico che deve essere arrotondato per difetto.

`decimals`: *Intero*

Un valore numerico che rappresenta il numero di posizioni decimali.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Questa funzione si comporta analogamente a [ROUND](er-functions-mathematical-round.md) ma sempre per difetto (verso lo zero).

## <a name="example-1"></a>Esempio 1

`ROUNDDOWN (1200.767, 2)` arrotonda per difetto a due posti decimali e restituisce **1200.76**. 

## <a name="example-2"></a>Esempio 2

`ROUNDDOWN (1700.767, -3)` arrotonda per difetto al più vicino multiplo di 1000 e restituisce **1000**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni matematiche](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]