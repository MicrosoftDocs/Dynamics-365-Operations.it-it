---
title: Funzione ER CURCREDREF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CURCREDREF della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: d5f126d71abdc9e3e488b4e8476850dc7763fe5a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567618"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="a95a7-103">Funzione ER CURCREDREF</span><span class="sxs-lookup"><span data-stu-id="a95a7-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a95a7-104">La funzione `CURCREDREF` restituisce un valore *Stringa* che rappresenta un riferimento creditore basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="a95a7-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="a95a7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a95a7-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="a95a7-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a95a7-106">Arguments</span></span>

<span data-ttu-id="a95a7-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="a95a7-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="a95a7-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="a95a7-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="a95a7-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a95a7-109">Return values</span></span>

<span data-ttu-id="a95a7-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="a95a7-110">*String*</span></span>

<span data-ttu-id="a95a7-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="a95a7-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="a95a7-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="a95a7-112">Example</span></span>

<span data-ttu-id="a95a7-113">`CURCredRef ("VEND-200002")` restituisce **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="a95a7-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a95a7-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a95a7-114">Additional resources</span></span>

[<span data-ttu-id="a95a7-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="a95a7-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]