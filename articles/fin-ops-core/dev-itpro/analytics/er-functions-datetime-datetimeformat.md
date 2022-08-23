---
title: Funzione ER DATETIMEFORMAT
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione DATETIMEFORMAT della creazione di report elettronici (ER).
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
ms.openlocfilehash: e21b676046b6279826a728657fcc0d2a00a38b76
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287370"
---
# <a name="datetimeformat-er-function"></a>Funzione ER DATETIMEFORMAT

[!include [banner](../includes/banner.md)]

La funzione `DATETIMEFORMAT` restituisce un valore *[Stringa](er-formula-supported-data-types-primitive.md#string)* che presenta un valore specifico di data/ora come testo nel formato specificato e nelle impostazioni [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente. Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Sintassi 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argomenti

`datetime`: *[DateTime](er-formula-supported-data-types-primitive.md#datetime)*

Un valore di data/ora che rappresenta la data e l'ora da formattare.

`format`: *Stringa*

Formato della stringa di output. Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings).

> [!NOTE]
> La stringa di formato fa distinzione tra maiuscole e minuscole quando si utilizza un formato standard o un formato personalizzato. Ad esempio, l'identificatore di formato "d" [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) restituisce la data utilizzando il modello di data breve, mentre l'identificatore di formato "D" standard restituisce la data utilizzando il modello di data lunga. Inoltre, l'identificatore di formato "M" [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings) restituisce il mese da 1 a 12, mentre l'identificatore di formato "m" personalizzato restituisce i minuti da 0 a 59.

`culture`: *Stringa*

La cultura da utilizzare per la formattazione. Per informazioni sulle impostazioni cultura supportate, vedi [impostazioni cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valori restituiti

*String*

Il valore di stringa risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Se la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata. Ad esempio, se la funzione `DATETIMEFORMAT` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca. Il valore `culture` predefinito è **EN-US**.

Quando la funzione `DATETIMEFORMAT` converte un determinato valore data/ora, considera l'impostazione del fuso orario dell'utente dell'applicazione che esegue il formato ER da cui viene richiamata la funzione nel contesto.

## <a name="example-1"></a>Esempio 1

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come **"24-12-2015"**, in base al formato personalizzato specificato.

## <a name="example-2"></a>Esempio 2

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` restituisce la data/ora della sessione dell'applicazione corrente, il 24 dicembre 2015, come **"24.12.2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.

## <a name="example-3"></a>Esempio 3

`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` restituisce il valore della stringa **2019-11-12T08:00:00.0000000-08:00** quando la funzione viene richiamata durante un processo avviato da un utente dell'applicazione che ha il valore del fuso orario **(GMT-08: 00) Pacific Time (Stati Uniti e Canada)** nella sezione **Preferenze di lingua e paese**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
