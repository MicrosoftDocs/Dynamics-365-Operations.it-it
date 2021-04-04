---
title: Funzione ER NULLCONTAINER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLCONTAINER della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: d08a4a12d2b142744d3f35c6f1088ec25158c97c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563224"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="fb075-103">Funzione ER NULLCONTAINER</span><span class="sxs-lookup"><span data-stu-id="fb075-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb075-104">La funzione `NULLCONTAINER` restituisce un valore *Contenitore (record)* nullo che ha la stessa struttura dell'elenco di record o del record specificato.</span><span class="sxs-lookup"><span data-stu-id="fb075-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb075-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb075-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="fb075-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fb075-106">Arguments</span></span>

<span data-ttu-id="fb075-107">`list`: *Elenco di record* o *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="fb075-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="fb075-108">Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record* o *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="fb075-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="fb075-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="fb075-109">Return values</span></span>

<span data-ttu-id="fb075-110">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="fb075-110">*Container (record)*</span></span>

<span data-ttu-id="fb075-111">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="fb075-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fb075-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="fb075-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="fb075-113">Questa funzione è obsoleta.</span><span class="sxs-lookup"><span data-stu-id="fb075-113">This function is obsolete.</span></span> <span data-ttu-id="fb075-114">Usare invece la funzione `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="fb075-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="fb075-115">Per ulteriori informazioni, vedere [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="fb075-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="fb075-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb075-116">Example</span></span>

<span data-ttu-id="fb075-117">`NULLCONTAINER (SPLIT ("abc", 1))` restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="fb075-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="fb075-118">Per ulteriori informazioni, vedere [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="fb075-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb075-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb075-119">Additional resources</span></span>

[<span data-ttu-id="fb075-120">Funzioni di record</span><span class="sxs-lookup"><span data-stu-id="fb075-120">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]