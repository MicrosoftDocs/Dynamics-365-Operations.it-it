---
title: Funzione ER FIRST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FIRST della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: f108676c2ff8801fddc0a72be3f75d212582efe6b5d96f7515354739eb446532
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740992"
---
# <a name="first-er-function"></a>Funzione ER FIRST

[!include [banner](../includes/banner.md)]

La funzione `FIRST` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale elenco non è vuoto. Se l'elenco è vuoto, questa funzione genera un'eccezione.

## <a name="syntax"></a>Sintassi

```vb
FIRST (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="example-1"></a>Esempio 1

L'espressione `FIRST(SPLIT("ABC",1)).Value` restituisce il valore del testo **"A"**.

## <a name="example-2"></a>Esempio 2

L'espressione `FIRST(SPLIT("",1)).Value` genera un'eccezione in fase di runtime.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]