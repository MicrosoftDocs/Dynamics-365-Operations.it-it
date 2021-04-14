---
title: Funzione ER FILTER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FILTER della creazione di report elettronici (ER).
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
ms.openlocfilehash: aa8c0b4601db625d442dd545151968f38bd58cf1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746605"
---
# <a name="filter-er-function"></a>Funzione ER FILTER

[!include [banner](../includes/banner.md)]

La funzione `FILTER` restituisce l'elenco specificato come un valore *Elenco di record* dopo che la query è stata modificata in modo da filtrare per la condizione specificata.

## <a name="syntax"></a>Sintassi

```vb
FILTER (list, condition)
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

Diversamente dalla funzione [WHERE](er-functions-list-where.md), la condizione specificata viene applicata a livello di database a qualsiasi origine dati della creazione di report elettronici (ER) del tipo di *Table records*. L'elenco e la condizione possono essere definite mediante le tabelle e le relazioni.

Se uno o entrambi gli argomenti configurati per questa funzione (`list` e `condition`) non consentono di convertire questa richiesta nella chiamata SQL diretta, al momento della progettazione viene generata un'eccezione. Questa eccezione informa l'utente che `list` o `condition` non può essere usato per eseguire query sul database.

## <a name="example-1"></a>Esempio 1

Se viene configurato **Vendor** come origine dati ER che fa riferimento alla tabella VendTable, l'espressione `FILTER (Vendors, Vendors.VendGroup = "40")` restituisce un elenco solo dei fornitori che appartengono al gruppo 40.

## <a name="example-2"></a>Esempio 2

Se **Vendor** viene configurato come origine dati ER che fa riferimento alla tabella VendTable e se **parmVendorBankGroup** viene configurato come origine dati ER che restituisce un valore del tipo di dati *Stringa*, l'espressione `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` restituisce un elenco costituito solo dai conti fornitore che appartengono a un gruppo bancario specifico.

## <a name="example-3"></a>Esempio 3

Si immette un'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("A,B,C", ",")`. Quindi si inserisce un'altra espressione, `FILTER( DS, DS.Value = "B")`. Quando si tenta di salvare questa espressione nel designer della formula ER, viene generata la seguente eccezione: "Errore di convalida: non è possibile eseguire query sull'espressione di elenco della funzione FILTER".

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]