---
title: Funzione ER CURCREDREF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CURCREDREF della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3923126060963122634d90c2ba8a380f534e9178
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686764"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="06eae-103">Funzione ER CURCREDREF</span><span class="sxs-lookup"><span data-stu-id="06eae-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="06eae-104">La funzione `CURCREDREF` restituisce un valore *Stringa* che rappresenta un riferimento creditore basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="06eae-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="06eae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06eae-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="06eae-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="06eae-106">Arguments</span></span>

<span data-ttu-id="06eae-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="06eae-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="06eae-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="06eae-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="06eae-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="06eae-109">Return values</span></span>

<span data-ttu-id="06eae-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="06eae-110">*String*</span></span>

<span data-ttu-id="06eae-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="06eae-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="06eae-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="06eae-112">Example</span></span>

<span data-ttu-id="06eae-113">`CURCredRef ("VEND-200002")` restituisce **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="06eae-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="06eae-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="06eae-114">Additional resources</span></span>

[<span data-ttu-id="06eae-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="06eae-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
