---
title: Funzione ER STRINGJOIN
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione STRINGJOIN della creazione di report elettronici (ER).
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
ms.openlocfilehash: 99d50313f8097d43b820ffc1c36eef0097e7ec55
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917191"
---
# <a name="STRINGJOIN">Funzione ER STRINGJOIN</a>

[!include [banner](../includes/banner.md)]

La funzione `STRINGJOIN` restituisce un valore *Stringa* costituito da valori concatenati del campo specificato dell'elenco specificato. I valori possono essere separati dal delimitatore specificato.

## <a name="syntax"></a>Sintassi

```
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`field`: *Campo*

Il percorso valido di un campo del tipo di dati *Stringa* nell'elenco specificato.

`delimiter`: *Stringa*

Un delimitatore utilizzato per separare le sottostringhe.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

Se si immette `SPLIT("abc" , 1)`come origine dati **DS**, l'espressione `STRINGJOIN (DS, DS.Value, "-")` restituisce **"a-b-c"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)