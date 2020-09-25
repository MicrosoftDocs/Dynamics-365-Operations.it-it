---
title: Funzione ER MID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione MID della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: e2addace5c5606ebaae56ca658700347978a805b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744721"
---
# <a name="mid-er-function"></a><span data-ttu-id="b2e59-103">Funzione ER MID</span><span class="sxs-lookup"><span data-stu-id="b2e59-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2e59-104">La funzione `MID` restituisce un valore *Stringa* che presenta il numero specificato di caratteri della stringa specificata all'inizio della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="b2e59-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2e59-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2e59-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="b2e59-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b2e59-106">Arguments</span></span>

<span data-ttu-id="b2e59-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="b2e59-107">`text`: *String*</span></span>

<span data-ttu-id="b2e59-108">Un valore *Stringa* che specifica il testo da cui restituire i caratteri.</span><span class="sxs-lookup"><span data-stu-id="b2e59-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="b2e59-109">`starting position`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="b2e59-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="b2e59-110">Un valore *Intero* che specifica la posizione del primo carattere che deve essere restituito dal testo specificato.</span><span class="sxs-lookup"><span data-stu-id="b2e59-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="b2e59-111">`number of characters`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="b2e59-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="b2e59-112">Un valore *Intero* che specifica il numero di caratteri che deve essere restituito, iniziando dalla posizione di inizio specificata.</span><span class="sxs-lookup"><span data-stu-id="b2e59-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="b2e59-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b2e59-113">Return values</span></span>

<span data-ttu-id="b2e59-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="b2e59-114">*String*</span></span>

<span data-ttu-id="b2e59-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="b2e59-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b2e59-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="b2e59-116">Usage notes</span></span>

<span data-ttu-id="b2e59-117">Se il valore dell'argomento `starting position` è inferiore a 0 (zero), i caratteri restituiti vengono conteggiati dalla prima posizione nella stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="b2e59-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="b2e59-118">Se il valore dell'argomento `starting position` supera la lunghezza della stringa specificata, viene restituita una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="b2e59-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="b2e59-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2e59-119">Example</span></span>

<span data-ttu-id="b2e59-120">`MID ("Sample", 2, 3)` restituisce **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="b2e59-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2e59-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b2e59-121">Additional resources</span></span>

[<span data-ttu-id="b2e59-122">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="b2e59-122">Text functions</span></span>](er-functions-category-text.md)
