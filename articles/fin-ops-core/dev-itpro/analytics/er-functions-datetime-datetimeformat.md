---
title: Funzione ER DATETIMEFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATETIMEFORMAT della creazione di report elettronici (ER).
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
ms.openlocfilehash: 9e550b0c7634c7aac3f8c597a1c1eac3f8125e3b
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070715"
---
# <span data-ttu-id="b92ed-103"><a name="DATETIMEFORMAT">Funzione ER DATETIMEFORMAT</a></span><span class="sxs-lookup"><span data-stu-id="b92ed-103"><a name="DATETIMEFORMAT">DATETIMEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b92ed-104">La funzione `DATETIMEFORMAT` restituisce un valore *Stringa* che presenta un valore specifico di data/ora come testo nel formato specificato e nelle impostazioni [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente.</span><span class="sxs-lookup"><span data-stu-id="b92ed-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="b92ed-105">Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="b92ed-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b92ed-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="b92ed-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="b92ed-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="b92ed-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="b92ed-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b92ed-108">Arguments</span></span>

<span data-ttu-id="b92ed-109">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="b92ed-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="b92ed-110">Un valore di data/ora che rappresenta la data e l'ora da formattare.</span><span class="sxs-lookup"><span data-stu-id="b92ed-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="b92ed-111">`format`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="b92ed-111">`format`: *String*</span></span>

<span data-ttu-id="b92ed-112">Formato della stringa di output.</span><span class="sxs-lookup"><span data-stu-id="b92ed-112">The format of the output string.</span></span>

<span data-ttu-id="b92ed-113">`culture`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="b92ed-113">`culture`: *String*</span></span>

<span data-ttu-id="b92ed-114">La cultura da utilizzare per la formattazione.</span><span class="sxs-lookup"><span data-stu-id="b92ed-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="b92ed-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b92ed-115">Return values</span></span>

<span data-ttu-id="b92ed-116">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="b92ed-116">*String*</span></span>

<span data-ttu-id="b92ed-117">Il valore di stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="b92ed-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b92ed-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="b92ed-118">Usage notes</span></span>

<span data-ttu-id="b92ed-119">Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b92ed-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="b92ed-120">Ad esempio, se la funzione `DATETIMEFORMAT` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca.</span><span class="sxs-lookup"><span data-stu-id="b92ed-120">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="b92ed-121">Il valore `culture` predefinito è **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="b92ed-121">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="b92ed-122">Quando la funzione `DATETIMEFORMAT` converte un determinato valore data/ora, considera l'impostazione del fuso orario dell'utente dell'applicazione che esegue il formato ER da cui viene richiamata la funzione nel contesto.</span><span class="sxs-lookup"><span data-stu-id="b92ed-122">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="b92ed-123">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b92ed-123">Example 1</span></span>

<span data-ttu-id="b92ed-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come **"24-12-2015"**, in base al formato personalizzato specificato.</span><span class="sxs-lookup"><span data-stu-id="b92ed-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="b92ed-125">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="b92ed-125">Example 2</span></span>

<span data-ttu-id="b92ed-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` restituisce la data/ora della sessione dell'applicazione corrente, il 24 dicembre 2015, come **"24.12.2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.</span><span class="sxs-lookup"><span data-stu-id="b92ed-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="b92ed-127">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="b92ed-127">Example 3</span></span>

<span data-ttu-id="b92ed-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` restituisce il valore della stringa **2019-11-12T08:00:00.0000000-08:00** quando viene richiamato durante un processo avviato da un utente dell'applicazione che ha il valore del fuso orario **(GMT-08: 00) Pacific Time (Stati Uniti e Canada)** nella sezione **Preferenze di lingua e paese**.</span><span class="sxs-lookup"><span data-stu-id="b92ed-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b92ed-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b92ed-129">Additional resources</span></span>

[<span data-ttu-id="b92ed-130">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="b92ed-130">Date and time functions</span></span>](er-functions-category-datetime.md)
