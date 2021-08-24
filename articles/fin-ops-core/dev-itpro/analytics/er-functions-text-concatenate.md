---
title: Funzione ER CONCATENATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CONCATENATE della creazione di report elettronici (ER).
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
ms.openlocfilehash: 1507e1b8a31ed45e7c540e4e2ff31b79e8de3b866ffbace9de17d7b3e169e877
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762502"
---
# <a name="concatenate-er-function"></a>Funzione ER CONCATENATE

[!include [banner](../includes/banner.md)]

La funzione `CONCATENATE` restituisce tutte le stringhe di testo specificate come valore *Stringa* dopo che sono stati uniti in una stringa.

## <a name="syntax"></a>Sintassi

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argomenti

`text 1`: *Stringa*

Un riferimento a un'origine dati del tipo dati *Stringa*. Questo argomento è obbligatorio.

`text N`: *Stringa*

Un riferimento a un'origine dati del tipo dati *Stringa*. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`CONCATENATE ("abc", "def")` restituisce **"abcdef"**.

## <a name="usage-notes"></a>Note sull'utilizzo

Anche l'espressione `"abc" & "def"` restituisce **"abcdef"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]