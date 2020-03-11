---
title: Funzione ER NUMBERVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMBERVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 6eeb66f4206eb39141a5b2573fcb9d15428ae52a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042658"
---
# <span data-ttu-id="2ddd4-103"><a name="NUMBERVALUE">Funzione ER NUMBERVALUE</a></span><span class="sxs-lookup"><span data-stu-id="2ddd4-103"><a name="NUMBERVALUE">NUMBERVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ddd4-104">La funzione `NUMBERVALUE` restituisce un valore *Reale* che viene convertito dal valore *Stringa* specificato.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="2ddd4-105">Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ddd4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ddd4-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="2ddd4-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2ddd4-107">Arguments</span></span>

<span data-ttu-id="2ddd4-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="2ddd4-108">`text`: *String*</span></span>

<span data-ttu-id="2ddd4-109">Un valore di testo che deve essere convertito in un numero *Reale*.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="2ddd4-110">`decimal separator`: Stringa</span><span class="sxs-lookup"><span data-stu-id="2ddd4-110">`decimal separator`: String</span></span>

<span data-ttu-id="2ddd4-111">Un separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-111">A decimal separator.</span></span> <span data-ttu-id="2ddd4-112">Utilizzato per separare le parti intere e frazionarie di un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="2ddd4-113">`digit grouping separator`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="2ddd4-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="2ddd4-114">Un separatore di raggruppamento delle cifre.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-114">A digit grouping separator.</span></span> <span data-ttu-id="2ddd4-115">È usato come separatore delle migliaia.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="2ddd4-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2ddd4-116">Return values</span></span>

<span data-ttu-id="2ddd4-117">*Reale*</span><span class="sxs-lookup"><span data-stu-id="2ddd4-117">*Real*</span></span>

<span data-ttu-id="2ddd4-118">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="2ddd4-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ddd4-119">Example</span></span>

<span data-ttu-id="2ddd4-120">`NUMBERVALUE( "1 234,56", ",", " ")` restituisce **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="2ddd4-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2ddd4-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2ddd4-121">Additional resources</span></span>

[<span data-ttu-id="2ddd4-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="2ddd4-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
