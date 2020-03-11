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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 92150bb23e76f82907e0f3e8f0738b25801958bf
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041564"
---
# <span data-ttu-id="d96af-103"><a name="ROUNDDOWN">Funzione ER ROUNDDOWN</a></span><span class="sxs-lookup"><span data-stu-id="d96af-103"><a name="ROUNDDOWN">ROUNDDOWN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d96af-104">La funzione `ROUNDDOWN` restituisce il numero specificato come valore *Reale* dopo che è stato arrotondato per difetto al numero di posizioni decimali specificato.</span><span class="sxs-lookup"><span data-stu-id="d96af-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="d96af-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d96af-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="d96af-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d96af-106">Arguments</span></span>

<span data-ttu-id="d96af-107">`number`: *Reale*</span><span class="sxs-lookup"><span data-stu-id="d96af-107">`number`: *Real*</span></span>

<span data-ttu-id="d96af-108">Un valore numerico che deve essere arrotondato per difetto.</span><span class="sxs-lookup"><span data-stu-id="d96af-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="d96af-109">`decimals`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="d96af-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="d96af-110">Un valore numerico che rappresenta il numero di posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="d96af-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="d96af-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d96af-111">Return values</span></span>

<span data-ttu-id="d96af-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="d96af-112">*Real*</span></span>

<span data-ttu-id="d96af-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="d96af-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d96af-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d96af-114">Usage notes</span></span>

<span data-ttu-id="d96af-115">Questa funzione si comporta analogamente a [ROUND](er-functions-mathematical-round.md) ma sempre per difetto (verso lo zero).</span><span class="sxs-lookup"><span data-stu-id="d96af-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="d96af-116">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="d96af-116">Example 1</span></span>

<span data-ttu-id="d96af-117">`ROUNDDOWN (1200.767, 2)` arrotonda per difetto a due posti decimali e restituisce **1200.76**.</span><span class="sxs-lookup"><span data-stu-id="d96af-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="d96af-118">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="d96af-118">Example 2</span></span>

<span data-ttu-id="d96af-119">`ROUNDDOWN (1700.767, -3)` arrotonda per difetto al più vicino multiplo di 1000 e restituisce **1000**.</span><span class="sxs-lookup"><span data-stu-id="d96af-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d96af-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d96af-120">Additional resources</span></span>

[<span data-ttu-id="d96af-121">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="d96af-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
