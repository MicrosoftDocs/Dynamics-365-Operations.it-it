---
title: Funzione ER EMPTYRECORD
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione EMPTYRECORD della creazione di report elettronici (ER).
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
ms.openlocfilehash: a02cdd085a236065bb3622b36f7d3284144d96e5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041285"
---
# <a name="EMPTYRECORD">Funzione ER EMPTYRECORD</a>

[!include [banner](../includes/banner.md)]

La funzione `EMPTYRECORD` restituisce un valore *Contenitore (record)* nullo che ha la stessa struttura dell'elenco di record o del record specificato.

## <a name="syntax"></a>Sintassi

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record* o *Contenitore (record)*

Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record* o *Contenitore (record)*.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

> [!NOTE] 
> Un record null è un record in cui il valore di tutti i campi è vuoto. Un valore vuoto è **0** (zero) per i numeri, stringa vuota per le stringhe e così via.

## <a name="example"></a>Esempio

`EMPTYRECORD (SPLIT ("abc", 1))` restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT`. Per ulteriori informazioni, vedere [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di record](er-functions-category-record.md)
