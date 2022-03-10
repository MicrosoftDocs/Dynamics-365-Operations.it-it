---
title: Funzione ER CURCREDREF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CURCREDREF della creazione di report elettronici (ER).
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
ms.openlocfilehash: c90385c3bf64adfe80fa054e1eb78a6aa368c04eb1758a2e453669bb3d4b7214
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727511"
---
# <a name="curcredref-er-function"></a>Funzione ER CURCREDREF

[!include [banner](../includes/banner.md)]

La funzione `CURCREDREF` restituisce un valore *Stringa* che rappresenta un riferimento creditore basato sulle cifre del numero di fattura specificato.

## <a name="syntax"></a>Sintassi

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argomenti

`invoice number digits`: *Stringa*

Un valore di testo che rappresenta le cifre di un numero di fattura.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`CURCredRef ("VEND-200002")` restituisce **"2200002"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]