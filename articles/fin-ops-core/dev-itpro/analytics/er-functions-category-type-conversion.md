---
title: Elenco delle funzioni ER nella categoria conversione del tipo
description: Questo argomento fornisce informazioni sulle funzioni di conversione supportate nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: d160c02403bf067ed523fbd634e65c622b522b97
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686077"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="3b845-103">Elenco delle funzioni ER nella categoria conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="3b845-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b845-104">Le funzioni di conversione del tipo creazione di report elettronici (ER) possono essere utilizzate per convertire valori tra tipi.</span><span class="sxs-lookup"><span data-stu-id="3b845-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="3b845-105">Questo argomento fornisce un riepilogo di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="3b845-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="3b845-106">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="3b845-106">Type conversion functions</span></span>

| <span data-ttu-id="3b845-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="3b845-107">Function</span></span> | <span data-ttu-id="3b845-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b845-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="3b845-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="3b845-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="3b845-110">Questa funzione restituisce un valore *Int64* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="3b845-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="3b845-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="3b845-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="3b845-112">Questa funzione restituisce un valore *Int* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="3b845-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="3b845-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="3b845-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="3b845-114">Questa funzione restituisce un valore *Reale* che viene convertito dal valore specificato *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="3b845-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="3b845-115">Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati.</span><span class="sxs-lookup"><span data-stu-id="3b845-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="3b845-116">Valore</span><span class="sxs-lookup"><span data-stu-id="3b845-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="3b845-117">Questa funzione restituisce un valore *Reale* che viene convertito dal valore specificato *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="3b845-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="3b845-118">Funzioni di conversione di tipo nella categoria data e ora</span><span class="sxs-lookup"><span data-stu-id="3b845-118">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="3b845-119">La tabella seguente descrive le funzioni di conversione di tipo nella [categoria data e ora](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="3b845-119">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="3b845-120">Funzione</span><span class="sxs-lookup"><span data-stu-id="3b845-120">Function</span></span> | <span data-ttu-id="3b845-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b845-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="3b845-122">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="3b845-122">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="3b845-123">Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore *Stringa* nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data/ora.</span><span class="sxs-lookup"><span data-stu-id="3b845-123">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="3b845-124">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="3b845-124">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="3b845-125">Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore *Data* a un valore di data/ora in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="3b845-125">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="3b845-126">DateValue</span><span class="sxs-lookup"><span data-stu-id="3b845-126">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="3b845-127">Questa funzione restituisce un valore *Data* che viene convertito da un determinato valore *Stringa* nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data.</span><span class="sxs-lookup"><span data-stu-id="3b845-127">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="3b845-128">Funzioni di conversione di tipo nella categoria elenco</span><span class="sxs-lookup"><span data-stu-id="3b845-128">Type conversion functions in the list category</span></span>

<span data-ttu-id="3b845-129">La tabella seguente descrive le funzioni di conversione di tipo nella [categoria elenco](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="3b845-129">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="3b845-130">Funzione</span><span class="sxs-lookup"><span data-stu-id="3b845-130">Function</span></span> | <span data-ttu-id="3b845-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b845-131">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="3b845-132">Elenco</span><span class="sxs-lookup"><span data-stu-id="3b845-132">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="3b845-133">Questa funzione restituisce un valore *Elenco di record* come un nuovo elenco creato dagli argomenti specificati del tipo *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="3b845-133">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="3b845-134">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="3b845-134">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="3b845-135">Questa funzione restituisce un valore *Elenco di record* creato in base alla struttura di un determinato argomento del tipo *Enumerazione* o *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="3b845-135">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="3b845-136">Dividi</span><span class="sxs-lookup"><span data-stu-id="3b845-136">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="3b845-137">Questa funzione divide il valore *Stringa* in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="3b845-137">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="3b845-138">StringJoin</span><span class="sxs-lookup"><span data-stu-id="3b845-138">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="3b845-139">Restituisce un valore *Stringa* costituito da valori concatenati del campo specificato dal valore *Elenco di record* specificato.</span><span class="sxs-lookup"><span data-stu-id="3b845-139">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="3b845-140">I valori possono essere separati dal delimitatore specificato.</span><span class="sxs-lookup"><span data-stu-id="3b845-140">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="3b845-141">Funzioni di conversione di tipo nella categoria testo</span><span class="sxs-lookup"><span data-stu-id="3b845-141">Type conversion functions in the text category</span></span>

<span data-ttu-id="3b845-142">La tabella seguente descrive le funzioni di conversione di tipo nella [categoria testo](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="3b845-142">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="3b845-143">Funzione</span><span class="sxs-lookup"><span data-stu-id="3b845-143">Function</span></span> | <span data-ttu-id="3b845-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b845-144">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="3b845-145">Char</span><span class="sxs-lookup"><span data-stu-id="3b845-145">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="3b845-146">Questa funzione restituisce un valore *Stringa* che rappresenta un singolo carattere a cui si fa riferimento mediante il numero Unicode specificato.</span><span class="sxs-lookup"><span data-stu-id="3b845-146">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="3b845-147">GuidValue</span><span class="sxs-lookup"><span data-stu-id="3b845-147">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="3b845-148">Questa funzione converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="3b845-148">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="3b845-149">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="3b845-149">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="3b845-150">Questa funzione restituisce un valore *Stringa* che rappresenta il numero specificato nel formato specificato e nelle impostazioni cultura specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="3b845-150">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="3b845-151">QrCode</span><span class="sxs-lookup"><span data-stu-id="3b845-151">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="3b845-152">Questa funzione restituisce un valore *Contenitore* che presenta l'immagine del codice QR (Quick Response Code) per la stringa specificata in formato binario.</span><span class="sxs-lookup"><span data-stu-id="3b845-152">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="3b845-153">Testo</span><span class="sxs-lookup"><span data-stu-id="3b845-153">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="3b845-154">Questa funzione restituisce un valore *Stringa* che rappresenta il numero specificato dopo che è stato convertito in stringa di testo formattata in base alle impostazioni locali del server dell'istanza corrente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b845-154">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="3b845-155">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3b845-155">Additional resources</span></span>

[<span data-ttu-id="3b845-156">Panoramica sui report elettronici</span><span class="sxs-lookup"><span data-stu-id="3b845-156">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="3b845-157">Designer formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="3b845-157">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="3b845-158">Linguaggio della formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="3b845-158">Electronic reporting formula language</span></span>](er-formula-language.md)
