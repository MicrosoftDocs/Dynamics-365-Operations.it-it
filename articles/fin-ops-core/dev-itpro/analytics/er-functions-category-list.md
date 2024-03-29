---
title: Elenco delle funzioni ER nella categoria elenco
description: Questo articolo fornisce informazioni sulle funzioni di elenco supportate nella creazione di report elettronici (ER).
author: kfend
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 6c28445f731393857cdb0c75c1244e557b5ff4a4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277694"
---
# <a name="list-of-er-functions-in-the-list-category"></a>Elenco delle funzioni ER nella categoria elenco

[!include [banner](../includes/banner.md)]

Le funzioni dell'elenco della creazione di report elettronici (ER) possono essere utilizzate per estrarre informazioni ed eseguire operazioni sulle origini dati dei tipi di dati *Elenco di record* e *Contenitore (record)*. Questo articolo fornisce un riepilogo di queste funzioni.

## <a name="list-of-supported-functions"></a>Elenco delle funzioni supportate

| Funzione | Descrizione |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | Questa funzione viene eseguite come selezione in memoria. Restituisce un nuovo valore bidimensionale *Elenco di record* costituito da un elenco di record che rappresenta tutti gli elementi che corrispondono al percorso specificato. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | Questa funzione viene eseguita come query SQL con join. Restituisce un nuovo valore bidimensionale *Elenco di record* costituito da un elenco di record che rappresenta tutti gli elementi che corrispondono al percorso specificato. |
| [Conteggio](er-functions-list-count.md)                       | Questa funzione restituisce un valore *Intero* che rappresenta il numero di record nell'elenco specificato, se l'elenco non è vuoto. Se l'elenco è vuoto, questa funzione restituisce **0** (zero). |
| [EmptyList](er-functions-list-emptylist.md)               | Restituisce un valore elenco *Elenco di record* vuoto utilizzando l'elenco specificato come origine della struttura elenco.|
| [Enumerato](er-functions-list-enumerate.md)               | Questa funzione restituisce un nuovo valore *Elenco di record* costituito da record enumerati dell'elenco specificato. |
| [Filtro](er-functions-list-filter.md)                     | Questa funzione restituisce l'elenco specificato come un valore *Elenco di record* dopo che la query è stata modificata in modo da filtrare per la condizione specificata. |
| [Prima](er-functions-list-first.md)                       | Questa funzione restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale elenco non è vuoto. Se l'elenco è vuoto, questa funzione genera un'eccezione. |
| [FirstOrNull](er-functions-list-firstornull.md)           | Questa funzione restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale record non è vuoto. Se il record è vuoto, questa funzione restituisce un valore null *Contenitore (record)*. |
| [Indice](er-functions-list-index.md)                       | Questa funzione restituisce un valore *Contenitore (record)* selezionato utilizzando l'indice numerico specificato nell'elenco specificato. Se l'indice non rientra nell'intervallo dei record nell'elenco specificato, questa funzione genera un'eccezione. |
| [IsEmpty](er-functions-list-isempty.md)                   | Questa funzione restituisce un valore *Booleano* **TRUE** se l'elenco specificato non contiene record. In caso contrario, restituisce il valore *Booleano* **FALSE**. |
| [Elenco](er-functions-list-list.md)                         | Questa funzione restituisce un valore *Elenco di record* costituito da un nuovo elenco creato dagli argomenti specificati.|
| [ListDistinct](er-functions-list-listdistinct.md)         | Questa funzione calcola l'espressione specificata come selettore per ogni record dell'elenco specificato. Restituisce un nuovo valore *Elenco di record* che contiene un singolo record per ogni valore del selettore univoco.|
| [ListJoin](er-functions-list-listjoin.md)                 | Questa funzione restituisce un valore *Elenco di record* che rappresenta un nuovo elenco unito creato dagli argomenti specificati.|
| [ListOfFields](er-functions-list-listoffields.md)         | Questa funzione restituisce un valore *Elenco di record* creato in base alla struttura dell'argomento specificato del tipo *Enumerazione* o *Contenitore (record)*. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | Questa funzione restituisce un nuovo valore *Elenco di record* costituito solo dal primo record dell'elenco specificato.|
| [OrderBy](er-functions-list-orderby.md)                   | Questa funzione restituisce l'elenco specificato come un valore *Elenco di record* dopo che è stato ordinato in base agli argomenti specificati. Questi argomenti possono essere definiti come espressioni. |
| [Ripeti](er-functions-list-repeat.md)                     | Questa funzione crea un record contenente il campo che ha un valore corrispondente all'input specificato. Quindi restituisce un nuovo *Elenco record* di un record che viene ripetuto un determinato numero di volte. |
| [Storna](er-functions-list-reverse.md)                   | Questa funzione restituisce l'elenco specificato come un valore *Elenco di record* in ordine inverso. |
| [Dividi](er-functions-list-split.md)                       | Questa funzione divide la stringa di input specificata in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*. |
| [SplitList](er-functions-list-splitlist.md)               | Questa funzione divide l'elenco specificato in elenchi secondari (o batch) ciascuno dei quali contiene il numero specificato di record. Quindi restituisce il risultato come nuovo valore *Elenco di record* costituito dai batch. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | Questa funzione divide l'elenco specificato in un nuovo elenco di elenchi secondari (batch). Il numero di record in ciascun batch viene calcolato dinamicamente. La funzione restituisce quindi il risultato come nuovo valore *Elenco di record* costituito dai batch. |
| [StringJoin](er-functions-list-stringjoin.md)             | Restituisce un valore *Stringa* costituito da valori concatenati del campo specificato dell'elenco specificato. I valori possono essere separati dal delimitatore specificato. |
| [Percorso](er-functions-list-where.md)                       | Questa funzione restituisce l'elenco specificato come un valore *Elenco di record* dopo che è stato filtrato in base alla condizione specificata. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
