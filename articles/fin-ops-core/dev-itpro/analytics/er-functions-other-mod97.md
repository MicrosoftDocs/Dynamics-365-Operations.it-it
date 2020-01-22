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
ms.openlocfilehash: 23e63f6b7999399fd5365c616613cbc603774d53
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916938"
---
# <span data-ttu-id="a0ca3-103"><a name="MOD_97">Funzione ER MOD_97</a></span><span class="sxs-lookup"><span data-stu-id="a0ca3-103"><a name="MOD_97">MOD_97 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0ca3-104">La funzione `MOD_97` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD97, basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="a0ca3-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0ca3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0ca3-105">Syntax</span></span>

```
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="a0ca3-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a0ca3-106">Arguments</span></span>

<span data-ttu-id="a0ca3-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="a0ca3-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="a0ca3-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="a0ca3-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="a0ca3-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a0ca3-109">Return values</span></span>

<span data-ttu-id="a0ca3-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="a0ca3-110">*String*</span></span>

<span data-ttu-id="a0ca3-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="a0ca3-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="a0ca3-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0ca3-112">Example</span></span>

<span data-ttu-id="a0ca3-113">`MOD_97 ("VEND-200002")` restituisce **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="a0ca3-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a0ca3-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a0ca3-114">Additional resources</span></span>

[<span data-ttu-id="a0ca3-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="a0ca3-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
