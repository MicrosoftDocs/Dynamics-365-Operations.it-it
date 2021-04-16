---
title: Funzione ER FIRSTORNULL
description: In questo argomento illustra l'utilizzo della funzione FIRSTORNULL della creazione di report elettronici (ER)
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753218"
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