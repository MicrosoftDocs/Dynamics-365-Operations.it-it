---
title: Funzione ER CN_GBT_ADDITIONALDIMENSIONID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CN_GBT_ADDITIONALDIMENSIONID della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 5774bb6928ae321af923819d6b2cc609dbf35b99
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564144"
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