---
title: Funzione ER STARTSWITH
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione di creazione di report elettronici (ER) STARTSWITH.
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
ms.openlocfilehash: ef7e9c88abff2b4b58ecb8abf1e69f7853f9b3fa
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751682"
---
# <a name="startswith-er-function"></a><span data-ttu-id="ae84f-103">Funzione ER STARTSWITH</span><span class="sxs-lookup"><span data-stu-id="ae84f-103">STARTSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae84f-104">La funzione `STARTSWITH` determina se l'input specificato inizia con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="ae84f-104">The `STARTSWITH` function determines whether the specified input starts with the specified text.</span></span> <span data-ttu-id="ae84f-105">Restituisce un valore *Booleano* **TRUE** se l'input specificato inizia con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="ae84f-105">It returns a *Boolean* value of **TRUE** if the specified input starts with the specified text.</span></span> <span data-ttu-id="ae84f-106">In caso contrario, restituisce il valore *Booleano* **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="ae84f-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae84f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae84f-107">Syntax</span></span>

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a><span data-ttu-id="ae84f-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ae84f-108">Arguments</span></span>

<span data-ttu-id="ae84f-109">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="ae84f-109">`input`: *String*</span></span>

<span data-ttu-id="ae84f-110">Il percorso valido di un elemento di un'origine dati di tipo *Stringa* o una costante di stringa, il cui valore potrebbe iniziare con il secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="ae84f-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might start with the second argument.</span></span>

<span data-ttu-id="ae84f-111">`start text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="ae84f-111">`start text`: *String*</span></span>

<span data-ttu-id="ae84f-112">Il percorso valido di un'origine dati del tipi di dati *Stringa* o una costante di stringa, il cui valore potrebbe essere all'inizio del primo argomento.</span><span class="sxs-lookup"><span data-stu-id="ae84f-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the beginning of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="ae84f-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="ae84f-113">Return values</span></span>

<span data-ttu-id="ae84f-114">*Boolean*</span><span class="sxs-lookup"><span data-stu-id="ae84f-114">*Boolean*</span></span>

<span data-ttu-id="ae84f-115">Il valore *Booleano* risultante.</span><span class="sxs-lookup"><span data-stu-id="ae84f-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ae84f-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="ae84f-116">Usage notes</span></span>

<span data-ttu-id="ae84f-117">Questa funzione può essere utilizzata per specificare un'espressione di condizione della funzione [FILTER](er-functions-list-filter.md) solo quando il mapping pertinente è configurato in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) per accedere a [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="ae84f-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="ae84f-118">Altrimenti, viene generata un'eccezione in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ae84f-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="ae84f-119">Il messaggio ricevuto consiglia di utilizzare la funzione [WHERE](er-functions-list-where.md) anziché la funzione `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="ae84f-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="ae84f-120">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ae84f-120">Example 1</span></span>

<span data-ttu-id="ae84f-121">L'espressione `STARTSWITH ("abc", "d")` restituisce **FALSE**, mentre l'espressione `STARTSWITH ("abc", "A")` restituisce **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="ae84f-121">The expression `STARTSWITH ("abc", "d")` returns **FALSE**, whereas the expression `STARTSWITH ("abc", "A")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ae84f-122">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="ae84f-122">Example 2</span></span>

<span data-ttu-id="ae84f-123">L'espressione `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` restituisce **TRUE** se il valore del campo **Indirizzo** dell'origine dati **modello** inizia con la stringa **123 Coffee Street**.</span><span class="sxs-lookup"><span data-stu-id="ae84f-123">The expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` returns **TRUE** if the value of the **Address** field of the **model** data source starts with the string **123 Coffee Street**.</span></span> <span data-ttu-id="ae84f-124">Altrimenti, restituisce **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="ae84f-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ae84f-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ae84f-125">Additional resources</span></span>

[<span data-ttu-id="ae84f-126">Funzioni logiche</span><span class="sxs-lookup"><span data-stu-id="ae84f-126">Logical functions</span></span>](er-functions-category-logical.md)
