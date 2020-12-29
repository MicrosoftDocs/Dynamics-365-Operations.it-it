---
title: Funzione ER VALUEINLARGE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione VALUEINLARGE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 26a7148a4caa80a191688145bac625bdf0bf83b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686908"
---
# <a name="valueinlarge-er-function"></a>Funzione ER VALUEINLARGE

[!include [banner](../includes/banner.md)]

La funzione `VALUEINLARGE` determina se l'input specificato di tipo *Int64* o *Intero* corrisponde a qualsiasi valore di una voce specificata nell'elenco specificato. La funzione restituisce un valore *Booleano* **TRUE** se l'input specificato corrisponde al risultato dell'esecuzione dell'espressione specificata per almeno un record dell'elenco specificato. In caso contrario, restituisce il valore *Booleano* **FALSE**. Per capire la differenza con la funzione `VALUEIN`, vedere la [Nota di utilizzo](#usage_note) più avanti in questo argomento.

## <a name="syntax"></a>Sintassi

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>Argomenti

`input`: *Campo*

Il percorso valido di un elemento origine dati del tipo *Elenco di record*. Il valore di questa voce verrà associato.

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`list item expression`: *Espressione*

Un'espressione condizionale valida che indica o contiene un singolo campo dell'elenco specificato da utilizzare per la corrispondenza.

## <a name="return-values"></a>Valori restituiti

*Boolean*

Il valore *Booleano* risultante.

## <a name=""></a><a name="usage_note">Note sull'utilizzo</a>

Quando l'input specificato rappresenta un tipo *Int64* o *Intero* di un elemento dell'origine dati, la chiamata è traducibile in un'istruzione SQL diretta, l'elenco specificato viene convertito in una tabella SQL temporanea e la corrispondenza viene eseguita nel database eseguendo una singola query `EXISTS JOIN`. Altrimenti, questa funzione funziona come la funzione [`VALUEIN`](er-functions-logical-valuein.md).

Quando l'input specificato rappresenta un elemento dell'origine dati progettato come elemento diverso dal tipo *Int64* e *Intero*, si verifica un errore in fase di progettazione che informa che la funzione `VALUEINLARGE` non è applicabile per l'espressione ER configurata.

Quando l'espressione della funzione `VALUEINLARGE` viene eseguita e viene utilizzata più di una tabella temporanea nell'ambito di questa esecuzione, si verifica un errore di runtime.

## <a name="example"></a>Esempio

Definire le origini dati seguenti nel mapping di modello:

- L'origine dati **In** del tipo *Record di tabella*.
    - Questa origine dati fa riferimento alla tabella **Intrastat**.
    - L'opzione **Interaziendale** è impostata su **No**.
- L'origine dati **InMemory** del tipo *Campo calcolato*.
    - Questa origine dati contiene l'espressione `WHERE (In, In.Port <> "")`.
- L'origine dati **InFiltered** del tipo *Campo calcolato*.
    - Questa origine dati contiene l'espressione `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.

Quando l'origine dati **InFiltered** è chiamata nell'ambito della società **DEMF**, viene creata una nuova tabella temporanea nel database dell'applicazione, l'elenco dei codici di identificazione dei record raccolti in memoria viene inserito in questa tabella e viene generata la seguente istruzione SQL per restituire i record filtrati della tabella **Intrastat**.

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)

[Funzioni VALUEIN](er-functions-logical-valuein.md)
