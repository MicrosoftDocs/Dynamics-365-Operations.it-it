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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 75df802b75454baeea75a8ceb32d5d045a77a3a0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916547"
---
# <span data-ttu-id="5dcf8-103"><a name="INT64VALUE">Funzione ER INT64VALUE</a></span><span class="sxs-lookup"><span data-stu-id="5dcf8-103"><a name="INT64VALUE">INT64VALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5dcf8-104">La funzione `INT64VALUE` restituisce un valore *Int64* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="5dcf8-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="5dcf8-105">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="5dcf8-105">Syntax 1</span></span>

```
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="5dcf8-106">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="5dcf8-106">Syntax 2</span></span>

```
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="5dcf8-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5dcf8-107">Arguments</span></span>

<span data-ttu-id="5dcf8-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="5dcf8-108">`text`: *String*</span></span>

<span data-ttu-id="5dcf8-109">Un valore di testo che deve essere convertito in un numero *Int64*.</span><span class="sxs-lookup"><span data-stu-id="5dcf8-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="5dcf8-110">`number`: *Reale* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="5dcf8-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="5dcf8-111">Un valore numerico *Reale* o *Intero* che deve essere convertito in un numero *Int64*.</span><span class="sxs-lookup"><span data-stu-id="5dcf8-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="5dcf8-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="5dcf8-112">Return values</span></span>

<span data-ttu-id="5dcf8-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="5dcf8-113">*Int64*</span></span>

<span data-ttu-id="5dcf8-114">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="5dcf8-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5dcf8-115">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="5dcf8-115">Usage notes</span></span>

<span data-ttu-id="5dcf8-116">Tutte le posizioni decimali sono troncate.</span><span class="sxs-lookup"><span data-stu-id="5dcf8-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="5dcf8-117">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="5dcf8-117">Example 1</span></span>

<span data-ttu-id="5dcf8-118">`INT64VALUE ("22565422744")` restituisce il valore *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="5dcf8-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5dcf8-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="5dcf8-119">Example 2</span></span>

<span data-ttu-id="5dcf8-120">`INT64VALUE ( VALUE("22565422744.77"))` restituisce il valore *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="5dcf8-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5dcf8-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5dcf8-121">Additional resources</span></span>

[<span data-ttu-id="5dcf8-122">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="5dcf8-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
