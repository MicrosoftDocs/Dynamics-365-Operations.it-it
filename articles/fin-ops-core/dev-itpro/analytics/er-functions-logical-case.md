---
title: Funzione ER CASE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CASE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 38b51a4d8bf8dc997bae2ae9206d8e71ca48dec6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916064"
---
# <a name="CASE">Funzione ER CASE</a>

[!include [banner](../includes/banner.md)]

La funzione `CASE` valuta il valore dell'espressione specificata rispetto alle opzioni alternative specificate e restituisce il risultato della prima opzione che è uguale al valore dell'espressione specificata. In caso contrario, restituisce il risultato predefinito facoltativo, se viene specificato un risultato predefinito come ultimo argomento della funzione richiamata che non è preceduto da un'opzione. Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati.

## <a name="syntax"></a>Sintassi

```
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>Argomenti

`expression`: *Tipo di dati primitivo* (booleano, numerico o testo)

Un'espressione valida che restituisce un valore del tipo di dati primitivo.

`option 1`: *Tipo di dati primitivo* (booleano, numerico o testo)

Un'espressione valida che restituisce un valore dello stesso tipo di dati primitivo come l'argomento `expression` della funzione chiamata. Questo argomento è obbligatorio.

`result 1`: *Qualsiasi tipo di dati supportato*

Il risultato restituito che corrisponde all'opzione precedente. Questo argomento è obbligatorio.

`option N`: *Tipo di dati primitivo* (booleano, numerico o testo)

Un'espressione valida che restituisce un valore dello stesso tipo di dati primitivo come l'argomento `expression` della funzione chiamata. Questo argomento è facoltativo.

`result N`: *Qualsiasi tipo di dati supportato*

Il risultato restituito che corrisponde all'opzione precedente. Questo argomento è facoltativo.

`default result`: *Qualsiasi tipo di dati supportato*

Il risultato che dovrebbe essere restituito se non c'è corrispondenza. Questo argomento è facoltativo.

## <a name="return-values"></a>Valori restituiti

*Qualsiasi tipo di dati supportato*

Il valore risultante di uno qualsiasi dei tipi di dati supportati.

## <a name="usage-notes"></a>Note sull'utilizzo

Viene generata un'eccezione in fase di runtime se non vi è corrispondenza e non viene definito un risultato predefinito facoltativo.

Tutti i risultati devono essere specificati utilizzando lo stesso tipo di dati. In fase di progettazione viene generata un'eccezione se i tipi di dati dei risultati configurati non corrispondono.

Se il primo valore dei risultati e il valore dei risultati *N*-esimo sono valori del tipo di dati *Contenitore (record)* o *Elenco di record*, il risultato ha solo i campi esistenti in entrambi i valori.

## <a name="example"></a>Esempio

`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` restituisce la stringa **"WINTER"** se la data della sessione dell'applicazione corrente è compresa tra ottobre e dicembre. In caso contrario, restituisce una stringa vuota.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)
