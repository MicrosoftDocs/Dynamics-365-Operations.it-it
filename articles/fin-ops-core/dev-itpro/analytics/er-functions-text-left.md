---
title: Funzione ER LEFT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LEFT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 9e9cdff9bb5c22c74803cf17c056c0ff1af5ef43
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685885"
---
# <a name="left-er-function"></a>Funzione ER LEFT

[!include [banner](../includes/banner.md)]

La funzione `LEFT` restituisce un valore *Stringa* che presenta il numero specificato di caratteri dall'inizio della stringa specificata.

## <a name="syntax"></a>Sintassi

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore *Stringa* che rappresenta il testo originale.

`number`: *Intero*

Il numero di caratteri che devono essere restituiti dall'inizio del testo originale.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`LEFT ("Sample", 3)` restituisce **"Sam"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]