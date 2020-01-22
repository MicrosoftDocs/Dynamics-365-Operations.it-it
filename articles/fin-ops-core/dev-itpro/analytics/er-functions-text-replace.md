---
title: Funzione ER REPLACE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione REPLACE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: d9c66f4c96f35e3ad5fc92e7925b5cd07c956aac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916869"
---
# <span data-ttu-id="d18f1-103"><a name="REPLACE">Funzione ER REPLACE</a></span><span class="sxs-lookup"><span data-stu-id="d18f1-103"><a name="REPLACE">REPLACE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d18f1-104">La funzione `REPLACE` restituisce la stringa di testo specificata come un valore *Stringa* dopo che tutta o parte di essa è stata sostituita con un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="d18f1-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="d18f1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d18f1-105">Syntax</span></span>

```
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="d18f1-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d18f1-106">Arguments</span></span>

<span data-ttu-id="d18f1-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d18f1-107">`text`: *String*</span></span>

<span data-ttu-id="d18f1-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="d18f1-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="d18f1-109">`pattern`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d18f1-109">`pattern`: *String*</span></span>

<span data-ttu-id="d18f1-110">Se l'argomento `regular expression flag` è **FALSE**, questo argomento contiene il testo che deve essere sostituito.</span><span class="sxs-lookup"><span data-stu-id="d18f1-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="d18f1-111">Se l'argomento `regular expression flag` è **TRUE**, questo argomento contiene un'espressione regolare che definisce sia un modello di ricerca che il testo sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="d18f1-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="d18f1-112">`replacement`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d18f1-112">`replacement`: *String*</span></span>

<span data-ttu-id="d18f1-113">Se l'argomento `regular expression flag` è **FALSE**, questo argomento contiene il testo che deve essere usato per la sostituzione.</span><span class="sxs-lookup"><span data-stu-id="d18f1-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="d18f1-114">Se l'argomento `regular expression flag` è **TRUE**, questo argomento non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d18f1-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="d18f1-115">`regular expression flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="d18f1-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="d18f1-116">Un valore *Booleano* che indica se per la sostituzione viene utilizzata un'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="d18f1-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="d18f1-117">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d18f1-117">Return values</span></span>

<span data-ttu-id="d18f1-118">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="d18f1-118">*String*</span></span>

<span data-ttu-id="d18f1-119">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="d18f1-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d18f1-120">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d18f1-120">Usage notes</span></span>

<span data-ttu-id="d18f1-121">Se l'argomento `regular expression flag` è **TRUE**, questa funzione restituisce la stringa specificata dopo che è stata modificata applicando l'espressione regolare specificata dall'argomento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="d18f1-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="d18f1-122">L'espressione regolare viene utilizzata per individuare i caratteri che devono essere sostituiti.</span><span class="sxs-lookup"><span data-stu-id="d18f1-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="d18f1-123">Se l'argomento `regular expression flag` è **FALSE**, questa funzione si comporta come [TRANSLATE](er-functions-text-translate.md).</span><span class="sxs-lookup"><span data-stu-id="d18f1-123">If the `regular expression flag` argument is **FALSE**, this function behaves like [TRANSLATE](er-functions-text-translate.md).</span></span> <span data-ttu-id="d18f1-124">I caratteri specificati dall'argomento `replacement` vengono utilizzati per sostituire i caratteri trovati.</span><span class="sxs-lookup"><span data-stu-id="d18f1-124">The characters that are specified by the `replacement` argument are used to replace the characters that are found.</span></span> 

## <a name="example-1"></a><span data-ttu-id="d18f1-125">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="d18f1-125">Example 1</span></span>

<span data-ttu-id="d18f1-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applica un'espressione regolare che rimuove tutti i simboli non numerici e restituisce **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="d18f1-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="d18f1-127">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="d18f1-127">Example 2</span></span>

<span data-ttu-id="d18f1-128">`REPLACE ("abcdef", "cd", "GH", false)` sostituisce il modello **"cd"** con la stringa **"GH"** e restituisce **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="d18f1-128">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d18f1-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d18f1-129">Additional resources</span></span>

[<span data-ttu-id="d18f1-130">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="d18f1-130">Text functions</span></span>](er-functions-category-text.md)
