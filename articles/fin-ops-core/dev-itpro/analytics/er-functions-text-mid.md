---
title: Funzione ER MID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione MID della creazione di report elettronici (ER).
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
ms.openlocfilehash: 9a9ff3f1055f6757d6d4073dbb816773d8bfc8ba
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746269"
---
# <a name="mid-er-function"></a><span data-ttu-id="19dc1-103">Funzione ER MID</span><span class="sxs-lookup"><span data-stu-id="19dc1-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19dc1-104">La funzione `MID` restituisce un valore *Stringa* che presenta il numero specificato di caratteri della stringa specificata all'inizio della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="19dc1-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="19dc1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19dc1-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="19dc1-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="19dc1-106">Arguments</span></span>

<span data-ttu-id="19dc1-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="19dc1-107">`text`: *String*</span></span>

<span data-ttu-id="19dc1-108">Un valore *Stringa* che specifica il testo da cui restituire i caratteri.</span><span class="sxs-lookup"><span data-stu-id="19dc1-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="19dc1-109">`starting position`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="19dc1-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="19dc1-110">Un valore *Intero* che specifica la posizione del primo carattere che deve essere restituito dal testo specificato.</span><span class="sxs-lookup"><span data-stu-id="19dc1-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="19dc1-111">`number of characters`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="19dc1-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="19dc1-112">Un valore *Intero* che specifica il numero di caratteri che deve essere restituito, iniziando dalla posizione di inizio specificata.</span><span class="sxs-lookup"><span data-stu-id="19dc1-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="19dc1-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="19dc1-113">Return values</span></span>

<span data-ttu-id="19dc1-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="19dc1-114">*String*</span></span>

<span data-ttu-id="19dc1-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="19dc1-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="19dc1-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="19dc1-116">Usage notes</span></span>

<span data-ttu-id="19dc1-117">Se il valore dell'argomento `starting position` è inferiore a 0 (zero), i caratteri restituiti vengono conteggiati dalla prima posizione nella stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="19dc1-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="19dc1-118">Se il valore dell'argomento `starting position` supera la lunghezza della stringa specificata, viene restituita una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="19dc1-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="19dc1-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="19dc1-119">Example</span></span>

<span data-ttu-id="19dc1-120">`MID ("Sample", 2, 3)` restituisce **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="19dc1-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="19dc1-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="19dc1-121">Additional resources</span></span>

[<span data-ttu-id="19dc1-122">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="19dc1-122">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]