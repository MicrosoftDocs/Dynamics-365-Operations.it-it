---
title: Funzione ER SPLIT
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione SPLIT della creazione di report elettronici (ER).
author: kfend
ms.date: 04/01/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e95ecaae46ee73899736b1d5729d7f9639fc6803
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274051"
---
# <a name="split-er-function"></a>Funzione ER SPLIT

[!include [banner](../includes/banner.md)]

La funzione `SPLIT` divide la stringa di input specificata in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*.

## <a name="syntax-1"></a>Sintassi 1

```vb
SPLIT (input, length)
```

Questa sintassi viene utilizzata per dividere la stringa di input specificata in sottostringhe, ciascuna delle quali ha la lunghezza specificata.

## <a name="syntax-2"></a>Sintassi 2

```vb
SPLIT (input, delimiter)
```

Questa sintassi viene utilizzata per dividere la stringa di input specificata in sottostringhe, in base al delimitatore specificato.

## <a name="arguments"></a>Argomenti

`input`: *Stringa*

Testo da dividere.

`length`: *Intero*

La lunghezza massima di una singola sottostringa.

`delimiter`: *Stringa*

Un delimitatore utilizzato per separare le sottostringhe.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

La struttura dei record dell'elenco restituito è costituita dal campo **Valore** del tipo *Stringa*. Ogni record dell'elenco che viene restituito contiene sottostringhe generate in questo campo.

Se l'argomento `delimiter` è vuoto, il nuovo elenco restituito è costituito da un record che ha il campo **Valore** del tipo *Stringa*. Questo campo contiene il testo di input.

Se l'argomento `input` è vuoto, viene restituito un nuovo elenco vuoto. Se l'argomento `input` o `delimiter` non è specificato (null), viene generata un'eccezione dell'applicazione.

## <a name="example-1"></a>Esempio 1

`SPLIT ("abcd", 3)` restituisce un nuovo elenco costituito da due record che hanno il campo **Valore** di tipo *Stringa*. Il campo **Valore** del primo record contiene il testo **"abc"** e il campo **Valore** nel secondo record contiene il testo **"d"**.

## <a name="example-2"></a>Esempio 2

`SPLIT ("XAb aBy", "aB")` restituisce un nuovo elenco costituito da tre record che hanno il campo **Valore** di tipo *Stringa*. Il campo **Value** del primo record contiene il testo **"X"**, il campo **Valore** nel secondo record contiene il testo **"&nbsp;"** e il campo **Valore** del terzo record contiene il testo **"y"**. 

## <a name="example-3"></a>Esempio 3

È possibile usare la funzione [INDEX](er-functions-list-index.md) per accedere a singoli elementi della stringa di input specificata. Se si immette l'origine dati **MyList** del tipo **Campo calcolato** e si configura per la stessa l'espressione `SPLIT("abc", 1)`, l'espressione `INDEX(MyList,2).Value` restituisce il testo **"b"**.

## <a name="example-4"></a>Esempio 4

La funzione [ENUMERATE](er-functions-list-enumerate.md) può anche consentire di accedere a singoli elementi della stringa di input specificata. Se dapprima si inserisce l'origine dati **MyList** del tipo **Campo calcolato** e per la stessa si configura l'espressione `SPLIT("abc", 1)`, quindi si inserisce l'origine dati **EnumeratedList** del tipo **Campo calcolato** e per la stessa si configura l'espressione `ENUMERATE(MyList)`, l'espressione `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` restituisce il testo **"b"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
