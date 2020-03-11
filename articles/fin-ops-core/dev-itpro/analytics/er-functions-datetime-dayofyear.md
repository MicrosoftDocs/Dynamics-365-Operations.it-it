---
title: Funzione ER DAYOFYEAR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DAYOFYEAR della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: d24aabb582151b0b357b64a988cc932a9c9f3cea
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070669"
---
# <span data-ttu-id="15fa4-103"><a name="DAYOFYEAR">Funzione ER DAYOFYEAR</a></span><span class="sxs-lookup"><span data-stu-id="15fa4-103"><a name="DAYOFYEAR">DAYOFYEAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15fa4-104">La funzione `DAYOFYEAR` restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra l'1 gennaio e la data specificata.</span><span class="sxs-lookup"><span data-stu-id="15fa4-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="15fa4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15fa4-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="15fa4-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="15fa4-106">Arguments</span></span>

<span data-ttu-id="15fa4-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="15fa4-107">`date`: *Date*</span></span>

<span data-ttu-id="15fa4-108">Un valore di data che rappresenta la data da utilizzare per il calcolo del numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="15fa4-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="15fa4-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="15fa4-109">Return values</span></span>

<span data-ttu-id="15fa4-110">*Intero*</span><span class="sxs-lookup"><span data-stu-id="15fa4-110">*Integer*</span></span>

<span data-ttu-id="15fa4-111">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="15fa4-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="15fa4-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="15fa4-112">Example 1</span></span>

<span data-ttu-id="15fa4-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` restituisce **61**.</span><span class="sxs-lookup"><span data-stu-id="15fa4-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="15fa4-114">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="15fa4-114">Example 2</span></span>

<span data-ttu-id="15fa4-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` restituisce **1**.</span><span class="sxs-lookup"><span data-stu-id="15fa4-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15fa4-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="15fa4-116">Additional resources</span></span>

[<span data-ttu-id="15fa4-117">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="15fa4-117">Date and time functions</span></span>](er-functions-category-datetime.md)
