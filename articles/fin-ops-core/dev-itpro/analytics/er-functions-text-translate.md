---
title: Funzione ER TRANSLATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TRANSLATE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 0b43c1edb2a26ebe01e8d5cf69e1ff377c6c8bf84e889b6bb3d1828d3dc84b53
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721930"
---
# <a name="translate-er-function"></a>Funzione ER TRANSLATE

[!include [banner](../includes/banner.md)]

La funzione `TRANSLATE` restituisce un valore *Stringa* che contiene il risultato della sostituzione del carattere del testo specificato in caratteri di un altro set fornito.

## <a name="syntax"></a>Sintassi

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Il percorso valido di un'origine dati del tipo *Stringa*.

`pattern`: *Stringa*

Il testo che deve essere sostituito.

`replacement`: *Stringa*

Il testo da utilizzare in sostituzione.

## <a name="return-values"></a>Valori restituiti

*String*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

La funzione `TRANSLATE` sostituisce un carattere alla volta. La funzione sostituisce il primo carattere dell'argomento `text` con il primo carattere dell'argomento `pattern`, quindi il secondo carattere e lo stesso flusso viene seguito fino al termine. Quando un carattere dagli argomenti `text` e `pattern` corrisponde, viene sostituito da un carattere dell'argomento `replacement` che si trova nella stessa posizione del carattere dell'argomento `pattern`. Se un carattere appare più volte nell'argomento `pattern`, viene utilizzata la mappatura dell'argomento `replacement` che corrisponde alla prima occorrenza di questo carattere.

## <a name="example-1"></a>Esempio 1

`TRANSLATE ("abcdef", "cd", "GH")` sostituisce il carattere **"c"** del testo **"abcdef"** specificato con il carattere **"G"** del testo `replacement` dovuto a quanto segue:
-   Il carattere **"C"** è presentato nel testo `pattern` in prima posizione.
-   La prima posizione del testo `replacement` contiene il carattere **"G"**.

## <a name="example-2"></a>Esempio 2

`TRANSLATE ("abcdef", "ccd", "GH")` restituisce **"abGdef"**.

## <a name="example-3"></a>Esempio 3

`TRANSLATE ("abccba", "abc", "123")` restituisce **"123321"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]