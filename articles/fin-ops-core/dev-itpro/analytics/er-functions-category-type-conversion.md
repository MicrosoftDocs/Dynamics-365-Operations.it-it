---
title: Elenco delle funzioni ER nella categoria conversione del tipo
description: Questo argomento fornisce informazioni sulle funzioni di conversione supportate nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 5613496d3131ccd39b198cac214eb791a6d07355
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561520"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="7df51-103">Elenco delle funzioni ER nella categoria conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="7df51-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7df51-104">Le funzioni di conversione del tipo creazione di report elettronici (ER) possono essere utilizzate per convertire valori tra tipi.</span><span class="sxs-lookup"><span data-stu-id="7df51-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="7df51-105">Questo argomento fornisce un riepilogo di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="7df51-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="7df51-106">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="7df51-106">Type conversion functions</span></span>

| <span data-ttu-id="7df51-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="7df51-107">Function</span></span> | <span data-ttu-id="7df51-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7df51-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="7df51-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="7df51-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="7df51-110">Questa funzione restituisce un valore *Int64* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="7df51-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="7df51-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="7df51-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="7df51-112">Questa funzione restituisce un valore *Int* che rappresenta la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="7df51-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="7df51-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="7df51-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="7df51-114">Questa funzione restituisce un valore *Reale* che viene convertito dal valore specificato *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="7df51-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="7df51-115">Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati.</span><span class="sxs-lookup"><span data-stu-id="7df51-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="7df51-116">Valore</span><span class="sxs-lookup"><span data-stu-id="7df51-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="7df51-117">Questa funzione restituisce un valore *Reale* che viene convertito dal valore specificato *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="7df51-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-container-category"></a><span data-ttu-id="7df51-118">Funzioni di conversione di tipo nella categoria contenitore</span><span class="sxs-lookup"><span data-stu-id="7df51-118">Type conversion functions in the container category</span></span>

<span data-ttu-id="7df51-119">La tabella seguente descrive le funzioni di conversione di tipo nella categoria [contenitore](er-functions-category-container.md).</span><span class="sxs-lookup"><span data-stu-id="7df51-119">The following table describes the type conversion functions in the [container](er-functions-category-container.md) category.</span></span>

| <span data-ttu-id="7df51-120">Funzione</span><span class="sxs-lookup"><span data-stu-id="7df51-120">Function</span></span> | <span data-ttu-id="7df51-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7df51-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="7df51-122">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="7df51-122">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="7df51-123">Questa funzione converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *Contenitore*.</span><span class="sxs-lookup"><span data-stu-id="7df51-123">This function converts the specified input of the *String* type to a data item of the *Container* type.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="7df51-124">Funzioni di conversione di tipo nella categoria data e ora</span><span class="sxs-lookup"><span data-stu-id="7df51-124">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="7df51-125">La tabella seguente descrive le funzioni di conversione di tipo nella [categoria data e ora](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="7df51-125">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="7df51-126">Funzione</span><span class="sxs-lookup"><span data-stu-id="7df51-126">Function</span></span> | <span data-ttu-id="7df51-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7df51-127">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="7df51-128">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="7df51-128">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="7df51-129">Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore *Stringa* nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data/ora.</span><span class="sxs-lookup"><span data-stu-id="7df51-129">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="7df51-130">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="7df51-130">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="7df51-131">Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore *Data* a un valore di data/ora in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="7df51-131">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="7df51-132">DateValue</span><span class="sxs-lookup"><span data-stu-id="7df51-132">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="7df51-133">Questa funzione restituisce un valore *Data* che viene convertito da un determinato valore *Stringa* nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data.</span><span class="sxs-lookup"><span data-stu-id="7df51-133">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="7df51-134">Funzioni di conversione di tipo nella categoria elenco</span><span class="sxs-lookup"><span data-stu-id="7df51-134">Type conversion functions in the list category</span></span>

<span data-ttu-id="7df51-135">La tabella seguente descrive le funzioni di conversione di tipo nella [categoria elenco](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="7df51-135">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="7df51-136">Funzione</span><span class="sxs-lookup"><span data-stu-id="7df51-136">Function</span></span> | <span data-ttu-id="7df51-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7df51-137">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="7df51-138">Elenco</span><span class="sxs-lookup"><span data-stu-id="7df51-138">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="7df51-139">Questa funzione restituisce un valore *Elenco di record* come un nuovo elenco creato dagli argomenti specificati del tipo *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="7df51-139">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="7df51-140">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="7df51-140">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="7df51-141">Questa funzione restituisce un valore *Elenco di record* creato in base alla struttura di un determinato argomento del tipo *Enumerazione* o *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="7df51-141">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="7df51-142">Dividi</span><span class="sxs-lookup"><span data-stu-id="7df51-142">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="7df51-143">Questa funzione divide il valore *Stringa* in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="7df51-143">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="7df51-144">StringJoin</span><span class="sxs-lookup"><span data-stu-id="7df51-144">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="7df51-145">Restituisce un valore *Stringa* costituito da valori concatenati del campo specificato dal valore *Elenco di record* specificato.</span><span class="sxs-lookup"><span data-stu-id="7df51-145">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="7df51-146">I valori possono essere separati dal delimitatore specificato.</span><span class="sxs-lookup"><span data-stu-id="7df51-146">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="7df51-147">Funzioni di conversione di tipo nella categoria testo</span><span class="sxs-lookup"><span data-stu-id="7df51-147">Type conversion functions in the text category</span></span>

<span data-ttu-id="7df51-148">La tabella seguente descrive le funzioni di conversione di tipo nella [categoria testo](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="7df51-148">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="7df51-149">Funzione</span><span class="sxs-lookup"><span data-stu-id="7df51-149">Function</span></span> | <span data-ttu-id="7df51-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7df51-150">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="7df51-151">Char</span><span class="sxs-lookup"><span data-stu-id="7df51-151">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="7df51-152">Questa funzione restituisce un valore *Stringa* che rappresenta un singolo carattere a cui si fa riferimento mediante il numero Unicode specificato.</span><span class="sxs-lookup"><span data-stu-id="7df51-152">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="7df51-153">GuidValue</span><span class="sxs-lookup"><span data-stu-id="7df51-153">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="7df51-154">Questa funzione converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="7df51-154">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="7df51-155">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="7df51-155">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="7df51-156">Questa funzione restituisce un valore *Stringa* che rappresenta il numero specificato nel formato specificato e nelle impostazioni cultura specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="7df51-156">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="7df51-157">QrCode</span><span class="sxs-lookup"><span data-stu-id="7df51-157">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="7df51-158">Questa funzione restituisce un valore *Contenitore* che presenta l'immagine del codice QR (Quick Response Code) per la stringa specificata in formato binario.</span><span class="sxs-lookup"><span data-stu-id="7df51-158">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="7df51-159">Testo</span><span class="sxs-lookup"><span data-stu-id="7df51-159">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="7df51-160">Questa funzione restituisce un valore *Stringa* che rappresenta il numero specificato dopo che è stato convertito in stringa di testo formattata in base alle impostazioni locali del server dell'istanza corrente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7df51-160">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="7df51-161">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7df51-161">Additional resources</span></span>

[<span data-ttu-id="7df51-162">Panoramica sui report elettronici</span><span class="sxs-lookup"><span data-stu-id="7df51-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="7df51-163">Designer formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="7df51-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="7df51-164">Linguaggio della formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="7df51-164">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]