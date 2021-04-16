---
title: Funzione ER CONCATENATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CONCATENATE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: f1a47a05127412588f4628cb425eab0379493c3c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746484"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="1189d-103">Funzione ER CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="1189d-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1189d-104">La funzione `CONCATENATE` restituisce tutte le stringhe di testo specificate come valore *Stringa* dopo che sono stati uniti in una stringa.</span><span class="sxs-lookup"><span data-stu-id="1189d-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="1189d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1189d-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="1189d-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1189d-106">Arguments</span></span>

<span data-ttu-id="1189d-107">`text 1`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="1189d-107">`text 1`: *String*</span></span>

<span data-ttu-id="1189d-108">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="1189d-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="1189d-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1189d-109">This argument is required.</span></span>

<span data-ttu-id="1189d-110">`text N`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="1189d-110">`text N`: *String*</span></span>

<span data-ttu-id="1189d-111">Un riferimento a un'origine dati del tipo dati *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="1189d-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="1189d-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="1189d-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="1189d-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="1189d-113">Return values</span></span>

<span data-ttu-id="1189d-114">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="1189d-114">*String*</span></span>

<span data-ttu-id="1189d-115">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="1189d-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="1189d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="1189d-116">Example</span></span>

<span data-ttu-id="1189d-117">`CONCATENATE ("abc", "def")` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="1189d-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1189d-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="1189d-118">Usage notes</span></span>

<span data-ttu-id="1189d-119">Anche l'espressione `"abc" & "def"` restituisce **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="1189d-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1189d-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1189d-120">Additional resources</span></span>

[<span data-ttu-id="1189d-121">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="1189d-121">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]