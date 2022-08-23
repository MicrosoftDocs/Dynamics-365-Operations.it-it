---
title: Funzione ER PADLEFT
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione PADLEFT della creazione di report elettronici (ER).
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: dac1f9142a381238bf116c4bce65958da8afc4db
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278890"
---
# <a name="padleft-er-function"></a>Funzione ER PADLEFT

[!include [banner](../includes/banner.md)]

La funzione `PADLEFT` restituisce un valore *Stringa* della lunghezza specificata in cui l'inizio della stringa specificata viene riempita con i caratteri specificati.

## <a name="syntax"></a>Sintassi

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore *Stringa* che rappresenta il testo originale.

`length`: *Intero*

Un valore *Intero* che rappresenta il numero finale di caratteri nella stringa riempita.

`padding chars`: *Stringa*

I caratteri da usare per il riempimento.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`PADLEFT ("1234", 10, "`&nbsp;`")` restituisce la stringa di testo **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
