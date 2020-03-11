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
ms.openlocfilehash: ee51b6da008d1c0fcfb303e9659f507629237333
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042023"
---
# <span data-ttu-id="d985c-103"><a name="LIST">Funzione ER LIST</a></span><span class="sxs-lookup"><span data-stu-id="d985c-103"><a name="LIST">LIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d985c-104">La funzione `LIST` restituisce un valore *Elenco di record* costituito da un nuovo elenco di record creato dagli argomenti specificati.</span><span class="sxs-lookup"><span data-stu-id="d985c-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="d985c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d985c-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="d985c-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d985c-106">Arguments</span></span>

<span data-ttu-id="d985c-107">`record 1`: *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="d985c-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="d985c-108">Un riferimento a un'origine dati del tipo dati *Record*.</span><span class="sxs-lookup"><span data-stu-id="d985c-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="d985c-109">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d985c-109">This argument is required.</span></span>

<span data-ttu-id="d985c-110">`record N`: *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="d985c-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="d985c-111">Un riferimento a un'origine dati del tipo dati *Record*.</span><span class="sxs-lookup"><span data-stu-id="d985c-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="d985c-112">Questi argomenti aggiuntivi sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d985c-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="d985c-113">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="d985c-113">Return values</span></span>

<span data-ttu-id="d985c-114">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="d985c-114">*Record list*</span></span>

<span data-ttu-id="d985c-115">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="d985c-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d985c-116">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d985c-116">Usage notes</span></span>

<span data-ttu-id="d985c-117">La struttura dell'elenco che viene creato contiene solo i campi che sono presentati nella struttura di ogni record menzionato negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="d985c-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="d985c-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d985c-118">Example</span></span>

<span data-ttu-id="d985c-119">Immettere l'origine dati **Record 1**del tipo *Contenitore*.</span><span class="sxs-lookup"><span data-stu-id="d985c-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="d985c-120">Questa origine dati contiene i seguenti campi nidificati del tipo *Campo calcolato*:</span><span class="sxs-lookup"><span data-stu-id="d985c-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="d985c-121">**Codice:** Questo campo contiene un'espressione che restituisce un valore di tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="d985c-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="d985c-122">**Importo:** Questo campo contiene un'espressione che restituisce un valore di tipo *Reale*.</span><span class="sxs-lookup"><span data-stu-id="d985c-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="d985c-123">Immettere quindi l'origine dati **Record 2**del tipo *Contenitore*.</span><span class="sxs-lookup"><span data-stu-id="d985c-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="d985c-124">Questa origine dati contiene i seguenti campi nidificati del tipo *Campo calcolato*:</span><span class="sxs-lookup"><span data-stu-id="d985c-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="d985c-125">**Importo:** Questo campo contiene un'espressione che restituisce un valore di tipo *Reale*.</span><span class="sxs-lookup"><span data-stu-id="d985c-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="d985c-126">**IsValid:** Questo campo contiene un'espressione che restituisce un valore di tipo *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="d985c-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="d985c-127">In questo caso, l'espressione `LIST('Record 1', 'Record 2')`restituisce un nuovo elenco che contiene due record.</span><span class="sxs-lookup"><span data-stu-id="d985c-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="d985c-128">La struttura di questo elenco è composta da un singolo campo **Importo** di tipo *Reale*, perché questo campo è l'unico campo presentato in ogni argomento della funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="d985c-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d985c-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d985c-129">Additional resources</span></span>

[<span data-ttu-id="d985c-130">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="d985c-130">List functions</span></span>](er-functions-category-list.md)
