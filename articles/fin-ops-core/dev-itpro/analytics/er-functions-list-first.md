---
title: Funzione ER FIRST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FIRST della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: d30c8481866ccf3f7080197b37586a0460a4ad2c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746581"
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