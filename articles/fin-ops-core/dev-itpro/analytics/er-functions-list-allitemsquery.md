---
title: Funzione ER ALLITEMSQUERY
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ALLITEMSQUERY della creazione di report elettronici (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: e350dfbe800ddc3e7b1f388fb951d091a283f4e3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285307"
---
# <a name="allitemsquery-er-function"></a>Funzione ER ALLITEMSQUERY

[!include [banner](../includes/banner.md)]

La funzione `ALLITEMSQUERY` viene eseguita come query SQL con join. Restituisce un nuovo valore bidimensionale *Elenco di record* costituito da un elenco di record che rappresentano tutti gli elementi che corrispondono al percorso specificato.

## <a name="syntax"></a>Sintassi

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>Argomenti

`path`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*. Deve contenere almeno una relazione.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

Il percorso specificato deve essere definito come percorso di un'origine dati valido in un elemento di origine dati del tipo di dati *Elenco di record*. Deve anche contenere almeno una relazione. Gli elementi di dati come *Stringa* e *Data* del percorso devono generare un errore in fase di progettazione nel generatore di espressioni ER.

Quando questa funzione viene applicata alle origini dati del tipo di dati *Elenco di record* che fa riferimento a un oggetto applicazione che può essere richiamato direttamente utilizzando SQL (ad esempio una tabella, un'entità o una query), viene eseguito come query SQL con join. Altrimenti, viene eseguita in memoria come funzione [ALLITEMS](er-functions-list-allitems.md).

## <a name="example"></a>Esempio

Definire le origini dati seguenti nel mapping di modello:

- Un'origine dati **CustInv** del tipo *Table records* che fa riferimento alla tabella CustInvoiceTable
- Un'origine dati **FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`
- **FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`

Quando si esegue il mapping di modello per chiamare l'origine dati **JourLines**, viene eseguita la seguente istruzione SQL:

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
