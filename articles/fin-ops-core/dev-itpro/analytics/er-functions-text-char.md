---
title: Funzione ER CHAR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CHAR della creazione di report elettronici (ER).
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
ms.openlocfilehash: 63df7b1ac847e12cf429467dd444450552a59162
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744963"
---
# <a name="char-er-function"></a>Funzione ER CHAR

[!include [banner](../includes/banner.md)]

La funzione `CHAR` restituisce un valore *Stringa* che presenta un singolo carattere a cui si fa riferimento mediante il numero Unicode specificato.

## <a name="syntax"></a>Sintassi

```vb
CHAR (number)
```

## <a name="arguments"></a>Argomenti

`number`: *Intero*

Un numero che corrisponde a un singolo carattere previsto.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

La stringa restituita dalla funzione dipende dalla codifica selezionata nell'elemento del formato **FILE** padre. Per un elenco delle codifiche supportate, vedere [Classe di codifica](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).

## <a name="example"></a>Esempio

`CHAR (255)` restituisce **"ÿ"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)
