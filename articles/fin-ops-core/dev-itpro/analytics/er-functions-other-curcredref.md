---
title: Funzione ER CURCREDREF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CURCREDREF della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 65f04e23000e4d2429574db71b18b6907403855e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744345"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="e8c46-103">Funzione ER CURCREDREF</span><span class="sxs-lookup"><span data-stu-id="e8c46-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8c46-104">La funzione `CURCREDREF` restituisce un valore *Stringa* che rappresenta un riferimento creditore basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="e8c46-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8c46-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8c46-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="e8c46-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e8c46-106">Arguments</span></span>

<span data-ttu-id="e8c46-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="e8c46-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="e8c46-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="e8c46-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="e8c46-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="e8c46-109">Return values</span></span>

<span data-ttu-id="e8c46-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="e8c46-110">*String*</span></span>

<span data-ttu-id="e8c46-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="e8c46-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="e8c46-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8c46-112">Example</span></span>

<span data-ttu-id="e8c46-113">`CURCredRef ("VEND-200002")` restituisce **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="e8c46-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8c46-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e8c46-114">Additional resources</span></span>

[<span data-ttu-id="e8c46-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="e8c46-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]