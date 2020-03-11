---
title: Funzione ER PADLEFT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione PADLEFT della creazione di report elettronici (ER).
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
ms.openlocfilehash: d11e2d8b46614085156228ab1001d1f9340a05b0
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040965"
---
# <span data-ttu-id="dfd53-103"><a name="PADLEFT">Funzione ER PADLEFT</a></span><span class="sxs-lookup"><span data-stu-id="dfd53-103"><a name="PADLEFT">PADLEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfd53-104">La funzione `PADLEFT` restituisce un valore *Stringa* della lunghezza specificata in cui l'inizio della stringa specificata viene riempita con i caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="dfd53-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="dfd53-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfd53-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="dfd53-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="dfd53-106">Arguments</span></span>

<span data-ttu-id="dfd53-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="dfd53-107">`text`: *String*</span></span>

<span data-ttu-id="dfd53-108">Un valore *Stringa* che rappresenta il testo originale.</span><span class="sxs-lookup"><span data-stu-id="dfd53-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="dfd53-109">`length`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="dfd53-109">`length`: *Integer*</span></span>

<span data-ttu-id="dfd53-110">Un valore *Intero* che rappresenta il numero finale di caratteri nella stringa riempita.</span><span class="sxs-lookup"><span data-stu-id="dfd53-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="dfd53-111">`padding chars`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="dfd53-111">`padding chars`: *String*</span></span>

<span data-ttu-id="dfd53-112">I caratteri da usare per il riempimento.</span><span class="sxs-lookup"><span data-stu-id="dfd53-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="dfd53-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="dfd53-113">Return values</span></span>

<span data-ttu-id="dfd53-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="dfd53-114">*String*</span></span>

<span data-ttu-id="dfd53-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="dfd53-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="dfd53-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfd53-116">Example</span></span>

<span data-ttu-id="dfd53-117">`PADLEFT ("1234", 10, "`&nbsp;`")` restituisce la stringa di testo **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="dfd53-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dfd53-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dfd53-118">Additional resources</span></span>

[<span data-ttu-id="dfd53-119">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="dfd53-119">Text functions</span></span>](er-functions-category-text.md)
