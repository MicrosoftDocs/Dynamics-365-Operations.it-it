---
title: Funzione ER EMPTYRECORD
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione EMPTYRECORD della creazione di report elettronici (ER).
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
ms.openlocfilehash: 5046a1cb43f12863ddbdf241e8ba72071d1016ce
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280157"
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
