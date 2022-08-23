---
title: Funzione ER DAYOFYEAR
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione DAYOFYEAR della creazione di report elettronici (ER).
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: e49a80b2ef3c7defcfc23e868374cec5832dc913
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292558"
---
# <a name="dayofyear-er-function"></a>Funzione ER DAYOFYEAR

[!include [banner](../includes/banner.md)]

La funzione `DAYOFYEAR` restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra l'1 gennaio e la data specificata.

## <a name="syntax"></a>Sintassi

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>Argomenti

`date`: *Data*

Un valore di data che rappresenta la data da utilizzare per il calcolo del numero di giorni.

## <a name="return-values"></a>Valori restituiti

*Intero*

Il valore numerico risultante.

## <a name="example-1"></a>Esempio 1

`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` restituisce **61**.

## <a name="example-2"></a>Esempio 2

`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` restituisce **1**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
