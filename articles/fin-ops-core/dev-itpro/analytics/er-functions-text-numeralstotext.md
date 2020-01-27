---
title: Funzione ER NUMERALSTOTEXT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMERALSTOTEXT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 459123a66dae7a3d87a22b042e1be6585959ac15
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915627"
---
# <a name="NUMERALSTOTEXT">Funzione ER NUMERALSTOTEXT</a>

[!include [banner](../includes/banner.md)]

La funzione `NUMERALSTOTEXT` restituisce il numero specificato come un valore *Stringa* dopo che è stato ovvero convertito in stringhe di testo nella lingua specificata.

## <a name="syntax"></a>Sintassi

```
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>Argomenti

`number`: *Intero* o *Reale*

Un valore numerico che specifica il numero che deve essere convertito.

`language`: *Stringa*

Un valore *Stringa* che rappresenta il codice della lingua.

`currency`: *Stringa*

Un valore *Stringa* che rappresenta il codice della valuta.

`print currency name flag`: *Booleano*

Un valore *Booleano* che indica se un nome di valuta deve essere aggiunto al testo convertito.

`decimal points`: *Intero*

Un valore *Intero* che indica il numero di posizioni decimali che dovrebbe avere il testo convertito.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Il codice lingua è facoltativo. Se viene definito come stringa vuota, viene utilizzato il codice lingua per il contesto di esecuzione. Il codice predefinito della lingua è **EN-US**. Il codice della lingua per il contesto corrente è definito in un elemento **Cartella** o **File** del formato creazione di report elettronici (ER) in esecuzione.

Il codice valuta è facoltativo. Se viene definito come stringa vuota, viene utilizzata la valuta della società per il contesto di esecuzione.

> [!NOTE] 
> Gli argomenti `print currency name flag` e `decimal points` vengono analizzati solo per i codici lingua seguenti: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** e **RU**. Inoltre, l'argomento `print currency name flag` viene analizzato solo per le società in cui il contesto del paese o area supporta la declinazione dei nomi valuta.

## <a name="example-1"></a>Esempio 1

`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` restituisce **"One Thousand Two Hundred Thirty Four and 56"**.

## <a name="example-2"></a>Esempio 2

`NUMERALSTOTEXT (120, "PL", "", false, 0)` restituisce **"Sto dwadzieścia"**. 

## <a name="example-3"></a>Esempio 3

`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` restituisce **"Сто двадцать евро 21 евроцент"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)
