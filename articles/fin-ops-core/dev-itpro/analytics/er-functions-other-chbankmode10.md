---
title: Funzione ER CH_BANK_MOD_10
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CH_BANK_MOD_10 della creazione di report elettronici (ER).
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
ms.openlocfilehash: 42a345fc48b0d87b353308060903a6b5156c0e62
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915880"
---
# <a name="CH_BANK_MOD_10">Funzione ER CH_BANK_MOD_10</a>

[!include [banner](../includes/banner.md)]

La funzione `CH_BANK_MOD_10` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD10, basato sulle cifre del numero di fattura specificato.

## <a name="syntax"></a>Sintassi

```
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a>Argomenti

`invoice number digits`: *Stringa*

Un valore di testo che rappresenta le cifre di un numero di fattura.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`CH_BANK_MOD_10 ("VEND-200002")` restituisce **3**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)