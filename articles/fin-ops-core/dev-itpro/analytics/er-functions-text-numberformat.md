---
title: Funzione ER NUMBERFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMBERFORMAT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 2c3907d1d2c74c852f4f90731e5f4bc23bfbd717
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680268"
---
# <a name="numberformat-er-function"></a>Funzione ER NUMBERFORMAT

[!include [banner](../includes/banner.md)]

La funzione `NUMBERFORMAT` restituisce un valore *Stringa* che presenta il numero specificato nel formato specificato e nelle [impostazioni cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente. Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).

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