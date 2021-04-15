---
title: Funzione LISTDISTINCT ER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LISTDISTINCT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 7/30/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 9ab9354b0fdb1c08c192b90e6bab303cb85ea41a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743825"
---
# <a name="listdistinct-er-function"></a>Funzione LISTDISTINCT ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La funzione  `LISTDISTINCT` calcola l'espressione specificata come selettore per ogni record dell'elenco specificato. Restituisce un nuovo valore *Elenco di record* che contiene un singolo record per ogni valore del selettore univoco.

## <a name="syntax"></a>Sintassi

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>Argomenti

`list`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`selector`: *tipo di dati primitivi*

Un'espressione valida utilizzata per calcolare un valore del selettore per ogni record nell'elenco specificato.

I seguenti tipi di dati sono supportati per questo parametro:

- Boolean
- Data
- DateTime
- Guid
- Integer
- Int64
- Real
- String

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

La struttura dell'elenco creato corrisponde alla struttura dell'elenco specificato.

Lo stesso valore del selettore potrebbe essere calcolato per più record nell'elenco specificato. In questo caso, i valori dei campi del record corrispondente nell'elenco creato sono uguali ai valori del primo record dell'elenco specificato per cui viene calcolato il valore del selettore.

L'esecuzione di questa funzione viene effettuata su qualsiasi origine dati [Reporting elettronico (ER)](general-electronic-reporting.md) del tipo *Elenco di record* presente in memoria.

L'origine dati **GROUPBY** può essere utilizzata anche per generare l'elenco di record per i quali viene calcolato il selettore con valori distinti. Tuttavia, dal punto di vista delle prestazioni e del consumo di memoria, è meglio usare la funzione `LISTDISTINCT` rispetto all'origine dati **GROUPBY**, perché l'esecuzione della funzione viene eseguita in memoria.

## <a name="example"></a>Esempio

L'esempio seguente mostra come ottenere l'elenco dei numeri di conto cliente univoci a cui è stata emessa almeno una fattura di vendita o una fattura di progetto durante un periodo specifico.

1. Immettere l'origine dati **SalesInvoice** del tipo `Record list` che fa riferimento alla tabella delle applicazioni **CustInvoiceJour** e filtra le fatture di vendita per periodi specifici.

    Il campo `InvoiceAccount` di questa origine dati restituisce il numero di conto di un cliente fatturato.

2. Immettere l'origine dati **ProjectInvoice** del tipo `Record list` che fa riferimento alla tabella delle applicazioni **ProjInvoiceJour** e filtrare le fatture del progetto per periodi specifici.

    Il campo `InvoiceAccount` di questa origine dati restituisce il numero di conto di un cliente fatturato.

3. Configuare l'origine dati **AllInvoices** del tipo `Calculated field` che contiene l'espressione `LISTJOIN(SalesInvoice, ProjectInvoice)`.

    Questa origine dati restituisce l'elenco unito di fatture di vendita e fatture di progetto.

4. Configuare l'origine dati **InvoicedCustomer** del tipo `Record list` che contiene l'espressione `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.

    Questa origine dati restituisce un nuovo elenco che contiene un singolo record per ogni cliente univoco che è stato fatturato durante il periodo definito. Il campo `InvoiceAccount` di questo elenco contiene un numero di conto cliente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]