---
title: Funzione ER ALLITEMS
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ALLITEMS della creazione di report elettronici (ER).
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: bb469955c66baf875eea80dde8199986e69e2e71
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274111"
---
# <a name="allitems-er-function"></a>Funzione ER ALLITEMS

[!include [banner](../includes/banner.md)]

La funzione `ALLITEMS` viene eseguita come una selezione in memoria e restituisce un nuovo valore bidimensionale *Elenco di record* come un elenco di record che rappresenta tutti gli elementi che corrispondono al percorso specificato.

## <a name="syntax"></a>Sintassi

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>Argomenti

`path`: *Elenco di record*

Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

Il percorso deve essere definito come percorso di un'origine dati valido in un elemento di origine dati del tipo di dati *Elenco di record*. Gli elementi di dati come stringa del percorso e la data devono generare un errore in fase di progettazione nel generatore di espressioni ER.

Non è consigliabile utilizzare questa funzione per origini dati transazionali che potrebbero contenere un grande volume di dati. Considerare invece l'utilizzo della funzione [ALLTEMSQUERY ](er-functions-list-allitemsquery.md).

## <a name="example-1"></a>Esempio 1

Se si immette `SPLIT("abcdef" , 2)`come origine dati **DS**, l'espressione `COUNT( ALLITEMS (DS))` restituisce **3**.

## <a name="example-2"></a>Esempio 2

Se si immette **Vend** come origine dati del tipo di dati *Elenco di record* che fa riferimento alla tabella dell'applicazione VendTable, l'espressione `ALLITEMS (Vend.'<Relations'.ContactPerson)` restituisce un elenco bidimensionale di record che ha struttura della tabella **ContactPerson** e contiene tutti i contatti a cui è possibile accedere utilizzando la relazione **ContactPerson.ContactForParty == VendTable.Party**, disponibile per tutti i fornitori dalla tabella fornitori di riferimento.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
