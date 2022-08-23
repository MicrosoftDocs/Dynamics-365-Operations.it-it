---
title: Funzione ER INDEX
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione INDEX della creazione di report elettronici (ER).
author: kfend
ms.date: 05/20/2021
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
ms.openlocfilehash: 1ecac869644b09ee6564a4cd0eb53a82de9df25f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274028"
---
# <a name="index-er-function"></a>Funzione ER INDEX

[!include [banner](../includes/banner.md)]

La funzione `INDEX` restituisce un valore *Contenitore (record)* selezionato utilizzando l'indice numerico specificato nell'elenco specificato. Viene generata un'eccezione se l'indice non rientra nell'intervallo dei record nell'elenco specificato.

## <a name="syntax"></a>Sintassi

```vb
INDEX (list, index)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`index`: *Intero*

Un indice numerico che indica la posizione del record desiderato nell'elenco specificato.

> [!NOTE]
> Poiché per questa funzione viene utilizzata la numerazione su base uno, specifica il valore **1** per restituire il primo record dell'elenco specificato.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="example-1"></a>Esempio 1

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e questo contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `DS.Value` restituisce il valore di testo **"B"** per il secondo record in questo elenco di record. L'espressione `INDEX (SPLIT ("A|B|C", "|"), 2).Value` restituisce anche il valore del testo **"B"**.

## <a name="example-2"></a>Esempio 2

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genera un'eccezione in fase di runtime.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
