---
title: Funzione ER CONCATENATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CONCATENATE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: e3d3ff87a59632d58a7c34ef96f856b38f005651
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915765"
---
# <a name="CONCATENATE">Funzione ER CONCATENATE</a>

[!include [banner](../includes/banner.md)]

La funzione `CONCATENATE` restituisce tutte le stringhe di testo specificate come valore *Stringa* dopo che sono stati uniti in una stringa.

## <a name="syntax"></a>Sintassi

```
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argomenti

`text 1`: *Stringa*

Un riferimento a un'origine dati del tipo dati *Stringa*. Questo argomento è obbligatorio.

`text N`: *Stringa*

Un riferimento a un'origine dati del tipo dati *Stringa*. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`CONCATENATE ("abc", "def")` restituisce **"abcdef"**.

## <a name="usage-notes"></a>Note sull'utilizzo

Anche l'espressione `"abc" & "def"` restituisce **"abcdef"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)
