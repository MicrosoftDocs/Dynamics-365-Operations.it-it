---
title: Funzione ER OR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione OR della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: faf07c5d8b30cd3babe8a6a55ae7effe5ce457a0
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744625"
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
