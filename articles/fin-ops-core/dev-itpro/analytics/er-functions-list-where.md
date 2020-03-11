---
title: Funzione ER WHERE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione WHERE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 392cf7acebd7ad95bcc0f5d4b7a67500a412a795
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041835"
---
# <span data-ttu-id="2f31e-103"><a name="WHERE">Funzione ER WHERE</a></span><span class="sxs-lookup"><span data-stu-id="2f31e-103"><a name="WHERE">WHERE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f31e-104">La funzione `WHERE` restituisce l'elenco specificato come un valore *Elenco di record* dopo che è stato filtrato in base alla condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="2f31e-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f31e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f31e-105">Syntax</span></span>

```vb
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="2f31e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2f31e-106">Arguments</span></span>

<span data-ttu-id="2f31e-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="2f31e-107">`list`: *Record list*</span></span>

<span data-ttu-id="2f31e-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="2f31e-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="2f31e-109">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="2f31e-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="2f31e-110">Un'espressione condizionale valida utilizzata per filtrare i record dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="2f31e-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="2f31e-111">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2f31e-111">Return values</span></span>

<span data-ttu-id="2f31e-112">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="2f31e-112">*Record list*</span></span>

<span data-ttu-id="2f31e-113">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="2f31e-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2f31e-114">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="2f31e-114">Usage notes</span></span>

<span data-ttu-id="2f31e-115">Questa funzione è diversa dalla funzione [FILTER](er-functions-list-filter.md), perché la condizione specificata viene applicata a qualsiasi origine dati della creazione di report elettronici (ER) del tipo di *Elenco di record* presenti in memoria.</span><span class="sxs-lookup"><span data-stu-id="2f31e-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="2f31e-116">Se gli argomenti configurati per questa funzione (`list` e `condition`) non consentono di convertire questa richiesta nella chiamata SQL diretta, al momento della progettazione viene generato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="2f31e-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="2f31e-117">Questo messaggio informa l'utente che le prestazioni potrebbero essere migliorate se la funzione [v](er-functions-list-filter.md) viene utilizzata al posto della funzione `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="2f31e-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="2f31e-118">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="2f31e-118">Example 1</span></span>

<span data-ttu-id="2f31e-119">Se viene configurato **Vendor** come origine dati ER che fa riferimento alla tabella VendTable, l'espressione `WHERE (Vendors, Vendors.VendGroup = "40")` restituisce un elenco solo dei fornitori che appartengono al gruppo 40.</span><span class="sxs-lookup"><span data-stu-id="2f31e-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="2f31e-120">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="2f31e-120">Example 2</span></span>

<span data-ttu-id="2f31e-121">Se si immette l'origine dati **DS** del tipo *Campo calcolato* e questo contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `WHERE( DS, DS.Value = "B")` restituisce un elenco di un solo record che contiene il testo **"B"** nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="2f31e-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2f31e-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2f31e-122">Additional resources</span></span>

[<span data-ttu-id="2f31e-123">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="2f31e-123">List functions</span></span>](er-functions-category-list.md)
