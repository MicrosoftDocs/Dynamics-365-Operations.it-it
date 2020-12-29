---
title: Funzione ER SPLIT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLIT della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1f11d68b697fdd363f429e60a79f1e1f97bab5b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686394"
---
# <a name="split-er-function"></a><span data-ttu-id="e954f-103">Funzione ER SPLIT</span><span class="sxs-lookup"><span data-stu-id="e954f-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e954f-104">La funzione `SPLIT` divide la stringa di input specificata in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="e954f-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="e954f-105">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="e954f-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="e954f-106">Questa sintassi viene utilizzata per dividere la stringa di input specificata in sottostringhe, ciascuna delle quali ha la lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="e954f-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="e954f-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="e954f-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="e954f-108">Questa sintassi viene utilizzata per dividere la stringa di input specificata in sottostringhe, in base al delimitatore specificato.</span><span class="sxs-lookup"><span data-stu-id="e954f-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="e954f-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e954f-109">Arguments</span></span>

<span data-ttu-id="e954f-110">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="e954f-110">`input`: *String*</span></span>

<span data-ttu-id="e954f-111">Testo da dividere.</span><span class="sxs-lookup"><span data-stu-id="e954f-111">The text to split.</span></span>

<span data-ttu-id="e954f-112">`length`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="e954f-112">`length`: *Integer*</span></span>

<span data-ttu-id="e954f-113">La lunghezza massima di una singola sottostringa.</span><span class="sxs-lookup"><span data-stu-id="e954f-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="e954f-114">`delimiter`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="e954f-114">`delimiter`: *String*</span></span>

<span data-ttu-id="e954f-115">Un delimitatore utilizzato per separare le sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="e954f-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="e954f-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="e954f-116">Return values</span></span>

<span data-ttu-id="e954f-117">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="e954f-117">*Record list*</span></span>

<span data-ttu-id="e954f-118">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="e954f-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e954f-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="e954f-119">Usage notes</span></span>

<span data-ttu-id="e954f-120">La struttura dei record dell'elenco restituito è costituita dal campo **Valore** del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="e954f-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="e954f-121">Ogni record dell'elenco che viene restituito contiene sottostringhe generate in questo campo.</span><span class="sxs-lookup"><span data-stu-id="e954f-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="e954f-122">Se l'argomento `delimiter` è vuoto, il nuovo elenco restituito è costituito da un record che ha il campo **Valore** del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="e954f-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="e954f-123">Questo campo contiene il testo di input.</span><span class="sxs-lookup"><span data-stu-id="e954f-123">This field contains the input text.</span></span>

<span data-ttu-id="e954f-124">Se l'argomento `input` è vuoto, viene restituito un nuovo elenco vuoto.</span><span class="sxs-lookup"><span data-stu-id="e954f-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="e954f-125">Se l'argomento `input` o `delimiter` non è specificato (null), viene generata un'eccezione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e954f-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="e954f-126">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="e954f-126">Example 1</span></span>

<span data-ttu-id="e954f-127">`SPLIT ("abcd", 3)` restituisce un nuovo elenco costituito da due record che hanno il campo **Valore** di tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="e954f-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="e954f-128">Il campo **Valore** del primo record contiene il testo **"abc"** e il campo **Valore** nel secondo record contiene il testo **"d"**.</span><span class="sxs-lookup"><span data-stu-id="e954f-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e954f-129">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="e954f-129">Example 2</span></span>

<span data-ttu-id="e954f-130">`SPLIT ("XAb aBy", "aB")` restituisce un nuovo elenco costituito da tre record che hanno il campo **Valore** di tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="e954f-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="e954f-131">Il campo **Value** del primo record contiene il testo **"X"**, il campo **Valore** nel secondo record contiene il testo **"&nbsp;"** e il campo **Valore** del terzo record contiene il testo **"y"**.</span><span class="sxs-lookup"><span data-stu-id="e954f-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="e954f-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e954f-132">Additional resources</span></span>

[<span data-ttu-id="e954f-133">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="e954f-133">List functions</span></span>](er-functions-category-list.md)
