---
title: Funzione ER ISVALIDCHARACTERISO7064
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ISVALIDCHARACTERISO7064 della creazione di report elettronici (ER).
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
ms.openlocfilehash: 6f6f3326c9ca5cdcb3cef52f243d6d3da34251ce
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915926"
---
# <span data-ttu-id="a5625-103"><a name="ISVALIDCHARACTERISO7064">Funzione ER ISVALIDCHARACTERISO7064</a></span><span class="sxs-lookup"><span data-stu-id="a5625-103"><a name="ISVALIDCHARACTERISO7064">ISVALIDCHARACTERISO7064 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5625-104">La funzione `ISVALIDCHARACTERISO7064` restituisce un valore *Booleano* **TRUE** quando la stringa specificata rappresenta un numero di conto bancario internazionale (IBAN) valido.</span><span class="sxs-lookup"><span data-stu-id="a5625-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="a5625-105">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a5625-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5625-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5625-106">Syntax</span></span>

```
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="a5625-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a5625-107">Arguments</span></span>

<span data-ttu-id="a5625-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="a5625-108">`text`: *String*</span></span>

<span data-ttu-id="a5625-109">Un valore di testo che rappresenta un IBAN.</span><span class="sxs-lookup"><span data-stu-id="a5625-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="a5625-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a5625-110">Return values</span></span>

<span data-ttu-id="a5625-111">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="a5625-111">*String*</span></span>

<span data-ttu-id="a5625-112">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="a5625-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="a5625-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5625-113">Example</span></span>

<span data-ttu-id="a5625-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="a5625-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="a5625-115">`ISVALIDCHARACTERISO7064 ("AT61")` restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a5625-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5625-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a5625-116">Additional resources</span></span>

[<span data-ttu-id="a5625-117">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="a5625-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
