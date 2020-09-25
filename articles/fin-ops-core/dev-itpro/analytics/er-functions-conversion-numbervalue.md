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
ms.openlocfilehash: 13346c4810d6c93d4ef47ce525831332562c7f51
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743401"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="875e9-103">Funzione ER NUMBERVALUE</span><span class="sxs-lookup"><span data-stu-id="875e9-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="875e9-104">La funzione `NUMBERVALUE` restituisce un valore *Reale* che viene convertito dal valore *Stringa* specificato.</span><span class="sxs-lookup"><span data-stu-id="875e9-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="875e9-105">Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati.</span><span class="sxs-lookup"><span data-stu-id="875e9-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="875e9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="875e9-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="875e9-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="875e9-107">Arguments</span></span>

<span data-ttu-id="875e9-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="875e9-108">`text`: *String*</span></span>

<span data-ttu-id="875e9-109">Un valore di testo che deve essere convertito in un numero *Reale*.</span><span class="sxs-lookup"><span data-stu-id="875e9-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="875e9-110">`decimal separator`: Stringa</span><span class="sxs-lookup"><span data-stu-id="875e9-110">`decimal separator`: String</span></span>

<span data-ttu-id="875e9-111">Un separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="875e9-111">A decimal separator.</span></span> <span data-ttu-id="875e9-112">Utilizzato per separare le parti intere e frazionarie di un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="875e9-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="875e9-113">`digit grouping separator`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="875e9-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="875e9-114">Un separatore di raggruppamento delle cifre.</span><span class="sxs-lookup"><span data-stu-id="875e9-114">A digit grouping separator.</span></span> <span data-ttu-id="875e9-115">È usato come separatore delle migliaia.</span><span class="sxs-lookup"><span data-stu-id="875e9-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="875e9-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="875e9-116">Return values</span></span>

<span data-ttu-id="875e9-117">*Reale*</span><span class="sxs-lookup"><span data-stu-id="875e9-117">*Real*</span></span>

<span data-ttu-id="875e9-118">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="875e9-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="875e9-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="875e9-119">Example</span></span>

<span data-ttu-id="875e9-120">`NUMBERVALUE( "1 234,56", ",", " ")` restituisce **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="875e9-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="875e9-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="875e9-121">Additional resources</span></span>

[<span data-ttu-id="875e9-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="875e9-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
