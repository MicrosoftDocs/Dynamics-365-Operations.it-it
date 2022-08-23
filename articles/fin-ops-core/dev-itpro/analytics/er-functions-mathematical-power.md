---
title: Funzione ER POWER
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione POWER della creazione di report elettronici (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9b6693d7c1afebcf9c30d1bf8d72950053c305bd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273998"
---
# <a name="power-er-function"></a>Funzione ER POWER

[!include [banner](../includes/banner.md)]

La funzione `POWER` restituisce un valore *Reale* che rappresenta il risultato dell'aumento del numero positivo specificato alla potenza specificata.

## <a name="syntax"></a>Sintassi

```vb
POWER (number, power)
```

## <a name="arguments"></a>Argomenti

`number`: *Reale* o *Intero*

Un valore numerico che deve essere elevato alla potenza specificata.

`power`: *Reale* o *Intero*

Un valore numerico che rappresenta la potenza specifica.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="example-1"></a>Esempio 1

`POWER (10, 2)` restituisce **100**.

## <a name="example-2"></a>Esempio 2

`POWER (4, 0.5)` restituisce **2**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni matematiche](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
