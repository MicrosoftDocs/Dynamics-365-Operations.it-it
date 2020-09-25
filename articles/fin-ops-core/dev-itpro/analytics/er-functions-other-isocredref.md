---
title: Funzione ER ISOCREDREF
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ISOCREDREF della creazione di report elettronici (ER).
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
ms.openlocfilehash: d6e5d025e7de15c27b19711ea5b597d75bdf3d41
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744097"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="f254b-103">Funzione ER ISOCREDREF</span><span class="sxs-lookup"><span data-stu-id="f254b-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f254b-104">La funzione `ISOCREDREF` restituisce un valore *Stringa* che rappresenta un riferimento creditore International Organization for Standardization (ISO), in base alle cifre e ai simboli alfabetici del numero di fattura specificato.</span><span class="sxs-lookup"><span data-stu-id="f254b-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="f254b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f254b-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="f254b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f254b-106">Arguments</span></span>

<span data-ttu-id="f254b-107">`invoice number digits`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="f254b-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="f254b-108">Un valore di testo che rappresenta le cifre di un numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="f254b-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="f254b-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="f254b-109">Return values</span></span>

<span data-ttu-id="f254b-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="f254b-110">*String*</span></span>

<span data-ttu-id="f254b-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="f254b-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f254b-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="f254b-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="f254b-113">Per eliminare i simboli da alfabeti che non sono conformi ISO, l'argomento `invoice number digits` deve essere tradotto prima di passarlo alla funzione.</span><span class="sxs-lookup"><span data-stu-id="f254b-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="f254b-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="f254b-114">Example</span></span>

<span data-ttu-id="f254b-115">`ISOCredRef ("VEND-200002")` restituisce **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="f254b-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f254b-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f254b-116">Additional resources</span></span>

[<span data-ttu-id="f254b-117">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="f254b-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
