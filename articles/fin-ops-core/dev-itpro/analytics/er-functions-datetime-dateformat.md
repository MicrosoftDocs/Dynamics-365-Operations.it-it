---
title: Funzione ER DATEFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATEFORMAT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 1b3a0a2608328b233004034f7ab2ccfa833c17e3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890912"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="510d4-103">Funzione ER DATEFORMAT</span><span class="sxs-lookup"><span data-stu-id="510d4-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="510d4-104">La funzione `DATEFORMAT` restituisce un valore *Stringa* che presenta un valore specifico di data come testo nel formato specificato e nelle impostazioni [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="510d4-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="510d4-105">Per informazioni sui formati supportati, vedere [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="510d4-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="510d4-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="510d4-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="510d4-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="510d4-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="510d4-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="510d4-108">Arguments</span></span>

<span data-ttu-id="510d4-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="510d4-109">`date`: *Date*</span></span>

<span data-ttu-id="510d4-110">Un valore di data che rappresenta la data da formattare.</span><span class="sxs-lookup"><span data-stu-id="510d4-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="510d4-111">`format`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="510d4-111">`format`: *String*</span></span>

<span data-ttu-id="510d4-112">Formato della stringa di output.</span><span class="sxs-lookup"><span data-stu-id="510d4-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="510d4-113">La stringa di formato fa distinzione tra maiuscole e minuscole quando si utilizza un formato standard o un formato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="510d4-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="510d4-114">Ad esempio, l'identificatore di formato "d" [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) restituisce la data utilizzando il modello di data breve, mentre l'identificatore di formato "D" standard restituisce la data utilizzando il modello di data lunga.</span><span class="sxs-lookup"><span data-stu-id="510d4-114">For example, the [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="510d4-115">Inoltre, l'identificatore di formato "M" [personalizzato](/dotnet/standard/base-types/custom-date-and-time-format-strings) restituisce il mese da 1 a 12, mentre l'identificatore di formato "m" personalizzato restituisce i minuti da 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="510d4-115">Additionally, the [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="510d4-116">`culture`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="510d4-116">`culture`: *String*</span></span>

<span data-ttu-id="510d4-117">La cultura da utilizzare per la formattazione.</span><span class="sxs-lookup"><span data-stu-id="510d4-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="510d4-118">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="510d4-118">Return values</span></span>

<span data-ttu-id="510d4-119">*String*</span><span class="sxs-lookup"><span data-stu-id="510d4-119">*String*</span></span>

<span data-ttu-id="510d4-120">Il valore di stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="510d4-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="510d4-121">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="510d4-121">Usage notes</span></span>

<span data-ttu-id="510d4-122">Se la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="510d4-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="510d4-123">Ad esempio, se la funzione `DATEFORMAT` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca.</span><span class="sxs-lookup"><span data-stu-id="510d4-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="510d4-124">Il valore `culture` predefinito è **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="510d4-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="510d4-125">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="510d4-125">Example 1</span></span>

<span data-ttu-id="510d4-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come stringa **"24-12-2015"**, in base al formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="510d4-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="510d4-127">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="510d4-127">Example 2</span></span>

<span data-ttu-id="510d4-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="510d4-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="510d4-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="510d4-129">Additional resources</span></span>

[<span data-ttu-id="510d4-130">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="510d4-130">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]