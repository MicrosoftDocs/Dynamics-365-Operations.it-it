---
title: Funzione ER ALLITEMSQUERY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ALLITEMSQUERY della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 7995b497a2bd95d4aec9ae6d5f1c3cb790823ea0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746701"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="c7e2e-103">Funzione ER ALLITEMSQUERY</span><span class="sxs-lookup"><span data-stu-id="c7e2e-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7e2e-104">La funzione `ALLITEMSQUERY` viene eseguita come query SQL con join.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="c7e2e-105">Restituisce un nuovo valore bidimensionale *Elenco di record* costituito da un elenco di record che rappresentano tutti gli elementi che corrispondono al percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7e2e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7e2e-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="c7e2e-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c7e2e-107">Arguments</span></span>

<span data-ttu-id="c7e2e-108">`path`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="c7e2e-108">`path`: *Record list*</span></span>

<span data-ttu-id="c7e2e-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="c7e2e-110">Deve contenere almeno una relazione.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="c7e2e-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c7e2e-111">Return values</span></span>

<span data-ttu-id="c7e2e-112">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="c7e2e-112">*Record list*</span></span>

<span data-ttu-id="c7e2e-113">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c7e2e-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="c7e2e-114">Usage notes</span></span>

<span data-ttu-id="c7e2e-115">Il percorso specificato deve essere definito come percorso di un'origine dati valido in un elemento di origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="c7e2e-116">Deve anche contenere almeno una relazione.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-116">It must also contain at least one relation.</span></span> <span data-ttu-id="c7e2e-117">Gli elementi di dati come *Stringa* e *Data* del percorso devono generare un errore in fase di progettazione nel generatore di espressioni ER.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="c7e2e-118">Quando questa funzione viene applicata alle origini dati del tipo di dati *Elenco di record* che fa riferimento a un oggetto applicazione che può essere richiamato direttamente utilizzando SQL (ad esempio una tabella, un'entità o una query), viene eseguito come query SQL con join.</span><span class="sxs-lookup"><span data-stu-id="c7e2e-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="c7e2e-119">Altrimenti, viene eseguita in memoria come funzione [ALLITEMS](er-functions-list-allitems.md).</span><span class="sxs-lookup"><span data-stu-id="c7e2e-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="c7e2e-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7e2e-120">Example</span></span>

<span data-ttu-id="c7e2e-121">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="c7e2e-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="c7e2e-122">Un'origine dati **CustInv** del tipo *Table records* che fa riferimento alla tabella CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="c7e2e-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="c7e2e-123">Un'origine dati **FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="c7e2e-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="c7e2e-124">**FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="c7e2e-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="c7e2e-125">Quando si esegue il mapping di modello per chiamare l'origine dati **JourLines**, viene eseguita la seguente istruzione SQL:</span><span class="sxs-lookup"><span data-stu-id="c7e2e-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="c7e2e-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c7e2e-126">Additional resources</span></span>

[<span data-ttu-id="c7e2e-127">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="c7e2e-127">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]