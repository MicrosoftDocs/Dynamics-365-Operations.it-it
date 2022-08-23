---
title: Funzione ER DAYS
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione DAYS della creazione di report elettronici (ER).
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
ms.openlocfilehash: a0c50e36bbf0c2bd999a17631e3e00d2feb162fd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268727"
---
# <a name="days-er-function"></a>Funzione ER DAYS

[!include [banner](../includes/banner.md)]

La funzione `DAYS` restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra una data specificata e una seconda data specificata.

## <a name="syntax"></a>Sintassi

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Argomenti

`date 1`: *Data*

Un valore di data che rappresenta la data di inizio per il calcolo del numero di giorni.

`date 2`: *Data*

Un valore di data che rappresenta la data di fine per il calcolo del numero di giorni.

## <a name="return-values"></a>Valori restituiti

*Intero*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

La funzione `DAYS` restituisce un valore positivo quando la prima data è successiva alla seconda data, restituisce **0** (zero) quando la prima data corrisponde alla seconda data o restituisce un valore negativo quando la prima data è antecedente alla seconda data.

## <a name="example"></a>Esempio

`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` restituisce **-1**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
