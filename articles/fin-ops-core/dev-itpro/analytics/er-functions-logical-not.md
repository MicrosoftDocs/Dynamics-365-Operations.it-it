---
title: Funzione ER NOT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOT della creazione di report elettronici (ER).
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
ms.openlocfilehash: b15277dba26dc7864193b11a127944daca6b989f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916041"
---
# <a name="NOT">Funzione ER NOT</a>

[!include [banner](../includes/banner.md)]

La funzione `NOT` restituisce il valore logico inverso della condizione specificata come valore *Booleano*.

## <a name="syntax"></a>Sintassi

```
NOT (condition)
```

## <a name="arguments"></a>Argomenti

`condition`: *Booleano*

Un'espressione condizionale valida che deve essere invertita.

## <a name="return-values"></a>Valori restituiti

*Booleano*

Il valore *Booleano* risultante.

## <a name="example"></a>Esempio

`NOT (TRUE)` restituisce **FALSE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)
