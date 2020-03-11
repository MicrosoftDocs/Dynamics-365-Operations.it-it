---
title: Funzione ER ORDERBY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ORDERBY della creazione di report elettronici (ER).
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
ms.openlocfilehash: 0a6b5cddc325625dc5b3d677ffcc1da1f8b829cd
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041954"
---
# <a name="ORDERBY">Funzione ER ORDERBY</a>

[!include [banner](../includes/banner.md)]

La funzione `ORDERBY` restituisce l'elenco specificato come un valore *Elenco di record* dopo che è stato ordinato in base agli argomenti specificati. Questi argomenti possono essere definiti come espressioni.

## <a name="syntax"></a>Sintassi

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`expression 1`: *Campo*

Il percorso valido di un campo dell'origine dati a cui fa riferimento l'argomento `list` della funzione chiamata. Il campo di riferimento deve essere un campo del tipo di dati primitivo. Questo argomento è obbligatorio.

`expression N`: *Campo*

Il percorso valido di un campo dell'origine dati a cui fa riferimento l'argomento `list` della funzione chiamata. Il campo di riferimento deve essere un campo del tipo di dati primitivo. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="example-1"></a>Esempio 1

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("C|B|A", "|")`, l'espressione `FIRST( ORDERBY( DS, DS. Value)).Value` restituisce il valore di testo **"A"**.

## <a name="example-2"></a>Esempio 2

Se **Vendor** è configurato come origine dati della creazione di report elettronici (ER) che fa riferimento alla tabella VendTable, l'espressione `ORDERBY (Vendors, Vendors.'name()')` restituisce un elenco di fornitori ordinato per nome in ordine crescente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
