---
title: Funzione ER ORDERBY
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ORDERBY della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 1a922405ea23d2b1ff5ac062785e68626edbc8f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883761"
---
# <a name="orderby-er-function"></a>Funzione ER ORDERBY

[!include [banner](../includes/banner.md)]

La funzione `ORDERBY` restituisce l'elenco specificato come un valore *Elenco di record* dopo che è stato ordinato in base agli argomenti specificati. Questi argomenti possono essere definiti come espressioni.

## <a name="syntax-1"></a><a name="syntax-1"></a>Sintassi 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>Sintassi 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Questa sintassi è supportata per Microsoft Dynamics 365 Finance versione 10.0.25 e successiva.

## <a name="arguments"></a>Argomenti

`location`: *[Stringa](er-formula-supported-data-types-primitive.md#string)*

La posizione in cui deve essere eseguito l'ordinamento. Le seguenti opzioni sono valide:

- "Query"
- "InMemory"

`list`: *[Elenco di record](er-formula-supported-data-types-composite.md#record-list)*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

`expression 1`: *Campo*

Il percorso valido di un campo dell'origine dati a cui fa riferimento l'argomento `list` della funzione chiamata. Il campo di riferimento deve essere un campo del tipo di dati primitivo. Questo argomento è obbligatorio.

`expression N`: *Campo*

Il percorso valido di un campo dell'origine dati a cui fa riferimento l'argomento `list` della funzione chiamata. Il campo di riferimento deve essere un campo del tipo di dati primitivo. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

### <a name="syntax-1"></a>Sintassi 1

L'ordinamento dei dati viene sempre eseguito nella memoria del server delle applicazioni. Per ulteriori dettagli, vedi l'[esempio 1](#example-1).

### <a name="syntax-2"></a>Sintassi 2

### <a name="sorting-in-memory"></a>Ordinamento in memoria

Quando l'argomento `location` è specificato come **InMemory**, l'ordinamento dei dati viene eseguito nella memoria di un server delle applicazioni. Per ulteriori dettagli, vedi l'[esempio 2](#example-2).

### <a name="sorting-in-database"></a>Ordinamento nel database

Quando l'argomento `location` è specificato come **Query**, l'ordinamento dei dati viene eseguito a livello di database. In questo caso, l'argomento `list` deve puntare a una delle seguenti origini dati [Creazione di report elettronici (ER)](general-electronic-reporting.md) che specifica l'origine dell'applicazione per la quale è possibile stabilire una query diretta del database:

- Origine dati del tipo *Record di tabella*
- Relazione di un'origine dati del tipo *Record di tabella*
- Origine dati del tipo *Campo calcolato*

Gli argomenti `expression 1` e `expression N` devono puntare ai campi di un'origine dati ER che specifica i campi pertinenti dell'origine dell'applicazione per la quale è anche possibile stabilire una query diretta del database.

Se non è possibile stabilire una query diretta al database, si verifica un [errore](er-components-inspections.md#i18) di convalida nella finestra di progettazione del mapping del modello ER. Il messaggio ricevuto indica che l'espressione ER che include la funzione `ORDERBY` non può essere eseguita in fase di esecuzione.

Per prestazioni migliori, è consigliabile utilizzare l'opzione **Query** quando l'ordinamento è configurato per le origini dati dell'applicazione che potrebbero contenere un numero elevato di record (ad esempio, per le tabelle dell'applicazione transazionale).

> [!NOTE]
> La stessa funzione `ORDEBY` non può essere tradotta in una query di database diretta. Pertanto, un'origine dati ER che contiene questa funzione non è interrogabile. Inoltre, non può essere utilizzato nell'ambito delle funzioni ER come [FILTER](er-functions-list-filter.md) e [ALLITEMSQUERY](er-functions-list-allitemsquery.md), dove possono essere utilizzate solo origini dati interrogabili.

Per maggiori dettagli, vedi l'[esempio 3](#example-3) e l'[esempio 4](#example-4).

### <a name="comparability"></a>Comparabilità

Poiché il motore di database SQL e il server delle applicazioni Finance possono utilizzare un valore di classificazione diverso per un singolo carattere, il risultato dell'ordinamento dello stesso elenco di record può differire quando un campo [Stringa](er-formula-supported-data-types-primitive.md#string) viene utilizzato per l'ordinamento. Per ulteriori dettagli, vedi l'[esempio 5](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>Esempio 1: esecuzione predefinita in memoria

Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("C|B|A", "|")`, l'espressione `FIRST( ORDERBY( DS, DS. Value)).Value` restituisce il valore di testo **"A"**.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>Esempio 2: esecuzione esplicita in memoria

Se **Fornitore** è configurato come un'origine dati ER del tipo *Record di tabella* che fa riferimento alla tabella **VendTable**, entrambe le espressioni `ORDERBY (Vendor, Vendor.'name()')` e `ORDERBY ("InMemory", Vendor, Vendor.'name()')` restituiscono un elenco di fornitori ordinato per nome in ordine crescente.

Quando configuri l'espressione `ORDERBY ("Query", Vendor, Vendor.'name()')` nella finestra di progettazione del mapping del modello ER, si verifica un [errore](er-components-inspections.md#i8) di convalida in fase di progettazione, perché il percorso `Vendor.'name()'` si riferisce a un metodo dell'applicazione con una logica che non può essere tradotta in una query diretta del database.

## <a name="example-3-database-query"></a><a name="example-3"></a>Esempio 3: query di database

Se **TaxTransaction** è configurato come origine dati ER del tipo *Record di tabella* che fa riferimento alla tabella **TaxTrans**, l'espressione `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` ordina i record a livello di database dell'applicazione e restituisce un elenco di transazioni fiscali ordinate per codice fiscale in ordine crescente.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>Esempio 4: origini dati interrogabili

Se **TaxTransaction** è configurata come origine dati ER del tipo *Record di tabelle* che fa riferimento alla tabella **TaxTrans**, l'origine dati ER **TaxTransactionFiltered** può essere configurata in modo che contenga l'espressione `FILTER(TaxTransaction, TaxCode="VAT19")` che recupererà le transazioni per un codice fiscale specificato. Poiché l'origine dati ER **TaxTransactionFiltered** configurata è interrogabile, l'espressione `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` può essere configurata per restituire l'elenco delle transazioni fiscali filtrate ordinate per data di transazione in ordine crescente.

Se configuri **TaxTransactionOrdered** come origine dati ER del tipo *Campo calcolato* che contiene l'espressione `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` e un'origine dati ER del tipo *Campo calcolato* che contiene l'espressione `FILTER(TaxTransactionOrdered, TaxCode="VAT19")`, si verifica un [errore](er-components-inspections.md#i18) di convalida in fase di progettazione nella finestra di progettazione del mapping del modello ER. Questo errore si verifica perché il primo argomento della funzione [FILTER](er-functions-list-filter.md#usage-notes) deve fare riferimento a un'origine dati ER interrogabile, ma l'origine dati **TaxTransactionOrdered** che contiene la funzione `ORDERBY` non è interrogabile.

## <a name="example-5-comparability"></a><a name="example-5"></a>Esempio 5: comparabilità

### <a name="prerequisites"></a>Prerequisiti

1. Immetti l'origine dati **DS1** del tipo *Campo calcolato* che contiene l'espressione `SPLIT ("D1|_D2|D3", "|")`
2. Apri la pagina **[Valori della dimensione finanziaria](../../../finance/general-ledger/financial-dimensions.md)** e seleziona la dimensione **CostCenter**.
3. Immetti i seguenti valori di dimensione: **D1**, **\_D2** e **D3**.

### <a name="sorting-in-memory"></a>Ordinamento in memoria

1. Configura l'origine dati **DS2** del tipo *Campo calcolato* che contiene l'espressione `ORDERBY("InMemory", DS1, DS1.Value)`.
2. Tieni presente che l'espressione `FIRST(DS2).Value` restituisce il valore di testo **"D1"**, l'espressione `INDEX(DS2, COUNT(DS2)).Value` restituisce il valore di testo **"\_D2"** e l'espressione `STRINGJOIN(DS2, DS2.Value, "|")` restituisce il valore di testo **"D1\|D3\|\_D2"**.

### <a name="sorting-in-database"></a>Ordinamento nel database

1. Immetti l'origine dati **DS3** del tipo *Record di tabella* che fa riferimento all'entità **FinancialDimensionValueEntity**.
2. Configura l'origine dati **DS4** del tipo *Campo calcolato* che contiene l'espressione `FILTER(DS3, DS3.FinancialDimension="CostCenter")`.
3. Configura l'origine dati **DS5** del tipo *Campo calcolato* che contiene l'espressione `ORDERBY(DS4, DS4.DimensionValue)`.
4. Tieni presente che l'espressione `FIRST(DS5).Value` restituisce il valore di testo **"\_D2"**, l'espressione  `INDEX(DS5, COUNT(DS5)).Value` restituisce il valore di testo **"D3"** e l'espressione `STRINGJOIN(DS5, DS5.Value, "|")` restituisce il valore di testo **"\_D2\|D1\|D3"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
