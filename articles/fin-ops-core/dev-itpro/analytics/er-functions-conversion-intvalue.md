---
title: Funzione ER INTVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INTVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2b279de39cf91c3919145735518034fc60cd3341
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917720"
---
# <a name="INTVALUE">Funzione ER INTVALUE</a>

[!include [banner](../includes/banner.md)]

La funzione `INTVALUE` restituisce un valore *Int* che rappresenta la stringa specificata.

## <a name="syntax-1"></a>Sintassi 1

```
INTVALUE (text)
```

## <a name="syntax-2"></a>Sintassi 2

```
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
