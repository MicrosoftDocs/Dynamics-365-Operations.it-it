---
title: Funzione ER GETENUMVALUEBYNAME
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione GETENUMVALUEBYNAME della creazione di report elettronici (ER).
author: kfend
ms.date: 09/23/2020
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
ms.openlocfilehash: eb0c4818c8d5020125d198da4ceb0562605da397
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285971"
---
# <a name="getenumvaluebyname-er-function"></a>Funzione ER GETENUMVALUEBYNAME

[!include [banner](../includes/banner.md)]

La funzione `GETENUMVALUEBYNAME` cerca un valore specifico *Enum* nell'origine dati di enumerazione specificata utilizzando il nome dell'enumerazione specificato come un valore *Stringa*. Se viene trovato il valore *Enum*, la funzione lo restituisce. Altrimenti, la funzione restituisce il valore di enumerazione **nullo**.

## <a name="syntax"></a>Sintassi

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argomenti

`enumeration data source path`: *Enumerazione*

Il percorso valido di un'origine dati di uno dei seguenti tipi di enumerazione:

- Enumerazione di modelli di creazione di report elettronici (ER)
- Enumerazione formato ER
- Enumerazione Microsoft Dynamics 365 Finance

`enumeration value text`: *Stringa*

Un valore di stringa che rappresenta il nome di un singolo valore di enumerazione.

## <a name="return-values"></a>Valori restituiti

*Enum* nullable

Il valore di enumerazione risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Nessuna eccezione viene generata se non viene trovato un valore *Enum* utilizzando il nome del valore di enumerazione specificato come un valore *Stringa*.

## <a name="example-1"></a>Esempio 1

Nella seguente figura viene illustrata l'enumerazione **ReportDirection** introdotta in un modello dati. Tenere presente che le etichette vengono definite per i valori dell'enumerazione.

![Valori disponibili per un'enumerazione del modello di dati.](./media/ER-data-model-enumeration-values.PNG)

La figura di seguito mostra questi dettagli:

- L'origine dati **$ Direction** è configurata in un report ER. Questa origine dati è configurata in base all'enumerazione del modello **ReportDirection**.
- L'espressione `$IsArrivals` viene progettata per l'utilizzo dell'origine dati **$Direction** basata sull'enumerazione di modello come parametro di questa funzione.
- Il valore di questa espressione di confronto è **TRUE**.

![Esempio di enumerazione del modello di dati.](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>Esempio 2

Le funzioni `GETENUMVALUEBYNAME` e [`LISTOFFIELDS`](er-functions-list-listoffields.md) consentono di recuperare i valori e le etichette delle enumerazioni supportate come valori di testo. (Le enumerazioni supportate sono enumerazioni di applicazioni, enumerazioni di modelli di dati ed enumerazioni di formato).

Nella seguente figura viene introdotta l'origine dati **TransType** in un mapping dei modelli. Questa origine dati fa riferimento all'enumerazione dell'applicazione **LedgerTransType**.

![Origine dati di un mapping modello che fa riferimento a un'enumerazione dell'applicazione.](./media/er-functions-text-getenumvaluebyname-example2-1.png)

Nella seguente figura viene mostrata l'origine dati **TransTypeList** configurata in un mapping dei modelli. Questa origine dati è configurata in base all'enumerazione dell'applicazione **TransType**. La funzione `LISTOFFIELDS` viene utilizzata per restituire tutti i valori di enumerazione come un elenco di record che contengono campi. In questo modo vengono esposti i dettagli di ogni valore di enumerazione.

> [!NOTE]
> Il campo **EnumValue** è configurato per l'origine dati **TransTypeList** utilizzando l'espressione `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`. Questo campo restituisce un valore di enumerazione per ogni record in questo elenco.

![Origine dati di un mapping modello che restituisce tutti i valori di enumerazione di un'enumerazione selezionata come elenco di record.](./media/er-functions-text-getenumvaluebyname-example2-2.png)

Nella seguente figura viene mostrata l'origine dati **VendTrans** configurata in un mapping dei modelli. Questa origine dati restituisce i record delle transazioni del fornitore dalla tabella delle applicazioni **VendTrans**. Il tipo di libro mastro di ogni transazione è definito dal valore del campo **TransType**.

> [!NOTE]
> Il campo **TransTypeTitle** è configurato per l'origine dati **VendTrans** utilizzando l'espressione `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`. Questo campo restituisce l'etichetta di un valore di enumerazione della transazione corrente come testo, se questo valore di enumerazione è disponibile. In caso contrario, restituisce una valore di stringa vuota.
>
> Il campo **TransTypeTitle** è associato al campo **LedgerType** di un modello di dati che consente di utilizzare queste informazioni in ogni formato ER che utilizza il modello di dati come origine di dati.

![Origine dati di un mapping modello che restituisce transazioni fornitore.](./media/er-functions-text-getenumvaluebyname-example2-3.png)

La figura seguente mostra come utilizzare il [debugger dell'origine dati](er-debug-data-sources.md) per testare il mapping dei modelli configurato.

![Utilizzo del debugger origine dati per testare il mapping modello configurato.](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

Il campo **LedgerType** di un modello di dati espone le etichette dei tipi di transazione come previsto.

Se prevedi di utilizzare questo approccio per una grande quantità di dati transazionali, è necessario considerare le prestazioni di esecuzione. Per altre informazioni, vedi [Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)

[Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md)

[Funzione ER LISTOFFIELDS](er-functions-list-listoffields.md)

[Funzione ER FIRSTORNULL](er-functions-list-firstornull.md)

[Funzione ER WHERE](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
