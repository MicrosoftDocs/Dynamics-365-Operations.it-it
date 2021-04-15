---
title: Funzione ER ISVALIDCHARACTERISO7064
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ISVALIDCHARACTERISO7064 della creazione di report elettronici (ER).
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
ms.openlocfilehash: 1f102a6a3eafe3b066101370b94fa2f17ad3ad8b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748295"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="b8166-103">Funzione ER ISVALIDCHARACTERISO7064</span><span class="sxs-lookup"><span data-stu-id="b8166-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8166-104">La funzione `ISVALIDCHARACTERISO7064` restituisce un valore *Booleano* **TRUE** quando la stringa specificata rappresenta un numero di conto bancario internazionale (IBAN) valido.</span><span class="sxs-lookup"><span data-stu-id="b8166-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="b8166-105">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b8166-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8166-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8166-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="b8166-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b8166-107">Arguments</span></span>

<span data-ttu-id="b8166-108">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="b8166-108">`text`: *String*</span></span>

<span data-ttu-id="b8166-109">Un valore di testo che rappresenta un IBAN.</span><span class="sxs-lookup"><span data-stu-id="b8166-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="b8166-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b8166-110">Return values</span></span>

<span data-ttu-id="b8166-111">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="b8166-111">*String*</span></span>

<span data-ttu-id="b8166-112">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="b8166-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b8166-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8166-113">Example</span></span>

<span data-ttu-id="b8166-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="b8166-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="b8166-115">`ISVALIDCHARACTERISO7064 ("AT61")` restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b8166-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8166-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b8166-116">Additional resources</span></span>

[<span data-ttu-id="b8166-117">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="b8166-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]