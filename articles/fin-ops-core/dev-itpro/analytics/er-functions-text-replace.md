---
title: Funzione ER REPLACE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione REPLACE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 83d5095620a938f1ac4b8428fff9209fda7a7831
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201068"
---
# <a name=""></a><a name="REPLACE">Funzione ER REPLACE</a>

[!include [banner](../includes/banner.md)]

La funzione `REPLACE` restituisce la stringa di testo specificata come un valore *Stringa* dopo che tutta o parte di essa è stata sostituita con un'altra stringa.

## <a name="syntax"></a>Sintassi

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Il percorso valido di un'origine dati del tipo *Stringa*.

`pattern`: *Stringa*

Se l'argomento `regular expression flag` è **FALSE**, questo argomento contiene il testo che deve essere sostituito.

Se l'argomento `regular expression flag` è **TRUE**, questo argomento contiene un'espressione regolare che definisce sia un modello di ricerca che il testo sostitutivo.

`replacement`: *Stringa*

Se l'argomento `regular expression flag` è **FALSE**, questo argomento contiene il testo che deve essere usato per la sostituzione.

Se l'argomento `regular expression flag` è **TRUE**, questo argomento non viene utilizzato.

`regular expression flag`: *Booleano*

Un valore *Booleano* che indica se per la sostituzione viene utilizzata un'espressione regolare.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Se l'argomento `regular expression flag` è **TRUE**, questa funzione restituisce la stringa specificata dopo che è stata modificata applicando l'espressione regolare specificata dall'argomento `pattern`. L'espressione regolare viene utilizzata per individuare i caratteri che devono essere sostituiti.

Se l'argomento `regular expression flag` è **FALSO**, questa funzione restituisce la stringa specificata dopo che il set di caratteri definito nell'argomento `pattern` è stato sostituito dai caratteri dell'argomento `replacement`. 

## <a name="example-1"></a>Esempio 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applica un'espressione regolare che rimuove tutti i simboli non numerici e restituisce **"19234564971"**. 

## <a name="example-2"></a>Esempio 2

`REPLACE ("abcdef", "cd", "GH", false)` sostituisce il modello **"cd"** con la stringa **"GH"** e restituisce **"abGHef"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)
