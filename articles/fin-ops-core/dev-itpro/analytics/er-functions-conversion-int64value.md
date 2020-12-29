---
title: Funzione ER INT64VALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INT64VALUE della creazione di report elettronici (ER).
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
ms.openlocfilehash: bb750116312df82448f5a0048e380f9e5274f8e9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686053"
---
# <a name="int64value-er-function"></a><span data-ttu-id="2231b-103">Funzione ER INT64VALUE</span><span class="sxs-lookup"><span data-stu-id="2231b-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2231b-104">La funzione `INT64VALUE` restituisce un valore *Int64* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="2231b-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="2231b-105">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="2231b-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="2231b-106">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="2231b-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="2231b-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2231b-107">Arguments</span></span>

<span data-ttu-id="2231b-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="2231b-108">`text`: *String*</span></span>

<span data-ttu-id="2231b-109">Un valore di testo che deve essere convertito in un numero *Int64*.</span><span class="sxs-lookup"><span data-stu-id="2231b-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="2231b-110">`number`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="2231b-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="2231b-111">Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int64*.</span><span class="sxs-lookup"><span data-stu-id="2231b-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="2231b-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2231b-112">Return values</span></span>

<span data-ttu-id="2231b-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="2231b-113">*Int64*</span></span>

<span data-ttu-id="2231b-114">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="2231b-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2231b-115">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="2231b-115">Usage notes</span></span>

<span data-ttu-id="2231b-116">Tutte le posizioni decimali sono troncate.</span><span class="sxs-lookup"><span data-stu-id="2231b-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="2231b-117">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="2231b-117">Example 1</span></span>

<span data-ttu-id="2231b-118">`INT64VALUE ("22565422744")` restituisce il valore *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="2231b-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2231b-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="2231b-119">Example 2</span></span>

<span data-ttu-id="2231b-120">`INT64VALUE ( VALUE("22565422744.77"))` restituisce il valore *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="2231b-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2231b-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2231b-121">Additional resources</span></span>

[<span data-ttu-id="2231b-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="2231b-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
