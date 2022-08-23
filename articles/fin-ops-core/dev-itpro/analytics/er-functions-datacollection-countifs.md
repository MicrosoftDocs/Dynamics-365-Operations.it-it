---
title: Funzione ER COUNTIFS
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione COUNTIFS della creazione di report elettronici (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: db5fb5b7c4faf749cf17da261130e3e9c3edf41b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280836"
---
# <a name="countifs-er-function"></a>Funzione ER COUNTIFS

[!include [banner](../includes/banner.md)]

La funzione `COUNTIFS` restituisce un valore *Intero* che rappresenta il numero di elementi di formato raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano le condizioni specificate. Ogni condizione è costituita da un intervallo di chiavi e un valore chiave.

## <a name="syntax"></a>Sintassi

```vb
COUNTIFS (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Argomenti

`condition 1 range`: *Stringa*

Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** di un componente di formato creazione di report elettronici (ER). Questo argomento è obbligatorio.

`condition 1 value`: *Stringa*

Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Valore chiave dati raccolti** di un componente del formato ER. Questo argomento è obbligatorio.

`condition N range`: *Stringa*

Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Nome chiave dati raccolti** di un componente del formato ER. Questi argomenti aggiuntivi sono facoltativi.

`condition N value`: *Stringa*

Un valore che viene restituito dall'espressione che è stata configurata nella proprietà **Valore chiave dati raccolti** di un componente del formato ER. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Intero*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Le proprietà **Nome chiave dati raccolti** e **Valore chiave dei dati raccolti** possono essere configurate per entrambi i componenti **Sequenza** o **Elemento XML** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.

Questa funzione restituisce un valore **0** (zero) se l'opzione **Raccogli dettagli di output** del componente corrente **Common\\File** è disattivata.

Negli argomenti `condition range`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.

Negli argomenti `condition value`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.

## <a name="example"></a>Esempio

Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni raccolta dati](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
