---
title: Funzione ER FIRSTORNULL
description: In questo articolo illustra l'utilizzo della funzione FIRSTORNULL della creazione di report elettronici (ER)
author: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 7ee1a5c1b6ac13581608f9adbda42fae0706d225
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273190"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
