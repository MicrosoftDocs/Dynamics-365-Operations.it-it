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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 107241dbf9a5127d61343fc1cf42c3bab577adb3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686980"
---
# <a name="or-er-function"></a><span data-ttu-id="73362-103">Funzione ER OR</span><span class="sxs-lookup"><span data-stu-id="73362-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73362-104">La funzione `OR` restituisce un valore *Booleano* **FALSE** se tutte le condizioni specificate sono false.</span><span class="sxs-lookup"><span data-stu-id="73362-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="73362-105">Se una condizione specificata è vera, la funzione restituisce un valore *Booleano* **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="73362-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="73362-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73362-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="73362-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="73362-107">Arguments</span></span>

<span data-ttu-id="73362-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="73362-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="73362-109">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="73362-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="73362-110">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="73362-110">This argument is required.</span></span>

<span data-ttu-id="73362-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="73362-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="73362-112">Un'espressione condizionale valida che deve essere testata.</span><span class="sxs-lookup"><span data-stu-id="73362-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="73362-113">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="73362-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="73362-114">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="73362-114">Return values</span></span>

<span data-ttu-id="73362-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="73362-115">*Boolean*</span></span>

<span data-ttu-id="73362-116">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="73362-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="73362-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="73362-117">Example</span></span>

<span data-ttu-id="73362-118">`OR (1=2, "a"="a")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="73362-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73362-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="73362-119">Additional resources</span></span>

[<span data-ttu-id="73362-120">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="73362-120">Logical functions</span></span>](er-functions-category-logical.md)
