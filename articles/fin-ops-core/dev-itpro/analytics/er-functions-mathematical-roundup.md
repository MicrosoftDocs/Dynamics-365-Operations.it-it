---
title: Funzione ER ROUNDUP
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ROUNDUP della creazione di report elettronici (ER).
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
ms.openlocfilehash: d23a984bd59c4d2d37c407e3fcfed9c7017dcc7f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569337"
---
# <a name="roundup-er-function"></a><span data-ttu-id="d6423-103">Funzione ER ROUNDUP</span><span class="sxs-lookup"><span data-stu-id="d6423-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d6423-104">La funzione `ROUNDUP` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato per eccesso al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="d6423-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6423-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6423-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="d6423-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d6423-106">Arguments</span></span>

<span data-ttu-id="d6423-107">`number`: *Reale*</span><span class="sxs-lookup"><span data-stu-id="d6423-107">`number`: *Real*</span></span>

<span data-ttu-id="d6423-108">Un valore numerico che deve essere arrotondato per eccesso.</span><span class="sxs-lookup"><span data-stu-id="d6423-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="d6423-109">`decimals`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="d6423-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="d6423-110">Un valore numerico che rappresenta il numero di posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="d6423-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="d6423-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d6423-111">Return values</span></span>

<span data-ttu-id="d6423-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="d6423-112">*Real*</span></span>

<span data-ttu-id="d6423-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="d6423-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d6423-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d6423-114">Usage notes</span></span>

<span data-ttu-id="d6423-115">Questa funzione si comporta analogamente a [ROUND](er-functions-mathematical-round.md) ma sempre per eccesso (lontano da zero).</span><span class="sxs-lookup"><span data-stu-id="d6423-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="d6423-116">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="d6423-116">Example 1</span></span>

<span data-ttu-id="d6423-117">`ROUNDUP (1200.763, 2)` arrotonda per eccesso a due posti decimali e restituisce **1200.77**.</span><span class="sxs-lookup"><span data-stu-id="d6423-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d6423-118">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="d6423-118">Example 2</span></span>

<span data-ttu-id="d6423-119">`ROUNDUP (1200.767, -3)` arrotonda per eccesso al più vicino multiplo di 1000 e restituisce **2000**.</span><span class="sxs-lookup"><span data-stu-id="d6423-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6423-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d6423-120">Additional resources</span></span>

[<span data-ttu-id="d6423-121">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="d6423-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]