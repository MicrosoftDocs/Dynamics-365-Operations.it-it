---
title: Funzione ER ROUNDUP
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUNDUP della creazione di report elettronici (ER).
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
ms.openlocfilehash: 83262a11f92a924e5e49461cf414fb07ab278541
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744505"
---
# <a name="roundup-er-function"></a><span data-ttu-id="b958b-103">Funzione ER ROUNDUP</span><span class="sxs-lookup"><span data-stu-id="b958b-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b958b-104">La funzione `ROUNDUP` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato per eccesso al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="b958b-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="b958b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b958b-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="b958b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b958b-106">Arguments</span></span>

<span data-ttu-id="b958b-107">`number`: *Reale*</span><span class="sxs-lookup"><span data-stu-id="b958b-107">`number`: *Real*</span></span>

<span data-ttu-id="b958b-108">Un valore numerico che deve essere arrotondato per eccesso.</span><span class="sxs-lookup"><span data-stu-id="b958b-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="b958b-109">`decimals`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="b958b-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="b958b-110">Un valore numerico che rappresenta il numero di posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="b958b-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="b958b-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b958b-111">Return values</span></span>

<span data-ttu-id="b958b-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="b958b-112">*Real*</span></span>

<span data-ttu-id="b958b-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="b958b-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b958b-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="b958b-114">Usage notes</span></span>

<span data-ttu-id="b958b-115">Questa funzione si comporta analogamente a [ROUND](er-functions-mathematical-round.md) ma sempre per eccesso (lontano da zero).</span><span class="sxs-lookup"><span data-stu-id="b958b-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="b958b-116">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b958b-116">Example 1</span></span>

<span data-ttu-id="b958b-117">`ROUNDUP (1200.763, 2)` arrotonda per eccesso a due posti decimali e restituisce **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="b958b-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b958b-118">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="b958b-118">Example 2</span></span>

<span data-ttu-id="b958b-119">`ROUNDUP (1200.767, -3)` arrotonda per eccesso al più vicino multiplo di 1000 e restituisce **2000**.</span><span class="sxs-lookup"><span data-stu-id="b958b-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b958b-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b958b-120">Additional resources</span></span>

[<span data-ttu-id="b958b-121">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="b958b-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
