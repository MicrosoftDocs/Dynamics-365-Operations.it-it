---
title: Elenco delle funzioni ER nella categoria raccolta dati
description: Questo argomento fornisce informazioni sulle funzioni di raccolta dati supportate nella creazione di report elettronici (ER).
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
ms.openlocfilehash: b318945c9cd10b237843d26cfdc46fc08e84e268
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917812"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Elenco delle funzioni ER nella categoria raccolta dati

[!include [banner](../includes/banner.md)]

Le funzioni di raccolta dati della creazione di report elettronici (ER) vengono utilizzate per eseguire il conteggio e la somma in un formato ER in esecuzione, in base ai dati dell'output già generati in formato **Testo** o **Xml**. Questo approccio viene utilizzato per migliorare le prestazioni di un formato ER in esecuzione, per immettere valori di totali in esecuzione nei documenti generati e per altri scopi. Questo argomento fornisce un riepilogo di queste funzioni.

## <a name="list-of-supported-functions"></a>Elenco delle funzioni supportate

| Funzione | Descrizione |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Questa funzione restituisce un valore *Elenco di record* che contiene l'elenco di valori restituiti dalla proprietà **Valore chiave dati raccolti** degli elementi di formato e raccolti quando gli elementi di formato sono stati utilizzati per generare un documento in uscita durante l'esecuzione e ciò soddisfa le condizioni specificate. Ogni condizione è costituita da un intervallo di chiavi e un valore chiave. |
| [CountIF](er-functions-datacollection-countif.md) | Questa funzione restituisce un valore *Intero* che rappresenta il numero di elementi di formato raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano la condizione specificata. La condizione è costituita da un intervallo di chiavi e un valore chiave. |
| [CountIFs](er-functions-datacollection-countifs.md) | Questa funzione restituisce un valore *Intero* che rappresenta il numero di elementi di formato raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano le condizioni specificate. Ogni condizione è costituita da un intervallo di chiavi e un valore chiave. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Questa funzione restituisce un valore *Stringa* che rappresenta il nome dell'elemento del formato ER corrente. |
| [SumIF](er-functions-datacollection-sumif.md) | Questa funzione restituisce un valore *Reale* che rappresenta la somma dei valori restituiti da associazioni di elementi di formato e raccolti quando sono stati utilizzati elementi di formato per generare un documento in uscita durante l'esecuzione del formato e che soddisfano la condizione specificata. La condizione è costituita da un intervallo di chiavi e un valore chiave. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Questa funzione restituisce un valore *Reale* che rappresenta la somma dei valori restituiti da associazioni di elementi di formato e raccolti quando sono stati utilizzati elementi di formato per generare un documento in uscita durante l'esecuzione del formato e che soddisfano le condizioni specificate. Ogni condizione è costituita da un intervallo di chiavi e un valore chiave. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)