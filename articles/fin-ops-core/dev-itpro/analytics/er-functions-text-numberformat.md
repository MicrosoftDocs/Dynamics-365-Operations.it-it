---
title: Funzione ER NUMBERFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMBERFORMAT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 0208796382bd6564539ebbe3d902cc41dedce235adafefe1126961774cdb2076
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749730"
---
# <a name="numberformat-er-function"></a>Funzione ER NUMBERFORMAT

[!include [banner](../includes/banner.md)]

La funzione `NUMBERFORMAT` restituisce un valore *Stringa* che presenta il numero specificato nel formato specificato e nelle [impostazioni cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente. Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-numeric-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="syntax-1"></a>Sintassi 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Argomenti

`number`: *Intero* o *Reale*

Un valore numerico che specifica il numero che deve essere formattato.

`format` : *Stringa*

Un valore *Stringa* che rappresenta il formato.

`culture`: *Stringa*

Un valore *Stringa* che rappresenta le impostazioni cultura da utilizzare per la formattazione.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Se le impostazioni cultura non sono definite come argomento della funzione chiamata, il contesto in cui viene eseguita questa funzione determina le impostazioni cultura utilizzate per formattare i numeri.

## <a name="example-1"></a>Esempio 1

Per le impostazioni cultura **EN-US**, `NUMBERFORMAT (0.45, "p")` restituisce **"45.00 %"** e `NUMBERFORMAT (10.45, "#")` restituisce **"10"**.

## <a name="example-2"></a>Esempio 2

`NUMBERFORMAT (10/3, "F2", "de")` restituisce **3,33**, mentre `NUMBERFORMAT (10/3, "F2", "en-us")` restituisce **3.33**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]