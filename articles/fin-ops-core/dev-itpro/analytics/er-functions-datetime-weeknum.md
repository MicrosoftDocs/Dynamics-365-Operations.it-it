---
title: Funzione ER WEEKNUM
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione WEEKNUM della creazione di report elettronici (ER).
author: NickSelin
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 2c6eef0d6e1f90a3f8d382591edad3d568da84ec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858772"
---
# <a name="weeknum-er-function"></a>Funzione ER WEEKNUM

[!include [banner](../includes/banner.md)]

La funzione `WEEKNUM` restituisce un valore *[Intero](er-formula-supported-data-types-primitive.md#integer)* che è la rappresentazione della settimana dell'anno che include un valore *[Data](er-formula-supported-data-types-primitive.md#date)* specifico. Il calcolo si basa su regole dipendenti dalle impostazioni cultura che definiscono una settimana di calendario e il primo giorno della settimana.

## <a name="syntax"></a>Sintassi

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Argomenti</a>

`date`: *Data*

Un valore di data che rappresenta la data da utilizzare per il calcolo della settimana dell'anno.

`culture`: *[Stringa](er-formula-supported-data-types-primitive.md#string)*

Le impostazioni cultura da utilizzare per il calcolo. È possibile utilizzare codici cultura supportati in conformità con gli [standard](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0) .NET.

## <a name="return-values"></a>Valori restituiti

*Integer*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

La settimana dell'anno viene calcolata in base allo standard [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), se è stato adottato da un paese o da un'area per cui le impostazioni locali sono fornite in fase di runtime. In caso contrario, il calcolo si basa su standard nazionali specifici per paese/area.

Se viene fornito un codice [cultura](#arguments) non supportato come argomento della funzione `WEEKNUM` in fase di esecuzione, viene generata un'eccezione. Se la stringa vuota viene fornita come codice cultura, per calcolare il numero della settimana viene utilizzato il calendario inglese indipendente dal paese.

## <a name="examples"></a>Esempi

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` restituisce **1**.

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` restituisce **53**.

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` restituisce **52**.

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` restituisce **21**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
