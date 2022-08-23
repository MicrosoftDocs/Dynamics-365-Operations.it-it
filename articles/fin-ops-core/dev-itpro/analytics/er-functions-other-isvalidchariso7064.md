---
title: Funzione ER ISVALIDCHARACTERISO7064
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ISVALIDCHARACTERISO7064 della creazione di report elettronici (ER).
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
ms.openlocfilehash: 26ee54d1c3cd5673ec573e2df688780d3902b69d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275377"
---
# <a name="isvalidcharacteriso7064-er-function"></a>Funzione ER ISVALIDCHARACTERISO7064

[!include [banner](../includes/banner.md)]

La funzione `ISVALIDCHARACTERISO7064` restituisce un valore *Booleano* **TRUE** quando la stringa specificata rappresenta un numero di conto bancario internazionale (IBAN) valido. In caso contrario, restituisce il valore *Booleano* **FALSE**.

## <a name="syntax"></a>Sintassi

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che rappresenta un IBAN.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` restituisce **TRUE**. 

`ISVALIDCHARACTERISO7064 ("AT61")` restituisce **FALSE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
