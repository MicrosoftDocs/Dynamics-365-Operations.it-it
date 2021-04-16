---
title: Funzione ER COUNT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione COUNT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
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
ms.openlocfilehash: a0b780051684ef52d06a9baf78d9b513d9ac1f0e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746629"
---
# <a name="count-er-function"></a>Funzione ER COUNT

[!include [banner](../includes/banner.md)]

La funzione `COUNT` restituisce un valore *Intero* che rappresenta il numero di record nell'elenco specificato, se l'elenco non è vuoto. Se l'elenco è vuoto, questa funzione restituisce **0** (zero).

## <a name="syntax"></a>Sintassi

```vb
COUNT (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Intero*

Il valore numerico risultante.

## <a name="example"></a>Esempio

`COUNT (SPLIT("abcd" , 3))` restituisce **2**, perché al funzione `SPLIT` utilizzata in questo esempio crea un elenco composto da due record.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]