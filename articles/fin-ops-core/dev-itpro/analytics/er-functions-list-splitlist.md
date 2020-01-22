---
title: Funzione ER SPLITLIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLITLIST della creazione di report elettronici (ER).
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
ms.openlocfilehash: b324d42a53b35074ba62ccf3df7b77cb4db70450
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917214"
---
# <span data-ttu-id="3b536-103"><a name="SPLITLIST">Funzione ER SPLITLIST</a></span><span class="sxs-lookup"><span data-stu-id="3b536-103"><a name="SPLITLIST">SPLITLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b536-104">La funzione `SPLITLIST` divide l'elenco specificato in elenchi secondari (o batch), ciascuno dei quali contiene il numero specificato di record.</span><span class="sxs-lookup"><span data-stu-id="3b536-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="3b536-105">Quindi restituisce il risultato come nuovo valore *Elenco di record* costituito dai batch.</span><span class="sxs-lookup"><span data-stu-id="3b536-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b536-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b536-106">Syntax</span></span>

```
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="3b536-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3b536-107">Arguments</span></span>

<span data-ttu-id="3b536-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="3b536-108">`list`: *Record list*</span></span>

<span data-ttu-id="3b536-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="3b536-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="3b536-110">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="3b536-110">`number`: *Integer*</span></span>

<span data-ttu-id="3b536-111">Il numero massimo di record per batch.</span><span class="sxs-lookup"><span data-stu-id="3b536-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="3b536-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="3b536-112">Return values</span></span>

<span data-ttu-id="3b536-113">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="3b536-113">*Record list*</span></span>

<span data-ttu-id="3b536-114">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="3b536-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3b536-115">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="3b536-115">Usage notes</span></span>

<span data-ttu-id="3b536-116">L'elenco di batch restituito contiene i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="3b536-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="3b536-117">**Value:** *List*</span><span class="sxs-lookup"><span data-stu-id="3b536-117">**Value:** *List*</span></span>

    <span data-ttu-id="3b536-118">L'elenco dei record che appartengono al batch corrente.</span><span class="sxs-lookup"><span data-stu-id="3b536-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="3b536-119">**BatchNumber:** *Intero*</span><span class="sxs-lookup"><span data-stu-id="3b536-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="3b536-120">Il numero del batch corrente nell'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="3b536-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="3b536-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b536-121">Example</span></span>

<span data-ttu-id="3b536-122">Nella seguente figura, un'origine dati **Lines** viene creata come un elenco di record contenente tre record.</span><span class="sxs-lookup"><span data-stu-id="3b536-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="3b536-123">Questo elenco viene suddiviso in batch, ciascuno contenente fino a due record.</span><span class="sxs-lookup"><span data-stu-id="3b536-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="3b536-124">Nella figura seguente è illustrato il layout di formato progettato.</span><span class="sxs-lookup"><span data-stu-id="3b536-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="3b536-125">In questo layout di formato, le associazioni all'origine dati **Righe** vengono create per generare l'output in formato XML.</span><span class="sxs-lookup"><span data-stu-id="3b536-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="3b536-126">Questo output presenta nodi individuali per ogni batch e i record contenuti.</span><span class="sxs-lookup"><span data-stu-id="3b536-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="3b536-127">Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</span><span class="sxs-lookup"><span data-stu-id="3b536-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="3b536-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3b536-128">Additional resources</span></span>

[<span data-ttu-id="3b536-129">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="3b536-129">List functions</span></span>](er-functions-category-list.md)
