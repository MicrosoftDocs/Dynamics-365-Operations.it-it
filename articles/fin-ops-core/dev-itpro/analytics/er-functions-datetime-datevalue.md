---
title: Funzione ER DATEVALUE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione DATEVALUE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 396d6823531d8bf2c5b5f61f2483422c84e54c62
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883790"
---
# <a name="datevalue-er-function"></a>Funzione ER DATEVALUE

[!include [banner](../includes/banner.md)]

La funzione `DATEVALUE` restituisce un valore *[Data](er-formula-supported-data-types-primitive.md#date)* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente in un valore data. Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Sintassi 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argomenti

`text`: *[Stringa](er-formula-supported-data-types-primitive.md#string)*

Testo che rappresenta il valore da formattare.

`format`: *Stringa*

Formato della testo fornito. Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture`: *Stringa*

La cultura utilizzata per la formattazione del testo fornito. Per informazioni sulle impostazioni cultura supportate, vedi [impostazioni cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valori restituiti

*Data*

Il valore di data risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata. Ad esempio, se la funzione `DATEVALUE` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca. Il valore `culture` predefinito è **EN-US**.

## <a name="example-1"></a>Esempio 1

`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` restituisce il valore di data **21 dicembre 2016**, basato sul formato personalizzato specificato e la cultura **EN-US** dell'applicazione predefinita.

## <a name="example-2"></a>Esempio 2

`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` restituisce il valore della data **21 gennaio 2016**, in base al formato e alla cultura personalizzati specificati.

Tuttavia, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` genera un'eccezione per informare l'utente che la stringa specificata non viene riconosciuta come data valida per la cultura specificata.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
