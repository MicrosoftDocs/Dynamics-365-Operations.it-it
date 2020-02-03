---
title: Funzione ER POWER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione POWER della creazione di report elettronici (ER).
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
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915903"
---
# <a name="POWER">Funzione ER POWER</a>

[!include [banner](../includes/banner.md)]

La funzione `POWER` restituisce un valore *Reale* che rappresenta il risultato dell'aumento del numero positivo specificato alla potenza specificata.

## <a name="syntax"></a>Sintassi

```
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