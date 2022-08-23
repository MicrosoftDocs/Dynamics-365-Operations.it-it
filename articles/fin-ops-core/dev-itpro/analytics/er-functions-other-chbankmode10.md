---
title: Funzione ER CH_BANK_MOD_10
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione CH_BANK_MOD_10 della creazione di report elettronici (ER).
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
ms.openlocfilehash: f658228e0c181bab9e07237adc330dbcb13c95c6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288110"
---
# <a name="ch_bank_mod_10-er-function"></a>Funzione ER CH_BANK_MOD_10

[!include [banner](../includes/banner.md)]

La funzione `CH_BANK_MOD_10` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD10, basato sulle cifre del numero di fattura specificato.

## <a name="syntax"></a>Sintassi

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
