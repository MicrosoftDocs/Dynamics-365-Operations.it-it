---
title: Funzione ER NUMBERFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMBERFORMAT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 41f48fb49b2d28acf69fe05fe87644a4c43e81fe
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070554"
---
# <span data-ttu-id="f479c-103"><a name="NUMBERFORMAT">Funzione ER NUMBERFORMAT</a></span><span class="sxs-lookup"><span data-stu-id="f479c-103"><a name="NUMBERFORMAT">NUMBERFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f479c-104">La funzione `NUMBERFORMAT` restituisce un valore *Stringa* che presenta il numero specificato nel formato specificato e nelle [impostazioni cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="f479c-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="f479c-105">Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="f479c-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f479c-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="f479c-106">Syntax 1</span></span>

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="f479c-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="f479c-107">Syntax 2</span></span>

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="f479c-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f479c-108">Arguments</span></span>

<span data-ttu-id="f479c-109">`number`: *Intero* o *Reale*</span><span class="sxs-lookup"><span data-stu-id="f479c-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="f479c-110">Un valore numerico che specifica il numero che deve essere formattato.</span><span class="sxs-lookup"><span data-stu-id="f479c-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="f479c-111">`format` : *Stringa*</span><span class="sxs-lookup"><span data-stu-id="f479c-111">`format` : *String*</span></span>

<span data-ttu-id="f479c-112">Un valore *Stringa* che rappresenta il formato.</span><span class="sxs-lookup"><span data-stu-id="f479c-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="f479c-113">`culture`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="f479c-113">`culture`: *String*</span></span>

<span data-ttu-id="f479c-114">Un valore *Stringa* che rappresenta le impostazioni cultura da utilizzare per la formattazione.</span><span class="sxs-lookup"><span data-stu-id="f479c-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="f479c-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="f479c-115">Return values</span></span>

<span data-ttu-id="f479c-116">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="f479c-116">*String*</span></span>

<span data-ttu-id="f479c-117">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="f479c-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f479c-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="f479c-118">Usage notes</span></span>

<span data-ttu-id="f479c-119">Se le impostazioni cultura non sono definite come argomento della funzione chiamata, il contesto in cui viene eseguita questa funzione determina le impostazioni cultura utilizzate per formattare i numeri.</span><span class="sxs-lookup"><span data-stu-id="f479c-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="f479c-120">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="f479c-120">Example 1</span></span>

<span data-ttu-id="f479c-121">Per le impostazioni cultura **EN-US**, `NUMBERFORMAT (0.45, "p")` restituisce **"45.00 %"** e `NUMBERFORMAT (10.45, "#")` restituisce **"10"**.</span><span class="sxs-lookup"><span data-stu-id="f479c-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f479c-122">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="f479c-122">Example 2</span></span>

<span data-ttu-id="f479c-123">`NUMBERFORMAT (10/3, "F2", "de")` restituisce **3,33**, mentre `NUMBERFORMAT (10/3, "F2", "en-us")` restituisce **3.33**.</span><span class="sxs-lookup"><span data-stu-id="f479c-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f479c-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f479c-124">Additional resources</span></span>

[<span data-ttu-id="f479c-125">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="f479c-125">Text functions</span></span>](er-functions-category-text.md)
