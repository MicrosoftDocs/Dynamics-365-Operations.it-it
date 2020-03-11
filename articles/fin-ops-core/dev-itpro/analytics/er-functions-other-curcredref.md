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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e684a8e063cb3c049d13005cbcf6ebbe688af00
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041494"
---
# <span data-ttu-id="89f2f-103"><a name="CURCREDREF">Funzione ER CURCREDREF</a></span><span class="sxs-lookup"><span data-stu-id="89f2f-103"><a name="CURCREDREF">CURCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89f2f-104">La funzione `CURCREDREF` restituisce un valore *Stringa* che rappresenta un riferimento creditore basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="89f2f-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="89f2f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89f2f-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="89f2f-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="89f2f-106">Arguments</span></span>

<span data-ttu-id="89f2f-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="89f2f-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="89f2f-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="89f2f-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="89f2f-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="89f2f-109">Return values</span></span>

<span data-ttu-id="89f2f-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="89f2f-110">*String*</span></span>

<span data-ttu-id="89f2f-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="89f2f-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="89f2f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="89f2f-112">Example</span></span>

<span data-ttu-id="89f2f-113">`CURCredRef ("VEND-200002")` restituisce **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="89f2f-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89f2f-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="89f2f-114">Additional resources</span></span>

[<span data-ttu-id="89f2f-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="89f2f-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
