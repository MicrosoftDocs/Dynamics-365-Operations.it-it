---
title: Funzione ER POWER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione POWER della creazione di report elettronici (ER).
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
ms.openlocfilehash: 080b2f9b1ada55209c9470386aceab2d3ef456af
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744577"
---
# <a name="power-er-function"></a><span data-ttu-id="d2ad5-103">Funzione ER POWER</span><span class="sxs-lookup"><span data-stu-id="d2ad5-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2ad5-104">La funzione `POWER` restituisce un valore *Reale* che rappresenta il risultato dell'aumento del numero positivo specificato alla potenza specificata.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2ad5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2ad5-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="d2ad5-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d2ad5-106">Arguments</span></span>

<span data-ttu-id="d2ad5-107">`number`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="d2ad5-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="d2ad5-108">Un valore numerico che deve essere elevato alla potenza specificata.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="d2ad5-109">`power`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="d2ad5-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="d2ad5-110">Un valore numerico che rappresenta la potenza specifica.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="d2ad5-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d2ad5-111">Return values</span></span>

<span data-ttu-id="d2ad5-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="d2ad5-112">*Real*</span></span>

<span data-ttu-id="d2ad5-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="d2ad5-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="d2ad5-114">Example 1</span></span>

<span data-ttu-id="d2ad5-115">`POWER (10, 2)` restituisce **100**.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d2ad5-116">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="d2ad5-116">Example 2</span></span>

<span data-ttu-id="d2ad5-117">`POWER (4, 0.5)` restituisce **2**.</span><span class="sxs-lookup"><span data-stu-id="d2ad5-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2ad5-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d2ad5-118">Additional resources</span></span>

[<span data-ttu-id="d2ad5-119">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="d2ad5-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
