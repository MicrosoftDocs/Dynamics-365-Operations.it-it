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
ms.openlocfilehash: 1080a1c2e30cd7ca64ea43120c11eb90d3c99416
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916340"
---
# <span data-ttu-id="1bdaf-103"><a name="DAYOFYEAR">Funzione ER DAYOFYEAR</a></span><span class="sxs-lookup"><span data-stu-id="1bdaf-103"><a name="DAYOFYEAR">DAYOFYEAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1bdaf-104">La funzione `DAYOFYEAR` restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra l'1 gennaio e la data specificata.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="1bdaf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bdaf-105">Syntax</span></span>

```
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="1bdaf-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1bdaf-106">Arguments</span></span>

<span data-ttu-id="1bdaf-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="1bdaf-107">`date`: *Date*</span></span>

<span data-ttu-id="1bdaf-108">Un valore di data che rappresenta la data da utilizzare per il calcolo del numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="1bdaf-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="1bdaf-109">Return values</span></span>

<span data-ttu-id="1bdaf-110">*Intero*</span><span class="sxs-lookup"><span data-stu-id="1bdaf-110">*Integer*</span></span>

<span data-ttu-id="1bdaf-111">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="1bdaf-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="1bdaf-112">Example 1</span></span>

<span data-ttu-id="1bdaf-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` restituisce **61**.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1bdaf-114">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="1bdaf-114">Example 2</span></span>

<span data-ttu-id="1bdaf-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` restituisce **1**.</span><span class="sxs-lookup"><span data-stu-id="1bdaf-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1bdaf-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1bdaf-116">Additional resources</span></span>

[<span data-ttu-id="1bdaf-117">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="1bdaf-117">Date and time functions</span></span>](er-functions-category-datetime.md)
