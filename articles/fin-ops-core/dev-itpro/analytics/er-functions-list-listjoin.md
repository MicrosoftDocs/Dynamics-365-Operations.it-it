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
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28f03e5e6af0f252a994f2e54b57a5ef654f4e67
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682245"
---
# <a name="listjoin-er-function"></a><span data-ttu-id="b7048-103">Funzione LISTJOIN ER</span><span class="sxs-lookup"><span data-stu-id="b7048-103">LISTJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7048-104">La funzione `LISTJOIN` restituisce un valore *Elenco di record* che rappresenta un nuovo elenco unito di record creato dagli argomenti specificati.</span><span class="sxs-lookup"><span data-stu-id="b7048-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7048-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7048-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="b7048-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b7048-106">Arguments</span></span>

<span data-ttu-id="b7048-107">`list 1`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="b7048-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="b7048-108">Un riferimento a un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="b7048-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="b7048-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7048-109">This argument is mandatory.</span></span>

<span data-ttu-id="b7048-110">`list N`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="b7048-110">`list N`: *Record list*</span></span>

<span data-ttu-id="b7048-111">Un riferimento a un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="b7048-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="b7048-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="b7048-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="b7048-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b7048-113">Return values</span></span>

<span data-ttu-id="b7048-114">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="b7048-114">*Record list*</span></span>

<span data-ttu-id="b7048-115">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="b7048-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b7048-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="b7048-116">Usage notes</span></span>

<span data-ttu-id="b7048-117">La struttura dell'elenco che viene creato contiene solo i campi presenti nella struttura di ogni elenco di record a cui si fa riferimento negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7048-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="b7048-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7048-118">Example</span></span>

<span data-ttu-id="b7048-119">Immettere l'origine dati **Record 1** del tipo `Container` .</span><span class="sxs-lookup"><span data-stu-id="b7048-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="b7048-120">Questa origine dati contiene i seguenti campi nidificati del tipo `Calculated field`</span><span class="sxs-lookup"><span data-stu-id="b7048-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="b7048-121">**Codice**: Questo campo contiene un'espressione che restituisce un valore del tipo`String` .</span><span class="sxs-lookup"><span data-stu-id="b7048-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="b7048-122">**Importo**: Questo campo contiene un'espressione che restituisce un valore del tipo`Real` .</span><span class="sxs-lookup"><span data-stu-id="b7048-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="b7048-123">Inserire quindi l'origine dati **Record 2** del tipo `Container` .</span><span class="sxs-lookup"><span data-stu-id="b7048-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="b7048-124">Questa origine dati contiene i seguenti campi nidificati del tipo `Calculated field`</span><span class="sxs-lookup"><span data-stu-id="b7048-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="b7048-125">**Importo**: Questo campo contiene un'espressione che restituisce un valore del tipo`Real` .</span><span class="sxs-lookup"><span data-stu-id="b7048-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="b7048-126">**Funzione**: Questo campo contiene un'espressione che restituisce un valore del tipo`Boolean` .</span><span class="sxs-lookup"><span data-stu-id="b7048-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Pagina della progettazione mapping modello di ER](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="b7048-128">In questo caso, l'espressione `LISTJOIN(LIST('Record 1'), LIST('Record 2'))`restituisce un nuovo elenco che contiene due record.</span><span class="sxs-lookup"><span data-stu-id="b7048-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Pagina di progettazione del mapping di modello ER con due record](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="b7048-130">La struttura di questo elenco è costituita da un singolo campo **Importo** di tipo `Real`, perché questo campo è l'unico campo che viene presentato in ogni argomento della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="b7048-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Campo dell'importo della pagina di progettazione del mapping di modello ER](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="b7048-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b7048-132">Additional resources</span></span>

[<span data-ttu-id="b7048-133">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="b7048-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="b7048-134">Eseguire il debug delle origini dati di un formato ER eseguito per analizzare il flusso e la trasformazione dei dati</span><span class="sxs-lookup"><span data-stu-id="b7048-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)
