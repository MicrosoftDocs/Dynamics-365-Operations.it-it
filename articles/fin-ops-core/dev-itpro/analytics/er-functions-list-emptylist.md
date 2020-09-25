---
title: Funzione ER EMPTYLIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione EMPTYLIST della creazione di report elettronici (ER).
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
ms.openlocfilehash: 747b661d0dee4e9c27741e167c89f9ef7eefa470
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745323"
---
# <a name="emptylist-er-function"></a>Funzione ER EMPTYLIST

[!include [banner](../includes/banner.md)]

La funzione `EMPTYLIST` restituisce un valore *Elenco di record* vuoto utilizzando l'elenco specificato come origine della struttura elenco.

## <a name="syntax"></a>Sintassi

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="example"></a>Esempio

`EMPTYLIST (SPLIT ("abc", 1))` restituisce un nuovo elenco vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT` utilizzata.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
