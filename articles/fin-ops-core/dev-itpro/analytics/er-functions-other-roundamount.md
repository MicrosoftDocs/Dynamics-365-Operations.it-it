---
title: Funzione ER ROUNDAMOUNT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUNDAMOUNT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 2a80587236d17160a996d701ca4ae38be21c818c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563296"
---
# <a name="roundamount-er-function"></a><span data-ttu-id="5361c-103">Funzione ER ROUNDAMOUNT</span><span class="sxs-lookup"><span data-stu-id="5361c-103">ROUNDAMOUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5361c-104">La funzione `ROUNDAMOUNT` restituisce un valore *Reale* come risultato dell'arrotondamento del numero specificato al multiplo più vicino di un altro numero in base alla regola di arrotondamento specificata.</span><span class="sxs-lookup"><span data-stu-id="5361c-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="5361c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5361c-105">Syntax</span></span>

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="5361c-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5361c-106">Arguments</span></span>

<span data-ttu-id="5361c-107">`number`: *Int* o *Reale*</span><span class="sxs-lookup"><span data-stu-id="5361c-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="5361c-108">Un valore numerico che deve essere arrotondato.</span><span class="sxs-lookup"><span data-stu-id="5361c-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="5361c-109">`decimals`: *Int* o *Reale*</span><span class="sxs-lookup"><span data-stu-id="5361c-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="5361c-110">Il numero al cui multiplo deve essere arrotondato il valore del parametro `number`.</span><span class="sxs-lookup"><span data-stu-id="5361c-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="5361c-111">`round rule`: *Valore enumerazione*</span><span class="sxs-lookup"><span data-stu-id="5361c-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="5361c-112">Un valore di enumerazione dell'enumerazione **RoundOffType** che definisce la regola di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="5361c-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="5361c-113">Questa enumerazione offre i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5361c-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="5361c-114">Normale (Ordinary)</span><span class="sxs-lookup"><span data-stu-id="5361c-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="5361c-115">Arrotondamento per difetto (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="5361c-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="5361c-116">Arrotondamento per eccesso (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="5361c-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="5361c-117">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="5361c-117">Return values</span></span>

<span data-ttu-id="5361c-118">*Reale*</span><span class="sxs-lookup"><span data-stu-id="5361c-118">*Real*</span></span>

<span data-ttu-id="5361c-119">Il valore numerico risultante è un multiplo del valore specificato dal parametro `decimals` ed è il più vicino al valore specificato dal parametro `number`.</span><span class="sxs-lookup"><span data-stu-id="5361c-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5361c-120">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="5361c-120">Usage notes</span></span>

<span data-ttu-id="5361c-121">Quando il parametro `number` è zero, questa funzione restituisce sempre zero.</span><span class="sxs-lookup"><span data-stu-id="5361c-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="5361c-122">Quando il parametro `decimals` è zero, questa funzione arrotonda al valore di arrotondamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="5361c-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="5361c-123">Quando il parametro `round rule` è impostato su **RoundOffType.Ordinary**, il valore di arrotondamento predefinito è **0,01**.</span><span class="sxs-lookup"><span data-stu-id="5361c-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="5361c-124">In caso contrario, il valore di arrotondamento predefinito è **1,0**.</span><span class="sxs-lookup"><span data-stu-id="5361c-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="5361c-125">Quando il parametro `round rule` è impostato su **RoundOffType.Ordinary**, questa funzione arrotonda all'importo di arrotondamento più vicino.</span><span class="sxs-lookup"><span data-stu-id="5361c-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="5361c-126">Quando il parametro `round rule` è impostato su **RoundOffType.RoundDown**, questa funzione arrotonda verso lo zero all'importo di arrotondamento più vicino.</span><span class="sxs-lookup"><span data-stu-id="5361c-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="5361c-127">Quando il parametro `round rule` è impostato su **RoundOffType.RoundUp**, questa funzione arrotonda lontano da zero all'importo di arrotondamento più vicino.</span><span class="sxs-lookup"><span data-stu-id="5361c-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="5361c-128">Quando il parametro `round rule` è impostato su **RoundOffType.Ordinary**, questa funzione si comporta come la funzione [ARROTONDA.MULTIPLO](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) di Excel e la funzione [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) di X++.</span><span class="sxs-lookup"><span data-stu-id="5361c-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="5361c-129">Note</span><span class="sxs-lookup"><span data-stu-id="5361c-129">Remarks</span></span>

<span data-ttu-id="5361c-130">Per arrotondare un valore numerico a un numero specificato di posizioni decimali, utilizzare la funzione [ROUND](er-functions-mathematical-round.md).</span><span class="sxs-lookup"><span data-stu-id="5361c-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="5361c-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="5361c-131">Example</span></span>

<span data-ttu-id="5361c-132">Se il parametro **model.RoundOff** è impostato su **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` restituisce 7,35.</span><span class="sxs-lookup"><span data-stu-id="5361c-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="5361c-133">Se il parametro **model.RoundOff** è impostato su **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` restituisce 7,35.</span><span class="sxs-lookup"><span data-stu-id="5361c-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="5361c-134">Se il parametro **model.RoundOff** è impostato su **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` restituisce 8,4.</span><span class="sxs-lookup"><span data-stu-id="5361c-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5361c-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5361c-135">Additional resources</span></span>

[<span data-ttu-id="5361c-136">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="5361c-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="5361c-137">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="5361c-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]