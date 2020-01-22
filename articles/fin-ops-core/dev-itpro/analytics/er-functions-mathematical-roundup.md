---
title: Funzione ER ROUNDUP
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUNDUP della creazione di report elettronici (ER).
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
ms.openlocfilehash: 84a62639b49db17fef1abcda75bc5ad7f08d1005
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917053"
---
# <a name="ROUNDUP">Funzione ER ROUNDUP</a>

[!include [banner](../includes/banner.md)]

La funzione `ROUNDUP` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato per eccesso al numero di posizioni decimali specificato.

## <a name="syntax"></a>Sintassi

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argomenti

`number`: *Reale*

Un valore numerico che deve essere arrotondato per eccesso.

`decimals`: *Intero*

Un valore numerico che rappresenta il numero di posizioni decimali.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Questa funzione si comporta analogamente a [ROUND](er-functions-mathematical-round.md) ma sempre per eccesso (lontano da zero).

## <a name="example-1"></a>Esempio 1

`ROUNDUP (1200.763, 2)` arrotonda per eccesso a due posti decimali e restituisce **1200.77**.

## <a name="example-2"></a>Esempio 2

`ROUNDUP (1200.767, -3)` arrotonda per eccesso al più vicino multiplo di 1000 e restituisce **2000**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni matematiche](er-functions-category-mathematical.md)
