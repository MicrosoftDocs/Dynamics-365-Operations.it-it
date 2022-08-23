---
title: Funzione ER NOT
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione NOT della creazione di report elettronici (ER).
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
ms.openlocfilehash: 032cdaa2c71f6fab8c15780594d5a26d73600e74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278978"
---
# <a name="not-er-function"></a>Funzione ER NOT

[!include [banner](../includes/banner.md)]

La funzione `NOT` restituisce il valore logico inverso della condizione specificata come valore *Booleano*.

## <a name="syntax"></a>Sintassi

```vb
NOT (condition)
```

## <a name="arguments"></a>Argomenti

`condition`: *Booleano*

Un'espressione condizionale valida che deve essere invertita.

## <a name="return-values"></a>Valori restituiti

*Booleano*

Il valore *Booleano* risultante.

## <a name="example"></a>Esempio

`NOT (TRUE)` restituisce **FALSE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
