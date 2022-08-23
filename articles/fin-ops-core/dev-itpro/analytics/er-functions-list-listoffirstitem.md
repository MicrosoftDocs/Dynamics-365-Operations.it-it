---
title: Funzione ER LISTOFFIRSTITEM
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione LISTOFFIRSTITEM della creazione di report elettronici (ER).
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
ms.openlocfilehash: dede32c58ef8dc67028ea17b8a26189f62f73593
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275587"
---
# <a name="listoffirstitem-er-function"></a>Funzione ER LISTOFFIRSTITEM

[!include [banner](../includes/banner.md)]

La funzione `LISTOFFIRSTITEM` restituisce un valore *Elenco di record* costituito solo dal primo record dell'elenco specificato.

## <a name="syntax"></a>Sintassi

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="example"></a>Esempio

L'espressione `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` restituisce il valore del testo **"A"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
