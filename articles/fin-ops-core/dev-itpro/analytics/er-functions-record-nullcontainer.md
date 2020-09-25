---
title: Funzione ER NULLCONTAINER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLCONTAINER della creazione di report elettronici (ER).
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
ms.openlocfilehash: dac6283ec35d3d03f586ca157048bd3ecc4bfa8a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743929"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="b0eb3-103">Funzione ER NULLCONTAINER</span><span class="sxs-lookup"><span data-stu-id="b0eb3-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0eb3-104">La funzione `NULLCONTAINER` restituisce un valore *Contenitore (record)* nullo che ha la stessa struttura dell'elenco di record o del record specificato.</span><span class="sxs-lookup"><span data-stu-id="b0eb3-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="b0eb3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0eb3-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="b0eb3-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b0eb3-106">Arguments</span></span>

<span data-ttu-id="b0eb3-107">`list`: *Elenco di record* o *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="b0eb3-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="b0eb3-108">Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record* o *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="b0eb3-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b0eb3-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="b0eb3-109">Return values</span></span>

<span data-ttu-id="b0eb3-110">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="b0eb3-110">*Container (record)*</span></span>

<span data-ttu-id="b0eb3-111">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="b0eb3-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b0eb3-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="b0eb3-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="b0eb3-113">Questa funzione è obsoleta.</span><span class="sxs-lookup"><span data-stu-id="b0eb3-113">This function is obsolete.</span></span> <span data-ttu-id="b0eb3-114">Usare invece la funzione `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="b0eb3-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="b0eb3-115">Per ulteriori informazioni, vedere [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="b0eb3-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="b0eb3-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0eb3-116">Example</span></span>

<span data-ttu-id="b0eb3-117">`NULLCONTAINER (SPLIT ("abc", 1))` restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="b0eb3-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="b0eb3-118">Per ulteriori informazioni, vedere [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="b0eb3-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0eb3-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0eb3-119">Additional resources</span></span>

[<span data-ttu-id="b0eb3-120">Funzioni di record</span><span class="sxs-lookup"><span data-stu-id="b0eb3-120">Record functions</span></span>](er-functions-category-record.md)
