---
title: Funzione ER DAYOFYEAR
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DAYOFYEAR della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ba63c96355a6a7a1eccaddf39e47a3edb2d1e651
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563536"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="383d7-103">Funzione ER DAYOFYEAR</span><span class="sxs-lookup"><span data-stu-id="383d7-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="383d7-104">La funzione `DAYOFYEAR` restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra l'1 gennaio e la data specificata.</span><span class="sxs-lookup"><span data-stu-id="383d7-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="383d7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="383d7-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="383d7-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="383d7-106">Arguments</span></span>

<span data-ttu-id="383d7-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="383d7-107">`date`: *Date*</span></span>

<span data-ttu-id="383d7-108">Un valore di data che rappresenta la data da utilizzare per il calcolo del numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="383d7-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="383d7-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="383d7-109">Return values</span></span>

<span data-ttu-id="383d7-110">*Intero*</span><span class="sxs-lookup"><span data-stu-id="383d7-110">*Integer*</span></span>

<span data-ttu-id="383d7-111">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="383d7-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="383d7-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="383d7-112">Example 1</span></span>

<span data-ttu-id="383d7-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` restituisce **61**.</span><span class="sxs-lookup"><span data-stu-id="383d7-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="383d7-114">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="383d7-114">Example 2</span></span>

<span data-ttu-id="383d7-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` restituisce **1**.</span><span class="sxs-lookup"><span data-stu-id="383d7-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="383d7-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="383d7-116">Additional resources</span></span>

[<span data-ttu-id="383d7-117">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="383d7-117">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]