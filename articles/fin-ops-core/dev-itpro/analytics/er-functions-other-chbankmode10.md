---
title: Funzione ER CH_BANK_MOD_10
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CH_BANK_MOD_10 della creazione di report elettronici (ER).
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
ms.openlocfilehash: c18a7f96096fbc6bbc7b6d15135c11bd70960d26
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744472"
---
# <a name="ch_bank_mod_10-er-function"></a><span data-ttu-id="ce297-103">Funzione ER CH_BANK_MOD_10</span><span class="sxs-lookup"><span data-stu-id="ce297-103">CH_BANK_MOD_10 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce297-104">La funzione `CH_BANK_MOD_10` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD10, basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="ce297-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce297-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce297-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="ce297-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ce297-106">Arguments</span></span>

<span data-ttu-id="ce297-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="ce297-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="ce297-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="ce297-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="ce297-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="ce297-109">Return values</span></span>

<span data-ttu-id="ce297-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="ce297-110">*String*</span></span>

<span data-ttu-id="ce297-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="ce297-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ce297-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce297-112">Example</span></span>

<span data-ttu-id="ce297-113">`CH_BANK_MOD_10 ("VEND-200002")` restituisce **3**.</span><span class="sxs-lookup"><span data-stu-id="ce297-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce297-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ce297-114">Additional resources</span></span>

[<span data-ttu-id="ce297-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="ce297-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
