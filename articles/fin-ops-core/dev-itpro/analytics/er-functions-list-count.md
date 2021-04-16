---
title: Funzione ER COUNT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione COUNT della creazione di report elettronici (ER).
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
ms.openlocfilehash: a0b780051684ef52d06a9baf78d9b513d9ac1f0e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746629"
---
# <a name="count-er-function"></a><span data-ttu-id="a3a25-103">Funzione ER COUNT</span><span class="sxs-lookup"><span data-stu-id="a3a25-103">COUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3a25-104">La funzione `COUNT` restituisce un valore *Intero* che rappresenta il numero di record nell'elenco specificato, se l'elenco non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="a3a25-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="a3a25-105">Se l'elenco è vuoto, questa funzione restituisce **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="a3a25-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="a3a25-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3a25-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="a3a25-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a3a25-107">Arguments</span></span>

<span data-ttu-id="a3a25-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="a3a25-108">`list`: *Record list*</span></span>

<span data-ttu-id="a3a25-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="a3a25-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a3a25-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a3a25-110">Return values</span></span>

<span data-ttu-id="a3a25-111">*Intero*</span><span class="sxs-lookup"><span data-stu-id="a3a25-111">*Integer*</span></span>

<span data-ttu-id="a3a25-112">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="a3a25-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="a3a25-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3a25-113">Example</span></span>

<span data-ttu-id="a3a25-114">`COUNT (SPLIT("abcd" , 3))` restituisce **2**, perché al funzione `SPLIT` utilizzata in questo esempio crea un elenco composto da due record.</span><span class="sxs-lookup"><span data-stu-id="a3a25-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3a25-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a3a25-115">Additional resources</span></span>

[<span data-ttu-id="a3a25-116">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="a3a25-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]