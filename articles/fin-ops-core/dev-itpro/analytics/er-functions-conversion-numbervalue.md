---
title: Funzione ER NUMBERVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMBERVALUE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 84d7f17f37a83547522cf09047b72100f6f5b859
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755350"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]