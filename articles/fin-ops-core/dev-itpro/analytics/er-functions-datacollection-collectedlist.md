---
title: Funzione ER COLLECTEDLIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione COLLECTEDLIST della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: d02f9ac4697a4d65417e522bffb5f40ebfdc237a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681234"
---
# <a name="collectedlist-er-function"></a>Funzione ER COLLECTEDLIST

[!include [banner](../includes/banner.md)]

La funzione `COLLECTEDLIST` restituisce un valore *Elenco di record* che contiene l'elenco di valori restituiti dalla proprietà **Valore chiave dati raccolti** degli elementi di formato e raccolti quando gli elementi di formato sono stati utilizzati per generare documenti in uscita durante l'esecuzione e ciò soddisfa le condizioni specificate. Ogni condizione è costituita da un intervallo di chiavi e un valore chiave.

## <a name="syntax"></a>Sintassi

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
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

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

Le proprietà **Nome chiave dati raccolti** e **Valore chiave dei dati raccolti** possono essere configurate per entrambi i componenti **Sequenza** o **Elemento XML** di un formato ER che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.

Questa funzione restituisce un elenco vuoto se l'opzione **Raccogli dettagli di output** del componente corrente **Common\\File** è disattivato.

Negli argomenti `condition range`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.

Negli argomenti `condition value`, il carattere jolly **"\*"** può essere usato per rappresentare più caratteri.

## <a name="example"></a>Esempio

Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni raccolta dati](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]