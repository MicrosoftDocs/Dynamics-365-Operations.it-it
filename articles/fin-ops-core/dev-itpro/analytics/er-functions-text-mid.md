---
title: Funzione ER MID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione MID della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 9a9ff3f1055f6757d6d4073dbb816773d8bfc8ba
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746269"
---
# <a name="mid-er-function"></a>Funzione ER MID

[!include [banner](../includes/banner.md)]

La funzione `MID` restituisce un valore *Stringa* che presenta il numero specificato di caratteri della stringa specificata all'inizio della posizione specificata.

## <a name="syntax"></a>Sintassi

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore *Stringa* che specifica il testo da cui restituire i caratteri.

`starting position`: *Intero*

Un valore *Intero* che specifica la posizione del primo carattere che deve essere restituito dal testo specificato.

`number of characters`: *Intero*

Un valore *Intero* che specifica il numero di caratteri che deve essere restituito, iniziando dalla posizione di inizio specificata.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Se il valore dell'argomento `starting position` è inferiore a 0 (zero), i caratteri restituiti vengono conteggiati dalla prima posizione nella stringa specificata.

Se il valore dell'argomento `starting position` supera la lunghezza della stringa specificata, viene restituita una stringa vuota.

## <a name="example"></a>Esempio

`MID ("Sample", 2, 3)` restituisce **"amp"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]