---
title: Funzione ER DATEFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATEFORMAT della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fa6bdef2168112aeb17e0edb9f9a6d1b3bd45c0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684934"
---
# <a name="dateformat-er-function"></a>Funzione ER DATEFORMAT

[!include [banner](../includes/banner.md)]

La funzione `DATEFORMAT` restituisce un valore *Stringa* che presenta un valore specifico di data come testo nel formato specificato e nelle impostazioni [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente. Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintassi 1

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>Argomenti

`date`: *Data*

Un valore di data che rappresenta la data da formattare.

`format`: *Stringa*

Formato della stringa di output.

`culture`: *Stringa*

La cultura da utilizzare per la formattazione.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di stringa risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata. Ad esempio, se la funzione `DATEFORMAT` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca. Il valore `culture` predefinito è **EN-US**.

## <a name="example-1"></a>Esempio 1

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come stringa **"24-12-2015"**, in base al formato personalizzato specificato.

## <a name="example-2"></a>Esempio 2

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]