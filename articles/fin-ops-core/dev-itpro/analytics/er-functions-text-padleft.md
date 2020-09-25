---
title: Funzione ER PADLEFT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione PADLEFT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 3f8a8e2006fe279b25bbf154c6e1802babf51117
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744361"
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
