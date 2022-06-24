---
title: Funzione ER STRINGJOIN
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione STRINGJOIN della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 08ed76f4dc61ed8afd63ffe99cead4866b63aba9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908505"
---
# <a name="stringjoin-er-function"></a>Funzione ER STRINGJOIN

[!include [banner](../includes/banner.md)]

La funzione `STRINGJOIN` restituisce un valore *Stringa* costituito da valori concatenati del campo specificato dell'elenco specificato. I valori possono essere separati dal delimitatore specificato.

## <a name="syntax"></a>Sintassi

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`field`: *Campo*

Il percorso valido di un campo del tipo di dati *Stringa* nell'elenco specificato.

`delimiter`: *Stringa*

Un delimitatore utilizzato per separare le sottostringhe.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

Se si immette `SPLIT("abc" , 1)`come origine dati **DS**, l'espressione `STRINGJOIN (DS, DS.Value, "-")` restituisce **"a-b-c"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]