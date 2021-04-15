---
title: Funzione ER SPLITLIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLITLIST della creazione di report elettronici (ER).
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: 99e199e238b3132622a8b305895637b430e8f6d2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745571"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="2a9ae-103">Funzione ER SPLITLIST</span><span class="sxs-lookup"><span data-stu-id="2a9ae-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a9ae-104">La funzione `SPLITLIST` divide l'elenco specificato in elenchi secondari (o batch), ciascuno dei quali contiene il numero specificato di record.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="2a9ae-105">Quindi restituisce il risultato come nuovo valore *Elenco di record* costituito dai batch.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="2a9ae-106">Sintassi 1</span><span class="sxs-lookup"><span data-stu-id="2a9ae-106">Syntax 1</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a><span data-ttu-id="2a9ae-107">Sintassi 2</span><span class="sxs-lookup"><span data-stu-id="2a9ae-107">Syntax 2</span></span>

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a><span data-ttu-id="2a9ae-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2a9ae-108">Arguments</span></span>

<span data-ttu-id="2a9ae-109">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="2a9ae-109">`list`: *Record list*</span></span>

<span data-ttu-id="2a9ae-110">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="2a9ae-111">`number`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="2a9ae-111">`number`: *Integer*</span></span>

<span data-ttu-id="2a9ae-112">Il numero massimo di record per batch.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-112">The maximum number of records per batch.</span></span>

<span data-ttu-id="2a9ae-113">`on-demand reading flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="2a9ae-113">`on-demand reading flag`: *Boolean*</span></span>

<span data-ttu-id="2a9ae-114">Un valore *Booleano* che specifica se gli elementi degli elenchi secondari devono essere generati su richiesta.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-114">A *Boolean* value that specifies whether elements of sublists should be generated on demand.</span></span>

## <a name="return-values"></a><span data-ttu-id="2a9ae-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="2a9ae-115">Return values</span></span>

<span data-ttu-id="2a9ae-116">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="2a9ae-116">*Record list*</span></span>

<span data-ttu-id="2a9ae-117">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-117">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2a9ae-118">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="2a9ae-118">Usage notes</span></span>

<span data-ttu-id="2a9ae-119">L'elenco di batch restituito contiene i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="2a9ae-119">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="2a9ae-120">**Value:** *List*</span><span class="sxs-lookup"><span data-stu-id="2a9ae-120">**Value:** *List*</span></span>

    <span data-ttu-id="2a9ae-121">L'elenco dei record che appartengono al batch corrente.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-121">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="2a9ae-122">**BatchNumber:** *Intero*</span><span class="sxs-lookup"><span data-stu-id="2a9ae-122">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="2a9ae-123">Il numero del batch corrente nell'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-123">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="2a9ae-124">Quando il flag di lettura su richiesta è impostato su **True**, gli elenchi secondari vengono generati su richiesta, il che consente una riduzione del consumo di memoria ma può causare un degrado delle prestazioni se gli elementi non vengono utilizzati in sequenza.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-124">When the on-demand reading flag is set to **True**, sublists are generated upon request which allows for a reduction in memory consumption but may cause performance degradation if elements aren't used sequentially.</span></span>

## <a name="example"></a><span data-ttu-id="2a9ae-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a9ae-125">Example</span></span>

<span data-ttu-id="2a9ae-126">Nella seguente figura, un'origine dati **Lines** viene creata come un elenco di record contenente tre record.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-126">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="2a9ae-127">Questo elenco viene suddiviso in batch, ciascuno contenente fino a due record.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-127">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="2a9ae-128">Nella figura seguente è illustrato il layout di formato progettato.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-128">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="2a9ae-129">In questo layout di formato, le associazioni all'origine dati **Righe** vengono create per generare l'output in formato XML.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-129">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="2a9ae-130">Questo output presenta nodi individuali per ogni batch e i record contenuti.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-130">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="2a9ae-131">Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</span><span class="sxs-lookup"><span data-stu-id="2a9ae-131">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="2a9ae-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2a9ae-132">Additional resources</span></span>

[<span data-ttu-id="2a9ae-133">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="2a9ae-133">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
