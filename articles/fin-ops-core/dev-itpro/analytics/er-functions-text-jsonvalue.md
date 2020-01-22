---
title: Funzione ER JSONVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione JSONVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: d8209f8ce9d244ab7c82f897e4f59283e94e0522
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915673"
---
# <a name="JSONVALUE">Funzione ER JSONVALUE</a>

[!include [banner](../includes/banner.md)]

La funzione `JSONVALUE` analizza i dati nel formato JSON (JavaScript Object Notation) accessibile nel percorso specificato ed estrae un valore scalare che ha l'ID specifico. Quindi restituisce il valore scalare estratto come valore *Stringa*.

## <a name="syntax"></a>Sintassi

```
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argomenti

`input`: *Stringa*

Il percorso valido di un'origine dati del tipo di dati *Stringa* che contiene dati JSON.

`path`: *Stringa*

L'identificatore di un valore scalare dei dati JSON.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

L'origine dati **JsonField** contiene i dati seguenti nel formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. In questo caso, l'espressione `JSONVALUE (JsonField, "BuildNumber")` restituisce il seguente valore del tipo di dati *Stringa*: **"7.3.1234.1"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)
