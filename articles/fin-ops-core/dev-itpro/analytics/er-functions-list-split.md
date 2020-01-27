---
title: Funzione ER SPLIT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLIT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 31caf7c728a92d31428f47320c074fa9fc35bda6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916110"
---
# <a name="SPLIT">Funzione ER SPLIT</a>

[!include [banner](../includes/banner.md)]

La funzione `SPLIT` divide la stringa di input specificata in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*.

## <a name="syntax-1"></a>Sintassi 1

```
SPLIT (input, length)
```

Questa sintassi viene utilizzata per dividere la stringa di input specificata in sottostringhe, ciascuna delle quali ha la lunghezza specificata.

## <a name="syntax-2"></a>Sintassi 2

```
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

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
