---
title: Funzione ER INDEX
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INDEX della creazione di report elettronici (ER).
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
ms.openlocfilehash: 051e22daa3fe2d6c328e36403201d940f724bd29
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745179"
---
# <a name="index-er-function"></a>Funzione ER INDEX

[!include [banner](../includes/banner.md)]

La funzione `INDEX` restituisce un valore *Contenitore (record)* selezionato utilizzando l'indice numerico specificato nell'elenco specificato. Viene generata un'eccezione se l'indice non rientra nell'intervallo dei record nell'elenco specificato.

## <a name="syntax"></a>Sintassi

```vb
INDEX (list, index)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`index`: *Intero*

Un indice numerico che indica la posizione del record desiderato nell'elenco specificato.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="example-1"></a>Esempio 1

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e questo contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `DS.Value` restituisce il valore di testo **"B"** per il secondo record in questo elenco di record. L'espressione `INDEX (SPLIT ("A|B|C", "|"), 2).Value` restituisce anche il valore del testo **"B"**.

## <a name="example-2"></a>Esempio 2

Se si immette l'origine dati **DS**del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genera un'eccezione in fase di runtime.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
