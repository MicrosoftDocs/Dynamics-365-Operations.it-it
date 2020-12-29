---
title: Funzione ER VALUEIN
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione VALUEIN della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 08/18/2020
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a133067ab74c711084cc1d7f456cbe49acdf79d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686932"
---
# <a name="valuein-er-function"></a>Funzione ER VALUEIN

[!include [banner](../includes/banner.md)]

La funzione `VALUEIN` determina se l'input specificato corrisponde a qualsiasi valore di una voce specificata nell'elenco specificato. Restituisce un valore *Booleano* **TRUE** se l'input specificato corrisponde al risultato dell'esecuzione dell'espressione specificata per almeno un record dell'elenco specificato. In caso contrario, restituisce il valore *Booleano* **FALSE**.

## <a name="syntax"></a>Sintassi

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>Argomenti

`input`: *Campo*

Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record*. Il valore di questa voce verrà associato.

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`list item expression`: *Booleano*

Un'espressione condizionale valida che indica o contiene un singolo campo dell'elenco specificato da utilizzare per la corrispondenza.

## <a name="return-values"></a>Valori restituiti

*Booleano*

Il valore *Booleano* risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

In generale la funzione `VALUEIN` viene convertita in un set di condizioni **OR** . Se l'elenco di condizioni **OR** è grande e la lunghezza totale massima di un'istruzione SQL potrebbe essere superata, prendere in considerazione l'utilizzo della funzione [`VALUEINLARGE`](er-functions-logical-valueinlarge.md).

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

In alcuni casi, può essere tradotta in un'istruzione di database SQL utilizzando l'operatore `EXISTS JOIN`.

## <a name="example-1"></a>Esempio 1

Nel mapping di modelli viene definita l'origine dati **List** del tipo *Campo calcolato*. Questa origine dati contiene l'espressione `SPLIT ("a,b,c", ",")`.

Quando viene chiamata un'origine dati, se è stata configurata come espressione `VALUEIN ("B", List, List.Value)`, restituisce **TRUE**. In questo caso la funzione `VALUEIN` viene convertita nel seguente set di condizioni: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, dove `("B" = "b")` corrisponde a **TRUE**.

Quando viene chiamata un'origine dati, se è stata configurata come espressione `VALUEIN ("B", List, LEFT(List.Value, 0))`, restituisce **FALSE**. In questo caso la funzione `VALUEIN` viene convertita nella seguente condizione: `("B" = "")`, che non corrisponde a **TRUE**.

Il limite massimo per il numero di caratteri nel testo di tale condizione è di 32.768 caratteri. Di conseguenza, evitare di creare origini dati che potrebbero superare il limite in fase di esecuzione. Se il limite viene superato, l'applicazione smette di funzionare e viene generata un'eccezione. Ad esempio, questa situazione può verificarsi se l'origine dati viene configurata come `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` e gli elenchi **List1** e **List2** contengono un ampio volume di record.

In alcuni casi, la funzione `VALUEIN` viene convertita in un'istruzione di database utilizzando l'operatore `EXISTS JOIN`. Questo comportamento avviene quando la funzione [`FILTER`](er-functions-list-filter.md) viene utilizzata e vengono soddisfatte le seguenti condizioni:

- L'opzione **Chiedi query** è disattivata per l'origine dati della funzione `VALUEIN` che fa riferimento all'elenco di record. Nessuna condizione aggiuntiva verrà applicata a questa origine dati in fase di esecuzione.
- Nessuna espressione nidificata è configurata per l'origine dati della funzione `VALUEIN` che fa riferimento all'elenco di record.
- Una voce dell'elenco della funzione `VALUEIN` si riferisce a un campo dell'origine dati specificata, non a un'espressione o un metodo di quell'origine dati.

Può essere opportuno di utilizzare questa opzione anziché la funzione [`WHERE`](er-functions-list-where.md) descritta in precedenza in questo esempio.

## <a name="example-2"></a>Esempio 2

Definire le origini dati seguenti nel mapping di modello:

- L'origine dati **In** del tipo *Record di tabella*. Questa origine dati fa riferimento alla tabella Intrastat.
- L'origine dati **Port** del tipo *Record di tabella*. Questa origine dati fa riferimento alla tabella IntrastatPort.

Quando viene chiamata un'origine dati che è stata configurata come l'espressione `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, la seguente istruzione SQL viene generata per restituire i record filtrati della tabella Intrastat.

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

Per i campi **dataAreaId**, l'istruzione SQL finale viene generata usando l'operatore `IN`.

## <a name="example-3"></a>Esempio 3

Definire le origini dati seguenti nel mapping di modello:

- L'origine dati **Le** del tipo *Campo calcolato*. Questa origine dati contiene l'espressione `SPLIT ("DEMF,GBSI,USMF", ",")`.
- L'origine dati **In** del tipo *Record di tabella*. Questa origine dati fa riferimento alla tabella Intrastat e l'opzione **Cross-company** è attivata.

Quando viene chiamata un'origine dati che è stata configurata come l'espressione `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, l'istruzione SQL finale contiene la condizione seguente.

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)

[Funzioni VALUEINLARGE](er-functions-logical-valueinlarge.md)
