---
title: Funzione ER REVERSE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione REVERSE della creazione di report elettronici (ER).
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
ms.openlocfilehash: 96fc3c2f845f84a5435fd0119a7eaa146caa2dc8da9c931ccfe0915af91ed7cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752365"
---
# <a name="reverse-er-function"></a>Funzione ER REVERSE

[!include [banner](../includes/banner.md)]

La funzione `REVERSE` restituisce l'elenco specificato come un valore *Elenco di record* in ordine inverso.

## <a name="syntax"></a>Sintassi

```vb
REVERSE (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="example-1"></a>Esempio 1

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("C|B|A", "|")`, l'espressione `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` restituisce il valore di testo **"C"**.

## <a name="example-2"></a>Esempio 2

Se **Vendor** è configurato come origine dati della creazione di report elettronici (ER) che fa riferimento alla tabella VendTable, l'espressione `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` restituisce un elenco di fornitori ordinato per nome in ordine decrescente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]