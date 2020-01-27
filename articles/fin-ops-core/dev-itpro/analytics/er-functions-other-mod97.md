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
ms.openlocfilehash: 23e63f6b7999399fd5365c616613cbc603774d53
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916938"
---
# <a name="MOD_97">Funzione ER MOD_97</a>

[!include [banner](../includes/banner.md)]

La funzione `MOD_97` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD97, basato sulle cifre del numero di fattura specificato.

## <a name="syntax"></a>Sintassi

```
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
