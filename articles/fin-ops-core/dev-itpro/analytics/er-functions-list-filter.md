---
title: Funzione ER FILTER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FILTER della creazione di report elettronici (ER).
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
ms.openlocfilehash: 0e90db1836a93dab42be5dc91e9ea478163a1437
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559701"
---
# <a name="filter-er-function"></a><span data-ttu-id="fc9ed-103">Funzione ER FILTER</span><span class="sxs-lookup"><span data-stu-id="fc9ed-103">FILTER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fc9ed-104">La funzione `FILTER` restituisce l'elenco specificato come un valore *Elenco di record* dopo che la query è stata modificata in modo da filtrare per la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-104">The `FILTER` function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc9ed-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc9ed-105">Syntax</span></span>

```vb
FILTER (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="fc9ed-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fc9ed-106">Arguments</span></span>

<span data-ttu-id="fc9ed-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fc9ed-107">`list`: *Record list*</span></span>

<span data-ttu-id="fc9ed-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="fc9ed-109">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="fc9ed-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="fc9ed-110">Un'espressione condizionale valida utilizzata per filtrare i record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="fc9ed-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="fc9ed-111">Return values</span></span>

<span data-ttu-id="fc9ed-112">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fc9ed-112">*Record list*</span></span>

<span data-ttu-id="fc9ed-113">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fc9ed-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="fc9ed-114">Usage notes</span></span>

<span data-ttu-id="fc9ed-115">Diversamente dalla funzione [WHERE](er-functions-list-where.md), la condizione specificata viene applicata a livello di database a qualsiasi origine dati della creazione di report elettronici (ER) del tipo di *Table records*.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-115">This function differs from the [WHERE](er-functions-list-where.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Table records* type at the database level.</span></span> <span data-ttu-id="fc9ed-116">L'elenco e la condizione possono essere definite mediante le tabelle e le relazioni.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-116">The list and condition can be defined by using tables and relations.</span></span>

<span data-ttu-id="fc9ed-117">Se uno o entrambi gli argomenti configurati per questa funzione (`list` e `condition`) non consentono di convertire questa richiesta nella chiamata SQL diretta, al momento della progettazione viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-117">If one or both arguments that are configured for this function (`list` and `condition`) don't allow this request to be translated to the direct SQL call, an exception is thrown at design time.</span></span> <span data-ttu-id="fc9ed-118">Questa eccezione informa l'utente che `list` o `condition` non può essere usato per eseguire query sul database.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-118">This exception informs the user that either `list` or `condition` can't be used to query the database.</span></span>

## <a name="example-1"></a><span data-ttu-id="fc9ed-119">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="fc9ed-119">Example 1</span></span>

<span data-ttu-id="fc9ed-120">Se viene configurato **Vendor** come origine dati ER che fa riferimento alla tabella VendTable, l'espressione `FILTER (Vendors, Vendors.VendGroup = "40")` restituisce un elenco solo dei fornitori che appartengono al gruppo 40.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-120">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `FILTER (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="fc9ed-121">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="fc9ed-121">Example 2</span></span>

<span data-ttu-id="fc9ed-122">Se **Vendor** viene configurato come origine dati ER che fa riferimento alla tabella VendTable e se **parmVendorBankGroup** viene configurato come origine dati ER che restituisce un valore del tipo di dati *Stringa*, l'espressione `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` restituisce un elenco costituito solo dai conti fornitore che appartengono a un gruppo bancario specifico.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-122">If **Vendor** is configured as an ER data source that refers to the VendTable table, and if **parmVendorBankGroup** is configured as an ER data source that returns a value of the *String* data type, the expression `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returns a list of only vendor accounts that belong to a specific bank group.</span></span>

## <a name="example-3"></a><span data-ttu-id="fc9ed-123">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="fc9ed-123">Example 3</span></span>

<span data-ttu-id="fc9ed-124">Si immette un'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("A,B,C", ",")`.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-124">You enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A,B,C", ",")`.</span></span> <span data-ttu-id="fc9ed-125">Quindi si inserisce un'altra espressione, `FILTER( DS, DS.Value = "B")`.</span><span class="sxs-lookup"><span data-stu-id="fc9ed-125">You then enter another expression, `FILTER( DS, DS.Value = "B")`.</span></span> <span data-ttu-id="fc9ed-126">Quando si tenta di salvare questa espressione nel designer della formula ER, viene generata la seguente eccezione: "Errore di convalida: non è possibile eseguire query sull'espressione di elenco della funzione FILTER".</span><span class="sxs-lookup"><span data-stu-id="fc9ed-126">When you try to save this expression in the ER formula designer, the following exception is thrown: "Validation error: The list expression of FILTER function is not queryable."</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc9ed-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fc9ed-127">Additional resources</span></span>

[<span data-ttu-id="fc9ed-128">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="fc9ed-128">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]