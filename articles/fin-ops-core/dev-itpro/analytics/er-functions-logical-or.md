---
title: Funzione ER OR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione OR della creazione di report elettronici (ER).
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
ms.openlocfilehash: f6751c70599b5e3c05b9d1c69a95e82673b230210170cfead1e6a87c57d59c7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747571"
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