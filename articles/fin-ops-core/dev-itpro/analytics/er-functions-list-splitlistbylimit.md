---
title: Funzione ER SPLITLISTBYLIMIT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SPLITLISTBYLIMIT della creazione di report elettronici (ER).
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
ms.openlocfilehash: 54c78f36c93e1bdb472b84fc7ca6428d20088bad
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041862"
---
# <span data-ttu-id="7845a-103"><a name="SPLITLISTBYLIMIT">Funzione ER SPLITLISTBYLIMIT</a></span><span class="sxs-lookup"><span data-stu-id="7845a-103"><a name="SPLITLISTBYLIMIT">SPLITLISTBYLIMIT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7845a-104">La funzione `SPLITLISTBYLIMIT` divide l'elenco specificato in un nuovo elenco di elenchi secondari (batch).</span><span class="sxs-lookup"><span data-stu-id="7845a-104">The `SPLITLISTBYLIMIT` function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="7845a-105">Il numero di record in ciascun batch viene calcolato dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="7845a-105">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="7845a-106">La funzione restituisce quindi il risultato come nuovo valore *Elenco di record* costituito dai batch.</span><span class="sxs-lookup"><span data-stu-id="7845a-106">The function then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="7845a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7845a-107">Syntax</span></span>

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a><span data-ttu-id="7845a-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7845a-108">Arguments</span></span>

<span data-ttu-id="7845a-109">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="7845a-109">`list`: *Record list*</span></span>

<span data-ttu-id="7845a-110">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="7845a-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="7845a-111">`limit value`: *Intero* o *Reale*</span><span class="sxs-lookup"><span data-stu-id="7845a-111">`limit value`: *Integer* or *Real*</span></span>

<span data-ttu-id="7845a-112">Il valore massimo del limite utilizzato per dividere l'elenco originale in batch.</span><span class="sxs-lookup"><span data-stu-id="7845a-112">The maximum value of the limit that is used to split the original list into batches.</span></span>

<span data-ttu-id="7845a-113">`limit source`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="7845a-113">`limit source`: *Field*</span></span>

<span data-ttu-id="7845a-114">Il percorso valido di un campo di tipo *Intero*o *Reale* nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="7845a-114">The valid path of a field of the *Integer* or *Real* type in the specified list.</span></span> <span data-ttu-id="7845a-115">Il valore di questo campo definisce di quanto viene aumentata la somma totale.</span><span class="sxs-lookup"><span data-stu-id="7845a-115">The value of this field defines the step that the total sum is increased on.</span></span>

## <a name="return-values"></a><span data-ttu-id="7845a-116">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="7845a-116">Return values</span></span>

<span data-ttu-id="7845a-117">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="7845a-117">*Record list*</span></span>

<span data-ttu-id="7845a-118">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="7845a-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7845a-119">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="7845a-119">Usage notes</span></span>

<span data-ttu-id="7845a-120">L'elenco di batch restituito contiene i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="7845a-120">The list of batches that is returned contains the following elements:</span></span>

- <span data-ttu-id="7845a-121">**Value**: *List*</span><span class="sxs-lookup"><span data-stu-id="7845a-121">**Value**: *List*</span></span>

    <span data-ttu-id="7845a-122">L'elenco dei record che appartengono al batch corrente.</span><span class="sxs-lookup"><span data-stu-id="7845a-122">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="7845a-123">**BatchNumber**: *Intero*</span><span class="sxs-lookup"><span data-stu-id="7845a-123">**BatchNumber**: *Integer*</span></span>

    <span data-ttu-id="7845a-124">Il numero del batch corrente nell'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="7845a-124">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="7845a-125">Il limite non è applicato a un singolo articolo dell'elenco originale se l'origine limite supera il limite definito.</span><span class="sxs-lookup"><span data-stu-id="7845a-125">The limit isn't applied to a single item of the original list if the limit source exceeds the defined limit.</span></span>

## <a name="example"></a><span data-ttu-id="7845a-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="7845a-126">Example</span></span>

<span data-ttu-id="7845a-127">L'illustrazione seguente mostra un formato creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="7845a-127">The following illustration shows an Electronic reporting (ER) format.</span></span>

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

<span data-ttu-id="7845a-128">Nella figura seguente vengono mostrate le origini dati che vengono utilizzate per il formato.</span><span class="sxs-lookup"><span data-stu-id="7845a-128">The following illustration shows the data sources that are used for the format.</span></span>

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

<span data-ttu-id="7845a-129">Nella figura seguente è illustrato il risultato dell'esecuzione del formato.</span><span class="sxs-lookup"><span data-stu-id="7845a-129">The following illustration shows the result when the format is run.</span></span> <span data-ttu-id="7845a-130">In questo caso, l'output è un elenco di voci doganali.</span><span class="sxs-lookup"><span data-stu-id="7845a-130">In this case, the output is a flat list of commodity items.</span></span>

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

<span data-ttu-id="7845a-131">Nelle illustrazioni seguenti, lo stesso formato è stato rettificato per presentare l'elenco di voci doganali in batch se un singolo batch deve includere voci doganali e il peso totale non deve superare il limite di 9.</span><span class="sxs-lookup"><span data-stu-id="7845a-131">In the following illustrations, the same format has been adjusted so that it presents the list of commodity items in batches if a single batch must include commodities and the total weight should not exceed a limit of 9.</span></span>

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

<span data-ttu-id="7845a-132">Nella figura seguente è illustrato il risultato dell'esecuzione del formato rettificato.</span><span class="sxs-lookup"><span data-stu-id="7845a-132">The following illustration shows the result when the adjusted format is run.</span></span>

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> <span data-ttu-id="7845a-133">Il limite non si applica all'ultima voce dell'elenco originale poiché il valore (**11**) dell'origine del limite (**weight**) supera il limite definito (**9**).</span><span class="sxs-lookup"><span data-stu-id="7845a-133">The limit isn't applied to the last item of the original list, because the value (**11**) of the limit source (**weight**) exceeds the defined limit (**9**).</span></span> <span data-ttu-id="7845a-134">Per ignorare gli elenchi secondari durante la generazione del report, utilizzare la funzione `WHERE` o l'espressione **Enabled** dell'elemento formato corrispondente come necessario.</span><span class="sxs-lookup"><span data-stu-id="7845a-134">To ignore sublists during report generation, use either the `WHERE` function or the **Enabled** expression of the corresponding format element, as you require.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7845a-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7845a-135">Additional resources</span></span>

[<span data-ttu-id="7845a-136">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="7845a-136">List functions</span></span>](er-functions-category-list.md)
