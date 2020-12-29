---
title: Funzione ER NUMBERVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMBERVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: d3eec6dc5a472f366c9029456fe05cf1e431e1c5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685981"
---
# <a name="numbervalue-er-function"></a>Funzione ER NUMBERVALUE

[!include [banner](../includes/banner.md)]

La funzione `NUMBERVALUE` restituisce un valore *Reale* che viene convertito dal valore *Stringa* specificato. Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati.

## <a name="syntax"></a>Sintassi

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che deve essere convertito in un numero *Reale*.

`decimal separator`: Stringa

Un separatore decimale. Utilizzato per separare le parti intere e frazionarie di un numero decimale.

`digit grouping separator`: *Stringa*

Un separatore di raggruppamento delle cifre. È usato come separatore delle migliaia.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="example"></a>Esempio

`NUMBERVALUE( "1 234,56", ",", " ")` restituisce **1234.56**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di conversione di tipo](er-functions-category-type-conversion.md)
