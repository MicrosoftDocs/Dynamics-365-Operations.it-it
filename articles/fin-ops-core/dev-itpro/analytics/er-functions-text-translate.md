---
title: Funzione ER TRANSLATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TRANSLATE della creazione di report elettronici (ER).
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
ms.openlocfilehash: 07fe19c5f66c33e336f76f3a72d3bbda0c7e8d86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040919"
---
# <span data-ttu-id="088d2-103"><a name="TRANSLATE">Funzione ER TRANSLATE</a></span><span class="sxs-lookup"><span data-stu-id="088d2-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="088d2-104">La funzione `TRANSLATE` restituisce la stringa di testo specificata come un valore *Stringa* dopo che tutta o parte di essa è stata sostituita con un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="088d2-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="088d2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="088d2-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="088d2-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="088d2-106">Arguments</span></span>

<span data-ttu-id="088d2-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="088d2-107">`text`: *String*</span></span>

<span data-ttu-id="088d2-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="088d2-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="088d2-109">`pattern`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="088d2-109">`pattern`: *String*</span></span>

<span data-ttu-id="088d2-110">Il testo che deve essere sostituito.</span><span class="sxs-lookup"><span data-stu-id="088d2-110">The text that must be replaced.</span></span>

<span data-ttu-id="088d2-111">`replacement`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="088d2-111">`replacement`: *String*</span></span>

<span data-ttu-id="088d2-112">Il testo da utilizzare in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="088d2-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="088d2-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="088d2-113">Return values</span></span>

<span data-ttu-id="088d2-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="088d2-114">*String*</span></span>

<span data-ttu-id="088d2-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="088d2-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="088d2-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="088d2-116">Example</span></span>

<span data-ttu-id="088d2-117">`TRANSLATE ("abcdef", "cd", "GH")` sostituisce il modello **"cd"** con la stringa **"GH"** e restituisce **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="088d2-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="088d2-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="088d2-118">Additional resources</span></span>

[<span data-ttu-id="088d2-119">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="088d2-119">Text functions</span></span>](er-functions-category-text.md)
