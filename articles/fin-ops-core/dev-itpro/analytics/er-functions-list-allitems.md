---
title: Funzione ER ALLITEMS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ALLITEMS della creazione di report elettronici (ER).
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
ms.openlocfilehash: 47113d52e15d3d61f00b3c54229e286eb0f1a8d7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745395"
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

Se si immette **Vend**come origine dati del tipo di dati *Elenco di record* che fa riferimento alla tabella dell'applicazione VendTable, l'espressione `ALLITEMS (Vend.'<Relations'.ContactPerson)` restituisce un elenco bidimensionale di record che ha struttura della tabella **ContactPerson** e contiene tutti i contatti a cui è possibile accedere utilizzando la relazione **ContactPerson.ContactForParty == VendTable.Party**, disponibile per tutti i fornitori dalla tabella fornitori di riferimento.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)
