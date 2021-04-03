---
title: Funzione ER ALLITEMSQUERY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ALLITEMSQUERY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 56ac956cdfe28d282b8a80d7caec34a50eca5dbe
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559605"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="02e33-103">Funzione ER ALLITEMSQUERY</span><span class="sxs-lookup"><span data-stu-id="02e33-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02e33-104">La funzione `ALLITEMSQUERY` viene eseguita come query SQL con join.</span><span class="sxs-lookup"><span data-stu-id="02e33-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="02e33-105">Restituisce un nuovo valore bidimensionale *Elenco di record* costituito da un elenco di record che rappresentano tutti gli elementi che corrispondono al percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="02e33-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="02e33-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02e33-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="02e33-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="02e33-107">Arguments</span></span>

<span data-ttu-id="02e33-108">`path`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="02e33-108">`path`: *Record list*</span></span>

<span data-ttu-id="02e33-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="02e33-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="02e33-110">Deve contenere almeno una relazione.</span><span class="sxs-lookup"><span data-stu-id="02e33-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="02e33-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="02e33-111">Return values</span></span>

<span data-ttu-id="02e33-112">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="02e33-112">*Record list*</span></span>

<span data-ttu-id="02e33-113">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="02e33-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="02e33-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="02e33-114">Usage notes</span></span>

<span data-ttu-id="02e33-115">Il percorso specificato deve essere definito come percorso di un'origine dati valido in un elemento di origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="02e33-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="02e33-116">Deve anche contenere almeno una relazione.</span><span class="sxs-lookup"><span data-stu-id="02e33-116">It must also contain at least one relation.</span></span> <span data-ttu-id="02e33-117">Gli elementi di dati come *Stringa* e *Data* del percorso devono generare un errore in fase di progettazione nel generatore di espressioni ER.</span><span class="sxs-lookup"><span data-stu-id="02e33-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="02e33-118">Quando questa funzione viene applicata alle origini dati del tipo di dati *Elenco di record* che fa riferimento a un oggetto applicazione che può essere richiamato direttamente utilizzando SQL (ad esempio una tabella, un'entità o una query), viene eseguito come query SQL con join.</span><span class="sxs-lookup"><span data-stu-id="02e33-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="02e33-119">Altrimenti, viene eseguita in memoria come funzione [ALLITEMS](er-functions-list-allitems.md).</span><span class="sxs-lookup"><span data-stu-id="02e33-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="02e33-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="02e33-120">Example</span></span>

<span data-ttu-id="02e33-121">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="02e33-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="02e33-122">Un'origine dati **CustInv** del tipo *Table records* che fa riferimento alla tabella CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="02e33-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="02e33-123">Un'origine dati **FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="02e33-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="02e33-124">**FilteredInv** del tipo *Campo calcolato* che contiene l'espressione `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="02e33-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="02e33-125">Quando si esegue il mapping di modello per chiamare l'origine dati **JourLines**, viene eseguita la seguente istruzione SQL:</span><span class="sxs-lookup"><span data-stu-id="02e33-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="02e33-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="02e33-126">Additional resources</span></span>

[<span data-ttu-id="02e33-127">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="02e33-127">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]