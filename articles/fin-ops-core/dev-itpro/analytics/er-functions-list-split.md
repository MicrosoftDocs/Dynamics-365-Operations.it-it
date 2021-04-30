---
title: Funzione ER SPLIT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLIT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 26b6ddeb2880fc220283b6389327a497549a4511
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853445"
---
# <a name="split-er-function"></a><span data-ttu-id="729b5-103">Funzione ER SPLIT</span><span class="sxs-lookup"><span data-stu-id="729b5-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="729b5-104">La funzione `SPLIT` divide la stringa di input specificata in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="729b5-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="729b5-105">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="729b5-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="729b5-106">Questa sintassi viene utilizzata per dividere la stringa di input specificata in sottostringhe, ciascuna delle quali ha la lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="729b5-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="729b5-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="729b5-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="729b5-108">Questa sintassi viene utilizzata per dividere la stringa di input specificata in sottostringhe, in base al delimitatore specificato.</span><span class="sxs-lookup"><span data-stu-id="729b5-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="729b5-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="729b5-109">Arguments</span></span>

<span data-ttu-id="729b5-110">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="729b5-110">`input`: *String*</span></span>

<span data-ttu-id="729b5-111">Testo da dividere.</span><span class="sxs-lookup"><span data-stu-id="729b5-111">The text to split.</span></span>

<span data-ttu-id="729b5-112">`length`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="729b5-112">`length`: *Integer*</span></span>

<span data-ttu-id="729b5-113">La lunghezza massima di una singola sottostringa.</span><span class="sxs-lookup"><span data-stu-id="729b5-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="729b5-114">`delimiter`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="729b5-114">`delimiter`: *String*</span></span>

<span data-ttu-id="729b5-115">Un delimitatore utilizzato per separare le sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="729b5-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="729b5-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="729b5-116">Return values</span></span>

<span data-ttu-id="729b5-117">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="729b5-117">*Record list*</span></span>

<span data-ttu-id="729b5-118">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="729b5-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="729b5-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="729b5-119">Usage notes</span></span>

<span data-ttu-id="729b5-120">La struttura dei record dell'elenco restituito è costituita dal campo **Valore** del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="729b5-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="729b5-121">Ogni record dell'elenco che viene restituito contiene sottostringhe generate in questo campo.</span><span class="sxs-lookup"><span data-stu-id="729b5-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="729b5-122">Se l'argomento `delimiter` è vuoto, il nuovo elenco restituito è costituito da un record che ha il campo **Valore** del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="729b5-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="729b5-123">Questo campo contiene il testo di input.</span><span class="sxs-lookup"><span data-stu-id="729b5-123">This field contains the input text.</span></span>

<span data-ttu-id="729b5-124">Se l'argomento `input` è vuoto, viene restituito un nuovo elenco vuoto.</span><span class="sxs-lookup"><span data-stu-id="729b5-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="729b5-125">Se l'argomento `input` o `delimiter` non è specificato (null), viene generata un'eccezione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="729b5-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="729b5-126">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="729b5-126">Example 1</span></span>

<span data-ttu-id="729b5-127">`SPLIT ("abcd", 3)` restituisce un nuovo elenco costituito da due record che hanno il campo **Valore** di tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="729b5-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="729b5-128">Il campo **Valore** del primo record contiene il testo **"abc"** e il campo **Valore** nel secondo record contiene il testo **"d"**.</span><span class="sxs-lookup"><span data-stu-id="729b5-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="729b5-129">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="729b5-129">Example 2</span></span>

<span data-ttu-id="729b5-130">`SPLIT ("XAb aBy", "aB")` restituisce un nuovo elenco costituito da tre record che hanno il campo **Valore** di tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="729b5-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="729b5-131">Il campo **Value** del primo record contiene il testo **"X"**, il campo **Valore** nel secondo record contiene il testo **"&nbsp;"** e il campo **Valore** del terzo record contiene il testo **"y"**.</span><span class="sxs-lookup"><span data-stu-id="729b5-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="729b5-132">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="729b5-132">Example 3</span></span>

<span data-ttu-id="729b5-133">È possibile usare la funzione [INDEX](er-functions-list-index.md) per accedere a singoli elementi della stringa di input specificata.</span><span class="sxs-lookup"><span data-stu-id="729b5-133">Yo can use the [INDEX](er-functions-list-index.md) function to access individual elements of the specified input string.</span></span> <span data-ttu-id="729b5-134">Se si immette l'origine dati **MyList** del tipo **Campo calcolato** e si configura per la stessa l'espressione `SPLIT("abc", 1)`, l'espressione `INDEX(MyList,2).Value` restituisce il testo **"b"**.</span><span class="sxs-lookup"><span data-stu-id="729b5-134">If you enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, the expression `INDEX(MyList,2).Value` returns the text **"b"**.</span></span>

## <a name="example-4"></a><span data-ttu-id="729b5-135">Esempio 4</span><span class="sxs-lookup"><span data-stu-id="729b5-135">Example 4</span></span>

<span data-ttu-id="729b5-136">La funzione [ENUMERATE](er-functions-list-enumerate.md) può anche consentire di accedere a singoli elementi della stringa di input specificata.</span><span class="sxs-lookup"><span data-stu-id="729b5-136">The [ENUMERATE](er-functions-list-enumerate.md) function can also help you access individual elements of the specified input string.</span></span> <span data-ttu-id="729b5-137">Se dapprima si inserisce l'origine dati **MyList** del tipo **Campo calcolato** e per la stessa si configura l'espressione `SPLIT("abc", 1)`, quindi si inserisce l'origine dati **EnumeratedList** del tipo **Campo calcolato** e per la stessa si configura l'espressione `ENUMERATE(MyList)`, l'espressione `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` restituisce il testo **"b"**.</span><span class="sxs-lookup"><span data-stu-id="729b5-137">If you first enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, and then enter the **EnumeratedList** data source of the **Calculated field** type and configure for it the `ENUMERATE(MyList)` expression, the expression `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` returns the text **"b"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="729b5-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="729b5-138">Additional resources</span></span>

[<span data-ttu-id="729b5-139">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="729b5-139">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
