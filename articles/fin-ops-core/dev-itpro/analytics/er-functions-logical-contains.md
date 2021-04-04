---
title: Funzione ER CONTAINS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione di creazione di report elettronici (ER) CONTAINS.
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 81964681688cebf870bc9b6c59aff0b7fdd82449
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557530"
---
# <a name="contains-er-function"></a>Funzione ER CONTAINS

[!include [banner](../includes/banner.md)]

La funzione `CONTAINS` determina se l'input specificato contiene il testo specificato. Restituisce un valore *Booleano* **TRUE** se l'input specificato contiene il testo specificato. In caso contrario, restituisce il valore *Booleano* **FALSE**.

## <a name="syntax"></a>Sintassi

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a>Argomenti

`input`: *Stringa*

Il percorso valido di un elemento di un'origine dati di tipo *Stringa* o una costante di stringa, il cui valore potrebbe contenere il secondo argomento.

`search text`: *Stringa*

Il percorso valido di un'origine dati del tipo di dati *Stringa* o una costante di stringa, il cui valore potrebbe contenere il primo argomento.

## <a name="return-values"></a>Valori restituiti

*Boolean*

Il valore *Booleano* risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Questa funzione può essere utilizzata per specificare un'espressione di condizione della funzione [FILTER](er-functions-list-filter.md) solo quando il mapping pertinente è configurato in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) per accedere a [Microsoft Dataverse](../data-entities/data-integration-cds.md). Altrimenti, viene generata un'eccezione in fase di progettazione. Il messaggio ricevuto consiglia di utilizzare la funzione [WHERE](er-functions-list-where.md) anziché la funzione `FILTER`.

## <a name="example-1"></a>Esempio 1

L'espressione `CONTAINS ("abc", "d")` restituisce **FALSE**, mentre l'espressione `CONTAINS ("abc", "C")` restituisce **TRUE**.

## <a name="example-2"></a>Esempio 2

L'espressione `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` restituisce **TRUE** se il valore del campo **Indirizzo** dell'origine dati **modello** contiene la stringa **DEU**. Altrimenti, restituisce **FALSE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)
