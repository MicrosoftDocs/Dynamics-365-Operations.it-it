---
title: Funzione ER ISVALIDCHARACTERISO7064
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ISVALIDCHARACTERISO7064 della creazione di report elettronici (ER).
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
ms.openlocfilehash: 26300adce5f9a8a567510885577c6cfb9b1c859a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563368"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="d866a-103">Funzione ER ISVALIDCHARACTERISO7064</span><span class="sxs-lookup"><span data-stu-id="d866a-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d866a-104">La funzione `ISVALIDCHARACTERISO7064` restituisce un valore *Booleano* **TRUE** quando la stringa specificata rappresenta un numero di conto bancario internazionale (IBAN) valido.</span><span class="sxs-lookup"><span data-stu-id="d866a-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="d866a-105">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="d866a-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="d866a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d866a-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="d866a-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d866a-107">Arguments</span></span>

<span data-ttu-id="d866a-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d866a-108">`text`: *String*</span></span>

<span data-ttu-id="d866a-109">Un valore di testo che rappresenta un IBAN.</span><span class="sxs-lookup"><span data-stu-id="d866a-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="d866a-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d866a-110">Return values</span></span>

<span data-ttu-id="d866a-111">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="d866a-111">*String*</span></span>

<span data-ttu-id="d866a-112">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="d866a-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d866a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d866a-113">Example</span></span>

<span data-ttu-id="d866a-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="d866a-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="d866a-115">`ISVALIDCHARACTERISO7064 ("AT61")` restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="d866a-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d866a-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d866a-116">Additional resources</span></span>

[<span data-ttu-id="d866a-117">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="d866a-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]