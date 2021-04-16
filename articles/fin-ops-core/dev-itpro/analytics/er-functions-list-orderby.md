---
title: Funzione ER ORDERBY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ORDERBY della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 51da7f3766f5af901c8be6668bc2511cd8e2f9e9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753194"
---
# <a name="orderby-er-function"></a><span data-ttu-id="1c1d9-103">Funzione ER ORDERBY</span><span class="sxs-lookup"><span data-stu-id="1c1d9-103">ORDERBY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c1d9-104">La funzione `ORDERBY` restituisce l'elenco specificato come un valore *Elenco di record* dopo che è stato ordinato in base agli argomenti specificati.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="1c1d9-105">Questi argomenti possono essere definiti come espressioni.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="1c1d9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c1d9-106">Syntax</span></span>

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="1c1d9-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1c1d9-107">Arguments</span></span>

<span data-ttu-id="1c1d9-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="1c1d9-108">`list`: *Record list*</span></span>

<span data-ttu-id="1c1d9-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="1c1d9-110">`expression 1`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="1c1d9-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="1c1d9-111">Il percorso valido di un campo dell'origine dati a cui fa riferimento l'argomento `list` della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="1c1d9-112">Il campo di riferimento deve essere un campo del tipo di dati primitivo.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="1c1d9-113">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-113">This argument is required.</span></span>

<span data-ttu-id="1c1d9-114">`expression N`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="1c1d9-114">`expression N`: *Field*</span></span>

<span data-ttu-id="1c1d9-115">Il percorso valido di un campo dell'origine dati a cui fa riferimento l'argomento `list` della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="1c1d9-116">Il campo di riferimento deve essere un campo del tipo di dati primitivo.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="1c1d9-117">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="1c1d9-118">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="1c1d9-118">Return values</span></span>

<span data-ttu-id="1c1d9-119">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="1c1d9-119">*Record list*</span></span>

<span data-ttu-id="1c1d9-120">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="1c1d9-121">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="1c1d9-121">Example 1</span></span>

<span data-ttu-id="1c1d9-122">Se si immette l'origine dati **DS** del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("C|B|A", "|")`, l'espressione `FIRST( ORDERBY( DS, DS. Value)).Value` restituisce il valore di testo **"A"**.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1c1d9-123">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="1c1d9-123">Example 2</span></span>

<span data-ttu-id="1c1d9-124">Se **Vendor** è configurato come origine dati della creazione di report elettronici (ER) che fa riferimento alla tabella VendTable, l'espressione `ORDERBY (Vendors, Vendors.'name()')` restituisce un elenco di fornitori ordinato per nome in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="1c1d9-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c1d9-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1c1d9-125">Additional resources</span></span>

[<span data-ttu-id="1c1d9-126">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="1c1d9-126">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]