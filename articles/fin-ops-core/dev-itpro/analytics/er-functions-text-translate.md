---
title: Funzione ER TRANSLATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TRANSLATE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: c5d192b8679d6df2c44a0038fe4ffc181a6a54df
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685305"
---
# <a name="translate-er-function"></a><span data-ttu-id="52824-103">Funzione ER TRANSLATE</span><span class="sxs-lookup"><span data-stu-id="52824-103">TRANSLATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52824-104">La funzione `TRANSLATE` restituisce un valore *Stringa* che contiene il risultato della sostituzione del carattere del testo specificato in caratteri di un altro set fornito.</span><span class="sxs-lookup"><span data-stu-id="52824-104">The `TRANSLATE` function returns a *String* value that contains the result of the character replacement of specified text in characters of another provided set.</span></span>

## <a name="syntax"></a><span data-ttu-id="52824-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52824-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="52824-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="52824-106">Arguments</span></span>

<span data-ttu-id="52824-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="52824-107">`text`: *String*</span></span>

<span data-ttu-id="52824-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="52824-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="52824-109">`pattern`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="52824-109">`pattern`: *String*</span></span>

<span data-ttu-id="52824-110">Il testo che deve essere sostituito.</span><span class="sxs-lookup"><span data-stu-id="52824-110">The text that must be replaced.</span></span>

<span data-ttu-id="52824-111">`replacement`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="52824-111">`replacement`: *String*</span></span>

<span data-ttu-id="52824-112">Il testo da utilizzare in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="52824-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="52824-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="52824-113">Return values</span></span>

<span data-ttu-id="52824-114">*String*</span><span class="sxs-lookup"><span data-stu-id="52824-114">*String*</span></span>

<span data-ttu-id="52824-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="52824-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="52824-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="52824-116">Usage notes</span></span>

<span data-ttu-id="52824-117">La funzione `TRANSLATE` sostituisce un carattere alla volta.</span><span class="sxs-lookup"><span data-stu-id="52824-117">The `TRANSLATE` function replaces one character at a time.</span></span> <span data-ttu-id="52824-118">La funzione sostituisce il primo carattere dell'argomento `text` con il primo carattere dell'argomento `pattern`, quindi il secondo carattere e lo stesso flusso viene seguito fino al termine.</span><span class="sxs-lookup"><span data-stu-id="52824-118">The function replaces the first character of the `text` argument with the first character of the `pattern` argument and then the second character and follows the same flow until finished.</span></span> <span data-ttu-id="52824-119">Quando un carattere dagli argomenti `text` e `pattern` corrisponde, viene sostituito da un carattere dell'argomento `replacement` che si trova nella stessa posizione del carattere dell'argomento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="52824-119">When a character from the `text` and `pattern` arguments match, it is replaced by a character from the `replacement` argument that is located in the same position as the character from the `pattern` argument.</span></span> <span data-ttu-id="52824-120">Se un carattere appare più volte nell'argomento `pattern`, viene utilizzata la mappatura dell'argomento `replacement` che corrisponde alla prima occorrenza di questo carattere.</span><span class="sxs-lookup"><span data-stu-id="52824-120">If a character appears multiple times in the `pattern` argument, the `replacement` argument mapping that corresponds to the first occurrence of this character is used.</span></span>

## <a name="example-1"></a><span data-ttu-id="52824-121">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="52824-121">Example 1</span></span>

<span data-ttu-id="52824-122">`TRANSLATE ("abcdef", "cd", "GH")` sostituisce il carattere **"c"** del testo **"abcdef"** specificato con il carattere **"G"** del testo `replacement` dovuto a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="52824-122">`TRANSLATE ("abcdef", "cd", "GH")` replaces the **"c"** character of the specified  **“abcdef”** text with the **"G"** character of the `replacement` text due to the following:</span></span>
-   <span data-ttu-id="52824-123">Il carattere **"C"** è presentato nel testo `pattern` in prima posizione.</span><span class="sxs-lookup"><span data-stu-id="52824-123">The **"c"** character is presented in the `pattern` text in the first position.</span></span>
-   <span data-ttu-id="52824-124">La prima posizione del testo `replacement` contiene il carattere **"G"**.</span><span class="sxs-lookup"><span data-stu-id="52824-124">The first position of the `replacement` text contains the **"G"** character.</span></span>

## <a name="example-2"></a><span data-ttu-id="52824-125">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="52824-125">Example 2</span></span>

<span data-ttu-id="52824-126">`TRANSLATE ("abcdef", "ccd", "GH")` restituisce **"abGdef"**.</span><span class="sxs-lookup"><span data-stu-id="52824-126">`TRANSLATE ("abcdef", "ccd", "GH")` returns **"abGdef"**.</span></span>

## <a name="example-3"></a><span data-ttu-id="52824-127">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="52824-127">Example 3</span></span>

<span data-ttu-id="52824-128">`TRANSLATE ("abccba", "abc", "123")` restituisce **"123321"**.</span><span class="sxs-lookup"><span data-stu-id="52824-128">`TRANSLATE ("abccba", "abc", "123")` returns **"123321"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52824-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="52824-129">Additional resources</span></span>

[<span data-ttu-id="52824-130">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="52824-130">Text functions</span></span>](er-functions-category-text.md)
