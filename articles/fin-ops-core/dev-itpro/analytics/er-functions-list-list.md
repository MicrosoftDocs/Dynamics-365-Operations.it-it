---
title: Funzione ER LIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LIST della creazione di report elettronici (ER).
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
ms.openlocfilehash: a31288885abda69873ae23b28a36e2a54852f593
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745155"
---
# <a name="list-er-function"></a><span data-ttu-id="57787-103">Funzione ER LIST</span><span class="sxs-lookup"><span data-stu-id="57787-103">LIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57787-104">La funzione `LIST` restituisce un valore *Elenco di record* costituito da un nuovo elenco di record creato dagli argomenti specificati.</span><span class="sxs-lookup"><span data-stu-id="57787-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="57787-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57787-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="57787-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="57787-106">Arguments</span></span>

<span data-ttu-id="57787-107">`record 1`: *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="57787-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="57787-108">Un riferimento a un'origine dati del tipo dati *Record*.</span><span class="sxs-lookup"><span data-stu-id="57787-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="57787-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="57787-109">This argument is required.</span></span>

<span data-ttu-id="57787-110">`record N`: *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="57787-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="57787-111">Un riferimento a un'origine dati del tipo dati *Record*.</span><span class="sxs-lookup"><span data-stu-id="57787-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="57787-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="57787-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="57787-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="57787-113">Return values</span></span>

<span data-ttu-id="57787-114">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="57787-114">*Record list*</span></span>

<span data-ttu-id="57787-115">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="57787-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="57787-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="57787-116">Usage notes</span></span>

<span data-ttu-id="57787-117">La struttura dell'elenco che viene creato contiene solo i campi che sono presentati nella struttura di ogni record menzionato negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="57787-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="57787-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="57787-118">Example</span></span>

<span data-ttu-id="57787-119">Immettere l'origine dati **Record 1**del tipo *Contenitore*.</span><span class="sxs-lookup"><span data-stu-id="57787-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="57787-120">Questa origine dati contiene i seguenti campi nidificati del tipo *Campo calcolato*:</span><span class="sxs-lookup"><span data-stu-id="57787-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="57787-121">**Codice:** Questo campo contiene un'espressione che restituisce un valore di tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="57787-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="57787-122">**Importo:** Questo campo contiene un'espressione che restituisce un valore di tipo *Reale*.</span><span class="sxs-lookup"><span data-stu-id="57787-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="57787-123">Immettere quindi l'origine dati **Record 2**del tipo *Contenitore*.</span><span class="sxs-lookup"><span data-stu-id="57787-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="57787-124">Questa origine dati contiene i seguenti campi nidificati del tipo *Campo calcolato*:</span><span class="sxs-lookup"><span data-stu-id="57787-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="57787-125">**Importo:** Questo campo contiene un'espressione che restituisce un valore di tipo *Reale*.</span><span class="sxs-lookup"><span data-stu-id="57787-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="57787-126">**IsValid:** Questo campo contiene un'espressione che restituisce un valore di tipo *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="57787-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="57787-127">In questo caso, l'espressione `LIST('Record 1', 'Record 2')`restituisce un nuovo elenco che contiene due record.</span><span class="sxs-lookup"><span data-stu-id="57787-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="57787-128">La struttura di questo elenco è composta da un singolo campo **Importo** di tipo *Reale*, perché questo campo è l'unico campo presentato in ogni argomento della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="57787-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57787-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="57787-129">Additional resources</span></span>

[<span data-ttu-id="57787-130">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="57787-130">List functions</span></span>](er-functions-category-list.md)
