---
title: Funzione ER AND
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione AND della creazione di report elettronici (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1836d25ad07ad1ce735fda5e008a3315626b62bb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041816"
---
# <a name="AND">Funzione ER AND</a>

[!include [banner](../includes/banner.md)]

La funzione `AND` restituisce un valore *Booleano* **TRUE** se tutte le condizioni specificate sono vere. In caso contrario, restituisce il valore *Booleano* **FALSE**.

## <a name="syntax"></a>Sintassi

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argomenti

`condition 1`: *Booleano*

Un'espressione condizionale valida che deve essere testata. Questo argomento è obbligatorio.

`condition N`: *Booleano*

Un'espressione condizionale valida che deve essere testata. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Booleano*

Il valore *Booleano* risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Negli argomenti delle funzioni logiche, è possibile utilizzare riferimenti a origini dati, valori numerici e di testo, valori booleani, operatori di confronto e altre funzioni della creazione di report elettronici (ER). Tuttavia, tutti gli argomenti devono essere valutati in base a un valore *Booleano* **TRUE** o **FALSE**.

## <a name="example"></a>Esempio

`AND (1=1, "a"="a")` restituisce **TRUE**.

`AND (1=2, "a"="a")` restituisce **FALSE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)
