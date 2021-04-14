---
title: Elenco delle funzioni ER nella categoria data e ora
description: Questo argomento fornisce informazioni sulle funzioni di data e ora supportate nella creazione di report elettronici (ER).
author: NickSelin
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
ms.openlocfilehash: 2dd8524c9cd368f0fe64347e3212b419bb0902b4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744563"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="fb45a-103">Elenco delle funzioni ER nella categoria data e ora</span><span class="sxs-lookup"><span data-stu-id="fb45a-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb45a-104">Le funzioni di data e ora della creazione di report elettronici (ER) possono essere utilizzate per estrarre informazioni dai valori di data e ora e per eseguire operazioni su di essi.</span><span class="sxs-lookup"><span data-stu-id="fb45a-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="fb45a-105">Questo argomento fornisce un riepilogo di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="fb45a-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="fb45a-106">Elenco delle funzioni supportate</span><span class="sxs-lookup"><span data-stu-id="fb45a-106">List of supported functions</span></span>

| <span data-ttu-id="fb45a-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="fb45a-107">Function</span></span> | <span data-ttu-id="fb45a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb45a-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="fb45a-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="fb45a-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="fb45a-110">Questa funzione restituisce un valore *DateTime* che è il numero specificato di giorni prima o dopo una data di inizio specificata.</span><span class="sxs-lookup"><span data-stu-id="fb45a-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="fb45a-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="fb45a-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="fb45a-112">Questa funzione restituisce un valore *Stringa* che presenta un valore specifico di data come testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="fb45a-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="fb45a-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="fb45a-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="fb45a-114">Questa funzione restituisce un valore *Stringa* che presenta un valore specifico di data/ora come testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="fb45a-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="fb45a-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="fb45a-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="fb45a-116">Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data/ora.</span><span class="sxs-lookup"><span data-stu-id="fb45a-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="fb45a-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="fb45a-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="fb45a-118">Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore di data a un valore di data / ora in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="fb45a-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="fb45a-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="fb45a-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="fb45a-120">Questa funzione restituisce un valore *Data* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data.</span><span class="sxs-lookup"><span data-stu-id="fb45a-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="fb45a-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="fb45a-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="fb45a-122">Restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra l'1 gennaio e la data specificata.</span><span class="sxs-lookup"><span data-stu-id="fb45a-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="fb45a-123">Giorni</span><span class="sxs-lookup"><span data-stu-id="fb45a-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="fb45a-124">Restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra una data specificata e una seconda data specificata.</span><span class="sxs-lookup"><span data-stu-id="fb45a-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="fb45a-125">Now</span><span class="sxs-lookup"><span data-stu-id="fb45a-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="fb45a-126">Questa funzione restituisce un valore *DateTime* che rappresenta la data e l'ora correnti del server delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="fb45a-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="fb45a-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="fb45a-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="fb45a-128">Questa funzione restituisce un valore *Data* che rappresenta la data **null** (1 gennaio 1900).</span><span class="sxs-lookup"><span data-stu-id="fb45a-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="fb45a-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="fb45a-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="fb45a-130">Questa funzione restituisce un valore *DateTime* che rappresenta il valore **null** data/ora (1 gennaio 1900) in Coordinated Universal Time.</span><span class="sxs-lookup"><span data-stu-id="fb45a-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="fb45a-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="fb45a-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="fb45a-132">Questa funzione restituisce un valore *DateTime* che rappresenta la data e l'ora correnti della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fb45a-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="fb45a-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="fb45a-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="fb45a-134">Questa funzione restituisce un valore *Data* che rappresenta la data corrente della sessione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fb45a-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="fb45a-135">Oggi</span><span class="sxs-lookup"><span data-stu-id="fb45a-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="fb45a-136">Questa funzione restituisce un valore *Data* che rappresenta la data corrente del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="fb45a-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="fb45a-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb45a-137">Additional resources</span></span>

[<span data-ttu-id="fb45a-138">Panoramica sui report elettronici</span><span class="sxs-lookup"><span data-stu-id="fb45a-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="fb45a-139">Designer formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="fb45a-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="fb45a-140">Linguaggio della formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="fb45a-140">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]