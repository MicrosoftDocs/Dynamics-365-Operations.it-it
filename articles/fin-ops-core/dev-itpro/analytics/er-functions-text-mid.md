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
ms.openlocfilehash: e178b01740954b46e2afbd2a2be6200a652a18c0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915604"
---
# <span data-ttu-id="2bf52-103"><a name="MID">Funzione ER MID</a></span><span class="sxs-lookup"><span data-stu-id="2bf52-103"><a name="MID">MID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bf52-104">La funzione `MID` restituisce un valore *Stringa* che presenta il numero specificato di caratteri della stringa specificata all'inizio della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="2bf52-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="2bf52-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bf52-105">Syntax</span></span>

```
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="2bf52-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2bf52-106">Arguments</span></span>

<span data-ttu-id="2bf52-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="2bf52-107">`text`: *String*</span></span>

<span data-ttu-id="2bf52-108">Un valore *Stringa* che specifica il testo da cui restituire i caratteri.</span><span class="sxs-lookup"><span data-stu-id="2bf52-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="2bf52-109">`starting position`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="2bf52-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="2bf52-110">Un valore *Intero* che specifica la posizione del primo carattere che deve essere restituito dal testo specificato.</span><span class="sxs-lookup"><span data-stu-id="2bf52-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="2bf52-111">`number of characters`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="2bf52-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="2bf52-112">Un valore *Intero* che specifica il numero di caratteri che deve essere restituito, iniziando dalla posizione di inizio specificata.</span><span class="sxs-lookup"><span data-stu-id="2bf52-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="2bf52-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2bf52-113">Return values</span></span>

<span data-ttu-id="2bf52-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="2bf52-114">*String*</span></span>

<span data-ttu-id="2bf52-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="2bf52-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2bf52-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="2bf52-116">Usage notes</span></span>

<span data-ttu-id="2bf52-117">Se il valore dell'argomento `starting position` è inferiore a 0 (zero), i caratteri restituiti vengono conteggiati dalla prima posizione nella stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="2bf52-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="2bf52-118">Se il valore dell'argomento `starting position` supera la lunghezza della stringa specificata, viene restituita una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="2bf52-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="2bf52-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="2bf52-119">Example</span></span>

<span data-ttu-id="2bf52-120">`MID ("Sample", 2, 3)` restituisce **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="2bf52-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2bf52-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2bf52-121">Additional resources</span></span>

[<span data-ttu-id="2bf52-122">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="2bf52-122">Text functions</span></span>](er-functions-category-text.md)
