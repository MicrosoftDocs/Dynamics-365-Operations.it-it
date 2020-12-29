---
title: Funzione ER CONCATENATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CONCATENATE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 903429994ae5618b597aa0ab0991e9f6783a96ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687940"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="9e72e-103">Funzione ER CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="9e72e-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e72e-104">La funzione `CONCATENATE` restituisce tutte le stringhe di testo specificate come valore *Stringa* dopo che sono stati uniti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="9e72e-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e72e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e72e-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="9e72e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9e72e-106">Arguments</span></span>

<span data-ttu-id="9e72e-107">`text 1`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="9e72e-107">`text 1`: *String*</span></span>

<span data-ttu-id="9e72e-108">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="9e72e-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="9e72e-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9e72e-109">This argument is required.</span></span>

<span data-ttu-id="9e72e-110">`text N`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="9e72e-110">`text N`: *String*</span></span>

<span data-ttu-id="9e72e-111">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="9e72e-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="9e72e-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="9e72e-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="9e72e-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="9e72e-113">Return values</span></span>

<span data-ttu-id="9e72e-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="9e72e-114">*String*</span></span>

<span data-ttu-id="9e72e-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="9e72e-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9e72e-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e72e-116">Example</span></span>

<span data-ttu-id="9e72e-117">`CONCATENATE ("abc", "def")` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="9e72e-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9e72e-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="9e72e-118">Usage notes</span></span>

<span data-ttu-id="9e72e-119">Anche l'espressione `"abc" & "def"` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="9e72e-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e72e-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9e72e-120">Additional resources</span></span>

[<span data-ttu-id="9e72e-121">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="9e72e-121">Text functions</span></span>](er-functions-category-text.md)
