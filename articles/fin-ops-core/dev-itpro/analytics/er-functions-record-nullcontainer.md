---
title: Funzione ER NULLCONTAINER
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLCONTAINER della creazione di report elettronici (ER).
author: NickSelin
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
ms.openlocfilehash: af6651ef3c62bd8d1285fa8179ac923d3c333ce7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746509"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="20eae-103">Funzione ER NULLCONTAINER</span><span class="sxs-lookup"><span data-stu-id="20eae-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20eae-104">La funzione `NULLCONTAINER` restituisce un valore *Contenitore (record)* nullo che ha la stessa struttura dell'elenco di record o del record specificato.</span><span class="sxs-lookup"><span data-stu-id="20eae-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="20eae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20eae-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="20eae-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="20eae-106">Arguments</span></span>

<span data-ttu-id="20eae-107">`list`: *Elenco di record* o *Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="20eae-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="20eae-108">Il percorso valido di un elemento di un'origine dati del tipo *Elenco di record* o *Contenitore (record)*.</span><span class="sxs-lookup"><span data-stu-id="20eae-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="20eae-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="20eae-109">Return values</span></span>

<span data-ttu-id="20eae-110">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="20eae-110">*Container (record)*</span></span>

<span data-ttu-id="20eae-111">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="20eae-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="20eae-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="20eae-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="20eae-113">Questa funzione è obsoleta.</span><span class="sxs-lookup"><span data-stu-id="20eae-113">This function is obsolete.</span></span> <span data-ttu-id="20eae-114">Usare invece la funzione `EMPTYRECORD`.</span><span class="sxs-lookup"><span data-stu-id="20eae-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="20eae-115">Per ulteriori informazioni, vedere [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="20eae-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="20eae-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="20eae-116">Example</span></span>

<span data-ttu-id="20eae-117">`NULLCONTAINER (SPLIT ("abc", 1))` restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="20eae-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="20eae-118">Per ulteriori informazioni, vedere [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="20eae-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="20eae-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="20eae-119">Additional resources</span></span>

[<span data-ttu-id="20eae-120">Funzioni di record</span><span class="sxs-lookup"><span data-stu-id="20eae-120">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]