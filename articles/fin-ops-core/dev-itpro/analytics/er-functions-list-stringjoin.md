---
title: Funzione ER STRINGJOIN
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione STRINGJOIN della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 586dbcb98d237325188f4b0384580613ab7a9347
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683739"
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