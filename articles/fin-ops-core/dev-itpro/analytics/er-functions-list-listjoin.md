---
title: 'Funzione LISTJOIN ER '
description: In questo argomento vengono fornite informazioni sull'utilizzo della funzione LISTJOIN Electronic reporting (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7f78b687865e63e658c1c1c4f148b50595bf063
ms.sourcegitcommit: 54bdcf8e9b6d1b1aae2a244f7a82754879d12053
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "3740665"
---
# <a name=""></a><a name="LISTJOIN">Funzione LISTJOIN ER</a>

[!include [banner](../includes/banner.md)]

La funzione `LISTJOIN` restituisce un valore *Elenco di record* che rappresenta un nuovo elenco unito di record creato dagli argomenti specificati.

## <a name="syntax"></a>Sintassi

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Argomenti

`list 1`: *Elenco di record*

Un riferimento a un'origine dati del tipo di dati *Elenco di record*. Questo argomento è obbligatorio.

`list N`: *Elenco di record*

Un riferimento a un'origine dati del tipo di dati *Elenco di record*. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

La struttura dell'elenco che viene creato contiene solo i campi presenti nella struttura di ogni elenco di record a cui si fa riferimento negli argomenti.

## <a name="example"></a>Esempio

Immettere l'origine dati **Record 1** del tipo `Container` . Questa origine dati contiene i seguenti campi nidificati del tipo `Calculated field`

- **Codice**: Questo campo contiene un'espressione che restituisce un valore del tipo`String` .
- **Importo**: Questo campo contiene un'espressione che restituisce un valore del tipo`Real` .

Inserire quindi l'origine dati **Record 2** del tipo `Container` . Questa origine dati contiene i seguenti campi nidificati del tipo `Calculated field`

- **Importo**: Questo campo contiene un'espressione che restituisce un valore del tipo`Real` .
- **Funzione**: Questo campo contiene un'espressione che restituisce un valore del tipo`Boolean` .

![Pagina della progettazione mapping modello di ER](./media/er-functions-list-listjoin-image1.gif)

In questo caso, l'espressione `LISTJOIN(LIST('Record 1'), LIST('Record 2'))`restituisce un nuovo elenco che contiene due record.

![Pagina della progettazione mapping modello di ER](./media/er-functions-list-listjoin-image2.gif)

La struttura di questo elenco è costituita da un singolo campo**Importo** di tipo `Real`, perché questo campo è l'unico campo che viene presentato in ogni argomento della funzione chiamata.

![Pagina della progettazione mapping modello di ER](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)

[Eseguire il debug delle origini dati di un formato ER eseguito per analizzare il flusso e la trasformazione dei dati](er-debug-data-sources.md)
