---
title: Funzione ER ROUNDDOWN
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ROUNDDOWN della creazione di report elettronici (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: e0fa2c92fe63c3c89548b5cc23dd714d3d7589af
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286091"
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
