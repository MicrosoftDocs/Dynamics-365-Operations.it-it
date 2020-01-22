---
title: Funzione ER AND
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione AND della creazione di report elettronici (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd9c0ed0238009f70ad7a9bf5a5e19ebfb95cccc
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917168"
---
# <span data-ttu-id="23e61-103"><a name="AND">Funzione ER AND</a></span><span class="sxs-lookup"><span data-stu-id="23e61-103"><a name="AND">AND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23e61-104">La funzione `AND` restituisce un valore *Booleano* **TRUE** se tutte le condizioni specificate sono vere.</span><span class="sxs-lookup"><span data-stu-id="23e61-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="23e61-105">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="23e61-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="23e61-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23e61-106">Syntax</span></span>

```
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="23e61-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="23e61-107">Arguments</span></span>

<span data-ttu-id="23e61-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="23e61-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="23e61-109">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="23e61-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="23e61-110">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="23e61-110">This argument is required.</span></span>

<span data-ttu-id="23e61-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="23e61-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="23e61-112">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="23e61-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="23e61-113">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="23e61-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="23e61-114">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="23e61-114">Return values</span></span>

<span data-ttu-id="23e61-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="23e61-115">*Boolean*</span></span>

<span data-ttu-id="23e61-116">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="23e61-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="23e61-117">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="23e61-117">Usage notes</span></span>

<span data-ttu-id="23e61-118">Negli argomenti delle funzioni logiche, è possibile utilizzare riferimenti a origini dati, valori numerici e di testo, valori booleani, operatori di confronto e altre funzioni della creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="23e61-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="23e61-119">Tuttavia, tutti gli argomenti devono essere valutati in base a un valore *Booleano* **TRUE** o **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="23e61-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="23e61-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="23e61-120">Example</span></span>

<span data-ttu-id="23e61-121">`AND (1=1, "a"="a")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="23e61-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="23e61-122">`AND (1=2, "a"="a")` restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="23e61-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23e61-123">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="23e61-123">Additional resources</span></span>

[<span data-ttu-id="23e61-124">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="23e61-124">Logical functions</span></span>](er-functions-category-logical.md)
