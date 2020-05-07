---
title: 'Funzione LISTJOIN ER '
description: In questo argomento vengono fornite informazioni sull'utilizzo della funzione LISTJOIN Electronic reporting (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249037"
---
# <a name=""></a><span data-ttu-id="73ebf-103"><a name="LISTJOIN">Funzione LISTJOIN ER</a></span><span class="sxs-lookup"><span data-stu-id="73ebf-103"><a name="LISTJOIN">LISTJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73ebf-104">La funzione `LISTJOIN` restituisce un valore *Elenco di record* che rappresenta un nuovo elenco unito di record creato dagli argomenti specificati.</span><span class="sxs-lookup"><span data-stu-id="73ebf-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="73ebf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73ebf-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="73ebf-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="73ebf-106">Arguments</span></span>

<span data-ttu-id="73ebf-107">`list 1`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="73ebf-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="73ebf-108">Un riferimento a un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="73ebf-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="73ebf-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="73ebf-109">This argument is mandatory.</span></span>

<span data-ttu-id="73ebf-110">`list N`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="73ebf-110">`list N`: *Record list*</span></span>

<span data-ttu-id="73ebf-111">Un riferimento a un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="73ebf-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="73ebf-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="73ebf-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="73ebf-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="73ebf-113">Return values</span></span>

<span data-ttu-id="73ebf-114">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="73ebf-114">*Record list*</span></span>

<span data-ttu-id="73ebf-115">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="73ebf-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="73ebf-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="73ebf-116">Usage notes</span></span>

<span data-ttu-id="73ebf-117">La struttura dell'elenco che viene creato contiene solo i campi presenti nella struttura di ogni elenco di record a cui si fa riferimento negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="73ebf-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="73ebf-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="73ebf-118">Example</span></span>

<span data-ttu-id="73ebf-119">Immettere l'origine dati **Record 1** del tipo `Container` .</span><span class="sxs-lookup"><span data-stu-id="73ebf-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="73ebf-120">Questa origine dati contiene i seguenti campi nidificati del tipo `Calculated field`</span><span class="sxs-lookup"><span data-stu-id="73ebf-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="73ebf-121">**Codice**: Questo campo contiene un'espressione che restituisce un valore del tipo`String` .</span><span class="sxs-lookup"><span data-stu-id="73ebf-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="73ebf-122">**Importo**: Questo campo contiene un'espressione che restituisce un valore del tipo`Real` .</span><span class="sxs-lookup"><span data-stu-id="73ebf-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="73ebf-123">Inserire quindi l'origine dati **Record 2** del tipo `Container` .</span><span class="sxs-lookup"><span data-stu-id="73ebf-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="73ebf-124">Questa origine dati contiene i seguenti campi nidificati del tipo `Calculated field`</span><span class="sxs-lookup"><span data-stu-id="73ebf-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="73ebf-125">**Importo**: Questo campo contiene un'espressione che restituisce un valore del tipo`Real` .</span><span class="sxs-lookup"><span data-stu-id="73ebf-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="73ebf-126">**Funzione**: Questo campo contiene un'espressione che restituisce un valore del tipo`Boolean` .</span><span class="sxs-lookup"><span data-stu-id="73ebf-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

<span data-ttu-id="73ebf-127">In questo caso, l'espressione `LISTJOIN(LIST('Record 1'), LIST('Record 2'))`restituisce un nuovo elenco che contiene due record.</span><span class="sxs-lookup"><span data-stu-id="73ebf-127">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span> <span data-ttu-id="73ebf-128">La struttura di questo elenco è costituita da un singolo campo**Importo** di tipo `Real`, perché questo campo è l'unico campo che viene presentato in ogni argomento della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="73ebf-128">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73ebf-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="73ebf-129">Additional resources</span></span>

[<span data-ttu-id="73ebf-130">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="73ebf-130">List functions</span></span>](er-functions-category-list.md)