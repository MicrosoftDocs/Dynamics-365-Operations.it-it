---
title: Funzione ER ENUMERATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ENUMERATE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 34ebbec94644276be4ef9beb1c77638606dd37a0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679464"
---
# <a name="enumerate-er-function"></a>Funzione ER ENUMERATE

[!include [banner](../includes/banner.md)]

La funzione `ENUMERATE` restituisce un nuovo valore *Elenco di record* costituito dai record enumerati dell'elenco specificato.

## <a name="syntax"></a>Sintassi

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

L'elenco dei record enumerati restituiti espone i seguenti elementi aggiuntivi:

- Il record dei campi (componente **Value**)
- L'indice del record corrente (componente **Number**)

## <a name="example"></a>Esempio

Nella seguente illustrazione, un'origine dati **Enumerated** viene creata come elenco enumerato di record fornitori dall'origine dati **Vendors** che fa riferimento alla tabella VendTable.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

L'illustrazione seguente mostra il formato creazione di report elettronici (ER). In questo formato, le associazioni dati vengono create per generare l'output in formato XML. Questo output presenta i singoli fornitori come nodi enumerati.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
