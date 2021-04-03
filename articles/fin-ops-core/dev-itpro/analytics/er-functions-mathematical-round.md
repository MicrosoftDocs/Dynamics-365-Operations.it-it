---
title: Funzione ER ROUND
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUND della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 10/21/2020
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
ms.openlocfilehash: 716ac0bbc9fec992ec1bbfc99bfc86434bf97984
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570400"
---
# <a name="round-er-function"></a><span data-ttu-id="332a3-103">Funzione ER ROUND</span><span class="sxs-lookup"><span data-stu-id="332a3-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="332a3-104">La funzione `ROUND` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="332a3-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="332a3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="332a3-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="332a3-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="332a3-106">Arguments</span></span>

<span data-ttu-id="332a3-107">`number`: *Reale*</span><span class="sxs-lookup"><span data-stu-id="332a3-107">`number`: *Real*</span></span>

<span data-ttu-id="332a3-108">Un valore numerico che deve essere arrotondato.</span><span class="sxs-lookup"><span data-stu-id="332a3-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="332a3-109">`decimals`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="332a3-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="332a3-110">Un valore numerico che rappresenta il numero di posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="332a3-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="332a3-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="332a3-111">Return values</span></span>

<span data-ttu-id="332a3-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="332a3-112">*Real*</span></span>

<span data-ttu-id="332a3-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="332a3-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="332a3-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="332a3-114">Usage notes</span></span>

<span data-ttu-id="332a3-115">Se il valore dell'argomento `decimals` è maggiore di 0 (zero), il numero specificato viene arrotondato al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="332a3-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="332a3-116">Se il valore dell'argomento `decimals` è **0** (zero), il numero specificato viene arrotondato all'intero pari più vicino.</span><span class="sxs-lookup"><span data-stu-id="332a3-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="332a3-117">Se il valore dell'argomento `decimals` è minore di 0 (zero), il numero specificato viene arrotondato a sinistra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="332a3-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="332a3-118">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="332a3-118">Example 1</span></span>

<span data-ttu-id="332a3-119">`ROUND (1200.767, 2)` arrotonda a due posti decimali e restituisce **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="332a3-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="332a3-120">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="332a3-120">Example 2</span></span>

<span data-ttu-id="332a3-121">`ROUND (1200.767, -3)` arrotonda al più vicino multiplo di 1000 e restituisce **1000**.</span><span class="sxs-lookup"><span data-stu-id="332a3-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="332a3-122">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="332a3-122">Example 3</span></span>

<span data-ttu-id="332a3-123">`ROUND (1200.5, 0)` arrotonda al numero intero pari più vicino e restituisce **1200**, mentre `ROUND (1201.5, 0)` fa lo stesso e restituisce **1202**.</span><span class="sxs-lookup"><span data-stu-id="332a3-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="332a3-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="332a3-124">Additional resources</span></span>

[<span data-ttu-id="332a3-125">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="332a3-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]