---
title: Funzione ER IF
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione IF della creazione di report elettronici (ER).
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
ms.openlocfilehash: 066cffaebc415305a2481e3bf0f0a5f4e108fabc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844560"
---
# <a name="if-er-function"></a>Funzione ER IF

[!include [banner](../includes/banner.md)]

La funzione `IF` restituisce il primo valore specificato se viene soddisfatta la condizione specificata. In caso contrario, restituisce il secondo valore specificato. Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati.

## <a name="syntax"></a>Sintassi

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>Argomenti

`condition`: *Booleano*

Un'espressione condizionale valida che deve essere testata.

`first value`: *Qualsiasi tipo di dati supportato*

Il risultato che viene restituito se la condizione viene soddisfatta.

`second value`: *Qualsiasi tipo di dati supportato*

Il risultato che viene restituito se la condizione non viene soddisfatta.

## <a name="return-values"></a>Valori restituiti

*Qualsiasi tipo di dati supportato*

Il valore risultante di uno qualsiasi dei tipi di dati supportati.

## <a name="usage-notes"></a>Note sull'utilizzo

Gli argomenti `first value` e `second value` devono essere specificati utilizzando lo stesso tipo di dati. In fase di progettazione viene generata un'eccezione se i tipi di dati dei valori configurati non corrispondono.

Se il primo valore e il secondo valore sono valori del tipo di dati *Contenitore (record)* o *Elenco di record*, il risultato ha solo i campi esistenti in entrambi i valori.

## <a name="example"></a>Esempio

`IF (1=2, "condition is met", "condition is not met")` restituisce la stringa **"condition is not met"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]