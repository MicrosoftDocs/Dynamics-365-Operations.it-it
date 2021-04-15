---
title: Funzione ER REPLACE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione REPLACE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 21cdd8532730925b7d5c6f5b3bb565dcd365dd6d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746201"
---
# <a name="replace-er-function"></a><span data-ttu-id="3321d-103">Funzione ER REPLACE</span><span class="sxs-lookup"><span data-stu-id="3321d-103">REPLACE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3321d-104">La funzione `REPLACE` restituisce la stringa di testo specificata come un valore *Stringa* dopo che tutta o parte di essa è stata sostituita con un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="3321d-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="3321d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3321d-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="3321d-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3321d-106">Arguments</span></span>

<span data-ttu-id="3321d-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="3321d-107">`text`: *String*</span></span>

<span data-ttu-id="3321d-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="3321d-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="3321d-109">`pattern`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="3321d-109">`pattern`: *String*</span></span>

<span data-ttu-id="3321d-110">Se l'argomento `regular expression flag` è **FALSE**, questo argomento contiene il testo che deve essere sostituito.</span><span class="sxs-lookup"><span data-stu-id="3321d-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="3321d-111">Se l'argomento `regular expression flag` è **TRUE**, questo argomento contiene un'espressione regolare che definisce sia un modello di ricerca che il testo sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="3321d-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="3321d-112">`replacement`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="3321d-112">`replacement`: *String*</span></span>

<span data-ttu-id="3321d-113">Se l'argomento `regular expression flag` è **FALSE**, questo argomento contiene il testo che deve essere usato per la sostituzione.</span><span class="sxs-lookup"><span data-stu-id="3321d-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="3321d-114">Se l'argomento `regular expression flag` è **TRUE**, questo argomento non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3321d-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="3321d-115">`regular expression flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="3321d-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="3321d-116">Un valore *Booleano* che indica se per la sostituzione viene utilizzata un'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="3321d-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="3321d-117">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3321d-117">Return values</span></span>

<span data-ttu-id="3321d-118">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="3321d-118">*String*</span></span>

<span data-ttu-id="3321d-119">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="3321d-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3321d-120">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="3321d-120">Usage notes</span></span>

<span data-ttu-id="3321d-121">Se l'argomento `regular expression flag` è **TRUE**, questa funzione restituisce la stringa specificata dopo che è stata modificata applicando l'espressione regolare specificata dall'argomento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="3321d-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="3321d-122">L'espressione regolare viene utilizzata per individuare i caratteri che devono essere sostituiti.</span><span class="sxs-lookup"><span data-stu-id="3321d-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="3321d-123">Se l'argomento `regular expression flag` è **FALSO**, questa funzione restituisce la stringa specificata dopo che il set di caratteri definito nell'argomento `pattern` è stato sostituito dai caratteri dell'argomento `replacement`.</span><span class="sxs-lookup"><span data-stu-id="3321d-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="3321d-124">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="3321d-124">Example 1</span></span>

<span data-ttu-id="3321d-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applica un'espressione regolare che rimuove tutti i simboli non numerici e restituisce **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="3321d-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="3321d-126">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="3321d-126">Example 2</span></span>

<span data-ttu-id="3321d-127">`REPLACE ("abcdef", "cd", "GH", false)` sostituisce il modello **"cd"** con la stringa **"GH"** e restituisce **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="3321d-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3321d-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3321d-128">Additional resources</span></span>

[<span data-ttu-id="3321d-129">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="3321d-129">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]