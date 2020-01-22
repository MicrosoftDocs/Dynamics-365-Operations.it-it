---
title: Funzione ER INTVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INTVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2b279de39cf91c3919145735518034fc60cd3341
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917720"
---
# <span data-ttu-id="5506e-103"><a name="INTVALUE">Funzione ER INTVALUE</a></span><span class="sxs-lookup"><span data-stu-id="5506e-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5506e-104">La funzione `INTVALUE` restituisce un valore *Int* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="5506e-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="5506e-105">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="5506e-105">Syntax 1</span></span>

```
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="5506e-106">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="5506e-106">Syntax 2</span></span>

```
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="5506e-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5506e-107">Arguments</span></span>

<span data-ttu-id="5506e-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="5506e-108">`text`: *String*</span></span>

<span data-ttu-id="5506e-109">Un valore di testo che deve essere convertito in un numero *Int*.</span><span class="sxs-lookup"><span data-stu-id="5506e-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="5506e-110">`number`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="5506e-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="5506e-111">Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int*.</span><span class="sxs-lookup"><span data-stu-id="5506e-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="5506e-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="5506e-112">Return values</span></span>

<span data-ttu-id="5506e-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="5506e-113">*Int*</span></span>

<span data-ttu-id="5506e-114">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="5506e-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5506e-115">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="5506e-115">Usage notes</span></span>

<span data-ttu-id="5506e-116">Tutte le posizioni decimali sono troncate.</span><span class="sxs-lookup"><span data-stu-id="5506e-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="5506e-117">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="5506e-117">Example 1</span></span>

<span data-ttu-id="5506e-118">`INTVALUE ("100.77")` restituisce il valore *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="5506e-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5506e-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="5506e-119">Example 2</span></span>

<span data-ttu-id="5506e-120">`INTVALUE (-100.77)` restituisce il valore *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="5506e-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5506e-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5506e-121">Additional resources</span></span>

[<span data-ttu-id="5506e-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="5506e-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
