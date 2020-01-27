---
title: Funzione ER RIGHT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione RIGHT della creazione di report elettronici (ER).
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
ms.openlocfilehash: 01718f9b153c1d6c46d50a9b17e899ccfba16915
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916731"
---
# <a name="RIGHT">Funzione ER RIGHT</a>

[!include [banner](../includes/banner.md)]

La funzione `RIGHT` restituisce un valore *Stringa* che presenta il numero specificato di caratteri alla fine della stringa specificata.

## <a name="syntax"></a>Sintassi

```
RIGHT (text, number)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore *Stringa* che rappresenta il testo originale.

`number`: *Intero*

Il numero di caratteri che devono essere restituiti dalla fine del testo originale.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`RIGHT ("Sample", 3)` restituisce **"ple"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)
