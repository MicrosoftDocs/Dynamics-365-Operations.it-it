---
title: Funzione REPEAT di ER
description: In questo articolo vengono fornite informazioni sull'utilizzo della funzione REPEAT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 08/01/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-06-01
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: c56139a3c63b03f907b1dcbf4365990d2a13c35a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220691"
---
# <a name="repeat-er-function"></a>Funzione REPEAT di ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La funzione `REPEAT` crea un record contenente il campo che ha un valore corrispondente all'input specificato. Quindi restituisce un nuovo *Elenco record* di un record che viene ripetuto un determinato numero di volte.

## <a name="syntax"></a>Sintassi

```vb
REPEAT (item, number)
```

## <a name="arguments"></a>Argomenti

`item`: qualsiasi tipo di dati [primitivo](er-formula-supported-data-types-primitive.md) o [composito](er-formula-supported-data-types-composite.md) supportato

Il valore da ripetere.

`number`: *Intero*

Il numero di ripetizioni.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

L'elenco dei record ripetuti restituiti espone i seguenti campi:

- Il valore specificato (campo `Item`)
- L'indice del record corrente (campo `Number`)

> [!NOTE]
> Poiché per questa funzione viene utilizzata la numerazione su base uno, il campo `Number` presenta il valore **1** per il primo record dell'elenco risultante.

Puoi utilizzare questa funzione per moltiplicare i dati esistenti in modo da poter eseguire test di prestazioni e volume delle soluzioni di [creazione di report elettronici (ER)](general-electronic-reporting.md) utilizzando lo strumento [Regression Suite Automation Tool (RSAT)](../perf-test/rsat/rsat-overview.md).

## <a name="example"></a>Esempio

Vuoi generare un documento in formato XML che deve contenere tutti gli elementi XML `Party` che hai specificato in un campo di immissione dati nella finestra di dialogo al runtime, prima dell'inizio dell'esecuzione di un formato ER.

Nella figura seguente è illustrato il [formato](er-overview-components.md#format-component) ER. In questo formato, il singolo elemento XML `Party` viene aggiunto per esporre le proprietà di una singola parte.

<a href="./media/er-repeat-function-1.png"><img src="./media/er-repeat-function-1.png" alt="Format structure on the Format tab of the Format designer page." class="alignnone size-full" width="929" height="548" /></a>

L'illustrazione successiva mostra le seguenti origini dati configurate:

- L'origine dati `Party` che rappresenta una singola parte. Il campo `Party.Value` viene utilizzato per esporre un singolo valore di testo.
- L'[origine dati](er-user-input-parameter-data-sources.md) `NumberOfRepeats` che viene utilizzata per offrire un campo di immissione dati nella finestra di dialogo al runtime, in modo da poter specificare il numero di parti da inserire nel documento generato.
- L'origine dati `Party2` che ripete il record `Party` per il numero di volte che hai specificato nell'origine dati `NumberOfRepeats`.

<a href="./media/er-repeat-function-2.png"><img src="./media/er-repeat-function-2.png" alt="Configured data sources on the Mapping tab of the Format designer page." class="alignnone size-full" width="1044" height="411" /></a>

L'illustrazione successiva mostra i data binding del formato ER modificabile creati per generare output in formato XML. Questo output presenta singole parti come nodi enumerati.

<a href="./media/er-repeat-function-3.png"><img src="./media/er-repeat-function-3.png" alt="Configured data bindings on the Mapping tab of the Format designer page." class="alignnone size-full" width="1051" height="417" /></a>

L'illustrazione seguente mostra il risultato quando viene eseguito il formato designato e il valore dell'origine dati `NumberOfRepeats` è **5**.

<a href="./media/er-repeat-function-4.png"><img src="./media/er-repeat-function-4.png" alt="Result of running the format on a new web browser tab." class="alignnone wp-image-290711 size-full" width="400" height="380" /></a>

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
