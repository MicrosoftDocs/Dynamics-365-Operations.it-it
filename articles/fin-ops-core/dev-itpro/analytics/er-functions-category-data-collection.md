---
title: Elenco delle funzioni ER nella categoria raccolta dati
description: Questo argomento fornisce informazioni sulle funzioni di raccolta dati supportate nella creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 31b5e7b08a3de77d461fff5e42164975e53dfe1e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748065"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]