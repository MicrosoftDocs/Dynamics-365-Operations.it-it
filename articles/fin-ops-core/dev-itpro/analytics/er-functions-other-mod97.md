---
title: Funzione ER MOD_97
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione MOD_97 della creazione di report elettronici (ER).
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
ms.openlocfilehash: b58e06a034fc6d26c891b78c26ac53c87a39b92b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744049"
---
# <a name="mod_97-er-function"></a>Funzione ER MOD_97

[!include [banner](../includes/banner.md)]

La funzione `MOD_97` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD97, basato sulle cifre del numero di fattura specificato.

## <a name="syntax"></a>Sintassi

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a>Argomenti

`invoice number digits`: *Stringa*

Un valore di testo che rappresenta le cifre di un numero di fattura.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`MOD_97 ("VEND-200002")` restituisce **"20000285"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)
