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
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915903"
---
# <span data-ttu-id="b93b4-103"><a name="POWER">Funzione ER POWER</a></span><span class="sxs-lookup"><span data-stu-id="b93b4-103"><a name="POWER">POWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b93b4-104">La funzione `POWER` restituisce un valore *Reale* che rappresenta il risultato dell'aumento del numero positivo specificato alla potenza specificata.</span><span class="sxs-lookup"><span data-stu-id="b93b4-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="b93b4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b93b4-105">Syntax</span></span>

```
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="b93b4-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b93b4-106">Arguments</span></span>

<span data-ttu-id="b93b4-107">`number`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="b93b4-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="b93b4-108">Un valore numerico che deve essere elevato alla potenza specificata.</span><span class="sxs-lookup"><span data-stu-id="b93b4-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="b93b4-109">`power`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="b93b4-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="b93b4-110">Un valore numerico che rappresenta la potenza specifica.</span><span class="sxs-lookup"><span data-stu-id="b93b4-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="b93b4-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b93b4-111">Return values</span></span>

<span data-ttu-id="b93b4-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="b93b4-112">*Real*</span></span>

<span data-ttu-id="b93b4-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="b93b4-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="b93b4-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b93b4-114">Example 1</span></span>

<span data-ttu-id="b93b4-115">`POWER (10, 2)` restituisce **100**.</span><span class="sxs-lookup"><span data-stu-id="b93b4-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b93b4-116">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="b93b4-116">Example 2</span></span>

<span data-ttu-id="b93b4-117">`POWER (4, 0.5)` restituisce **2**.</span><span class="sxs-lookup"><span data-stu-id="b93b4-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b93b4-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b93b4-118">Additional resources</span></span>

[<span data-ttu-id="b93b4-119">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="b93b4-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
