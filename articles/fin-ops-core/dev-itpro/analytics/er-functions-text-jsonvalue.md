---
title: Funzione ER JSONVALUE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione JSONVALUE della creazione di report elettronici (ER).
author: kfend
ms.date: 10/25/2021
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
ms.openlocfilehash: fba1141bce91fd7c9da3cd21aef13ce99329f379
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267965"
---
# <a name="jsonvalue-er-function"></a>Funzione ER JSONVALUE

[!include [banner](../includes/banner.md)]

La funzione `JSONVALUE` analizza i dati nel formato JSON (JavaScript Object Notation) accessibile nel percorso specificato ed estrae un valore scalare che ha l'ID specifico. Quindi restituisce il valore scalare estratto come valore *Stringa*.

## <a name="syntax"></a>Sintassi

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argomenti

`input`: *Stringa*

Il percorso valido di un'origine dati del tipo di dati *Stringa* che contiene dati JSON.

`path`: *Stringa*

L'identificatore di un valore scalare dei dati JSON. Usa una barra (/) per separare i nomi dei nodi JSON correlati. Utilizzare la parentesi (\[\]) per specificare l'indice di un particolare valore in un array JSON. Si noti che per questo indice viene utilizzata la numerazione in base zero.

## <a name="return-values"></a>Valori restituiti

*String*

Il valore di testo risultante.

## <a name="example-1"></a>Esempio 1

L'origine dati **JsonField** contiene i dati seguenti nel formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. In questo caso, l'espressione `JSONVALUE (JsonField, "BuildNumber")` restituisce il seguente valore del tipo di dati *Stringa*: **"7.3.1234.1"**.

## <a name="example-2"></a>Esempio 2

L'origine dati **JsonField** del tipo *Campo calcolato* contiene l'espressione seguente: `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

Questa espressione è configurata per restituire un valore [*Stringa*](er-formula-supported-data-types-primitive.md#string) che rappresenta i dati seguenti in formato JSON.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

In questo caso, l'espressione `JSONVALUE(json, "workers/[1]/emails/[0]")` restituisce il valore seguente del tipo di dati *Stringa*: `JohnS@Contoso.com`.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
