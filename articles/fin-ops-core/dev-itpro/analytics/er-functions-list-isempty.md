---
title: Funzione ER ISEMPTY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ISEMPTY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: b689e6d4bb849f07db5d00cf8a9dc5c16646a927
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563874"
---
# <a name="isempty-er-function"></a>Funzione ER ISEMPTY

[!include [banner](../includes/banner.md)]

La funzione `ISEMPTY` restituisce un valore *Booleano* **TRUE** se l'elenco specificato non contiene record. In caso contrario, restituisce il valore *Booleano* **FALSE**.

## <a name="syntax"></a>Sintassi

```vb
ISEMPTY (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Booleano*

Il valore *Booleano* risultante.

## <a name="example-1"></a>Esempio 1

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `ISEMPTY(DS)` restituisce **FALSE**.

## <a name="example-2"></a>Esempio 2

L'espressione `ISEMPTY (SPLIT ("",1))` restituisce **TRUE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]