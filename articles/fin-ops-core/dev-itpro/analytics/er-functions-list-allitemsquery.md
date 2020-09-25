---
title: Funzione ER ALLITEMSQUERY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ALLITEMSQUERY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 37546fccf804a4522638147d39206997e8c0c24c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745371"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="b6f13-103">Funzione ER ALLITEMSQUERY</span><span class="sxs-lookup"><span data-stu-id="b6f13-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6f13-104">La funzione `ALLITEMSQUERY` viene eseguita come query SQL con join.</span><span class="sxs-lookup"><span data-stu-id="b6f13-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="b6f13-105">Restituisce un nuovo valore bidimensionale *Elenco di record* costituito da un elenco di record che rappresentano tutti gli elementi che corrispondono al percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="b6f13-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6f13-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6f13-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="b6f13-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b6f13-107">Arguments</span></span>

<span data-ttu-id="b6f13-108">`path`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="b6f13-108">`path`: *Record list*</span></span>

<span data-ttu-id="b6f13-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="b6f13-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="b6f13-110">Deve contenere almeno una relazione.</span><span class="sxs-lookup"><span data-stu-id="b6f13-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="b6f13-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b6f13-111">Return values</span></span>

<span data-ttu-id="b6f13-112">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="b6f13-112">*Record list*</span></span>

<span data-ttu-id="b6f13-113">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="b6f13-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b6f13-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="b6f13-114">Usage notes</span></span>

<span data-ttu-id="b6f13-115">Il percorso specificato deve essere definito come percorso di un'origine dati valido in un elemento di origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="b6f13-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="b6f13-116">Deve anche contenere almeno una relazione.</span><span class="sxs-lookup"><span data-stu-id="b6f13-116">It must also contain at least one relation.</span></span> <span data-ttu-id="b6f13-117">Gli elementi di dati come *Stringa* e *Data* del percorso devono generare un errore in fase di progettazione nel generatore di espressioni ER.</span><span class="sxs-lookup"><span data-stu-id="b6f13-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="b6f13-118">Quando questa funzione viene applicata alle origini dati del tipo di dati *Elenco di record*che fa riferimento a un oggetto applicazione che può essere richiamato direttamente utilizzando SQL (ad esempio una tabella, un'entità o una query), viene eseguito come query SQL con join.</span><span class="sxs-lookup"><span data-stu-id="b6f13-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="b6f13-119">Altrimenti, viene eseguita in memoria come funzione [ALLITEMS](er-functions-list-allitems.md).</span><span class="sxs-lookup"><span data-stu-id="b6f13-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="b6f13-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6f13-120">Example</span></span>

<span data-ttu-id="b6f13-121">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="b6f13-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="b6f13-122">Un'origine dati **CustInv** del tipo *Table records* che fa riferimento alla tabella CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="b6f13-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="b6f13-123">Un'origine dati **FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="b6f13-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="b6f13-124">**FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="b6f13-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="b6f13-125">Quando si esegue il mapping di modello per chiamare l'origine dati **JourLines**, viene eseguita la seguente istruzione SQL:</span><span class="sxs-lookup"><span data-stu-id="b6f13-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="b6f13-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b6f13-126">Additional resources</span></span>

[<span data-ttu-id="b6f13-127">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="b6f13-127">List functions</span></span>](er-functions-category-list.md)
