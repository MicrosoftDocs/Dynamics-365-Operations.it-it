---
title: Funzione ER NULLCONTAINER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLCONTAINER della creazione di report elettronici (ER).
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
ms.openlocfilehash: 1dde102acf18e451cb895b51b28d22102f38936c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915788"
---
# <a name="NULLCONTAINER">Funzione ER NULLCONTAINER</a>

[!include [banner](../includes/banner.md)]

La funzione `NULLCONTAINER` restituisce un valore *Contenitore (record)* nullo che ha la stessa struttura dell'elenco di record o del record specificato.

## <a name="syntax"></a>Sintassi

```
NULLCONTAINER (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record* o *Contenitore (record)*

Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record* o *Contenitore (record)*.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

> [!NOTE] 
> Questa funzione è obsoleta. Usare invece la funzione `EMPTYRECORD`. Per ulteriori informazioni, vedere [EMPTYRECORD](er-functions-record-emptyrecord.md).

## <a name="example"></a>Esempio

`NULLCONTAINER (SPLIT ("abc", 1))` restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT`. Per ulteriori informazioni, vedere [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di record](er-functions-category-record.md)