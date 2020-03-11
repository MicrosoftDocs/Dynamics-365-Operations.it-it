---
title: Funzione ER MOD_97
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione MOD_97 della creazione di report elettronici (ER).
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
ms.openlocfilehash: ce2192c7bc849996e08573d71d8ed43956c8fb89
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070531"
---
# <span data-ttu-id="7677d-103"><a name="MOD_97">Funzione ER MOD_97</a></span><span class="sxs-lookup"><span data-stu-id="7677d-103"><a name="MOD_97">MOD_97 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7677d-104">La funzione `MOD_97` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD97, basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="7677d-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="7677d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7677d-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="7677d-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7677d-106">Arguments</span></span>

<span data-ttu-id="7677d-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="7677d-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="7677d-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="7677d-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="7677d-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="7677d-109">Return values</span></span>

<span data-ttu-id="7677d-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="7677d-110">*String*</span></span>

<span data-ttu-id="7677d-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="7677d-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="7677d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7677d-112">Example</span></span>

<span data-ttu-id="7677d-113">`MOD_97 ("VEND-200002")` restituisce **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="7677d-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7677d-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7677d-114">Additional resources</span></span>

[<span data-ttu-id="7677d-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="7677d-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
