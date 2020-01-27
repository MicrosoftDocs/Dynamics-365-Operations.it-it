---
title: Funzione ER INT64VALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INT64VALUE della creazione di report elettronici (ER).
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
ms.openlocfilehash: 75df802b75454baeea75a8ceb32d5d045a77a3a0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916547"
---
# <a name="INT64VALUE">Funzione ER INT64VALUE</a>

[!include [banner](../includes/banner.md)]

La funzione `INT64VALUE` restituisce un valore *Int64* che rappresenta la stringa specificata.

## <a name="syntax-1"></a>Sintassi 1

```
INT64VALUE (text)
```

## <a name="syntax-2"></a>Sintassi 2

```
INT64VALUE (number)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che deve essere convertito in un numero *Int64*.

`number`: *Reale* o *Intero*

Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int64*.

## <a name="return-values"></a>Valori restituiti

*Int64*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Tutte le posizioni decimali sono troncate.

## <a name="example-1"></a>Esempio 1

`INT64VALUE ("22565422744")` restituisce il valore *Int64* **22565422744**.

## <a name="example-2"></a>Esempio 2

`INT64VALUE ( VALUE("22565422744.77"))` restituisce il valore *Int64* **22565422744**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di conversione di tipo](er-functions-category-type-conversion.md)
