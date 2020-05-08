---
title: Linguaggio della formula nella creazione di report elettronici
description: In questo argomento sono riportate le informazioni sull'utilizzo del linguaggio della formula nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/18/2019
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
ms.openlocfilehash: 79b4640a23d4fc78ade4de57e4071abe6c9ecb56
ms.sourcegitcommit: 0d7b700950b1f95dc030ceab5bbdfd4fe1f79ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284358"
---
# <a name="electronic-reporting-formula-language"></a>Linguaggio della formula nella creazione di report elettronici

[!include [banner](../includes/banner.md)]

La creazione di report elettronici (ER) offre una potente esperienza di trasformazione dei dati. l linguaggio utilizzato per esprimere le manipolazioni dei dati richieste in [Designer formula ER](general-electronic-reporting-formula-designer.md) è simile al linguaggio delle formule in Microsoft Excel.

## <a name="basic-syntax"></a>Sintassi di base

Le espressioni ER possono contenere qualsiasi o tutti i seguenti elementi:

- [Costanti](#Constants)
- [Operatori](#Operators)
- [Riferimenti](#References)
- [Percorsi](#Paths)
- [Funzioni](#Functions)

## <a name=""></a><a name="Constants">Costanti</a>

È possibile utilizzare testo e costanti numeriche (ovvero valori che non vengono calcolati) nella progettazione delle espressioni. Ad esempio, l'espressione `VALUE ("100") + 20` utilizza la costante numerica **20** e la costante di tipo stringa **"100"** e restituisce il valore numerico **120**.

Le sequenze di escape sono supportate in Designer formula ER. Di conseguenza, è possibile specificare una stringa di espressione che deve essere gestita in modo diverso. Ad esempio, l'espressione `"Leo Tolstoy ""War and Peace"" Volume 1"` restituisce la stringa di testo **Leo Tolstoy "Guerra e pace" Volume 1**.

## <a name=""></a><a name="Operators">Operatori</a>

La seguente tabella mostra agli operatori aritmetici che è possibile utilizzare per eseguire le operazioni matematiche di base, ad esempio addizione, sottrazione, moltiplicazione e divisione.

| Operatore | Significato               | Esempio     |
|----------|-----------------------|-------------|
| +        | Addizione              | `1+2`       |
| -        | Sottrazione, negativa | `5-2`, `-1` |
| \*       | Moltiplicazione        | `7\*8`      |
| /        | Divisione              | `9/3`       |

Nella seguente tabella vengono visualizzati gli operatori di confronto supportati. È possibile utilizzare questi operatori per confrontare due valori.

| Operatore | Significato                  | Esempio      |
|----------|--------------------------|--------------|
| =        | Uguale                    | `X=Y`        |
| &gt;     | Maggiore di             | `X>Y`        |
| &lt;     | Minore di                | `X<Y`        |
| &gt;=    | Maggiore o uguale a | `X>=Y`       |
| &lt;=    | Minore o uguale a    | `X<=Y`       |
| &lt;&gt; | Diverso da             | `X<>Y`       |

Inoltre, è possibile utilizzare una e commerciale (&) come operatore di concatenazione del testo. In questo modo, è possibile unire, o concatenare, una o più stringhe di testo in un testo unico.

| Operatore | Significato     | Esempio                                               |
|----------|-------------|-------------------------------------------------------|
| &        | Concatena | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>Precedenza di operatore

L'ordine in cui le parti di un'espressione composta vengono valutate è importante. Ad esempio, il risultato dell'espressione `1 + 4 / 2` varia a seconda se viene eseguita prima l'addizione o la divisione. È possibile utilizzare le parentesi per definire in modo esplicito come un'espressione viene valutata. Ad esempio, per indicare che l'operazione di addizione deve essere eseguita per prima, è possibile modificare l'espressione precedente in `(1 + 4) / 2`. Se l'ordine delle operazioni in un'espressione non è definito in modo esplicito, l'ordine è basato sulla precedenza predefinita assegnata agli operatori supportati. Nella seguente tabella viene visualizzata la precedenza assegnata a ciascun operatore. Gli operatori con una precedenza più alta (ad esempio, 7) vengono valutati prima degli operatori con una precedenza inferiore (ad esempio, 1).

| Precedenza | Operatori      | Sintassi                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Raggruppamento       | ( … )                                                                   |
| 6          | Accesso a membro  | … . …                                                                   |
| 5          | Chiamata di funzione  | … ( … )                                                                 |
| 4          | Moltiplicativo | … \* …<br>… / …                                                         |
| 3          | Addizione       | … + …<br>… - …                                                          |
| 2          | Confronto     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separazione     | … , …                                                                   |

Se un'espressione include più operatori consecutivi con la stessa precedenza, tali operazioni vengono valutate da sinistra a destra. Ad esempio, l'espressione `1 + 6 / 2 \* 3 > 5` restituisce **true**. Si consiglia di utilizzare le parentesi per indicare in modo esplicito l'ordine desiderato delle operazione nelle espressioni, per rendere le espressioni più facili da leggere e gestire.

## <a name=""></a><a name="References">Riferimenti</a>

Tutte le origini dati del componente ER corrente disponibili nella progettazione di un'espressione possono essere utilizzate come riferimenti denominati. Il componente ER corrente può essere una mappatura del modello o un formato. Ad esempio, la mappatura del modello ER corrente contiene l'origine dati **ReportingDate** che restituisce un valore del tipo di dati *DateTime*. Per formattare correttamente il valore per la generazione del documento, è possibile fare riferimento all'origine dati nell'espressione nel seguente modo: `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`.

Tutti i caratteri nel nome di un'origine dati di riferimento che non rappresentano una lettera di alfabeto devono essere preceduti da una virgoletta singola ('). Se il nome di un'origine dati di riferimento contiene almeno un simbolo che non rappresenta una lettera di alfabeto, il nome deve essere racchiuso tra virgolette singole. Ad esempio, i simboli non alfabetici possono essere segni di punteggiatura o altri simboli scritti. Di seguito sono riportati alcuni esempi.

- L'origine dati **Today's date & time** deve essere utilizzata in un'espressione ER come segue: `'Today''s date & time'`.
- Al metodo **name()** dell'origine dati **Customers** deve essere fatto riferimento in un'espressione ER come segue: `Customers.'name()'`.

Se i metodi delle origini dati dell'applicazione includono dei parametri, la seguente sintassi viene utilizzata per chiamare i metodi:

- Se il metodo **isLanguageRTL** dell'origine dati **System** ha un parametro **EN-US** del tipo di dati *Stringa*, questo metodo deve corrispondere all'espressione ER nel seguente modo: `System.isLanguageRTL("EN-US")`.
- Le virgolette non sono richieste quando un nome di metodo contiene solo simboli alfanumerici. Tuttavia, sono obbligatorie per un metodo di tabella se il nome include le parentesi.

Se l'origine dati **System** viene aggiunta a un mapping ER che fa riferimento alla classe dell'applicazione **Global**, l'espressione `System.isLanguageRTL("EN-US ")` restituisce il valore *Booleano* **FALSE**. L'espressione modificata `System.isLanguageRTL("AR")` restituisce il valore *Booleano* **TRUE**.

È possibile limitare il modo in cui i valori vengono passati ai parametri di questo tipo di metodo:

- Solo le costanti possono essere passate ai metodi di questo tipo. I valori delle costanti vengono definiti in fase di progettazione.
- Solo i tipi di dati primitivi (base) sono supportati per i parametri di questo tipo. I tipi di dati primitivi includono *Intero*, *Reale*, *Booleano* e *Stringa*.

## <a name=""></a><a name="Paths">Percorsi</a>

Quando un'espressione fa riferimento a un'origine dati strutturata, è possibile utilizzare la definizione di percorso per selezionare un elemento primitivo specifico di tale origine dati. Un carattere di punto (.) viene utilizzato per separare i singoli elementi di origine dati strutturata. Ad esempio, la mappatura del modello ER corrente contiene l'origine dati **InvoiceTransactions** e l'origine dati restituisce un elenco di record. La struttura di record **InvoiceTransactions** contiene i campi **AmountDebit** e **AmountCredit** che restituiscono entrambi valori numerici. Pertanto, è possibile progettare la seguente espressione per calcolare l'importo fatturato: `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. La costruzione `InvoiceTransactions.AmountDebit` in questa espressione è il percorso utilizzato per accedere al campo **AmountDebit** dell'origine dati **InvoiceTransactions** del tipo *Elenco di record*.

### <a name="relative-path"></a>Percorso relativo

Se il percorso di un'origine dati strutturata inizia con un segno "at" (@), è un percorso relativo. Viene visualizzato il segno "at" anziché la parte rimanente del percorso assoluto della struttura gerarchica utilizzata. Nella figura seguente viene illustrato un esempio. Qui il percorso assoluto `Ledger.'accountingCurrency()'` indica che il valore della valuta contabile dall'origine dati **Contabilità generale** è inserita nel campo **AccountingCurrency** del modello dati.

![Esempio di percorso assoluto nella pagina di progettazione della mappatura del modello ER](./media/ER-FormulaLanguage-AbsolutePath.png)

L'esempio nella figura seguente mostra come viene utilizzato un percorso relativo. Il percorso relativo `@.AccountNum` indica che il campo **AccountNum** dell'origine dati **Intrastat** (che appare un livello sopra il campo **AccountNum** nella struttura gerarchica del modello dati) viene utilizzato per inserire il numero di conto cliente o fornitore nel campo del modello dati **AccountNum**.

![Esempio di percorso relativo nella pagina di progettazione della mappatura del modello ER](./media/ER-FormulaLanguage-RelativePath1.png)

La parte rimanente del percorso assoluto è anche mostrata in [Editor di formule ER](general-electronic-reporting-formula-designer.md).

![Parte rimanente del percorso assoluto nella pagina di progettazione della formula ER](./media/ER-FormulaLanguage-RelativePath2.png)

## <a name=""></a><a name="Functions">Funzioni</a>

Le funzioni integrate ER possono essere utilizzate nelle espressioni ER. Tutte le origini dati del contesto dell'espressione (vale a dire, la mappatura del modello ER o il formato ER corrente) possono essere utilizzate come parametri di funzioni di chiamata, secondo l'elenco degli argomenti delle funzioni di chiamata. Anche le costanti possono essere utilizzate come parametri delle funzioni di chiamata. Ad esempio, la mappatura del modello ER corrente contiene l'origine dati **InvoiceTransactions** e l'origine dati restituisce un elenco di record. La struttura di record **InvoiceTransactions** contiene i campi **AmountDebit** e **AmountCredit** che restituiscono entrambi valori numerici. Pertanto, per calcolare l'importo fatturato è possibile progettare la seguente espressione che usa la funzione di arrotondamento ER integrata: `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`.

Quando si progettano mappature dei modelli ER e report ER, è possibile utilizzare le funzioni ER dalle seguenti categorie:

- [Funzioni di data e ora](er-functions-category-datetime.md)
- [Funzioni di elenco](er-functions-category-list.md)
- [Funzioni logiche](er-functions-category-logical.md)
- [Funzioni matematiche](er-functions-category-mathematical.md)
- [Funzioni di record](er-functions-category-record.md)
- [Funzioni di testo](er-functions-category-text.md)
- [Funzioni raccolta dati](er-functions-category-data-collection.md)
- [Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)
- [Funzioni di conversione di tipo](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>Estensione dell'elenco di funzioni

ER consente di estendere l'elenco di funzioni utilizzate nelle espressioni ER. A tal fine sono richieste alcune operazioni progettuali. Per informazioni dettagliate, vedere [Estensione dell'elenco di funzioni di creazione di report elettronici (ER)](general-electronic-reporting-formulas-list-extension.md).

## <a name="compound-expressions"></a>Espressioni composte

È possibile creare espressioni composte che utilizzano funzioni di categorie diverse, a condizione che i tipi di dati corrispondano. Quando si usano insieme le funzioni, abbinare il tipo di dati dell'output da una funzione al tipo di dati di input richiesto da un'altra funzione. Ad esempio, per evitare un possibile errore "list-is-empty" in un'associazione di un campo a un elemento in formato ER, combinare le funzioni dalla categoria [Elenco](er-functions-category-list.md) con una funzione dalla categoria [Logica](er-functions-category-logical.md), come mostra il seguente esempio. Qui, la formula utilizza la funzione [IF](er-functions-logical-if.md) per verificare se l'elenco **IntrastatTotals** è vuoto prima di restituire il valore dell'aggregazione richiesta da tale elenco. Se l'elenco **IntrastatTotals** è vuoto, la formula restituisce **0** (zero).

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>Più soluzioni

Spesso, è possibile ottenere lo stesso risultato di trasformazione dei dati in più modi, utilizzando funzioni di categorie diverse o funzioni diverse della stessa categoria. Ad esempio, l'espressione precedente può essere configurata anche usando la funzione [COUNT](er-functions-list-count.md) dalla categoria [Elenco](er-functions-category-list.md).

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Estendere l'elenco delle funzioni di creazione di report elettronici](general-electronic-reporting-formulas-list-extension.md)
