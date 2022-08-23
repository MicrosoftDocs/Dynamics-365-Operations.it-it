---
title: Funzione ER CHAR
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione CHAR della creazione di report elettronici (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 61e402718723325fc975d577ab76039e3e59691e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288050"
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

La stringa restituita dalla funzione dipende dalla codifica selezionata nell'elemento del formato **FILE** padre. Per un elenco delle codifiche supportate, vedere [Classe di codifica](/dotnet/api/system.text.encoding).

## <a name="example"></a>Esempio

`CHAR (255)` restituisce **"ÿ"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
