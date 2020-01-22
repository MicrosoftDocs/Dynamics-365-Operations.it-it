---
title: Funzione ER FIRST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FIRST della creazione di report elettronici (ER).
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
ms.openlocfilehash: 211891a0ad5dc6152ce8d980bcd40a9a6bc7e3e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917352"
---
# <a name="FIRST">Funzione ER FIRST</a>

[!include [banner](../includes/banner.md)]

La funzione `FIRST` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale elenco non è vuoto. Se l'elenco è vuoto, questa funzione genera un'eccezione.

## <a name="syntax"></a>Sintassi

```
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
