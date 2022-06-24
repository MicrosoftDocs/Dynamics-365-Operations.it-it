---
title: Funzione ER OR
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione OR della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: d2783b5aff34e6ab4b5bde5dfe39e92d20892634
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892953"
---
# <a name="or-er-function"></a>Funzione ER OR

[!include [banner](../includes/banner.md)]

La funzione `OR` restituisce un valore *Booleano* **FALSE** se tutte le condizioni specificate sono false. Se una condizione specificata è vera, la funzione restituisce un valore *Booleano* **TRUE**.

## <a name="syntax"></a>Sintassi

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argomenti

`condition 1`: *Booleano*

Un'espressione condizionale valida che deve essere testata. Questo argomento è obbligatorio.

`condition N`: *Booleano*

Un'espressione condizionale valida che deve essere testata. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Booleano*

Il valore *Booleano* risultante.

## <a name="example"></a>Esempio

`OR (1=2, "a"="a")` restituisce **TRUE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]