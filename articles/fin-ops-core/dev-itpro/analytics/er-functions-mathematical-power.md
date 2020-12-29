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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 858f59cf0bc6387b09cbb6f0c59f58ba8107582c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683331"
---
# <a name="power-er-function"></a><span data-ttu-id="033e9-103">Funzione ER POWER</span><span class="sxs-lookup"><span data-stu-id="033e9-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="033e9-104">La funzione `POWER` restituisce un valore *Reale* che rappresenta il risultato dell'aumento del numero positivo specificato alla potenza specificata.</span><span class="sxs-lookup"><span data-stu-id="033e9-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="033e9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="033e9-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="033e9-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="033e9-106">Arguments</span></span>

<span data-ttu-id="033e9-107">`number`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="033e9-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="033e9-108">Un valore numerico che deve essere elevato alla potenza specificata.</span><span class="sxs-lookup"><span data-stu-id="033e9-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="033e9-109">`power`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="033e9-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="033e9-110">Un valore numerico che rappresenta la potenza specifica.</span><span class="sxs-lookup"><span data-stu-id="033e9-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="033e9-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="033e9-111">Return values</span></span>

<span data-ttu-id="033e9-112">*Reale*</span><span class="sxs-lookup"><span data-stu-id="033e9-112">*Real*</span></span>

<span data-ttu-id="033e9-113">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="033e9-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="033e9-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="033e9-114">Example 1</span></span>

<span data-ttu-id="033e9-115">`POWER (10, 2)` restituisce **100**.</span><span class="sxs-lookup"><span data-stu-id="033e9-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="033e9-116">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="033e9-116">Example 2</span></span>

<span data-ttu-id="033e9-117">`POWER (4, 0.5)` restituisce **2**.</span><span class="sxs-lookup"><span data-stu-id="033e9-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="033e9-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="033e9-118">Additional resources</span></span>

[<span data-ttu-id="033e9-119">Funzioni matematiche</span><span class="sxs-lookup"><span data-stu-id="033e9-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
