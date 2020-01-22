---
title: Funzione ER DATEFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATEFORMAT della creazione di report elettronici (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1453be0c93764f9f0364206822a9e3899061a58
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917582"
---
# <span data-ttu-id="69458-103"><a name="DATEFORMAT">Funzione ER DATEFORMAT</a></span><span class="sxs-lookup"><span data-stu-id="69458-103"><a name="DATEFORMAT">DATEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69458-104">La funzione `DATEFORMAT` restituisce un valore *Stringa* che presenta un valore specifico di data come testo nel formato specificato e nelle impostazioni [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="69458-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="69458-105">Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="69458-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="69458-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="69458-106">Syntax 1</span></span>

```
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="69458-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="69458-107">Syntax 2</span></span>

```
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="69458-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="69458-108">Arguments</span></span>

<span data-ttu-id="69458-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="69458-109">`date`: *Date*</span></span>

<span data-ttu-id="69458-110">Un valore di data che rappresenta la data da formattare.</span><span class="sxs-lookup"><span data-stu-id="69458-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="69458-111">`format`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="69458-111">`format`: *String*</span></span>

<span data-ttu-id="69458-112">Formato della stringa di output.</span><span class="sxs-lookup"><span data-stu-id="69458-112">The format of the output string.</span></span>

<span data-ttu-id="69458-113">`culture`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="69458-113">`culture`: *String*</span></span>

<span data-ttu-id="69458-114">La cultura da utilizzare per la formattazione.</span><span class="sxs-lookup"><span data-stu-id="69458-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="69458-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="69458-115">Return values</span></span>

<span data-ttu-id="69458-116">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="69458-116">*String*</span></span>

<span data-ttu-id="69458-117">Il valore di stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="69458-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="69458-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="69458-118">Usage notes</span></span>

<span data-ttu-id="69458-119">Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="69458-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="69458-120">Ad esempio, se la funzione `DATEFORMAT` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca.</span><span class="sxs-lookup"><span data-stu-id="69458-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="69458-121">Il valore `culture` predefinito è **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="69458-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="69458-122">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="69458-122">Example 1</span></span>

<span data-ttu-id="69458-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come stringa **"24-12-2015"**, in base al formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="69458-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="69458-124">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="69458-124">Example 2</span></span>

<span data-ttu-id="69458-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="69458-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69458-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="69458-126">Additional resources</span></span>

[<span data-ttu-id="69458-127">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="69458-127">Date and time functions</span></span>](er-functions-category-datetime.md)
