---
title: Funzione ER INDEX
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione INDEX della creazione di report elettronici (ER).
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
ms.openlocfilehash: 45e95751e3adfe6aa208daaba774a349216e1f1f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042069"
---
# <span data-ttu-id="8be11-103"><a name="INDEX">Funzione ER INDEX</a></span><span class="sxs-lookup"><span data-stu-id="8be11-103"><a name="INDEX">INDEX ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8be11-104">La funzione `INDEX` restituisce un valore *Contenitore (record)* selezionato utilizzando l'indice numerico specificato nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="8be11-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="8be11-105">Viene generata un'eccezione se l'indice non rientra nell'intervallo dei record nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="8be11-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="8be11-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8be11-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="8be11-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8be11-107">Arguments</span></span>

<span data-ttu-id="8be11-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="8be11-108">`list`: *Record list*</span></span>

<span data-ttu-id="8be11-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="8be11-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="8be11-110">`index`: *Intero*</span><span class="sxs-lookup"><span data-stu-id="8be11-110">`index`: *Integer*</span></span>

<span data-ttu-id="8be11-111">Un indice numerico che indica la posizione del record desiderato nell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="8be11-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="8be11-112">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="8be11-112">Return values</span></span>

<span data-ttu-id="8be11-113">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="8be11-113">*Container (record)*</span></span>

<span data-ttu-id="8be11-114">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="8be11-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="8be11-115">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="8be11-115">Example 1</span></span>

<span data-ttu-id="8be11-116">Se si immette l'origine dati **DS** del tipo *Campo calcolato* e questo contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `DS.Value` restituisce il valore di testo **"B"** per il secondo record in questo elenco di record.</span><span class="sxs-lookup"><span data-stu-id="8be11-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="8be11-117">L'espressione `INDEX (SPLIT ("A|B|C", "|"), 2).Value` restituisce anche il valore del testo **"B"**.</span><span class="sxs-lookup"><span data-stu-id="8be11-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="8be11-118">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="8be11-118">Example 2</span></span>

<span data-ttu-id="8be11-119">Se si immette l'origine dati **DS**del tipo *Campo calcolato* e contiene l'espressione `SPLIT ("A|B|C", "|")`, l'espressione `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genera un'eccezione in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="8be11-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8be11-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8be11-120">Additional resources</span></span>

[<span data-ttu-id="8be11-121">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="8be11-121">List functions</span></span>](er-functions-category-list.md)
