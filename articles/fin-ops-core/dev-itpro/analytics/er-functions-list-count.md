---
title: Funzione ER COUNT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione COUNT della creazione di report elettronici (ER).
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
ms.openlocfilehash: 2d29b82a8c3b108f7651e6d593cb17e7ec8ca872
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916248"
---
# <span data-ttu-id="4046e-103"><a name="COUNT">Funzione ER COUNT</a></span><span class="sxs-lookup"><span data-stu-id="4046e-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4046e-104">La funzione `COUNT` restituisce un valore *Intero* che rappresenta il numero di record nell'elenco specificato, se l'elenco non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="4046e-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="4046e-105">Se l'elenco è vuoto, questa funzione restituisce **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="4046e-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="4046e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4046e-106">Syntax</span></span>

```
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="4046e-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4046e-107">Arguments</span></span>

<span data-ttu-id="4046e-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="4046e-108">`list`: *Record list*</span></span>

<span data-ttu-id="4046e-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="4046e-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="4046e-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="4046e-110">Return values</span></span>

<span data-ttu-id="4046e-111">*Intero*</span><span class="sxs-lookup"><span data-stu-id="4046e-111">*Integer*</span></span>

<span data-ttu-id="4046e-112">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="4046e-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="4046e-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="4046e-113">Example</span></span>

<span data-ttu-id="4046e-114">`COUNT (SPLIT("abcd" , 3))` restituisce **2**, perché al funzione `SPLIT` utilizzata in questo esempio crea un elenco composto da due record.</span><span class="sxs-lookup"><span data-stu-id="4046e-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4046e-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4046e-115">Additional resources</span></span>

[<span data-ttu-id="4046e-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="4046e-116">List functions</span></span>](er-functions-category-list.md)
