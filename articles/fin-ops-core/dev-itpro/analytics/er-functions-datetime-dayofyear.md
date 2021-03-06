---
title: Funzione ER DAYOFYEAR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DAYOFYEAR della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 569e988db91ff992fb7db6e7fd6e8c6aa6a1a3e8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746917"
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