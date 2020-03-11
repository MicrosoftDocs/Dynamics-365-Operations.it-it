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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042654"
---
# <span data-ttu-id="30eb4-103"><a name="INTVALUE">Funzione ER INTVALUE</a></span><span class="sxs-lookup"><span data-stu-id="30eb4-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30eb4-104">La funzione `INTVALUE` restituisce un valore *Int* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="30eb4-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="30eb4-105">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="30eb4-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="30eb4-106">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="30eb4-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="30eb4-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="30eb4-107">Arguments</span></span>

<span data-ttu-id="30eb4-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="30eb4-108">`text`: *String*</span></span>

<span data-ttu-id="30eb4-109">Un valore di testo che deve essere convertito in un numero *Int*.</span><span class="sxs-lookup"><span data-stu-id="30eb4-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="30eb4-110">`number`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="30eb4-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="30eb4-111">Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int*.</span><span class="sxs-lookup"><span data-stu-id="30eb4-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="30eb4-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="30eb4-112">Return values</span></span>

<span data-ttu-id="30eb4-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="30eb4-113">*Int*</span></span>

<span data-ttu-id="30eb4-114">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="30eb4-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="30eb4-115">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="30eb4-115">Usage notes</span></span>

<span data-ttu-id="30eb4-116">Tutte le posizioni decimali sono troncate.</span><span class="sxs-lookup"><span data-stu-id="30eb4-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="30eb4-117">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="30eb4-117">Example 1</span></span>

<span data-ttu-id="30eb4-118">`INTVALUE ("100.77")` restituisce il valore *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="30eb4-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="30eb4-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="30eb4-119">Example 2</span></span>

<span data-ttu-id="30eb4-120">`INTVALUE (-100.77)` restituisce il valore *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="30eb4-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30eb4-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="30eb4-121">Additional resources</span></span>

[<span data-ttu-id="30eb4-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="30eb4-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
