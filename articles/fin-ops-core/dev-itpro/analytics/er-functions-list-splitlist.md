---
title: Funzione ER SPLITLIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLITLIST della creazione di report elettronici (ER).
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
ms.openlocfilehash: d0f527dcf313a6a5e3b6601cac9a0f6495f66833
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680341"
---
# <a name="splitlist-er-function"></a>Funzione ER SPLITLIST

[!include [banner](../includes/banner.md)]

La funzione `SPLITLIST` divide l'elenco specificato in elenchi secondari (o batch), ciascuno dei quali contiene il numero specificato di record. Quindi restituisce il risultato come nuovo valore *Elenco di record* costituito dai batch.

## <a name="syntax"></a>Sintassi

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`number`: *Intero*

Il numero massimo di record per batch.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

L'elenco di batch restituito contiene i seguenti elementi:

 - **Value:** *List*

    L'elenco dei record che appartengono al batch corrente.

- **BatchNumber:** *Intero*

    Il numero del batch corrente nell'elenco restituito.

## <a name="example"></a>Esempio

Nella seguente figura, un'origine dati **Lines** viene creata come un elenco di record contenente tre record. Questo elenco viene suddiviso in batch, ciascuno contenente fino a due record.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Nella figura seguente è illustrato il layout di formato progettato. In questo layout di formato, le associazioni all'origine dati **Righe** vengono create per generare l'output in formato XML. Questo output presenta nodi individuali per ogni batch e i record contenuti.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
