---
title: Funzione ER OR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione OR della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: faf07c5d8b30cd3babe8a6a55ae7effe5ce457a0
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744625"
---
# <a name="or-er-function"></a><span data-ttu-id="039f3-103">Funzione ER OR</span><span class="sxs-lookup"><span data-stu-id="039f3-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="039f3-104">La funzione `OR` restituisce un valore *Booleano* **FALSE** se tutte le condizioni specificate sono false.</span><span class="sxs-lookup"><span data-stu-id="039f3-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="039f3-105">Se una condizione specificata è vera, la funzione restituisce un valore *Booleano* **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="039f3-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="039f3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="039f3-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="039f3-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="039f3-107">Arguments</span></span>

<span data-ttu-id="039f3-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="039f3-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="039f3-109">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="039f3-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="039f3-110">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="039f3-110">This argument is required.</span></span>

<span data-ttu-id="039f3-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="039f3-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="039f3-112">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="039f3-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="039f3-113">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="039f3-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="039f3-114">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="039f3-114">Return values</span></span>

<span data-ttu-id="039f3-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="039f3-115">*Boolean*</span></span>

<span data-ttu-id="039f3-116">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="039f3-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="039f3-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="039f3-117">Example</span></span>

<span data-ttu-id="039f3-118">`OR (1=2, "a"="a")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="039f3-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="039f3-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="039f3-119">Additional resources</span></span>

[<span data-ttu-id="039f3-120">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="039f3-120">Logical functions</span></span>](er-functions-category-logical.md)
