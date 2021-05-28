---
title: Funzione ER STARTSWITH
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione di creazione di report elettronici (ER) STARTSWITH.
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 50883bb604d2d1f2947545ce27fa02099e70b0e6
ms.sourcegitcommit: 17cee26b03f7b5afe8a089a0a9b2380e8d377d70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2021
ms.locfileid: "6048844"
---
# <a name="startswith-er-function"></a>Funzione ER STARTSWITH

[!include [banner](../includes/banner.md)]

La funzione `STARTSWITH` determina se l'input specificato inizia con il testo specificato. Restituisce un valore *Booleano* **TRUE** se l'input specificato inizia con il testo specificato. In caso contrario, restituisce il valore *Booleano* **FALSE**.

## <a name="syntax"></a>Sintassi

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a>Argomenti

`input`: *Stringa*

Il percorso valido di un elemento di un'origine dati di tipo *Stringa* o una costante di stringa, il cui valore potrebbe iniziare con il secondo argomento.

`start text`: *Stringa*

Il percorso valido di un'origine dati del tipi di dati *Stringa* o una costante di stringa, il cui valore potrebbe essere all'inizio del primo argomento.

## <a name="return-values"></a>Valori restituiti

*Boolean*

Il valore *Booleano* risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Questa funzione può essere utilizzata per specificare un'espressione di condizione della funzione [FILTER](er-functions-list-filter.md) solo quando il mapping pertinente è configurato in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) per accedere a [Microsoft Dataverse](/power-platform/admin/data-integrator). Altrimenti, viene generata un'eccezione in fase di progettazione. Il messaggio ricevuto consiglia di utilizzare la funzione [WHERE](er-functions-list-where.md) anziché la funzione `FILTER`.

## <a name="example-1"></a>Esempio 1

L'espressione `STARTSWITH ("abc", "d")` restituisce **FALSE**, mentre l'espressione `STARTSWITH ("abc", "A")` restituisce **TRUE**.

## <a name="example-2"></a>Esempio 2

L'espressione `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` restituisce **TRUE** se il valore del campo **Indirizzo** dell'origine dati **modello** inizia con la stringa **123 Coffee Street**. Altrimenti, restituisce **FALSE**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni logiche](er-functions-category-logical.md)
