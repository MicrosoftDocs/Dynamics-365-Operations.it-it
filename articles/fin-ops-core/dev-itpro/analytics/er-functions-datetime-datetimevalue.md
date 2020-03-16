---
title: Funzione ER DATETIMEVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATETIMEVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29d81599563dec2827fa8a82c86b74cb9e34eea2
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070692"
---
# <a name="DATETIMEVALUE">Funzione ER DATETIMEVALUE</a>

[!include [banner](../includes/banner.md)]

La funzione `DATETIMEVALUE` restituisce un valore *DateTime* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente in un valore data/ora. Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintassi 1

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Testo che rappresenta il valore da formattare.

`format`: *Stringa*

Formato della testo fornito.

`culture`: *Stringa*

La cultura utilizzata per la formattazione del testo fornito.

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
