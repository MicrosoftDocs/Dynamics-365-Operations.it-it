---
title: Funzione ER DATETIMEVALUE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione DATETIMEVALUE della creazione di report elettronici (ER).
author: kfend
ms.date: 09/08/2021
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
ms.openlocfilehash: 591c707ae7f57236386de0b4ef85d428c9ae31fd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287340"
---
# <a name="datetimevalue-er-function"></a>Funzione ER DATETIMEVALUE

[!include [banner](../includes/banner.md)]

La funzione `DATETIMEVALUE` restituisce un valore *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente in un valore data/ora. Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Sintassi 1

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argomenti

`text`: *[Stringa](er-formula-supported-data-types-primitive.md#string)*

Testo che rappresenta il valore da formattare.

`format`: *Stringa*

Formato della testo fornito. Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture`: *Stringa*

La cultura utilizzata per la formattazione del testo fornito. Per informazioni sulle impostazioni cultura supportate, vedi [impostazioni cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata. Ad esempio, se la funzione `DATETIMEVALUE` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca. Il valore `culture` predefinito è **EN-US**.

## <a name="example-1"></a>Esempio 1

`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` restituisce **2:55:00 del 21 dicembre 2016**, basato sul formato personalizzato specificato e sulla cultura **EN-US** dell'applicazione predefinita.

## <a name="example-2"></a>Esempio 2

`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` restituisce **2:55:00 del 21 dicembre 2016**, in base al formato e alla cultura personalizzati specificati.

Tuttavia, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` genera un'eccezione per informare l'utente che la stringa specificata non viene riconosciuta come data/ora valida per la cultura specificata.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
