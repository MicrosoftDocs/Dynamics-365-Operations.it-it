---
title: Funzione ER FIRSTORNULL
description: In questo argomento illustra l'utilizzo della funzione FIRSTORNULL della creazione di report elettronici (ER)
author: NickSelin
manager: kfend
ms.date: 11/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 3547eeea3c6fef5cca0699002cc0c35cffd940b3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688045"
---
# <a name="firstornull-er-function"></a>Funzione ER FIRSTORNULL

[!include [banner](../includes/banner.md)]

La funzione `FIRSTORNULL` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto. Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*.

## <a name="syntax"></a>Sintassi

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="example"></a>Esempio

L'espressione `FIRSTORNULL(SPLIT("",1)).Value` restituisce una stringa vuota ( **""**).

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
