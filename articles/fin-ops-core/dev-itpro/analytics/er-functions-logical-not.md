---
title: Funzione ER NOT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/17/2019
ms.topic: article
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751717"
---
# <a name="not-er-function"></a>Funzione ER NOT

[!include [banner](../includes/banner.md)]

La funzione `NOT` restituisce il valore logico inverso della condizione specificata come valore *Booleano*.

## <a name="syntax"></a>Sintassi

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]