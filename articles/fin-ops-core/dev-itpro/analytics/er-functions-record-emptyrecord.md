---
title: Funzione ER EMPTYRECORD
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione EMPTYRECORD della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 6f339347187f145b90f14d56017097ff3d7712e8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886822"
---
# <a name="emptyrecord-er-function"></a>Funzione ER EMPTYRECORD

[!include [banner](../includes/banner.md)]

La funzione `EMPTYRECORD` restituisce un valore *Contenitore (record)* nullo che ha la stessa struttura dell'elenco di record o del record specificato.

## <a name="syntax"></a>Sintassi

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record* o *Contenitore (record)*

Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record* o *Contenitore (record)*.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

> [!NOTE] 
> Un record null è un record in cui il valore di tutti i campi è vuoto. Un valore vuoto è **0** (zero) per i numeri, stringa vuota per le stringhe e così via.

## <a name="example"></a>Esempio

`EMPTYRECORD (SPLIT ("abc", 1))` restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT`. Per ulteriori informazioni, vedere [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di record](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]