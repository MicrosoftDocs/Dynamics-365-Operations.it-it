---
title: Funzione ER CONTAINS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione di creazione di report elettronici (ER) CONTAINS.
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: c1d2d761a38d0edfb9abd439e0f710b336f54927
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745427"
---
# <a name="contains-er-function"></a><span data-ttu-id="ef8f9-103">Funzione ER CONTAINS</span><span class="sxs-lookup"><span data-stu-id="ef8f9-103">CONTAINS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef8f9-104">La funzione `CONTAINS` determina se l'input specificato contiene il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-104">The `CONTAINS` function determines whether the specified input contains the specified text.</span></span> <span data-ttu-id="ef8f9-105">Restituisce un valore *Booleano* **TRUE** se l'input specificato contiene il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-105">It returns a *Boolean* value of **TRUE** if the specified input contains the specified text.</span></span> <span data-ttu-id="ef8f9-106">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef8f9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef8f9-107">Syntax</span></span>

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a><span data-ttu-id="ef8f9-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ef8f9-108">Arguments</span></span>

<span data-ttu-id="ef8f9-109">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="ef8f9-109">`input`: *String*</span></span>

<span data-ttu-id="ef8f9-110">Il percorso valido di un elemento di un'origine dati di tipo *Stringa* o una costante di stringa, il cui valore potrebbe contenere il secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might contain the second argument.</span></span>

<span data-ttu-id="ef8f9-111">`search text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="ef8f9-111">`search text`: *String*</span></span>

<span data-ttu-id="ef8f9-112">Il percorso valido di un'origine dati del tipo di dati *Stringa* o una costante di stringa, il cui valore potrebbe contenere il primo argomento.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be contained in the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="ef8f9-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="ef8f9-113">Return values</span></span>

<span data-ttu-id="ef8f9-114">*Boolean*</span><span class="sxs-lookup"><span data-stu-id="ef8f9-114">*Boolean*</span></span>

<span data-ttu-id="ef8f9-115">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ef8f9-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="ef8f9-116">Usage notes</span></span>

<span data-ttu-id="ef8f9-117">Questa funzione può essere utilizzata per specificare un'espressione di condizione della funzione [FILTER](er-functions-list-filter.md) solo quando il mapping pertinente è configurato in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) per accedere a [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="ef8f9-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="ef8f9-118">Altrimenti, viene generata un'eccezione in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="ef8f9-119">Il messaggio ricevuto consiglia di utilizzare la funzione [WHERE](er-functions-list-where.md) anziché la funzione `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="ef8f9-120">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ef8f9-120">Example 1</span></span>

<span data-ttu-id="ef8f9-121">L'espressione `CONTAINS ("abc", "d")` restituisce **FALSE**, mentre l'espressione `CONTAINS ("abc", "C")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-121">The expression `CONTAINS ("abc", "d")` returns **FALSE**, whereas the expression `CONTAINS ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ef8f9-122">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="ef8f9-122">Example 2</span></span>

<span data-ttu-id="ef8f9-123">L'espressione `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` restituisce **TRUE** se il valore del campo **Indirizzo** dell'origine dati **modello** contiene la stringa **DEU**.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-123">The expression `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returns **TRUE** if the value of the **Address** field of the **model** data source contains the string **DEU**.</span></span> <span data-ttu-id="ef8f9-124">Altrimenti, restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="ef8f9-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ef8f9-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ef8f9-125">Additional resources</span></span>

[<span data-ttu-id="ef8f9-126">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="ef8f9-126">Logical functions</span></span>](er-functions-category-logical.md)
