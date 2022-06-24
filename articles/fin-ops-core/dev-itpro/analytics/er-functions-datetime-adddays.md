---
title: Funzione ER ADDDAYS
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ADDDAYS della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: 7cf2031c042ae93512cc85afe6a1b51558f6c8f7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858743"
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