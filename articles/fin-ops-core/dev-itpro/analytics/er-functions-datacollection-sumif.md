---
title: Funzione ER SUMIF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SUMIF della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 579b14c713bc5f9831c5e012d16bb3b6f97b1035
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916432"
---
# <a name="SUMIF">Funzione ER SUMIF</a>

[!include [banner](../includes/banner.md)]

La funzione `SUMIF` restituisce un valore *Reale* che rappresenta la somma dei valori restituiti da associazioni di elementi di formato e raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano la condizione specificata. La condizione è costituita da un intervallo di chiavi e un valore chiave.

## <a name="syntax"></a>Sintassi

```
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a>Argomenti

`key name for summing`: *Stringa*

Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** del componente del formato creazione di report elettronici (ER) per il quale il valore dell'associazione deve essere utilizzato per la somma.

La proprietà **Valore chiave dei dati raccolti** può essere configurata per un componente **Sequence** o **XML Element** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Questa funzione restituisce un valore **0** (zero) se l'opzione **Raccogli dettagli di output** del componente corrente **Common\\File** è disattivata.

Nell'argomento `condition range`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.

Nell'argomento `condition value`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.

## <a name="example"></a>Esempio

Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni raccolta dati](er-functions-category-data-collection.md)
