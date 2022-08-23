---
title: Funzione ER CN_GBT_ADDITIONALDIMENSIONID
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione CN_GBT_ADDITIONALDIMENSIONID della creazione di report elettronici (ER).
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
ms.openlocfilehash: 0ed2593f865a4764b1c6172722d701a0a10ba5f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281754"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>Funzione ER CN_GBT_ADDITIONALDIMENSIONID

[!include [banner](../includes/banner.md)]

La funzione `CN_GBT_ADDITIONALDIMENSIONID` restituisce un valore *Stringa* che rappresenta un singolo ID dimensione finanziaria preso dalla stringa specificata. La stringa specificata presenta tutte le dimensioni come un elenco di ID separato da virgole.

## <a name="syntax"></a>Sintassi

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore *Stringa* che presenta tutte le dimensioni come un elenco di ID separato da virgole.

`number`: Intero

Un valore *Intero* che definisce il codice di sequenza della dimensione richiesta nella stringa specificata.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` restituisce **"CC"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
