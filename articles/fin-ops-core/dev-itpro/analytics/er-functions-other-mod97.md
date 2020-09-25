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
ms.openlocfilehash: b58e06a034fc6d26c891b78c26ac53c87a39b92b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744049"
---
# <a name="mod_97-er-function"></a><span data-ttu-id="02cbe-103">Funzione ER MOD_97</span><span class="sxs-lookup"><span data-stu-id="02cbe-103">MOD_97 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02cbe-104">La funzione `MOD_97` restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD97, basato sulle cifre del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="02cbe-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="02cbe-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02cbe-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="02cbe-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="02cbe-106">Arguments</span></span>

<span data-ttu-id="02cbe-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="02cbe-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="02cbe-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="02cbe-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="02cbe-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="02cbe-109">Return values</span></span>

<span data-ttu-id="02cbe-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="02cbe-110">*String*</span></span>

<span data-ttu-id="02cbe-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="02cbe-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="02cbe-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="02cbe-112">Example</span></span>

<span data-ttu-id="02cbe-113">`MOD_97 ("VEND-200002")` restituisce **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="02cbe-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02cbe-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="02cbe-114">Additional resources</span></span>

[<span data-ttu-id="02cbe-115">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="02cbe-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
