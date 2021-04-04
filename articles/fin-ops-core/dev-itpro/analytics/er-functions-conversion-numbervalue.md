---
title: Funzione ER NUMBERVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMBERVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: f542621c4bcc29e03d8c92b0c700e2c80c9846f6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561424"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="33afe-103">Funzione ER NUMBERVALUE</span><span class="sxs-lookup"><span data-stu-id="33afe-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33afe-104">La funzione `NUMBERVALUE` restituisce un valore *Reale* che viene convertito dal valore *Stringa* specificato.</span><span class="sxs-lookup"><span data-stu-id="33afe-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="33afe-105">Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati.</span><span class="sxs-lookup"><span data-stu-id="33afe-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="33afe-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33afe-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="33afe-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="33afe-107">Arguments</span></span>

<span data-ttu-id="33afe-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="33afe-108">`text`: *String*</span></span>

<span data-ttu-id="33afe-109">Un valore di testo che deve essere convertito in un numero *Reale*.</span><span class="sxs-lookup"><span data-stu-id="33afe-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="33afe-110">`decimal separator`: Stringa</span><span class="sxs-lookup"><span data-stu-id="33afe-110">`decimal separator`: String</span></span>

<span data-ttu-id="33afe-111">Un separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="33afe-111">A decimal separator.</span></span> <span data-ttu-id="33afe-112">Utilizzato per separare le parti intere e frazionarie di un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="33afe-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="33afe-113">`digit grouping separator`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="33afe-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="33afe-114">Un separatore di raggruppamento delle cifre.</span><span class="sxs-lookup"><span data-stu-id="33afe-114">A digit grouping separator.</span></span> <span data-ttu-id="33afe-115">È usato come separatore delle migliaia.</span><span class="sxs-lookup"><span data-stu-id="33afe-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="33afe-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="33afe-116">Return values</span></span>

<span data-ttu-id="33afe-117">*Reale*</span><span class="sxs-lookup"><span data-stu-id="33afe-117">*Real*</span></span>

<span data-ttu-id="33afe-118">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="33afe-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="33afe-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="33afe-119">Example</span></span>

<span data-ttu-id="33afe-120">`NUMBERVALUE( "1 234,56", ",", " ")` restituisce **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="33afe-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33afe-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="33afe-121">Additional resources</span></span>

[<span data-ttu-id="33afe-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="33afe-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]