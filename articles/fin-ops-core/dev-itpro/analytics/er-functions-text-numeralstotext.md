---
title: Funzione ER NUMERALSTOTEXT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMERALSTOTEXT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: e26890a0d99e0df631a3b3350d284e63aaed8e09
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746149"
---
# <a name="numeralstotext-er-function"></a><span data-ttu-id="76743-103">Funzione ER NUMERALSTOTEXT</span><span class="sxs-lookup"><span data-stu-id="76743-103">NUMERALSTOTEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76743-104">La funzione `NUMERALSTOTEXT` restituisce il numero specificato come un valore *Stringa* dopo che è stato ovvero convertito in stringhe di testo nella lingua specificata.</span><span class="sxs-lookup"><span data-stu-id="76743-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="76743-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76743-105">Syntax</span></span>

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="76743-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="76743-106">Arguments</span></span>

<span data-ttu-id="76743-107">`number`: *Intero* o *Reale*</span><span class="sxs-lookup"><span data-stu-id="76743-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="76743-108">Un valore numerico che specifica il numero che deve essere convertito.</span><span class="sxs-lookup"><span data-stu-id="76743-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="76743-109">`language`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="76743-109">`language`: *String*</span></span>

<span data-ttu-id="76743-110">Un valore *Stringa* che rappresenta il codice della lingua.</span><span class="sxs-lookup"><span data-stu-id="76743-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="76743-111">`currency`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="76743-111">`currency`: *String*</span></span>

<span data-ttu-id="76743-112">Un valore *Stringa* che rappresenta il codice della valuta.</span><span class="sxs-lookup"><span data-stu-id="76743-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="76743-113">`print currency name flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="76743-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="76743-114">Un valore *Booleano* che indica se un nome di valuta deve essere aggiunto al testo convertito.</span><span class="sxs-lookup"><span data-stu-id="76743-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="76743-115">`decimal points`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="76743-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="76743-116">Un valore *Intero* che indica il numero di posizioni decimali che dovrebbe avere il testo convertito.</span><span class="sxs-lookup"><span data-stu-id="76743-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="76743-117">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="76743-117">Return values</span></span>

<span data-ttu-id="76743-118">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="76743-118">*String*</span></span>

<span data-ttu-id="76743-119">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="76743-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="76743-120">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="76743-120">Usage notes</span></span>

<span data-ttu-id="76743-121">Il codice lingua è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="76743-121">The language code is optional.</span></span> <span data-ttu-id="76743-122">Se viene definito come stringa vuota, viene utilizzato il codice lingua per il contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="76743-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="76743-123">Il codice predefinito della lingua è **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="76743-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="76743-124">Il codice della lingua per il contesto corrente è definito in un elemento **Cartella** o **File** del formato creazione di report elettronici (ER) in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="76743-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="76743-125">Il codice valuta è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="76743-125">The currency code is optional.</span></span> <span data-ttu-id="76743-126">Se viene definito come stringa vuota, viene utilizzata la valuta della società per il contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="76743-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="76743-127">Gli argomenti `print currency name flag` e `decimal points` vengono analizzati solo per i codici lingua seguenti: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** e **RU**.</span><span class="sxs-lookup"><span data-stu-id="76743-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="76743-128">Inoltre, l'argomento `print currency name flag` viene analizzato solo per le società in cui il contesto del paese o area supporta la declinazione dei nomi valuta.</span><span class="sxs-lookup"><span data-stu-id="76743-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="76743-129">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="76743-129">Example 1</span></span>

<span data-ttu-id="76743-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` restituisce **"One Thousand Two Hundred Thirty Four and 56"**.</span><span class="sxs-lookup"><span data-stu-id="76743-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="76743-131">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="76743-131">Example 2</span></span>

<span data-ttu-id="76743-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` restituisce **"Sto dwadzieścia"**.</span><span class="sxs-lookup"><span data-stu-id="76743-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="76743-133">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="76743-133">Example 3</span></span>

<span data-ttu-id="76743-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` restituisce **"Сто двадцать евро 21 евроцент"**.</span><span class="sxs-lookup"><span data-stu-id="76743-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="76743-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="76743-135">Additional resources</span></span>

[<span data-ttu-id="76743-136">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="76743-136">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]