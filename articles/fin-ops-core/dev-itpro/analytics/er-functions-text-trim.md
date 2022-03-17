---
title: Funzione ER TRIM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TRIM della creazione di report elettronici (ER).
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 816f6d6623bb778c9186d294c9b67db7edddd671
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "8367794"
---
# <a name="trim-er-function"></a>Funzione ER TRIM

[!include [banner](../includes/banner.md)]

La funzione `TRIM` restituisce la stringa di testo specificata come un valore *Stringa* dopo che la tabulazione, i caratteri di ritorno a capo, di avanzamento riga e di avanzamento modulo sono stati sostituiti da uno spazio singolo, dopo che gli spazi iniziali e finali sono stati troncati e dopo che più spazi tra le parole sono stati rimossi.

## <a name="syntax"></a>Sintassi

```vb
TRIM (text)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Il percorso valido di un'origine dati del tipo *Stringa*.

## <a name="return-values"></a>Valori restituiti

*String*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

In alcuni casi, potresti voler troncare gli spazi iniziali e finali, ma preferisci mantenere la formattazione per il testo specificato. Ad esempio, quando questo testo rappresenta un indirizzo che può essere immesso nella casella di testo su più righe e potrebbe contenere avanzamento riga e formattazione del ritorno a capo. In questo caso, utilizza la seguente espressione: `REPLACE(text,"^[ \t]+|[ \t]+$","", true)` dove `text` è l'argomento che fa riferimento alla stringa di testo specificata.

## <a name="example-1"></a>Esempio 1

`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` restituisce **"Sample text"**.

## <a name="example-2"></a>Esempio 2

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` restituisce **"Sample text"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)

[Funzione ER REPLACE](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
