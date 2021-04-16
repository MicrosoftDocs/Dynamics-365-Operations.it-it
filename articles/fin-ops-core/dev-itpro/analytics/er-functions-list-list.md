---
title: Funzione ER LIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LIST della creazione di report elettronici (ER).
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
ms.openlocfilehash: 50cb8858301c030df07ad4af9fe2a9513f41fead
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750414"
---
# <a name="list-er-function"></a>Funzione ER LIST

[!include [banner](../includes/banner.md)]

La funzione `LIST` restituisce un valore *Elenco di record* costituito da un nuovo elenco di record creato dagli argomenti specificati.

## <a name="syntax"></a>Sintassi

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>Argomenti

`record 1`: *Contenitore (record)*

Un riferimento a un'origine dati del tipo dati *Record*. Questo argomento è obbligatorio.

`record N`: *Contenitore (record)*

Un riferimento a un'origine dati del tipo dati *Record*. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

La struttura dell'elenco che viene creato contiene solo i campi che sono presentati nella struttura di ogni record menzionato negli argomenti.

## <a name="example"></a>Esempio

Immettere l'origine dati **Record 1** del tipo *Contenitore*. Questa origine dati contiene i seguenti campi nidificati del tipo *Campo calcolato*:

- **Codice:** Questo campo contiene un'espressione che restituisce un valore di tipo *Stringa*.
- **Importo:** Questo campo contiene un'espressione che restituisce un valore di tipo *Reale*.

Immettere quindi l'origine dati **Record 2** del tipo *Contenitore*. Questa origine dati contiene i seguenti campi nidificati del tipo *Campo calcolato*:

- **Importo:** Questo campo contiene un'espressione che restituisce un valore di tipo *Reale*.
- **IsValid:** Questo campo contiene un'espressione che restituisce un valore di tipo *Booleano*.

In questo caso, l'espressione `LIST('Record 1', 'Record 2')`restituisce un nuovo elenco che contiene due record. La struttura di questo elenco è composta da un singolo campo **Importo** di tipo *Reale*, perché questo campo è l'unico campo presentato in ogni argomento della funzione chiamata.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]