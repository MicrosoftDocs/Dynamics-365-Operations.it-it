---
title: Funzione ER CASE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CASE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 69b76a06bcd3ba002d9543447e60afa14d5a6ce6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687028"
---
# <a name="case-er-function"></a><span data-ttu-id="ef50c-103">Funzione ER CASE</span><span class="sxs-lookup"><span data-stu-id="ef50c-103">CASE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef50c-104">La funzione `CASE` valuta il valore dell'espressione specificata rispetto alle opzioni alternative specificate e restituisce il risultato della prima opzione che è uguale al valore dell'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="ef50c-104">The `CASE` function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="ef50c-105">In caso contrario, restituisce il risultato predefinito facoltativo, se viene specificato un risultato predefinito come ultimo argomento della funzione richiamata che non è preceduto da un'opzione.</span><span class="sxs-lookup"><span data-stu-id="ef50c-105">Otherwise, it returns the optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="ef50c-106">Il valore restituito può essere un valore di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="ef50c-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef50c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef50c-107">Syntax</span></span>

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a><span data-ttu-id="ef50c-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ef50c-108">Arguments</span></span>

<span data-ttu-id="ef50c-109">`expression`: *Tipo di dati primitivo* (booleano, numerico o testo)</span><span class="sxs-lookup"><span data-stu-id="ef50c-109">`expression`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="ef50c-110">Un'espressione valida che restituisce un valore del tipo di dati primitivo.</span><span class="sxs-lookup"><span data-stu-id="ef50c-110">A valid expression that returns a value of the primitive data type.</span></span>

<span data-ttu-id="ef50c-111">`option 1`: *Tipo di dati primitivo* (booleano, numerico o testo)</span><span class="sxs-lookup"><span data-stu-id="ef50c-111">`option 1`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="ef50c-112">Un'espressione valida che restituisce un valore dello stesso tipo di dati primitivo come l'argomento `expression` della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="ef50c-112">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="ef50c-113">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ef50c-113">This argument is required.</span></span>

<span data-ttu-id="ef50c-114">`result 1`: *Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="ef50c-114">`result 1`: *Any of the supported data types*</span></span>

<span data-ttu-id="ef50c-115">Il risultato restituito che corrisponde all'opzione precedente.</span><span class="sxs-lookup"><span data-stu-id="ef50c-115">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="ef50c-116">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ef50c-116">This argument is required.</span></span>

<span data-ttu-id="ef50c-117">`option N`: *Tipo di dati primitivo* (booleano, numerico o testo)</span><span class="sxs-lookup"><span data-stu-id="ef50c-117">`option N`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="ef50c-118">Un'espressione valida che restituisce un valore dello stesso tipo di dati primitivo come l'argomento `expression` della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="ef50c-118">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="ef50c-119">Questo argomento è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ef50c-119">This argument is optional.</span></span>

<span data-ttu-id="ef50c-120">`result N`: *Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="ef50c-120">`result N`: *Any of the supported data types*</span></span>

<span data-ttu-id="ef50c-121">Il risultato restituito che corrisponde all'opzione precedente.</span><span class="sxs-lookup"><span data-stu-id="ef50c-121">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="ef50c-122">Questo argomento è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ef50c-122">This argument is optional.</span></span>

<span data-ttu-id="ef50c-123">`default result`: *Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="ef50c-123">`default result`: *Any of the supported data types*</span></span>

<span data-ttu-id="ef50c-124">Il risultato che dovrebbe essere restituito se non c'è corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ef50c-124">The result that should be returned if there is no match.</span></span> <span data-ttu-id="ef50c-125">Questo argomento è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ef50c-125">This argument is optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="ef50c-126">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="ef50c-126">Return values</span></span>

<span data-ttu-id="ef50c-127">*Qualsiasi tipo di dati supportato*</span><span class="sxs-lookup"><span data-stu-id="ef50c-127">*Any of the supported data types*</span></span>

<span data-ttu-id="ef50c-128">Il valore risultante di uno qualsiasi dei tipi di dati supportati.</span><span class="sxs-lookup"><span data-stu-id="ef50c-128">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ef50c-129">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="ef50c-129">Usage notes</span></span>

<span data-ttu-id="ef50c-130">Viene generata un'eccezione in fase di runtime se non vi è corrispondenza e non viene definito un risultato predefinito facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ef50c-130">An exception is thrown at runtime if there is no match and an optional default result isn't defined.</span></span>

<span data-ttu-id="ef50c-131">Tutti i risultati devono essere specificati utilizzando lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="ef50c-131">All results must be specified by using the same data type.</span></span> <span data-ttu-id="ef50c-132">In fase di progettazione viene generata un'eccezione se i tipi di dati dei risultati configurati non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="ef50c-132">An exception is thrown at design time if the data types of the configured results don't match.</span></span>

<span data-ttu-id="ef50c-133">Se il primo valore dei risultati e il valore dei risultati *N*-esimo sono valori del tipo di dati *Contenitore (record)* o *Elenco di record*, il risultato ha solo i campi esistenti in entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="ef50c-133">If the first result value and the *N* th result value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="ef50c-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef50c-134">Example</span></span>

<span data-ttu-id="ef50c-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` restituisce la stringa **"WINTER"** se la data della sessione dell'applicazione corrente è compresa tra ottobre e dicembre.</span><span class="sxs-lookup"><span data-stu-id="ef50c-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returns the string **"WINTER"** if the current application session date is between October and December.</span></span> <span data-ttu-id="ef50c-136">In caso contrario, restituisce una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="ef50c-136">Otherwise, it returns a blank string.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ef50c-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ef50c-137">Additional resources</span></span>

[<span data-ttu-id="ef50c-138">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="ef50c-138">Logical functions</span></span>](er-functions-category-logical.md)
