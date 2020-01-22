---
title: Funzione ER CN_GBT_ADDITIONALDIMENSIONID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CN_GBT_ADDITIONALDIMENSIONID della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: df693d745d1fe74b4500dd3fda0cc0c4be21142d
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917030"
---
# <a name="CN_GBT_ADDITIONALDIMENSIONID">Funzione ER CN_GBT_ADDITIONALDIMENSIONID</a>

[!include [banner](../includes/banner.md)]

La funzione `CN_GBT_ADDITIONALDIMENSIONID` restituisce un valore *Stringa* che rappresenta un singolo ID dimensione finanziaria preso dalla stringa specificata. La stringa specificata presenta tutte le dimensioni come un elenco di ID separato da virgole.

## <a name="syntax"></a>Sintassi

```
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
