---
title: Funzione ER LEFT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LEFT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: 69b1d95ea0e82b1947b665b0724cff6c5b319633
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746341"
---
# <a name="left-er-function"></a><span data-ttu-id="bd55a-103">Funzione ER LEFT</span><span class="sxs-lookup"><span data-stu-id="bd55a-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd55a-104">La funzione `LEFT` restituisce un valore *Stringa* che presenta il numero specificato di caratteri dall'inizio della stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="bd55a-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd55a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd55a-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="bd55a-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="bd55a-106">Arguments</span></span>

<span data-ttu-id="bd55a-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="bd55a-107">`text`: *String*</span></span>

<span data-ttu-id="bd55a-108">Un valore *Stringa* che rappresenta il testo originale.</span><span class="sxs-lookup"><span data-stu-id="bd55a-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="bd55a-109">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="bd55a-109">`number`: *Integer*</span></span>

<span data-ttu-id="bd55a-110">Il numero di caratteri che devono essere restituiti dall'inizio del testo originale.</span><span class="sxs-lookup"><span data-stu-id="bd55a-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="bd55a-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="bd55a-111">Return values</span></span>

<span data-ttu-id="bd55a-112">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="bd55a-112">*String*</span></span>

<span data-ttu-id="bd55a-113">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="bd55a-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="bd55a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd55a-114">Example</span></span>

<span data-ttu-id="bd55a-115">`LEFT ("Sample", 3)` restituisce **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="bd55a-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd55a-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bd55a-116">Additional resources</span></span>

[<span data-ttu-id="bd55a-117">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="bd55a-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]