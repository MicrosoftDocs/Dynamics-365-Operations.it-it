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
ms.openlocfilehash: 56ef02e3ea0ca2207ccdc79468a9ea4c1fbe8f95
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041885"
---
# <span data-ttu-id="fdd5f-103"><a name="SPLITLIST">Funzione ER SPLITLIST</a></span><span class="sxs-lookup"><span data-stu-id="fdd5f-103"><a name="SPLITLIST">SPLITLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fdd5f-104">La funzione `SPLITLIST` divide l'elenco specificato in elenchi secondari (o batch), ciascuno dei quali contiene il numero specificato di record.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="fdd5f-105">Quindi restituisce il risultato come nuovo valore *Elenco di record* costituito dai batch.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="fdd5f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdd5f-106">Syntax</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="fdd5f-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fdd5f-107">Arguments</span></span>

<span data-ttu-id="fdd5f-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fdd5f-108">`list`: *Record list*</span></span>

<span data-ttu-id="fdd5f-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="fdd5f-110">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="fdd5f-110">`number`: *Integer*</span></span>

<span data-ttu-id="fdd5f-111">Il numero massimo di record per batch.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="fdd5f-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="fdd5f-112">Return values</span></span>

<span data-ttu-id="fdd5f-113">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fdd5f-113">*Record list*</span></span>

<span data-ttu-id="fdd5f-114">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fdd5f-115">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="fdd5f-115">Usage notes</span></span>

<span data-ttu-id="fdd5f-116">L'elenco di batch restituito contiene i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="fdd5f-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="fdd5f-117">**Value:** *List*</span><span class="sxs-lookup"><span data-stu-id="fdd5f-117">**Value:** *List*</span></span>

    <span data-ttu-id="fdd5f-118">L'elenco dei record che appartengono al batch corrente.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="fdd5f-119">**BatchNumber:** *Intero*</span><span class="sxs-lookup"><span data-stu-id="fdd5f-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="fdd5f-120">Il numero del batch corrente nell'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="fdd5f-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="fdd5f-121">Example</span></span>

<span data-ttu-id="fdd5f-122">Nella seguente figura, un'origine dati **Lines** viene creata come un elenco di record contenente tre record.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="fdd5f-123">Questo elenco viene suddiviso in batch, ciascuno contenente fino a due record.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="fdd5f-124">Nella figura seguente è illustrato il layout di formato progettato.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="fdd5f-125">In questo layout di formato, le associazioni all'origine dati **Righe** vengono create per generare l'output in formato XML.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="fdd5f-126">Questo output presenta nodi individuali per ogni batch e i record contenuti.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="fdd5f-127">Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</span><span class="sxs-lookup"><span data-stu-id="fdd5f-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="fdd5f-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fdd5f-128">Additional resources</span></span>

[<span data-ttu-id="fdd5f-129">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="fdd5f-129">List functions</span></span>](er-functions-category-list.md)
