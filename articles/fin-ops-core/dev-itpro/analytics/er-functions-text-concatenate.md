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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a21140e5636ebd96eca4be90308c915e77510e1
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743905"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="da1bc-103">Funzione ER CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="da1bc-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da1bc-104">La funzione `CONCATENATE` restituisce tutte le stringhe di testo specificate come valore *Stringa* dopo che sono stati uniti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="da1bc-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="da1bc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da1bc-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="da1bc-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="da1bc-106">Arguments</span></span>

<span data-ttu-id="da1bc-107">`text 1`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="da1bc-107">`text 1`: *String*</span></span>

<span data-ttu-id="da1bc-108">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="da1bc-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="da1bc-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="da1bc-109">This argument is required.</span></span>

<span data-ttu-id="da1bc-110">`text N`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="da1bc-110">`text N`: *String*</span></span>

<span data-ttu-id="da1bc-111">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="da1bc-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="da1bc-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="da1bc-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="da1bc-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="da1bc-113">Return values</span></span>

<span data-ttu-id="da1bc-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="da1bc-114">*String*</span></span>

<span data-ttu-id="da1bc-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="da1bc-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="da1bc-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="da1bc-116">Example</span></span>

<span data-ttu-id="da1bc-117">`CONCATENATE ("abc", "def")` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="da1bc-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="da1bc-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="da1bc-118">Usage notes</span></span>

<span data-ttu-id="da1bc-119">Anche l'espressione `"abc" & "def"` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="da1bc-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da1bc-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="da1bc-120">Additional resources</span></span>

[<span data-ttu-id="da1bc-121">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="da1bc-121">Text functions</span></span>](er-functions-category-text.md)
