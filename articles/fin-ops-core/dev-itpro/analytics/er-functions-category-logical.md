---
title: Elenco delle funzioni ER nella categoria logica
description: Questo argomento fornisce informazioni sulle funzioni logiche supportate nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
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
ms.openlocfilehash: e622778c60646e5cc84cd6e23a5d4954a0fe0bb3
ms.sourcegitcommit: 38ad6f791c3d5688a5dc201a234ba89f155f7f03
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705097"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Elenco delle funzioni ER nella categoria logica

[!include [banner](../includes/banner.md)]

Le funzioni logiche della creazione di report elettronici (ER) possono essere utilizzate per utilizzare i valori logici per eseguire più di un confronto in una singola espressione o testare più condizioni. Questo argomento fornisce un riepilogo di queste funzioni.

## <a name="list-of-supported-functions"></a>Elenco delle funzioni supportate

| Funzione | Descrizione |
|----------|-------------|
| [E](er-functions-logical-and.md)                       | Questa funzione restituisce un valore *Booleano* **TRUE** se tutte le condizioni specificate sono vere. In caso contrario, restituisce il valore *Booleano* **FALSE**. |
| [Caso](er-functions-logical-case.md)                     | Questa funzione valuta il valore dell'espressione specificata rispetto alle opzioni alternative specificate e restituisce il risultato della prima opzione che è uguale al valore dell'espressione specificata. In caso contrario, restituisce un risultato predefinito facoltativo, se viene specificato un risultato predefinito come ultimo argomento della funzione richiamata che non è preceduto da un'opzione. Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati. |
| [Se](er-functions-logical-if.md)                         | Questa funzione restituisce il primo valore specificato se viene soddisfatta la condizione specificata. In caso contrario, restituisce il secondo valore specificato. Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati. |
| [Non](er-functions-logical-not.md)                       | Questa funzione restituisce il valore logico inverso della condizione specificata come valore *Booleano*. |
| [Or](er-functions-logical-or.md)                         | Questa funzione restituisce un valore *Booleano* **FALSE** se tutte le condizioni specificate sono false. Se una condizione specificata è vera, la funzione restituisce un valore *Booleano* **TRUE**. |
| [ValueIn](er-functions-logical-valuein.md)               | Questa funzione determina se l'input specificato corrisponde a qualsiasi valore di una voce specificata nell'elenco specificato. Restituisce un valore *Booleano* **TRUE** se l'input specificato corrisponde al risultato dell'esecuzione dell'espressione specificata per almeno un record dell'elenco specificato. In caso contrario, restituisce il valore *Booleano* **FALSE**. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Questa funzione determina se l'input specificato di tipo *Int64* o *Intero* corrisponde a qualsiasi valore di una voce specificata nell'elenco specificato. Restituisce un valore *Booleano* **TRUE** se l'input specificato corrisponde al risultato dell'esecuzione dell'espressione specificata per almeno un record dell'elenco specificato. In caso contrario, restituisce il valore *Booleano* **FALSE**. |


## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
