---
title: Funzione ER ROUND
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUND della creazione di report elettronici (ER).
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
ms.openlocfilehash: c9384d5975e4a25d18ff741f87431daa4b0bbd7e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917076"
---
# <span data-ttu-id="31952-103"><a name="ROUND">Funzione ER ROUND</a></span><span class="sxs-lookup"><span data-stu-id="31952-103"><a name="ROUND">ROUND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31952-104">La funzione `ROUND` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="31952-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="31952-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31952-105">Syntax</span></span>

```
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="31952-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="31952-106">Arguments</span></span>

<span data-ttu-id="31952-107">`number`: *Reale*</span><span class="sxs-lookup"><span data-stu-id="31952-107">`number`: *Real*</span></span>

<span data-ttu-id="31952-108">Un valore numerico che deve essere arrotondato.</span><span class="sxs-lookup"><span data-stu-id="31952-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="31952-109">`decimals`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="31952-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="31952-110">Un valore numerico che rappresenta il numero di posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="31952-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="31952-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="31952-111">Return values</span></span>

<span data-ttu-id="31952-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="31952-112">*Real*</span></span>

<span data-ttu-id="31952-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="31952-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="31952-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="31952-114">Usage notes</span></span>

<span data-ttu-id="31952-115">Se il valore dell'argomento `decimals` è maggiore di 0 (zero), il numero specificato viene arrotondato al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="31952-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="31952-116">Se il valore dell'argomento `decimals` è **0** (zero), il numero specificato viene arrotondato all'intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="31952-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="31952-117">Se il valore dell'argomento `decimals` è minore di 0 (zero), il numero specificato viene arrotondato a sinistra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="31952-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="31952-118">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="31952-118">Example 1</span></span>

<span data-ttu-id="31952-119">`ROUND (1200.767, 2)` arrotonda a due posti decimali e restituisce **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="31952-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="31952-120">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="31952-120">Example 2</span></span>

<span data-ttu-id="31952-121">`ROUND (1200.767, -3)` arrotonda al più vicino multiplo di 1000 e restituisce **1000**.</span><span class="sxs-lookup"><span data-stu-id="31952-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31952-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="31952-122">Additional resources</span></span>

[<span data-ttu-id="31952-123">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="31952-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
