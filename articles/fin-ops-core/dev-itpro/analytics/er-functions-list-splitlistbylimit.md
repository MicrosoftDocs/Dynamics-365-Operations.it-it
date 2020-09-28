---
title: Funzione ER SPLITLISTBYLIMIT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLITLISTBYLIMIT della creazione di report elettronici (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bf13b7c1e7cab7c803b352370084421a8180dee
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743436"
---
# <a name="splitlistbylimit-er-function"></a>Funzione ER SPLITLISTBYLIMIT

[!include [banner](../includes/banner.md)]

La funzione `SPLITLISTBYLIMIT` divide l'elenco specificato in un nuovo elenco di elenchi secondari (batch). Il numero di record in ciascun batch viene calcolato dinamicamente. La funzione restituisce quindi il risultato come nuovo valore *Elenco di record* costituito dai batch.

## <a name="syntax"></a>Sintassi

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`limit value`: *Intero* o *Reale*

Il valore massimo del limite utilizzato per dividere l'elenco originale in batch.

`limit source`: *Campo*

Il percorso valido di un campo di tipo *Intero*o *Reale* nell'elenco specificato. Il valore di questo campo definisce di quanto viene aumentata la somma totale.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

L'elenco di batch restituito contiene i seguenti elementi:

- **Value**: *List*

    L'elenco dei record che appartengono al batch corrente.

- **BatchNumber**: *Intero*

    Il numero del batch corrente nell'elenco restituito.

Il limite non è applicato a un singolo articolo dell'elenco originale se l'origine limite supera il limite definito.

## <a name="example"></a>Esempio

L'illustrazione seguente mostra un formato creazione di report elettronici (ER).

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

Nella figura seguente vengono mostrate le origini dati che vengono utilizzate per il formato.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

Nella figura seguente è illustrato il risultato dell'esecuzione del formato. In questo caso, l'output è un elenco di voci doganali.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

Nelle illustrazioni seguenti, lo stesso formato è stato rettificato per presentare l'elenco di voci doganali in batch se un singolo batch deve includere voci doganali e il peso totale non deve superare il limite di 9.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

Nella figura seguente è illustrato il risultato dell'esecuzione del formato rettificato.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> Il limite non si applica all'ultima voce dell'elenco originale poiché il valore (**11**) dell'origine del limite (**weight**) supera il limite definito (**9**). Per ignorare gli elenchi secondari durante la generazione del report, utilizzare la funzione `WHERE` o l'espressione **Enabled** dell'elemento formato corrispondente come necessario.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
