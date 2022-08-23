---
title: Funzione ER ADDDAYS
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ADDDAYS della creazione di report elettronici (ER).
author: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 69273794def0dc52dc8e31615c319ccf5067fa77
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274141"
---
# <a name="adddays-er-function"></a>Funzione ER ADDDAYS

[!include [banner](../includes/banner.md)]

La funzione `ADDDAYS` calcola un valore *DateTime* che è il numero specificato di giorni prima o dopo una data di inizio specificata.

## <a name="syntax"></a>Sintassi

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argomenti

`datetime`: *DateTime*

Un valore data/ora che rappresenta la data di inizio.

`days`: *Intero*

Il numero di giorni prima o dopo `datetime`.

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Un valore positivo per `days`produce una data futura. Un valore negativo restituisce una data trascorsa.

## <a name="example-1"></a>Esempio 1

`ADDDAYS (NOW(), 7)` restituisce la data e l'ora di sette giorni in futuro.

## <a name="example-2"></a>Esempio 2

`ADDDAYS (NOW(), -3)` restituisce la data e l'ora di tre giorni in passato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
