---
title: Funzione ER ROUNDDOWN
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUNDDOWN della creazione di report elettronici (ER).
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
ms.openlocfilehash: 9221476c1c12a7cc3fe2367cdee3ad44e5cbe381
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686884"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="482bb-103">Funzione ER ROUNDDOWN</span><span class="sxs-lookup"><span data-stu-id="482bb-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="482bb-104">La funzione `ROUNDDOWN` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato per difetto al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="482bb-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="482bb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="482bb-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="482bb-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="482bb-106">Arguments</span></span>

<span data-ttu-id="482bb-107">`number`: *Reale*</span><span class="sxs-lookup"><span data-stu-id="482bb-107">`number`: *Real*</span></span>

<span data-ttu-id="482bb-108">Un valore numerico che deve essere arrotondato per difetto.</span><span class="sxs-lookup"><span data-stu-id="482bb-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="482bb-109">`decimals`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="482bb-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="482bb-110">Un valore numerico che rappresenta il numero di posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="482bb-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="482bb-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="482bb-111">Return values</span></span>

<span data-ttu-id="482bb-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="482bb-112">*Real*</span></span>

<span data-ttu-id="482bb-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="482bb-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="482bb-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="482bb-114">Usage notes</span></span>

<span data-ttu-id="482bb-115">Questa funzione si comporta analogamente a [ROUND](er-functions-mathematical-round.md) ma sempre per difetto (verso lo zero).</span><span class="sxs-lookup"><span data-stu-id="482bb-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="482bb-116">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="482bb-116">Example 1</span></span>

<span data-ttu-id="482bb-117">`ROUNDDOWN (1200.767, 2)` arrotonda per difetto a due posti decimali e restituisce **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="482bb-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="482bb-118">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="482bb-118">Example 2</span></span>

<span data-ttu-id="482bb-119">`ROUNDDOWN (1700.767, -3)` arrotonda per difetto al più vicino multiplo di 1000 e restituisce **1000**.</span><span class="sxs-lookup"><span data-stu-id="482bb-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="482bb-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="482bb-120">Additional resources</span></span>

[<span data-ttu-id="482bb-121">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="482bb-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
