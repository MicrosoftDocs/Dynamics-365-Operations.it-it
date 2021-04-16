---
title: Funzione ER DATEVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATEVALUE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: d760c3f874bfebad11b9497b136cb67df4e9ea61
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746941"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="2928f-103">Funzione ER DATEVALUE</span><span class="sxs-lookup"><span data-stu-id="2928f-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2928f-104">La funzione `DATEVALUE` restituisce un valore *Data* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente in un valore data.</span><span class="sxs-lookup"><span data-stu-id="2928f-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="2928f-105">Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="2928f-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="2928f-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="2928f-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="2928f-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="2928f-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="2928f-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2928f-108">Arguments</span></span>

<span data-ttu-id="2928f-109">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="2928f-109">`text`: *String*</span></span>

<span data-ttu-id="2928f-110">Testo che rappresenta il valore da formattare.</span><span class="sxs-lookup"><span data-stu-id="2928f-110">Text that represents the value to format.</span></span>

<span data-ttu-id="2928f-111">`format`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="2928f-111">`format`: *String*</span></span>

<span data-ttu-id="2928f-112">Formato della testo fornito.</span><span class="sxs-lookup"><span data-stu-id="2928f-112">The format of the given text.</span></span>

<span data-ttu-id="2928f-113">`culture`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="2928f-113">`culture`: *String*</span></span>

<span data-ttu-id="2928f-114">La cultura utilizzata per la formattazione del testo fornito.</span><span class="sxs-lookup"><span data-stu-id="2928f-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="2928f-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2928f-115">Return values</span></span>

<span data-ttu-id="2928f-116">*Data*</span><span class="sxs-lookup"><span data-stu-id="2928f-116">*Date*</span></span>

<span data-ttu-id="2928f-117">Il valore di data risultante.</span><span class="sxs-lookup"><span data-stu-id="2928f-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2928f-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="2928f-118">Usage notes</span></span>

<span data-ttu-id="2928f-119">Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2928f-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="2928f-120">Ad esempio, se la funzione `DATEVALUE` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca.</span><span class="sxs-lookup"><span data-stu-id="2928f-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="2928f-121">Il valore `culture` predefinito è **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="2928f-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="2928f-122">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="2928f-122">Example 1</span></span>

<span data-ttu-id="2928f-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` restituisce il valore di data **21 dicembre 2016**, basato sul formato personalizzato specificato e la cultura **EN-US** dell'applicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2928f-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="2928f-124">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="2928f-124">Example 2</span></span>

<span data-ttu-id="2928f-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` restituisce il valore della data **21 gennaio 2016**, in base al formato e alla cultura personalizzati specificati.</span><span class="sxs-lookup"><span data-stu-id="2928f-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="2928f-126">Tuttavia, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` genera un'eccezione per informare l'utente che la stringa specificata non viene riconosciuta come data valida per la cultura specificata.</span><span class="sxs-lookup"><span data-stu-id="2928f-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2928f-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2928f-127">Additional resources</span></span>

[<span data-ttu-id="2928f-128">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="2928f-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]