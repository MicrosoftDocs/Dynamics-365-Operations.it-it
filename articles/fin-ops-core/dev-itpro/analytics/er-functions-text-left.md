---
title: Funzione ER LEFT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LEFT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 112852ab955fdf8de9f78cc93486cc1d5f048517
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743785"
---
# <a name="left-er-function"></a><span data-ttu-id="c549a-103">Funzione ER LEFT</span><span class="sxs-lookup"><span data-stu-id="c549a-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c549a-104">La funzione `LEFT` restituisce un valore *Stringa* che presenta il numero specificato di caratteri dall'inizio della stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="c549a-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="c549a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c549a-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="c549a-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c549a-106">Arguments</span></span>

<span data-ttu-id="c549a-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="c549a-107">`text`: *String*</span></span>

<span data-ttu-id="c549a-108">Un valore *Stringa* che rappresenta il testo originale.</span><span class="sxs-lookup"><span data-stu-id="c549a-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="c549a-109">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="c549a-109">`number`: *Integer*</span></span>

<span data-ttu-id="c549a-110">Il numero di caratteri che devono essere restituiti dall'inizio del testo originale.</span><span class="sxs-lookup"><span data-stu-id="c549a-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="c549a-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="c549a-111">Return values</span></span>

<span data-ttu-id="c549a-112">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="c549a-112">*String*</span></span>

<span data-ttu-id="c549a-113">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="c549a-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c549a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="c549a-114">Example</span></span>

<span data-ttu-id="c549a-115">`LEFT ("Sample", 3)` restituisce **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="c549a-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c549a-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c549a-116">Additional resources</span></span>

[<span data-ttu-id="c549a-117">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="c549a-117">Text functions</span></span>](er-functions-category-text.md)
