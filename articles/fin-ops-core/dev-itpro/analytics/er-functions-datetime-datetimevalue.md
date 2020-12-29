---
title: Funzione ER DATETIMEVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATETIMEVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 30879796b483752a578e516d8afd75f5a690cabc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684909"
---
# <a name="datetimevalue-er-function"></a><span data-ttu-id="30b54-103">Funzione ER DATETIMEVALUE</span><span class="sxs-lookup"><span data-stu-id="30b54-103">DATETIMEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30b54-104">La funzione `DATETIMEVALUE` restituisce un valore *DateTime* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente in un valore data/ora.</span><span class="sxs-lookup"><span data-stu-id="30b54-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="30b54-105">Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="30b54-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="30b54-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="30b54-106">Syntax 1</span></span>

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="30b54-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="30b54-107">Syntax 2</span></span>

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="30b54-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="30b54-108">Arguments</span></span>

<span data-ttu-id="30b54-109">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="30b54-109">`text`: *String*</span></span>

<span data-ttu-id="30b54-110">Testo che rappresenta il valore da formattare.</span><span class="sxs-lookup"><span data-stu-id="30b54-110">Text that represents the value to format.</span></span>

<span data-ttu-id="30b54-111">`format`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="30b54-111">`format`: *String*</span></span>

<span data-ttu-id="30b54-112">Formato della testo fornito.</span><span class="sxs-lookup"><span data-stu-id="30b54-112">The format of the given text.</span></span>

<span data-ttu-id="30b54-113">`culture`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="30b54-113">`culture`: *String*</span></span>

<span data-ttu-id="30b54-114">La cultura utilizzata per la formattazione del testo fornito.</span><span class="sxs-lookup"><span data-stu-id="30b54-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="30b54-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="30b54-115">Return values</span></span>

<span data-ttu-id="30b54-116">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="30b54-116">*DateTime*</span></span>

<span data-ttu-id="30b54-117">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="30b54-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="30b54-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="30b54-118">Usage notes</span></span>

<span data-ttu-id="30b54-119">Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="30b54-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="30b54-120">Ad esempio, se la funzione `DATETIMEVALUE` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca.</span><span class="sxs-lookup"><span data-stu-id="30b54-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="30b54-121">Il valore `culture` predefinito è **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="30b54-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="30b54-122">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="30b54-122">Example 1</span></span>

<span data-ttu-id="30b54-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` restituisce **2:55:00 del 21 dicembre 2016**, basato sul formato personalizzato specificato e sulla cultura **EN-US** dell'applicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30b54-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="30b54-124">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="30b54-124">Example 2</span></span>

<span data-ttu-id="30b54-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` restituisce **2:55:00 del 21 dicembre 2016**, in base al formato e alla cultura personalizzati specificati.</span><span class="sxs-lookup"><span data-stu-id="30b54-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="30b54-126">Tuttavia, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` genera un'eccezione per informare l'utente che la stringa specificata non viene riconosciuta come data/ora valida per la cultura specificata.</span><span class="sxs-lookup"><span data-stu-id="30b54-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30b54-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="30b54-127">Additional resources</span></span>

[<span data-ttu-id="30b54-128">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="30b54-128">Date and time functions</span></span>](er-functions-category-datetime.md)
