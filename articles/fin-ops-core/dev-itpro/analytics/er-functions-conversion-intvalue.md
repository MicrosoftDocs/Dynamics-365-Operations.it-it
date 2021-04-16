---
title: Funzione ER INTVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INTVALUE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 71eedde5a22f36a8a827824087633de32c00cc7d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755374"
---
# <a name="intvalue-er-function"></a>Funzione ER INTVALUE

[!include [banner](../includes/banner.md)]

La funzione `INTVALUE` restituisce un valore *Int* che rappresenta la stringa specificata.

## <a name="syntax-1"></a>Sintassi 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che deve essere convertito in un numero *Int*.

`number`: *Reale* o *Intero*

Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int*.

## <a name="return-values"></a>Valori restituiti

*Int*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Tutte le posizioni decimali sono troncate.

## <a name="example-1"></a>Esempio 1

`INTVALUE ("100.77")` restituisce il valore *Int* **100**.

## <a name="example-2"></a>Esempio 2

`INTVALUE (-100.77)` restituisce il valore *Int* **-100**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di conversione di tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]