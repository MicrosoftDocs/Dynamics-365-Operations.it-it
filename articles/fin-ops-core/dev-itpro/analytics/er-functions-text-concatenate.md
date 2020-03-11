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
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041173"
---
# <span data-ttu-id="d3b58-103"><a name="CONCATENATE">Funzione ER CONCATENATE</a></span><span class="sxs-lookup"><span data-stu-id="d3b58-103"><a name="CONCATENATE">CONCATENATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3b58-104">La funzione `CONCATENATE` restituisce tutte le stringhe di testo specificate come valore *Stringa* dopo che sono stati uniti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="d3b58-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3b58-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3b58-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="d3b58-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d3b58-106">Arguments</span></span>

<span data-ttu-id="d3b58-107">`text 1`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d3b58-107">`text 1`: *String*</span></span>

<span data-ttu-id="d3b58-108">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="d3b58-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="d3b58-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3b58-109">This argument is required.</span></span>

<span data-ttu-id="d3b58-110">`text N`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="d3b58-110">`text N`: *String*</span></span>

<span data-ttu-id="d3b58-111">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="d3b58-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="d3b58-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d3b58-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="d3b58-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d3b58-113">Return values</span></span>

<span data-ttu-id="d3b58-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="d3b58-114">*String*</span></span>

<span data-ttu-id="d3b58-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="d3b58-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d3b58-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3b58-116">Example</span></span>

<span data-ttu-id="d3b58-117">`CONCATENATE ("abc", "def")` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d3b58-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d3b58-118">Usage notes</span></span>

<span data-ttu-id="d3b58-119">Anche l'espressione `"abc" & "def"` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3b58-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d3b58-120">Additional resources</span></span>

[<span data-ttu-id="d3b58-121">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="d3b58-121">Text functions</span></span>](er-functions-category-text.md)
