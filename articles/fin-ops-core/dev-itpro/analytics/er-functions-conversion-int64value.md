---
title: Funzione ER INT64VALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INT64VALUE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 89a26e867579bcb34a9bae33fa0b98e1ecfe9995
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755398"
---
# <a name="int64value-er-function"></a>Funzione ER INT64VALUE

[!include [banner](../includes/banner.md)]

La funzione `INT64VALUE` restituisce un valore *Int64* che rappresenta la stringa specificata.

## <a name="syntax-1"></a>Sintassi 1

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
INT64VALUE (number)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che deve essere convertito in un numero *Int64*.

`number`: *Reale* o *Intero*

Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int64*.

## <a name="return-values"></a>Valori restituiti

*Int64*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Tutte le posizioni decimali sono troncate.

## <a name="example-1"></a>Esempio 1

`INT64VALUE ("22565422744")` restituisce il valore *Int64* **22565422744**.

## <a name="example-2"></a>Esempio 2

`INT64VALUE ( VALUE("22565422744.77"))` restituisce il valore *Int64* **22565422744**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di conversione di tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]