---
title: Funzione ER WHERE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione WHERE della creazione di report elettronici (ER).
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
ms.openlocfilehash: 392cf7acebd7ad95bcc0f5d4b7a67500a412a795
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041835"
---
# <a name="WHERE">Funzione ER WHERE</a>

[!include [banner](../includes/banner.md)]

La funzione `WHERE` restituisce l'elenco specificato come un valore *Elenco di record* dopo che è stato filtrato in base alla condizione specificata.

## <a name="syntax"></a>Sintassi

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`condition`: *Booleano*

Un'espressione condizionale valida utilizzata per filtrare i record dell'elenco specificato.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

Questa funzione è diversa dalla funzione [FILTER](er-functions-list-filter.md), perché la condizione specificata viene applicata a qualsiasi origine dati della creazione di report elettronici (ER) del tipo di *Elenco di record* presenti in memoria.

Se gli argomenti configurati per questa funzione (`list` e `condition`) non consentono di convertire questa richiesta nella chiamata SQL diretta, al momento della progettazione viene generato un messaggio di avviso. Questo messaggio informa l'utente che le prestazioni potrebbero essere migliorate se la funzione [v](er-functions-list-filter.md) viene utilizzata al posto della funzione `WHERE`.

## <a name="example-1"></a>Esempio 1

Se viene configurato **Vendor** come origine dati ER che fa riferimento alla tabella VendTable, l'espressione `WHERE (Vendors, Vendors.VendGroup = "40")` restituisce un elenco solo dei fornitori che appartengono al gruppo 40.

## <a name="example-2"></a>Esempio 2

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e questo contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `WHERE( DS, DS.Value = "B")` restituisce un elenco di un solo record che contiene il testo **"B"** nel campo **Valore**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
