---
title: Funzione ER RIGHT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione RIGHT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: f59b12f0b3f7b100b953b2072677c83c836746ff
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746125"
---
# <a name="right-er-function"></a><span data-ttu-id="7d27b-103">Funzione ER RIGHT</span><span class="sxs-lookup"><span data-stu-id="7d27b-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d27b-104">La funzione `RIGHT` restituisce un valore *Stringa* che presenta il numero specificato di caratteri alla fine della stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="7d27b-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d27b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d27b-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="7d27b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7d27b-106">Arguments</span></span>

<span data-ttu-id="7d27b-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="7d27b-107">`text`: *String*</span></span>

<span data-ttu-id="7d27b-108">Un valore *Stringa* che rappresenta il testo originale.</span><span class="sxs-lookup"><span data-stu-id="7d27b-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="7d27b-109">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="7d27b-109">`number`: *Integer*</span></span>

<span data-ttu-id="7d27b-110">Il numero di caratteri che devono essere restituiti dalla fine del testo originale.</span><span class="sxs-lookup"><span data-stu-id="7d27b-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="7d27b-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="7d27b-111">Return values</span></span>

<span data-ttu-id="7d27b-112">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="7d27b-112">*String*</span></span>

<span data-ttu-id="7d27b-113">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="7d27b-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="7d27b-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d27b-114">Example</span></span>

<span data-ttu-id="7d27b-115">`RIGHT ("Sample", 3)` restituisce **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="7d27b-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d27b-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7d27b-116">Additional resources</span></span>

[<span data-ttu-id="7d27b-117">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="7d27b-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]