---
title: Funzione ER ISVALIDCHARACTERISO7064
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ISVALIDCHARACTERISO7064 della creazione di report elettronici (ER).
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
ms.openlocfilehash: 6f6f3326c9ca5cdcb3cef52f243d6d3da34251ce
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915926"
---
# <a name="ISVALIDCHARACTERISO7064">Funzione ER ISVALIDCHARACTERISO7064</a>

[!include [banner](../includes/banner.md)]

La funzione `ISVALIDCHARACTERISO7064` restituisce un valore *Booleano* **TRUE** quando la stringa specificata rappresenta un numero di conto bancario internazionale (IBAN) valido. In caso contrario, restituisce il valore *Booleano* **FALSE**.

## <a name="syntax"></a>Sintassi

```
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che rappresenta un IBAN.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` restituisce **TRUE**. 

`ISVALIDCHARACTERISO7064 ("AT61")` restituisce **FALSE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)
