---
title: Funzione ER DAYOFYEAR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DAYOFYEAR della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 1080a1c2e30cd7ca64ea43120c11eb90d3c99416
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916340"
---
# <a name="DAYOFYEAR">Funzione ER DAYOFYEAR</a>

[!include [banner](../includes/banner.md)]

La funzione `DAYOFYEAR` restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra l'1 gennaio e la data specificata.

## <a name="syntax"></a>Sintassi

```
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
