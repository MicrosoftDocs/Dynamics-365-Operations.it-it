---
title: Funzione ER INTVALUE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione INTVALUE della creazione di report elettronici (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: eccee60c40bfc96f1fd93e7177207a1dd1888dc6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282623"
---
# <a name="intvalue-er-function"></a>Funzione ER INTVALUE

[!include [banner](../includes/banner.md)]

La funzione `INTVALUE` restituisce un valore *Int* che rappresenta la stringa specificata.

## <a name="syntax-1"></a>Sintassi 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che deve essere convertito in un numero *Int*.

`number`: *Reale* o *Intero*

Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int*.

## <a name="return-values"></a>Valori restituiti

*Int*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Tutte le posizioni decimali sono troncate.

## <a name="example-1"></a>Esempio 1

`INTVALUE ("100.77")` restituisce il valore *Int* **100**.

## <a name="example-2"></a>Esempio 2

`INTVALUE (-100.77)` restituisce il valore *Int* **-100**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di conversione di tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
