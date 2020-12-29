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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3eec6dc5a472f366c9029456fe05cf1e431e1c5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685981"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="56d2d-103">Funzione ER NUMBERVALUE</span><span class="sxs-lookup"><span data-stu-id="56d2d-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56d2d-104">La funzione `NUMBERVALUE` restituisce un valore *Reale* che viene convertito dal valore *Stringa* specificato.</span><span class="sxs-lookup"><span data-stu-id="56d2d-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="56d2d-105">Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati.</span><span class="sxs-lookup"><span data-stu-id="56d2d-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="56d2d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56d2d-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="56d2d-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="56d2d-107">Arguments</span></span>

<span data-ttu-id="56d2d-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="56d2d-108">`text`: *String*</span></span>

<span data-ttu-id="56d2d-109">Un valore di testo che deve essere convertito in un numero *Reale*.</span><span class="sxs-lookup"><span data-stu-id="56d2d-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="56d2d-110">`decimal separator`: Stringa</span><span class="sxs-lookup"><span data-stu-id="56d2d-110">`decimal separator`: String</span></span>

<span data-ttu-id="56d2d-111">Un separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="56d2d-111">A decimal separator.</span></span> <span data-ttu-id="56d2d-112">Utilizzato per separare le parti intere e frazionarie di un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="56d2d-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="56d2d-113">`digit grouping separator`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="56d2d-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="56d2d-114">Un separatore di raggruppamento delle cifre.</span><span class="sxs-lookup"><span data-stu-id="56d2d-114">A digit grouping separator.</span></span> <span data-ttu-id="56d2d-115">È usato come separatore delle migliaia.</span><span class="sxs-lookup"><span data-stu-id="56d2d-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="56d2d-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="56d2d-116">Return values</span></span>

<span data-ttu-id="56d2d-117">*Reale*</span><span class="sxs-lookup"><span data-stu-id="56d2d-117">*Real*</span></span>

<span data-ttu-id="56d2d-118">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="56d2d-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="56d2d-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="56d2d-119">Example</span></span>

<span data-ttu-id="56d2d-120">`NUMBERVALUE( "1 234,56", ",", " ")` restituisce **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="56d2d-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56d2d-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="56d2d-121">Additional resources</span></span>

[<span data-ttu-id="56d2d-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="56d2d-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
